--- 
title: "Tworzenie harmonogramu dla oddziału"
description: "W tej procedurze pokazano sposób planowania zleceń produkcyjnych, które jeszcze nie zostały rozpoczęte w oddziale."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: a33ef9e60c7aca13f745441c825362cdee52f9ea
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-schedule-for-a-site"></a><span data-ttu-id="92bf4-103">Tworzenie harmonogramu dla oddziału</span><span class="sxs-lookup"><span data-stu-id="92bf4-103">Create a schedule for a site</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="92bf4-104">W tej procedurze pokazano sposób planowania zleceń produkcyjnych, które jeszcze nie zostały rozpoczęte w oddziale.</span><span class="sxs-lookup"><span data-stu-id="92bf4-104">This procedure shows how to schedule production orders that are not yet started for a site.</span></span>  <span data-ttu-id="92bf4-105">Dane wykorzystane do wykonania tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="92bf4-105">The demo data company USMF is used to complete this procedure.</span></span>


## <a name="identify-production-orders-that-are-not-started"></a><span data-ttu-id="92bf4-106">Identyfikowanie zleceń produkcyjnych, które się jeszcze nie rozpoczęły</span><span class="sxs-lookup"><span data-stu-id="92bf4-106">Identify production orders that are not started</span></span>
1. <span data-ttu-id="92bf4-107">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="92bf4-107">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="92bf4-108">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="92bf4-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="92bf4-109">Na przykład wyfiltruj według pola Oddział z wartością „1”.</span><span class="sxs-lookup"><span data-stu-id="92bf4-109">For example, filter on the Site field with a value of '1'.</span></span>
    * <span data-ttu-id="92bf4-110">1 odpowiada oddziałowi w firmie USMF.</span><span class="sxs-lookup"><span data-stu-id="92bf4-110">1 represents a site in USMF.</span></span> <span data-ttu-id="92bf4-111">Jeśli nie używasz firmy USMF, wybierz oddział ze swojej firmy.</span><span class="sxs-lookup"><span data-stu-id="92bf4-111">If you are not using USMF, select a site from your own company.</span></span>  
3. <span data-ttu-id="92bf4-112">Otwórz filtr kolumn Stan.</span><span class="sxs-lookup"><span data-stu-id="92bf4-112">Open the Status column filter.</span></span>
4. <span data-ttu-id="92bf4-113">Zastosuj filtr do pola „Stan” z wartością „Zaplanowane” i operatorem „równa się”.</span><span class="sxs-lookup"><span data-stu-id="92bf4-113">Apply a filter on the "Status" field, with a value of "Scheduled", using the "is exactly" filter operator.</span></span>

## <a name="create-a-schedule"></a><span data-ttu-id="92bf4-114">Tworzenie harmonogramu</span><span class="sxs-lookup"><span data-stu-id="92bf4-114">Create a schedule</span></span>
1. <span data-ttu-id="92bf4-115">Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.</span><span class="sxs-lookup"><span data-stu-id="92bf4-115">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="92bf4-116">W okienku akcji kliknij pozycję Harmonogram.</span><span class="sxs-lookup"><span data-stu-id="92bf4-116">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="92bf4-117">Kliknij opcję Planowanie zadań.</span><span class="sxs-lookup"><span data-stu-id="92bf4-117">Click Schedule jobs.</span></span>
4. <span data-ttu-id="92bf4-118">W polu Kierunek planowania wybierz opcję "Wstecz od daty dostawy".</span><span class="sxs-lookup"><span data-stu-id="92bf4-118">In the Scheduling direction field, select 'Backward from delivery date'.</span></span>
5. <span data-ttu-id="92bf4-119">W polu Ograniczone zdolności produkcyjne wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="92bf4-119">Select No in the Finite capacity field.</span></span>
6. <span data-ttu-id="92bf4-120">W polu Ograniczone materiały wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="92bf4-120">Select No in the Finite material field.</span></span>
7. <span data-ttu-id="92bf4-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="92bf4-121">Click OK.</span></span>
    * <span data-ttu-id="92bf4-122">Może to trochę potrwać.</span><span class="sxs-lookup"><span data-stu-id="92bf4-122">This may take a while.</span></span>  

## <a name="view-the-result-of-scheduled-production-orders"></a><span data-ttu-id="92bf4-123">Wyświetlanie rezultatów zaplanowanych zleceń produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="92bf4-123">View the result of scheduled production orders</span></span>
1. <span data-ttu-id="92bf4-124">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="92bf4-124">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="92bf4-125">Można oznaczyć dowolny wiersz.</span><span class="sxs-lookup"><span data-stu-id="92bf4-125">You can mark any row.</span></span>  
2. <span data-ttu-id="92bf4-126">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="92bf4-126">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="92bf4-127">Kliknij opcję Wszystkie zadania.</span><span class="sxs-lookup"><span data-stu-id="92bf4-127">Click All jobs.</span></span>
    * <span data-ttu-id="92bf4-128">Na tej stronie widać listę zadań.</span><span class="sxs-lookup"><span data-stu-id="92bf4-128">On this page, you can see the list of jobs.</span></span> <span data-ttu-id="92bf4-129">Na karcie Planowanie widać daty rozpoczęcia i zakończenia zadania.</span><span class="sxs-lookup"><span data-stu-id="92bf4-129">On the Scheduling tab, you can see the Start date and End date for a job.</span></span>  
4. <span data-ttu-id="92bf4-130">Kliknij opcję Materiały.</span><span class="sxs-lookup"><span data-stu-id="92bf4-130">Click Materials.</span></span>
    * <span data-ttu-id="92bf4-131">Na tej stronie widać szacowane zużycie materiału w operacjach zlecenia produkcyjnego oraz aktualnie dostępne zapasy.</span><span class="sxs-lookup"><span data-stu-id="92bf4-131">On this page, you can see the estimated material consumption for the operations on the production order and the current available inventory.</span></span>  


