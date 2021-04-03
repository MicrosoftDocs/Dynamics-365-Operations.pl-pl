---
title: Określanie lokalizacji niestandardowego magazynu wygenerowanych dokumentów
description: W tym temacie wyjaśniono, jak rozszerzyć listę lokalizacji przechowywania dokumentów generowanych przez raportowanie elektroniczne.
author: NickSelin
manager: AnnBe
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: b71ad5a9701922eb94b1d611e2d3f6a945ce6c06
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562245"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a>Określanie lokalizacji niestandardowego magazynu wygenerowanych dokumentów

[!include[banner](../includes/banner.md)]

Interfejs API raportowania elektronicznego pozwala rozszerzyć listę lokalizacji, w których można przechowywać dokumenty generowane przez funkcję raportowania elektronicznego. Ten temat zawiera przegląd głównych zadań, które należy wykonać, aby dodać niestandardowe miejsce przechowywania.

## <a name="prerequisites"></a>Wymagania wstępne

Należy wdrożyć topologię, która obsługuje ciągłą kompilację. (Aby uzyskać więcej informacji, zobacz [Wdrażanie topologii, która obsługuje ciągłą kompilację i automatyzację testowania](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) Musisz mieć dostęp do tej topologii dla jednej z następujących ról:

- Deweloper raportowania elektronicznego
- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

Ponadto musisz także mieć dostęp do środowiska programowania dla tej topologii.

## <a name="create-or-import-an-er-format-configuration"></a>Tworzenie lub importowanie konfiguracji formatu raportowania elektronicznego

W bieżącej topologii [utwórz nowy format raportowania elektronicznego](tasks/er-format-configuration-2016-11.md) do generowania dokumentów, dla których chcesz dodać niestandardową lokalizację przechowywania. Alternatywnie [Zaimportuj istniejący format raportowania elektronicznego do tej topologii](general-electronic-reporting-manage-configuration-lifecycle.md).

![Strona projektanta formatu](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> Format raportowania elektronicznego, który tworzysz lub importujesz, musi zawierać co najmniej jedenz następujących elementów formatu:
>
> - Plik
> - Folder
> - Scalenie
> - Załącznik

## <a name="create-a-new-document-type"></a>Tworzenie nowego typu dokumentu

Aby określić, jak dokumenty, które generuje format raportowania elektronicznego są kierowane, należy skonfigurować [Lokalizacje docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md). W każdym miejscu docelowym raportowania elektronicznego, które jest skonfigurowane do przechowywania wygenerowanych dokumentów jako plików należy określić typ dokumentu struktury zarządzania dokumentami. Różne typy dokumentów mogą służyć do kierowania dokumentów generowanych przez raportowanie elektroniczne.

1. Dodaj nowy [typu dokumentu](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) dla formatu raportowania elektronicznego utworzonego lub zaimportowanego wcześniej. Na ilustracji typem dokumentu jest **FileX**.
2. W celu odróżnienia tego typu dokumentu od innych zamieść specjalne słowo kluczowe w jego nazwie. Na przykład na ilustracji poniżej, nazwa jest **(LOKALNY) folder**.
3. W polu **klasy** wybierz **Dołącz plik**.
4. W polu **grupa** wybierz **Plik**.

![Strona Typy dokumentów](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> Typy dokumentów są specyficzne dla firmy. Aby użyć formatu raportowania elektronicznego ze skonfigurowanym miejscem docelowym w wielu firmach, musisz skonfigurować osobny typ dokumentu w każdej firmie.

## <a name="review-source-code"></a>Przejrzyj kod źródłowy

Przejrzyj kod metody **insertFile()** w klasie **ERDocuManagement**. Należy zauważyć, że zdarzenie **AttachingFile()** jest wywoływane, gdy wygenerowany plik jest dołączony do rekordu.


```xpp
/// <summary>
/// Inserts file as attachment in Document Management.
/// </summary>
/// <param name = "_owner">A record as the attachment owner.</param>
/// <param name = "_stream">The file stream.</param>
/// <param name = "_filePath">The file path with name.</param>
/// <param name = "_attachmentName">The name of file attachment.</param>
/// <returns>The reference to inserted file.</returns>
[Hookable(false)]
public DocuRef insertFile(
    Common _owner, 
    System.IO.Stream _stream, 
    str _filePath, 
    str _attachmentName, 
    DocuTypeId _docuTypeId)
{
    DocuRef docuRef;
    if (_stream)
    {
        DocuType::createDefaults();
        if (!this.isDocuTypeValid(_docuTypeId))
        {
            throw error(strFmt("@ElectronicReporting:DocuTypeIsNotValid", _docuTypeId));
        }
        var args = ERDocuManagementAttachingFileEventArgs::construct(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        ERDocuManagementEvents::onAttachingFile(args);
        if (args.isHandled())
        {
            docuRef = args.getDocuRef();
        }
        else
        {
            docuRef = this.attachFile(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        }
    }
    return docuRef;
}
```

Zdarzenie **AttachingFile()** jest wywoływane po przetworzeniu następujących miejsc docelowych raportowania elektronicznego:

- **Archiwum** — kiedy jest używana ta lokalizacja, jest tworzony nowy rekord dla formatu raportowania elektronicznego w tabeli ERFormatMappingRunJobTable. Pole **Archiwizacji** w tym rekordzie jest ustawione jako **Fałsz**. Jeśli format raportowania elektronicznego zostanie pomyślnie uruchomiony, wygenerowany dokument będzie dołączony do rekordu i zostanie wywołane zdarzenie **AttachingFile()**. Typ dokumentu, który jest wybrany w tym miejscu docelowym elektronicznego raportowania określa lokalizację przechowywania dla dołączonego pliku (Microsoft Azure lub folder SharePoint).
- **Archiwum zadania** — kiedy jest używana ta lokalizacja, jest tworzony nowy rekord dla formatu raportowania elektronicznego w tabeli ERFormatMappingRunJobTable. Pole **Archiwizacji** w tym rekordzie jest ustawione jako **Prawda**. Jeśli format raportowania elektronicznego zostanie pomyślnie uruchomiony, wygenerowany dokument będzie dołączony do rekordu i zostanie wywołane zdarzenie **AttachingFile()**. Typ dokumentu, który jest skonfigurowany w parametrach elektronicznego raportowania określa lokalizację przechowywania dla dołączonego pliku (Magazyn Azure lub folder SharePoint).

![Strona parametrów raportowania elektronicznego](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a>Konfigurowanie miejsca docelowego raportowania elektronicznego

1. Skonfiguruj zarchiwizowane miejsce docelowe dla jednego z wcześniej wspomnianych elementów raportowania elektronicznego (plik, folder, scalanie lub załącznik), który został utworzony lub zaimportowany. Aby uzyskać instrukcje, zobacz [Konfigurowanie miejsc docelowych dla raportowania elektronicznego](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).
2. Użyj wcześniej typu dokumentu dodanego wcześniej do skonfigurowanego miejsca docelowego. (Na przykład w tym temacie, typem dokumentu jest **FileX**.)

![Okno dialogowe Ustawienia lokalizacji docelowej](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a>Zmień kod źródłowy

1. Dodaj nową klasę do projektu Microsoft Visual Studio i napisz kod, aby subskrybować wcześniej wspomniane zdarzenie **AttachingFile()**. (Aby uzyskać więcej informacji o używanym wzorcu rozszerzenia, zobacz [Odpowiedz za pomocą EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Na przykład: w nowej klasie napisz kod do wykonywania następujących akcji:

    1. Wygenerowane pliki przechowuje w folderze lokalnego systemu plików serwera, na którym działa usługa Serwer obiektów aplikacji (AOS).
    2. Zapisuje te wygenerowane pliki tylko kiedy jest używany nowy typ dokumentu (na przykład typ **FileX**, którego nazwa zawiera słowo „(LOCAL)”), jeśli plik jest załączany do rekordu w dzienniku wykonania zadania raportowania elektronicznego.

    ```xpp
    class ERDocuSubscriptionSample
    {
        void new()
        {
        }
        [SubscribesTo(classStr(ERDocuManagementEvents), 
        staticDelegateStr(ERDocuManagementEvents, 
        attachingFile))]
        public static void ERDocuManagementEvents_attachingFile(ERDocuManagementAttachingFileEventArgs _args)
        {
            if (!_args.isHandled())
            {
                DocuType docuType = DocuType::find(_args.getDocuTypeId());
                if (strContains(docuType.Name, '(LOCAL)'))
                {
                    _args.markAsHandled();
                    var stream = _args.getStream();
                    if (stream.CanSeek)
                    {
                        stream.Seek(0, System.IO.SeekOrigin::Begin);
                    }
                    using (var localStream = System.IO.File::OpenWrite(@'c:\0\' + _args.getAttachmentName()))
                    {
                        stream.CopyTo(localStream);
                    }
                }
            }
        }
    }
    ```

2. Zmodyfikuj projekt.

## <a name="run-the-er-format-that-you-created-or-imported"></a>Uruchom utworzony lub zaimportowany format raportowania elektronicznego

1. Wykonaj utworzony lub zaimportowany format raportowania elektronicznego.
2. Wybierz kolejno opcje **Administrowanie organizacją \> Raportowanie elektroniczne \> Zadania raportowania elektronicznego**. Znajdź rekord, który został utworzony dla tego zadania do wykonania i ma dołączony wygenerowany plik.
3. Zajrzyj do lokalnego folderu **C:\\0** i znajdź wygenerowany plik.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Lokalizacje docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)
- [Możliwości rozszerzania — strona główna](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]