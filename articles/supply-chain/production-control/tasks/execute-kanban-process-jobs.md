--- 
title: "Wykonywanie zadań procesu w systemie Kanban"
description: "Ta procedura skupia się na wykonywaniu zadań procesu w systemie Kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: d9505b74e5fbb14882356968d0f0273ef2b3feb8
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="execute-kanban-process-jobs"></a><span data-ttu-id="90a3f-103">Wykonywanie zadań procesu w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="90a3f-103">Execute kanban process jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="90a3f-104">Ta procedura skupia się na wykonywaniu zadań procesu w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="90a3f-104">This procedure focuses on executing kanban process jobs.</span></span> <span data-ttu-id="90a3f-105">Pierwsze zadanie zostało ukończone z oczekiwaną ilością i nie zawiera błędów.</span><span class="sxs-lookup"><span data-stu-id="90a3f-105">The first job is completed with the expected quantity and has no errors.</span></span> <span data-ttu-id="90a3f-106">Drugie zadanie zostało ukończone z błędami.</span><span class="sxs-lookup"><span data-stu-id="90a3f-106">The second job is completed with errors.</span></span> <span data-ttu-id="90a3f-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="90a3f-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="90a3f-108">Ta procedura jest przeznaczona dla operatora maszyny.</span><span class="sxs-lookup"><span data-stu-id="90a3f-108">This procedure is intended for the machine operator.</span></span>


## <a name="select-a-kanban-job"></a><span data-ttu-id="90a3f-109">Wybieranie zadania Kanban</span><span class="sxs-lookup"><span data-stu-id="90a3f-109">Select a kanban job</span></span>
1. <span data-ttu-id="90a3f-110">Wybierz kolejno opcje Kontrola produkcji > Kanban > Tablica Kanban dla zadań procesu.</span><span class="sxs-lookup"><span data-stu-id="90a3f-110">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="90a3f-111">W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="90a3f-111">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="90a3f-112">Kliknij wiersz z grupą zasobów 1250.</span><span class="sxs-lookup"><span data-stu-id="90a3f-112">Click the row with resource group 1250.</span></span> <span data-ttu-id="90a3f-113">Spowoduje to wyfiltrowanie listy zadań, aby wyświetlić tylko zadania komórki roboczej 1250.</span><span class="sxs-lookup"><span data-stu-id="90a3f-113">This filters the Jobs list to display only the jobs for work cell 1250.</span></span>
    * <span data-ttu-id="90a3f-114">Zaznacz wiersz, który ma stan Zaplanowane zadanie.</span><span class="sxs-lookup"><span data-stu-id="90a3f-114">Mark the row that has the Planned job status.</span></span>  

## <a name="complete-a-job-with-expected-quantity"></a><span data-ttu-id="90a3f-115">Kończenie zadania z oczekiwaną ilością</span><span class="sxs-lookup"><span data-stu-id="90a3f-115">Complete a job with expected quantity</span></span>
1. <span data-ttu-id="90a3f-116">Rozwiń lub zwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="90a3f-116">Expand or collapse the Details section.</span></span>
    * <span data-ttu-id="90a3f-117">Ta sekcja zawiera ważne informacje dotyczące numeru karty, numeru towaru, ilości zamówionej i nazwy działania.</span><span class="sxs-lookup"><span data-stu-id="90a3f-117">This section displays important information about card number, item number, quantity ordered, and activity name.</span></span>  
2. <span data-ttu-id="90a3f-118">Rozwiń lub zwiń sekcje Instrukcje produkcji.</span><span class="sxs-lookup"><span data-stu-id="90a3f-118">Expand or collapse the Production instructions section.</span></span>
    * <span data-ttu-id="90a3f-119">W tej sekcji są wyświetlane instrukcje produkcji dla działania.</span><span class="sxs-lookup"><span data-stu-id="90a3f-119">This section displays production instructions for the activity.</span></span> <span data-ttu-id="90a3f-120">Instrukcjami mogą być teksty, obrazy, rysunki i inne dokumenty.</span><span class="sxs-lookup"><span data-stu-id="90a3f-120">The instructions can be text, pictures, drawings, and other documents.</span></span>  
3. <span data-ttu-id="90a3f-121">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="90a3f-121">Click Start.</span></span>
    * <span data-ttu-id="90a3f-122">Wybierz zadanie, które nie zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="90a3f-122">Select a job that is not completed.</span></span> <span data-ttu-id="90a3f-123">Użyj ikon stanu w polu Stan zadania, aby wyświetlić stan zadania.</span><span class="sxs-lookup"><span data-stu-id="90a3f-123">Use status icons in the Job status field to view job status.</span></span>      
4. <span data-ttu-id="90a3f-124">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="90a3f-124">Click Complete.</span></span>
    * <span data-ttu-id="90a3f-125">Zadanie jest zakończone z oczekiwaną jakością.</span><span class="sxs-lookup"><span data-stu-id="90a3f-125">The job is completed with the expected quality.</span></span>  

## <a name="complete-a-job-with-errors"></a><span data-ttu-id="90a3f-126">Kończenie zadania z błędami</span><span class="sxs-lookup"><span data-stu-id="90a3f-126">Complete a job with errors</span></span>
1. <span data-ttu-id="90a3f-127">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="90a3f-127">Click Start.</span></span>
    * <span data-ttu-id="90a3f-128">Po zakończeniu zadania następne zadanie na liście jest wybierane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="90a3f-128">When a job is completed, the next job on the list is selected automatically.</span></span> <span data-ttu-id="90a3f-129">Dlatego nie ma potrzeby zaznaczania zadania przed kliknięciem przycisku Uruchom.</span><span class="sxs-lookup"><span data-stu-id="90a3f-129">This is why you don't need to select a job before you click Start.</span></span>  
2. <span data-ttu-id="90a3f-130">W okienku akcji kliknij pozycję Produkcja.</span><span class="sxs-lookup"><span data-stu-id="90a3f-130">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="90a3f-131">Kliknij opcję Zakończ (szczegóły).</span><span class="sxs-lookup"><span data-stu-id="90a3f-131">Click Complete (details).</span></span>
4. <span data-ttu-id="90a3f-132">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="90a3f-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="90a3f-133">W polu Ilość wadliwych wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="90a3f-133">In the Error quantity field, enter a number.</span></span>
6. <span data-ttu-id="90a3f-134">W polu Ilość dobrych wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="90a3f-134">In the Good quantity field, enter a number.</span></span>
7. <span data-ttu-id="90a3f-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="90a3f-135">Click OK.</span></span>


