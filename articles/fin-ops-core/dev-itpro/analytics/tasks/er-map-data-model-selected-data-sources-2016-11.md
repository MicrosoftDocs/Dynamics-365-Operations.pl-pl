---
title: ER Mapowanie modelu danych na wybrane źródła danych
description: W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może mapować model danych raportowania elektronicznego (ER) na wybrane źródła danych Microsoft Dynamics 365 Finance.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2d09370b0e08897799d40c41c20c21b58e885dc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684314"
---
# <a name="er-map-data-model-to-selected-data-sources"></a><span data-ttu-id="0f7d1-103">ER Mapowanie modelu danych na wybrane źródła danych</span><span class="sxs-lookup"><span data-stu-id="0f7d1-103">ER Map data model to selected data sources</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0f7d1-104">W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może mapować model danych raportowania elektronicznego (ER) na wybrane źródła danych.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can map an Electronic reporting (ER) data model to selected data sources.</span></span> <span data-ttu-id="0f7d1-105">To mapowanie modelu będzie później używane jako źródło danych w konfiguracji formatu używanej do zarządzania dokumentami płatności elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-105">This model mapping will later be used as a data source in a format configuration that will be used to manage electronic payment documents.</span></span> <span data-ttu-id="0f7d1-106">W tym przykładzie zmapujesz model danych przykładowej firmy Litware, Inc. na źródła danych.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-106">In this example, you map a data model for sample company, Litware, Inc. to data sources.</span></span> <span data-ttu-id="0f7d1-107">W celu wykonania tych kroków należy najpierw wykonać kroki w procedurze „Wybór źródeł danych do mapowania modelu”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-107">To complete these steps, you must first complete the steps in the "Select data sources for model mapping" procedure.</span></span>


## <a name="open-er-configurations-tree"></a><span data-ttu-id="0f7d1-108">Otwórz drzewo konfiguracje raportowania w przedsiębiorstwie.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-108">Open ER configurations tree</span></span>
1. <span data-ttu-id="0f7d1-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="0f7d1-110">Kliknij opcję Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-110">Click Configurations.</span></span>

## <a name="select-created-model-mapping"></a><span data-ttu-id="0f7d1-111">Wybór utworzonego mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="0f7d1-111">Select created model mapping</span></span>
1. <span data-ttu-id="0f7d1-112">W drzewie zaznacz element „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-112">In the tree, select 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="0f7d1-113">Upewnij się, że wcześniej utworzono konfigurację modelu „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-113">Make sure that the model configuration "Payments (simplified model)" has been created in advance.</span></span> <span data-ttu-id="0f7d1-114">W przeciwnym razie teraz przerwij, wykonaj przewodnik po zadaniu „Tworzenie nowej konfiguracji z modelem danych wybranej domeny” i wróć do tego miejsca.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-114">Otherwise, stop now and return after completion of the task guide 'Create a new configuration with data model of the selected domain'.</span></span>  
2. <span data-ttu-id="0f7d1-115">Kliknij opcję Projektant modeli.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-115">Click Model designer.</span></span>
3. <span data-ttu-id="0f7d1-116">Kliknij opcję Mapuj model na źródło danych.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-116">Click Map model to datasource.</span></span>
4. <span data-ttu-id="0f7d1-117">Wybierz rekord „Mapowanie polecenia przelewu”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-117">Select the 'CT mapping' record.</span></span>
    * <span data-ttu-id="0f7d1-118">Mapowanie polecenia przelewu</span><span class="sxs-lookup"><span data-stu-id="0f7d1-118">CT mapping</span></span>  

## <a name="bind-created-data-sources-to-data-model-elements"></a><span data-ttu-id="0f7d1-119">Tworzenie powiązania między źródłami danych a elementami modelu danych</span><span class="sxs-lookup"><span data-stu-id="0f7d1-119">Bind created data sources to data model elements</span></span>
1. <span data-ttu-id="0f7d1-120">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-120">Click Designer.</span></span>
2. <span data-ttu-id="0f7d1-121">W drzewie zaznacz element „Data i godzina przetwarzania(ProcessingDateTime)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-121">In the tree, select 'Processing date & time(ProcessingDateTime)'.</span></span>
3. <span data-ttu-id="0f7d1-122">W drzewie zaznacz element „Data przetwarzania(ProcessingDateTime)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-122">In the tree, select 'Processing date(ProcessingDateTime)'.</span></span>
4. <span data-ttu-id="0f7d1-123">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-123">Click Bind.</span></span>
5. <span data-ttu-id="0f7d1-124">W drzewie zaznacz element „Identyfikator komunikatu płatności(MessageIdentification)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-124">In the tree, select 'Payment message identification(MessageIdentification)'.</span></span>
6. <span data-ttu-id="0f7d1-125">W drzewie rozwiń węzeł „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-125">In the tree, expand 'Transactions'.</span></span>
7. <span data-ttu-id="0f7d1-126">W drzewie zaznacz element „Transakcje\Arkusz z numerem partii(JournalNum)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-126">In the tree, select 'Transactions\Journal batch number(JournalNum)'.</span></span>
8. <span data-ttu-id="0f7d1-127">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-127">Click Bind.</span></span>
9. <span data-ttu-id="0f7d1-128">W drzewie zaznacz element „Płatności”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-128">In the tree, select 'Payments'.</span></span>
10. <span data-ttu-id="0f7d1-129">W drzewie zaznacz element „Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-129">In the tree, select 'Transactions'.</span></span>
11. <span data-ttu-id="0f7d1-130">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-130">Click Bind.</span></span>
12. <span data-ttu-id="0f7d1-131">W drzewie rozwiń węzeł „Płatności=Transakcje”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-131">In the tree, expand 'Payments= Transactions'.</span></span>
13. <span data-ttu-id="0f7d1-132">W drzewie rozwiń węzeł „Płatności=Transakcje\Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-132">In the tree, expand 'Payments= Transactions\Creditor'.</span></span>
14. <span data-ttu-id="0f7d1-133">W drzewie rozwiń węzeł „Płatności=Transakcje\Wierzyciel\Konto”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-133">In the tree, expand 'Payments= Transactions\Creditor\Account'.</span></span>
15. <span data-ttu-id="0f7d1-134">W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Konto\Kod waluty(Currency)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-134">In the tree, select 'Payments= Transactions\Creditor\Account\Currency code(Currency)'.</span></span>
16. <span data-ttu-id="0f7d1-135">W drzewie rozwiń węzeł „Transakcje\vendBankAccountInTransactionCompany()”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-135">In the tree, expand 'Transactions\vendBankAccountInTransactionCompany()'.</span></span>
17. <span data-ttu-id="0f7d1-136">W drzewie zaznacz element „Płatności=Transakcje\vendBankAccountInTransactionCompany()\Waluta(CurrencyCode)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-136">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)'.</span></span>
18. <span data-ttu-id="0f7d1-137">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-137">Click Bind.</span></span>
19. <span data-ttu-id="0f7d1-138">W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Konto\Kod IBAN(IBAN)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-138">In the tree, select 'Payments= Transactions\Creditor\Account\IBAN code(IBAN)'.</span></span>
20. <span data-ttu-id="0f7d1-139">W drzewie zaznacz element „Transakcje\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-139">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'.</span></span>
21. <span data-ttu-id="0f7d1-140">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-140">Click Bind.</span></span>
22. <span data-ttu-id="0f7d1-141">W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Konto\Numer”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-141">In the tree, select 'Payments= Transactions\Creditor\Account\Number'.</span></span>
23. <span data-ttu-id="0f7d1-142">W drzewie zaznacz element „Płatności=Transakcje\vendBankAccountInTransactionCompany()\Numer konta bankowego(AccountNum)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-142">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)'.</span></span>
24. <span data-ttu-id="0f7d1-143">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-143">Click Bind.</span></span>
25. <span data-ttu-id="0f7d1-144">W drzewie rozwiń węzeł „Płatności=Transakcje\Wierzyciel\Agent”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-144">In the tree, expand 'Payments= Transactions\Creditor\Agent'.</span></span>
26. <span data-ttu-id="0f7d1-145">W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Agent\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-145">In the tree, select 'Payments= Transactions\Creditor\Agent\Name'.</span></span>
27. <span data-ttu-id="0f7d1-146">W drzewie zaznacz element „Transakcje\vendBankAccountInTransactionCompany()\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-146">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Name'.</span></span>
28. <span data-ttu-id="0f7d1-147">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-147">Click Bind.</span></span>
29. <span data-ttu-id="0f7d1-148">W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Agent\Numer rozliczeniowy(RoutingNumber)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-148">In the tree, select 'Payments= Transactions\Creditor\Agent\Routing number(RoutingNumber)'.</span></span>
30. <span data-ttu-id="0f7d1-149">W drzewie zaznacz element „Płatności=Transakcje\vendBankAccountInTransactionCompany()\Numer rozliczeniowy(RegistrationNum)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-149">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)'.</span></span>
31. <span data-ttu-id="0f7d1-150">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-150">Click Bind.</span></span>
32. <span data-ttu-id="0f7d1-151">W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Agent\Kod SWIFT(SWIFT)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-151">In the tree, select 'Payments= Transactions\Creditor\Agent\SWIFT code(SWIFT)'.</span></span>
33. <span data-ttu-id="0f7d1-152">W drzewie zaznacz element „Płatności=Transakcje\vendBankAccountInTransactionCompany()\Kod SWIFT(SWIFTNo)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-152">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)'.</span></span>
34. <span data-ttu-id="0f7d1-153">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-153">Click Bind.</span></span>
35. <span data-ttu-id="0f7d1-154">W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-154">In the tree, select 'Payments= Transactions\Creditor\Name'.</span></span>
36. <span data-ttu-id="0f7d1-155">W drzewie rozwiń węzeł „Transakcje\findVendTable()”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-155">In the tree, expand 'Transactions\findVendTable()'.</span></span>
37. <span data-ttu-id="0f7d1-156">W drzewie zaznacz element „Transactions\findVendTable()\name()”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-156">In the tree, select 'Transactions\findVendTable()\name()'.</span></span>
38. <span data-ttu-id="0f7d1-157">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-157">Click Bind.</span></span>
39. <span data-ttu-id="0f7d1-158">W drzewie zaznacz element „Płatności=Transakcje\Kod waluty(Currency)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-158">In the tree, select 'Payments= Transactions\Currency code(Currency)'.</span></span>
40. <span data-ttu-id="0f7d1-159">W drzewie rozwiń węzeł „Transakcje\>Relacje”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-159">In the tree, expand 'Transactions\>Relations'.</span></span>
41. <span data-ttu-id="0f7d1-160">W drzewie rozwiń węzeł „Transakcje\>Relacje\Tabela walut(Currency)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-160">In the tree, expand 'Transactions\>Relations\Currency table(Currency)'.</span></span>
42. <span data-ttu-id="0f7d1-161">W drzewie zaznacz element „Transakcje\>Relacje\Tabela walut(Currency)\Kod waluty(CurrencyCodeISO)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-161">In the tree, select 'Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)'.</span></span>
43. <span data-ttu-id="0f7d1-162">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-162">Click Bind.</span></span>
44. <span data-ttu-id="0f7d1-163">W drzewie rozwiń węzeł „Płatności=Transakcje\Dłużnik”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-163">In the tree, expand 'Payments= Transactions\Debtor'.</span></span>
45. <span data-ttu-id="0f7d1-164">W drzewie rozwiń węzeł „Płatności=Transakcje\Dłużnik\Konto”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-164">In the tree, expand 'Payments= Transactions\Debtor\Account'.</span></span>
46. <span data-ttu-id="0f7d1-165">W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Konto\Kod waluty(Currency)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-165">In the tree, select 'Payments= Transactions\Debtor\Account\Currency code(Currency)'.</span></span>
47. <span data-ttu-id="0f7d1-166">W drzewie zaznacz element „Konto bankowe(BankAccount)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-166">In the tree, select 'Bank Account(BankAccount)'.</span></span>
48. <span data-ttu-id="0f7d1-167">W drzewie rozwiń węzeł „Konto bankowe(BankAccount)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-167">In the tree, expand 'Bank Account(BankAccount)'.</span></span>
49. <span data-ttu-id="0f7d1-168">W drzewie zaznacz element „Konto bankowe(BankAccount)\Waluta(CurrencyCode)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-168">In the tree, select 'Bank Account(BankAccount)\Currency(CurrencyCode)'.</span></span>
50. <span data-ttu-id="0f7d1-169">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-169">Click Bind.</span></span>
51. <span data-ttu-id="0f7d1-170">W drzewie zaznacz element „Konto bankowe(BankAccount)\IBAN”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-170">In the tree, select 'Bank Account(BankAccount)\IBAN'.</span></span>
52. <span data-ttu-id="0f7d1-171">W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Konto\Kod IBAN(IBAN)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-171">In the tree, select 'Payments= Transactions\Debtor\Account\IBAN code(IBAN)'.</span></span>
53. <span data-ttu-id="0f7d1-172">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-172">Click Bind.</span></span>
54. <span data-ttu-id="0f7d1-173">W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Konto\Numer”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-173">In the tree, select 'Payments= Transactions\Debtor\Account\Number'.</span></span>
55. <span data-ttu-id="0f7d1-174">W drzewie zaznacz element „Konto bankowe(BankAccount)\Numer konta bankowego(AccountNum)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-174">In the tree, select 'Bank Account(BankAccount)\Bank account number(AccountNum)'.</span></span>
56. <span data-ttu-id="0f7d1-175">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-175">Click Bind.</span></span>
57. <span data-ttu-id="0f7d1-176">W drzewie rozwiń węzeł „Płatności=Transakcje\Dłużnik\Agent”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-176">In the tree, expand 'Payments= Transactions\Debtor\Agent'.</span></span>
58. <span data-ttu-id="0f7d1-177">W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Agent\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-177">In the tree, select 'Payments= Transactions\Debtor\Agent\Name'.</span></span>
59. <span data-ttu-id="0f7d1-178">W drzewie zaznacz element „Konto bankowe(BankAccount)\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-178">In the tree, select 'Bank Account(BankAccount)\Name'.</span></span>
60. <span data-ttu-id="0f7d1-179">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-179">Click Bind.</span></span>
61. <span data-ttu-id="0f7d1-180">W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Agent\Numer rozliczeniowy(RoutingNumber)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-180">In the tree, select 'Payments= Transactions\Debtor\Agent\Routing number(RoutingNumber)'.</span></span>
62. <span data-ttu-id="0f7d1-181">W drzewie zaznacz element „Konto bankowe(BankAccount)\Numer rozliczeniowy(RegistrationNum)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-181">In the tree, select 'Bank Account(BankAccount)\Routing number(RegistrationNum)'.</span></span>
63. <span data-ttu-id="0f7d1-182">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-182">Click Bind.</span></span>
64. <span data-ttu-id="0f7d1-183">W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Agent\Kod SWIFT(SWIFT)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-183">In the tree, select 'Payments= Transactions\Debtor\Agent\SWIFT code(SWIFT)'.</span></span>
65. <span data-ttu-id="0f7d1-184">W drzewie zaznacz element „Konto bankowe(BankAccount)\Kod SWIFT(SWIFTNo)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-184">In the tree, select 'Bank Account(BankAccount)\SWIFT code(SWIFTNo)'.</span></span>
66. <span data-ttu-id="0f7d1-185">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-185">Click Bind.</span></span>
67. <span data-ttu-id="0f7d1-186">W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-186">In the tree, select 'Payments= Transactions\Debtor\Name'.</span></span>
68. <span data-ttu-id="0f7d1-187">W drzewie zaznacz element „Informacje o firmie(Company)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-187">In the tree, select 'Company information(Company)'.</span></span>
69. <span data-ttu-id="0f7d1-188">W drzewie rozwiń węzeł „Informacje o firmie(Company)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-188">In the tree, expand 'Company information(Company)'.</span></span>
70. <span data-ttu-id="0f7d1-189">W drzewie zaznacz element „Informacje o firmie(Company)\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-189">In the tree, select 'Company information(Company)\Name'.</span></span>
71. <span data-ttu-id="0f7d1-190">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-190">Click Bind.</span></span>
72. <span data-ttu-id="0f7d1-191">W drzewie zaznacz element „Płatności=Transakcje\Opis”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-191">In the tree, select 'Payments= Transactions\Description'.</span></span>
73. <span data-ttu-id="0f7d1-192">W drzewie zaznacz element „Transakcje\Opis(Txt)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-192">In the tree, select 'Transactions\Description(Txt)'.</span></span>
74. <span data-ttu-id="0f7d1-193">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-193">Click Bind.</span></span>
75. <span data-ttu-id="0f7d1-194">W drzewie zaznacz element „Płatności=Transakcje\Kod kompleksowej identyfikacji(End2EndID)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-194">In the tree, select 'Payments= Transactions\End to end identification code(End2EndID)'.</span></span>
76. <span data-ttu-id="0f7d1-195">W drzewie zaznacz element „Transakcje\$EndToEndID”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-195">In the tree, select 'Transactions\$EndToEndID'.</span></span>
77. <span data-ttu-id="0f7d1-196">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-196">Click Bind.</span></span>
78. <span data-ttu-id="0f7d1-197">W drzewie zaznacz element „Płatności=Transakcje\Wskazana kwota(InstructedAmount)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-197">In the tree, select 'Payments= Transactions\Instructed amount(InstructedAmount)'.</span></span>
79. <span data-ttu-id="0f7d1-198">W drzewie zaznacz element „Transakcje\$Amount”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-198">In the tree, select 'Transactions\$Amount'.</span></span>
80. <span data-ttu-id="0f7d1-199">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-199">Click Bind.</span></span>
81. <span data-ttu-id="0f7d1-200">W drzewie zaznacz element „Płatności=Transakcje\Data transakcji(TransactionDate)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-200">In the tree, select 'Payments= Transactions\Transaction date(TransactionDate)'.</span></span>
82. <span data-ttu-id="0f7d1-201">W drzewie zaznacz element „Transakcje\Data(TransDate)”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-201">In the tree, select 'Transactions\Date(TransDate)'.</span></span>
83. <span data-ttu-id="0f7d1-202">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-202">Click Bind.</span></span>

## <a name="validate-created-mapping"></a><span data-ttu-id="0f7d1-203">Sprawdzanie poprawności utworzonego mapowania</span><span class="sxs-lookup"><span data-stu-id="0f7d1-203">Validate created mapping</span></span>
1. <span data-ttu-id="0f7d1-204">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-204">Click Validate.</span></span>
    * <span data-ttu-id="0f7d1-205">Sprawdź poprawność nowego mapowania, aby się upewnić, że wszystkie powiązania są w porządku.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-205">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="0f7d1-206">Kliknij strzałkę, aby rozwinąć lub zwinąć sekcję Lista błędów.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-206">Click the arrow to expand or collapse the Error List section.</span></span>
3. <span data-ttu-id="0f7d1-207">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-207">Click Save.</span></span>
4. <span data-ttu-id="0f7d1-208">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-208">Close the page.</span></span>
5. <span data-ttu-id="0f7d1-209">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-209">Close the page.</span></span>
6. <span data-ttu-id="0f7d1-210">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-210">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a><span data-ttu-id="0f7d1-211">Zmiana stanu bieżącej wersji konfiguracji modelu</span><span class="sxs-lookup"><span data-stu-id="0f7d1-211">Change the status of the current version of model configuration</span></span>
1. <span data-ttu-id="0f7d1-212">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-212">Click Change status.</span></span>
    * <span data-ttu-id="0f7d1-213">Zmień stan żądanej konfiguracji modelu — z Wersja robocza na Zakończono, aby ją udostępnić na potrzeby projektu formatu płatności.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-213">Change the status of designed model configuration – from Draft to Completed to make it available for payment format design.</span></span>  
2. <span data-ttu-id="0f7d1-214">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-214">Click Complete.</span></span>
    * <span data-ttu-id="0f7d1-215">Wybierz opcję Zakończone.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-215">Select Complete.</span></span>  
3. <span data-ttu-id="0f7d1-216">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-216">In the Description field, type a value.</span></span>
    * <span data-ttu-id="0f7d1-217">Na przykład „wersja 1”.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-217">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="0f7d1-218">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-218">Click OK.</span></span>
5. <span data-ttu-id="0f7d1-219">Wybierz ukończoną wersję bieżącej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-219">Select the completed version of the current configuration.</span></span>
    * <span data-ttu-id="0f7d1-220">Należy zauważyć, że utworzona konfiguracja została zapisana jako ukończona wersja 1.</span><span class="sxs-lookup"><span data-stu-id="0f7d1-220">Note that the created configuration is saved as completed version 1.</span></span>  

