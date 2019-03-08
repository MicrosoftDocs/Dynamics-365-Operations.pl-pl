---
title: Akredytywa eksportowa
description: Ta procedura poprowadzi przez proces tworzenia akredytywy eksportowej.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 730a6cc6ed4872f8d0ad92b89665587f472f6791
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "335906"
---
# <a name="export-letter-of-credit"></a><span data-ttu-id="2ac6d-103">Akredytywa eksportowa</span><span class="sxs-lookup"><span data-stu-id="2ac6d-103">Export letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2ac6d-104">Ta procedura poprowadzi przez proces tworzenia akredytywy eksportowej.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-104">This procedure walks through the process of the Export letter of credit.</span></span>

<span data-ttu-id="2ac6d-105">Akredytywa jest umową wystawianą przez bank, w której bank wyraża zgodę na zapłatę w imieniu nabywcy, jeśli zostaną spełnione warunki umowy między nabywcą a sprzedawcą.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-105">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to ensure payment on behalf of the buyer, if the terms of the agreement between the buyer and seller are met.</span></span>



<span data-ttu-id="2ac6d-106">Przed uruchomieniem tej procedury wykonaj procedury „Konfigurowanie instrumentów bankowych i profilów księgowania” oraz „Akredytywa_Tworzenie umowy instrumentu bankowego”.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-106">Run the 'Set up bank facilities and posting profiles' procedure and the 'Letter of Credit_Create a bank facility agreement' procedure prior to this procedure.</span></span> <span data-ttu-id="2ac6d-107">Aby pomyślnie wykonać tę procedurę, należy zaznaczyć firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-107">The USMF demo company must be selected in order to run this procedure successfully.</span></span>




## <a name="create-sales-order-for-export-letter-of-credit"></a><span data-ttu-id="2ac6d-108">Tworzenie zamówienia sprzedaży dla akredytywy</span><span class="sxs-lookup"><span data-stu-id="2ac6d-108">Create Sales Order for Export letter of credit</span></span>
1. <span data-ttu-id="2ac6d-109">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="2ac6d-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-110">Click New.</span></span>
3. <span data-ttu-id="2ac6d-111">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="2ac6d-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2ac6d-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2ac6d-114">Rozwiń lub zwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-114">Expand or collapse the General section.</span></span>
7. <span data-ttu-id="2ac6d-115">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-115">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac6d-116">Zaznacz oddział, w którym jest składowany towar przeznaczony do wydania.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-116">Select the Site where the item to be issued is stocked.</span></span>  
8. <span data-ttu-id="2ac6d-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2ac6d-118">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-118">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac6d-119">Zaznacz magazyn, w którym jest składowany towar przeznaczony do wydania.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-119">Select the Warehouse where item to be issued is stocked.</span></span>  
10. <span data-ttu-id="2ac6d-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2ac6d-121">Uwaga: Wybierz pole Typ dokumentu bankowego z wartością „Akredytywa”.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-121">Note: The Bank document type field should be selected with the value 'Letter of credit'.</span></span>  
11. <span data-ttu-id="2ac6d-122">W polu Typ dokumentu bankowego wybierz opcję „Akredytywa”.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-122">In the Bank document type field, select 'Letter of credit'.</span></span>
12. <span data-ttu-id="2ac6d-123">Rozwiń lub zwiń sekcję Dostawa.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-123">Expand or collapse the Delivery section.</span></span>
    * <span data-ttu-id="2ac6d-124">W polu Kontrola daty dostawy wybierz wartość Brak.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-124">Select Delivery date control = None.</span></span>  
13. <span data-ttu-id="2ac6d-125">W polu Żądana data odbioru wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-125">In the Requested receipt date field, enter a date.</span></span>
14. <span data-ttu-id="2ac6d-126">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-126">Click OK.</span></span>
15. <span data-ttu-id="2ac6d-127">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-127">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac6d-128">Zaznacz towar, który ma zostać wydany/sprzedany.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-128">Select the required item to be Issued/Sold.</span></span>  
16. <span data-ttu-id="2ac6d-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-129">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="2ac6d-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="2ac6d-131">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-131">In the Unit price field, enter a number.</span></span>
19. <span data-ttu-id="2ac6d-132">Rozwiń lub zwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-132">Expand or collapse the Line details section.</span></span>
20. <span data-ttu-id="2ac6d-133">Kliknij kartę Dostawa.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-133">Click the Delivery tab.</span></span>
21. <span data-ttu-id="2ac6d-134">W polu Żądana data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-134">In the Requested ship date field, enter a date.</span></span>
22. <span data-ttu-id="2ac6d-135">W polu Potwierdzona data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-135">In the Confirmed ship date field, enter a date.</span></span>
23. <span data-ttu-id="2ac6d-136">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-136">On the Action Pane, click Manage.</span></span>
24. <span data-ttu-id="2ac6d-137">Kliknij opcję Akredytywa.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-137">Click Letter of credit.</span></span>
25. <span data-ttu-id="2ac6d-138">W polu Numer dokumentu banku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-138">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="2ac6d-139">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-139">In the Expiration date field, enter a date and time.</span></span>
27. <span data-ttu-id="2ac6d-140">Rozwiń lub zwiń sekcję Szczegóły banku.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-140">Expand or collapse the Bank details section.</span></span>
28. <span data-ttu-id="2ac6d-141">W polu Bank wystawiający kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-141">In the Issuing bank field, click the drop-down button to open the lookup.</span></span>
29. <span data-ttu-id="2ac6d-142">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-142">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="2ac6d-143">W polu Bank doradczy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-143">In the Advising bank field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="2ac6d-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-144">In the list, find and select the desired record.</span></span>
32. <span data-ttu-id="2ac6d-145">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-145">In the list, click the link in the selected row.</span></span>
33. <span data-ttu-id="2ac6d-146">Kliknij opcję Pobierz wysyłki zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-146">Click Fetch sales order shipments.</span></span>
34. <span data-ttu-id="2ac6d-147">Kliknij opcję Wystaw dokument bankowy.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-147">Click Issue bank document.</span></span>
35. <span data-ttu-id="2ac6d-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-148">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="2ac6d-149">Księgowanie dokumentu dostawy</span><span class="sxs-lookup"><span data-stu-id="2ac6d-149">Post Packing slip</span></span>
1. <span data-ttu-id="2ac6d-150">W okienku akcji kliknij opcję Pobierz i zapakuj.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-150">On the Action Pane, click Pick and pack.</span></span>
2. <span data-ttu-id="2ac6d-151">Kliknij opcję Księguj dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-151">Click Post packing slip.</span></span>
3. <span data-ttu-id="2ac6d-152">Rozwiń lub zwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-152">Expand or collapse the Parameters section.</span></span>
4. <span data-ttu-id="2ac6d-153">W polu Ilość zaznacz opcję „Wszystko”.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-153">In the Quantity field, select 'All'.</span></span>
5. <span data-ttu-id="2ac6d-154">Rozwiń lub zwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-154">Expand or collapse the Setup section.</span></span>
6. <span data-ttu-id="2ac6d-155">W polu Data dokumentu dostawy wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-155">In the Packing slip date field, enter a date.</span></span>
7. <span data-ttu-id="2ac6d-156">Wybierz numer wysyłki.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-156">Select the Shipment number.</span></span>
8. <span data-ttu-id="2ac6d-157">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2ac6d-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-158">Click OK.</span></span>
10. <span data-ttu-id="2ac6d-159">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-159">Click OK.</span></span>

## <a name="post-sales-invoice"></a><span data-ttu-id="2ac6d-160">Księgowanie faktury sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2ac6d-160">Post sales invoice</span></span>
1. <span data-ttu-id="2ac6d-161">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-161">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="2ac6d-162">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-162">Click Invoice.</span></span>
3. <span data-ttu-id="2ac6d-163">Rozwiń lub zwiń sekcję Przegląd.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-163">Expand or collapse the Overview section.</span></span>
4. <span data-ttu-id="2ac6d-164">Wybierz numer wysyłki.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-164">Select the Shipment number.</span></span>
5. <span data-ttu-id="2ac6d-165">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-165">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2ac6d-166">Rozwiń lub zwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-166">Expand or collapse the Setup section.</span></span>
7. <span data-ttu-id="2ac6d-167">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-167">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="2ac6d-168">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-168">Click OK.</span></span>
9. <span data-ttu-id="2ac6d-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-169">Click OK.</span></span>

## <a name="shipment-document-submitted-status"></a><span data-ttu-id="2ac6d-170">Stan przesłania dokumentu wysyłki</span><span class="sxs-lookup"><span data-stu-id="2ac6d-170">Shipment document submitted status</span></span>
1. <span data-ttu-id="2ac6d-171">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-171">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="2ac6d-172">Kliknij opcję Akredytywa.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-172">Click Letter of credit.</span></span>
3. <span data-ttu-id="2ac6d-173">Rozwiń lub zwiń sekcję Wiersze.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-173">Expand or collapse the Lines section.</span></span>
    * <span data-ttu-id="2ac6d-174">Uwaga: Pole „Dokument przesłany” powinno być ustawione na wartość „Tak”.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-174">Note: The 'Document submitted' field should be set to 'Yes'.</span></span>  

## <a name="verify-export-letter-of-credit"></a><span data-ttu-id="2ac6d-175">Weryfikacja akredytywy eksportowej</span><span class="sxs-lookup"><span data-stu-id="2ac6d-175">Verify Export letter of credit</span></span>
1. <span data-ttu-id="2ac6d-176">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa eksportowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-176">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="2ac6d-177">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-177">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2ac6d-178">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2ac6d-179">Sprawdź, czy akredytywa eksportowa ma w polu Stan wysyłki wartość „Zafakturowane”.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-179">Verify that the Export letter of credit has a Shipment status of 'Invoiced'.</span></span>  

## <a name="customer-payment"></a><span data-ttu-id="2ac6d-180">Płatność od odbiorcy</span><span class="sxs-lookup"><span data-stu-id="2ac6d-180">Customer payment</span></span>
1. <span data-ttu-id="2ac6d-181">Wybierz kolejno opcje Rozrachunki z odbiorcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-181">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="2ac6d-182">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-182">Click New.</span></span>
3. <span data-ttu-id="2ac6d-183">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-183">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="2ac6d-184">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-184">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2ac6d-185">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-185">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2ac6d-186">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-186">Click Lines.</span></span>
7. <span data-ttu-id="2ac6d-187">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-187">In the Date field, enter a date.</span></span>
8. <span data-ttu-id="2ac6d-188">W polu Konto podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-188">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="2ac6d-189">Kliknij opcję Rozliczenie.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-189">Click Settlement.</span></span>
10. <span data-ttu-id="2ac6d-190">Zaznacz pole wyboru w nagłówku formantu Sumy.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-190">Select the check box on the header of Totals.</span></span>
    * <span data-ttu-id="2ac6d-191">Uwaga: W polu Pokaż ustaw wartość „Akredytywa”.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-191">Note: Set the Show field to 'Letter of credit'.</span></span>  
11. <span data-ttu-id="2ac6d-192">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-192">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="2ac6d-193">Zaznacz lub wyczyść pole wyboru Zaznacz.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-193">Select or clear the Mark check box.</span></span>
13. <span data-ttu-id="2ac6d-194">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-194">Click OK.</span></span>
14. <span data-ttu-id="2ac6d-195">Kliknij kartę Płatność.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-195">Click the Payment tab.</span></span>
    * <span data-ttu-id="2ac6d-196">Sprawdź informacje w polach Numer dokumentu banku i Numer wysyłki.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-196">Verify Bank document number and Shipment number details</span></span>  
15. <span data-ttu-id="2ac6d-197">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-197">Click Post.</span></span>

## <a name="verify-export-letter-of-credit-after-payment"></a><span data-ttu-id="2ac6d-198">Sprawdzanie poprawności akredytywy eksportowej po zapłacie</span><span class="sxs-lookup"><span data-stu-id="2ac6d-198">Verify Export letter of credit after payment</span></span>
1. <span data-ttu-id="2ac6d-199">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa eksportowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-199">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="2ac6d-200">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-200">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2ac6d-201">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-201">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2ac6d-202">Sprawdź, czy Stan wysyłki = Płatność otrzymana, a kwota salda = 0,00.</span><span class="sxs-lookup"><span data-stu-id="2ac6d-202">Verify Shipment status = Payment received and balance amount = 0.00.</span></span>  

