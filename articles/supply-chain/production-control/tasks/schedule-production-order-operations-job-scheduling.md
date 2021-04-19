---
title: Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań
description: Ten temat skupia się na planowaniu zlecenia pracy przy użyciu funkcji planowania operacji i planowania zadań.
author: ChristianRytt
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 883a68af78a9d91df089d30d8f1b3d7ba498d577
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841390"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="72f05-103">Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań</span><span class="sxs-lookup"><span data-stu-id="72f05-103">Schedule a production order with operations and job scheduling</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72f05-104">Ten temat skupia się na planowaniu zlecenia pracy przy użyciu funkcji planowania operacji i planowania zadań.</span><span class="sxs-lookup"><span data-stu-id="72f05-104">This topic focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="72f05-105">Funkcja planowania operacji nie powoduje utworzenia żadnych zadań, natomiast zadania są tworzone przy użyciu funkcji planowania zadań.</span><span class="sxs-lookup"><span data-stu-id="72f05-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="72f05-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="72f05-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="72f05-107">Ta procedura jest przeznaczona dla kierownika produkcji, planisty produkcji lub kierownika zakładu produkcyjnego w środowisku wytwarzania dyskretnego.</span><span class="sxs-lookup"><span data-stu-id="72f05-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="72f05-108">Tworzenie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="72f05-108">Create a production order</span></span>
1. <span data-ttu-id="72f05-109">W okienku nawigacji przejdź po **Moduły > Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="72f05-109">In the navigation pane, go to **Modules > Production control > Production orders > All production orders**.</span></span>
2. <span data-ttu-id="72f05-110">Wybierz **Nowe zlecenie produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="72f05-110">Select **New production order**.</span></span>
3. <span data-ttu-id="72f05-111">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="72f05-111">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="72f05-112">Wybierz towar o numerze **D0001**.</span><span class="sxs-lookup"><span data-stu-id="72f05-112">Select Item number **D0001**.</span></span>  
4. <span data-ttu-id="72f05-113">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="72f05-113">Select **Create**.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="72f05-114">Planowanie operacji dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="72f05-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="72f05-115">Umożliwia oznaczenie nowo utworzonego wiersza.</span><span class="sxs-lookup"><span data-stu-id="72f05-115">Mark the newly created row.</span></span>      
2. <span data-ttu-id="72f05-116">W okienku akcji wybierz **Harmonogram**.</span><span class="sxs-lookup"><span data-stu-id="72f05-116">On the Action Pane, select **Schedule**.</span></span>
3. <span data-ttu-id="72f05-117">Wybierz **Planowanie operacji**.</span><span class="sxs-lookup"><span data-stu-id="72f05-117">Select **Schedule operations**.</span></span>
4. <span data-ttu-id="72f05-118">W polu **Kierunek planowania** wybierz opcję **W przód od daty planowania**.</span><span class="sxs-lookup"><span data-stu-id="72f05-118">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
5. <span data-ttu-id="72f05-119">W polu **Data planowania** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="72f05-119">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="72f05-120">Wybierz przyszłą datę, na przykład dziś plus jeden tydzień.</span><span class="sxs-lookup"><span data-stu-id="72f05-120">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="72f05-121">Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.</span><span class="sxs-lookup"><span data-stu-id="72f05-121">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="72f05-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="72f05-122">Select **OK**.</span></span>
7. <span data-ttu-id="72f05-123">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="72f05-123">In the list, mark the selected row.</span></span> <span data-ttu-id="72f05-124">Zwróć uwagę, że stan zmienił się na **Zaplanowane**.</span><span class="sxs-lookup"><span data-stu-id="72f05-124">Note that the status is changed to **Scheduled**.</span></span> 
8. <span data-ttu-id="72f05-125">Wybierz **Wszystkie zadania**.</span><span class="sxs-lookup"><span data-stu-id="72f05-125">Select **All jobs**.</span></span> <span data-ttu-id="72f05-126">Należy zauważyć, że planowanie operacji nie powoduje tworzenia żadnych zadań.</span><span class="sxs-lookup"><span data-stu-id="72f05-126">Note that no jobs are created with operations scheduling.</span></span>  
9. <span data-ttu-id="72f05-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="72f05-127">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="72f05-128">Planowanie zadań dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="72f05-128">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="72f05-129">W okienku akcji wybierz **Harmonogram**.</span><span class="sxs-lookup"><span data-stu-id="72f05-129">On the Action Pane, select **Schedule**.</span></span>
2. <span data-ttu-id="72f05-130">Wybierz **Planowanie zadań**.</span><span class="sxs-lookup"><span data-stu-id="72f05-130">Select **Schedule jobs**.</span></span>
3. <span data-ttu-id="72f05-131">W polu **Kierunek planowania** wybierz opcję **W przód od daty planowania**.</span><span class="sxs-lookup"><span data-stu-id="72f05-131">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
4. <span data-ttu-id="72f05-132">W polu **Data planowania** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="72f05-132">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="72f05-133">Wybierz datę w przyszłości, na przykład dziś plus jeden tydzień.</span><span class="sxs-lookup"><span data-stu-id="72f05-133">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="72f05-134">Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.</span><span class="sxs-lookup"><span data-stu-id="72f05-134">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="72f05-135">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="72f05-135">Select **OK**.</span></span>
6. <span data-ttu-id="72f05-136">W okienku akcji kliknij opcję **Zlecenie produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="72f05-136">On the Action Pane, select **Production order**.</span></span>
7. <span data-ttu-id="72f05-137">Wybierz **Wszystkie zadania**.</span><span class="sxs-lookup"><span data-stu-id="72f05-137">Select **All jobs**.</span></span> <span data-ttu-id="72f05-138">Należy zauważyć, że na podstawie aktywnej marszruty planowanie zadań tworzy 5 zadań.</span><span class="sxs-lookup"><span data-stu-id="72f05-138">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]