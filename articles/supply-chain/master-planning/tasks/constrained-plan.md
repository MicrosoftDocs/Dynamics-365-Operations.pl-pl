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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0e2265f7788fd2a4a37f6fb96d7562649dbc5b1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556030"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="eeee0-103">Generowanie planu z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="eeee0-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eeee0-104">W tej procedurze pokazano, jak utworzyć plan, który bierze pod uwagę ograniczenia dotyczące materiałów i zdolności produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="eeee0-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="eeee0-105">Plan gwarantuje, że produkcja nie rozpocznie się przed zapewnieniem dostępności materiałów i wyeliminowaniem ryzyka nadrezerwacji.</span><span class="sxs-lookup"><span data-stu-id="eeee0-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="eeee0-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="eeee0-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="eeee0-107">Ta procedura jest przeznaczona dla planisty produkcji.</span><span class="sxs-lookup"><span data-stu-id="eeee0-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="eeee0-108">Konfigurowanie planu z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="eeee0-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="eeee0-109">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="eeee0-109">Click Master planning.</span></span>
2. <span data-ttu-id="eeee0-110">Kliknij opcję Plany główne.</span><span class="sxs-lookup"><span data-stu-id="eeee0-110">Click Master plans.</span></span>
3. <span data-ttu-id="eeee0-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="eeee0-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="eeee0-112">Przykład: Plan statyczny</span><span class="sxs-lookup"><span data-stu-id="eeee0-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="eeee0-113">W polu Ograniczone zdolności produkcyjne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="eeee0-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="eeee0-114">W polu Horyzont czasowy ograniczonych zdolności produkcyjnych wpisz „30”.</span><span class="sxs-lookup"><span data-stu-id="eeee0-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="eeee0-115">Rozwiń sekcję Horyzonty czasowe w dniach.</span><span class="sxs-lookup"><span data-stu-id="eeee0-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="eeee0-116">W polu Zdolności produkcyjne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="eeee0-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="eeee0-117">W polu Horyzont czasowy planowania zdolności produkcyjnych wpisz liczbę dni.</span><span class="sxs-lookup"><span data-stu-id="eeee0-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="eeee0-118">Przykład: 60</span><span class="sxs-lookup"><span data-stu-id="eeee0-118">Example: 60</span></span>  
9. <span data-ttu-id="eeee0-119">W polu Obliczone opóźnienia zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="eeee0-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="eeee0-120">W polu Oblicz horyzont czasowy opóźnień (dni) wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="eeee0-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="eeee0-121">Przykład: 60</span><span class="sxs-lookup"><span data-stu-id="eeee0-121">Example: 60</span></span>  
11. <span data-ttu-id="eeee0-122">Rozwiń sekcję Obliczone opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="eeee0-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="eeee0-123">W polu Dodaj obliczone opóźnienie do daty zapotrzebowania zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="eeee0-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="eeee0-124">W polu Dodaj obliczone opóźnienie do daty zapotrzebowania zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="eeee0-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="eeee0-125">W polu Dodaj obliczone opóźnienie do daty zapotrzebowania zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="eeee0-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="eeee0-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="eeee0-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="eeee0-127">Tworzenie planu z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="eeee0-127">Create a constrained plan</span></span>
1. <span data-ttu-id="eeee0-128">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="eeee0-128">Click Run.</span></span>
2. <span data-ttu-id="eeee0-129">W polu Plan główny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="eeee0-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="eeee0-130">Zaznacz plan, dla którego skonfigurowano ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="eeee0-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="eeee0-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eeee0-131">Click OK.</span></span>
    * <span data-ttu-id="eeee0-132">Może to trochę potrwać.</span><span class="sxs-lookup"><span data-stu-id="eeee0-132">This may take a while.</span></span>  
4. <span data-ttu-id="eeee0-133">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="eeee0-133">Click Planned orders.</span></span>

