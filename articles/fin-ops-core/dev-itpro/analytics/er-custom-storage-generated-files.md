---
title: Określanie niestandardowych lokalizacji przechowywania wygenerowanych dokumentów
description: W tym temacie wyjaśniono, jak rozszerzyć listę lokalizacji przechowywania dokumentów generowanych przez formaty modułu Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 83b2d3c35e3e68aaad22bc03a46b17abc1526073895057717fd055dacdfbee5c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718484"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a>Określanie niestandardowych lokalizacji przechowywania wygenerowanych dokumentów

[!include[banner](../includes/banner.md)]

Interfejs API raportowania elektronicznego pozwala rozszerzyć listę lokalizacji, w których można przechowywać dokumenty generowane przez funkcję raportowania elektronicznego. W tym temacie opisano sposób dodawania niestandardowej lokalizacji przechowywania dla generowanych dokumentów poprzez oddelegowanie zadania tworzenia miejsc docelowych modułu ER do fabryki domyślnego miejsca docelowego, a następnie zaimplementowanie niestandardowej klasy mającej własną logikę lokalizacji docelowej.

## <a name="prerequisites"></a>Wymagania wstępne

Wdróż topologię, która obsługuje ciągłą kompilację. Więcej informacji znajdziesz w [Wdrażanie topologii obsługujących ciągłą budowę i automatyzację testów](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation). Musisz mieć dostęp do tej topologii w jednej z następujących ról:

- Deweloper raportowania elektronicznego
- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

Ponadto musisz także mieć dostęp do środowiska programowania dla tej topologii.

Wszystkie zadania przedstawione w tym temacie można wykonać w kontekście firmy **USMF**.

## <a name="import-the-fixed-asset-roll-forward-er-format"></a>Importowanie formatu ER Przesunięcie środków trwałych do przodu

Aby wygenerować dokumenty, dla których ma zostać dodana niestandardowa lokalizacja przechowywania, [zaimportuj](er-download-configurations-global-repo.md) konfigurację formatu ER **Przesunięcie środków trwałych do przodu** do bieżącej topologii.

![Strona Repozytorium konfiguracji.](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a>Uruchamianie raportu Przesunięcie środków trwałych do przodu

1. Wybierz kolejno opcje **Środki trwałe** \> **Zapytania i raporty** \> **Raporty transakcji** \> **Przesunięcie środków trwałych do przodu**.
2. W polu **Od dnia** wpisz **1.1.2017** (1 stycznia 2017 r.).
3. W polu **Do dnia** wpisz **31.1.2017** (31 stycznia 2017 r.).
4. W polu **Waluta** wybierz **Waluta rozliczeniowa**.
5. W polu **Mapowanie formatu** wybierz opcję **Przesunięcie środków trwałych do przodu**.
6. Kliknij przycisk **OK**.

![Okno dialogowe środowiska uruchomieniowego dla raportu Przesunięcie środków trwałych do przodu.](./media/er-custom-storage-generated-files-runtime-dialog.png)

W programie Microsoft Excel przejrzyj dokument wychodzący, który został wygenerowany i jest dostępny do pobrania. To zachowanie jest [domyślnym zachowaniem](electronic-reporting-destinations.md#default-behavior) dla formatu ER, dla którego nie są skonfigurowane żadne [miejsca docelowe](electronic-reporting-destinations.md) i który działa w trybie interaktywnym.

## <a name="review-the-source-code"></a>Przejrzenie kodu źródłowego

Przejrzyj kod metody `generateReportByGER()` w klasie `AssetRollForwardService`. Zauważ, że do wywołania struktury ER i wygenerowania raportu **Przesunięcie środków trwałych do przodu** jest używana metoda `Run()`.

```xpp
class AssetRollForwardService extends SysOperationServiceBase
{
    public const str ERFormatModelName = 'Fixed assets';
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'AssetRollForward';

    /// <summary>
    /// Generates report by general electronic reporting
    /// </summary>
    /// <param name = "_contract">The Asset Period Statement contract</param>
    public void generateReportByGER(AssetRollForwardContract _contract)
    {
        ERFormatMappingId   formatMappingId;
        AssetRollForwardDP  dataProvider;
        AssetRollForwardTmp assetRollForwardTmp;
        Query               query;

        query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
        dataProvider = AssetRollForwardDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

        if (assetRollForwardTmp)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                // Call ER to generate the report.
                ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName)
                    .withParameter(parameters)
                    .withFileDestination(_contract.getFileDestination())
                    .run();
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

## <a name="modify-the-source-code"></a>Modyfikacja kodu źródłowego

1. W projekcie w programie Visual Studio dodaj nową klasę (w tym przykładzie `AssetRollForwardDestination`) i wpisz kod źródłowy, który zaimplementuje niestandardową lokalizację docelową dla generowanych raportów **Przesunięcie środków trwałych do przodu**.

    - Metoda `new()` jest przeznaczona do pobierania oryginalnego obiektu miejsca docelowego ER oraz parametru opartego na logice aplikacji określającego niestandardową lokalizację, w której mają być przechowywane wygenerowane raporty. W tym przykładzie niestandardową lokalizacją jest nazwa folderu w lokalnym systemie plików na serwerze, na którym jest uruchomiona usługa serwera obiektów aplikacji (AOS).
    - Metoda `saveFile()` jest przeznaczona do zapisywania wygenerowanego dokumentu w folderze lokalnego systemu plików serwera, na którym jest uruchomiona usługa AOS.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;

    /// <summary>
    /// Destination class for <c>AssetRollForwardDestinationFactory</c> that stores a generated report.
    /// </summary>
    public class AssetRollForwardDestination implements ERIFileDestination
    {
        private ERIFileDestination originDestination;
        private str TargetFolder;

        /// <summary>
        /// Creates a stream for new file.
        /// </summary>
        /// <param name = "_fileName">Name of a new file.</param>
        /// <returns>Stream for new file.</returns>
        public System.IO.Stream newFileStream(System.String _fileName)
        {
            return originDestination.newFileStream(_fileName);
        }

        /// <summary>
        /// Saves file in destination.
        /// </summary>
        /// <param name = "_stream">A stream to save.</param>
        /// <param name = "_fileName">A file name.</param>
        /// <returns>Saved stream.</returns>
        public System.IO.Stream saveFile(System.IO.Stream _stream, System.String _fileName)
        {
            _stream.Seek(0, System.IO.SeekOrigin::Begin);
            using (var localStream = System.IO.File::OpenWrite(TargetFolder + _fileName))
            {
                _stream.CopyTo(localStream);
            }
            return _stream;
        }

        /// <summary>
        /// Constructs destination for fixed asset roll forward report.
        /// </summary>
        /// <param name = "_originDestination">The original destination.</param>
        /// <param name = "_TargetFoder">The folder to store a report that's being created.</param>
        /// <returns>The fixed asset roll forward destination.</returns>
        public static AssetRollForwardDestination construct(ERIFileDestination _originDestination, str _TargetFoder)
        {
            return new AssetRollForwardDestination(_originDestination, _TargetFoder);
        }

        protected void new(ERIFileDestination _originDestination, str _TargetFoder)
        {
            originDestination = _originDestination;
            TargetFolder = _TargetFoder;
        }
    }
    ```

2. W projekcie programu Visual Studio dodaj nową klasę (w tym przykładzie `AssetRollForwardDestinationFactory`) i wpisz kod źródłowy, który skonfiguruje fabrykę niestandardowego miejsca docelowego delegującą tworzenie miejsca docelowego do fabryki domyślnego miejsca docelowego oraz zawinie plikowe miejsce docelowe w miejsce docelowe ustawione przez Ciebie.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    using Microsoft.Dynamics365.LocalizationFramework.Format.FileGeneration;

    /// <summary>
    /// Destination factory for using <c>AssetRollForwardDestinationFactory</c>.
    /// </summary>
    public class AssetRollForwardDestinationFactory implements ERIFileDestinationFactory, ERIFileDestinationFactoryPostProcessor
    {
        private ERIFileDestinationFactory originDestinationFactory;
        private str TargetFolder;

        /// <summary>
        /// Creates file destination for print management.
        /// </summary>
        /// <param name = "_fileDestination">A default file destination.</param>
        /// <param name = "_identification">An identification strategy.</param>
        /// <param name = "_rootContext">A root context.</param>
        /// <param name = "_root">A root element.</param>
        /// <returns>A file destination.</returns>
        public ERIDataDrivenFileDestination createPrintMgmtDestination(
            ERIFileDestination _fileDestination,
            ERIObjectIdentificationStrategy _identification,
            ERTextFormatDataContext _rootContext,
            ERTextFormatIFileComponent _root)
        {
            ERIDataDrivenFileDestination dataDrivenDestination = originDestinationFactory.createPrintMgmtDestination(
                _fileDestination,
                _identification,
                _rootContext,
                _root);

            IFileDestinationHost fileDestinationHost = dataDrivenDestination as IFileDestinationHost;
            if (fileDestinationHost)
            {
                fileDestinationHost.FileDestination = AssetRollForwardDestination::construct(
                    fileDestinationHost.get_FileDestination(),
                    TargetFolder);
            }

            return dataDrivenDestination;
        }

        /// <summary>
        /// Constructs the fixed asset roll forward destination factory.
        /// </summary>
        /// <param name = "_originDestinationFactory">The original destination.</param>
        /// <param name = "_TargetFolder">The string containing a folder name that corresponds to the report, that's being created.</param>
        /// <returns>The destination factory for the fixed asset roll forward report.</returns>
        public static AssetRollForwardDestinationFactory construct(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            AssetRollForwardDestinationFactory destinationFactory = new AssetRollForwardDestinationFactory(_originDestinationFactory, _TargetFolder);

            ERIFileDestinationFactoryPostProcessorsHost factoryPostProcessing = ERCast::asObject(destinationFactory.originDestinationFactory) as ERIFileDestinationFactoryPostProcessorsHost;

            if (factoryPostProcessing)
            {
                factoryPostProcessing.addDestinationPostProcessor(destinationFactory);
            }
            return destinationFactory;
        }

        public ERIFileDestination processDestinationAfterCreation(ERIFileDestination _sourceDestination)
        {
            return AssetRollForwardDestination::construct(_sourceDestination, TargetFolder);
        }

        protected void new(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            originDestinationFactory = _originDestinationFactory;
            TargetFolder = _TargetFolder;
        }
    }
    ```

3. Zmodyfikuj istniejącą klasę `AssetRollForwardService` i wpisz kod źródłowy, który skonfiguruje fabrykę niestandardowego miejsca docelowego dla modułu uruchamiającego raport. Zauważ, że podczas konstruowania fabryki niestandardowego miejsca docelowego jest przekazywany parametr oparty na aplikacji, który określa folder docelowy. W ten sposób folder docelowy jest używany do przechowywania wygenerowanych plików.

    > [!NOTE] 
    > Upewnij się, że podany folder (w tym przykładzie **c:\\0**) jest obecny w lokalnym systemie plików serwera, na którym jest uruchomiona usługa AOS. W przeciwnym razie w czasie wykonywania zostanie zgłoszony wyjątek [DirectoryNotFoundException](/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1).

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    /// <summary>
    /// The electronic reporting service class for fixed asset roll forward report
    /// </summary>
    class AssetRollForwardService extends SysOperationServiceBase
    {
        public const str ERFormatModelName = 'Fixed assets';
        public const str ERModelDataSourceName = 'model';
        public const str DefaultExportedFileName = 'AssetRollForward';

        /// <summary>
        /// Generates report by general electronic reporting
        /// </summary>
        /// <param name = "_contract">The Asset Period Statement contract</param>
        public void generateReportByGER(AssetRollForwardContract _contract)
        {
            ERFormatMappingId   formatMappingId;
            AssetRollForwardDP  dataProvider;
            AssetRollForwardTmp assetRollForwardTmp;
            Query               query;

            query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
            dataProvider = AssetRollForwardDP::construct();
            formatMappingId = _contract.parmFormatMapping();
            assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

            if (assetRollForwardTmp)
            {
                try
                {
                    ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                        .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                        .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                    // Call ER to generate the report.
                    ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());

                    ERIFileDestinationFactoryHost factoryHost = ERCast::asObject(formatMappingRun) as ERIFileDestinationFactoryHost;
                    if (factoryHost)
                    {
                        ERIFileDestinationFactory fileDestinationFactory = factoryHost.getFileDestinationFactory();
                        factoryHost.setFileDestinationFactory(AssetRollForwardDestinationFactory::construct(fileDestinationFactory, @'c:\0\'));
                        formatMappingRun.run();
                    }
                }
                catch
                {
                    // An error occurred while exporting data.
                    error("@SYP4861341");
                }
            }
            else
            {
                // There is no data available.
                info("@SYS300117");
            }
        }
    }
    ```

4. Zmodyfikuj projekt.

## <a name="re-run-the-fixed-asset-roll-forward-report"></a>Ponowne uruchamianie raportu Przesunięcie środków trwałych do przodu

1. Wybierz kolejno opcje **Środki trwałe** \> **Zapytania i raporty** \> **Raporty transakcji** \> **Przesunięcie środków trwałych do przodu**.
2. W polu **Od dnia** wprowadź wartość **1.1.2017**.
3. W polu **Do dnia** wprowadź wartość **31.1.2017**.
4. W polu **Waluta** wybierz **Waluta rozliczeniowa**.
5. W polu **Mapowanie formatu** wybierz opcję **Przesunięcie środków trwałych do przodu**.
6. Kliknij przycisk **OK**.
7. Przejdź do lokalnego folderu **C:\\0** i znajdź wygenerowany plik.

> [!NOTE]
> Ponieważ w tym przykładzie obiekt `originDestination` nie jest używany w obiekcie `AssetRollForwardDestination`, konfiguracje dla [miejsc docelowych](electronic-reporting-destinations.md) formatu ER będą ignorowane w czasie wykonywania.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)
- [Możliwości rozszerzania — strona główna](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]