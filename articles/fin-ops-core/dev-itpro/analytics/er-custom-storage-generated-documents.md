---
title: Określanie lokalizacji niestandardowego magazynu wygenerowanych dokumentów
description: W tym temacie wyjaśniono, jak rozszerzyć listę lokalizacji przechowywania dokumentów generowanych przez raportowanie elektroniczne.
author: NickSelin
manager: AnnBe
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: f65118b6a7393ced9d80c30fad7540a7b27da6c7
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569091"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a><span data-ttu-id="8b857-103">Określanie lokalizacji niestandardowego magazynu wygenerowanych dokumentów</span><span class="sxs-lookup"><span data-stu-id="8b857-103">Specify a custom storage location for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8b857-104">Interfejs API raportowania elektronicznego pozwala rozszerzyć listę lokalizacji, w których można przechowywać dokumenty generowane przez funkcję raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="8b857-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="8b857-105">Ten temat zawiera przegląd głównych zadań, które należy wykonać, aby dodać niestandardowe miejsce przechowywania.</span><span class="sxs-lookup"><span data-stu-id="8b857-105">This topic includes an overview of the main tasks that you must complete to add a custom storage location.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b857-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="8b857-106">Prerequisites</span></span>

<span data-ttu-id="8b857-107">Należy wdrożyć topologię, która obsługuje ciągłą kompilację.</span><span class="sxs-lookup"><span data-stu-id="8b857-107">You must deploy a topology that supports continuous build.</span></span> <span data-ttu-id="8b857-108">(Aby uzyskać więcej informacji, zobacz [Wdrażanie topologii, która obsługuje ciągłą kompilację i automatyzację testowania](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) Musisz mieć dostęp do tej topologii dla jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="8b857-108">(For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="8b857-109">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8b857-109">Electronic reporting developer</span></span>
- <span data-ttu-id="8b857-110">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8b857-110">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="8b857-111">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="8b857-111">System administrator</span></span>

<span data-ttu-id="8b857-112">Ponadto musisz także mieć dostęp do środowiska programowania dla tej topologii.</span><span class="sxs-lookup"><span data-stu-id="8b857-112">You must also have access to the development environment for this topology.</span></span>

## <a name="create-or-import-an-er-format-configuration"></a><span data-ttu-id="8b857-113">Tworzenie lub importowanie konfiguracji formatu raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8b857-113">Create or import an ER format configuration</span></span>

<span data-ttu-id="8b857-114">W bieżącej topologii [utwórz nowy format raportowania elektronicznego](tasks/er-format-configuration-2016-11.md) do generowania dokumentów, dla których chcesz dodać niestandardową lokalizację przechowywania.</span><span class="sxs-lookup"><span data-stu-id="8b857-114">In the current topology, [create a new ER format](tasks/er-format-configuration-2016-11.md) to generate documents that you plan to add a custom storage location for.</span></span> <span data-ttu-id="8b857-115">Alternatywnie [Zaimportuj istniejący format raportowania elektronicznego do tej topologii](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="8b857-115">Alternatively, [import an existing ER format into this topology](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Strona projektanta formatu](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> <span data-ttu-id="8b857-117">Format raportowania elektronicznego, który tworzysz lub importujesz, musi zawierać co najmniej jedenz następujących elementów formatu:</span><span class="sxs-lookup"><span data-stu-id="8b857-117">The ER format that you create or import must contain at least one of the following format elements:</span></span>
>
> - <span data-ttu-id="8b857-118">Plik</span><span class="sxs-lookup"><span data-stu-id="8b857-118">File</span></span>
> - <span data-ttu-id="8b857-119">Folder</span><span class="sxs-lookup"><span data-stu-id="8b857-119">Folder</span></span>
> - <span data-ttu-id="8b857-120">Scalenie</span><span class="sxs-lookup"><span data-stu-id="8b857-120">Merger</span></span>
> - <span data-ttu-id="8b857-121">Załącznik</span><span class="sxs-lookup"><span data-stu-id="8b857-121">Attachment</span></span>

## <a name="create-a-new-document-type"></a><span data-ttu-id="8b857-122">Tworzenie nowego typu dokumentu</span><span class="sxs-lookup"><span data-stu-id="8b857-122">Create a new document type</span></span>

<span data-ttu-id="8b857-123">Aby określić, jak dokumenty, które generuje format raportowania elektronicznego są kierowane, należy skonfigurować [miejsca docelowe raportowania elektronicznego](electronic-reporting-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8b857-123">To specify how documents that an ER format generates are routed, you must configure [ER destinations](electronic-reporting-destinations.md).</span></span> <span data-ttu-id="8b857-124">W każdym miejscu docelowym raportowania elektronicznego, które jest skonfigurowane do przechowywania wygenerowanych dokumentów jako plików należy określić typ dokumentu struktury zarządzania dokumentami.</span><span class="sxs-lookup"><span data-stu-id="8b857-124">In each ER destination that is configured to store generated documents as files, you must specify a document type of the Document management framework.</span></span> <span data-ttu-id="8b857-125">Różne typy dokumentów mogą służyć do kierowania dokumentów generowanych przez raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="8b857-125">Different document types can be used to route documents that different ER formats generate.</span></span>

1. <span data-ttu-id="8b857-126">Dodaj nowy [typu dokumentu](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) dla formatu raportowania elektronicznego utworzonego lub zaimportowanego wcześniej.</span><span class="sxs-lookup"><span data-stu-id="8b857-126">Add a new [document type](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) for the ER format that you created or imported earlier.</span></span> <span data-ttu-id="8b857-127">Na ilustracji typem dokumentu jest **FileX**.</span><span class="sxs-lookup"><span data-stu-id="8b857-127">In the illustration that follows, the document type is **FileX**.</span></span>
2. <span data-ttu-id="8b857-128">W celu odróżnienia tego typu dokumentu od innych zamieść specjalne słowo kluczowe w jego nazwie.</span><span class="sxs-lookup"><span data-stu-id="8b857-128">To differentiate this document type from other document types, include a specific keyword in its name.</span></span> <span data-ttu-id="8b857-129">Na przykład na ilustracji poniżej, nazwa jest **(LOKALNY) folder**.</span><span class="sxs-lookup"><span data-stu-id="8b857-129">For example, in the illustration that follows, the name is **(LOCAL) folder**.</span></span>
3. <span data-ttu-id="8b857-130">W polu **klasy** wybierz **Dołącz plik**.</span><span class="sxs-lookup"><span data-stu-id="8b857-130">In the **Class** field, specify **Attach file**.</span></span>
4. <span data-ttu-id="8b857-131">W polu **grupa** wybierz **Plik**.</span><span class="sxs-lookup"><span data-stu-id="8b857-131">In the **Group** field, specify **File**.</span></span>

![Strona Typy dokumentów](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> <span data-ttu-id="8b857-133">Typy dokumentów są specyficzne dla firmy.</span><span class="sxs-lookup"><span data-stu-id="8b857-133">Document types are company-specific.</span></span> <span data-ttu-id="8b857-134">Aby użyć formatu raportowania elektronicznego ze skonfigurowanym miejscem docelowym w wielu firmach, musisz skonfigurować osobny typ dokumentu w każdej firmie.</span><span class="sxs-lookup"><span data-stu-id="8b857-134">To use an ER format with a configured destination in multiple companies, you must configure a separate document type in each company.</span></span>

## <a name="review-source-code"></a><span data-ttu-id="8b857-135">Przejrzyj kod źródłowy</span><span class="sxs-lookup"><span data-stu-id="8b857-135">Review source code</span></span>

<span data-ttu-id="8b857-136">Przejrzyj kod metody **insertFile()** w klasie **ERDocuManagement**.</span><span class="sxs-lookup"><span data-stu-id="8b857-136">Review the code of the **insertFile()** method of the **ERDocuManagement** class.</span></span> <span data-ttu-id="8b857-137">Należy zauważyć, że zdarzenie **AttachingFile()** jest wywoływane, gdy wygenerowany plik jest dołączony do rekordu.</span><span class="sxs-lookup"><span data-stu-id="8b857-137">Notice that the **AttachingFile()** event is raised while the generated file is attached to a record.</span></span>

```
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

<span data-ttu-id="8b857-138">Zdarzenie **AttachingFile()** jest wywoływane po przetworzeniu następujących miejsc docelowych raportowania elektronicznego:</span><span class="sxs-lookup"><span data-stu-id="8b857-138">The **AttachingFile()** event is raised when the following ER destinations are processed:</span></span>

- <span data-ttu-id="8b857-139">**Archiwum** — kiedy jest używana ta lokalizacja, jest tworzony nowy rekord dla formatu raportowania elektronicznego w tabeli ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="8b857-139">**Archive** – When this destination is used, a new record for the ER format that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="8b857-140">Pole **Archiwizacji** w tym rekordzie jest ustawione jako **Fałsz**.</span><span class="sxs-lookup"><span data-stu-id="8b857-140">The **Archived** field in this record is set to **False**.</span></span> <span data-ttu-id="8b857-141">Jeśli format raportowania elektronicznego zostanie pomyślnie uruchomiony, wygenerowany dokument będzie dołączony do rekordu i zostanie wywołane zdarzenie **AttachingFile()**.</span><span class="sxs-lookup"><span data-stu-id="8b857-141">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="8b857-142">Typ dokumentu, który jest wybrany w tym miejscu docelowym elektronicznego raportowania określa lokalizację przechowywania dla dołączonego pliku (Microsoft Azure lub folder SharePoint).</span><span class="sxs-lookup"><span data-stu-id="8b857-142">The document type that is selected in this ER destination determines the storage location for the attached file (Microsoft Azure Storage or a Microsoft SharePoint folder).</span></span>
- <span data-ttu-id="8b857-143">**Archiwum zadania** — kiedy jest używana ta lokalizacja, jest tworzony nowy rekord dla formatu raportowania elektronicznego w tabeli ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="8b857-143">**Job archive** – When this destination is used, a new record for the ER form that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="8b857-144">Pole **Archiwizacji** w tym rekordzie jest ustawione jako **Prawda**.</span><span class="sxs-lookup"><span data-stu-id="8b857-144">The **Archived** field in this record is set to **True**.</span></span> <span data-ttu-id="8b857-145">Jeśli format raportowania elektronicznego zostanie pomyślnie uruchomiony, wygenerowany dokument będzie dołączony do rekordu i zostanie wywołane zdarzenie **AttachingFile()**.</span><span class="sxs-lookup"><span data-stu-id="8b857-145">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="8b857-146">Typ dokumentu, który jest skonfigurowany w parametrach elektronicznego raportowania określa lokalizację przechowywania dla dołączonego pliku (Magazyn Azure lub folder SharePoint).</span><span class="sxs-lookup"><span data-stu-id="8b857-146">The document type that is configured in the ER parameters determines the storage location for the attached file (Azure Storage or a SharePoint folder).</span></span>

![Strona parametrów raportowania elektronicznego](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a><span data-ttu-id="8b857-148">Konfigurowanie miejsca docelowego raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8b857-148">Configure an ER destination</span></span>

1. <span data-ttu-id="8b857-149">Skonfiguruj zarchiwizowane miejsce docelowe dla jednego z wcześniej wspomnianych elementów raportowania elektronicznego (plik, folder, scalanie lub załącznik), który został utworzony lub zaimportowany.</span><span class="sxs-lookup"><span data-stu-id="8b857-149">Configure the archived destination for one of the previously mentioned elements (file, folder, merger, or attachment) of the ER format that you created or imported.</span></span> <span data-ttu-id="8b857-150">Aby uzyskać instrukcje, zobacz [Konfigurowanie miejsc docelowych dla raportowania elektronicznego](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span><span class="sxs-lookup"><span data-stu-id="8b857-150">For guidance, see [ER Configure destinations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span></span>
2. <span data-ttu-id="8b857-151">Użyj wcześniej typu dokumentu dodanego wcześniej do skonfigurowanego miejsca docelowego.</span><span class="sxs-lookup"><span data-stu-id="8b857-151">Use the document type that you added earlier for the configured destination.</span></span> <span data-ttu-id="8b857-152">(Na przykład w tym temacie, typem dokumentu jest **FileX**.)</span><span class="sxs-lookup"><span data-stu-id="8b857-152">(For the example in this topic, the document type is **FileX**.)</span></span>

![Okno dialogowe Ustawienia lokalizacji docelowej](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a><span data-ttu-id="8b857-154">Zmień kod źródłowy</span><span class="sxs-lookup"><span data-stu-id="8b857-154">Modify source code</span></span>

1. <span data-ttu-id="8b857-155">Dodaj nową klasę do projektu Microsoft Visual Studio i napisz kod, aby subskrybować wcześniej wspomniane zdarzenie **AttachingFile()**.</span><span class="sxs-lookup"><span data-stu-id="8b857-155">Add a new class to your Microsoft Visual Studio project, and write code to subscribe to the **AttachingFile()** event that was mentioned earlier.</span></span> <span data-ttu-id="8b857-156">(Aby uzyskać więcej informacji o używanym wzorcu rozszerzenia, zobacz [Odpowiedz za pomocą EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Na przykład: w nowej klasie napisz kod do wykonywania następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="8b857-156">(For more information about the extensibility pattern that is used, see [Respond by using EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) For example, in the new class, write code that performs the following actions:</span></span>

    1. <span data-ttu-id="8b857-157">Wygenerowane pliki przechowuje w folderze lokalnego systemu plików serwera, na którym działa usługa Serwer obiektów aplikacji (AOS).</span><span class="sxs-lookup"><span data-stu-id="8b857-157">Store generated files in a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    2. <span data-ttu-id="8b857-158">Zapisuje te wygenerowane pliki tylko kiedy jest używany nowy typ dokumentu (na przykład typ **FileX**, którego nazwa zawiera słowo „(LOCAL)”), jeśli plik jest załączany do rekordu w dzienniku wykonania zadania raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="8b857-158">Store these generated files only when the new document type (for example, the **FileX** type that has the "(LOCAL)" keyword in its name) is used while a file is attached to the record in the ER execution job log.</span></span>

    ```
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

2. <span data-ttu-id="8b857-159">Zmodyfikuj projekt.</span><span class="sxs-lookup"><span data-stu-id="8b857-159">Rebuild your project.</span></span>

## <a name="run-the-er-format-that-you-created-or-imported"></a><span data-ttu-id="8b857-160">Uruchom utworzony lub zaimportowany format raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8b857-160">Run the ER format that you created or imported</span></span>

1. <span data-ttu-id="8b857-161">Wykonaj utworzony lub zaimportowany format raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="8b857-161">Execute the ER format that you created or imported.</span></span>
2. <span data-ttu-id="8b857-162">Wybierz kolejno opcje **Administrowanie organizacją \> Raportowanie elektroniczne \> Zadania raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="8b857-162">Go to **Organization administration \> Electronic reporting \> Electronic reporting jobs**.</span></span> <span data-ttu-id="8b857-163">Znajdź rekord, który został utworzony dla tego zadania do wykonania i ma dołączony wygenerowany plik.</span><span class="sxs-lookup"><span data-stu-id="8b857-163">Find the record that was created for this execution job, and that has the generated file attached to it.</span></span>
3. <span data-ttu-id="8b857-164">Zajrzyj do lokalnego folderu **C:\\0** i znajdź wygenerowany plik.</span><span class="sxs-lookup"><span data-stu-id="8b857-164">Explore the local **C:\\0** folder to find same generated file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8b857-165">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8b857-165">Additional resources</span></span>

- [<span data-ttu-id="8b857-166">Aplikacje docelowe Raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8b857-166">Electronic reporting destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="8b857-167">Strona główna rozszerzania</span><span class="sxs-lookup"><span data-stu-id="8b857-167">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
