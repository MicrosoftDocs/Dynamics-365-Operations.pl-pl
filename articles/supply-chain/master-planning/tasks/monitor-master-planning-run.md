---
title: Monitorowanie przebiegu planowania głównego
description: Planista produkcji chce sprawdzić, czy trwa sesja planowania głównego.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b923b215528ecceaed9b5057ddb736ec959f1d65
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845120"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="3dcd3-103">Monitorowanie przebiegu planowania głównego</span><span class="sxs-lookup"><span data-stu-id="3dcd3-103">Monitor a master planning run</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3dcd3-104">Planista produkcji chce sprawdzić, czy trwa sesja planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="3dcd3-105">Do wykonania tej procedury użyj danych z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="3dcd3-106">Uruchamianie planowania głównego</span><span class="sxs-lookup"><span data-stu-id="3dcd3-106">Run master planning</span></span>
1. <span data-ttu-id="3dcd3-107">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-107">Click Master planning.</span></span>
    * <span data-ttu-id="3dcd3-108">Znajdziesz to w domyślnym pulpicie nawigacyjnym.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="3dcd3-109">W polu Plan wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="3dcd3-110">Przykład: Plan statyczny</span><span class="sxs-lookup"><span data-stu-id="3dcd3-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="3dcd3-111">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-111">Click Run.</span></span>
4. <span data-ttu-id="3dcd3-112">W polu Śledź czas przetwarzania zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="3dcd3-113">Jeśli to pole jest już zaznaczone, pomiń ten krok.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="3dcd3-114">W polu Liczba wątków wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="3dcd3-115">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="3dcd3-116">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-116">Click Filter.</span></span>
8. <span data-ttu-id="3dcd3-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3dcd3-118">Zaznacz wiersz, w którym Pole = Numer pozycji.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="3dcd3-119">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="3dcd3-120">Przykład: T0001</span><span class="sxs-lookup"><span data-stu-id="3dcd3-120">Example: T0001</span></span>  
10. <span data-ttu-id="3dcd3-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-121">Click OK.</span></span>
11. <span data-ttu-id="3dcd3-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="3dcd3-123">Monitorowanie przebiegu planowania głównego</span><span class="sxs-lookup"><span data-stu-id="3dcd3-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="3dcd3-124">Kliknij przycisk Historia.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-124">Click History.</span></span>
2. <span data-ttu-id="3dcd3-125">Kliknij przycisk Informacje.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-125">Click Inquiries.</span></span>
3. <span data-ttu-id="3dcd3-126">Kliknij opcję Czas trwania zadania procesu.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-126">Click Process task duration.</span></span>
4. <span data-ttu-id="3dcd3-127">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3dcd3-128">Dla każdego towaru można orientacyjnie sprawdzić, ile czasu zajął każdy etap planowania.</span><span class="sxs-lookup"><span data-stu-id="3dcd3-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  

