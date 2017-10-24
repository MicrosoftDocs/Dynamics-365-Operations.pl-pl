--- 
title: "Mapowanie modeli w celu używania wymiarów finansowych jako źródła danych na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a3eafa7b66dcc0c2481d7eeaf98bed7f58e4be33
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="map-models--to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="48111-103">Mapowanie modeli w celu używania wymiarów finansowych jako źródła danych na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="48111-103">Map models  to use financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="48111-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="48111-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="48111-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="48111-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="48111-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 1: Projektowanie modelu danych)”.</span><span class="sxs-lookup"><span data-stu-id="48111-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 1: Design data model” procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="48111-107">Dodawanie wymaganych źródeł danych do mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="48111-107">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="48111-108">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="48111-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="48111-109">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="48111-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="48111-110">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="48111-110">Click Designer.</span></span>
4. <span data-ttu-id="48111-111">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="48111-111">Click Map model to datasource.</span></span>
5. <span data-ttu-id="48111-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="48111-112">Click New.</span></span>
6. <span data-ttu-id="48111-113">W polu Definicja zaznacz wartość Wpis.</span><span class="sxs-lookup"><span data-stu-id="48111-113">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="48111-114">W polu Nazwa wpisz „Mapowanie danych wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="48111-114">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="48111-115">W polu Opis wpisz „Mapowanie danych wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="48111-115">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="48111-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="48111-116">Click Save.</span></span>
10. <span data-ttu-id="48111-117">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="48111-117">Click Designer.</span></span>
11. <span data-ttu-id="48111-118">W drzewie zaznacz element „Dynamics 365 for Operations\Tabela”.</span><span class="sxs-lookup"><span data-stu-id="48111-118">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="48111-119">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="48111-119">Click Add root.</span></span>
13. <span data-ttu-id="48111-120">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="48111-120">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="48111-121">W polu Tabela wpisz „CompanyInfo”.</span><span class="sxs-lookup"><span data-stu-id="48111-121">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="48111-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="48111-122">Click OK.</span></span>
16. <span data-ttu-id="48111-123">W drzewie zaznacz element „Funkcje\Szczegóły wymiarów finansowych”.</span><span class="sxs-lookup"><span data-stu-id="48111-123">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="48111-124">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="48111-124">Click Add root.</span></span>
    * <span data-ttu-id="48111-125">To źródło danych określa, jak zakres wymiarów finansowych zostanie zdefiniowany dla każdego raportu, który będzie używał tego modelu jako źródła danych.</span><span class="sxs-lookup"><span data-stu-id="48111-125">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="48111-126">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="48111-126">In the Name field, type a value.</span></span>
19. <span data-ttu-id="48111-127">W polu Zapytaj o wymiary wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="48111-127">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="48111-128">Wybierz opcję Tak, aby umożliwić użytkownikowi wybieranie wymiarów w czasie wykonywania w formularzu Okno dialogowe użytkownika.</span><span class="sxs-lookup"><span data-stu-id="48111-128">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="48111-129">Jeśli ustawisz wartość Nie, domyślnie będą używane wszystkie wymiary finansowe bieżącego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="48111-129">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="48111-130">W polu Wybór wymiarów finansowych zaznacz wartość „Firma”.</span><span class="sxs-lookup"><span data-stu-id="48111-130">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="48111-131">Zaznacz opcję Wszystko, aby umożliwić użytkownikowi wybieranie żądanych wymiarów dla bieżącego wystąpienia w polu Wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="48111-131">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="48111-132">Zaznacz opcję Firma, aby umożliwić użytkownikowi wybieranie wymiarów dla firmy w polu Wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="48111-132">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="48111-133">Wybierz opcję Wymiar, aby umożliwić użytkownikowi wybieranie wymiarów przy użyciu jednego zestawu wymiarów.</span><span class="sxs-lookup"><span data-stu-id="48111-133">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="48111-134">W polu Zapytaj o konto główne wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="48111-134">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="48111-135">W ustawieniu „Zapytaj o konto główne” zaznacz wartość Tak, aby zezwolić użytkownikom na wybieranie konta głównego jako części listy wymiarów.</span><span class="sxs-lookup"><span data-stu-id="48111-135">Set ‘Ask for main account’ to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="48111-136">Jeśli zaznaczysz wartość Nie, konto główne nie zostanie włączone do listy wymiarów, a opcja „Czy konto główne jest obowiązkowe” zostanie włączona.</span><span class="sxs-lookup"><span data-stu-id="48111-136">If set to No, the main account will not be included to the list of dimensions and the ‘Is main account mandatory’ option is enabled.</span></span> <span data-ttu-id="48111-137">Jeśli w opcji „Czy konto główne jest obowiązkowe” ustawisz wartość Tak, konto główne będzie umieszczane na liście wymiarów niezależnie od wyboru dokonanego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="48111-137">If “Is main account mandatory’ is set to Yes, include the main account in the list of dimensions regardless of the user’s selection.</span></span>  
22. <span data-ttu-id="48111-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="48111-138">Click OK.</span></span>
23. <span data-ttu-id="48111-139">W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.</span><span class="sxs-lookup"><span data-stu-id="48111-139">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="48111-140">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="48111-140">Click Add root.</span></span>
25. <span data-ttu-id="48111-141">W polu Nazwa wpisz „LedgerJournal”.</span><span class="sxs-lookup"><span data-stu-id="48111-141">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="48111-142">W polu Monituj o zapytanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="48111-142">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="48111-143">W polu Tabela wpisz „LedgerJournalTable”.</span><span class="sxs-lookup"><span data-stu-id="48111-143">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="48111-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="48111-144">Click OK.</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="48111-145">Mapowanie elementów modelu danych na dodane źródła danych</span><span class="sxs-lookup"><span data-stu-id="48111-145">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="48111-146">W drzewie rozwiń węzeł „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="48111-146">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="48111-147">W drzewie rozwiń węzeł „Arkusz\Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="48111-147">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="48111-148">W drzewie rozwiń węzeł „Arkusz\Transakcja\Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="48111-148">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="48111-149">W drzewie rozwiń węzeł „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="48111-149">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="48111-150">W drzewie rozwiń węzeł „LedgerJournal”.</span><span class="sxs-lookup"><span data-stu-id="48111-150">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="48111-151">W drzewie rozwiń węzeł „LedgerJournal\<Relacje”.</span><span class="sxs-lookup"><span data-stu-id="48111-151">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="48111-152">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans”.</span><span class="sxs-lookup"><span data-stu-id="48111-152">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="48111-153">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="48111-153">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="48111-154">W drzewie zaznacz element „Arkusz\Transakcja\Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="48111-154">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="48111-155">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-155">Click Bind.</span></span>
11. <span data-ttu-id="48111-156">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)”.</span><span class="sxs-lookup"><span data-stu-id="48111-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="48111-157">Należy zauważyć, że dla każdego odwołania do wymiarów finansowych, na przykład, LedgerDimension, jest dostępny odpowiadający mu element źródła danych (LedgerDimension.Wymiar).</span><span class="sxs-lookup"><span data-stu-id="48111-157">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="48111-158">Ten element źródła danych udostępnia wymiary finansowe tego zestawu wymiarów jako listę rekordu.</span><span class="sxs-lookup"><span data-stu-id="48111-158">This data source item offers the financial dimensions of that dimensions set as the record’s list.</span></span>  
12. <span data-ttu-id="48111-159">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)”.</span><span class="sxs-lookup"><span data-stu-id="48111-159">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="48111-160">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="48111-160">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="48111-161">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość”.</span><span class="sxs-lookup"><span data-stu-id="48111-161">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="48111-162">W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Definicja”.</span><span class="sxs-lookup"><span data-stu-id="48111-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="48111-163">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Definicja\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="48111-163">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="48111-164">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="48111-164">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="48111-165">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-165">Click Bind.</span></span>
19. <span data-ttu-id="48111-166">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość\Opis”.</span><span class="sxs-lookup"><span data-stu-id="48111-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="48111-167">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Opis”.</span><span class="sxs-lookup"><span data-stu-id="48111-167">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="48111-168">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-168">Click Bind.</span></span>
22. <span data-ttu-id="48111-169">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość\Kod”.</span><span class="sxs-lookup"><span data-stu-id="48111-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="48111-170">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Kod”.</span><span class="sxs-lookup"><span data-stu-id="48111-170">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="48111-171">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-171">Click Bind.</span></span>
25. <span data-ttu-id="48111-172">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="48111-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="48111-173">W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="48111-173">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="48111-174">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-174">Click Bind.</span></span>
28. <span data-ttu-id="48111-175">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Debet(AmountCurDebit)”.</span><span class="sxs-lookup"><span data-stu-id="48111-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="48111-176">W drzewie zaznacz element „Arkusz\Transakcja\Debet”.</span><span class="sxs-lookup"><span data-stu-id="48111-176">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="48111-177">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-177">Click Bind.</span></span>
31. <span data-ttu-id="48111-178">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Data(TransDate)”.</span><span class="sxs-lookup"><span data-stu-id="48111-178">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="48111-179">W drzewie zaznacz element „Arkusz\Transakcja\Data”.</span><span class="sxs-lookup"><span data-stu-id="48111-179">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="48111-180">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-180">Click Bind.</span></span>
34. <span data-ttu-id="48111-181">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Waluta(CurrencyCode)”.</span><span class="sxs-lookup"><span data-stu-id="48111-181">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="48111-182">W drzewie zaznacz element „Arkusz\Transakcja\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="48111-182">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="48111-183">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-183">Click Bind.</span></span>
37. <span data-ttu-id="48111-184">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Kredyt(AmountCurCredit)”.</span><span class="sxs-lookup"><span data-stu-id="48111-184">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="48111-185">W drzewie zaznacz element „Arkusz\Transakcja\Kredyt”.</span><span class="sxs-lookup"><span data-stu-id="48111-185">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="48111-186">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-186">Click Bind.</span></span>
40. <span data-ttu-id="48111-187">W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans”.</span><span class="sxs-lookup"><span data-stu-id="48111-187">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="48111-188">W drzewie zaznacz element „Arkusz\Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="48111-188">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="48111-189">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-189">Click Bind.</span></span>
43. <span data-ttu-id="48111-190">W drzewie zaznacz element „LedgerJournal\Arkusz z numerem partii(JournalNum)”.</span><span class="sxs-lookup"><span data-stu-id="48111-190">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="48111-191">W drzewie zaznacz element „Arkusz\Partia”.</span><span class="sxs-lookup"><span data-stu-id="48111-191">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="48111-192">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-192">Click Bind.</span></span>
46. <span data-ttu-id="48111-193">W drzewie zaznacz element „LedgerJournal”.</span><span class="sxs-lookup"><span data-stu-id="48111-193">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="48111-194">W drzewie zaznacz element „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="48111-194">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="48111-195">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-195">Click Bind.</span></span>
49. <span data-ttu-id="48111-196">W drzewie rozwiń węzeł „Wymiary”.</span><span class="sxs-lookup"><span data-stu-id="48111-196">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="48111-197">W drzewie rozwiń węzeł „Wymiary\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="48111-197">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="48111-198">W drzewie rozwiń węzeł „Wymiary\Konto główne i wymiary\Definicja”.</span><span class="sxs-lookup"><span data-stu-id="48111-198">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="48111-199">W drzewie zaznacz element „Wymiary\Konto główne i wymiary\Definicja\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="48111-199">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="48111-200">W drzewie zaznacz element „Ustawienie wymiarów\Kod”.</span><span class="sxs-lookup"><span data-stu-id="48111-200">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="48111-201">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-201">Click Bind.</span></span>
55. <span data-ttu-id="48111-202">W drzewie zaznacz element „Wymiary\Konto główne i wymiary\Definicja\Nazwa kolumny raportu”.</span><span class="sxs-lookup"><span data-stu-id="48111-202">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="48111-203">W drzewie zaznacz element „Ustawienie wymiarów\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="48111-203">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="48111-204">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-204">Click Bind.</span></span>
58. <span data-ttu-id="48111-205">W drzewie zaznacz element „Wymiary\Konto główne i wymiary”.</span><span class="sxs-lookup"><span data-stu-id="48111-205">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="48111-206">W drzewie zaznacz element „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="48111-206">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="48111-207">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="48111-207">Click Bind.</span></span>
61. <span data-ttu-id="48111-208">W drzewie zaznacz element „Firma”.</span><span class="sxs-lookup"><span data-stu-id="48111-208">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="48111-209">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="48111-209">Click Edit.</span></span>
63. <span data-ttu-id="48111-210">W polu expressionAsStringText wpisz „Firma.'find()'.'name()'”.</span><span class="sxs-lookup"><span data-stu-id="48111-210">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="48111-211">Firma.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="48111-211">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="48111-212">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="48111-212">Click Save.</span></span>
65. <span data-ttu-id="48111-213">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="48111-213">Close the page.</span></span>
66. <span data-ttu-id="48111-214">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="48111-214">Click Save.</span></span>
67. <span data-ttu-id="48111-215">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="48111-215">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="48111-216">Finalizowanie tej wersji modelu roboczego</span><span class="sxs-lookup"><span data-stu-id="48111-216">Complete this draft model’s version</span></span>
1. <span data-ttu-id="48111-217">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="48111-217">Close the page.</span></span>
2. <span data-ttu-id="48111-218">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="48111-218">Close the page.</span></span>
3. <span data-ttu-id="48111-219">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="48111-219">Click Change status.</span></span>
4. <span data-ttu-id="48111-220">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="48111-220">Click Complete.</span></span>
5. <span data-ttu-id="48111-221">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="48111-221">Click OK.</span></span>


