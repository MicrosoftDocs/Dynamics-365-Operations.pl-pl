--- 
title: "Określanie sekwencji zadań produkcji procesowej"
description: "Ta procedura wykorzystuje farby dla przykładu prezentującego sposób ustawienia kolejności planowanych zamówień zgodnie z priorytetem koloru i rozmiaru paczki."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a25a4575ca1600b07b2dac5949c8775bcd162650
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="sequence-production-jobs-for-process-manufacturing"></a><span data-ttu-id="41bad-103">Określanie sekwencji zadań produkcji procesowej</span><span class="sxs-lookup"><span data-stu-id="41bad-103">Sequence production jobs for process manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="41bad-104">Ta procedura wykorzystuje farby dla przykładu prezentującego sposób ustawienia kolejności planowanych zamówień zgodnie z priorytetem koloru i rozmiaru paczki.</span><span class="sxs-lookup"><span data-stu-id="41bad-104">This procedure uses paint products as an example to show how to sequence planned orders according to the priority of color and package size.</span></span> <span data-ttu-id="41bad-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USPI.</span><span class="sxs-lookup"><span data-stu-id="41bad-105">The demo data company used to create this procedure is USPI.</span></span> <span data-ttu-id="41bad-106">Ta procedura jest przeznaczona dla planisty produkcji.</span><span class="sxs-lookup"><span data-stu-id="41bad-106">This procedure is intended for the production planner.</span></span>


## <a name="run-master-planning-for-uspi"></a><span data-ttu-id="41bad-107">Wykonywanie planowania głównego dla firmy USPI</span><span class="sxs-lookup"><span data-stu-id="41bad-107">Run master planning for USPI</span></span>
1. <span data-ttu-id="41bad-108">Wybierz kolejno opcje Planowanie główne > Planowanie główne > Uruchom > Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="41bad-108">Go to Master planning > Master planning > Run > Master planning.</span></span>
2. <span data-ttu-id="41bad-109">W polu Plan główny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="41bad-109">In the Master plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="41bad-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="41bad-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="41bad-111">Wybierz opcję Plan główny.</span><span class="sxs-lookup"><span data-stu-id="41bad-111">Select MasterPlan.</span></span>  
4. <span data-ttu-id="41bad-112">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="41bad-112">Click OK.</span></span>
    * <span data-ttu-id="41bad-113">Spowoduje to rozpoczęcie planowania głównego, łącznie z procesem ustalania kolejności operacji.</span><span class="sxs-lookup"><span data-stu-id="41bad-113">This starts Master Planning, including the sequence process.</span></span> <span data-ttu-id="41bad-114">Proces może potrwać kilka minut.</span><span class="sxs-lookup"><span data-stu-id="41bad-114">This process can take a few minutes.</span></span>  

## <a name="view-planned-orders-for-the-paint-products"></a><span data-ttu-id="41bad-115">Wyświetlanie planowanych zamówień na farby</span><span class="sxs-lookup"><span data-stu-id="41bad-115">View planned orders for the paint products</span></span>
1. <span data-ttu-id="41bad-116">Wybierz kolejno opcje Planowanie główne > Planowanie główne > Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="41bad-116">Go to Master planning > Master planning > Planned orders.</span></span>
2. <span data-ttu-id="41bad-117">Rozwiń pole informacji Szczegóły pozycji.</span><span class="sxs-lookup"><span data-stu-id="41bad-117">Expand the Item details FactBox.</span></span>
3. <span data-ttu-id="41bad-118">Rozwiń pole informacji Szczegóły harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="41bad-118">Expand the Schedule details FactBox.</span></span>
4. <span data-ttu-id="41bad-119">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="41bad-119">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="41bad-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="41bad-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="41bad-121">Wybierz opcję Plan główny.</span><span class="sxs-lookup"><span data-stu-id="41bad-121">Select MasterPlan.</span></span>  
6. <span data-ttu-id="41bad-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="41bad-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="41bad-123">Użyj szybkiego filtru, aby filtrować na podstawie pola Numer pozycji z wartością „P300”.</span><span class="sxs-lookup"><span data-stu-id="41bad-123">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="41bad-124">Odblokuj, aby przewinąć w prawo i zobaczyć datę zamówienia oraz datę dostawy.</span><span class="sxs-lookup"><span data-stu-id="41bad-124">Unlock to scroll to the right to see the order date and delivery date.</span></span> <span data-ttu-id="41bad-125">Zwróć uwagę, że te towary mają datę zamówienia Dzisiaj, a daty dostawy zamówień planowanych nie są ustawione w kolejności pod względem priorytetu koloru i rozmiaru paczki, jak to widać w nazwie produktu.</span><span class="sxs-lookup"><span data-stu-id="41bad-125">Notice that these items have an order date of Today and the delivery dates for the planned orders are not sequenced after the priority of color and package size, as shown in the product name.</span></span> <span data-ttu-id="41bad-126">Można umieścić wskaźnik myszy nad numerem towaru, aby zobaczyć nazwę produktu i priorytet.</span><span class="sxs-lookup"><span data-stu-id="41bad-126">You can hover over an item number to see the product name and priority.</span></span>  

## <a name="sequence-planned-orders-for-paint"></a><span data-ttu-id="41bad-127">Ustawianie kolejności planowanych zamówień na farby</span><span class="sxs-lookup"><span data-stu-id="41bad-127">Sequence planned orders for paint</span></span>
1. <span data-ttu-id="41bad-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="41bad-128">Close the page.</span></span>
2. <span data-ttu-id="41bad-129">Wybierz kolejno opcje Planowanie główne > Planowanie główne > Kolejne planowane zlecenia.</span><span class="sxs-lookup"><span data-stu-id="41bad-129">Go to Master planning > Master planning > Sequenced planned orders.</span></span>
3. <span data-ttu-id="41bad-130">Rozwiń pole informacji Szczegóły pozycji.</span><span class="sxs-lookup"><span data-stu-id="41bad-130">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="41bad-131">Rozwiń pole informacji Szczegóły harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="41bad-131">Expand the Schedule details FactBox.</span></span>
    * <span data-ttu-id="41bad-132">Uwaga: Tutaj widać, że daty/godziny rozpoczęcia planowanych zamówień są ustawione w kolejności według koloru i rozmiaru paczki w przedziale czasu 28 dni.</span><span class="sxs-lookup"><span data-stu-id="41bad-132">Note: Here you see that the Start date/time for the planned orders are sequenced according to color and package size within a bucket period of 28 days.</span></span> <span data-ttu-id="41bad-133">Te okresy są definiowane przez liczbę w polu Kampania.</span><span class="sxs-lookup"><span data-stu-id="41bad-133">These periods are defined by a number in the field Campaign.</span></span> <span data-ttu-id="41bad-134">Formularz zamówienia planowanego sekwencji działa jak typowy formularz zamówienia planowanego i planista produkcji może tutaj akceptować zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="41bad-134">The sequenced planned order form acts like the typical planned order form, and the production planner can firm the planned orders here.</span></span>  
5. <span data-ttu-id="41bad-135">Zaznacz wszystkie wiersze.</span><span class="sxs-lookup"><span data-stu-id="41bad-135">Mark all rows.</span></span>
6. <span data-ttu-id="41bad-136">Kliknij przycisk Akceptuj.</span><span class="sxs-lookup"><span data-stu-id="41bad-136">Click Accept.</span></span>
    * <span data-ttu-id="41bad-137">Spowoduje to aktualizację planowanych zamówień o wybraną akcję sekwencji Opóźnij lub Przejdź dalej.</span><span class="sxs-lookup"><span data-stu-id="41bad-137">This will update the planned orders with the selected sequence action of either Postpone or Advance.</span></span>  

## <a name="verify-the-sequence-of-the-planned-orders"></a><span data-ttu-id="41bad-138">Weryfikowanie kolejności planowanych zamówień</span><span class="sxs-lookup"><span data-stu-id="41bad-138">Verify the sequence of the planned orders</span></span>
1. <span data-ttu-id="41bad-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="41bad-139">Close the page.</span></span>
2. <span data-ttu-id="41bad-140">Wybierz kolejno opcje Planowanie główne > Planowanie główne > Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="41bad-140">Go to Master planning > Master planning > Planned orders.</span></span>
3. <span data-ttu-id="41bad-141">Rozwiń pole informacji Szczegóły pozycji.</span><span class="sxs-lookup"><span data-stu-id="41bad-141">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="41bad-142">Rozwiń pole informacji Szczegóły harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="41bad-142">Expand the Schedule details FactBox.</span></span>
5. <span data-ttu-id="41bad-143">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="41bad-143">In the Plan field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="41bad-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="41bad-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="41bad-145">Wybierz opcję Plan główny.</span><span class="sxs-lookup"><span data-stu-id="41bad-145">Select MasterPlan.</span></span>  
7. <span data-ttu-id="41bad-146">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="41bad-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="41bad-147">Użyj szybkiego filtru, aby filtrować na podstawie pola Numer pozycji z wartością „P300”.</span><span class="sxs-lookup"><span data-stu-id="41bad-147">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="41bad-148">Zwróć uwagę, że zamówienia są teraz ustawione w kolejności według priorytetu koloru i rozmiaru, a planowane zamówienia rozpoczynają się od najwcześniejszej daty zamówienia i daty dostawy.</span><span class="sxs-lookup"><span data-stu-id="41bad-148">Notice that the orders now are sequenced according to the priority of color and size and the planned orders start at the earliest order date and delivery date.</span></span> <span data-ttu-id="41bad-149">Sprawdź poprawność zawartości kolumny Data zamówienia lub pola Data rozpoczęcia w polu informacji Szczegóły harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="41bad-149">Validate the Order date column or the Start date in the Schedule details FactBbox.</span></span>  


