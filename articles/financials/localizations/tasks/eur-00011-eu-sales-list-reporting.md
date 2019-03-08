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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aef1d19aabb7937fcd961a9657b8ca65c064b0b1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "371447"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a><span data-ttu-id="79a54-103">EUR-00011 Konfigurowanie unijnego raportu listy sprzedaży</span><span class="sxs-lookup"><span data-stu-id="79a54-103">EUR-00011 Set up EU sales list reporting</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="79a54-104">To zadanie prowadzi przez omówienie warunków wstępnych wymaganych na potrzeby raportowania listy sprzedaży do UE.</span><span class="sxs-lookup"><span data-stu-id="79a54-104">This task walks you through an overview of the prerequisites required for EU sales list reporting.</span></span> <span data-ttu-id="79a54-105">Aby uzyskać więcej informacji na temat raportowania list sprzedaży do UE, w tym o wymaganiach wstępnych, zobacz Pomoc programu Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79a54-105">For more information about EU Sales list reporting, including required prerequisites, refer to the Dynamics 365 for Finance and Operations Help.</span></span>

<span data-ttu-id="79a54-106">To zadanie dotyczy wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="79a54-106">This task applies to all European countries/regions.</span></span> <span data-ttu-id="79a54-107">Przewodnik został utworzony przy użyciu danych firmy demonstracyjnej DEMF i w związku z tym Niemiec jako przykładowego lokalnego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="79a54-107">The guide was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="79a54-108">W przewodniku jest również używana Portugalia jako przykładowy kraj/region UE.</span><span class="sxs-lookup"><span data-stu-id="79a54-108">The guide also uses Portugal as an exemplar EU country/region.</span></span>

<span data-ttu-id="79a54-109">Te zadania są przeznaczone dla administratorów systemu.</span><span class="sxs-lookup"><span data-stu-id="79a54-109">These tasks are intended for system administrators.</span></span>


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a><span data-ttu-id="79a54-110">Importowanie konfiguracji raportowania elektronicznego na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="79a54-110">Import electronic reporting configurations for EU sales list reporting</span></span>
1. <span data-ttu-id="79a54-111">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="79a54-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="79a54-112">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="79a54-112">Click Set active.</span></span>
3. <span data-ttu-id="79a54-113">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="79a54-113">Click Repositories.</span></span>
4. <span data-ttu-id="79a54-114">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="79a54-114">Click Open.</span></span>
5. <span data-ttu-id="79a54-115">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="79a54-115">On the Action Pane, click Options.</span></span>
6. <span data-ttu-id="79a54-116">Kliknij opcję Filtr/sortowanie zaawansowane.</span><span class="sxs-lookup"><span data-stu-id="79a54-116">Click Advanced Filter/Sort.</span></span>
7. <span data-ttu-id="79a54-117">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="79a54-117">Click Add.</span></span>
8. <span data-ttu-id="79a54-118">W polu Pole wybierz opcję „Nazwa konfiguracji”.</span><span class="sxs-lookup"><span data-stu-id="79a54-118">In the Field field, select 'Configuration name'.</span></span>
9. <span data-ttu-id="79a54-119">W polu Kryteria wpisz „Lista sprzedaży do UE (DE)”.</span><span class="sxs-lookup"><span data-stu-id="79a54-119">In the Criteria field, type 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="79a54-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="79a54-120">Click OK.</span></span>
11. <span data-ttu-id="79a54-121">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="79a54-121">Click Import.</span></span>
12. <span data-ttu-id="79a54-122">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="79a54-122">Click Yes.</span></span>
13. <span data-ttu-id="79a54-123">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="79a54-123">On the Action Pane, click Options.</span></span>
14. <span data-ttu-id="79a54-124">Kliknij opcję Filtr/sortowanie zaawansowane.</span><span class="sxs-lookup"><span data-stu-id="79a54-124">Click Advanced Filter/Sort.</span></span>
15. <span data-ttu-id="79a54-125">Kliknij pozycję Resetuj.</span><span class="sxs-lookup"><span data-stu-id="79a54-125">Click Reset.</span></span>
16. <span data-ttu-id="79a54-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="79a54-126">Click Add.</span></span>
17. <span data-ttu-id="79a54-127">W polu Pole wybierz opcję „Nazwa konfiguracji”.</span><span class="sxs-lookup"><span data-stu-id="79a54-127">In the Field field, select 'Configuration name'.</span></span>
18. <span data-ttu-id="79a54-128">W polu Kryteria wpisz „Raport o liście sprzedaży do UE z podziałem na wiersze”.</span><span class="sxs-lookup"><span data-stu-id="79a54-128">In the Criteria field, type 'EU Sales list by rows report'.</span></span>
19. <span data-ttu-id="79a54-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="79a54-129">Click OK.</span></span>
20. <span data-ttu-id="79a54-130">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="79a54-130">Click Import.</span></span>
21. <span data-ttu-id="79a54-131">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="79a54-131">Click Yes.</span></span>

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a><span data-ttu-id="79a54-132">Konfigurowanie kodów podatków na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="79a54-132">Set up sales tax codes for EU sales list reporting</span></span>
1. <span data-ttu-id="79a54-133">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Kody podatków.</span><span class="sxs-lookup"><span data-stu-id="79a54-133">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="79a54-134">Użyj szybkiego filtru, aby wyfiltrować pole Kod podatku według wartości „VAT19”.</span><span class="sxs-lookup"><span data-stu-id="79a54-134">Use the Quick Filter to filter on the Sales tax code field with a value of 'VAT19'.</span></span>
3. <span data-ttu-id="79a54-135">Rozwiń sekcję Konfiguracja raportu.</span><span class="sxs-lookup"><span data-stu-id="79a54-135">Expand the Report setup section.</span></span>
    * <span data-ttu-id="79a54-136">Upewnij się, że opcja Wykluczone ma ustawioną wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="79a54-136">Verify that the Excluded selection is set to No.</span></span>  
    * <span data-ttu-id="79a54-137">W celu zmiany tego ustawienia może być konieczne odblokowanie zadań w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="79a54-137">You may need to unlock the task guide to change this setting.</span></span>  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="79a54-138">Konfigurowanie grup podatków na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="79a54-138">Set up sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="79a54-139">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="79a54-139">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="79a54-140">Użyj szybkiego filtru, aby wyfiltrować pole Grupa podatków według wartości „AR-DOM”.</span><span class="sxs-lookup"><span data-stu-id="79a54-140">Use the Quick Filter to filter on the Sales tax group field with a value of 'AR-DOM'.</span></span>
3. <span data-ttu-id="79a54-141">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="79a54-141">Click Edit.</span></span>
4. <span data-ttu-id="79a54-142">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="79a54-142">Expand the Setup section.</span></span>
5. <span data-ttu-id="79a54-143">Na liście zaznacz pierwszy wiersz.</span><span class="sxs-lookup"><span data-stu-id="79a54-143">In the list, select the first row.</span></span>
6. <span data-ttu-id="79a54-144">Zaznacz pole wyboru Zwolnienie.</span><span class="sxs-lookup"><span data-stu-id="79a54-144">Select the Exempt check box.</span></span>
7. <span data-ttu-id="79a54-145">Na liście zaznacz drugi wiersz.</span><span class="sxs-lookup"><span data-stu-id="79a54-145">In the list, select the second row.</span></span>
8. <span data-ttu-id="79a54-146">Zaznacz pole wyboru Zwolnienie.</span><span class="sxs-lookup"><span data-stu-id="79a54-146">Select the Exempt check box.</span></span>
9. <span data-ttu-id="79a54-147">Na liście zaznacz trzeci wiersz.</span><span class="sxs-lookup"><span data-stu-id="79a54-147">In the list, select the third row.</span></span>
10. <span data-ttu-id="79a54-148">Zaznacz pole wyboru Zwolnienie.</span><span class="sxs-lookup"><span data-stu-id="79a54-148">Select the Exempt check box.</span></span>

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="79a54-149">Konfigurowanie grup podatków dla towarów na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="79a54-149">Set up item sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="79a54-150">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków dla towaru.</span><span class="sxs-lookup"><span data-stu-id="79a54-150">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
2. <span data-ttu-id="79a54-151">Użyj szybkiego filtru, aby wyfiltrować pole Grupa podatków dla towaru według wartości „PEŁNE”.</span><span class="sxs-lookup"><span data-stu-id="79a54-151">Use the Quick Filter to filter on the Item sales tax group field with a value of 'FULL '.</span></span>
    * <span data-ttu-id="79a54-152">Upewnij się, że opcja Typ raportowania ma ustawioną wartość „Towar”.</span><span class="sxs-lookup"><span data-stu-id="79a54-152">Verify that the Reporting type selection is set to 'Item'.</span></span>  
    * <span data-ttu-id="79a54-153">W celu zmiany wartości tego pola może być konieczne odblokowanie zadań w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="79a54-153">You may need to unlock the task guide to change the value in this field.</span></span>  
3. <span data-ttu-id="79a54-154">Użyj szybkiego filtru, aby wyfiltrować pole Grupa podatków dla towaru według wartości „CZERWONE”.</span><span class="sxs-lookup"><span data-stu-id="79a54-154">Use the Quick Filter to filter on the Item sales tax group field with a value of 'RED '.</span></span>
    * <span data-ttu-id="79a54-155">Upewnij się, że opcja Typ raportowania ma ustawioną wartość „Usługa”.</span><span class="sxs-lookup"><span data-stu-id="79a54-155">Verify that the Reporting type selection is set to 'Service'.</span></span>  
    * <span data-ttu-id="79a54-156">W celu zmiany wartości tego pola może być konieczne odblokowanie zadań w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="79a54-156">You may need to unlock the task guide to change the value in this field.</span></span>  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a><span data-ttu-id="79a54-157">Konfigurowanie parametrów kraju/regionu na potrzeby raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="79a54-157">Set up country/region parameters for EU sales list reporting</span></span>
1. <span data-ttu-id="79a54-158">Wybierz kolejno opcje Podatek > Ustawienia > Podatek > Parametry kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="79a54-158">Go to Tax > Setup > Sales tax > Country/region parameters.</span></span>
2. <span data-ttu-id="79a54-159">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="79a54-159">Click New.</span></span>
3. <span data-ttu-id="79a54-160">W polu Kraj/region wpisz „PRT”.</span><span class="sxs-lookup"><span data-stu-id="79a54-160">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="79a54-161">W polu Podatek wpisz „PT”.</span><span class="sxs-lookup"><span data-stu-id="79a54-161">In the Sales tax field, type 'PT'.</span></span>

## <a name="create-tax-exempt-numbers"></a><span data-ttu-id="79a54-162">Tworzenie numerów identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="79a54-162">Create tax exempt numbers</span></span>
1. <span data-ttu-id="79a54-163">Wybierz kolejno opcje Podatek > Ustawienia > Podatek > Numery identyfikacji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="79a54-163">Go to Tax > Setup > Sales tax > Tax exempt numbers.</span></span>
2. <span data-ttu-id="79a54-164">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="79a54-164">Click New.</span></span>
3. <span data-ttu-id="79a54-165">W polu Kraj/region wpisz „PRT”.</span><span class="sxs-lookup"><span data-stu-id="79a54-165">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="79a54-166">W polu Numer identyfikacji podatkowej wpisz „PT12345”.</span><span class="sxs-lookup"><span data-stu-id="79a54-166">In the Tax exempt number field, type 'PT12345'.</span></span>

## <a name="set-up-eu-sales-list-reporting-parameters"></a><span data-ttu-id="79a54-167">Konfigurowanie parametrów raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="79a54-167">Set up EU sales list reporting parameters</span></span>
1. <span data-ttu-id="79a54-168">Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="79a54-168">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="79a54-169">Kliknij kartę Lista sprzedaży do UE.</span><span class="sxs-lookup"><span data-stu-id="79a54-169">Click the EU sales list tab.</span></span>
3. <span data-ttu-id="79a54-170">W polu Przenieś zakupy wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="79a54-170">Select Yes in the Transfer purchases field.</span></span>
4. <span data-ttu-id="79a54-171">Rozwiń sekcję Reguły zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="79a54-171">Expand the Rounding rules section.</span></span>
5. <span data-ttu-id="79a54-172">W polu Reguła zaokrąglania wpisz „0,1”.</span><span class="sxs-lookup"><span data-stu-id="79a54-172">Set Rounding rule to '0.1'.</span></span>
6. <span data-ttu-id="79a54-173">W polu Użyj wartości minimalnej zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="79a54-173">Select Yes in the Use minimum value field.</span></span>
7. <span data-ttu-id="79a54-174">W polu Liczba cyfr dziesiętnych wpisz wartość „2”.</span><span class="sxs-lookup"><span data-stu-id="79a54-174">In the Number of decimals field, enter '2'.</span></span>
8. <span data-ttu-id="79a54-175">Rozwiń sekcję Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="79a54-175">Expand the Electronic reporting section.</span></span>
9. <span data-ttu-id="79a54-176">W polu Mapowanie formatu plików wybierz opcję „Lista sprzedaży do UE (DE)”.</span><span class="sxs-lookup"><span data-stu-id="79a54-176">In the File format mapping field, select 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="79a54-177">W polu Mapowanie formatu raportów wybierz opcję „Raport o liście sprzedaży do UE z podziałem na wiersze”.</span><span class="sxs-lookup"><span data-stu-id="79a54-177">In the Report format mapping field, select 'EU Sales list by rows report'.</span></span>
11. <span data-ttu-id="79a54-178">Kliknij kartę Właściwości kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="79a54-178">Click the Country/region properties tab.</span></span>
    * <span data-ttu-id="79a54-179">Upewnij się, że dla kraju/regionu DEU pole Typ kraju/regionu ma ustawioną wartość „Krajowy”.</span><span class="sxs-lookup"><span data-stu-id="79a54-179">Verify that the Country/region type field is set to 'Domestic' for Country/region DEU.</span></span>  
    * <span data-ttu-id="79a54-180">W celu zmiany wartości tego pola może być konieczne odblokowanie zadań w przewodniku.</span><span class="sxs-lookup"><span data-stu-id="79a54-180">You may need to unlock the task guide to change the value in this field.</span></span>  
12. <span data-ttu-id="79a54-181">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="79a54-181">Click New.</span></span>
13. <span data-ttu-id="79a54-182">W polu Kraj/region wpisz „PRT”.</span><span class="sxs-lookup"><span data-stu-id="79a54-182">In the Country/region field, type 'PRT'.</span></span>
14. <span data-ttu-id="79a54-183">W polu Kod Intrastat wpisz „PT”.</span><span class="sxs-lookup"><span data-stu-id="79a54-183">In the Intrastat code field, type 'PT'.</span></span>
15. <span data-ttu-id="79a54-184">W polu Typ kraju/regionu wybierz opcję „UE”.</span><span class="sxs-lookup"><span data-stu-id="79a54-184">In the Country/region type field, select 'EU'.</span></span>
16. <span data-ttu-id="79a54-185">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="79a54-185">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="79a54-186">Upewnij się, że kod sekwencji numerów jest określony dla odwołania „Lista sprzedaży do UE”.</span><span class="sxs-lookup"><span data-stu-id="79a54-186">Verify that a Number sequence code is specified for the Reference 'EU sales list'.</span></span>  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a><span data-ttu-id="79a54-187">Tworzenie odbiorcy do celów demonstracji raportowania listy sprzedaży do UE</span><span class="sxs-lookup"><span data-stu-id="79a54-187">Create a customer for EU sales list reporting demo purposes</span></span>
1. <span data-ttu-id="79a54-188">Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="79a54-188">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="79a54-189">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="79a54-189">Click New.</span></span>
3. <span data-ttu-id="79a54-190">W polu Konto odbiorcy wpisz „PRT-001”.</span><span class="sxs-lookup"><span data-stu-id="79a54-190">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="79a54-191">W polu Nazwa wpisz „Odbiorca z Portugalii”.</span><span class="sxs-lookup"><span data-stu-id="79a54-191">In the Name field, type 'A customer from Portugal'.</span></span>
5. <span data-ttu-id="79a54-192">W polu Grupa odbiorców wybierz opcję „10”.</span><span class="sxs-lookup"><span data-stu-id="79a54-192">In the Customer group field, select '10'.</span></span>
6. <span data-ttu-id="79a54-193">W polu Grupa podatków wybierz opcję „AR-DOM”.</span><span class="sxs-lookup"><span data-stu-id="79a54-193">In the Sales tax group field, select 'AR-DOM'.</span></span>
7. <span data-ttu-id="79a54-194">W polu Numer identyfikacji podatkowej wybierz opcję „PT12345”.</span><span class="sxs-lookup"><span data-stu-id="79a54-194">In the Tax exempt number field, select 'PT12345'.</span></span>
8. <span data-ttu-id="79a54-195">W polu Kraj/region wpisz „PRT”.</span><span class="sxs-lookup"><span data-stu-id="79a54-195">In the Country/region field, type 'PRT'.</span></span>
9. <span data-ttu-id="79a54-196">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="79a54-196">Click Save.</span></span>

