---
title: Szablony danych z wieloma arkuszami
description: W tym temacie opisano, jak przeprowadzić import danych przy użyciu szablonów jednostki danych programu Excel do Finance and Operations.
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 64515ff74c0ca2b01bb9dac06331ba0424811411
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565578"
---
# <a name="data-templates-with-multiple-worksheets"></a><span data-ttu-id="577e4-103">Szablony danych z wieloma arkuszami</span><span class="sxs-lookup"><span data-stu-id="577e4-103">Data templates with multiple worksheets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="577e4-104">Zarządzanie danymi w aplikacji obsługuje szablony Microsoft Excel dla jednostek danych.</span><span class="sxs-lookup"><span data-stu-id="577e4-104">Data management in the application supports Microsoft Excel-based templates for data entities.</span></span> <span data-ttu-id="577e4-105">Szablony te mogą zawierać jeden lub więcej arkuszy.</span><span class="sxs-lookup"><span data-stu-id="577e4-105">These templates can contain one or more worksheets.</span></span> <span data-ttu-id="577e4-106">Szablony z wieloma arkuszami są często używane, gdy wygodne jest zarządzanie danymi w jednym pliku i importowanie go do wielu jednostek danych.</span><span class="sxs-lookup"><span data-stu-id="577e4-106">Templates with multiple worksheets are often used when it is convenient to manage data in a single file and import it to multiple data entities.</span></span> <span data-ttu-id="577e4-107">Przykładem mogą być oddziały i magazyny.</span><span class="sxs-lookup"><span data-stu-id="577e4-107">An example would be sites and warehouses.</span></span>

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a><span data-ttu-id="577e4-108">Przekazanie pliku raz i mapowanie go do wszystkich jednostek</span><span class="sxs-lookup"><span data-stu-id="577e4-108">Upload a file once and map it to all entities</span></span>
<span data-ttu-id="577e4-109">Przeanalizujmy przykład, w którym występuje jeden plik programu Excel z arkuszami o nazwie **Oddziały** i **Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="577e4-109">Let's take an example where there is one Excel file with worksheets called **Sites** and **Warehouses**.</span></span> <span data-ttu-id="577e4-110">Aby skonfigurować projekt importu danych, należy dodać pierwszą jednostkę danych, **Oddziały**, a następnie przekazać plik.</span><span class="sxs-lookup"><span data-stu-id="577e4-110">To set up the data import project, you would add the first data entity, **Sites** and then upload the file.</span></span> <span data-ttu-id="577e4-111">Będzie można wybrać arkusz **Oddziały** do użycia dla tej jednostki.</span><span class="sxs-lookup"><span data-stu-id="577e4-111">You will be able to select **Sites** as the worksheet to be used for this entity.</span></span>

<span data-ttu-id="577e4-112">Jeżeli dodasz drugą jednostkę **Magazyny** bez opuszczania formularza **Dodaj plik**, wyszukiwanie arkusza umożliwi wybranie arkusza **Magazyny** bez konieczności ponownego przekazywania pliku.</span><span class="sxs-lookup"><span data-stu-id="577e4-112">If you add the second entity **Warehouses** without leaving the **Add file** form, the worksheet lookup will let you select the **Warehouses** worksheet without having to upload the file again.</span></span> <span data-ttu-id="577e4-113">Jedynym powodem przekazania nowego pliku byłby fakt, że dane z arkusza **Magazyny** znajdują się w innym pliku.</span><span class="sxs-lookup"><span data-stu-id="577e4-113">The only reason to upload a new file would be if the **Warehouses** data was in a different file.</span></span>

![Wiele arkuszy](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a><span data-ttu-id="577e4-115">Naprawianie mapowania arkusza w jednostce</span><span class="sxs-lookup"><span data-stu-id="577e4-115">Fix worksheet to entity mapping</span></span>

<span data-ttu-id="577e4-116">Mapowanie arkusza w jednostce danych w zadaniu importowania można naprawić w siatce.</span><span class="sxs-lookup"><span data-stu-id="577e4-116">The mapping of the worksheet to a data entity in the import job can be fixed from the grid.</span></span> <span data-ttu-id="577e4-117">Kolumna **Arkusz** w siatce pokazuje arkusze z pliku, który został zmapowany.</span><span class="sxs-lookup"><span data-stu-id="577e4-117">The **Worksheet** column in the grid shows the worksheets from the file that was mapped.</span></span> <span data-ttu-id="577e4-118">Można wybrać inny arkusz z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="577e4-118">You can choose a different worksheet from the drop-down menu.</span></span> <span data-ttu-id="577e4-119">Jeśli wybrany arkusz jest już zmapowany do jednostki w projekcie danych, system wyświetli monit o potwierdzenie zmiany.</span><span class="sxs-lookup"><span data-stu-id="577e4-119">If the chosen worksheet is already mapped to an entity in the data project, the system asks you to confirm the change.</span></span> <span data-ttu-id="577e4-120">Zalecamy naprawę mapowań w siatce.</span><span class="sxs-lookup"><span data-stu-id="577e4-120">We recommend that you fix all mappings in the grid.</span></span>

![Aktualizacja mapowania arkusza](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a><span data-ttu-id="577e4-122">Ponowne mapowanie do nowego pliku</span><span class="sxs-lookup"><span data-stu-id="577e4-122">Re-map to a new file</span></span>

<span data-ttu-id="577e4-123">W przypadku gdy konieczne jest przekazanie nowej wersji tego samego pliku lub całkowicie nowego pliku dla istniejących jednostek w projekcie danych należy użyć funkcji **Dodaj plik** i dodać jednostki ponownie, tak jakby były dodawane po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="577e4-123">In cases where a new version of the same file or a completely new file must be uploaded for existing entities in a data project, you must use the **Add file** experience, and add the entities again as if they were being added for the first time.</span></span> <span data-ttu-id="577e4-124">Przed kontynuacją system potwierdzi, że chcesz zastąpić istniejące jednostki w projekcie danych.</span><span class="sxs-lookup"><span data-stu-id="577e4-124">The system will confirm that you want to overwrite the existing entities in the data project before proceeding.</span></span> <span data-ttu-id="577e4-125">Jednostki, które nie dodawane ponownie (ani zastępowane) będą nadal zawierać poprzednie mapowania z poprzedniego pliku.</span><span class="sxs-lookup"><span data-stu-id="577e4-125">Entities that are not added again (or overwritten) will continue to hold the previous mappings from the previous file.</span></span>

## <a name="upload-a-file-using-run-project"></a><span data-ttu-id="577e4-126">Przekazywanie pliku przy użyciu funkcji Uruchom projekt</span><span class="sxs-lookup"><span data-stu-id="577e4-126">Upload a file using Run project</span></span>

<span data-ttu-id="577e4-127">Plik programu Excel można przekazać, używając opcji **Uruchom projekt** w celu wykonania projektu importu.</span><span class="sxs-lookup"><span data-stu-id="577e4-127">You can upload an Excel file while using the **Run project** option to execute an import project.</span></span> <span data-ttu-id="577e4-128">Należy uważać, aby przekazać tylko pliki, które zawierają te same arkusze co istniejące mapowania w jednostkach danych w projekcie danych.</span><span class="sxs-lookup"><span data-stu-id="577e4-128">You must be careful to upload only files that have the same worksheets as the existing mappings on the data entities in the data project.</span></span> <span data-ttu-id="577e4-129">Jeżeli w nowym przekazanym pliku arkusz nie zostanie znaleziony, system wyświetli komunikat o błędzie i zatrzyma import.</span><span class="sxs-lookup"><span data-stu-id="577e4-129">If a worksheet is not found in the newly uploaded file, the system displays an error and will stop the import.</span></span> <span data-ttu-id="577e4-130">Jeżeli mapowanie w arkuszu musi zostać zmienione, mapowania w projekcie danych należy najpierw zaktualizować z poziomu projektu danych przed użyciem pliku w ramach funkcji **Uruchom projekt**.</span><span class="sxs-lookup"><span data-stu-id="577e4-130">If the mapping to the worksheet must be changed for an entity, then the mappings in the data project must be first updated from within the data project before using the file in the **Run project** experience.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]