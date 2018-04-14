--- 
title: Importowanie akredytywy
description: Ta procedura poprowadzi przez proces tworzenia akredytywy importowej.
author: kweekley
manager: AnnBe
ms.date: 02/26/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c4996f77cee1611c1bcb3ed015447747fd03fad1
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="import-a-letter-of-credit"></a><span data-ttu-id="f6f61-103">Importowanie akredytywy</span><span class="sxs-lookup"><span data-stu-id="f6f61-103">Import a letter of credit</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f6f61-104">Ta procedura poprowadzi przez proces tworzenia akredytywy importowej.</span><span class="sxs-lookup"><span data-stu-id="f6f61-104">This procedure walks through the process of importing a letter of credit.</span></span> <span data-ttu-id="f6f61-105">Następujące ustawienia należy skonfigurować przed wykonaniem tej procedury: instrument bankowy, profile księgowania, umowa instrumentu bankowego oraz dane bankowe dostawcy.</span><span class="sxs-lookup"><span data-stu-id="f6f61-105">The following must be set up before completing this procedure: bank facilities, posting profiles, a bank facility agreement and vendor bank details.</span></span>

<span data-ttu-id="f6f61-106">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="f6f61-106">This procedure uses the USMF demo company.</span></span>


## <a name="create-a-purchase-order-with-letter-of-credit"></a><span data-ttu-id="f6f61-107">Tworzenie zamówienia zakupu z akredytywą</span><span class="sxs-lookup"><span data-stu-id="f6f61-107">Create a Purchase order with Letter of credit</span></span>
1. <span data-ttu-id="f6f61-108">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="f6f61-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f6f61-109">Click New.</span></span>
3. <span data-ttu-id="f6f61-110">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="f6f61-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f6f61-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f6f61-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f6f61-113">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="f6f61-113">Expand the General section.</span></span>
7. <span data-ttu-id="f6f61-114">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-114">In the Site field, enter or select a value.</span></span>
8. <span data-ttu-id="f6f61-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="f6f61-116">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-116">In the Warehouse field, enter or select a value.</span></span>
10. <span data-ttu-id="f6f61-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="f6f61-118">W polu Data księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-118">In the Accounting date field, enter a date.</span></span>
12. <span data-ttu-id="f6f61-119">W polu Data dostawy wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-119">In the Delivery date field, enter a date.</span></span>
    * <span data-ttu-id="f6f61-120">Uwaga: Wybierz pole „Typ dokumentu bankowego” z wartością „Akredytywa”.</span><span class="sxs-lookup"><span data-stu-id="f6f61-120">Note: The 'Bank document type' field should be selected with the value  'Letter of credit'.</span></span>  
13. <span data-ttu-id="f6f61-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f6f61-121">Click OK.</span></span>
14. <span data-ttu-id="f6f61-122">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-122">In the Item number field, enter or select a value.</span></span>
15. <span data-ttu-id="f6f61-123">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f6f61-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="f6f61-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="f6f61-125">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="f6f61-125">Expand the Line details section.</span></span>
18. <span data-ttu-id="f6f61-126">Kliknij kartę Dostawa.</span><span class="sxs-lookup"><span data-stu-id="f6f61-126">Click the Delivery tab.</span></span>
19. <span data-ttu-id="f6f61-127">W polu Data dostawy wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-127">In the Delivery date field, enter a date.</span></span>
20. <span data-ttu-id="f6f61-128">W polu Potwierdzona data dostawy wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-128">In the Confirmed delivery date field, enter a date.</span></span>
21. <span data-ttu-id="f6f61-129">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="f6f61-129">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="f6f61-130">Wprowadź szczegóły akredytywy.</span><span class="sxs-lookup"><span data-stu-id="f6f61-130">Define the Letter of credit details.</span></span>  
22. <span data-ttu-id="f6f61-131">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="f6f61-131">On the Action Pane, click Manage.</span></span>
23. <span data-ttu-id="f6f61-132">Kliknij opcję Akredytywa/inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="f6f61-132">Click Letter of credit / import collection.</span></span>
24. <span data-ttu-id="f6f61-133">W polu Data zgłoszenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-133">In the Application date field, enter a date and time.</span></span>
    * <span data-ttu-id="f6f61-134">Sprawdź, czy pole „Konto bankowe” zawiera domyślne aktywne konto bankowego, co zależy od daty zgłoszenia.</span><span class="sxs-lookup"><span data-stu-id="f6f61-134">Verify that the 'Bank account' field has the default active Bank account, which is based on the application date.</span></span>  
25. <span data-ttu-id="f6f61-135">W polu Numer dokumentu banku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-135">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="f6f61-136">W polu Data otrzymania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-136">In the Date of receipt field, enter a date and time.</span></span>
27. <span data-ttu-id="f6f61-137">Rozwiń sekcję Dokument bankowy.</span><span class="sxs-lookup"><span data-stu-id="f6f61-137">Expand the Bank document section.</span></span>
28. <span data-ttu-id="f6f61-138">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-138">In the Expiration date field, enter a date and time.</span></span>
29. <span data-ttu-id="f6f61-139">Rozwiń sekcję Szczegóły banku.</span><span class="sxs-lookup"><span data-stu-id="f6f61-139">Expand the Bank details section.</span></span>
30. <span data-ttu-id="f6f61-140">W polu Bank doradczy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-140">In the Advising bank field, enter or select a value.</span></span>
31. <span data-ttu-id="f6f61-141">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="f6f61-142">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f6f61-142">Click Save.</span></span>
33. <span data-ttu-id="f6f61-143">Kliknij opcję Pobierz wysyłki zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-143">Click Fetch purchase order shipments.</span></span>
34. <span data-ttu-id="f6f61-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-144">Close the page.</span></span>
35. <span data-ttu-id="f6f61-145">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="f6f61-145">On the Action Pane, click Purchase.</span></span>
36. <span data-ttu-id="f6f61-146">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="f6f61-146">Click Confirm.</span></span>
37. <span data-ttu-id="f6f61-147">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="f6f61-147">On the Action Pane, click Manage.</span></span>
38. <span data-ttu-id="f6f61-148">Kliknij opcję Akredytywa/inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="f6f61-148">Click Letter of credit / import collection.</span></span>
39. <span data-ttu-id="f6f61-149">Kliknij przycisk Przetwarzaj.</span><span class="sxs-lookup"><span data-stu-id="f6f61-149">Click Process.</span></span>
40. <span data-ttu-id="f6f61-150">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="f6f61-150">Click Confirm.</span></span>
    * <span data-ttu-id="f6f61-151">Sprawdź, czy saldo instrumentu zmniejsza kwotę zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-151">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="f6f61-152">W tym przykładzie kwota zakupu = 500,00, limit instrumentu = 10000,00, dlatego saldo instrumentu = 9500,00.</span><span class="sxs-lookup"><span data-stu-id="f6f61-152">In this example, Purchase amount = 500.00,  Facility limit = 10000.00,  therefore, Facility balance = 9500.00.</span></span>  
41. <span data-ttu-id="f6f61-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-153">Close the page.</span></span>
42. <span data-ttu-id="f6f61-154">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="f6f61-154">In the Unit price field, enter a number.</span></span>
43. <span data-ttu-id="f6f61-155">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f6f61-155">Click Save.</span></span>
44. <span data-ttu-id="f6f61-156">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="f6f61-156">On the Action Pane, click Purchase.</span></span>
45. <span data-ttu-id="f6f61-157">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="f6f61-157">Click Confirm.</span></span>
    * <span data-ttu-id="f6f61-158">Skoryguj akredytywę ze względu na zmianę ceny jednostkowej.</span><span class="sxs-lookup"><span data-stu-id="f6f61-158">Amend the Letter of credit, due to the change in Unit price.</span></span>  
46. <span data-ttu-id="f6f61-159">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="f6f61-159">On the Action Pane, click Manage.</span></span>
47. <span data-ttu-id="f6f61-160">Kliknij opcję Akredytywa/inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="f6f61-160">Click Letter of credit / import collection.</span></span>
    * <span data-ttu-id="f6f61-161">Skoryguj akredytywę ze względu na zmianę ceny jednostkowej zakupu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-161">Amend the letter of credit, due to the change in Purchase unit price.</span></span>  
48. <span data-ttu-id="f6f61-162">Kliknij przycisk Przetwarzaj.</span><span class="sxs-lookup"><span data-stu-id="f6f61-162">Click Process.</span></span>
49. <span data-ttu-id="f6f61-163">Kliknij przycisk Zmiana.</span><span class="sxs-lookup"><span data-stu-id="f6f61-163">Click Amend.</span></span>
50. <span data-ttu-id="f6f61-164">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="f6f61-164">Click Remove.</span></span>
51. <span data-ttu-id="f6f61-165">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="f6f61-165">Click Yes.</span></span>
52. <span data-ttu-id="f6f61-166">Kliknij opcję Pobierz wysyłki zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-166">Click Fetch purchase order shipments.</span></span>
53. <span data-ttu-id="f6f61-167">Kliknij przycisk Przetwarzaj.</span><span class="sxs-lookup"><span data-stu-id="f6f61-167">Click Process.</span></span>
54. <span data-ttu-id="f6f61-168">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="f6f61-168">Click Confirm.</span></span>
    * <span data-ttu-id="f6f61-169">Sprawdź, czy saldo instrumentu zmniejsza kwotę zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-169">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="f6f61-170">W tym przykładzie zmodyfikowana kwota zakupu = 600,00, limit instrumentu = 10000,00, dlatego saldo instrumentu = 9400,00.</span><span class="sxs-lookup"><span data-stu-id="f6f61-170">In this example, edited Purchase amount = 600.00,  Facility limit = 10000.00,  therefore, Facility balance = 9400.00.</span></span>  
55. <span data-ttu-id="f6f61-171">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-171">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="f6f61-172">Księgowanie dokumentu dostawy</span><span class="sxs-lookup"><span data-stu-id="f6f61-172">Post Packing slip</span></span>
1. <span data-ttu-id="f6f61-173">W okienku akcji kliknij pozycję Odbierz.</span><span class="sxs-lookup"><span data-stu-id="f6f61-173">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="f6f61-174">Kliknij opcję Dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="f6f61-174">Click Product receipt.</span></span>
3. <span data-ttu-id="f6f61-175">W polu PurchParmTable_Num wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-175">In the PurchParmTable_Num field, type a value.</span></span>
    * <span data-ttu-id="f6f61-176">Wybierz numer wysyłki utworzonej z odniesieniem do akredytywy.</span><span class="sxs-lookup"><span data-stu-id="f6f61-176">Select the Shipment number created with reference to the Letter of credit.</span></span>  
4. <span data-ttu-id="f6f61-177">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-177">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f6f61-178">W polu Data dokumentu przyjęcia produktów wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-178">In the Product receipt date field, enter a date.</span></span>
6. <span data-ttu-id="f6f61-179">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f6f61-179">Click OK.</span></span>
7. <span data-ttu-id="f6f61-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-180">Close the page.</span></span>
8. <span data-ttu-id="f6f61-181">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-181">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="f6f61-182">Weryfikacja stanu akredytywy importowej</span><span class="sxs-lookup"><span data-stu-id="f6f61-182">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="f6f61-183">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa importowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="f6f61-183">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="f6f61-184">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f6f61-184">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f6f61-185">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-185">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f6f61-186">Zweryfikuj stan akredytywy importowej.</span><span class="sxs-lookup"><span data-stu-id="f6f61-186">Verify the Import letter of credit status.</span></span>  
4. <span data-ttu-id="f6f61-187">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-187">Close the page.</span></span>
5. <span data-ttu-id="f6f61-188">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-188">Close the page.</span></span>

## <a name="post-purchase-invoice"></a><span data-ttu-id="f6f61-189">Księgowanie faktury zakupu</span><span class="sxs-lookup"><span data-stu-id="f6f61-189">Post purchase invoice</span></span>
1. <span data-ttu-id="f6f61-190">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-190">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
    * <span data-ttu-id="f6f61-191">Wybierz zamówienie zakupu, które zostało utworzone z akredytywą.</span><span class="sxs-lookup"><span data-stu-id="f6f61-191">Select the purchase order that was created with letter of credit.</span></span>  
2. <span data-ttu-id="f6f61-192">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f6f61-192">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f6f61-193">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-193">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f6f61-194">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="f6f61-194">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="f6f61-195">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="f6f61-195">Click Invoice.</span></span>
6. <span data-ttu-id="f6f61-196">W polu Numer wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-196">In the Number field, type a value.</span></span>
7. <span data-ttu-id="f6f61-197">W polu Numer wysyłki wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-197">In the Shipment number field, enter or select a value.</span></span>
8. <span data-ttu-id="f6f61-198">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-198">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="f6f61-199">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="f6f61-199">In the Invoice date field, enter a date.</span></span>
10. <span data-ttu-id="f6f61-200">Kliknij przycisk Aktualizuj stan uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="f6f61-200">Click Update match status.</span></span>
11. <span data-ttu-id="f6f61-201">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="f6f61-201">Click Post.</span></span>
12. <span data-ttu-id="f6f61-202">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-202">Close the page.</span></span>
13. <span data-ttu-id="f6f61-203">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-203">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="f6f61-204">Weryfikacja stanu akredytywy importowej</span><span class="sxs-lookup"><span data-stu-id="f6f61-204">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="f6f61-205">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa importowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="f6f61-205">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="f6f61-206">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f6f61-206">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f6f61-207">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-207">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f6f61-208">Zweryfikuj akredytywę importową2.</span><span class="sxs-lookup"><span data-stu-id="f6f61-208">Verify the Import letter of credit2.</span></span>  
    * <span data-ttu-id="f6f61-209">Sprawdzanie poprawności: Stan wysyłki = Zafakturowana  Szczegóły instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="f6f61-209">Validate :  Shipment status = Invoiced  Bank facility details</span></span>  
4. <span data-ttu-id="f6f61-210">Kliknij przycisk Wyświetl.</span><span class="sxs-lookup"><span data-stu-id="f6f61-210">Click View.</span></span>
5. <span data-ttu-id="f6f61-211">Kliknij opcję Drukuj zgłoszenie.</span><span class="sxs-lookup"><span data-stu-id="f6f61-211">Click Print application.</span></span>
6. <span data-ttu-id="f6f61-212">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f6f61-212">Click OK.</span></span>
    * <span data-ttu-id="f6f61-213">Sprawdź, czy zgłoszenie akredytywy jest drukowane.</span><span class="sxs-lookup"><span data-stu-id="f6f61-213">Verify that the Letter of credit application gets printed.</span></span>  
7. <span data-ttu-id="f6f61-214">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-214">Close the page.</span></span>
8. <span data-ttu-id="f6f61-215">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-215">Close the page.</span></span>
9. <span data-ttu-id="f6f61-216">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-216">Close the page.</span></span>

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a><span data-ttu-id="f6f61-217">Księgowanie arkusza płatności dostawcy dla utworzonej faktury zakupu z akredytywą</span><span class="sxs-lookup"><span data-stu-id="f6f61-217">Post Vendor payment journal for the created purchase invoice with letter of credit</span></span>
1. <span data-ttu-id="f6f61-218">Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="f6f61-218">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="f6f61-219">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f6f61-219">Click New.</span></span>
3. <span data-ttu-id="f6f61-220">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-220">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="f6f61-221">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-221">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f6f61-222">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="f6f61-222">Click Lines.</span></span>
6. <span data-ttu-id="f6f61-223">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-223">In the Date field, enter a date.</span></span>
7. <span data-ttu-id="f6f61-224">W polu Konto podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="f6f61-224">In the Account field, specify the desired values.</span></span>
8. <span data-ttu-id="f6f61-225">Kliknij opcję Rozlicz transakcje.</span><span class="sxs-lookup"><span data-stu-id="f6f61-225">Click Settle transactions.</span></span>
9. <span data-ttu-id="f6f61-226">Rozwiń sekcję Sumy.</span><span class="sxs-lookup"><span data-stu-id="f6f61-226">Expand the Totals section.</span></span>
10. <span data-ttu-id="f6f61-227">W polu Pokaż wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="f6f61-227">In the Show field, select an option.</span></span>
    * <span data-ttu-id="f6f61-228">Sprawdź, czy pola Numer dokumentu banku i Numer wysyłki zostały zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="f6f61-228">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
11. <span data-ttu-id="f6f61-229">Zaznacz pole wyboru Zaznacz.</span><span class="sxs-lookup"><span data-stu-id="f6f61-229">Select the Mark check box.</span></span>
12. <span data-ttu-id="f6f61-230">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f6f61-230">Click OK.</span></span>
13. <span data-ttu-id="f6f61-231">Kliknij kartę Płatność.</span><span class="sxs-lookup"><span data-stu-id="f6f61-231">Click the Payment tab.</span></span>
    * <span data-ttu-id="f6f61-232">Sprawdź, czy pola Numer dokumentu banku i Numer wysyłki zostały zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="f6f61-232">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
14. <span data-ttu-id="f6f61-233">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="f6f61-233">Click Post.</span></span>
15. <span data-ttu-id="f6f61-234">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-234">Close the page.</span></span>
16. <span data-ttu-id="f6f61-235">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-235">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a><span data-ttu-id="f6f61-236">Weryfikacja stanu akredytywy importowej po zapłacie faktury</span><span class="sxs-lookup"><span data-stu-id="f6f61-236">Verify Import letter of credit status after Invoice paid</span></span>
1. <span data-ttu-id="f6f61-237">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Akredytywy > Akredytywa importowa i inkaso importowe.</span><span class="sxs-lookup"><span data-stu-id="f6f61-237">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="f6f61-238">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f6f61-238">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f6f61-239">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-239">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f6f61-240">Zweryfikuj stan akredytywy importowej.</span><span class="sxs-lookup"><span data-stu-id="f6f61-240">Verify the Import letter of credit status.</span></span>   
4. <span data-ttu-id="f6f61-241">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-241">Close the page.</span></span>

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a><span data-ttu-id="f6f61-242">Weryfikacja raportu o limicie i wykorzystaniu instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="f6f61-242">Verify the Bank facility limit and utilization report</span></span>
1. <span data-ttu-id="f6f61-243">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Zapytania i raporty > Akredytywy lub poręczenia > Raport produktów bankowych i wykorzystania.</span><span class="sxs-lookup"><span data-stu-id="f6f61-243">Go to Cash and bank management > Inquiries and reports > Letters of credit or guarantee > Bank facilities and utilization report.</span></span>
2. <span data-ttu-id="f6f61-244">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="f6f61-244">Expand the Records to include section.</span></span>
3. <span data-ttu-id="f6f61-245">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="f6f61-245">Click Filter.</span></span>
    * <span data-ttu-id="f6f61-246">W polu Kryteria wpisz wymagane konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="f6f61-246">Define the Criteria field with the required bank account.</span></span>  
4. <span data-ttu-id="f6f61-247">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f6f61-247">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="f6f61-248">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-248">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f6f61-249">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f6f61-249">Click OK.</span></span>
7. <span data-ttu-id="f6f61-250">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f6f61-250">Click OK.</span></span>
    * <span data-ttu-id="f6f61-251">Sprawdź raport zawierający listę transakcji.</span><span class="sxs-lookup"><span data-stu-id="f6f61-251">Verify the report which lists the transactions.</span></span>  
    * <span data-ttu-id="f6f61-252">Sprawdź, czy w raporcie znajdują się transakcje z numerem dokumentu banku, limit instrumentu, wykorzystaną kwotą i kwotą salda instrumentu.</span><span class="sxs-lookup"><span data-stu-id="f6f61-252">Verify the report lists the transactions with Bank document number, Facility limit, utilized amount and the facility balance amount.</span></span>  
8. <span data-ttu-id="f6f61-253">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f6f61-253">Close the page.</span></span>


