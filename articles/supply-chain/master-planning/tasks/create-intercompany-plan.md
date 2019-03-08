---
title: Tworzenie planu międzyfirmowego
description: Ta procedura pokazuje, jak utworzyć plan międzyfirmowy.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d378a89bbb4de6d67db0019dc72a27945d50c4e9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "333744"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="25335-103">Tworzenie planu międzyfirmowego</span><span class="sxs-lookup"><span data-stu-id="25335-103">Create an intercompany plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25335-104">Ta procedura pokazuje, jak utworzyć plan międzyfirmowy.</span><span class="sxs-lookup"><span data-stu-id="25335-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="25335-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="25335-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="25335-106">Konfigurowanie grupy planowania międzyfirmowego</span><span class="sxs-lookup"><span data-stu-id="25335-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="25335-107">Przejdź do okna Grupy planowania międzyfirmowego.</span><span class="sxs-lookup"><span data-stu-id="25335-107">Go to Intercompany planning groups.</span></span>
    * <span data-ttu-id="25335-108">Planowanie główne > Ustawienia > Grupy planowania międzyfirmowego</span><span class="sxs-lookup"><span data-stu-id="25335-108">Master planning > Setup > Intercompany planning groups</span></span>  
2. <span data-ttu-id="25335-109">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="25335-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="25335-110">Na przykład wyfiltruj według pola Nazwa z wartością „10”.</span><span class="sxs-lookup"><span data-stu-id="25335-110">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="25335-111">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="25335-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="25335-112">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="25335-112">Click Delete.</span></span>
    * <span data-ttu-id="25335-113">Ten krok jest konieczny w celu przyspieszenia planowania międzyfirmowego.</span><span class="sxs-lookup"><span data-stu-id="25335-113">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="25335-114">Planowanie międzyfirmowe spowoduje wykonanie planowania głównego we wszystkich firmach w grupie planowania, zaczynając od planowania o najniższym numerze.</span><span class="sxs-lookup"><span data-stu-id="25335-114">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="25335-115">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="25335-115">Click Yes.</span></span>
6. <span data-ttu-id="25335-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="25335-116">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="25335-117">Tworzenie planu międzyfirmowego</span><span class="sxs-lookup"><span data-stu-id="25335-117">Create an intercompany plan</span></span>
1. <span data-ttu-id="25335-118">Kliknij opcję Międzyfirmowe planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="25335-118">Click Intercompany master planning.</span></span>
    * <span data-ttu-id="25335-119">To jest w obszarze roboczym Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="25335-119">This is on the Master planning workspace.</span></span>  
2. <span data-ttu-id="25335-120">W polu Grupa planowania międzyfirmowego kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="25335-120">In the Intercompany planning group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="25335-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="25335-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="25335-122">Wybierz grupę planowania międzyfirmowego 10.</span><span class="sxs-lookup"><span data-stu-id="25335-122">Select intercompany planning group 10.</span></span>  
4. <span data-ttu-id="25335-123">W polu Liczba iteracji planowania międzyfirmowego wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="25335-123">In the Number of intercompany planning iterations field, enter '2'.</span></span>
    * <span data-ttu-id="25335-124">Grupa planowania międzyfirmowego 10 ma dwa elementy członkowskie.</span><span class="sxs-lookup"><span data-stu-id="25335-124">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="25335-125">W celu rozpowszechnienia opóźnień z firmy źródłowej (USMF) do firmy odbiorcy (DEMF) należy wykonać planowanie międzyfirmowe dwa razy w obu firmach.</span><span class="sxs-lookup"><span data-stu-id="25335-125">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="25335-126">Pierwsza iteracja spowoduje rozpowszechnienie informacji o zapotrzebowaniu i zidentyfikowanie opóźnień w firmie źródłowej (USMF).</span><span class="sxs-lookup"><span data-stu-id="25335-126">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="25335-127">Druga iteracja rozpowszechni opóźnienia z firmy USMF do firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="25335-127">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
5. <span data-ttu-id="25335-128">W polu Pierwsza iteracja wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="25335-128">In the First iteration field, select an option.</span></span>
6. <span data-ttu-id="25335-129">W polu Pierwsza iteracja wybierz opcję „Ponowne generowanie”.</span><span class="sxs-lookup"><span data-stu-id="25335-129">In the First iteration field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="25335-130">W polu Kolejne iteracje wybierz opcję „Ponowne generowanie”.</span><span class="sxs-lookup"><span data-stu-id="25335-130">In the Subsequent iterations field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="25335-131">W polu Liczba wątków wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="25335-131">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="25335-132">Reprezentuje liczbę równoległych wątków używanych w planowaniu.</span><span class="sxs-lookup"><span data-stu-id="25335-132">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="25335-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="25335-133">Click OK.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="25335-134">Wyświetlanie wyniku planowania</span><span class="sxs-lookup"><span data-stu-id="25335-134">View the result of the plan</span></span>
1. <span data-ttu-id="25335-135">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="25335-135">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="25335-136">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="25335-136">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="25335-137">Kliknij łącze do planu statycznego.</span><span class="sxs-lookup"><span data-stu-id="25335-137">Click the link for StaticPlan.</span></span> <span data-ttu-id="25335-138">Musisz być w firmie USMF.</span><span class="sxs-lookup"><span data-stu-id="25335-138">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="25335-139">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="25335-139">Click Planned orders.</span></span>

