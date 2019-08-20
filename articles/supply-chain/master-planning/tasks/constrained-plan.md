---
title: Generowanie planu z ograniczeniami
description: W tej procedurze pokazano, jak utworzyć plan, który bierze pod uwagę ograniczenia dotyczące materiałów i zdolności produkcyjnych.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72cddd58b7068e08cddf24df83da8da2f7af7168
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845314"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="3dac7-103">Generowanie planu z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="3dac7-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3dac7-104">W tej procedurze pokazano, jak utworzyć plan, który bierze pod uwagę ograniczenia dotyczące materiałów i zdolności produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="3dac7-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="3dac7-105">Plan gwarantuje, że produkcja nie rozpocznie się przed zapewnieniem dostępności materiałów i wyeliminowaniem ryzyka nadrezerwacji.</span><span class="sxs-lookup"><span data-stu-id="3dac7-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="3dac7-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3dac7-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3dac7-107">Ta procedura jest przeznaczona dla planisty produkcji.</span><span class="sxs-lookup"><span data-stu-id="3dac7-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="3dac7-108">Konfigurowanie planu z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="3dac7-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="3dac7-109">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="3dac7-109">Click Master planning.</span></span>
2. <span data-ttu-id="3dac7-110">Kliknij opcję Plany główne.</span><span class="sxs-lookup"><span data-stu-id="3dac7-110">Click Master plans.</span></span>
3. <span data-ttu-id="3dac7-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3dac7-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3dac7-112">Przykład: Plan statyczny</span><span class="sxs-lookup"><span data-stu-id="3dac7-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="3dac7-113">W polu Ograniczone zdolności produkcyjne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3dac7-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="3dac7-114">W polu Horyzont czasowy ograniczonych zdolności produkcyjnych wpisz „30”.</span><span class="sxs-lookup"><span data-stu-id="3dac7-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="3dac7-115">Rozwiń sekcję Horyzonty czasowe w dniach.</span><span class="sxs-lookup"><span data-stu-id="3dac7-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="3dac7-116">W polu Zdolności produkcyjne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3dac7-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="3dac7-117">W polu Horyzont czasowy planowania zdolności produkcyjnych wpisz liczbę dni.</span><span class="sxs-lookup"><span data-stu-id="3dac7-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="3dac7-118">Przykład: 60</span><span class="sxs-lookup"><span data-stu-id="3dac7-118">Example: 60</span></span>  
9. <span data-ttu-id="3dac7-119">W polu Obliczone opóźnienia zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3dac7-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="3dac7-120">W polu Oblicz horyzont czasowy opóźnień (dni) wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="3dac7-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="3dac7-121">Przykład: 60</span><span class="sxs-lookup"><span data-stu-id="3dac7-121">Example: 60</span></span>  
11. <span data-ttu-id="3dac7-122">Rozwiń sekcję Obliczone opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="3dac7-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="3dac7-123">W polu Dodaj obliczone opóźnienie do daty zapotrzebowania zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3dac7-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="3dac7-124">W polu Dodaj obliczone opóźnienie do daty zapotrzebowania zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3dac7-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="3dac7-125">W polu Dodaj obliczone opóźnienie do daty zapotrzebowania zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3dac7-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="3dac7-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3dac7-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="3dac7-127">Tworzenie planu z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="3dac7-127">Create a constrained plan</span></span>
1. <span data-ttu-id="3dac7-128">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="3dac7-128">Click Run.</span></span>
2. <span data-ttu-id="3dac7-129">W polu Plan główny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dac7-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="3dac7-130">Zaznacz plan, dla którego skonfigurowano ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="3dac7-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="3dac7-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3dac7-131">Click OK.</span></span>
    * <span data-ttu-id="3dac7-132">Może to trochę potrwać.</span><span class="sxs-lookup"><span data-stu-id="3dac7-132">This may take a while.</span></span>  
4. <span data-ttu-id="3dac7-133">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="3dac7-133">Click Planned orders.</span></span>

