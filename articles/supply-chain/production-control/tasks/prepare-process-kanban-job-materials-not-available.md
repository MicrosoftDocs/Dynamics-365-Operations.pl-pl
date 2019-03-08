---
title: Przygotowanie zadania procesu w systemie Kanban, gdy materiały nie są dostępne dla komórki roboczej
description: Ta procedura jest zorientowana na przygotowanie zadania przetwarzania w systemie Kanban, gdy niektóre materiały są niedostępne w komórce roboczej i z tego względu konieczne jest ich pobranie z magazynu.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7e7eb46bda13ef7e72189f921686a9889a8773c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "339908"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a><span data-ttu-id="1c3d6-103">Przygotowanie zadania procesu w systemie Kanban, gdy materiały nie są dostępne dla komórki roboczej</span><span class="sxs-lookup"><span data-stu-id="1c3d6-103">Prepare a process kanban job when materials are not available for the work cell</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1c3d6-104">Ta procedura jest zorientowana na przygotowanie zadania przetwarzania w systemie Kanban, gdy niektóre materiały są niedostępne w komórce roboczej i z tego względu konieczne jest ich pobranie z magazynu.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-104">This procedure focuses on preparing a process kanban job when some materials are not available for the work cell, therefore it's necessary to pick materials from the warehouse.</span></span> <span data-ttu-id="1c3d6-105">Warunkiem wstępnym utworzenia tej procedury jest wykonanie procedury „Przygotowanie zadania przetwarzania w systemie Kanban, gdy materiały są dostępne”.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-105">The procedure "Prepare a process kanban job when materials are available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="1c3d6-106">Ta procedura jest przeznaczona dla operatora maszyny.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-106">This procedure is intended for the machine operator.</span></span> <span data-ttu-id="1c3d6-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="1c3d6-108">Wybierz kolejno opcje Kontrola produkcji > Kanban > Tablica Kanban dla zadań procesu.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-108">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="1c3d6-109">W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="1c3d6-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1c3d6-111">Zaznacz komórkę roboczą 1250.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="1c3d6-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1c3d6-113">Wybierz opcję Kanban 000356.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-113">Select Kanban 000356.</span></span>  
5. <span data-ttu-id="1c3d6-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1c3d6-115">Na liście usuń zaznaczenie wiersza 4</span><span class="sxs-lookup"><span data-stu-id="1c3d6-115">In the list, deselect row 4.</span></span> <span data-ttu-id="1c3d6-116">lub wybierz wiersz 4, jeśli nie wykonano zadania „Przygotowanie zadania przetwarzania w systemie Kanban, gdy materiały są dostępne”.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-116">or Select row 4 if you haven't completed the task "Prepare a process kanban job when materials are available."</span></span>  
6. <span data-ttu-id="1c3d6-117">Przełącz rozwinięcie sekcji Lista pobrania.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-117">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="1c3d6-118">Ikona barku wpisu w stanie dostaw wskazuje, że w komórce roboczej brakuje 48 sztuk towaru P0002.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-118">The No entry icon in the supply status indicates that 48 ea of item P0002 are missing for the work cell.</span></span>  

## <a name="transfer-materials-to-work-cell"></a><span data-ttu-id="1c3d6-119">Przenoszenie materiałów do komórki roboczej</span><span class="sxs-lookup"><span data-stu-id="1c3d6-119">Transfer materials to work cell</span></span>
1. <span data-ttu-id="1c3d6-120">Przełącz rozwinięcie sekcji Zadania przenoszenia.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-120">Toggle the expansion of the Transfer jobs section.</span></span>
2. <span data-ttu-id="1c3d6-121">Użyj szybkiego filtru, aby filtrować na podstawie pola Numer pozycji z wartością „P0002”.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-121">Use the Quick Filter to filter on the Item number field with a value of 'P0002'.</span></span>
3. <span data-ttu-id="1c3d6-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="1c3d6-123">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-123">Click Start.</span></span>
    * <span data-ttu-id="1c3d6-124">Przenoszenie jest w toku.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-124">Transfer is in progress.</span></span>  
5. <span data-ttu-id="1c3d6-125">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-125">Click Complete.</span></span>
    * <span data-ttu-id="1c3d6-126">Towar P0002 jest teraz dostępny na liście pobrania dla zadania w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-126">Item P0002 is now available in the picking list for the kanban job.</span></span> <span data-ttu-id="1c3d6-127">Oznacza to, że możemy przygotować kartę Kanban ze wszystkimi niezbędnymi materiałami.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-127">This means that we can prepare the kanban with all the needed materials.</span></span>  
6. <span data-ttu-id="1c3d6-128">Kliknij przycisk Przygotuj.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-128">Click Prepare.</span></span>
    * <span data-ttu-id="1c3d6-129">Zwróć uwagę na ikonę w polu Stan zadania, która wskazuje, że zadanie jest gotowe.</span><span class="sxs-lookup"><span data-stu-id="1c3d6-129">Notice that an icon in the Job status indicates that the job is now ready.</span></span>  

