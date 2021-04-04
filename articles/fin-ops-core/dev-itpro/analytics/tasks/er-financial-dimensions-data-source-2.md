---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 2 — Mapowanie modelu)
description: W tym temacie opisano sposób konfigurowania modelu raportowania elektronicznego w celu używania wymiarów finansowych jako źródła danych dla raportów ER. (część 2)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 59f65962ef8f6ae79190b6595a313831eca53830
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570175"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a><span data-ttu-id="ba1ea-104">ER Używanie wymiarów finansowych jako źródła danych (Część 2 — Mapowanie modelu)</span><span class="sxs-lookup"><span data-stu-id="ba1ea-104">ER Use financial dimensions as a data source (Part 2 - Model mapping)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ba1ea-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="ba1ea-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="ba1ea-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 1: Projektowanie modelu danych)”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 1: Design data model" procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="ba1ea-108">Dodawanie wymaganych źródeł danych do mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="ba1ea-108">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="ba1ea-109">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="ba1ea-110">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="ba1ea-111">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-111">Click Designer.</span></span>
4. <span data-ttu-id="ba1ea-112">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-112">Click Map model to datasource.</span></span>
5. <span data-ttu-id="ba1ea-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-113">Click New.</span></span>
6. <span data-ttu-id="ba1ea-114">W polu Definicja zaznacz wartość Wpis.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-114">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="ba1ea-115">W polu Nazwa wpisz „Mapowanie danych wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-115">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="ba1ea-116">W polu Opis wpisz „Mapowanie danych wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-116">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="ba1ea-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-117">Click Save.</span></span>
10. <span data-ttu-id="ba1ea-118">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-118">Click Designer.</span></span>
11. <span data-ttu-id="ba1ea-119">W drzewie zaznacz element „Dynamics 365 for Operations\Tabela”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-119">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="ba1ea-120">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-120">Click Add root.</span></span>
13. <span data-ttu-id="ba1ea-121">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-121">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="ba1ea-122">W polu Tabela wpisz „CompanyInfo”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-122">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="ba1ea-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-123">Click OK.</span></span>
16. <span data-ttu-id="ba1ea-124">W drzewie zaznacz element „Funkcje\Szczegóły wymiarów finansowych”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-124">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="ba1ea-125">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-125">Click Add root.</span></span>
    * <span data-ttu-id="ba1ea-126">To źródło danych określa, jak zakres wymiarów finansowych zostanie zdefiniowany dla każdego raportu, który będzie używał tego modelu jako źródła danych.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-126">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="ba1ea-127">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-127">In the Name field, type a value.</span></span>
19. <span data-ttu-id="ba1ea-128">W polu Zapytaj o wymiary wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-128">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="ba1ea-129">Wybierz opcję Tak, aby umożliwić użytkownikowi wybieranie wymiarów w czasie wykonywania w formularzu Okno dialogowe użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-129">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="ba1ea-130">Jeśli ustawisz wartość Nie, domyślnie będą używane wszystkie wymiary finansowe bieżącego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-130">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="ba1ea-131">W polu Wybór wymiarów finansowych zaznacz wartość „Firma”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-131">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="ba1ea-132">Zaznacz opcję Wszystko, aby umożliwić użytkownikowi wybieranie żądanych wymiarów dla bieżącego wystąpienia w polu Wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-132">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="ba1ea-133">Zaznacz opcję Firma, aby umożliwić użytkownikowi wybieranie wymiarów dla firmy w polu Wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-133">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="ba1ea-134">Wybierz opcję Wymiar, aby umożliwić użytkownikowi wybieranie wymiarów przy użyciu jednego zestawu wymiarów.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-134">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="ba1ea-135">W polu Zapytaj o konto główne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-135">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="ba1ea-136">W ustawieniu „Zapytaj o konto główne” zaznacz wartość Tak, aby zezwolić użytkownikom na wybieranie konta głównego jako części listy wymiarów.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-136">Set 'Ask for main account' to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="ba1ea-137">Jeśli zaznaczysz wartość Nie, konto główne nie zostanie włączone do listy wymiarów, a opcja „Czy konto główne jest obowiązkowe” zostanie włączona.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-137">If set to No, the main account will not be included to the list of dimensions and the 'Is main account mandatory' option is enabled.</span></span> <span data-ttu-id="ba1ea-138">Jeśli w opcji „Czy konto główne jest obowiązkowe” ustawisz wartość Tak, konto główne będzie umieszczane na liście wymiarów niezależnie od wyboru dokonanego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-138">If "Is main account mandatory' is set to Yes, include the main account in the list of dimensions regardless of the user's selection.</span></span>  
22. <span data-ttu-id="ba1ea-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-139">Click OK.</span></span>
<span data-ttu-id="ba1ea-140">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping1.png)</span><span class="sxs-lookup"><span data-stu-id="ba1ea-140">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping1.png)</span></span>
23. <span data-ttu-id="ba1ea-141">W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-141">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="ba1ea-142">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-142">Click Add root.</span></span>
25. <span data-ttu-id="ba1ea-143">W polu Nazwa wpisz „LedgerJournal”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-143">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="ba1ea-144">W polu Monituj o zapytanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-144">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="ba1ea-145">W polu Tabela wpisz „LedgerJournalTable”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-145">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="ba1ea-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-146">Click OK.</span></span>
<span data-ttu-id="ba1ea-147">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping2.png)</span><span class="sxs-lookup"><span data-stu-id="ba1ea-147">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping2.png)</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="ba1ea-148">Mapowanie elementów modelu danych na dodane źródła danych</span><span class="sxs-lookup"><span data-stu-id="ba1ea-148">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="ba1ea-149">W drzewie rozwiń węzeł „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-149">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="ba1ea-150">W drzewie rozwiń węzeł „Arkusz\Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-150">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="ba1ea-151">W drzewie rozwiń węzeł „Arkusz\Transakcja\Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-151">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="ba1ea-152">W drzewie rozwiń węzeł „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-152">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="ba1ea-153">W drzewie rozwiń węzeł „LedgerJournal”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-153">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="ba1ea-154">W drzewie rozwiń węzeł „LedgerJournal\<Relacje”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-154">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="ba1ea-155">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-155">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="ba1ea-156">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="ba1ea-157">W drzewie zaznacz element „Arkusz\Transakcja\Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-157">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="ba1ea-158">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-158">Click Bind.</span></span>
11. <span data-ttu-id="ba1ea-159">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-159">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="ba1ea-160">Należy zauważyć, że dla każdego odwołania do wymiarów finansowych, na przykład, LedgerDimension, jest dostępny odpowiadający mu element źródła danych (LedgerDimension.Wymiar).</span><span class="sxs-lookup"><span data-stu-id="ba1ea-160">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="ba1ea-161">Ten element źródła danych udostępnia wymiary finansowe tego zestawu wymiarów jako listę rekordu.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-161">This data source item offers the financial dimensions of that dimensions set as the record's list.</span></span>  
12. <span data-ttu-id="ba1ea-162">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="ba1ea-163">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-163">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="ba1ea-164">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-164">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="ba1ea-165">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Definicja”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-165">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="ba1ea-166">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Definicja\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="ba1ea-167">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-167">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="ba1ea-168">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-168">Click Bind.</span></span>
19. <span data-ttu-id="ba1ea-169">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość\Opis”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="ba1ea-170">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Opis”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-170">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="ba1ea-171">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-171">Click Bind.</span></span>
22. <span data-ttu-id="ba1ea-172">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość\Kod”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="ba1ea-173">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Kod”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-173">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="ba1ea-174">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-174">Click Bind.</span></span>
25. <span data-ttu-id="ba1ea-175">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="ba1ea-176">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-176">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="ba1ea-177">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-177">Click Bind.</span></span>
<span data-ttu-id="ba1ea-178">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping3.png)</span><span class="sxs-lookup"><span data-stu-id="ba1ea-178">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping3.png)</span></span>
28. <span data-ttu-id="ba1ea-179">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Debet(AmountCurDebit)”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-179">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="ba1ea-180">W drzewie zaznacz element „Arkusz\Transakcja\Debet”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-180">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="ba1ea-181">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-181">Click Bind.</span></span>
31. <span data-ttu-id="ba1ea-182">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Data(TransDate)”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-182">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="ba1ea-183">W drzewie zaznacz element „Arkusz\Transakcja\Data”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-183">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="ba1ea-184">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-184">Click Bind.</span></span>
34. <span data-ttu-id="ba1ea-185">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Waluta(CurrencyCode)”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-185">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="ba1ea-186">W drzewie zaznacz element „Arkusz\Transakcja\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-186">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="ba1ea-187">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-187">Click Bind.</span></span>
37. <span data-ttu-id="ba1ea-188">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Kredyt(AmountCurCredit)”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-188">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="ba1ea-189">W drzewie zaznacz element „Arkusz\Transakcja\Kredyt”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-189">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="ba1ea-190">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-190">Click Bind.</span></span>
40. <span data-ttu-id="ba1ea-191">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-191">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="ba1ea-192">W drzewie zaznacz element „Arkusz\Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-192">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="ba1ea-193">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-193">Click Bind.</span></span>
43. <span data-ttu-id="ba1ea-194">W drzewie zaznacz element „LedgerJournal\Arkusz z numerem partii(JournalNum)”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-194">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="ba1ea-195">W drzewie zaznacz element „Arkusz\Partia”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-195">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="ba1ea-196">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-196">Click Bind.</span></span>
46. <span data-ttu-id="ba1ea-197">W drzewie zaznacz element „LedgerJournal”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-197">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="ba1ea-198">W drzewie zaznacz element „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-198">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="ba1ea-199">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-199">Click Bind.</span></span>
49. <span data-ttu-id="ba1ea-200">W drzewie rozwiń węzeł „Wymiary”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-200">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="ba1ea-201">W drzewie rozwiń węzeł „Wymiary\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-201">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="ba1ea-202">W drzewie rozwiń węzeł „Wymiary\Konto główne i wymiary\Definicja”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-202">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="ba1ea-203">W drzewie zaznacz element „Wymiary\Konto główne i wymiary\Definicja\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-203">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="ba1ea-204">W drzewie zaznacz element „Ustawienie wymiarów\Kod”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-204">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="ba1ea-205">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-205">Click Bind.</span></span>
55. <span data-ttu-id="ba1ea-206">W drzewie zaznacz element „Wymiary\Konto główne i wymiary\Definicja\Nazwa kolumny raportu”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-206">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="ba1ea-207">W drzewie zaznacz element „Ustawienie wymiarów\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-207">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="ba1ea-208">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-208">Click Bind.</span></span>
58. <span data-ttu-id="ba1ea-209">W drzewie zaznacz element „Wymiary\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-209">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="ba1ea-210">W drzewie zaznacz element „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-210">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="ba1ea-211">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-211">Click Bind.</span></span>
61. <span data-ttu-id="ba1ea-212">W drzewie zaznacz element „Firma”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-212">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="ba1ea-213">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-213">Click Edit.</span></span>
63. <span data-ttu-id="ba1ea-214">W polu expressionAsStringText wpisz „Firma.'find()'.'name()'”.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-214">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="ba1ea-215">Firma.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="ba1ea-215">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="ba1ea-216">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-216">Click Save.</span></span>
<span data-ttu-id="ba1ea-217">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping4.png)</span><span class="sxs-lookup"><span data-stu-id="ba1ea-217">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping4.png)</span></span>
65. <span data-ttu-id="ba1ea-218">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-218">Close the page.</span></span>
66. <span data-ttu-id="ba1ea-219">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-219">Click Save.</span></span>
67. <span data-ttu-id="ba1ea-220">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-220">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="ba1ea-221">Finalizowanie tej wersji roboczej modelu</span><span class="sxs-lookup"><span data-stu-id="ba1ea-221">Complete this draft model's version</span></span>
1. <span data-ttu-id="ba1ea-222">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-222">Close the page.</span></span>
2. <span data-ttu-id="ba1ea-223">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-223">Close the page.</span></span>
3. <span data-ttu-id="ba1ea-224">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-224">Click Change status.</span></span>
4. <span data-ttu-id="ba1ea-225">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-225">Click Complete.</span></span>
5. <span data-ttu-id="ba1ea-226">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ba1ea-226">Click OK.</span></span>
<span data-ttu-id="ba1ea-227">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping5.png)</span><span class="sxs-lookup"><span data-stu-id="ba1ea-227">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping5.png)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]