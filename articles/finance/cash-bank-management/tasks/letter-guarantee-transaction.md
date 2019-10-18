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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff105bdefff2ea93c853d590c77391653f50a4dc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179425"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="4c594-103">Transakcja poręczenia</span><span class="sxs-lookup"><span data-stu-id="4c594-103">Letter of guarantee transaction</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4c594-104">Ta procedura poprowadzi przez proces tworzenia poręczenia.</span><span class="sxs-lookup"><span data-stu-id="4c594-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="4c594-105">Następujące zadania należy wykonać przed wykonaniem tej procedury:</span><span class="sxs-lookup"><span data-stu-id="4c594-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="4c594-106">Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczenia.</span><span class="sxs-lookup"><span data-stu-id="4c594-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="4c594-107">Tworzenie umowy instrumentu bankowego dla poręczenia.</span><span class="sxs-lookup"><span data-stu-id="4c594-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="4c594-108">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="4c594-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="4c594-109">Tworzenie zamówienia sprzedaży z poręczeniem</span><span class="sxs-lookup"><span data-stu-id="4c594-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="4c594-110">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c594-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4c594-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4c594-111">Click New.</span></span>
3. <span data-ttu-id="4c594-112">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c594-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="4c594-113">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="4c594-113">Expand the General section.</span></span>
5. <span data-ttu-id="4c594-114">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c594-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="4c594-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="4c594-116">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c594-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="4c594-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="4c594-118">W polu Typ dokumentu bankowego wybierz opcję „Poręczenie”.</span><span class="sxs-lookup"><span data-stu-id="4c594-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="4c594-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-119">Click OK.</span></span>
11. <span data-ttu-id="4c594-120">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c594-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="4c594-121">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="4c594-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="4c594-122">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="4c594-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="4c594-123">Kliknij kartę Dostawa.</span><span class="sxs-lookup"><span data-stu-id="4c594-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="4c594-124">Uwaga: W polu Kontrola daty dostawy wybierz wartość Brak.</span><span class="sxs-lookup"><span data-stu-id="4c594-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="4c594-125">W polu Żądana data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="4c594-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="4c594-126">W polu Potwierdzona data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="4c594-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="4c594-127">Przetwarzanie poręczenia_Wniosek</span><span class="sxs-lookup"><span data-stu-id="4c594-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="4c594-128">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="4c594-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="4c594-129">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="4c594-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="4c594-130">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="4c594-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="4c594-131">Kliknij przycisk Wniosek, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4c594-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="4c594-132">W polu Typ wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c594-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="4c594-133">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="4c594-134">W polu Wartość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="4c594-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="4c594-135">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="4c594-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="4c594-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-136">Click OK.</span></span>
10. <span data-ttu-id="4c594-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c594-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="4c594-138">Przetwarzanie poręczenia_Prześlij do banku</span><span class="sxs-lookup"><span data-stu-id="4c594-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="4c594-139">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="4c594-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="4c594-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4c594-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="4c594-141">Kliknij przycisk Prześlij do banku, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4c594-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="4c594-142">W polu Konto bankowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c594-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="4c594-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4c594-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="4c594-145">Przetwarzanie poręczenia_Otrzymaj z banku</span><span class="sxs-lookup"><span data-stu-id="4c594-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="4c594-146">Kliknij opcję Otrzymaj z banku, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4c594-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="4c594-147">W polu Kod banku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c594-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="4c594-148">Sprawdź wartości w polach obliczeniowych Marża i Wydatki.</span><span class="sxs-lookup"><span data-stu-id="4c594-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="4c594-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-149">Click OK.</span></span>
4. <span data-ttu-id="4c594-150">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="4c594-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="4c594-151">Sprawdź rekord „Otrzymaj z banku”.</span><span class="sxs-lookup"><span data-stu-id="4c594-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="4c594-152">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="4c594-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="4c594-153">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="4c594-153">Click Lines.</span></span>
    * <span data-ttu-id="4c594-154">Sprawdź księgowanie wpisów w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="4c594-155">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c594-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="4c594-156">Przetwarzanie poręczenia_Przekaż beneficjentowi</span><span class="sxs-lookup"><span data-stu-id="4c594-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="4c594-157">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c594-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4c594-158">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="4c594-159">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="4c594-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="4c594-160">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="4c594-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="4c594-161">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="4c594-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="4c594-162">Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4c594-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="4c594-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-163">Click OK.</span></span>
8. <span data-ttu-id="4c594-164">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="4c594-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="4c594-165">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4c594-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="4c594-166">Kliknij przycisk Przekaż beneficjentowi, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4c594-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="4c594-167">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-167">Click OK.</span></span>
12. <span data-ttu-id="4c594-168">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="4c594-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="4c594-169">Sprawdź rekord „Przekaż beneficjentowi”.</span><span class="sxs-lookup"><span data-stu-id="4c594-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="4c594-170">Przetwarzanie poręczenia_Zwiększ wartość</span><span class="sxs-lookup"><span data-stu-id="4c594-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="4c594-171">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c594-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4c594-172">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="4c594-173">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="4c594-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="4c594-174">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="4c594-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="4c594-175">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="4c594-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="4c594-176">Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4c594-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="4c594-177">W polu Wartość do dodania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c594-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="4c594-178">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-178">Click OK.</span></span>
9. <span data-ttu-id="4c594-179">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="4c594-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="4c594-180">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4c594-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="4c594-181">Kliknij przycisk Zwiększ wartość, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4c594-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="4c594-182">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-182">Click OK.</span></span>
13. <span data-ttu-id="4c594-183">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="4c594-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="4c594-184">Sprawdź rekord „Zwiększ wartość”.</span><span class="sxs-lookup"><span data-stu-id="4c594-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="4c594-185">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4c594-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="4c594-186">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="4c594-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="4c594-187">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="4c594-187">Click Lines.</span></span>
    * <span data-ttu-id="4c594-188">Sprawdź zaksięgowanie wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="4c594-189">Przetwarzanie poręczenia_Zlikwiduj</span><span class="sxs-lookup"><span data-stu-id="4c594-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="4c594-190">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4c594-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4c594-191">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="4c594-192">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="4c594-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="4c594-193">Kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="4c594-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="4c594-194">W okienku akcji kliknij opcję Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="4c594-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="4c594-195">Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4c594-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="4c594-196">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-196">Click OK.</span></span>
8. <span data-ttu-id="4c594-197">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Poręczenia.</span><span class="sxs-lookup"><span data-stu-id="4c594-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="4c594-198">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4c594-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="4c594-199">Kliknij przycisk Zlikwiduj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4c594-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="4c594-200">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4c594-200">Click OK.</span></span>
12. <span data-ttu-id="4c594-201">Rozwiń sekcję Akcje.</span><span class="sxs-lookup"><span data-stu-id="4c594-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="4c594-202">Sprawdź rekord „Zlikwiduj”.</span><span class="sxs-lookup"><span data-stu-id="4c594-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="4c594-203">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4c594-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="4c594-204">Kliknij, aby otworzyć łącze znajdujące się w polu Arkusz z numerem partii.</span><span class="sxs-lookup"><span data-stu-id="4c594-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="4c594-205">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="4c594-205">Click Lines.</span></span>
    * <span data-ttu-id="4c594-206">Sprawdź zaksięgowanie wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="4c594-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="4c594-207">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4c594-207">Close the page.</span></span>

