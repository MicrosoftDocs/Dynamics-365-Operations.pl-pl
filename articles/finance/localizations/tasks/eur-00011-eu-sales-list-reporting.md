---
title: EUR-00011 Konfigurowanie unijnego raportu listy sprzedaży
description: To zadanie prowadzi przez omówienie warunków wstępnych wymaganych na potrzeby raportowania listy sprzedaży do UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0ce458697fd61aabddcbf844dd0b2afbe3aa1c0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228015"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a><span data-ttu-id="39f58-103">EUR-00011 Konfigurowanie unijnego raportu listy sprzedaży</span><span class="sxs-lookup"><span data-stu-id="39f58-103">EUR-00011 Set up EU sales list reporting</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="39f58-104">To zadanie prowadzi przez omówienie warunków wstępnych wymaganych na potrzeby raportowania listy sprzedaży do UE.</span><span class="sxs-lookup"><span data-stu-id="39f58-104">This task walks you through an overview of the prerequisites required for EU sales list reporting.</span></span> <span data-ttu-id="39f58-105">Aby uzyskać więcej informacji na temat raportowania list sprzedaży do UE, w tym o wymaganiach wstępnych, zobacz Pomoc.</span><span class="sxs-lookup"><span data-stu-id="39f58-105">For more information about EU Sales list reporting, including required prerequisites, refer to Help.</span></span>

<span data-ttu-id="39f58-106">To zadanie dotyczy wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="39f58-106">This task applies to all European countries/regions.</span></span> <span data-ttu-id="39f58-107">Przewodnik został utworzony przy użyciu danych firmy demonstracyjnej DEMF i w związku z tym Niemiec jako przykładowego lokalnego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="39f58-107">The guide was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="39f58-108">W przewodniku jest również używana Portugalia jako przykładowy kraj/region UE.</span><span class="sxs-lookup"><span data-stu-id="39f58-108">The guide also uses Portugal as an exemplar EU country/region.</span></span>

<span data-ttu-id="39f58-109">Te zadania są przeznaczone dla administratorów systemu.</span><span class="sxs-lookup"><span data-stu-id="39f58-109">These tasks are intended for system administrators.</span></span>


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a><span data-ttu-id="39f58-110">Importowanie konfiguracji raportowania elektronicznego na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="39f58-110">Import electronic reporting configurations for EU sales list reporting</span></span>
1. <span data-ttu-id="39f58-111">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39f58-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="39f58-112">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="39f58-112">Click Set active.</span></span>
3. <span data-ttu-id="39f58-113">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="39f58-113">Click Repositories.</span></span>
4. <span data-ttu-id="39f58-114">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="39f58-114">Click Open.</span></span>
5. <span data-ttu-id="39f58-115">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="39f58-115">On the Action Pane, click Options.</span></span>
6. <span data-ttu-id="39f58-116">Kliknij opcję Filtr/sortowanie zaawansowane.</span><span class="sxs-lookup"><span data-stu-id="39f58-116">Click Advanced Filter/Sort.</span></span>
7. <span data-ttu-id="39f58-117">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="39f58-117">Click Add.</span></span>
8. <span data-ttu-id="39f58-118">W polu Pole wybierz opcję „Nazwa konfiguracji”.</span><span class="sxs-lookup"><span data-stu-id="39f58-118">In the Field field, select 'Configuration name'.</span></span>
9. <span data-ttu-id="39f58-119">W polu Kryteria wpisz „Lista sprzedaży do UE (DE)”.</span><span class="sxs-lookup"><span data-stu-id="39f58-119">In the Criteria field, type 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="39f58-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="39f58-120">Click OK.</span></span>
11. <span data-ttu-id="39f58-121">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="39f58-121">Click Import.</span></span>
12. <span data-ttu-id="39f58-122">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="39f58-122">Click Yes.</span></span>
13. <span data-ttu-id="39f58-123">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="39f58-123">On the Action Pane, click Options.</span></span>
14. <span data-ttu-id="39f58-124">Kliknij opcję Filtr/sortowanie zaawansowane.</span><span class="sxs-lookup"><span data-stu-id="39f58-124">Click Advanced Filter/Sort.</span></span>
15. <span data-ttu-id="39f58-125">Kliknij pozycję Resetuj.</span><span class="sxs-lookup"><span data-stu-id="39f58-125">Click Reset.</span></span>
16. <span data-ttu-id="39f58-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="39f58-126">Click Add.</span></span>
17. <span data-ttu-id="39f58-127">W polu Pole wybierz opcję „Nazwa konfiguracji”.</span><span class="sxs-lookup"><span data-stu-id="39f58-127">In the Field field, select 'Configuration name'.</span></span>
18. <span data-ttu-id="39f58-128">W polu Kryteria wpisz „Raport o liście sprzedaży do UE z podziałem na wiersze”.</span><span class="sxs-lookup"><span data-stu-id="39f58-128">In the Criteria field, type 'EU Sales list by rows report'.</span></span>
19. <span data-ttu-id="39f58-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="39f58-129">Click OK.</span></span>
20. <span data-ttu-id="39f58-130">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="39f58-130">Click Import.</span></span>
21. <span data-ttu-id="39f58-131">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="39f58-131">Click Yes.</span></span>

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a><span data-ttu-id="39f58-132">Konfigurowanie kodów podatków na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="39f58-132">Set up sales tax codes for EU sales list reporting</span></span>
1. <span data-ttu-id="39f58-133">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Kody podatków.</span><span class="sxs-lookup"><span data-stu-id="39f58-133">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="39f58-134">Użyj szybkiego filtru, aby wyfiltrować pole Kod podatku według wartości „VAT19”.</span><span class="sxs-lookup"><span data-stu-id="39f58-134">Use the Quick Filter to filter on the Sales tax code field with a value of 'VAT19'.</span></span>
3. <span data-ttu-id="39f58-135">Rozwiń sekcję Konfiguracja raportu.</span><span class="sxs-lookup"><span data-stu-id="39f58-135">Expand the Report setup section.</span></span>
    * <span data-ttu-id="39f58-136">Upewnij się, że opcja Wykluczone ma ustawioną wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="39f58-136">Verify that the Excluded selection is set to No.</span></span>  
    * <span data-ttu-id="39f58-137">W celu zmiany tego ustawienia może być konieczne odblokowanie zadań w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="39f58-137">You may need to unlock the task guide to change this setting.</span></span>  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="39f58-138">Konfigurowanie grup podatków na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="39f58-138">Set up sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="39f58-139">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="39f58-139">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="39f58-140">Użyj szybkiego filtru, aby wyfiltrować pole Grupa podatków według wartości „AR-DOM”.</span><span class="sxs-lookup"><span data-stu-id="39f58-140">Use the Quick Filter to filter on the Sales tax group field with a value of 'AR-DOM'.</span></span>
3. <span data-ttu-id="39f58-141">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="39f58-141">Click Edit.</span></span>
4. <span data-ttu-id="39f58-142">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="39f58-142">Expand the Setup section.</span></span>
5. <span data-ttu-id="39f58-143">Na liście zaznacz pierwszy wiersz.</span><span class="sxs-lookup"><span data-stu-id="39f58-143">In the list, select the first row.</span></span>
6. <span data-ttu-id="39f58-144">Zaznacz pole wyboru Zwolnienie.</span><span class="sxs-lookup"><span data-stu-id="39f58-144">Select the Exempt check box.</span></span>
7. <span data-ttu-id="39f58-145">Na liście zaznacz drugi wiersz.</span><span class="sxs-lookup"><span data-stu-id="39f58-145">In the list, select the second row.</span></span>
8. <span data-ttu-id="39f58-146">Zaznacz pole wyboru Zwolnienie.</span><span class="sxs-lookup"><span data-stu-id="39f58-146">Select the Exempt check box.</span></span>
9. <span data-ttu-id="39f58-147">Na liście zaznacz trzeci wiersz.</span><span class="sxs-lookup"><span data-stu-id="39f58-147">In the list, select the third row.</span></span>
10. <span data-ttu-id="39f58-148">Zaznacz pole wyboru Zwolnienie.</span><span class="sxs-lookup"><span data-stu-id="39f58-148">Select the Exempt check box.</span></span>

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="39f58-149">Konfigurowanie grup podatków dla towarów na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="39f58-149">Set up item sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="39f58-150">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków dla towaru.</span><span class="sxs-lookup"><span data-stu-id="39f58-150">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
2. <span data-ttu-id="39f58-151">Użyj szybkiego filtru, aby wyfiltrować pole Grupa podatków dla towaru według wartości „PEŁNE”.</span><span class="sxs-lookup"><span data-stu-id="39f58-151">Use the Quick Filter to filter on the Item sales tax group field with a value of 'FULL '.</span></span>
    * <span data-ttu-id="39f58-152">Upewnij się, że opcja Typ raportowania ma ustawioną wartość „Towar”.</span><span class="sxs-lookup"><span data-stu-id="39f58-152">Verify that the Reporting type selection is set to 'Item'.</span></span>  
    * <span data-ttu-id="39f58-153">W celu zmiany wartości tego pola może być konieczne odblokowanie zadań w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="39f58-153">You may need to unlock the task guide to change the value in this field.</span></span>  
3. <span data-ttu-id="39f58-154">Użyj szybkiego filtru, aby wyfiltrować pole Grupa podatków dla towaru według wartości „CZERWONE”.</span><span class="sxs-lookup"><span data-stu-id="39f58-154">Use the Quick Filter to filter on the Item sales tax group field with a value of 'RED '.</span></span>
    * <span data-ttu-id="39f58-155">Upewnij się, że opcja Typ raportowania ma ustawioną wartość „Usługa”.</span><span class="sxs-lookup"><span data-stu-id="39f58-155">Verify that the Reporting type selection is set to 'Service'.</span></span>  
    * <span data-ttu-id="39f58-156">W celu zmiany wartości tego pola może być konieczne odblokowanie zadań w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="39f58-156">You may need to unlock the task guide to change the value in this field.</span></span>  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a><span data-ttu-id="39f58-157">Konfigurowanie parametrów kraju/regionu na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="39f58-157">Set up country/region parameters for EU sales list reporting</span></span>
1. <span data-ttu-id="39f58-158">Wybierz kolejno opcje Podatek > Ustawienia > Podatek > Parametry kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="39f58-158">Go to Tax > Setup > Sales tax > Country/region parameters.</span></span>
2. <span data-ttu-id="39f58-159">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="39f58-159">Click New.</span></span>
3. <span data-ttu-id="39f58-160">W polu Kraj/region wpisz „PRT”.</span><span class="sxs-lookup"><span data-stu-id="39f58-160">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="39f58-161">W polu Podatek wpisz „PT”.</span><span class="sxs-lookup"><span data-stu-id="39f58-161">In the Sales tax field, type 'PT'.</span></span>

## <a name="create-tax-exempt-numbers"></a><span data-ttu-id="39f58-162">Tworzenie numerów identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="39f58-162">Create tax exempt numbers</span></span>
1. <span data-ttu-id="39f58-163">Wybierz kolejno opcje Podatek > Ustawienia > Podatek > Numery identyfikacji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="39f58-163">Go to Tax > Setup > Sales tax > Tax exempt numbers.</span></span>
2. <span data-ttu-id="39f58-164">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="39f58-164">Click New.</span></span>
3. <span data-ttu-id="39f58-165">W polu Kraj/region wpisz „PRT”.</span><span class="sxs-lookup"><span data-stu-id="39f58-165">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="39f58-166">W polu Numer identyfikacji podatkowej wpisz „PT12345”.</span><span class="sxs-lookup"><span data-stu-id="39f58-166">In the Tax exempt number field, type 'PT12345'.</span></span>

## <a name="set-up-eu-sales-list-reporting-parameters"></a><span data-ttu-id="39f58-167">Konfigurowanie parametrów raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="39f58-167">Set up EU sales list reporting parameters</span></span>
1. <span data-ttu-id="39f58-168">Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="39f58-168">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="39f58-169">Kliknij kartę Lista sprzedaży do UE.</span><span class="sxs-lookup"><span data-stu-id="39f58-169">Click the EU sales list tab.</span></span>
3. <span data-ttu-id="39f58-170">W polu Przenieś zakupy wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="39f58-170">Select Yes in the Transfer purchases field.</span></span>
4. <span data-ttu-id="39f58-171">Rozwiń sekcję Reguły zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="39f58-171">Expand the Rounding rules section.</span></span>
5. <span data-ttu-id="39f58-172">W polu Reguła zaokrąglania wpisz „0,1”.</span><span class="sxs-lookup"><span data-stu-id="39f58-172">Set Rounding rule to '0.1'.</span></span>
6. <span data-ttu-id="39f58-173">W polu Użyj wartości minimalnej zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="39f58-173">Select Yes in the Use minimum value field.</span></span>
7. <span data-ttu-id="39f58-174">W polu Liczba cyfr dziesiętnych wpisz wartość „2”.</span><span class="sxs-lookup"><span data-stu-id="39f58-174">In the Number of decimals field, enter '2'.</span></span>
8. <span data-ttu-id="39f58-175">Rozwiń sekcję Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="39f58-175">Expand the Electronic reporting section.</span></span>
9. <span data-ttu-id="39f58-176">W polu Mapowanie formatu plików wybierz opcję „Lista sprzedaży do UE (DE)”.</span><span class="sxs-lookup"><span data-stu-id="39f58-176">In the File format mapping field, select 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="39f58-177">W polu Mapowanie formatu raportów wybierz opcję „Raport o liście sprzedaży do UE z podziałem na wiersze”.</span><span class="sxs-lookup"><span data-stu-id="39f58-177">In the Report format mapping field, select 'EU Sales list by rows report'.</span></span>
11. <span data-ttu-id="39f58-178">Kliknij kartę Właściwości kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="39f58-178">Click the Country/region properties tab.</span></span>
    * <span data-ttu-id="39f58-179">Upewnij się, że dla kraju/regionu DEU pole Typ kraju/regionu ma ustawioną wartość „Krajowy”.</span><span class="sxs-lookup"><span data-stu-id="39f58-179">Verify that the Country/region type field is set to 'Domestic' for Country/region DEU.</span></span>  
    * <span data-ttu-id="39f58-180">W celu zmiany wartości tego pola może być konieczne odblokowanie zadań w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="39f58-180">You may need to unlock the task guide to change the value in this field.</span></span>  
12. <span data-ttu-id="39f58-181">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="39f58-181">Click New.</span></span>
13. <span data-ttu-id="39f58-182">W polu Kraj/region wpisz „PRT”.</span><span class="sxs-lookup"><span data-stu-id="39f58-182">In the Country/region field, type 'PRT'.</span></span>
14. <span data-ttu-id="39f58-183">W polu Kod Intrastat wpisz „PT”.</span><span class="sxs-lookup"><span data-stu-id="39f58-183">In the Intrastat code field, type 'PT'.</span></span>
15. <span data-ttu-id="39f58-184">W polu Typ kraju/regionu wybierz opcję „UE”.</span><span class="sxs-lookup"><span data-stu-id="39f58-184">In the Country/region type field, select 'EU'.</span></span>
16. <span data-ttu-id="39f58-185">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="39f58-185">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="39f58-186">Upewnij się, że kod sekwencji numerów jest określony dla odwołania „Lista sprzedaży do UE”.</span><span class="sxs-lookup"><span data-stu-id="39f58-186">Verify that a Number sequence code is specified for the Reference 'EU sales list'.</span></span>  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a><span data-ttu-id="39f58-187">Tworzenie odbiorcy do celów demonstracji raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="39f58-187">Create a customer for EU sales list reporting demo purposes</span></span>
1. <span data-ttu-id="39f58-188">Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="39f58-188">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="39f58-189">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="39f58-189">Click New.</span></span>
3. <span data-ttu-id="39f58-190">W polu Konto odbiorcy wpisz „PRT-001”.</span><span class="sxs-lookup"><span data-stu-id="39f58-190">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="39f58-191">W polu Nazwa wpisz „Odbiorca z Portugalii”.</span><span class="sxs-lookup"><span data-stu-id="39f58-191">In the Name field, type 'A customer from Portugal'.</span></span>
5. <span data-ttu-id="39f58-192">W polu Grupa odbiorców wybierz opcję „10”.</span><span class="sxs-lookup"><span data-stu-id="39f58-192">In the Customer group field, select '10'.</span></span>
6. <span data-ttu-id="39f58-193">W polu Grupa podatków wybierz opcję „AR-DOM”.</span><span class="sxs-lookup"><span data-stu-id="39f58-193">In the Sales tax group field, select 'AR-DOM'.</span></span>
7. <span data-ttu-id="39f58-194">W polu Numer identyfikacji podatkowej wybierz opcję „PT12345”.</span><span class="sxs-lookup"><span data-stu-id="39f58-194">In the Tax exempt number field, select 'PT12345'.</span></span>
8. <span data-ttu-id="39f58-195">W polu Kraj/region wpisz „PRT”.</span><span class="sxs-lookup"><span data-stu-id="39f58-195">In the Country/region field, type 'PRT'.</span></span>
9. <span data-ttu-id="39f58-196">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="39f58-196">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]