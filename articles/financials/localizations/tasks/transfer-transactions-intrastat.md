---
title: Przesyłanie transakcji do systemu Intrastat
description: Ta procedura pokazuje, jak skonfigurować parametry systemu Intrastat i przesłać do niego transakcje.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0e332d5cae09c5026a64a4463e301a008860bd9
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538218"
---
# <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="590a9-103">Przesyłanie transakcji do systemu Intrastat</span><span class="sxs-lookup"><span data-stu-id="590a9-103">Transfer transactions to the Intrastat</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="590a9-104">Ta procedura pokazuje, jak skonfigurować parametry systemu Intrastat i przesłać do niego transakcje.</span><span class="sxs-lookup"><span data-stu-id="590a9-104">This procedure walks you through how to set up Intrastat parameters and transfer transactions to Intrastat.</span></span> <span data-ttu-id="590a9-105">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="590a9-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="create-new-and-update-existing-commodity-code"></a><span data-ttu-id="590a9-106">Tworzenie nowego i aktualizowanie istniejącego kodu asortymentu</span><span class="sxs-lookup"><span data-stu-id="590a9-106">Create new and update existing commodity code</span></span>
1. <span data-ttu-id="590a9-107">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Ustawienia > Kategorie i atrybuty > Hierarchie kategorii.</span><span class="sxs-lookup"><span data-stu-id="590a9-107">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="590a9-108">Na liście znajdź lub zaznacz rekord „Kody asortymentu Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="590a9-108">In the list, find or select the record "Intrastat commodity codes."</span></span>
3. <span data-ttu-id="590a9-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="590a9-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="590a9-110">W drzewie zaznacz rekord.</span><span class="sxs-lookup"><span data-stu-id="590a9-110">In the tree, select 'a record'.</span></span>
    * <span data-ttu-id="590a9-111">Na przykład wybierz „Intrastat\Głośnik”.</span><span class="sxs-lookup"><span data-stu-id="590a9-111">For example, select 'Intrastat\Speaker'.</span></span>  
5. <span data-ttu-id="590a9-112">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="590a9-112">Click Edit.</span></span>
6. <span data-ttu-id="590a9-113">Rozwiń sekcję Handel zagraniczny.</span><span class="sxs-lookup"><span data-stu-id="590a9-113">Expand the Foreign trade section.</span></span>
7. <span data-ttu-id="590a9-114">W polu Jednostki dodatkowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-114">In the Additional units field, enter or select a value.</span></span>
    * <span data-ttu-id="590a9-115">Na przykład wybierz opcję „szt.”.</span><span class="sxs-lookup"><span data-stu-id="590a9-115">For example, choose 'pcs'.</span></span>  
8. <span data-ttu-id="590a9-116">W polu Waga nie ma zastosowania zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="590a9-116">Select Yes in the Weight not applicable field.</span></span>
9. <span data-ttu-id="590a9-117">W drzewie zaznacz element „Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="590a9-117">In the tree, select 'Intrastat'.</span></span>
10. <span data-ttu-id="590a9-118">Kliknij opcję Nowy węzeł kategorii.</span><span class="sxs-lookup"><span data-stu-id="590a9-118">Click New category node.</span></span>
11. <span data-ttu-id="590a9-119">W polu Nazwa wprowadź nazwę asortymentu.</span><span class="sxs-lookup"><span data-stu-id="590a9-119">In the Name field, enter the name of commodity.</span></span>
    * <span data-ttu-id="590a9-120">Na przykład wpisz „Inny towar”.</span><span class="sxs-lookup"><span data-stu-id="590a9-120">For example, type 'Other commodity'.</span></span>  
12. <span data-ttu-id="590a9-121">W polu Kod wprowadź kod asortymentu.</span><span class="sxs-lookup"><span data-stu-id="590a9-121">In the Code field, enter the commodity code.</span></span>
    * <span data-ttu-id="590a9-122">Na przykład wpisz „995 00 00”.</span><span class="sxs-lookup"><span data-stu-id="590a9-122">For example, type '995 00 00'.</span></span>  
13. <span data-ttu-id="590a9-123">W polu Przyjazna nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-123">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="590a9-124">Na przykład wpisz „Inny”.</span><span class="sxs-lookup"><span data-stu-id="590a9-124">For example, type 'Other'.</span></span>  
14. <span data-ttu-id="590a9-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="590a9-125">Click Save.</span></span>
15. <span data-ttu-id="590a9-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="590a9-126">Close the page.</span></span>

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a><span data-ttu-id="590a9-127">Przypisywanie kodu asortymentu do hierarchii produktów i zwolnionego produktu</span><span class="sxs-lookup"><span data-stu-id="590a9-127">Assign commodity code to product hierarchy and released product</span></span>
1. <span data-ttu-id="590a9-128">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="590a9-128">Use the Quick Filter to find records.</span></span> <span data-ttu-id="590a9-129">Na przykład wyfiltruj według pola Nazwa z wartością „sprzedaż”.</span><span class="sxs-lookup"><span data-stu-id="590a9-129">For example, filter on the Name field with a value of 'sales'.</span></span>
2. <span data-ttu-id="590a9-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="590a9-130">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="590a9-131">W drzewie rozwiń węzeł kategorii.</span><span class="sxs-lookup"><span data-stu-id="590a9-131">In the tree, expand 'a category node'.</span></span>
    * <span data-ttu-id="590a9-132">Na przykład rozwiń węzeł „Hierarchia sprzedaży\Domowy zestaw audio”.</span><span class="sxs-lookup"><span data-stu-id="590a9-132">For example, expand 'Sales hierarchy\Home audio'.</span></span>  
4. <span data-ttu-id="590a9-133">W drzewie zaznacz kategorię, którą chcesz przypisać do kodu asortymentu.</span><span class="sxs-lookup"><span data-stu-id="590a9-133">In the tree, select 'the category to assign to the commodity code'.</span></span>
    * <span data-ttu-id="590a9-134">Na przykład zaznacz element „Hierarchia sprzedaży\Domowy zestaw audio\Głośniki”.</span><span class="sxs-lookup"><span data-stu-id="590a9-134">For example, select 'Sales hierarchy\Home audio\Speakers.</span></span>  
5. <span data-ttu-id="590a9-135">Rozwiń sekcję Kody asortymentu.</span><span class="sxs-lookup"><span data-stu-id="590a9-135">Expand the Commodity codes section.</span></span>
6. <span data-ttu-id="590a9-136">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="590a9-136">Click Add.</span></span>
7. <span data-ttu-id="590a9-137">W polu Wybierz hierarchię zaznacz opcję „Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="590a9-137">In the Select hierarchy field, select 'Intrastat'.</span></span>
8. <span data-ttu-id="590a9-138">Na liście znajdź i zaznacz kod asortymentu.</span><span class="sxs-lookup"><span data-stu-id="590a9-138">In the list, find and select the commodity code</span></span>
    * <span data-ttu-id="590a9-139">Na przykład wybierz „920 20 34 Głośnik”.</span><span class="sxs-lookup"><span data-stu-id="590a9-139">For example, select '920 20 34 Speaker'.</span></span>  
9. <span data-ttu-id="590a9-140">Kliknij opcję SelectCodes.</span><span class="sxs-lookup"><span data-stu-id="590a9-140">Click SelectCodes.</span></span>
10. <span data-ttu-id="590a9-141">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="590a9-141">Click OK.</span></span>
11. <span data-ttu-id="590a9-142">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="590a9-142">Go to Product information management > Products > Released products.</span></span>
12. <span data-ttu-id="590a9-143">Z listy wybierz zwolniony produkt, który przypiszesz do kodu asortymentu.</span><span class="sxs-lookup"><span data-stu-id="590a9-143">In the list, choose the released product that you will assign to the commodity code.</span></span>
    * <span data-ttu-id="590a9-144">Na przykład wybierz opcję „D0001”.</span><span class="sxs-lookup"><span data-stu-id="590a9-144">For example, choose 'D0001'.</span></span>  
13. <span data-ttu-id="590a9-145">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="590a9-145">Click Edit.</span></span>
14. <span data-ttu-id="590a9-146">Rozwiń sekcję Handel zagraniczny.</span><span class="sxs-lookup"><span data-stu-id="590a9-146">Expand the Foreign trade section.</span></span>
15. <span data-ttu-id="590a9-147">W polu Asortyment wprowadź kod asortymentu.</span><span class="sxs-lookup"><span data-stu-id="590a9-147">In the Commodity field, enter the commodity code</span></span>
    * <span data-ttu-id="590a9-148">Na przykład wybierz wartość „920 20 34 Głośnik”.</span><span class="sxs-lookup"><span data-stu-id="590a9-148">For example, select value '920 20 34 Speaker'.</span></span>    
16. <span data-ttu-id="590a9-149">W polu % opłat dodatkowych wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="590a9-149">In the Charges percentage field, enter a number.</span></span>
    * <span data-ttu-id="590a9-150">Na przykład wpisz „3”.</span><span class="sxs-lookup"><span data-stu-id="590a9-150">For example, enter '3'.</span></span>  
17. <span data-ttu-id="590a9-151">W polu Kraj/region wprowadź lub wybierz kraj albo region pochodzenia.</span><span class="sxs-lookup"><span data-stu-id="590a9-151">In the Country/region field, enter or select a country or region of origin</span></span>
    * <span data-ttu-id="590a9-152">Na przykład zaznacz „AUT”.</span><span class="sxs-lookup"><span data-stu-id="590a9-152">For example, select 'AUT'.</span></span>  
18. <span data-ttu-id="590a9-153">Rozwiń sekcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="590a9-153">Expand the Manage inventory section.</span></span>
19. <span data-ttu-id="590a9-154">W polu Waga netto wpisz wagę w kg.</span><span class="sxs-lookup"><span data-stu-id="590a9-154">In the Net weight field, enter a weight in kg.</span></span>
    * <span data-ttu-id="590a9-155">Na przykład wpisz „2,5”.</span><span class="sxs-lookup"><span data-stu-id="590a9-155">For example, enter '2.5'.</span></span>  
20. <span data-ttu-id="590a9-156">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="590a9-156">Click Save.</span></span>

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a><span data-ttu-id="590a9-157">Konfigurowanie kodów transakcji Intrastat i parametrów handlu zagranicznego</span><span class="sxs-lookup"><span data-stu-id="590a9-157">Set up Intrastat transaction codes and foreign trade parameters</span></span>
1. <span data-ttu-id="590a9-158">Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Kody transakcji</span><span class="sxs-lookup"><span data-stu-id="590a9-158">Go to Tax > Setup > Foreign trade > Transaction codes</span></span>
2. <span data-ttu-id="590a9-159">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="590a9-159">Click New.</span></span>
3. <span data-ttu-id="590a9-160">W polu Kod transakcji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-160">In the Transaction code field, type a value.</span></span>
    * <span data-ttu-id="590a9-161">Na przykład wpisz „21” jako kod transakcji używanej do wykonania zwrotu.</span><span class="sxs-lookup"><span data-stu-id="590a9-161">For example, enter '21' for the transaction code used as return.</span></span>  
4. <span data-ttu-id="590a9-162">W polu Nazwa wpisz nazwę kodu transakcji.</span><span class="sxs-lookup"><span data-stu-id="590a9-162">In the Name field, type the name of transaction code.</span></span>
    * <span data-ttu-id="590a9-163">Na przykład wpisz „Zwrot”.</span><span class="sxs-lookup"><span data-stu-id="590a9-163">For example, enter 'Return'.</span></span>  
5. <span data-ttu-id="590a9-164">W polu Kwota statystyczna wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="590a9-164">In the Statistical amount field, select an option.</span></span>
    * <span data-ttu-id="590a9-165">Na przykład zaznacz opcję „Puste”, co wskaże, że wartości statystyczna, która ma być raportowana dla transakcji o kodzie transakcji „21”, zawsze będzie równa zero.</span><span class="sxs-lookup"><span data-stu-id="590a9-165">For example, select 'Empty' which indicates that the Statistical value to be reported for transactions with Transaction code of "21" will always be zero.</span></span>  
6. <span data-ttu-id="590a9-166">Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego</span><span class="sxs-lookup"><span data-stu-id="590a9-166">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
7. <span data-ttu-id="590a9-167">W polu Kod transakcji wpisz lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-167">In the Transaction code field, enter or select a value.</span></span>
    * <span data-ttu-id="590a9-168">Na przykład wybierz opcję „11”.</span><span class="sxs-lookup"><span data-stu-id="590a9-168">For example, select '11'.</span></span>  
8. <span data-ttu-id="590a9-169">W polu Faktura korygująca wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-169">In the Credit note field, enter or select a value.</span></span>
    * <span data-ttu-id="590a9-170">Ta wartość określa również fizyczny zwrot.</span><span class="sxs-lookup"><span data-stu-id="590a9-170">This value also identifies the physical return.</span></span> <span data-ttu-id="590a9-171">Faktura korygująca na fizyczny zwrot zostanie przesłana do dziennika systemu Intrastat z zastosowaniem przeciwnego kierunku.</span><span class="sxs-lookup"><span data-stu-id="590a9-171">The credit note for the physical return will be transferred in the Intrastat journal with opposite direction.</span></span> <span data-ttu-id="590a9-172">Na przykład zwrot przyjęcia jest przenoszony jako wysyłka.</span><span class="sxs-lookup"><span data-stu-id="590a9-172">For example, the return of arrival is transferred as dispatch.</span></span>   <span data-ttu-id="590a9-173">Natomiast faktura korygująca jest traktowana jako korekta i przenoszona z zastosowaniem tego samego kierunku, ale przeciwnego znaku.</span><span class="sxs-lookup"><span data-stu-id="590a9-173">Otherwise, the credit note is considered a correction and is transferred with the same direction and opposite sign.</span></span> <span data-ttu-id="590a9-174">Na przykład korekta przyjęcia jest przenoszona jako przyjęcie z kwotą ujemną, a flaga aktywności jest ustawiana na „Korekta”.</span><span class="sxs-lookup"><span data-stu-id="590a9-174">For example, the correction of arrival is transferred as an arrival with negative amount and the active flag is set to "Correction".</span></span>  
9. <span data-ttu-id="590a9-175">Rozwiń sekcję Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="590a9-175">Expand the Transfer section.</span></span>
10. <span data-ttu-id="590a9-176">W polu Pozycje z kodem asortymentu zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="590a9-176">Select Yes in the Items with commodity code field.</span></span>
    * <span data-ttu-id="590a9-177">Wybierz tę opcję, aby przenieść tylko transakcje z przypisanym kodem asortymentu.</span><span class="sxs-lookup"><span data-stu-id="590a9-177">Select this option to transfer only the transactions with a commodity code assigned.</span></span> <span data-ttu-id="590a9-178">Transakcje bez kodu asortymentu nie będą przenoszone do systemu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="590a9-178">Transactions without a commodity code won't be transferred to Intrastat.</span></span>  
11. <span data-ttu-id="590a9-179">W polu Przenieś, jeśli spełnione kryterium dla wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="590a9-179">In the Transfer when meeting criterion for field, select an option.</span></span>
    * <span data-ttu-id="590a9-180">Na przykład wybierz wartość „Jeden z wybranych”.</span><span class="sxs-lookup"><span data-stu-id="590a9-180">For example, select 'One of the selected'.</span></span>  
12. <span data-ttu-id="590a9-181">Rozwiń sekcję Hierarchia kodów asortymentu.</span><span class="sxs-lookup"><span data-stu-id="590a9-181">Expand the Commodity code hierarchy section.</span></span>
13. <span data-ttu-id="590a9-182">Kliknij kartę Właściwości kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="590a9-182">Click the Country/region properties tab.</span></span>
14. <span data-ttu-id="590a9-183">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="590a9-183">Click New.</span></span>
15. <span data-ttu-id="590a9-184">W polu kraj/region wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-184">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="590a9-185">Na przykład wybierz wartość „FRA”.</span><span class="sxs-lookup"><span data-stu-id="590a9-185">For example, select the value 'FRA'.</span></span>  
16. <span data-ttu-id="590a9-186">W polu Kod Intrastat wprowadź kod ISO kraju.</span><span class="sxs-lookup"><span data-stu-id="590a9-186">In the Intrastat code field, enter the ISO code for the country.</span></span>
    * <span data-ttu-id="590a9-187">Na przykład wpisz „FR”.</span><span class="sxs-lookup"><span data-stu-id="590a9-187">For example, type 'FR'.</span></span>  
17. <span data-ttu-id="590a9-188">W polu Typ kraju/regionu wybierz opcję „UE”.</span><span class="sxs-lookup"><span data-stu-id="590a9-188">In the Country/region type field, select 'EU'.</span></span>
18. <span data-ttu-id="590a9-189">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="590a9-189">Click the Number sequences tab.</span></span>

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a><span data-ttu-id="590a9-190">Konfigurowanie metod dostawy i reguł uwzględniania opłat w raportowaniu Intrastat</span><span class="sxs-lookup"><span data-stu-id="590a9-190">Set up Modes of delivery and rules for including charges in Intrastat</span></span>
1. <span data-ttu-id="590a9-191">Wybierz kolejno opcje Sprzedaż i marketing > Ustawienia > Dystrybucja > Metody dostawy</span><span class="sxs-lookup"><span data-stu-id="590a9-191">Go to Sales and marketing > Setup > Distribution > Modes of delivery</span></span>
2. <span data-ttu-id="590a9-192">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="590a9-192">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="590a9-193">Na przykład wybierz wartość „20 Lotniczy”.</span><span class="sxs-lookup"><span data-stu-id="590a9-193">For example, select '20 Air'.</span></span>  
3. <span data-ttu-id="590a9-194">Rozwiń sekcję Handel zagraniczny.</span><span class="sxs-lookup"><span data-stu-id="590a9-194">Expand the Foreign trade section.</span></span>
4. <span data-ttu-id="590a9-195">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="590a9-195">Click Edit.</span></span>
5. <span data-ttu-id="590a9-196">W polu Transport wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-196">In the Transport field, enter or select a value.</span></span>
    * <span data-ttu-id="590a9-197">Na przykład wybierz opcję „02”.</span><span class="sxs-lookup"><span data-stu-id="590a9-197">For example, select '02'.</span></span>  
6. <span data-ttu-id="590a9-198">Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia opłat > Kod opłat.</span><span class="sxs-lookup"><span data-stu-id="590a9-198">Go to Accounts receivable > Charges setup > Charges code.</span></span>
7. <span data-ttu-id="590a9-199">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="590a9-199">Use the Quick Filter to find records.</span></span> <span data-ttu-id="590a9-200">Na przykład wyfiltruj według pola Kod opłat z wartością „fracht”.</span><span class="sxs-lookup"><span data-stu-id="590a9-200">For example, filter on the Charges code field with a value of 'freight'.</span></span>
8. <span data-ttu-id="590a9-201">Rozwiń sekcję Handel zagraniczny.</span><span class="sxs-lookup"><span data-stu-id="590a9-201">Expand the Foreign trade section.</span></span>
9. <span data-ttu-id="590a9-202">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="590a9-202">Click Edit.</span></span>
10. <span data-ttu-id="590a9-203">W polu Wartość faktury dla Intrastat zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="590a9-203">Select Yes in the Intrastat invoice value field.</span></span>
    * <span data-ttu-id="590a9-204">Kwota zostanie przeniesiona do pola Opłaty faktury i zsumowana z kwotą przeniesioną do pola Kwota faktury.</span><span class="sxs-lookup"><span data-stu-id="590a9-204">The amount will be transferred to the  Invoice charges field and will be summarized with the amount transferred in the Invoice amount field.</span></span>    <span data-ttu-id="590a9-205">W polu Wartość statystyczna Intrastat wybierz opcję Tak, jeśli kwota opłat musi zostać przeniesiona do pola Opłaty statystyczne i zsumowana z wartością pola Kwota statystyczna.</span><span class="sxs-lookup"><span data-stu-id="590a9-205">Select Yes in the Intrastat statistical value field if the amount of changes need to be transferred to the field Statistical charges and summarized with Statistical amount.</span></span>  

## <a name="sell-products-for-eu-customers"></a><span data-ttu-id="590a9-206">Sprzedaż produktów do odbiorców w UE</span><span class="sxs-lookup"><span data-stu-id="590a9-206">Sell products for EU customers</span></span>
1. <span data-ttu-id="590a9-207">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="590a9-207">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="590a9-208">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="590a9-208">Click New.</span></span>
3. <span data-ttu-id="590a9-209">W polu Konto odbiorcy zaznacz odbiorcę z UE.</span><span class="sxs-lookup"><span data-stu-id="590a9-209">In the Customer account field, select an EU customer</span></span>
    * <span data-ttu-id="590a9-210">Na przykład wybierz wartość „DE 012 Litware Retail”.</span><span class="sxs-lookup"><span data-stu-id="590a9-210">For example, select "DE-012 Litware Retail".</span></span>  
4. <span data-ttu-id="590a9-211">Rozwiń sekcję Dostawa.</span><span class="sxs-lookup"><span data-stu-id="590a9-211">Expand the Delivery section.</span></span>
5. <span data-ttu-id="590a9-212">W polu Metoda dostawy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-212">In the Mode of delivery field, enter or select a value.</span></span>
    * <span data-ttu-id="590a9-213">Na przykład wybierz wartość „20 Lotniczy”.</span><span class="sxs-lookup"><span data-stu-id="590a9-213">For example, select '20 Air'.</span></span>  
6. <span data-ttu-id="590a9-214">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="590a9-214">Click OK.</span></span>
7. <span data-ttu-id="590a9-215">Umieść kursor w pierwszym wierszu zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="590a9-215">Place the cursor on the first row of sales order lines.</span></span>
8. <span data-ttu-id="590a9-216">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-216">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="590a9-217">Na przykład zaznacz „D001”.</span><span class="sxs-lookup"><span data-stu-id="590a9-217">For example, select 'D001'.</span></span>  
9. <span data-ttu-id="590a9-218">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="590a9-218">Expand the Line details section.</span></span>
10. <span data-ttu-id="590a9-219">Kliknij kartę Handel zagraniczny.</span><span class="sxs-lookup"><span data-stu-id="590a9-219">Click the Foreign trade tab.</span></span>
    * <span data-ttu-id="590a9-220">Pole transportu jest wypełniane automatycznie na podstawie wybranej metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="590a9-220">The transport is filled automatically from the chosen Mode of delivery.</span></span>  
11. <span data-ttu-id="590a9-221">W polu Port wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-221">In the Port field, enter or select a value.</span></span>
12. <span data-ttu-id="590a9-222">Kliknij opcję Finanse.</span><span class="sxs-lookup"><span data-stu-id="590a9-222">Click Financials.</span></span>
    * <span data-ttu-id="590a9-223">Zgodnie z ustawieniami ta kwota będzie dodana do pola Wartość faktury dla Intrastat.</span><span class="sxs-lookup"><span data-stu-id="590a9-223">As per the settings, this amount will be included in Intrastat invoice value.</span></span>  
13. <span data-ttu-id="590a9-224">Kliknij opcję Obsługuj opłaty.</span><span class="sxs-lookup"><span data-stu-id="590a9-224">Click Maintain charges.</span></span>
14. <span data-ttu-id="590a9-225">W polu Kod opłat wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-225">In the Charges code field, enter or select a value.</span></span>
    * <span data-ttu-id="590a9-226">Na przykład wybierz wartość „FRACHT”.</span><span class="sxs-lookup"><span data-stu-id="590a9-226">For example, select 'FREIGHT'.</span></span>  
15. <span data-ttu-id="590a9-227">Zaznacz pole wyboru Zachowaj.</span><span class="sxs-lookup"><span data-stu-id="590a9-227">Select the Keep check box.</span></span>
16. <span data-ttu-id="590a9-228">W polu Kod opłat wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="590a9-228">In the Charges value field, enter a number.</span></span>
    * <span data-ttu-id="590a9-229">Na przykład wpisz „10”.</span><span class="sxs-lookup"><span data-stu-id="590a9-229">For example, enter '10'.</span></span>  
17. <span data-ttu-id="590a9-230">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="590a9-230">Click Save.</span></span>
18. <span data-ttu-id="590a9-231">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="590a9-231">Close the page.</span></span>
19. <span data-ttu-id="590a9-232">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="590a9-232">On the Action Pane, click Invoice.</span></span>
20. <span data-ttu-id="590a9-233">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="590a9-233">Click Invoice.</span></span>
21. <span data-ttu-id="590a9-234">Rozwiń sekcję Parametry.</span><span class="sxs-lookup"><span data-stu-id="590a9-234">Expand the Parameters section.</span></span>
22. <span data-ttu-id="590a9-235">W polu Ilość zaznacz opcję Wszystko.</span><span class="sxs-lookup"><span data-stu-id="590a9-235">In the Quantity field, select 'All'.</span></span>
23. <span data-ttu-id="590a9-236">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="590a9-236">Expand the Setup section.</span></span>
24. <span data-ttu-id="590a9-237">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="590a9-237">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="590a9-238">Na przykład wpisz „2015-01-31”.</span><span class="sxs-lookup"><span data-stu-id="590a9-238">For example, enter '2015-01-31'.</span></span>  
25. <span data-ttu-id="590a9-239">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="590a9-239">Click OK.</span></span>
26. <span data-ttu-id="590a9-240">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="590a9-240">Click OK.</span></span>
27. <span data-ttu-id="590a9-241">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="590a9-241">Close the page.</span></span>
28. <span data-ttu-id="590a9-242">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="590a9-242">Click New.</span></span>
29. <span data-ttu-id="590a9-243">W polu Konto odbiorcy zaznacz odbiorcę z UE.</span><span class="sxs-lookup"><span data-stu-id="590a9-243">In the Customer account field, select an EU customer.</span></span>
    * <span data-ttu-id="590a9-244">Na przykład wybierz wartość „DE-013 Trey Wholesales”.</span><span class="sxs-lookup"><span data-stu-id="590a9-244">For example, select 'DE-013 Trey Wholesales'</span></span>  
30. <span data-ttu-id="590a9-245">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="590a9-245">Click OK.</span></span>
31. <span data-ttu-id="590a9-246">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-246">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="590a9-247">Na przykład zaznacz „D0001”.</span><span class="sxs-lookup"><span data-stu-id="590a9-247">For example, select 'D0001'.</span></span>  
32. <span data-ttu-id="590a9-248">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="590a9-248">Click Save.</span></span>
33. <span data-ttu-id="590a9-249">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="590a9-249">Click Invoice.</span></span>
34. <span data-ttu-id="590a9-250">Wprowadź datę w polu Data faktury.</span><span class="sxs-lookup"><span data-stu-id="590a9-250">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="590a9-251">Na przykład wpisz datę „2015-01-31”.</span><span class="sxs-lookup"><span data-stu-id="590a9-251">For example, enter the date '2015-01-31'.</span></span>  
35. <span data-ttu-id="590a9-252">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="590a9-252">Click OK.</span></span>
36. <span data-ttu-id="590a9-253">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="590a9-253">Click OK.</span></span>

## <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="590a9-254">Przesyłanie transakcji do systemu Intrastat</span><span class="sxs-lookup"><span data-stu-id="590a9-254">Transfer transactions to the Intrastat</span></span>
1. <span data-ttu-id="590a9-255">Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="590a9-255">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
2. <span data-ttu-id="590a9-256">Kliknij przycisk Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="590a9-256">Click Transfer.</span></span>
3. <span data-ttu-id="590a9-257">W polu Faktura dla odbiorcy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="590a9-257">Select Yes in the Customer invoice field.</span></span>
4. <span data-ttu-id="590a9-258">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="590a9-258">Click Filter.</span></span>
5. <span data-ttu-id="590a9-259">Na liście zaznacz wiersz z datą.</span><span class="sxs-lookup"><span data-stu-id="590a9-259">In the list, mark the row with Date</span></span>
6. <span data-ttu-id="590a9-260">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="590a9-260">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="590a9-261">Na przykład wprowadzić filtru na okres stycznia 2015 r. (dokładna wartość zależy od formatu daty): 1.1.2015..31.1.2015</span><span class="sxs-lookup"><span data-stu-id="590a9-261">For example, enter the filter for the period January 2015 (the exact value depends on your date format): 1/1/2015..1/31/2015</span></span>  
7. <span data-ttu-id="590a9-262">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="590a9-262">Click OK.</span></span>
8. <span data-ttu-id="590a9-263">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="590a9-263">Click OK.</span></span>
9. <span data-ttu-id="590a9-264">Na liście znajdź i zaznacz przeniesiony rekord.</span><span class="sxs-lookup"><span data-stu-id="590a9-264">In the list, find and selected the transferred record.</span></span>
10. <span data-ttu-id="590a9-265">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="590a9-265">Click the General tab.</span></span>
    * <span data-ttu-id="590a9-266">Przejrzyj przeniesione dane, w tym kraj/region miejsca docelowego/wysyłki, kraj pochodzenia, wagę, ilość, ilość w jednostkach dodatkowych, oznaczenie asortymentu, kod transakcji, kwoty na fakturach i kwoty statystyczne.</span><span class="sxs-lookup"><span data-stu-id="590a9-266">Review transferred data, including country\region of destination/dispatch, country of origin, weight, quantity, quantity in additional units, commodity, transaction code, invoice amounts and statistical amounts.</span></span>   <span data-ttu-id="590a9-267">W razie potrzeby można zmodyfikować te dane.</span><span class="sxs-lookup"><span data-stu-id="590a9-267">You can modify data if necessary.</span></span>  

