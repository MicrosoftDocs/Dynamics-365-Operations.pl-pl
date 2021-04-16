---
title: Transakcja poręczenia
description: Ta procedura poprowadzi przez proces tworzenia poręczenia.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 089515287fc5706983b10614f69b4b1cd90178c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834723"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="3cd41-103">Transakcja poręczenia</span><span class="sxs-lookup"><span data-stu-id="3cd41-103">Letter of guarantee transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3cd41-104">Ta procedura poprowadzi przez proces tworzenia poręczenia.</span><span class="sxs-lookup"><span data-stu-id="3cd41-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="3cd41-105">Następujące zadania należy wykonać przed wykonaniem tej procedury:</span><span class="sxs-lookup"><span data-stu-id="3cd41-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="3cd41-106">Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczenia.</span><span class="sxs-lookup"><span data-stu-id="3cd41-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="3cd41-107">Tworzenie umowy instrumentu bankowego dla poręczenia.</span><span class="sxs-lookup"><span data-stu-id="3cd41-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="3cd41-108">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="3cd41-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="3cd41-109">Tworzenie zamówienia sprzedaży z poręczeniem</span><span class="sxs-lookup"><span data-stu-id="3cd41-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="3cd41-110">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3cd41-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="3cd41-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3cd41-111">Click New.</span></span>
3. <span data-ttu-id="3cd41-112">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3cd41-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="3cd41-113">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="3cd41-113">Expand the General section.</span></span>
5. <span data-ttu-id="3cd41-114">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3cd41-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="3cd41-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="3cd41-116">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3cd41-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="3cd41-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="3cd41-118">W polu Typ dokumentu bankowego wybierz opcję „Poręczenie”.</span><span class="sxs-lookup"><span data-stu-id="3cd41-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="3cd41-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-119">Click OK.</span></span>
11. <span data-ttu-id="3cd41-120">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3cd41-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="3cd41-121">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="3cd41-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="3cd41-122">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="3cd41-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="3cd41-123">Kliknij kartę Dostawa.</span><span class="sxs-lookup"><span data-stu-id="3cd41-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="3cd41-124">Uwaga: W polu Kontrola daty dostawy wybierz wartość Brak.</span><span class="sxs-lookup"><span data-stu-id="3cd41-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="3cd41-125">W polu Żądana data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="3cd41-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="3cd41-126">W polu Potwierdzona data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="3cd41-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="3cd41-127">Przetwarzanie poręczenia_Wniosek</span><span class="sxs-lookup"><span data-stu-id="3cd41-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="3cd41-128">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="3cd41-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="3cd41-129">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="3cd41-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="3cd41-130">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="3cd41-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="3cd41-131">Kliknij przycisk Wniosek, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3cd41-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="3cd41-132">W polu Typ wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3cd41-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="3cd41-133">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="3cd41-134">W polu Wartość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="3cd41-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="3cd41-135">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="3cd41-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="3cd41-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-136">Click OK.</span></span>
10. <span data-ttu-id="3cd41-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3cd41-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="3cd41-138">Przetwarzanie poręczenia_Prześlij do banku</span><span class="sxs-lookup"><span data-stu-id="3cd41-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="3cd41-139">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="3cd41-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="3cd41-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3cd41-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="3cd41-141">Kliknij przycisk Prześlij do banku, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3cd41-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="3cd41-142">W polu Konto bankowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3cd41-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="3cd41-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="3cd41-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="3cd41-145">Przetwarzanie poręczenia_Otrzymaj z banku</span><span class="sxs-lookup"><span data-stu-id="3cd41-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="3cd41-146">Kliknij opcję Otrzymaj z banku, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3cd41-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="3cd41-147">W polu Kod banku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3cd41-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="3cd41-148">Sprawdź wartości w polach obliczeniowych Marża i Wydatki.</span><span class="sxs-lookup"><span data-stu-id="3cd41-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="3cd41-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-149">Click OK.</span></span>
4. <span data-ttu-id="3cd41-150">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="3cd41-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="3cd41-151">Sprawdź rekord „Otrzymaj z banku”.</span><span class="sxs-lookup"><span data-stu-id="3cd41-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="3cd41-152">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="3cd41-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="3cd41-153">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="3cd41-153">Click Lines.</span></span>
    * <span data-ttu-id="3cd41-154">Sprawdź księgowanie wpisów w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="3cd41-155">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3cd41-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="3cd41-156">Przetwarzanie poręczenia_Przekaż beneficjentowi</span><span class="sxs-lookup"><span data-stu-id="3cd41-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="3cd41-157">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3cd41-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="3cd41-158">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="3cd41-159">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="3cd41-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="3cd41-160">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="3cd41-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="3cd41-161">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="3cd41-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="3cd41-162">Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3cd41-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="3cd41-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-163">Click OK.</span></span>
8. <span data-ttu-id="3cd41-164">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="3cd41-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="3cd41-165">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3cd41-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="3cd41-166">Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3cd41-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="3cd41-167">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-167">Click OK.</span></span>
12. <span data-ttu-id="3cd41-168">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="3cd41-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="3cd41-169">Sprawdź rekord „Przekaż beneficjentowi”.</span><span class="sxs-lookup"><span data-stu-id="3cd41-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="3cd41-170">Przetwarzanie poręczenia_Zwiększ wartość</span><span class="sxs-lookup"><span data-stu-id="3cd41-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="3cd41-171">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3cd41-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="3cd41-172">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="3cd41-173">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="3cd41-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="3cd41-174">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="3cd41-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="3cd41-175">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="3cd41-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="3cd41-176">Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3cd41-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="3cd41-177">W polu Wartość do dodania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3cd41-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="3cd41-178">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-178">Click OK.</span></span>
9. <span data-ttu-id="3cd41-179">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="3cd41-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="3cd41-180">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3cd41-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="3cd41-181">Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3cd41-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="3cd41-182">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-182">Click OK.</span></span>
13. <span data-ttu-id="3cd41-183">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="3cd41-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="3cd41-184">Sprawdź rekord „Zwiększ wartość”.</span><span class="sxs-lookup"><span data-stu-id="3cd41-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="3cd41-185">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3cd41-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="3cd41-186">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="3cd41-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="3cd41-187">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="3cd41-187">Click Lines.</span></span>
    * <span data-ttu-id="3cd41-188">Sprawdź zaksięgowanie wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="3cd41-189">Przetwarzanie poręczenia_Zlikwiduj</span><span class="sxs-lookup"><span data-stu-id="3cd41-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="3cd41-190">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3cd41-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="3cd41-191">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="3cd41-192">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="3cd41-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="3cd41-193">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="3cd41-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="3cd41-194">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="3cd41-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="3cd41-195">Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3cd41-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="3cd41-196">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-196">Click OK.</span></span>
8. <span data-ttu-id="3cd41-197">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="3cd41-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="3cd41-198">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3cd41-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="3cd41-199">Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3cd41-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="3cd41-200">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cd41-200">Click OK.</span></span>
12. <span data-ttu-id="3cd41-201">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="3cd41-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="3cd41-202">Sprawdź rekord „Zlikwiduj”.</span><span class="sxs-lookup"><span data-stu-id="3cd41-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="3cd41-203">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3cd41-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="3cd41-204">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="3cd41-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="3cd41-205">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="3cd41-205">Click Lines.</span></span>
    * <span data-ttu-id="3cd41-206">Sprawdź zaksięgowanie wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="3cd41-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="3cd41-207">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3cd41-207">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]