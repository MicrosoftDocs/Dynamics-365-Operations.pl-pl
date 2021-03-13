---
title: Tworzenie planu międzyfirmowego
description: Ta procedura pokazuje, jak utworzyć plan międzyfirmowy.
author: ShylaThompson
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c368e461860a41d0110f5aed79c2aac49c437d68
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011422"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="3bd9d-103">Tworzenie planu międzyfirmowego</span><span class="sxs-lookup"><span data-stu-id="3bd9d-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3bd9d-104">Ta procedura pokazuje, jak utworzyć plan międzyfirmowy.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="3bd9d-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="3bd9d-106">Konfigurowanie grupy planowania międzyfirmowego</span><span class="sxs-lookup"><span data-stu-id="3bd9d-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="3bd9d-107">W **okienku nawigacji** przejdź do **Moduły > Planowanie główne > Konfiguracja > Grupy planowania międzyfirmowego**.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span> 
2. <span data-ttu-id="3bd9d-108">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3bd9d-109">Na przykład wyfiltruj według pola Nazwa z wartością „10”.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="3bd9d-110">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="3bd9d-111">Kliknij przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-111">Click **Delete**.</span></span> <span data-ttu-id="3bd9d-112">Ten krok jest konieczny w celu przyspieszenia planowania międzyfirmowego.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="3bd9d-113">Planowanie międzyfirmowe spowoduje wykonanie planowania głównego we wszystkich firmach w grupie planowania, zaczynając od planowania o najniższym numerze.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="3bd9d-114">Kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-114">Click **Yes**.</span></span>
6. <span data-ttu-id="3bd9d-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-115">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="3bd9d-116">Tworzenie planu międzyfirmowego</span><span class="sxs-lookup"><span data-stu-id="3bd9d-116">Create an intercompany plan</span></span>
1. <span data-ttu-id="3bd9d-117">W **okienku nawigacji** przejdź do **Moduły > Planowanie główne > Obszary robocze > Planowanie główne**.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="3bd9d-118">Kliknij opcję **Międzyfirmowe planowanie główne**.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-118">Click **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="3bd9d-119">W polu **IGrupa planowania międzyfirmowego** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-119">In the **Intercompany planning group** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="3bd9d-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-120">In the list, click the link in the selected row.</span></span> <span data-ttu-id="3bd9d-121">Wybierz grupę planowania międzyfirmowego 10.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="3bd9d-122">W polu **Liczba iteracji planowania międzyfirmowego** wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="3bd9d-123">Grupa planowania międzyfirmowego 10 ma dwa elementy członkowskie.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="3bd9d-124">W celu rozpowszechnienia opóźnień z firmy źródłowej (USMF) do firmy odbiorcy (DEMF) należy wykonać planowanie międzyfirmowe dwa razy w obu firmach.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="3bd9d-125">Pierwsza iteracja spowoduje rozpowszechnienie informacji o zapotrzebowaniu i zidentyfikowanie opóźnień w firmie źródłowej (USMF).</span><span class="sxs-lookup"><span data-stu-id="3bd9d-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="3bd9d-126">Druga iteracja rozpowszechni opóźnienia z firmy USMF do firmy DEMF.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="3bd9d-127">W polu **Pierwsza iteracja** wybierz opcję „Ponowne generowanie”.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="3bd9d-128">W polu **Kolejne iteracje** wybierz opcję „Ponowne generowanie”.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="3bd9d-129">W polu **Liczba wątków** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="3bd9d-130">Reprezentuje liczbę równoległych wątków używanych w planowaniu.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="3bd9d-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-131">Click **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="3bd9d-132">Wyświetlanie wyniku planowania</span><span class="sxs-lookup"><span data-stu-id="3bd9d-132">View the result of the plan</span></span>
1. <span data-ttu-id="3bd9d-133">W polu **Plan** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-133">In the **Plan** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="3bd9d-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-134">In the list, click the link in the selected row.</span></span> <span data-ttu-id="3bd9d-135">Kliknij łącze do planu statycznego.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-135">Click the link for StaticPlan.</span></span> <span data-ttu-id="3bd9d-136">Musisz być w firmie USMF.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="3bd9d-137">Kliknij opcję **Zamówienia planowane**.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-137">Click **Planned orders**.</span></span>

