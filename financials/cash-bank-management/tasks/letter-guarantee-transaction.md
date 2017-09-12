--- 
title: "Transakcja poręczenia"
description: "Ta procedura poprowadzi przez proces tworzenia poręczenia."
author: kweekley
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 21895bcda8f0fe46e9b7c4b2189ca8b13e0dc012
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="6a7a9-103">Transakcja poręczenia</span><span class="sxs-lookup"><span data-stu-id="6a7a9-103">Letter of guarantee transaction</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6a7a9-104">Ta procedura poprowadzi przez proces tworzenia poręczenia.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="6a7a9-105">Następujące zadania należy wykonać przed wykonaniem tej procedury:</span><span class="sxs-lookup"><span data-stu-id="6a7a9-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="6a7a9-106">Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczenia.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="6a7a9-107">Tworzenie umowy instrumentu bankowego dla poręczenia.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="6a7a9-108">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="6a7a9-109">Tworzenie zamówienia sprzedaży z poręczeniem</span><span class="sxs-lookup"><span data-stu-id="6a7a9-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="6a7a9-110">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6a7a9-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-111">Click New.</span></span>
3. <span data-ttu-id="6a7a9-112">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="6a7a9-113">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-113">Expand the General section.</span></span>
5. <span data-ttu-id="6a7a9-114">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="6a7a9-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="6a7a9-116">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="6a7a9-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="6a7a9-118">W polu Typ dokumentu bankowego wybierz opcję „Poręczenie”.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="6a7a9-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-119">Click OK.</span></span>
11. <span data-ttu-id="6a7a9-120">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="6a7a9-121">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="6a7a9-122">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="6a7a9-123">Kliknij kartę Dostawa.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="6a7a9-124">Uwaga: W polu Kontrola daty dostawy wybierz wartość Brak.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="6a7a9-125">W polu Żądana data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="6a7a9-126">W polu Potwierdzona data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guaranteerequest"></a><span data-ttu-id="6a7a9-127">Przetwarzanie poręczenia_Wniosek</span><span class="sxs-lookup"><span data-stu-id="6a7a9-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="6a7a9-128">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="6a7a9-129">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="6a7a9-130">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="6a7a9-131">Kliknij przycisk Wniosek, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="6a7a9-132">W polu Typ wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="6a7a9-133">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="6a7a9-134">W polu Wartość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="6a7a9-135">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="6a7a9-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-136">Click OK.</span></span>
10. <span data-ttu-id="6a7a9-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-137">Close the page.</span></span>

## <a name="process-letter-of-guaranteesubmit-to-bank"></a><span data-ttu-id="6a7a9-138">Przetwarzanie poręczenia_Prześlij do banku</span><span class="sxs-lookup"><span data-stu-id="6a7a9-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="6a7a9-139">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="6a7a9-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="6a7a9-141">Kliknij przycisk Prześlij do banku, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="6a7a9-142">W polu Konto bankowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="6a7a9-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="6a7a9-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-144">Click OK.</span></span>

## <a name="process-letter-of-guaranteereceive-from-bank"></a><span data-ttu-id="6a7a9-145">Przetwarzanie poręczenia_Otrzymaj z banku</span><span class="sxs-lookup"><span data-stu-id="6a7a9-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="6a7a9-146">Kliknij opcję Otrzymaj z banku, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="6a7a9-147">W polu Kod banku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="6a7a9-148">Sprawdź wartości w polach obliczeniowych Marża i Wydatki.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="6a7a9-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-149">Click OK.</span></span>
4. <span data-ttu-id="6a7a9-150">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="6a7a9-151">Sprawdź rekord „Otrzymaj z banku”.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="6a7a9-152">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="6a7a9-153">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-153">Click Lines.</span></span>
    * <span data-ttu-id="6a7a9-154">Sprawdź księgowanie wpisów w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="6a7a9-155">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-155">Close the page.</span></span>

## <a name="process-letter-of-guaranteegive-to-beneficiary"></a><span data-ttu-id="6a7a9-156">Przetwarzanie poręczenia_Przekaż beneficjentowi</span><span class="sxs-lookup"><span data-stu-id="6a7a9-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="6a7a9-157">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6a7a9-158">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="6a7a9-159">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="6a7a9-160">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="6a7a9-161">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="6a7a9-162">Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="6a7a9-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-163">Click OK.</span></span>
8. <span data-ttu-id="6a7a9-164">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="6a7a9-165">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="6a7a9-166">Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="6a7a9-167">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-167">Click OK.</span></span>
12. <span data-ttu-id="6a7a9-168">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="6a7a9-169">Sprawdź rekord „Przekaż beneficjentowi”.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guaranteeincrease-value"></a><span data-ttu-id="6a7a9-170">Przetwarzanie poręczenia_Zwiększ wartość</span><span class="sxs-lookup"><span data-stu-id="6a7a9-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="6a7a9-171">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6a7a9-172">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="6a7a9-173">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="6a7a9-174">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="6a7a9-175">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="6a7a9-176">Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="6a7a9-177">W polu Wartość do dodania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="6a7a9-178">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-178">Click OK.</span></span>
9. <span data-ttu-id="6a7a9-179">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="6a7a9-180">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="6a7a9-181">Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="6a7a9-182">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-182">Click OK.</span></span>
13. <span data-ttu-id="6a7a9-183">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="6a7a9-184">Sprawdź rekord „Zwiększ wartość”.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="6a7a9-185">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="6a7a9-186">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="6a7a9-187">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-187">Click Lines.</span></span>
    * <span data-ttu-id="6a7a9-188">Sprawdź zaksięgowanie wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guaranteeliquidate"></a><span data-ttu-id="6a7a9-189">Przetwarzanie poręczenia_Zlikwiduj</span><span class="sxs-lookup"><span data-stu-id="6a7a9-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="6a7a9-190">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6a7a9-191">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="6a7a9-192">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="6a7a9-193">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="6a7a9-194">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="6a7a9-195">Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="6a7a9-196">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-196">Click OK.</span></span>
8. <span data-ttu-id="6a7a9-197">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="6a7a9-198">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="6a7a9-199">Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="6a7a9-200">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-200">Click OK.</span></span>
12. <span data-ttu-id="6a7a9-201">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="6a7a9-202">Sprawdź rekord „Zlikwiduj”.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="6a7a9-203">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="6a7a9-204">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="6a7a9-205">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-205">Click Lines.</span></span>
    * <span data-ttu-id="6a7a9-206">Sprawdź zaksięgowanie wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="6a7a9-207">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-207">Close the page.</span></span>


