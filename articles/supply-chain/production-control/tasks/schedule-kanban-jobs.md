---
title: Tworzenie harmonogramu zadań w systemie Kanban
description: Ta procedura skupia się na planowaniu zadań przetwarzania w systemie Kanban dla określonej komórki roboczej.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c8342bf6c56adc41cc4944dc709152246ad93a3e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435418"
---
# <a name="schedule-kanban-jobs"></a><span data-ttu-id="bf327-103">Tworzenie harmonogramu zadań w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="bf327-103">Schedule kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bf327-104">Ta procedura skupia się na planowaniu zadań przetwarzania w systemie Kanban dla określonej komórki roboczej.</span><span class="sxs-lookup"><span data-stu-id="bf327-104">This procedure focuses on scheduling process kanban jobs for a specific work cell.</span></span> <span data-ttu-id="bf327-105">Warunkiem wstępnym utworzenia tej procedury jest wykonanie procedury „Przygotowanie zadania przetwarzania w systemie Kanban, gdy materiały są niedostępne”.</span><span class="sxs-lookup"><span data-stu-id="bf327-105">The procedure "Prepare a process kanban job when materials are not available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="bf327-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="bf327-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bf327-107">Zadanie jest przeznaczone dla kierownika zakładu produkcyjnego i planisty produkcji używających kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="bf327-107">This task is intended for the shop floor supervisor and production planner working with kanbans.</span></span>


## <a name="select-kanban-jobs-for-a-work-cell"></a><span data-ttu-id="bf327-108">Wybieranie zadań w systemie Kanban dla komórki roboczej</span><span class="sxs-lookup"><span data-stu-id="bf327-108">Select kanban jobs for a work cell</span></span>
1. <span data-ttu-id="bf327-109">Wybierz kolejno opcje Kontrola produkcji > Kanban > Planowanie zadań Kanban.</span><span class="sxs-lookup"><span data-stu-id="bf327-109">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="bf327-110">Rozwiń pole informacji Zdolności produkcyjne w okresie.</span><span class="sxs-lookup"><span data-stu-id="bf327-110">Expand the Period capacity fact box</span></span>
    * <span data-ttu-id="bf327-111">Rozwiń pole informacji Kanban.</span><span class="sxs-lookup"><span data-stu-id="bf327-111">Expand the Kanban FactBox.</span></span>  
3. <span data-ttu-id="bf327-112">W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="bf327-112">In the Work cell field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="bf327-113">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bf327-113">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="bf327-114">Zaznacz komórkę roboczą 1250.</span><span class="sxs-lookup"><span data-stu-id="bf327-114">Select work cell 1250.</span></span> <span data-ttu-id="bf327-115">Spowoduje to wyfiltrowanie widoku, aby wyświetlić tylko zadania komórki roboczej 1250.</span><span class="sxs-lookup"><span data-stu-id="bf327-115">This will filter the view to display only the jobs for work cell 1250.</span></span>  
5. <span data-ttu-id="bf327-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="bf327-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="bf327-117">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="bf327-117">Click Select.</span></span>

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a><span data-ttu-id="bf327-118">Planowanie zadania w systemie Kanban na pierwszy dostępny okres</span><span class="sxs-lookup"><span data-stu-id="bf327-118">Schedule a kanban job in the first available period</span></span>
1. <span data-ttu-id="bf327-119">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bf327-119">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="bf327-120">Zaznacz pierwszy wiersz na liście, który ma status Niezaplanowane.</span><span class="sxs-lookup"><span data-stu-id="bf327-120">Select the first row in the list that has the Not planned status.</span></span> <span data-ttu-id="bf327-121">Ikona z kropkami w polu Stan zadania wskazuje, że zadanie jest niezaplanowane.</span><span class="sxs-lookup"><span data-stu-id="bf327-121">The dotted icon in the Job status field indicates not planned.</span></span>  
2. <span data-ttu-id="bf327-122">Kliknij opcję Harmonogram.</span><span class="sxs-lookup"><span data-stu-id="bf327-122">Click Schedule.</span></span>
    * <span data-ttu-id="bf327-123">Spowoduje to zaplanowanie zadania w systemie Kanban na pierwszy dostępny okres.</span><span class="sxs-lookup"><span data-stu-id="bf327-123">This will schedule the kanban job in the first available period.</span></span>  
    * <span data-ttu-id="bf327-124">Należy zauważyć, że zadanie w systemie Kanban zostało przeniesione na koniec listy, ponieważ dodano je do okresu rozpoczynającego się dzisiaj.</span><span class="sxs-lookup"><span data-stu-id="bf327-124">Notice that the kanban job is moved to the end of the list because it has been added to the period starting from today.</span></span>  
    * <span data-ttu-id="bf327-125">Jeśli okres rozpoczynający się od dnia dzisiejszego jest w pełni zarezerwowany, zadanie zostanie przeniesione do pierwszego dostępnego okresu.</span><span class="sxs-lookup"><span data-stu-id="bf327-125">If the period starting from today is fully booked, the job will be moved to the first available period.</span></span>  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a><span data-ttu-id="bf327-126">Planowanie dwóch zadań w systemie Kanban na określony dzień</span><span class="sxs-lookup"><span data-stu-id="bf327-126">Schedule two kanban jobs for a specific day</span></span>
1. <span data-ttu-id="bf327-127">Na liście zaznacz wiersz 1.</span><span class="sxs-lookup"><span data-stu-id="bf327-127">In the list, select row 1.</span></span>
    * <span data-ttu-id="bf327-128">Powinno być widać, że w polu Stan zadania pierwszy wiersz ma stan Niezaplanowane.</span><span class="sxs-lookup"><span data-stu-id="bf327-128">You should see that the first row has the Not planned status in the Job status field.</span></span>  
2. <span data-ttu-id="bf327-129">Na liście zaznacz wiersz 2.</span><span class="sxs-lookup"><span data-stu-id="bf327-129">In the list, select row 2.</span></span>
    * <span data-ttu-id="bf327-130">Powinno być widać, że w polu Stan zadania drugi wiersz ma stan Niezaplanowane.</span><span class="sxs-lookup"><span data-stu-id="bf327-130">You should see that the second row has the Not planned status in the Job status field.</span></span> <span data-ttu-id="bf327-131">Teraz dwa pierwsze zdania są zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="bf327-131">Now you have the first two jobs selected.</span></span>  
3. <span data-ttu-id="bf327-132">Kliknij opcję Harmonogram od daty, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="bf327-132">Click Schedule from date to open the drop dialog.</span></span>
4. <span data-ttu-id="bf327-133">Zaznacz lub wyczyść pole wyboru Zastąpienie reakcji na niedobór zdolności produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="bf327-133">Check or uncheck the Override capacity shortage reaction box.</span></span>
    * <span data-ttu-id="bf327-134">Ta opcja umożliwia zastąpienie domyślnej reakcji na niedobór zdolności produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="bf327-134">This option allows you to override the default capacity shortage reaction.</span></span>  
5. <span data-ttu-id="bf327-135">W polu Reakcja na niedobór zdolności produkcyjnych zaznacz opcję „Dodaj do zgłaszanego okresu”.</span><span class="sxs-lookup"><span data-stu-id="bf327-135">In the Capacity shortage reaction field, select 'Add to the requested period'.</span></span>
    * <span data-ttu-id="bf327-136">Ta opcja zapewnia dodanie zadania do żądanego okresu, nawet wtedy, gdy komórka robocza jest przeciążona.</span><span class="sxs-lookup"><span data-stu-id="bf327-136">This option will ensure that the job is added to the requested period, regardless if the work cell might be overloaded.</span></span>  
6. <span data-ttu-id="bf327-137">Kliknij opcję Harmonogram.</span><span class="sxs-lookup"><span data-stu-id="bf327-137">Click Schedule.</span></span>
    * <span data-ttu-id="bf327-138">Należy zauważyć, że oba zadania zostały dodane do żądanego okresu.</span><span class="sxs-lookup"><span data-stu-id="bf327-138">Notice that both jobs are added to the desired period.</span></span>  
    * <span data-ttu-id="bf327-139">W tej sekcji Zdolności produkcyjne w okresie widać obciążenie dla każdego okresu.</span><span class="sxs-lookup"><span data-stu-id="bf327-139">In the Period capacity section, you can see the load for each period.</span></span> <span data-ttu-id="bf327-140">Pola Zużycie pokazuje zużycie zaplanowane w tym okresie.</span><span class="sxs-lookup"><span data-stu-id="bf327-140">The Consumption field shows the scheduled consumption in this period.</span></span> <span data-ttu-id="bf327-141">Jeśli planowane zużycie jest wyższe niż zdolności produkcyjne dostępne w tym okresie, zostanie zaznaczone przeciążone zużycie.</span><span class="sxs-lookup"><span data-stu-id="bf327-141">If the scheduled consumption is higher than the available capacity in this period, the overloaded consumption will be selected.</span></span>  

