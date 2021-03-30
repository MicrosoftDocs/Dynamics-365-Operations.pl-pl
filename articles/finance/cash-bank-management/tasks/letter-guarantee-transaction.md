---
title: Transakcja poręczenia
description: Ta procedura poprowadzi przez proces tworzenia poręczenia.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 566849cfcedd29f4bb92d08a17b67e16b1cbc372
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225376"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="9f8ec-103">Transakcja poręczenia</span><span class="sxs-lookup"><span data-stu-id="9f8ec-103">Letter of guarantee transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9f8ec-104">Ta procedura poprowadzi przez proces tworzenia poręczenia.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="9f8ec-105">Następujące zadania należy wykonać przed wykonaniem tej procedury:</span><span class="sxs-lookup"><span data-stu-id="9f8ec-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="9f8ec-106">Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczenia.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="9f8ec-107">Tworzenie umowy instrumentu bankowego dla poręczenia.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="9f8ec-108">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="9f8ec-109">Tworzenie zamówienia sprzedaży z poręczeniem</span><span class="sxs-lookup"><span data-stu-id="9f8ec-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="9f8ec-110">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="9f8ec-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-111">Click New.</span></span>
3. <span data-ttu-id="9f8ec-112">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="9f8ec-113">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-113">Expand the General section.</span></span>
5. <span data-ttu-id="9f8ec-114">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="9f8ec-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="9f8ec-116">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="9f8ec-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="9f8ec-118">W polu Typ dokumentu bankowego wybierz opcję „Poręczenie”.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="9f8ec-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-119">Click OK.</span></span>
11. <span data-ttu-id="9f8ec-120">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="9f8ec-121">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="9f8ec-122">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="9f8ec-123">Kliknij kartę Dostawa.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="9f8ec-124">Uwaga: W polu Kontrola daty dostawy wybierz wartość Brak.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="9f8ec-125">W polu Żądana data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="9f8ec-126">W polu Potwierdzona data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="9f8ec-127">Przetwarzanie poręczenia_Wniosek</span><span class="sxs-lookup"><span data-stu-id="9f8ec-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="9f8ec-128">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="9f8ec-129">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="9f8ec-130">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="9f8ec-131">Kliknij przycisk Wniosek, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="9f8ec-132">W polu Typ wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="9f8ec-133">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="9f8ec-134">W polu Wartość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="9f8ec-135">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="9f8ec-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-136">Click OK.</span></span>
10. <span data-ttu-id="9f8ec-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="9f8ec-138">Przetwarzanie poręczenia_Prześlij do banku</span><span class="sxs-lookup"><span data-stu-id="9f8ec-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="9f8ec-139">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="9f8ec-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="9f8ec-141">Kliknij przycisk Prześlij do banku, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="9f8ec-142">W polu Konto bankowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="9f8ec-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="9f8ec-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="9f8ec-145">Przetwarzanie poręczenia_Otrzymaj z banku</span><span class="sxs-lookup"><span data-stu-id="9f8ec-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="9f8ec-146">Kliknij opcję Otrzymaj z banku, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="9f8ec-147">W polu Kod banku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="9f8ec-148">Sprawdź wartości w polach obliczeniowych Marża i Wydatki.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="9f8ec-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-149">Click OK.</span></span>
4. <span data-ttu-id="9f8ec-150">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="9f8ec-151">Sprawdź rekord „Otrzymaj z banku”.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="9f8ec-152">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="9f8ec-153">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-153">Click Lines.</span></span>
    * <span data-ttu-id="9f8ec-154">Sprawdź księgowanie wpisów w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="9f8ec-155">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="9f8ec-156">Przetwarzanie poręczenia_Przekaż beneficjentowi</span><span class="sxs-lookup"><span data-stu-id="9f8ec-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="9f8ec-157">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="9f8ec-158">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="9f8ec-159">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="9f8ec-160">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="9f8ec-161">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="9f8ec-162">Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="9f8ec-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-163">Click OK.</span></span>
8. <span data-ttu-id="9f8ec-164">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="9f8ec-165">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="9f8ec-166">Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="9f8ec-167">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-167">Click OK.</span></span>
12. <span data-ttu-id="9f8ec-168">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="9f8ec-169">Sprawdź rekord „Przekaż beneficjentowi”.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="9f8ec-170">Przetwarzanie poręczenia_Zwiększ wartość</span><span class="sxs-lookup"><span data-stu-id="9f8ec-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="9f8ec-171">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="9f8ec-172">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="9f8ec-173">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="9f8ec-174">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="9f8ec-175">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="9f8ec-176">Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="9f8ec-177">W polu Wartość do dodania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="9f8ec-178">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-178">Click OK.</span></span>
9. <span data-ttu-id="9f8ec-179">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="9f8ec-180">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="9f8ec-181">Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="9f8ec-182">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-182">Click OK.</span></span>
13. <span data-ttu-id="9f8ec-183">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="9f8ec-184">Sprawdź rekord „Zwiększ wartość”.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="9f8ec-185">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="9f8ec-186">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="9f8ec-187">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-187">Click Lines.</span></span>
    * <span data-ttu-id="9f8ec-188">Sprawdź zaksięgowanie wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="9f8ec-189">Przetwarzanie poręczenia_Zlikwiduj</span><span class="sxs-lookup"><span data-stu-id="9f8ec-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="9f8ec-190">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="9f8ec-191">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="9f8ec-192">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="9f8ec-193">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="9f8ec-194">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="9f8ec-195">Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="9f8ec-196">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-196">Click OK.</span></span>
8. <span data-ttu-id="9f8ec-197">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="9f8ec-198">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="9f8ec-199">Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="9f8ec-200">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-200">Click OK.</span></span>
12. <span data-ttu-id="9f8ec-201">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="9f8ec-202">Sprawdź rekord „Zlikwiduj”.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="9f8ec-203">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="9f8ec-204">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="9f8ec-205">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-205">Click Lines.</span></span>
    * <span data-ttu-id="9f8ec-206">Sprawdź zaksięgowanie wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="9f8ec-207">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9f8ec-207">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]