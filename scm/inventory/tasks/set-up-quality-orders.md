---
title: "Konfigurowanie zleceń kontroli jakości"
description: "W tej procedurze pokazano sposób włączania procesu zarządzania jakością, gdzie zapasy przychodzące muszą być kontrolowane bezpośrednio po rejestracji przyjęcia."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 73981313fc662094ee4f8bb15a88271e16d41193
ms.contentlocale: pl-pl
ms.lasthandoff: 09/12/2017

---
# <a name="set-up-quality-orders"></a><span data-ttu-id="dbafd-103">Konfigurowanie zleceń kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="dbafd-103">Set up quality orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dbafd-104">W tej procedurze pokazano sposób włączania procesu zarządzania jakością, gdzie zapasy przychodzące muszą być kontrolowane bezpośrednio po rejestracji przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="dbafd-104">This procedure shows you how to enable a quality management process where incoming inventory must be inspected immediately after arrival registration.</span></span> <span data-ttu-id="dbafd-105">Procedurę zazwyczaj przeprowadza menedżer ds. kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="dbafd-105">The procedure will typically be carried out by a quality manager.</span></span> <span data-ttu-id="dbafd-106">Proces obejmuje utworzenie grupy kontroli jakości, zdefiniowanie towarów, z których mają być pobierane próbki, oraz utworzenie grupy testów, które mają być wykonywane na towarach w grupie kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="dbafd-106">The process includes the creation of a quality group, to define the items that are going to be sampled, and a test group to group the tests that are to be performed on items in the quality group.</span></span> <span data-ttu-id="dbafd-107">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="dbafd-107">You can run this guide in the USMF demo data company.</span></span>


## <a name="enable-quality-management"></a><span data-ttu-id="dbafd-108">Włączanie zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="dbafd-108">Enable quality management</span></span>
1. <span data-ttu-id="dbafd-109">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem.</span><span class="sxs-lookup"><span data-stu-id="dbafd-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="dbafd-110">Kliknij kartę Zarządzanie jakością.</span><span class="sxs-lookup"><span data-stu-id="dbafd-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="dbafd-111">W opcji Korzystaj z funkcji zarządzania jakością wybierz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="dbafd-111">Set the Use quality management option to Yes.</span></span>
4. <span data-ttu-id="dbafd-112">Kliknij opcję Konfiguracja raportu.</span><span class="sxs-lookup"><span data-stu-id="dbafd-112">Click Report setup.</span></span>
    * <span data-ttu-id="dbafd-113">W firmie USMF konfiguracja raportu dotyczącego zarządzania jakością jest już zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="dbafd-113">In USMF, the report setup for quality management is already defined.</span></span> <span data-ttu-id="dbafd-114">Jeśli tego nie zrobiono, musisz w tym miejscu dodać nowe wiersze dla różnych typów raportów, a następnie wybrać typ dokumentu, który ma być używany dla każdego raportu.</span><span class="sxs-lookup"><span data-stu-id="dbafd-114">If this wasn’t done, you’d add new lines here for the different report types, and select the type of document to be used for each report.</span></span>  
5. <span data-ttu-id="dbafd-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-115">Close the page.</span></span>
6. <span data-ttu-id="dbafd-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-116">Close the page.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="dbafd-117">Tworzenie testu</span><span class="sxs-lookup"><span data-stu-id="dbafd-117">Create a test</span></span>
1. <span data-ttu-id="dbafd-118">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Kontrola jakości > Testy.</span><span class="sxs-lookup"><span data-stu-id="dbafd-118">Go to Inventory management > Setup > Quality control > Tests.</span></span>
2. <span data-ttu-id="dbafd-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dbafd-119">Click New.</span></span>
3. <span data-ttu-id="dbafd-120">W polu Test wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbafd-120">In the Test field, type a value.</span></span>
4. <span data-ttu-id="dbafd-121">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="dbafd-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="dbafd-122">W polu Typ wpisz „Opcja”.</span><span class="sxs-lookup"><span data-stu-id="dbafd-122">In the Type field, select 'Option'.</span></span>
    * <span data-ttu-id="dbafd-123">W tym przykładzie wybierzemy opcję „Opcja”, co umożliwi przypisywanie wyników testów na podstawie wstępnie zdefiniowanych wartości.</span><span class="sxs-lookup"><span data-stu-id="dbafd-123">In this example, we'll select "Option" which will make it possible to assign the test results based on pre-defined values.</span></span>  
6. <span data-ttu-id="dbafd-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dbafd-124">Click Save.</span></span>
7. <span data-ttu-id="dbafd-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-125">Close the page.</span></span>

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a><span data-ttu-id="dbafd-126">Tworzenie zmiennych testowych w celu zdefiniowania sposobu rejestrowania wyników testów</span><span class="sxs-lookup"><span data-stu-id="dbafd-126">Create Test variables to define the way test results are recorded</span></span>
1. <span data-ttu-id="dbafd-127">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Kontrola jakości > Zmienne testowe.</span><span class="sxs-lookup"><span data-stu-id="dbafd-127">Go to Inventory management > Setup > Quality control > Test variables.</span></span>
2. <span data-ttu-id="dbafd-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dbafd-128">Click New.</span></span>
3. <span data-ttu-id="dbafd-129">W polu Zmienna wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbafd-129">In the Variable field, type a value.</span></span>
4. <span data-ttu-id="dbafd-130">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="dbafd-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="dbafd-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dbafd-131">Click Save.</span></span>
6. <span data-ttu-id="dbafd-132">Kliknij opcję Wyniki.</span><span class="sxs-lookup"><span data-stu-id="dbafd-132">Click Outcomes.</span></span>
7. <span data-ttu-id="dbafd-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dbafd-133">Click New.</span></span>
8. <span data-ttu-id="dbafd-134">W polu Wynik wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbafd-134">In the Outcome field, type a value.</span></span>
9. <span data-ttu-id="dbafd-135">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="dbafd-135">In the Description field, type a value.</span></span>
10. <span data-ttu-id="dbafd-136">W polu Stan wyniku wybierz opcję „Sukces”.</span><span class="sxs-lookup"><span data-stu-id="dbafd-136">In the Outcome status field, select 'Pass'.</span></span>
11. <span data-ttu-id="dbafd-137">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dbafd-137">Click Save.</span></span>
12. <span data-ttu-id="dbafd-138">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dbafd-138">Click New.</span></span>
13. <span data-ttu-id="dbafd-139">W polu Wynik wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbafd-139">In the Outcome field, type a value.</span></span>
14. <span data-ttu-id="dbafd-140">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="dbafd-140">In the Description field, type a value.</span></span>
15. <span data-ttu-id="dbafd-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dbafd-141">Click Save.</span></span>
16. <span data-ttu-id="dbafd-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-142">Close the page.</span></span>
17. <span data-ttu-id="dbafd-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-143">Close the page.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="dbafd-144">Konfigurowanie wyrywkowej kontroli towarów</span><span class="sxs-lookup"><span data-stu-id="dbafd-144">Set up item sampling</span></span>
1. <span data-ttu-id="dbafd-145">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Kontrola jakości > Kontrola wyrywkowa pozycji.</span><span class="sxs-lookup"><span data-stu-id="dbafd-145">Go to Inventory management > Setup > Quality control > Item sampling.</span></span>
2. <span data-ttu-id="dbafd-146">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dbafd-146">Click New.</span></span>
3. <span data-ttu-id="dbafd-147">W polu Kontrola wyrywkowa towarów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbafd-147">In the Item sampling field, type a value.</span></span>
4. <span data-ttu-id="dbafd-148">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="dbafd-148">In the Description field, type a value.</span></span>
5. <span data-ttu-id="dbafd-149">W polu Wartość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-149">In the Value field, enter a number.</span></span>
    * <span data-ttu-id="dbafd-150">Ta wartość odnosi się do specyfikacji ilości wybranej w sąsiednim polu.</span><span class="sxs-lookup"><span data-stu-id="dbafd-150">This value relates to the Quantity specification that’s selected in the adjacent field.</span></span>  
6. <span data-ttu-id="dbafd-151">Rozwiń lub zwiń sekcję Proces.</span><span class="sxs-lookup"><span data-stu-id="dbafd-151">Expand or collapse the Process section.</span></span>
7. <span data-ttu-id="dbafd-152">Zaznacz lub wyczyść pole wyboru Pełne blokowanie.</span><span class="sxs-lookup"><span data-stu-id="dbafd-152">Select or clear the Full blocking check box.</span></span>
    * <span data-ttu-id="dbafd-153">Jeśli wybierzesz tę opcję, niepowodzenie testu spowoduje zablokowanie całej partii lub ilości w wierszu zamówienia.</span><span class="sxs-lookup"><span data-stu-id="dbafd-153">If you select this option, the whole lot or order line quantity is blocked if a test is failed.</span></span> <span data-ttu-id="dbafd-154">Jeśli nie zaznaczysz opcji, będą blokowane tylko towary w zleceniu kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="dbafd-154">If you don't select it, only the items in the quality order are blocked.</span></span>  
8. <span data-ttu-id="dbafd-155">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dbafd-155">Click Save.</span></span>
9. <span data-ttu-id="dbafd-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-156">Close the page.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="dbafd-157">Tworzenie grupy kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="dbafd-157">Create a quality group</span></span>
1. <span data-ttu-id="dbafd-158">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Kontrola jakości > Grupy jakości.</span><span class="sxs-lookup"><span data-stu-id="dbafd-158">Go to Inventory management > Setup > Quality control > Quality groups.</span></span>
2. <span data-ttu-id="dbafd-159">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dbafd-159">Click New.</span></span>
3. <span data-ttu-id="dbafd-160">W polu Grupa jakości wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbafd-160">In the Quality group field, type a value.</span></span>
    * <span data-ttu-id="dbafd-161">Użyj nazwy opisowej, aby łatwiej identyfikować, które rodzaje towarów będzie zawierać grupa (tzn. jakich użyto kryteriów pobierania próbek).</span><span class="sxs-lookup"><span data-stu-id="dbafd-161">Use a descriptive name to help you identify which kind of items the group will contain (your sampling criteria).</span></span>  
4. <span data-ttu-id="dbafd-162">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="dbafd-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="dbafd-163">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dbafd-163">Click Save.</span></span>
6. <span data-ttu-id="dbafd-164">Kliknij przycisk Dodaj towary.</span><span class="sxs-lookup"><span data-stu-id="dbafd-164">Click Add items.</span></span>
7. <span data-ttu-id="dbafd-165">Zaznacz wiersz Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="dbafd-165">Select the Item number row</span></span>
    * <span data-ttu-id="dbafd-166">W tym przykładzie filtrowanie będzie wykonywane na podstawie kodu towaru.</span><span class="sxs-lookup"><span data-stu-id="dbafd-166">In this example the filtering will be run based on  the item number.</span></span>  
8. <span data-ttu-id="dbafd-167">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbafd-167">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="dbafd-168">Na przykład wpisz T*, aby filtrować według kodów towarów rozpoczynających się literą T.</span><span class="sxs-lookup"><span data-stu-id="dbafd-168">For example, type T* to filter on the item numbers that start with T.</span></span>  
9. <span data-ttu-id="dbafd-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dbafd-169">Click OK.</span></span>
10. <span data-ttu-id="dbafd-170">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="dbafd-170">Click OK.</span></span>
11. <span data-ttu-id="dbafd-171">Kliknij opcję Grupy jakości towarów.</span><span class="sxs-lookup"><span data-stu-id="dbafd-171">Click Item quality groups.</span></span>
12. <span data-ttu-id="dbafd-172">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-172">Close the page.</span></span>
13. <span data-ttu-id="dbafd-173">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-173">Close the page.</span></span>

## <a name="create-a-test-group"></a><span data-ttu-id="dbafd-174">Tworzenie grupy testowej</span><span class="sxs-lookup"><span data-stu-id="dbafd-174">Create a test group</span></span>
1. <span data-ttu-id="dbafd-175">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Kontrola jakości > Grupy testowe.</span><span class="sxs-lookup"><span data-stu-id="dbafd-175">Go to Inventory management > Setup > Quality control > Test groups.</span></span>
2. <span data-ttu-id="dbafd-176">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dbafd-176">Click New.</span></span>
3. <span data-ttu-id="dbafd-177">W polu Grupa testowa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbafd-177">In the Test group field, type a value.</span></span>
    * <span data-ttu-id="dbafd-178">Nadaj grupie testowej nazwę, która pomoże Ci zapamiętać, jakiego rodzaju testy były wykonywane i z którą grupą kontroli jakości powinny być skojarzone.</span><span class="sxs-lookup"><span data-stu-id="dbafd-178">Give the Test group a name that will help you remember what kind of tests are being run, and which quality group it should be associated with.</span></span> <span data-ttu-id="dbafd-179">Jeśli na przykład grupa ma być używana do testów jakości na towarach o nazwach zaczynających się literą „T”, można nazwać grupę „Testy towarów na T”.</span><span class="sxs-lookup"><span data-stu-id="dbafd-179">For example, it it’s to be used with a quality group that selects items starting with “T”, you could call it “T-item tests”.</span></span>  
4. <span data-ttu-id="dbafd-180">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="dbafd-180">In the Description field, type a value.</span></span>
5. <span data-ttu-id="dbafd-181">W polu Kontrola wyrywkowa towarów zaznacz utworzony wcześniej wiersz pobierania próbek.</span><span class="sxs-lookup"><span data-stu-id="dbafd-181">In the Item sampling field, select the item sampling line that you created before.</span></span>
6. <span data-ttu-id="dbafd-182">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="dbafd-182">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="dbafd-183">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dbafd-183">Click Add.</span></span>
8. <span data-ttu-id="dbafd-184">W polu Numer sekwencyjny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-184">In the Sequence number field, enter a number.</span></span>
9. <span data-ttu-id="dbafd-185">W polu Test zaznacz utworzony wcześniej test.</span><span class="sxs-lookup"><span data-stu-id="dbafd-185">In the Test field, select the test that you created earlier.</span></span>
10. <span data-ttu-id="dbafd-186">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="dbafd-186">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="dbafd-187">Kliknij kartę Test.</span><span class="sxs-lookup"><span data-stu-id="dbafd-187">Click the Test tab.</span></span>
12. <span data-ttu-id="dbafd-188">W polu Zmienna zaznacz utworzoną wcześniej zmienną.</span><span class="sxs-lookup"><span data-stu-id="dbafd-188">In the Variable field, select the test variable that you created before</span></span>
13. <span data-ttu-id="dbafd-189">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="dbafd-189">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="dbafd-190">W polu Wynik domyślny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="dbafd-190">In the Default outcome field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="dbafd-191">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="dbafd-191">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="dbafd-192">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dbafd-192">Click Save.</span></span>
17. <span data-ttu-id="dbafd-193">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-193">Close the page.</span></span>

## <a name="define-when-quality-orders-will-be-created"></a><span data-ttu-id="dbafd-194">Określanie warunków tworzenia zleceń kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="dbafd-194">Define when quality orders will be created</span></span>
1. <span data-ttu-id="dbafd-195">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Kontrola jakości > Skojarzenia jakości.</span><span class="sxs-lookup"><span data-stu-id="dbafd-195">Go to Inventory management > Setup > Quality control > Quality associations.</span></span>
2. <span data-ttu-id="dbafd-196">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="dbafd-196">Click New.</span></span>
3. <span data-ttu-id="dbafd-197">W polu Typ odwołania wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="dbafd-197">In the Reference type field, select an option.</span></span>
4. <span data-ttu-id="dbafd-198">W polu Kod towaru zaznacz opcję „Grupa”.</span><span class="sxs-lookup"><span data-stu-id="dbafd-198">In the Item code field, select 'Group'.</span></span>
    * <span data-ttu-id="dbafd-199">W tym przykładzie wybierzemy opcję „Grupa” i użyjemy grupy kontroli jakości utworzonej wcześniej.</span><span class="sxs-lookup"><span data-stu-id="dbafd-199">In this example, we’ll select "Group" and use the quality group we created before.</span></span> <span data-ttu-id="dbafd-200">Można także zaznaczyć wartość „Tabela”, aby określić towary ręcznie, lub opcję „Wszystko”, aby dodać wszystkie towary do zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="dbafd-200">You could also set this to "Table" to specify the items manually, or select "All" to add all items to the quality order.</span></span>  
5. <span data-ttu-id="dbafd-201">W polu Towar wybierz utworzoną wcześniej grupę towarów.</span><span class="sxs-lookup"><span data-stu-id="dbafd-201">In the Item field, select the quality group that you created before.</span></span>
    * <span data-ttu-id="dbafd-202">Opcje dostępne w polu Towar zależą od ustawienia w polu Kod towaru.</span><span class="sxs-lookup"><span data-stu-id="dbafd-202">The options available in the Item field depend on what you set in the Item code field.</span></span>  
6. <span data-ttu-id="dbafd-203">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="dbafd-203">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="dbafd-204">Rozwiń lub zwiń sekcję Proces.</span><span class="sxs-lookup"><span data-stu-id="dbafd-204">Expand or collapse the Process section.</span></span>
8. <span data-ttu-id="dbafd-205">W polu Typ zdarzenia wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="dbafd-205">In the Event type field, select an option.</span></span>
    * <span data-ttu-id="dbafd-206">Jest to zdarzenie wyzwalające test.</span><span class="sxs-lookup"><span data-stu-id="dbafd-206">This is the event that triggers the test.</span></span> <span data-ttu-id="dbafd-207">Dostępne opcje zależą od procesu, który wybrano w polu Typ odwołania.</span><span class="sxs-lookup"><span data-stu-id="dbafd-207">The options available here depend on which process you selected in the Reference type field.</span></span>  
9. <span data-ttu-id="dbafd-208">W polu Wykonanie wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="dbafd-208">In the Execution field, select an option.</span></span>
10. <span data-ttu-id="dbafd-209">Rozwiń lub zwiń sekcję Przetwarzanie zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="dbafd-209">Expand or collapse the Quality order process section.</span></span>
11. <span data-ttu-id="dbafd-210">W polu Blokowanie zdarzeń kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="dbafd-210">In the Event blocking field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="dbafd-211">To pole zawiera listę procesów, które można zablokować, jeśli zlecenie kontroli jakości jest nadal otwarte.</span><span class="sxs-lookup"><span data-stu-id="dbafd-211">This field shows the list of processes that it’s possible to block if the quality order is still open.</span></span> <span data-ttu-id="dbafd-212">Dostępne opcje zależą od tego, co wybrano w polu Typ zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="dbafd-212">The options depend on what you selected in the Event type field.</span></span>  
12. <span data-ttu-id="dbafd-213">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="dbafd-213">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="dbafd-214">Będzie to zależało od poprzednio wybranych wartości.</span><span class="sxs-lookup"><span data-stu-id="dbafd-214">This will be depending on the previous selected values.</span></span> <span data-ttu-id="dbafd-215">Zaznacz tę opcję, jeśli następujące procesy mają być zablokowane przy jednoczesnym zachowaniu powiązania otwartych zleceń kontroli jakości z wierszem dokumentu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="dbafd-215">Select if the following processes must be blocked while having open quality orders linked to a source document line.</span></span>  
13. <span data-ttu-id="dbafd-216">Rozwiń lub zwiń sekcję Specyfikacje.</span><span class="sxs-lookup"><span data-stu-id="dbafd-216">Expand or collapse the Specifications section.</span></span>
14. <span data-ttu-id="dbafd-217">W polu Grupa testowa zaznacz utworzoną wcześniej grupę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-217">In the Test group field, select the test group that you created before.</span></span>
15. <span data-ttu-id="dbafd-218">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="dbafd-218">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="dbafd-219">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dbafd-219">Click Save.</span></span>
17. <span data-ttu-id="dbafd-220">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dbafd-220">Close the page.</span></span>

