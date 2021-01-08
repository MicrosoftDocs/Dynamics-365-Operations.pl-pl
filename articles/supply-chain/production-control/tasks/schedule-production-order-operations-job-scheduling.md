---
title: Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań
description: Ten temat skupia się na planowaniu zlecenia pracy przy użyciu funkcji planowania operacji i planowania zadań.
author: ChristianRytt
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a69339bc678de8343dbf2646a4d6fe0ace9964c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435182"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="349b8-103">Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań</span><span class="sxs-lookup"><span data-stu-id="349b8-103">Schedule a production order with operations and job scheduling</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="349b8-104">Ten temat skupia się na planowaniu zlecenia pracy przy użyciu funkcji planowania operacji i planowania zadań.</span><span class="sxs-lookup"><span data-stu-id="349b8-104">This topic focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="349b8-105">Funkcja planowania operacji nie powoduje utworzenia żadnych zadań, natomiast zadania są tworzone przy użyciu funkcji planowania zadań.</span><span class="sxs-lookup"><span data-stu-id="349b8-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="349b8-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="349b8-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="349b8-107">Ta procedura jest przeznaczona dla kierownika produkcji, planisty produkcji lub kierownika zakładu produkcyjnego w środowisku wytwarzania dyskretnego.</span><span class="sxs-lookup"><span data-stu-id="349b8-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="349b8-108">Tworzenie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="349b8-108">Create a production order</span></span>
1. <span data-ttu-id="349b8-109">W okienku nawigacji przejdź po **Moduły > Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="349b8-109">In the navigation pane, go to **Modules > Production control > Production orders > All production orders**.</span></span>
2. <span data-ttu-id="349b8-110">Wybierz **Nowe zlecenie produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="349b8-110">Select **New production order**.</span></span>
3. <span data-ttu-id="349b8-111">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="349b8-111">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="349b8-112">Wybierz towar o numerze **D0001**.</span><span class="sxs-lookup"><span data-stu-id="349b8-112">Select Item number **D0001**.</span></span>  
4. <span data-ttu-id="349b8-113">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="349b8-113">Select **Create**.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="349b8-114">Planowanie operacji dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="349b8-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="349b8-115">Umożliwia oznaczenie nowo utworzonego wiersza.</span><span class="sxs-lookup"><span data-stu-id="349b8-115">Mark the newly created row.</span></span>      
2. <span data-ttu-id="349b8-116">W okienku akcji wybierz **Harmonogram**.</span><span class="sxs-lookup"><span data-stu-id="349b8-116">On the Action Pane, select **Schedule**.</span></span>
3. <span data-ttu-id="349b8-117">Wybierz **Planowanie operacji**.</span><span class="sxs-lookup"><span data-stu-id="349b8-117">Select **Schedule operations**.</span></span>
4. <span data-ttu-id="349b8-118">W polu **Kierunek planowania** wybierz opcję **W przód od daty planowania**.</span><span class="sxs-lookup"><span data-stu-id="349b8-118">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
5. <span data-ttu-id="349b8-119">W polu **Data planowania** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="349b8-119">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="349b8-120">Wybierz przyszłą datę, na przykład dziś plus jeden tydzień.</span><span class="sxs-lookup"><span data-stu-id="349b8-120">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="349b8-121">Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.</span><span class="sxs-lookup"><span data-stu-id="349b8-121">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="349b8-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="349b8-122">Select **OK**.</span></span>
7. <span data-ttu-id="349b8-123">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="349b8-123">In the list, mark the selected row.</span></span> <span data-ttu-id="349b8-124">Zwróć uwagę, że stan zmienił się na **Zaplanowane**.</span><span class="sxs-lookup"><span data-stu-id="349b8-124">Note that the status is changed to **Scheduled**.</span></span> 
8. <span data-ttu-id="349b8-125">Wybierz **Wszystkie zadania**.</span><span class="sxs-lookup"><span data-stu-id="349b8-125">Select **All jobs**.</span></span> <span data-ttu-id="349b8-126">Należy zauważyć, że planowanie operacji nie powoduje tworzenia żadnych zadań.</span><span class="sxs-lookup"><span data-stu-id="349b8-126">Note that no jobs are created with operations scheduling.</span></span>  
9. <span data-ttu-id="349b8-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="349b8-127">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="349b8-128">Planowanie zadań dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="349b8-128">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="349b8-129">W okienku akcji wybierz **Harmonogram**.</span><span class="sxs-lookup"><span data-stu-id="349b8-129">On the Action Pane, select **Schedule**.</span></span>
2. <span data-ttu-id="349b8-130">Wybierz **Planowanie zadań**.</span><span class="sxs-lookup"><span data-stu-id="349b8-130">Select **Schedule jobs**.</span></span>
3. <span data-ttu-id="349b8-131">W polu **Kierunek planowania** wybierz opcję **W przód od daty planowania**.</span><span class="sxs-lookup"><span data-stu-id="349b8-131">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
4. <span data-ttu-id="349b8-132">W polu **Data planowania** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="349b8-132">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="349b8-133">Wybierz datę w przyszłości, na przykład dziś plus jeden tydzień.</span><span class="sxs-lookup"><span data-stu-id="349b8-133">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="349b8-134">Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.</span><span class="sxs-lookup"><span data-stu-id="349b8-134">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="349b8-135">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="349b8-135">Select **OK**.</span></span>
6. <span data-ttu-id="349b8-136">W okienku akcji kliknij opcję **Zlecenie produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="349b8-136">On the Action Pane, select **Production order**.</span></span>
7. <span data-ttu-id="349b8-137">Wybierz **Wszystkie zadania**.</span><span class="sxs-lookup"><span data-stu-id="349b8-137">Select **All jobs**.</span></span> <span data-ttu-id="349b8-138">Należy zauważyć, że na podstawie aktywnej marszruty planowanie zadań tworzy 5 zadań.</span><span class="sxs-lookup"><span data-stu-id="349b8-138">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

