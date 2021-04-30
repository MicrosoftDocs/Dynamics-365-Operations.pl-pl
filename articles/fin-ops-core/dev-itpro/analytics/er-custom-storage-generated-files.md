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
ms.openlocfilehash: bd979bf5369b6878caaee82fc9c6a40d363cc165
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894155"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a><span data-ttu-id="2a828-103">Określanie niestandardowych lokalizacji przechowywania wygenerowanych dokumentów</span><span class="sxs-lookup"><span data-stu-id="2a828-103">Specify custom storage locations for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2a828-104">Interfejs API raportowania elektronicznego pozwala rozszerzyć listę lokalizacji, w których można przechowywać dokumenty generowane przez funkcję raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="2a828-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="2a828-105">W tym temacie opisano sposób dodawania niestandardowej lokalizacji przechowywania dla generowanych dokumentów poprzez oddelegowanie zadania tworzenia miejsc docelowych modułu ER do fabryki domyślnego miejsca docelowego, a następnie zaimplementowanie niestandardowej klasy mającej własną logikę lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="2a828-105">This topic explains how to add a custom storage location for generated documents by delegating the task of creating ER destinations to the default destination factory and then implementing a custom class that has its own destination logic.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2a828-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2a828-106">Prerequisites</span></span>

<span data-ttu-id="2a828-107">Wdróż topologię, która obsługuje ciągłą kompilację.</span><span class="sxs-lookup"><span data-stu-id="2a828-107">Deploy a topology that supports continuous build.</span></span> <span data-ttu-id="2a828-108">Więcej informacji znajdziesz w [Wdrażanie topologii obsługujących ciągłą budowę i automatyzację testów](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span><span class="sxs-lookup"><span data-stu-id="2a828-108">For more information, see [Deploy topologies that support continuous build and test automation](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span></span> <span data-ttu-id="2a828-109">Musisz mieć dostęp do tej topologii w jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="2a828-109">You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="2a828-110">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="2a828-110">Electronic reporting developer</span></span>
- <span data-ttu-id="2a828-111">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="2a828-111">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="2a828-112">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="2a828-112">System administrator</span></span>

<span data-ttu-id="2a828-113">Ponadto musisz także mieć dostęp do środowiska programowania dla tej topologii.</span><span class="sxs-lookup"><span data-stu-id="2a828-113">You must also have access to the development environment for this topology.</span></span>

<span data-ttu-id="2a828-114">Wszystkie zadania przedstawione w tym temacie można wykonać w kontekście firmy **USMF**.</span><span class="sxs-lookup"><span data-stu-id="2a828-114">All the tasks in this topic can be completed in the **USMF** company.</span></span>

## <a name="import-the-fixed-asset-roll-forward-er-format"></a><span data-ttu-id="2a828-115">Importowanie formatu ER Przesunięcie środków trwałych do przodu</span><span class="sxs-lookup"><span data-stu-id="2a828-115">Import the Fixed asset roll forward ER format</span></span>

<span data-ttu-id="2a828-116">Aby wygenerować dokumenty, dla których ma zostać dodana niestandardowa lokalizacja przechowywania, [zaimportuj](er-download-configurations-global-repo.md) konfigurację formatu ER **Przesunięcie środków trwałych do przodu** do bieżącej topologii.</span><span class="sxs-lookup"><span data-stu-id="2a828-116">To generate the documents that you plan to add a custom storage location for, [import](er-download-configurations-global-repo.md) the **Fixed asset roll forward** ER format configuration into the current topology.</span></span>

![Strona Repozytorium konfiguracji](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="2a828-118">Uruchamianie raportu Przesunięcie środków trwałych do przodu</span><span class="sxs-lookup"><span data-stu-id="2a828-118">Run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="2a828-119">Wybierz kolejno opcje **Środki trwałe** \> **Zapytania i raporty** \> **Raporty transakcji** \> **Przesunięcie środków trwałych do przodu**.</span><span class="sxs-lookup"><span data-stu-id="2a828-119">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="2a828-120">W polu **Od dnia** wpisz **1.1.2017** (1 stycznia 2017 r.).</span><span class="sxs-lookup"><span data-stu-id="2a828-120">In the **From date** field, enter **1/1/2017** (January 1, 2017).</span></span>
3. <span data-ttu-id="2a828-121">W polu **Do dnia** wpisz **31.1.2017** (31 stycznia 2017 r.).</span><span class="sxs-lookup"><span data-stu-id="2a828-121">In the **To date** field, enter **1/31/2017** (January 31, 2017).</span></span>
4. <span data-ttu-id="2a828-122">W polu **Waluta** wybierz **Waluta rozliczeniowa**.</span><span class="sxs-lookup"><span data-stu-id="2a828-122">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="2a828-123">W polu **Mapowanie formatu** wybierz opcję **Przesunięcie środków trwałych do przodu**.</span><span class="sxs-lookup"><span data-stu-id="2a828-123">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="2a828-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a828-124">Select **OK**.</span></span>

![Okno dialogowe środowiska uruchomieniowego dla raportu Przesunięcie środków trwałych do przodu](./media/er-custom-storage-generated-files-runtime-dialog.png)

<span data-ttu-id="2a828-126">W programie Microsoft Excel przejrzyj dokument wychodzący, który został wygenerowany i jest dostępny do pobrania.</span><span class="sxs-lookup"><span data-stu-id="2a828-126">In Microsoft Excel, review the outbound document that is generated and available for download.</span></span> <span data-ttu-id="2a828-127">To zachowanie jest [domyślnym zachowaniem](electronic-reporting-destinations.md#default-behavior) dla formatu ER, dla którego nie są skonfigurowane żadne [miejsca docelowe](electronic-reporting-destinations.md) i który działa w trybie interaktywnym.</span><span class="sxs-lookup"><span data-stu-id="2a828-127">This behavior is the [default behavior](electronic-reporting-destinations.md#default-behavior) for an ER format that no [destinations](electronic-reporting-destinations.md) are configured for, and that is running in interactive mode.</span></span>

## <a name="review-the-source-code"></a><span data-ttu-id="2a828-128">Przejrzenie kodu źródłowego</span><span class="sxs-lookup"><span data-stu-id="2a828-128">Review the source code</span></span>

<span data-ttu-id="2a828-129">Przejrzyj kod metody `generateReportByGER()` w klasie `AssetRollForwardService`.</span><span class="sxs-lookup"><span data-stu-id="2a828-129">Review the code of the `generateReportByGER()` method of the `AssetRollForwardService` class.</span></span> <span data-ttu-id="2a828-130">Zauważ, że do wywołania struktury ER i wygenerowania raportu **Przesunięcie środków trwałych do przodu** jest używana metoda `Run()`.</span><span class="sxs-lookup"><span data-stu-id="2a828-130">Notice that the `Run()` method is used to call the ER framework and generate the **Fixed asset roll forward** report.</span></span>

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

## <a name="modify-the-source-code"></a><span data-ttu-id="2a828-131">Modyfikacja kodu źródłowego</span><span class="sxs-lookup"><span data-stu-id="2a828-131">Modify the source code</span></span>

1. <span data-ttu-id="2a828-132">W projekcie w programie Visual Studio dodaj nową klasę (w tym przykładzie `AssetRollForwardDestination`) i wpisz kod źródłowy, który zaimplementuje niestandardową lokalizację docelową dla generowanych raportów **Przesunięcie środków trwałych do przodu**.</span><span class="sxs-lookup"><span data-stu-id="2a828-132">In your Visual Studio project, add a new class (`AssetRollForwardDestination` in this example), and write code to implement your custom destination for **Fixed asset roll forward** reports that are generated.</span></span>

    - <span data-ttu-id="2a828-133">Metoda `new()` jest przeznaczona do pobierania oryginalnego obiektu miejsca docelowego ER oraz parametru opartego na logice aplikacji określającego niestandardową lokalizację, w której mają być przechowywane wygenerowane raporty.</span><span class="sxs-lookup"><span data-stu-id="2a828-133">The `new()` method is designed to get the original ER destination object and the application logic–driven parameter that specifies the custom location where generated reports should be stored.</span></span> <span data-ttu-id="2a828-134">W tym przykładzie niestandardową lokalizacją jest nazwa folderu w lokalnym systemie plików na serwerze, na którym jest uruchomiona usługa serwera obiektów aplikacji (AOS).</span><span class="sxs-lookup"><span data-stu-id="2a828-134">In this example, the custom location is the name of a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    - <span data-ttu-id="2a828-135">Metoda `saveFile()` jest przeznaczona do zapisywania wygenerowanego dokumentu w folderze lokalnego systemu plików serwera, na którym jest uruchomiona usługa AOS.</span><span class="sxs-lookup"><span data-stu-id="2a828-135">The `saveFile()` method is designed to save a generated document to a folder of the local file system of the server that runs the AOS service.</span></span>

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

2. <span data-ttu-id="2a828-136">W projekcie programu Visual Studio dodaj nową klasę (w tym przykładzie `AssetRollForwardDestinationFactory`) i wpisz kod źródłowy, który skonfiguruje fabrykę niestandardowego miejsca docelowego delegującą tworzenie miejsca docelowego do fabryki domyślnego miejsca docelowego oraz zawinie plikowe miejsce docelowe w miejsce docelowe ustawione przez Ciebie.</span><span class="sxs-lookup"><span data-stu-id="2a828-136">In your Visual Studio project, add a new class (`AssetRollForwardDestinationFactory` in this example), and write code to set up a custom destination factory that delegates the creation of a destination to the default destination factory, and to wrap a file destination with your own destination.</span></span>

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

3. <span data-ttu-id="2a828-137">Zmodyfikuj istniejącą klasę `AssetRollForwardService` i wpisz kod źródłowy, który skonfiguruje fabrykę niestandardowego miejsca docelowego dla modułu uruchamiającego raport.</span><span class="sxs-lookup"><span data-stu-id="2a828-137">Modify the existing `AssetRollForwardService` class, and write code to set up a custom destination factory for the report runner.</span></span> <span data-ttu-id="2a828-138">Zauważ, że podczas konstruowania fabryki niestandardowego miejsca docelowego jest przekazywany parametr oparty na aplikacji, który określa folder docelowy.</span><span class="sxs-lookup"><span data-stu-id="2a828-138">Notice that when a custom destination factory is constructed, the application-driven parameter that specifies a target folder is passed.</span></span> <span data-ttu-id="2a828-139">W ten sposób folder docelowy jest używany do przechowywania wygenerowanych plików.</span><span class="sxs-lookup"><span data-stu-id="2a828-139">In this way, that target folder is used to store generated files.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="2a828-140">Upewnij się, że podany folder (w tym przykładzie **c:\\0**) jest obecny w lokalnym systemie plików serwera, na którym jest uruchomiona usługa AOS.</span><span class="sxs-lookup"><span data-stu-id="2a828-140">Make sure that the specified folder (**c:\\0** in this example) is present in the local file system of the server that runs the AOS service.</span></span> <span data-ttu-id="2a828-141">W przeciwnym razie w czasie wykonywania zostanie zgłoszony wyjątek [DirectoryNotFoundException](/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1).</span><span class="sxs-lookup"><span data-stu-id="2a828-141">Otherwise, a [DirectoryNotFoundException](/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) exception will be thrown at runtime.</span></span>

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

4. <span data-ttu-id="2a828-142">Zmodyfikuj projekt.</span><span class="sxs-lookup"><span data-stu-id="2a828-142">Rebuild your project.</span></span>

## <a name="re-run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="2a828-143">Ponowne uruchamianie raportu Przesunięcie środków trwałych do przodu</span><span class="sxs-lookup"><span data-stu-id="2a828-143">Re-run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="2a828-144">Wybierz kolejno opcje **Środki trwałe** \> **Zapytania i raporty** \> **Raporty transakcji** \> **Przesunięcie środków trwałych do przodu**.</span><span class="sxs-lookup"><span data-stu-id="2a828-144">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="2a828-145">W polu **Od dnia** wprowadź wartość **1.1.2017**.</span><span class="sxs-lookup"><span data-stu-id="2a828-145">In the **From date** field, enter **1/1/2017**.</span></span>
3. <span data-ttu-id="2a828-146">W polu **Do dnia** wprowadź wartość **31.1.2017**.</span><span class="sxs-lookup"><span data-stu-id="2a828-146">In the **To date** field, enter **1/31/2017**.</span></span>
4. <span data-ttu-id="2a828-147">W polu **Waluta** wybierz **Waluta rozliczeniowa**.</span><span class="sxs-lookup"><span data-stu-id="2a828-147">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="2a828-148">W polu **Mapowanie formatu** wybierz opcję **Przesunięcie środków trwałych do przodu**.</span><span class="sxs-lookup"><span data-stu-id="2a828-148">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="2a828-149">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a828-149">Select **OK**.</span></span>
7. <span data-ttu-id="2a828-150">Przejdź do lokalnego folderu **C:\\0** i znajdź wygenerowany plik.</span><span class="sxs-lookup"><span data-stu-id="2a828-150">Browse the local **C:\\0** folder to find the generated file.</span></span>

> [!NOTE]
> <span data-ttu-id="2a828-151">Ponieważ w tym przykładzie obiekt `originDestination` nie jest używany w obiekcie `AssetRollForwardDestination`, konfiguracje dla [miejsc docelowych](electronic-reporting-destinations.md) formatu ER będą ignorowane w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="2a828-151">Because the `originDestination` object isn't used in the `AssetRollForwardDestination` object in this example, the configurations for the ER format [destinations](electronic-reporting-destinations.md) will be ignored at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2a828-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2a828-152">Additional resources</span></span>

- [<span data-ttu-id="2a828-153">Miejsca docelowe raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="2a828-153">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="2a828-154">Możliwości rozszerzania — strona główna</span><span class="sxs-lookup"><span data-stu-id="2a828-154">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]