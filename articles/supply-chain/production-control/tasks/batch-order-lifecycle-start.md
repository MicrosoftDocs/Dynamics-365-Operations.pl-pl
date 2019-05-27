---
title: Cykl zamówienia partii od utworzenia do rozpoczęcia
description: Ta procedura prowadzi Cię przez pierwszą częścią cyklu życia szarży produkcyjnej.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6484c1954ff4cc600938adb07b5384f1edce8bf7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545909"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="57b88-103">Cykl zamówienia partii od utworzenia do rozpoczęcia</span><span class="sxs-lookup"><span data-stu-id="57b88-103">Batch order lifecycle from create to start</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57b88-104">Ta procedura prowadzi Cię przez pierwszą częścią cyklu życia szarży produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="57b88-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="57b88-105">Od utworzenia, oszacowania kosztów i zaplanowania zadań produkcyjnych, aż do rzeczywistego rozpoczęcia szarży.</span><span class="sxs-lookup"><span data-stu-id="57b88-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="57b88-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="57b88-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="57b88-107">Warunkiem wstępnym wykonania tej procedury przy użyciu innego zestawu danych jest istnienie zwolnionego produktu z aktywną formułą i wersją marszruty.</span><span class="sxs-lookup"><span data-stu-id="57b88-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="57b88-108">Tworzenie zamówienia partii</span><span class="sxs-lookup"><span data-stu-id="57b88-108">Create a batch order</span></span>
1. <span data-ttu-id="57b88-109">Przejdź do okna Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="57b88-109">Go to All production orders.</span></span>
2. <span data-ttu-id="57b88-110">Kliknij opcję Nowe zamówienie partii.</span><span class="sxs-lookup"><span data-stu-id="57b88-110">Click New batch order.</span></span>
3. <span data-ttu-id="57b88-111">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="57b88-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="57b88-112">Kliknij Utwórz.</span><span class="sxs-lookup"><span data-stu-id="57b88-112">Click Create.</span></span>
5. <span data-ttu-id="57b88-113">Użyj szybkiego filtru, aby wyfiltrować pole Produkcja według wartości „b”.</span><span class="sxs-lookup"><span data-stu-id="57b88-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="57b88-114">Wyświetlanie formuły produkcji i oczekiwanych produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="57b88-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="57b88-115">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="57b88-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="57b88-116">Kliknij przycisk Formuła.</span><span class="sxs-lookup"><span data-stu-id="57b88-116">Click Formula.</span></span>
3. <span data-ttu-id="57b88-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57b88-117">Close the page.</span></span>
4. <span data-ttu-id="57b88-118">Kliknij przycisk Produkty towarzyszące.</span><span class="sxs-lookup"><span data-stu-id="57b88-118">Click Co-products.</span></span>
5. <span data-ttu-id="57b88-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57b88-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="57b88-120">Szacowanie szarży produkcyjnej</span><span class="sxs-lookup"><span data-stu-id="57b88-120">Estimate the batch order</span></span>
1. <span data-ttu-id="57b88-121">Kliknij przycisk Szacuj.</span><span class="sxs-lookup"><span data-stu-id="57b88-121">Click Estimate.</span></span>
2. <span data-ttu-id="57b88-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="57b88-122">Click OK.</span></span>
3. <span data-ttu-id="57b88-123">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="57b88-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="57b88-124">Kliknij opcję Wyświetl szczegóły obliczeń.</span><span class="sxs-lookup"><span data-stu-id="57b88-124">Click View calculation details.</span></span>
5. <span data-ttu-id="57b88-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57b88-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="57b88-126">Zwalnianie szarży produkcyjnej</span><span class="sxs-lookup"><span data-stu-id="57b88-126">Release the batch order</span></span>
1. <span data-ttu-id="57b88-127">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="57b88-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="57b88-128">Kliknij opcję Zwolnienie.</span><span class="sxs-lookup"><span data-stu-id="57b88-128">Click Release.</span></span>
3. <span data-ttu-id="57b88-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="57b88-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="57b88-130">Planowanie zadań produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="57b88-130">Schedule production jobs</span></span>
1. <span data-ttu-id="57b88-131">W okienku akcji kliknij pozycję Harmonogram.</span><span class="sxs-lookup"><span data-stu-id="57b88-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="57b88-132">Kliknij harmonogram zadań.</span><span class="sxs-lookup"><span data-stu-id="57b88-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="57b88-133">W polu Ograniczone zdolności produkcyjne wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="57b88-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="57b88-134">W polu Ograniczone materiały wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="57b88-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="57b88-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="57b88-135">Click OK.</span></span>
6. <span data-ttu-id="57b88-136">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="57b88-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="57b88-137">Kliknij opcję Wszystkie zadania.</span><span class="sxs-lookup"><span data-stu-id="57b88-137">Click All jobs.</span></span>
8. <span data-ttu-id="57b88-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57b88-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="57b88-139">Uruchamianie szarży produkcyjnej</span><span class="sxs-lookup"><span data-stu-id="57b88-139">Start the batch order</span></span>
1. <span data-ttu-id="57b88-140">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="57b88-140">Click Start.</span></span>
2. <span data-ttu-id="57b88-141">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="57b88-141">Click the General tab.</span></span>
3. <span data-ttu-id="57b88-142">W polu Księgowanie listy pobrania wybierz wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="57b88-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="57b88-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="57b88-143">Click OK.</span></span>
5. <span data-ttu-id="57b88-144">W okienku akcji kliknij pozycję Widok.</span><span class="sxs-lookup"><span data-stu-id="57b88-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="57b88-145">Kliknij opcję Lista pobrania.</span><span class="sxs-lookup"><span data-stu-id="57b88-145">Click Picking list.</span></span>
7. <span data-ttu-id="57b88-146">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="57b88-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="57b88-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57b88-147">Close the page.</span></span>
9. <span data-ttu-id="57b88-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57b88-148">Close the page.</span></span>
10. <span data-ttu-id="57b88-149">Kliknij opcję Karta marszruty.</span><span class="sxs-lookup"><span data-stu-id="57b88-149">Click Route card.</span></span>
11. <span data-ttu-id="57b88-150">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="57b88-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="57b88-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57b88-151">Close the page.</span></span>
13. <span data-ttu-id="57b88-152">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="57b88-152">Close the page.</span></span>

