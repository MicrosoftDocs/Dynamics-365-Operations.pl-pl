---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 2 — Mapowanie modelu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3aabd622d15917d7e4549d0b0679aa20231c5815
ms.sourcegitcommit: d9125c20b21459076e4fd92fd9ebfe2e53a0431b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2020
ms.locfileid: "3406527"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a><span data-ttu-id="05c4c-103">ER Używanie wymiarów finansowych jako źródła danych (Część 2 — Mapowanie modelu)</span><span class="sxs-lookup"><span data-stu-id="05c4c-103">ER Use financial dimensions as a data source (Part 2 - Model mapping)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="05c4c-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="05c4c-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="05c4c-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="05c4c-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="05c4c-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 1: Projektowanie modelu danych)”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 1: Design data model" procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="05c4c-107">Dodawanie wymaganych źródeł danych do mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="05c4c-107">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="05c4c-108">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="05c4c-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="05c4c-109">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="05c4c-110">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="05c4c-110">Click Designer.</span></span>
4. <span data-ttu-id="05c4c-111">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="05c4c-111">Click Map model to datasource.</span></span>
5. <span data-ttu-id="05c4c-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="05c4c-112">Click New.</span></span>
6. <span data-ttu-id="05c4c-113">W polu Definicja zaznacz wartość Wpis.</span><span class="sxs-lookup"><span data-stu-id="05c4c-113">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="05c4c-114">W polu Nazwa wpisz „Mapowanie danych wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-114">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="05c4c-115">W polu Opis wpisz „Mapowanie danych wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-115">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="05c4c-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="05c4c-116">Click Save.</span></span>
10. <span data-ttu-id="05c4c-117">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="05c4c-117">Click Designer.</span></span>
11. <span data-ttu-id="05c4c-118">W drzewie zaznacz element „Dynamics 365 for Operations\Tabela”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-118">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="05c4c-119">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="05c4c-119">Click Add root.</span></span>
13. <span data-ttu-id="05c4c-120">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-120">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="05c4c-121">W polu Tabela wpisz „CompanyInfo”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-121">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="05c4c-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="05c4c-122">Click OK.</span></span>
16. <span data-ttu-id="05c4c-123">W drzewie zaznacz element „Funkcje\Szczegóły wymiarów finansowych”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-123">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="05c4c-124">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="05c4c-124">Click Add root.</span></span>
    * <span data-ttu-id="05c4c-125">To źródło danych określa, jak zakres wymiarów finansowych zostanie zdefiniowany dla każdego raportu, który będzie używał tego modelu jako źródła danych.</span><span class="sxs-lookup"><span data-stu-id="05c4c-125">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="05c4c-126">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="05c4c-126">In the Name field, type a value.</span></span>
19. <span data-ttu-id="05c4c-127">W polu Zapytaj o wymiary wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="05c4c-127">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="05c4c-128">Wybierz opcję Tak, aby umożliwić użytkownikowi wybieranie wymiarów w czasie wykonywania w formularzu Okno dialogowe użytkownika.</span><span class="sxs-lookup"><span data-stu-id="05c4c-128">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="05c4c-129">Jeśli ustawisz wartość Nie, domyślnie będą używane wszystkie wymiary finansowe bieżącego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="05c4c-129">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="05c4c-130">W polu Wybór wymiarów finansowych zaznacz wartość „Firma”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-130">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="05c4c-131">Zaznacz opcję Wszystko, aby umożliwić użytkownikowi wybieranie żądanych wymiarów dla bieżącego wystąpienia w polu Wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="05c4c-131">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="05c4c-132">Zaznacz opcję Firma, aby umożliwić użytkownikowi wybieranie wymiarów dla firmy w polu Wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="05c4c-132">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="05c4c-133">Wybierz opcję Wymiar, aby umożliwić użytkownikowi wybieranie wymiarów przy użyciu jednego zestawu wymiarów.</span><span class="sxs-lookup"><span data-stu-id="05c4c-133">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="05c4c-134">W polu Zapytaj o konto główne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="05c4c-134">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="05c4c-135">W ustawieniu „Zapytaj o konto główne” zaznacz wartość Tak, aby zezwolić użytkownikom na wybieranie konta głównego jako części listy wymiarów.</span><span class="sxs-lookup"><span data-stu-id="05c4c-135">Set 'Ask for main account' to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="05c4c-136">Jeśli zaznaczysz wartość Nie, konto główne nie zostanie włączone do listy wymiarów, a opcja „Czy konto główne jest obowiązkowe” zostanie włączona.</span><span class="sxs-lookup"><span data-stu-id="05c4c-136">If set to No, the main account will not be included to the list of dimensions and the 'Is main account mandatory' option is enabled.</span></span> <span data-ttu-id="05c4c-137">Jeśli w opcji „Czy konto główne jest obowiązkowe” ustawisz wartość Tak, konto główne będzie umieszczane na liście wymiarów niezależnie od wyboru dokonanego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="05c4c-137">If "Is main account mandatory' is set to Yes, include the main account in the list of dimensions regardless of the user's selection.</span></span>  
22. <span data-ttu-id="05c4c-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="05c4c-138">Click OK.</span></span>
<span data-ttu-id="05c4c-139">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping1.png)</span><span class="sxs-lookup"><span data-stu-id="05c4c-139">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping1.png)</span></span>
23. <span data-ttu-id="05c4c-140">W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-140">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="05c4c-141">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="05c4c-141">Click Add root.</span></span>
25. <span data-ttu-id="05c4c-142">W polu Nazwa wpisz „LedgerJournal”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-142">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="05c4c-143">W polu Monituj o zapytanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="05c4c-143">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="05c4c-144">W polu Tabela wpisz „LedgerJournalTable”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-144">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="05c4c-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="05c4c-145">Click OK.</span></span>
<span data-ttu-id="05c4c-146">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping2.png)</span><span class="sxs-lookup"><span data-stu-id="05c4c-146">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping2.png)</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="05c4c-147">Mapowanie elementów modelu danych na dodane źródła danych</span><span class="sxs-lookup"><span data-stu-id="05c4c-147">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="05c4c-148">W drzewie rozwiń węzeł „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-148">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="05c4c-149">W drzewie rozwiń węzeł „Arkusz\Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-149">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="05c4c-150">W drzewie rozwiń węzeł „Arkusz\Transakcja\Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-150">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="05c4c-151">W drzewie rozwiń węzeł „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-151">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="05c4c-152">W drzewie rozwiń węzeł „LedgerJournal”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-152">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="05c4c-153">W drzewie rozwiń węzeł „LedgerJournal\<Relacje”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-153">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="05c4c-154">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-154">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="05c4c-155">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-155">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="05c4c-156">W drzewie zaznacz element „Arkusz\Transakcja\Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-156">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="05c4c-157">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-157">Click Bind.</span></span>
11. <span data-ttu-id="05c4c-158">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-158">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="05c4c-159">Należy zauważyć, że dla każdego odwołania do wymiarów finansowych, na przykład, LedgerDimension, jest dostępny odpowiadający mu element źródła danych (LedgerDimension.Wymiar).</span><span class="sxs-lookup"><span data-stu-id="05c4c-159">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="05c4c-160">Ten element źródła danych udostępnia wymiary finansowe tego zestawu wymiarów jako listę rekordu.</span><span class="sxs-lookup"><span data-stu-id="05c4c-160">This data source item offers the financial dimensions of that dimensions set as the record's list.</span></span>  
12. <span data-ttu-id="05c4c-161">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-161">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="05c4c-162">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="05c4c-163">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-163">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="05c4c-164">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Definicja”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-164">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="05c4c-165">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Definicja\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-165">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="05c4c-166">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-166">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="05c4c-167">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-167">Click Bind.</span></span>
19. <span data-ttu-id="05c4c-168">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość\Opis”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-168">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="05c4c-169">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Opis”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-169">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="05c4c-170">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-170">Click Bind.</span></span>
22. <span data-ttu-id="05c4c-171">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość\Kod”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-171">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="05c4c-172">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Kod”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-172">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="05c4c-173">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-173">Click Bind.</span></span>
25. <span data-ttu-id="05c4c-174">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-174">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="05c4c-175">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-175">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="05c4c-176">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-176">Click Bind.</span></span>
<span data-ttu-id="05c4c-177">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping3.png)</span><span class="sxs-lookup"><span data-stu-id="05c4c-177">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping3.png)</span></span>
28. <span data-ttu-id="05c4c-178">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Debet(AmountCurDebit)”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-178">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="05c4c-179">W drzewie zaznacz element „Arkusz\Transakcja\Debet”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-179">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="05c4c-180">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-180">Click Bind.</span></span>
31. <span data-ttu-id="05c4c-181">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Data(TransDate)”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-181">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="05c4c-182">W drzewie zaznacz element „Arkusz\Transakcja\Data”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-182">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="05c4c-183">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-183">Click Bind.</span></span>
34. <span data-ttu-id="05c4c-184">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Waluta(CurrencyCode)”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-184">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="05c4c-185">W drzewie zaznacz element „Arkusz\Transakcja\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-185">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="05c4c-186">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-186">Click Bind.</span></span>
37. <span data-ttu-id="05c4c-187">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Kredyt(AmountCurCredit)”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-187">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="05c4c-188">W drzewie zaznacz element „Arkusz\Transakcja\Kredyt”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-188">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="05c4c-189">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-189">Click Bind.</span></span>
40. <span data-ttu-id="05c4c-190">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-190">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="05c4c-191">W drzewie zaznacz element „Arkusz\Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-191">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="05c4c-192">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-192">Click Bind.</span></span>
43. <span data-ttu-id="05c4c-193">W drzewie zaznacz element „LedgerJournal\Arkusz z numerem partii(JournalNum)”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-193">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="05c4c-194">W drzewie zaznacz element „Arkusz\Partia”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-194">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="05c4c-195">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-195">Click Bind.</span></span>
46. <span data-ttu-id="05c4c-196">W drzewie zaznacz element „LedgerJournal”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-196">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="05c4c-197">W drzewie zaznacz element „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-197">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="05c4c-198">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-198">Click Bind.</span></span>
49. <span data-ttu-id="05c4c-199">W drzewie rozwiń węzeł „Wymiary”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-199">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="05c4c-200">W drzewie rozwiń węzeł „Wymiary\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-200">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="05c4c-201">W drzewie rozwiń węzeł „Wymiary\Konto główne i wymiary\Definicja”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-201">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="05c4c-202">W drzewie zaznacz element „Wymiary\Konto główne i wymiary\Definicja\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-202">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="05c4c-203">W drzewie zaznacz element „Ustawienie wymiarów\Kod”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-203">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="05c4c-204">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-204">Click Bind.</span></span>
55. <span data-ttu-id="05c4c-205">W drzewie zaznacz element „Wymiary\Konto główne i wymiary\Definicja\Nazwa kolumny raportu”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-205">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="05c4c-206">W drzewie zaznacz element „Ustawienie wymiarów\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-206">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="05c4c-207">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-207">Click Bind.</span></span>
58. <span data-ttu-id="05c4c-208">W drzewie zaznacz element „Wymiary\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-208">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="05c4c-209">W drzewie zaznacz element „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-209">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="05c4c-210">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="05c4c-210">Click Bind.</span></span>
61. <span data-ttu-id="05c4c-211">W drzewie zaznacz element „Firma”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-211">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="05c4c-212">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="05c4c-212">Click Edit.</span></span>
63. <span data-ttu-id="05c4c-213">W polu expressionAsStringText wpisz „Firma.'find()'.'name()'”.</span><span class="sxs-lookup"><span data-stu-id="05c4c-213">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="05c4c-214">Firma.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="05c4c-214">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="05c4c-215">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="05c4c-215">Click Save.</span></span>
<span data-ttu-id="05c4c-216">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping4.png)</span><span class="sxs-lookup"><span data-stu-id="05c4c-216">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping4.png)</span></span>
65. <span data-ttu-id="05c4c-217">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="05c4c-217">Close the page.</span></span>
66. <span data-ttu-id="05c4c-218">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="05c4c-218">Click Save.</span></span>
67. <span data-ttu-id="05c4c-219">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="05c4c-219">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="05c4c-220">Finalizowanie tej wersji roboczej modelu</span><span class="sxs-lookup"><span data-stu-id="05c4c-220">Complete this draft model's version</span></span>
1. <span data-ttu-id="05c4c-221">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="05c4c-221">Close the page.</span></span>
2. <span data-ttu-id="05c4c-222">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="05c4c-222">Close the page.</span></span>
3. <span data-ttu-id="05c4c-223">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="05c4c-223">Click Change status.</span></span>
4. <span data-ttu-id="05c4c-224">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="05c4c-224">Click Complete.</span></span>
5. <span data-ttu-id="05c4c-225">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="05c4c-225">Click OK.</span></span>
<span data-ttu-id="05c4c-226">![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping5.png)</span><span class="sxs-lookup"><span data-stu-id="05c4c-226">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping5.png)</span></span>
