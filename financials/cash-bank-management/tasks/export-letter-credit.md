--- 
title: Eksportowanie akredytywy
description: Ta procedura poprowadzi przez proces tworzenia akredytywy eksportowej.
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
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
ms.openlocfilehash: 07fef304361fa0008f57425ff27596e4e382072a
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="export-a-letter-of-credit"></a><span data-ttu-id="10f7b-103">Eksportowanie akredytywy</span><span class="sxs-lookup"><span data-stu-id="10f7b-103">Export a letter of credit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10f7b-104">Ta procedura poprowadzi przez proces tworzenia akredytywy eksportowej.</span><span class="sxs-lookup"><span data-stu-id="10f7b-104">This procedure walks through the process of the Export letter of credit.</span></span>

<span data-ttu-id="10f7b-105">Akredytywa jest umową wystawianą przez bank, w której bank wyraża zgodę na zapłatę w imieniu nabywcy, jeśli zostaną spełnione warunki umowy między nabywcą a sprzedawcą.</span><span class="sxs-lookup"><span data-stu-id="10f7b-105">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to ensure payment on behalf of the buyer, if the terms of the agreement between the buyer and seller are met.</span></span>



<span data-ttu-id="10f7b-106">Przed uruchomieniem tej procedury wykonaj procedury „Konfigurowanie instrumentów bankowych i profilów księgowania” oraz „Akredytywa_Tworzenie umowy instrumentu bankowego”.</span><span class="sxs-lookup"><span data-stu-id="10f7b-106">Run the 'Set up bank facilities and posting profiles' procedure and the 'Letter of Credit_Create a bank facility agreement' procedure prior to this procedure.</span></span> <span data-ttu-id="10f7b-107">Aby pomyślnie wykonać tę procedurę, należy zaznaczyć firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="10f7b-107">The USMF demo company must be selected in order to run this procedure successfully.</span></span>




## <a name="create-sales-order-for-export-letter-of-credit"></a><span data-ttu-id="10f7b-108">Tworzenie zamówienia sprzedaży dla akredytywy</span><span class="sxs-lookup"><span data-stu-id="10f7b-108">Create Sales Order for Export letter of credit</span></span>
1. <span data-ttu-id="10f7b-109">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="10f7b-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="10f7b-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="10f7b-110">Click New.</span></span>
3. <span data-ttu-id="10f7b-111">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="10f7b-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="10f7b-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="10f7b-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="10f7b-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="10f7b-114">Rozwiń lub zwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="10f7b-114">Expand or collapse the General section.</span></span>
7. <span data-ttu-id="10f7b-115">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="10f7b-115">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="10f7b-116">Zaznacz oddział, w którym jest składowany towar przeznaczony do wydania.</span><span class="sxs-lookup"><span data-stu-id="10f7b-116">Select the Site where the item to be issued is stocked.</span></span>  
8. <span data-ttu-id="10f7b-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="10f7b-118">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="10f7b-118">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="10f7b-119">Zaznacz magazyn, w którym jest składowany towar przeznaczony do wydania.</span><span class="sxs-lookup"><span data-stu-id="10f7b-119">Select the Warehouse where item to be issued is stocked.</span></span>  
10. <span data-ttu-id="10f7b-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="10f7b-121">Uwaga: Wybierz pole Typ dokumentu bankowego z wartością „Akredytywa”.</span><span class="sxs-lookup"><span data-stu-id="10f7b-121">Note: The Bank document type field should be selected with the value 'Letter of credit'.</span></span>  
11. <span data-ttu-id="10f7b-122">W polu Typ dokumentu bankowego wybierz opcję „Akredytywa”.</span><span class="sxs-lookup"><span data-stu-id="10f7b-122">In the Bank document type field, select 'Letter of credit'.</span></span>
12. <span data-ttu-id="10f7b-123">Rozwiń lub zwiń sekcję Dostawa.</span><span class="sxs-lookup"><span data-stu-id="10f7b-123">Expand or collapse the Delivery section.</span></span>
    * <span data-ttu-id="10f7b-124">W polu Kontrola daty dostawy wybierz wartość Brak.</span><span class="sxs-lookup"><span data-stu-id="10f7b-124">Select Delivery date control = None.</span></span>  
13. <span data-ttu-id="10f7b-125">W polu Żądana data odbioru wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="10f7b-125">In the Requested receipt date field, enter a date.</span></span>
14. <span data-ttu-id="10f7b-126">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="10f7b-126">Click OK.</span></span>
15. <span data-ttu-id="10f7b-127">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="10f7b-127">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="10f7b-128">Zaznacz towar, który ma zostać wydany/sprzedany.</span><span class="sxs-lookup"><span data-stu-id="10f7b-128">Select the required item to be Issued/Sold.</span></span>  
16. <span data-ttu-id="10f7b-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="10f7b-129">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="10f7b-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="10f7b-131">W polu Cena jednostkowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="10f7b-131">In the Unit price field, enter a number.</span></span>
19. <span data-ttu-id="10f7b-132">Rozwiń lub zwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="10f7b-132">Expand or collapse the Line details section.</span></span>
20. <span data-ttu-id="10f7b-133">Kliknij kartę Dostawa.</span><span class="sxs-lookup"><span data-stu-id="10f7b-133">Click the Delivery tab.</span></span>
21. <span data-ttu-id="10f7b-134">W polu Żądana data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="10f7b-134">In the Requested ship date field, enter a date.</span></span>
22. <span data-ttu-id="10f7b-135">W polu Potwierdzona data wysyłki wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="10f7b-135">In the Confirmed ship date field, enter a date.</span></span>
23. <span data-ttu-id="10f7b-136">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="10f7b-136">On the Action Pane, click Manage.</span></span>
24. <span data-ttu-id="10f7b-137">Kliknij opcję Akredytywa.</span><span class="sxs-lookup"><span data-stu-id="10f7b-137">Click Letter of credit.</span></span>
25. <span data-ttu-id="10f7b-138">W polu Numer dokumentu banku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="10f7b-138">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="10f7b-139">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="10f7b-139">In the Expiration date field, enter a date and time.</span></span>
27. <span data-ttu-id="10f7b-140">Rozwiń lub zwiń sekcję Szczegóły banku.</span><span class="sxs-lookup"><span data-stu-id="10f7b-140">Expand or collapse the Bank details section.</span></span>
28. <span data-ttu-id="10f7b-141">W polu Bank wystawiający kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="10f7b-141">In the Issuing bank field, click the drop-down button to open the lookup.</span></span>
29. <span data-ttu-id="10f7b-142">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-142">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="10f7b-143">W polu Bank doradczy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="10f7b-143">In the Advising bank field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="10f7b-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="10f7b-144">In the list, find and select the desired record.</span></span>
32. <span data-ttu-id="10f7b-145">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-145">In the list, click the link in the selected row.</span></span>
33. <span data-ttu-id="10f7b-146">Kliknij opcję Pobierz wysyłki zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="10f7b-146">Click Fetch sales order shipments.</span></span>
34. <span data-ttu-id="10f7b-147">Kliknij opcję Wystaw dokument bankowy.</span><span class="sxs-lookup"><span data-stu-id="10f7b-147">Click Issue bank document.</span></span>
35. <span data-ttu-id="10f7b-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="10f7b-148">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="10f7b-149">Księgowanie dokumentu dostawy</span><span class="sxs-lookup"><span data-stu-id="10f7b-149">Post Packing slip</span></span>
1. <span data-ttu-id="10f7b-150">W okienku akcji kliknij opcję Pobierz i zapakuj.</span><span class="sxs-lookup"><span data-stu-id="10f7b-150">On the Action Pane, click Pick and pack.</span></span>
2. <span data-ttu-id="10f7b-151">Kliknij opcję Księguj dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="10f7b-151">Click Post packing slip.</span></span>
3. <span data-ttu-id="10f7b-152">Rozwiń lub zwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="10f7b-152">Expand or collapse the Parameters section.</span></span>
4. <span data-ttu-id="10f7b-153">W polu Ilość zaznacz opcję „Wszystko”.</span><span class="sxs-lookup"><span data-stu-id="10f7b-153">In the Quantity field, select 'All'.</span></span>
5. <span data-ttu-id="10f7b-154">Rozwiń lub zwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="10f7b-154">Expand or collapse the Setup section.</span></span>
6. <span data-ttu-id="10f7b-155">W polu Data dokumentu dostawy wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="10f7b-155">In the Packing slip date field, enter a date.</span></span>
7. <span data-ttu-id="10f7b-156">Wybierz numer wysyłki.</span><span class="sxs-lookup"><span data-stu-id="10f7b-156">Select the Shipment number.</span></span>
8. <span data-ttu-id="10f7b-157">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="10f7b-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="10f7b-158">Click OK.</span></span>
10. <span data-ttu-id="10f7b-159">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="10f7b-159">Click OK.</span></span>

## <a name="post-sales-invoice"></a><span data-ttu-id="10f7b-160">Księgowanie faktury sprzedaży</span><span class="sxs-lookup"><span data-stu-id="10f7b-160">Post sales invoice</span></span>
1. <span data-ttu-id="10f7b-161">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="10f7b-161">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="10f7b-162">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="10f7b-162">Click Invoice.</span></span>
3. <span data-ttu-id="10f7b-163">Rozwiń lub zwiń sekcję Przegląd.</span><span class="sxs-lookup"><span data-stu-id="10f7b-163">Expand or collapse the Overview section.</span></span>
4. <span data-ttu-id="10f7b-164">Wybierz numer wysyłki.</span><span class="sxs-lookup"><span data-stu-id="10f7b-164">Select the Shipment number.</span></span>
5. <span data-ttu-id="10f7b-165">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-165">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="10f7b-166">Rozwiń lub zwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="10f7b-166">Expand or collapse the Setup section.</span></span>
7. <span data-ttu-id="10f7b-167">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="10f7b-167">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="10f7b-168">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="10f7b-168">Click OK.</span></span>
9. <span data-ttu-id="10f7b-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="10f7b-169">Click OK.</span></span>

## <a name="shipment-document-submitted-status"></a><span data-ttu-id="10f7b-170">Stan przesłania dokumentu wysyłki</span><span class="sxs-lookup"><span data-stu-id="10f7b-170">Shipment document submitted status</span></span>
1. <span data-ttu-id="10f7b-171">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="10f7b-171">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="10f7b-172">Kliknij opcję Akredytywa.</span><span class="sxs-lookup"><span data-stu-id="10f7b-172">Click Letter of credit.</span></span>
3. <span data-ttu-id="10f7b-173">Rozwiń lub zwiń sekcję Wiersze.</span><span class="sxs-lookup"><span data-stu-id="10f7b-173">Expand or collapse the Lines section.</span></span>
    * <span data-ttu-id="10f7b-174">Uwaga: Pole „Dokument przesłany” powinno być ustawione na wartość „Tak”.</span><span class="sxs-lookup"><span data-stu-id="10f7b-174">Note: The 'Document submitted' field should be set to 'Yes'.</span></span>  

## <a name="verify-export-letter-of-credit"></a><span data-ttu-id="10f7b-175">Weryfikacja akredytywy eksportowej</span><span class="sxs-lookup"><span data-stu-id="10f7b-175">Verify Export letter of credit</span></span>
1. <span data-ttu-id="10f7b-176">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa eksportowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="10f7b-176">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="10f7b-177">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="10f7b-177">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="10f7b-178">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="10f7b-179">Sprawdź, czy akredytywa eksportowa ma w polu Stan wysyłki wartość „Zafakturowane”.</span><span class="sxs-lookup"><span data-stu-id="10f7b-179">Verify that the Export letter of credit has a Shipment status of 'Invoiced'.</span></span>  

## <a name="customer-payment"></a><span data-ttu-id="10f7b-180">Płatność od odbiorcy</span><span class="sxs-lookup"><span data-stu-id="10f7b-180">Customer payment</span></span>
1. <span data-ttu-id="10f7b-181">Wybierz kolejno opcje Rozrachunki z odbiorcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="10f7b-181">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="10f7b-182">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="10f7b-182">Click New.</span></span>
3. <span data-ttu-id="10f7b-183">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="10f7b-183">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="10f7b-184">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="10f7b-184">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="10f7b-185">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-185">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="10f7b-186">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="10f7b-186">Click Lines.</span></span>
7. <span data-ttu-id="10f7b-187">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="10f7b-187">In the Date field, enter a date.</span></span>
8. <span data-ttu-id="10f7b-188">W polu Konto podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="10f7b-188">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="10f7b-189">Kliknij opcję Rozliczenie.</span><span class="sxs-lookup"><span data-stu-id="10f7b-189">Click Settlement.</span></span>
10. <span data-ttu-id="10f7b-190">Zaznacz pole wyboru w nagłówku formantu Sumy.</span><span class="sxs-lookup"><span data-stu-id="10f7b-190">Select the check box on the header of Totals.</span></span>
    * <span data-ttu-id="10f7b-191">Uwaga: W polu Pokaż ustaw wartość „Akredytywa”.</span><span class="sxs-lookup"><span data-stu-id="10f7b-191">Note: Set the Show field to 'Letter of credit'.</span></span>  
11. <span data-ttu-id="10f7b-192">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="10f7b-192">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="10f7b-193">Zaznacz lub wyczyść pole wyboru Zaznacz.</span><span class="sxs-lookup"><span data-stu-id="10f7b-193">Select or clear the Mark check box.</span></span>
13. <span data-ttu-id="10f7b-194">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="10f7b-194">Click OK.</span></span>
14. <span data-ttu-id="10f7b-195">Kliknij kartę Płatność.</span><span class="sxs-lookup"><span data-stu-id="10f7b-195">Click the Payment tab.</span></span>
    * <span data-ttu-id="10f7b-196">Sprawdź informacje w polach Numer dokumentu banku i Numer wysyłki.</span><span class="sxs-lookup"><span data-stu-id="10f7b-196">Verify Bank document number and Shipment number details</span></span>  
15. <span data-ttu-id="10f7b-197">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="10f7b-197">Click Post.</span></span>

## <a name="verify-export-letter-of-credit-after-payment"></a><span data-ttu-id="10f7b-198">Sprawdzanie poprawności akredytywy eksportowej po zapłacie</span><span class="sxs-lookup"><span data-stu-id="10f7b-198">Verify Export letter of credit after payment</span></span>
1. <span data-ttu-id="10f7b-199">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa eksportowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="10f7b-199">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="10f7b-200">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="10f7b-200">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="10f7b-201">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="10f7b-201">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="10f7b-202">Sprawdź, czy Stan wysyłki = Płatność otrzymana, a kwota salda = 0,00.</span><span class="sxs-lookup"><span data-stu-id="10f7b-202">Verify Shipment status = Payment received and balance amount = 0.00.</span></span>  


