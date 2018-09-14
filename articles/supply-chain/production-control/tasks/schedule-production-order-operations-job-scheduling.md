--- 
title: "Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań"
description: "Ta procedura skupia się na planowaniu zlecenia produkcyjnego przy użyciu funkcji planowania operacji i planowania zadań."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 00698e9cd2ed0481e5fed301c8a8c2e98690a5db
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="2e6a4-103">Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań</span><span class="sxs-lookup"><span data-stu-id="2e6a4-103">Schedule a production order with operations and job scheduling</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e6a4-104">Ta procedura skupia się na planowaniu zlecenia produkcyjnego przy użyciu funkcji planowania operacji i planowania zadań.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="2e6a4-105">Funkcja planowania operacji nie powoduje utworzenia żadnych zadań, natomiast zadania są tworzone przy użyciu funkcji planowania zadań.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="2e6a4-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="2e6a4-107">Ta procedura jest przeznaczona dla kierownika produkcji, planisty produkcji lub kierownika zakładu produkcyjnego w środowisku wytwarzania dyskretnego.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="2e6a4-108">Tworzenie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="2e6a4-108">Create a production order</span></span>
1. <span data-ttu-id="2e6a4-109">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="2e6a4-110">Kliknij opcję Nowe zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-110">Click New production order.</span></span>
3. <span data-ttu-id="2e6a4-111">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="2e6a4-112">Wybierz towar o numerze D0001.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="2e6a4-113">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="2e6a4-114">Planowanie operacji dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="2e6a4-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="2e6a4-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2e6a4-116">Zaznacz zlecenie produkcyjne, która właśnie zostało utworzone.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-116">Select the production order that you have just created.</span></span> <span data-ttu-id="2e6a4-117">Powinno być u góry listy.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="2e6a4-118">W okienku akcji kliknij pozycję Harmonogram.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="2e6a4-119">Kliknij opcję Planowanie operacji.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="2e6a4-120">W polu Kierunek planowania wybierz opcję „W przód od daty planowania”.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="2e6a4-121">W polu Data planowania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="2e6a4-122">Wybierz przyszłą datę, na przykład dziś plus jeden tydzień.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="2e6a4-123">Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="2e6a4-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-124">Click OK.</span></span>
7. <span data-ttu-id="2e6a4-125">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2e6a4-126">Zwróć uwagę, że stan zmienił się na Zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="2e6a4-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2e6a4-128">Kliknij opcję Wszystkie zadania.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-128">Click All jobs.</span></span>
    * <span data-ttu-id="2e6a4-129">Należy zauważyć, że planowanie operacji nie powoduje tworzenia żadnych zadań.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="2e6a4-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="2e6a4-131">Planowanie zadań dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="2e6a4-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="2e6a4-132">W okienku akcji kliknij pozycję Harmonogram.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="2e6a4-133">Kliknij harmonogram zadań.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="2e6a4-134">W polu Kierunek planowania wybierz opcję „W przód od daty planowania”.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="2e6a4-135">W polu Data planowania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="2e6a4-136">Wybierz datę w przyszłości, na przykład dziś plus jeden tydzień.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="2e6a4-137">Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="2e6a4-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-138">Click OK.</span></span>
6. <span data-ttu-id="2e6a4-139">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="2e6a4-140">Kliknij opcję Wszystkie zadania.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-140">Click All jobs.</span></span>
    * <span data-ttu-id="2e6a4-141">Należy zauważyć, że na podstawie aktywnej marszruty planowanie zadań tworzy 5 zadań.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  


