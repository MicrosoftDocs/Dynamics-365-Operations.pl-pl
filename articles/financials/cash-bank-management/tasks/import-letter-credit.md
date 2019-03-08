---
title: Akredytywa importowa
description: Ta procedura poprowadzi przez proces tworzenia akredytywy importowej.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1768494182a79d7a33044498c1e768e61d937d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "313573"
---
# <a name="import-letter-of-credit"></a><span data-ttu-id="60f92-103">Akredytywa importowa</span><span class="sxs-lookup"><span data-stu-id="60f92-103">Import letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="60f92-104">Ta procedura poprowadzi przez proces tworzenia akredytywy importowej.</span><span class="sxs-lookup"><span data-stu-id="60f92-104">This procedure walks through the process of importing a letter of credit.</span></span> <span data-ttu-id="60f92-105">Następujące ustawienia należy skonfigurować przed wykonaniem tej procedury: instrument bankowy, profile księgowania, umowa instrumentu bankowego oraz dane bankowe dostawcy.</span><span class="sxs-lookup"><span data-stu-id="60f92-105">The following must be set up before completing this procedure: bank facilities, posting profiles, a bank facility agreement and vendor bank details.</span></span>

<span data-ttu-id="60f92-106">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="60f92-106">This procedure uses the USMF demo company.</span></span>


## <a name="create-a-purchase-order-with-letter-of-credit"></a><span data-ttu-id="60f92-107">Tworzenie zamówienia zakupu z akredytywą</span><span class="sxs-lookup"><span data-stu-id="60f92-107">Create a Purchase order with Letter of credit</span></span>
1. <span data-ttu-id="60f92-108">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="60f92-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="60f92-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="60f92-109">Click New.</span></span>
3. <span data-ttu-id="60f92-110">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="60f92-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="60f92-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="60f92-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="60f92-113">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="60f92-113">Expand the General section.</span></span>
7. <span data-ttu-id="60f92-114">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-114">In the Site field, enter or select a value.</span></span>
8. <span data-ttu-id="60f92-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="60f92-116">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-116">In the Warehouse field, enter or select a value.</span></span>
10. <span data-ttu-id="60f92-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="60f92-118">W polu Data księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="60f92-118">In the Accounting date field, enter a date.</span></span>
12. <span data-ttu-id="60f92-119">W polu Data dostawy wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="60f92-119">In the Delivery date field, enter a date.</span></span>
    * <span data-ttu-id="60f92-120">Uwaga: Wybierz pole „Typ dokumentu bankowego” z wartością „Akredytywa”.</span><span class="sxs-lookup"><span data-stu-id="60f92-120">Note: The 'Bank document type' field should be selected with the value  'Letter of credit'.</span></span>  
13. <span data-ttu-id="60f92-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="60f92-121">Click OK.</span></span>
14. <span data-ttu-id="60f92-122">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-122">In the Item number field, enter or select a value.</span></span>
15. <span data-ttu-id="60f92-123">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="60f92-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="60f92-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="60f92-125">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="60f92-125">Expand the Line details section.</span></span>
18. <span data-ttu-id="60f92-126">Kliknij kartę Dostawa.</span><span class="sxs-lookup"><span data-stu-id="60f92-126">Click the Delivery tab.</span></span>
19. <span data-ttu-id="60f92-127">W polu Data dostawy wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="60f92-127">In the Delivery date field, enter a date.</span></span>
20. <span data-ttu-id="60f92-128">W polu Potwierdzona data dostawy wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="60f92-128">In the Confirmed delivery date field, enter a date.</span></span>
21. <span data-ttu-id="60f92-129">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="60f92-129">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="60f92-130">Wprowadź szczegóły akredytywy.</span><span class="sxs-lookup"><span data-stu-id="60f92-130">Define the Letter of credit details.</span></span>  
22. <span data-ttu-id="60f92-131">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="60f92-131">On the Action Pane, click Manage.</span></span>
23. <span data-ttu-id="60f92-132">Kliknij opcję Akredytywa/inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="60f92-132">Click Letter of credit / import collection.</span></span>
24. <span data-ttu-id="60f92-133">W polu Data zgłoszenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="60f92-133">In the Application date field, enter a date and time.</span></span>
    * <span data-ttu-id="60f92-134">Sprawdź, czy pole „Konto bankowe” zawiera domyślne aktywne konto bankowego, co zależy od daty zgłoszenia.</span><span class="sxs-lookup"><span data-stu-id="60f92-134">Verify that the 'Bank account' field has the default active Bank account, which is based on the application date.</span></span>  
25. <span data-ttu-id="60f92-135">W polu Numer dokumentu banku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-135">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="60f92-136">W polu Data otrzymania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="60f92-136">In the Date of receipt field, enter a date and time.</span></span>
27. <span data-ttu-id="60f92-137">Rozwiń sekcję Dokument bankowy.</span><span class="sxs-lookup"><span data-stu-id="60f92-137">Expand the Bank document section.</span></span>
28. <span data-ttu-id="60f92-138">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="60f92-138">In the Expiration date field, enter a date and time.</span></span>
29. <span data-ttu-id="60f92-139">Rozwiń sekcję Szczegóły banku.</span><span class="sxs-lookup"><span data-stu-id="60f92-139">Expand the Bank details section.</span></span>
30. <span data-ttu-id="60f92-140">W polu Bank doradczy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-140">In the Advising bank field, enter or select a value.</span></span>
31. <span data-ttu-id="60f92-141">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="60f92-142">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="60f92-142">Click Save.</span></span>
33. <span data-ttu-id="60f92-143">Kliknij opcję Pobierz wysyłki zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="60f92-143">Click Fetch purchase order shipments.</span></span>
34. <span data-ttu-id="60f92-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-144">Close the page.</span></span>
35. <span data-ttu-id="60f92-145">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="60f92-145">On the Action Pane, click Purchase.</span></span>
36. <span data-ttu-id="60f92-146">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="60f92-146">Click Confirm.</span></span>
37. <span data-ttu-id="60f92-147">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="60f92-147">On the Action Pane, click Manage.</span></span>
38. <span data-ttu-id="60f92-148">Kliknij opcję Akredytywa/inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="60f92-148">Click Letter of credit / import collection.</span></span>
39. <span data-ttu-id="60f92-149">Kliknij przycisk Przetwarzaj.</span><span class="sxs-lookup"><span data-stu-id="60f92-149">Click Process.</span></span>
40. <span data-ttu-id="60f92-150">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="60f92-150">Click Confirm.</span></span>
    * <span data-ttu-id="60f92-151">Sprawdź, czy saldo instrumentu zmniejsza kwotę zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="60f92-151">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="60f92-152">W tym przykładzie kwota zakupu = 500,00, limit instrumentu = 10000,00, dlatego saldo instrumentu = 9500,00.</span><span class="sxs-lookup"><span data-stu-id="60f92-152">In this example, Purchase amount = 500.00,  Facility limit = 10000.00,  therefore, Facility balance = 9500.00.</span></span>  
41. <span data-ttu-id="60f92-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-153">Close the page.</span></span>
42. <span data-ttu-id="60f92-154">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="60f92-154">In the Unit price field, enter a number.</span></span>
43. <span data-ttu-id="60f92-155">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="60f92-155">Click Save.</span></span>
44. <span data-ttu-id="60f92-156">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="60f92-156">On the Action Pane, click Purchase.</span></span>
45. <span data-ttu-id="60f92-157">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="60f92-157">Click Confirm.</span></span>
    * <span data-ttu-id="60f92-158">Skoryguj akredytywę ze względu na zmianę ceny jednostkowej.</span><span class="sxs-lookup"><span data-stu-id="60f92-158">Amend the Letter of credit, due to the change in Unit price.</span></span>  
46. <span data-ttu-id="60f92-159">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="60f92-159">On the Action Pane, click Manage.</span></span>
47. <span data-ttu-id="60f92-160">Kliknij opcję Akredytywa/inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="60f92-160">Click Letter of credit / import collection.</span></span>
    * <span data-ttu-id="60f92-161">Skoryguj akredytywę ze względu na zmianę ceny jednostkowej zakupu.</span><span class="sxs-lookup"><span data-stu-id="60f92-161">Amend the letter of credit, due to the change in Purchase unit price.</span></span>  
48. <span data-ttu-id="60f92-162">Kliknij przycisk Przetwarzaj.</span><span class="sxs-lookup"><span data-stu-id="60f92-162">Click Process.</span></span>
49. <span data-ttu-id="60f92-163">Kliknij przycisk Zmiana.</span><span class="sxs-lookup"><span data-stu-id="60f92-163">Click Amend.</span></span>
50. <span data-ttu-id="60f92-164">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="60f92-164">Click Remove.</span></span>
51. <span data-ttu-id="60f92-165">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="60f92-165">Click Yes.</span></span>
52. <span data-ttu-id="60f92-166">Kliknij opcję Pobierz wysyłki zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="60f92-166">Click Fetch purchase order shipments.</span></span>
53. <span data-ttu-id="60f92-167">Kliknij przycisk Przetwarzaj.</span><span class="sxs-lookup"><span data-stu-id="60f92-167">Click Process.</span></span>
54. <span data-ttu-id="60f92-168">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="60f92-168">Click Confirm.</span></span>
    * <span data-ttu-id="60f92-169">Sprawdź, czy saldo instrumentu zmniejsza kwotę zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="60f92-169">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="60f92-170">W tym przykładzie zmodyfikowana kwota zakupu = 600,00, limit instrumentu = 10000,00, dlatego saldo instrumentu = 9400,00.</span><span class="sxs-lookup"><span data-stu-id="60f92-170">In this example, edited Purchase amount = 600.00,  Facility limit = 10000.00,  therefore, Facility balance = 9400.00.</span></span>  
55. <span data-ttu-id="60f92-171">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-171">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="60f92-172">Księgowanie dokumentu dostawy</span><span class="sxs-lookup"><span data-stu-id="60f92-172">Post Packing slip</span></span>
1. <span data-ttu-id="60f92-173">W okienku akcji kliknij pozycję Odbierz.</span><span class="sxs-lookup"><span data-stu-id="60f92-173">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="60f92-174">Kliknij opcję Dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="60f92-174">Click Product receipt.</span></span>
3. <span data-ttu-id="60f92-175">W polu PurchParmTable_Num wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-175">In the PurchParmTable_Num field, type a value.</span></span>
    * <span data-ttu-id="60f92-176">Wybierz numer wysyłki utworzonej z odniesieniem do akredytywy.</span><span class="sxs-lookup"><span data-stu-id="60f92-176">Select the Shipment number created with reference to the Letter of credit.</span></span>  
4. <span data-ttu-id="60f92-177">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-177">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="60f92-178">W polu Data dokumentu przyjęcia produktów wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="60f92-178">In the Product receipt date field, enter a date.</span></span>
6. <span data-ttu-id="60f92-179">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="60f92-179">Click OK.</span></span>
7. <span data-ttu-id="60f92-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-180">Close the page.</span></span>
8. <span data-ttu-id="60f92-181">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-181">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="60f92-182">Weryfikacja stanu akredytywy importowej</span><span class="sxs-lookup"><span data-stu-id="60f92-182">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="60f92-183">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa importowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="60f92-183">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="60f92-184">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="60f92-184">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="60f92-185">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-185">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="60f92-186">Zweryfikuj stan akredytywy importowej.</span><span class="sxs-lookup"><span data-stu-id="60f92-186">Verify the Import letter of credit status.</span></span>    
    *   
4. <span data-ttu-id="60f92-187">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-187">Close the page.</span></span>
5. <span data-ttu-id="60f92-188">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-188">Close the page.</span></span>

## <a name="post-purchase-invoice"></a><span data-ttu-id="60f92-189">Księgowanie faktury zakupu</span><span class="sxs-lookup"><span data-stu-id="60f92-189">Post purchase invoice</span></span>
1. <span data-ttu-id="60f92-190">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="60f92-190">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
    * <span data-ttu-id="60f92-191">Wybierz zamówienie zakupu, które zostało utworzone z akredytywą.</span><span class="sxs-lookup"><span data-stu-id="60f92-191">Select the purchase order that was created with letter of credit.</span></span>  
2. <span data-ttu-id="60f92-192">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="60f92-192">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="60f92-193">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-193">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="60f92-194">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="60f92-194">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="60f92-195">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="60f92-195">Click Invoice.</span></span>
6. <span data-ttu-id="60f92-196">W polu Numer wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-196">In the Number field, type a value.</span></span>
7. <span data-ttu-id="60f92-197">W polu Numer wysyłki wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-197">In the Shipment number field, enter or select a value.</span></span>
8. <span data-ttu-id="60f92-198">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-198">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="60f92-199">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="60f92-199">In the Invoice date field, enter a date.</span></span>
10. <span data-ttu-id="60f92-200">Kliknij przycisk Aktualizuj stan uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="60f92-200">Click Update match status.</span></span>
11. <span data-ttu-id="60f92-201">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="60f92-201">Click Post.</span></span>
12. <span data-ttu-id="60f92-202">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-202">Close the page.</span></span>
13. <span data-ttu-id="60f92-203">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-203">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="60f92-204">Weryfikacja stanu akredytywy importowej</span><span class="sxs-lookup"><span data-stu-id="60f92-204">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="60f92-205">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa importowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="60f92-205">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="60f92-206">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="60f92-206">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="60f92-207">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-207">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="60f92-208">Zweryfikuj akredytywę importową2.</span><span class="sxs-lookup"><span data-stu-id="60f92-208">Verify the Import letter of credit2.</span></span>  
    * <span data-ttu-id="60f92-209">Sprawdzanie poprawności: Stan wysyłki = Zafakturowana  Szczegóły instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="60f92-209">Validate :  Shipment status = Invoiced  Bank facility details</span></span>  
4. <span data-ttu-id="60f92-210">Kliknij przycisk Wyświetl.</span><span class="sxs-lookup"><span data-stu-id="60f92-210">Click View.</span></span>
5. <span data-ttu-id="60f92-211">Kliknij opcję Drukuj zgłoszenie.</span><span class="sxs-lookup"><span data-stu-id="60f92-211">Click Print application.</span></span>
6. <span data-ttu-id="60f92-212">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="60f92-212">Click OK.</span></span>
    * <span data-ttu-id="60f92-213">Sprawdź, czy zgłoszenie akredytywy jest drukowane.</span><span class="sxs-lookup"><span data-stu-id="60f92-213">Verify that the Letter of credit application gets printed.</span></span>  
7. <span data-ttu-id="60f92-214">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-214">Close the page.</span></span>
8. <span data-ttu-id="60f92-215">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-215">Close the page.</span></span>
9. <span data-ttu-id="60f92-216">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-216">Close the page.</span></span>

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a><span data-ttu-id="60f92-217">Księgowanie arkusza płatności dostawcy dla utworzonej faktury zakupu z akredytywą</span><span class="sxs-lookup"><span data-stu-id="60f92-217">Post Vendor payment journal for the created purchase invoice with letter of credit</span></span>
1. <span data-ttu-id="60f92-218">Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="60f92-218">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="60f92-219">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="60f92-219">Click New.</span></span>
3. <span data-ttu-id="60f92-220">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-220">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="60f92-221">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-221">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="60f92-222">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="60f92-222">Click Lines.</span></span>
6. <span data-ttu-id="60f92-223">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="60f92-223">In the Date field, enter a date.</span></span>
7. <span data-ttu-id="60f92-224">W polu Konto podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="60f92-224">In the Account field, specify the desired values.</span></span>
8. <span data-ttu-id="60f92-225">Kliknij opcję Rozlicz transakcje.</span><span class="sxs-lookup"><span data-stu-id="60f92-225">Click Settle transactions.</span></span>
9. <span data-ttu-id="60f92-226">Rozwiń sekcję Sumy.</span><span class="sxs-lookup"><span data-stu-id="60f92-226">Expand the Totals section.</span></span>
10. <span data-ttu-id="60f92-227">W polu Pokaż wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="60f92-227">In the Show field, select an option.</span></span>
    * <span data-ttu-id="60f92-228">Sprawdź, czy pola Numer dokumentu banku i Numer wysyłki zostały zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="60f92-228">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
11. <span data-ttu-id="60f92-229">Zaznacz pole wyboru Zaznacz.</span><span class="sxs-lookup"><span data-stu-id="60f92-229">Select the Mark check box.</span></span>
12. <span data-ttu-id="60f92-230">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="60f92-230">Click OK.</span></span>
13. <span data-ttu-id="60f92-231">Kliknij kartę Płatność.</span><span class="sxs-lookup"><span data-stu-id="60f92-231">Click the Payment tab.</span></span>
    * <span data-ttu-id="60f92-232">Sprawdź, czy pola Numer dokumentu banku i Numer wysyłki zostały zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="60f92-232">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
14. <span data-ttu-id="60f92-233">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="60f92-233">Click Post.</span></span>
15. <span data-ttu-id="60f92-234">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-234">Close the page.</span></span>
16. <span data-ttu-id="60f92-235">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-235">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a><span data-ttu-id="60f92-236">Weryfikacja stanu akredytywy importowej po zapłacie faktury</span><span class="sxs-lookup"><span data-stu-id="60f92-236">Verify Import letter of credit status after Invoice paid</span></span>
1. <span data-ttu-id="60f92-237">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa importowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="60f92-237">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="60f92-238">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="60f92-238">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="60f92-239">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-239">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="60f92-240">Zweryfikuj stan akredytywy importowej.</span><span class="sxs-lookup"><span data-stu-id="60f92-240">Verify the Import letter of credit status.</span></span>   
4. <span data-ttu-id="60f92-241">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-241">Close the page.</span></span>

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a><span data-ttu-id="60f92-242">Weryfikacja raportu o limicie i wykorzystaniu instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="60f92-242">Verify the Bank facility limit and utilization report</span></span>
1. <span data-ttu-id="60f92-243">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Zapytania i raporty > Akredytywy lub poręczenia > Raport produktów bankowych i wykorzystania.</span><span class="sxs-lookup"><span data-stu-id="60f92-243">Go to Cash and bank management > Inquiries and reports > Letters of credit or guarantee > Bank facilities and utilization report.</span></span>
2. <span data-ttu-id="60f92-244">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="60f92-244">Expand the Records to include section.</span></span>
3. <span data-ttu-id="60f92-245">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="60f92-245">Click Filter.</span></span>
    * <span data-ttu-id="60f92-246">W polu Kryteria wpisz wymagane konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="60f92-246">Define the Criteria field with the required bank account.</span></span>  
4. <span data-ttu-id="60f92-247">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="60f92-247">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="60f92-248">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="60f92-248">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="60f92-249">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="60f92-249">Click OK.</span></span>
7. <span data-ttu-id="60f92-250">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="60f92-250">Click OK.</span></span>
    * <span data-ttu-id="60f92-251">Sprawdź raport zawierający listę transakcji.</span><span class="sxs-lookup"><span data-stu-id="60f92-251">Verify the report which lists the transactions.</span></span>  
    * <span data-ttu-id="60f92-252">Sprawdź, czy w raporcie znajdują się transakcje z numerem dokumentu banku, limit instrumentu, wykorzystaną kwotą i kwotą salda instrumentu.</span><span class="sxs-lookup"><span data-stu-id="60f92-252">Verify the report lists the transactions with Bank document number, Facility limit, utilized amount and the facility balance amount.</span></span>  
8. <span data-ttu-id="60f92-253">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="60f92-253">Close the page.</span></span>

