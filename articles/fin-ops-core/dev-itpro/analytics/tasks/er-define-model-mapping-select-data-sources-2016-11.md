---
title: Definiowanie mapowań modeli raportowanie elektronicznego i wybieranie dla nich źródeł danych
description: W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może wybrać źródła danych modelu danych raportowania elektronicznego.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6287fa95b7ce7341e99d1b1a6b972db68a30398
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142180"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a><span data-ttu-id="3a39d-103">Definiowanie mapowań modeli raportowanie elektronicznego i wybieranie dla nich źródeł danych</span><span class="sxs-lookup"><span data-stu-id="3a39d-103">Define ER model mappings and select data sources for them</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3a39d-104">W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może wybrać źródła danych modelu danych raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="3a39d-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="3a39d-105">Źródła danych będą kojarzone z poszczególnymi składnikami wybranego modelu danych podczas projektowania oraz wypełnią model danych danymi biznesowymi w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="3a39d-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="3a39d-106">W tym przykładzie wybierzesz źródła danych dla istniejącego modelu danych, który został utworzony dla przykładowej firmy Litware, Inc. Aby wykonać te kroki, należy najpierw wykonać procedurę „Tworzenie nowego modelu danych”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Create a new data model" procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="3a39d-107">Otwieranie drzewa konfiguracji raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="3a39d-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="3a39d-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="3a39d-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="3a39d-109">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="3a39d-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="3a39d-110">Wstaw nowe mapowanie modelu.</span><span class="sxs-lookup"><span data-stu-id="3a39d-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="3a39d-111">W drzewie zaznacz element „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="3a39d-112">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="3a39d-112">Click Designer.</span></span>
3. <span data-ttu-id="3a39d-113">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="3a39d-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3a39d-114">Click New.</span></span>
    * <span data-ttu-id="3a39d-115">Spowoduje to utworzenie nowego rekordu, który przyporządkuje model danych do źródła danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="3a39d-116">W tym przykładzie modelu danych zostanie zmapowany do źródeł danych dla żądanego typu płatności: polecenia przelewu.</span><span class="sxs-lookup"><span data-stu-id="3a39d-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="3a39d-117">Istnieje możliwość zaprojektowania więcej niż jednego mapowania dla określonego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="3a39d-118">Na przykład można utworzyć mapowanie dla różnych typów płatności, na przykład dla poleceń zapłaty i poleceń przelewu.</span><span class="sxs-lookup"><span data-stu-id="3a39d-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="3a39d-119">W tym przykładzie utworzysz mapowanie dla poleceń przelewu.</span><span class="sxs-lookup"><span data-stu-id="3a39d-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="3a39d-120">W polu Nazwa wpisz „Mapowanie polecenia przelewu”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="3a39d-121">Mapowanie polecenia przelewu</span><span class="sxs-lookup"><span data-stu-id="3a39d-121">CT mapping</span></span>  
6. <span data-ttu-id="3a39d-122">W polu Opis wpisz „Mapowanie polecenia przelewu w modelu płatności”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="3a39d-123">Mapowanie polecenia przelewu w modelu płatności</span><span class="sxs-lookup"><span data-stu-id="3a39d-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="3a39d-124">W polu Definicja wpisz „CustomerCreditTransferInitiation”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="3a39d-125">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="3a39d-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="3a39d-126">Rozstrzygnij zmiany w definicji.</span><span class="sxs-lookup"><span data-stu-id="3a39d-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="3a39d-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3a39d-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="3a39d-128">Definiowanie wymaganych źródeł danych dla mapowania bieżącego modelu</span><span class="sxs-lookup"><span data-stu-id="3a39d-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="3a39d-129">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="3a39d-129">Click Designer.</span></span>
2. <span data-ttu-id="3a39d-130">W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="3a39d-131">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="3a39d-131">Click Add root.</span></span>
    * <span data-ttu-id="3a39d-132">Wprowadź to źródło danych, aby uzyskać dostęp do transakcji płatności.</span><span class="sxs-lookup"><span data-stu-id="3a39d-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="3a39d-133">W polu Nazwa wpisz „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="3a39d-134">Transakcje</span><span class="sxs-lookup"><span data-stu-id="3a39d-134">Transactions</span></span>  
5. <span data-ttu-id="3a39d-135">W polu Etykieta wpisz „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="3a39d-136">Transakcje</span><span class="sxs-lookup"><span data-stu-id="3a39d-136">Transactions</span></span>  
6. <span data-ttu-id="3a39d-137">W polu Pomoc wpisz „Wiersze arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="3a39d-138">Wiersze arkusza księgi</span><span class="sxs-lookup"><span data-stu-id="3a39d-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="3a39d-139">W polu Monituj o zapytanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a39d-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="3a39d-140">Wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a39d-140">Select Yes.</span></span>  
8. <span data-ttu-id="3a39d-141">W polu Tabela wpisz „LedgerJournalTrans”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="3a39d-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="3a39d-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="3a39d-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a39d-143">Click OK.</span></span>
    * <span data-ttu-id="3a39d-144">Wybierz tabelę LedgerJournalTrans jako źródło danych dla bieżącego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="3a39d-145">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="3a39d-146">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="3a39d-146">Click Add.</span></span>
    * <span data-ttu-id="3a39d-147">Kliknij przycisk Dodaj, aby dodać nowe pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="3a39d-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="3a39d-148">W polu Nazwa wpisz „$EndToEndID”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="3a39d-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="3a39d-149">$EndToEndID</span></span>  
13. <span data-ttu-id="3a39d-150">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="3a39d-150">Click Edit formula.</span></span>
14. <span data-ttu-id="3a39d-151">W drzewie zaznacz element „Ciąg\ZŁĄCZ”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="3a39d-152">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="3a39d-152">Click Add function.</span></span>
16. <span data-ttu-id="3a39d-153">W drzewie rozwiń węzeł „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="3a39d-154">W drzewie zaznacz element „Transakcje\Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="3a39d-155">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-155">Click Add data source.</span></span>
19. <span data-ttu-id="3a39d-156">W polu Formuła wpisz „CONCATENATE(Transakcje.Załącznik, "-", ”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="3a39d-157">Na końcu formuły wpisz [ , "-", ].</span><span class="sxs-lookup"><span data-stu-id="3a39d-157">Type [ , "-", ] at the end of the formula.</span></span>  
20. <span data-ttu-id="3a39d-158">W drzewie zaznacz element „Ciąg\TEKST”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="3a39d-159">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="3a39d-159">Click Add function.</span></span>
22. <span data-ttu-id="3a39d-160">W drzewie zaznacz element „Transakcje\Identyfikator rekordu(RecId)”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="3a39d-161">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-161">Click Add data source.</span></span>
24. <span data-ttu-id="3a39d-162">W polu Formuła wpisz „CONCATENATE(Transakcje.Załącznik, "-", TEKST(Transakcje.RecId))”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="3a39d-163">Na końcu formuły wpisz [))].</span><span class="sxs-lookup"><span data-stu-id="3a39d-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="3a39d-164">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3a39d-164">Click Save.</span></span>
    * <span data-ttu-id="3a39d-165">Upewnij się, że w utworzonej formule nie zostały wykryte żadne błędy.</span><span class="sxs-lookup"><span data-stu-id="3a39d-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="3a39d-166">Zobacz kartę BŁĘDY pod formantem edytora formuły.</span><span class="sxs-lookup"><span data-stu-id="3a39d-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="3a39d-167">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3a39d-167">Close the page.</span></span>
27. <span data-ttu-id="3a39d-168">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a39d-168">Click OK.</span></span>
    * <span data-ttu-id="3a39d-169">Dodaj pole obliczeniowe do tego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="3a39d-170">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="3a39d-170">Click Add.</span></span>
    * <span data-ttu-id="3a39d-171">Kliknij przycisk Dodaj, aby dodać nowe pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="3a39d-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="3a39d-172">W polu Nazwa wpisz „$Amount”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="3a39d-173">$Amount</span><span class="sxs-lookup"><span data-stu-id="3a39d-173">$Amount</span></span>  
30. <span data-ttu-id="3a39d-174">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="3a39d-174">Click Edit formula.</span></span>
31. <span data-ttu-id="3a39d-175">W drzewie rozwiń węzeł „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="3a39d-176">W drzewie zaznacz element „Transakcje\Debet(AmountCurDebit)”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="3a39d-177">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-177">Click Add data source.</span></span>
34. <span data-ttu-id="3a39d-178">W polu Formuła wpisz „Transakcje.AmountCurDebit - ”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="3a39d-179">Na końcu formuły wpisz [ - ].</span><span class="sxs-lookup"><span data-stu-id="3a39d-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="3a39d-180">W drzewie zaznacz element „Transakcje\Kredyt(AmountCurCredit)”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="3a39d-181">Kliknij opcję Dodaj źródło danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-181">Click Add data source.</span></span>
37. <span data-ttu-id="3a39d-182">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3a39d-182">Click Save.</span></span>
38. <span data-ttu-id="3a39d-183">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3a39d-183">Close the page.</span></span>
39. <span data-ttu-id="3a39d-184">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a39d-184">Click OK.</span></span>
    * <span data-ttu-id="3a39d-185">To spowoduje dodanie pola obliczeniowego $Amount do wybranego źródła danych dla bieżącego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="3a39d-186">W drzewie zaznacz element „Transakcje\$Amount”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="3a39d-187">W drzewie rozwiń węzeł „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="3a39d-188">W drzewie rozwiń lub zwiń węzeł „Transakcje\$Amount”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="3a39d-189">W drzewie rozwiń lub zwiń węzeł „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="3a39d-190">W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="3a39d-191">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="3a39d-191">Click Add root.</span></span>
    * <span data-ttu-id="3a39d-192">Wprowadź to źródło danych, aby uzyskać dostęp do szczegółów konta bankowego firmy.</span><span class="sxs-lookup"><span data-stu-id="3a39d-192">Enter this data source to access the company's bank account details.</span></span>  
46. <span data-ttu-id="3a39d-193">W polu nazwa wpisz „BankAccount”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="3a39d-194">BankAccount</span><span class="sxs-lookup"><span data-stu-id="3a39d-194">BankAccount</span></span>  
47. <span data-ttu-id="3a39d-195">W polu Etykieta wpisz „Konto bankowe”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="3a39d-196">Konto bankowe</span><span class="sxs-lookup"><span data-stu-id="3a39d-196">Bank Account</span></span>  
48. <span data-ttu-id="3a39d-197">W polu Pomoc wpisz „Konto bankowe”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="3a39d-198">Konto bankowe</span><span class="sxs-lookup"><span data-stu-id="3a39d-198">Bank Account</span></span>  
49. <span data-ttu-id="3a39d-199">W polu Monituj o zapytanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a39d-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="3a39d-200">Wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a39d-200">Select Yes.</span></span>  
50. <span data-ttu-id="3a39d-201">W polu Tabela wpisz „BankAccountTable”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="3a39d-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="3a39d-202">BankAccountTable</span></span>  
51. <span data-ttu-id="3a39d-203">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a39d-203">Click OK.</span></span>
    * <span data-ttu-id="3a39d-204">Wybierz tabelę BankAccountTable jako źródło danych dla bieżącego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="3a39d-205">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="3a39d-205">Click Add root.</span></span>
    * <span data-ttu-id="3a39d-206">Wprowadź to źródło danych, aby uzyskać dostęp do wymagań firmy.</span><span class="sxs-lookup"><span data-stu-id="3a39d-206">Enter this data source to access the company's requisites.</span></span>  
53. <span data-ttu-id="3a39d-207">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="3a39d-208">Firma</span><span class="sxs-lookup"><span data-stu-id="3a39d-208">Company</span></span>  
54. <span data-ttu-id="3a39d-209">W polu Etykieta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3a39d-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="3a39d-210">Informacje o firmie</span><span class="sxs-lookup"><span data-stu-id="3a39d-210">Company information</span></span>  
55. <span data-ttu-id="3a39d-211">W polu Pomoc wpisz „Informacje o firmie”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="3a39d-212">Informacje o firmie</span><span class="sxs-lookup"><span data-stu-id="3a39d-212">Company information</span></span>  
56. <span data-ttu-id="3a39d-213">W polu Monituj o zapytanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a39d-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="3a39d-214">Wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="3a39d-214">Select Yes.</span></span>  
57. <span data-ttu-id="3a39d-215">W polu Tabela wpisz „CompanyInfo”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="3a39d-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="3a39d-216">CompanyInfo</span></span>  
58. <span data-ttu-id="3a39d-217">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a39d-217">Click OK.</span></span>
    * <span data-ttu-id="3a39d-218">Wybierz tabelę CompanyInfo jako źródło danych dla bieżącego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="3a39d-219">W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="3a39d-220">Kliknij opcję Dodaj element główny.</span><span class="sxs-lookup"><span data-stu-id="3a39d-220">Click Add root.</span></span>
    * <span data-ttu-id="3a39d-221">Wstaw pole obliczeniowe jako nowe źródło danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="3a39d-222">W polu Nazwa wpisz „ProcessingDateTime”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="3a39d-223">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="3a39d-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="3a39d-224">W polu Etykieta wpisz „Data i godzina przetwarzania”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="3a39d-225">Data i godzina przetwarzania</span><span class="sxs-lookup"><span data-stu-id="3a39d-225">Processing date & time</span></span>  
63. <span data-ttu-id="3a39d-226">Kliknij opcję Edytuj formułę.</span><span class="sxs-lookup"><span data-stu-id="3a39d-226">Click Edit formula.</span></span>
64. <span data-ttu-id="3a39d-227">W drzewie zaznacz element „Data/godzina\SESSIONNOW”.</span><span class="sxs-lookup"><span data-stu-id="3a39d-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="3a39d-228">Kliknij opcję Dodaj funkcję.</span><span class="sxs-lookup"><span data-stu-id="3a39d-228">Click Add function.</span></span>
66. <span data-ttu-id="3a39d-229">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3a39d-229">Click Save.</span></span>
67. <span data-ttu-id="3a39d-230">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3a39d-230">Close the page.</span></span>
68. <span data-ttu-id="3a39d-231">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3a39d-231">Click OK.</span></span>
    * <span data-ttu-id="3a39d-232">Dodaj pole obliczeniowe ProcessingDateTime jako źródło danych dla bieżącego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="3a39d-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="3a39d-233">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3a39d-233">Click Save.</span></span>
70. <span data-ttu-id="3a39d-234">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3a39d-234">Close the page.</span></span>
71. <span data-ttu-id="3a39d-235">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3a39d-235">Close the page.</span></span>
72. <span data-ttu-id="3a39d-236">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3a39d-236">Close the page.</span></span>

