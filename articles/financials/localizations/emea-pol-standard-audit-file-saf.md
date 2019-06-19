---
title: Standardowy plik audytu (SAF) dla Polski
description: Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML. Ten temat zawiera informacje o formatach dla Polski.
author: LizaGolub
manager: AnnBe
ms.date: 02/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 274193
ms.assetid: b85c4019-f682-45bf-9a0d-c7549a2f1274
ms.search.region: Poland
ms.author: v-elgolu
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 57d6924c7b1fde450a14a5083e84a77fc6549ead
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556377"
---
# <a name="standard-audit-file-saf-for-poland"></a><span data-ttu-id="565c7-104">Standardowy plik audytu (SAF) dla Polski</span><span class="sxs-lookup"><span data-stu-id="565c7-104">Standard audit file (SAF) for Poland</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="565c7-105">Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="565c7-105">Users in legal entities in Poland can generate a Standard Audit File for Tax (SAF-T) in XML format.</span></span> <span data-ttu-id="565c7-106">Ten temat zawiera informacje o formatach dla Polski.</span><span class="sxs-lookup"><span data-stu-id="565c7-106">This topic provides information about the formats for Poland.</span></span> 

<span data-ttu-id="565c7-107">Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="565c7-107">Users in legal entities in Poland can generate a Standard Audit File for Tax (SAF-T) in XML format.</span></span> <span data-ttu-id="565c7-108">Ten dokument zawiera informacje o formatach dla Polski.</span><span class="sxs-lookup"><span data-stu-id="565c7-108">This document provides information about the formats for Poland.</span></span> <span data-ttu-id="565c7-109">Niniejszy dokument odnosi się do funkcji, która nie została jeszcze wdrożona.</span><span class="sxs-lookup"><span data-stu-id="565c7-109">This document refers to functionality that has not yet been released.</span></span>

## <a name="set-up-the-standard-audit-file-for-tax-for-poland"></a><span data-ttu-id="565c7-110">Konfigurowanie standardowego pliku audytu dla podatku dla Polski</span><span class="sxs-lookup"><span data-stu-id="565c7-110">Set up the Standard Audit File for Tax for Poland</span></span>
<span data-ttu-id="565c7-111">Aby określić format raportowania elektronicznego (ER) dla każdego schematu SAF-T, kliknij przycisk kolejno opcje **Księga główna > Ustawienia księgi > Parametry księgi głównej**, a następnie na karcie **Standardowy plik audytu dla podatków (SAF-T)** skonfiguruj konkretne formaty dla każdego z następujących schematów:</span><span class="sxs-lookup"><span data-stu-id="565c7-111">To specify an Electronic reporting (ER) format for each SAF-T scheme, click **General ledger > Ledger setup > General ledger parameters**, and then, on the **Standard Audit File for Taxes (SAF-T)** tab, set up a specific format for each of the following schemes:</span></span>

-   <span data-ttu-id="565c7-112">Księgi księgowania SAF</span><span class="sxs-lookup"><span data-stu-id="565c7-112">SAF Accounting books</span></span>
-   <span data-ttu-id="565c7-113">Wyciągi bankowe SAF</span><span class="sxs-lookup"><span data-stu-id="565c7-113">SAF Bank statements</span></span>
-   <span data-ttu-id="565c7-114">Zapasy SAF</span><span class="sxs-lookup"><span data-stu-id="565c7-114">SAF Inventory</span></span>
-   <span data-ttu-id="565c7-115">Rejestry SAF zakupów i sprzedaży objętych podatkiem VAT</span><span class="sxs-lookup"><span data-stu-id="565c7-115">SAF VAT sale and purchase registers</span></span>
-   <span data-ttu-id="565c7-116">Faktury VAT SAF</span><span class="sxs-lookup"><span data-stu-id="565c7-116">SAF VAT invoices</span></span>

<span data-ttu-id="565c7-117">Każdy format raportowania elektronicznego powinien być wstępnie zdefiniowany i pozwalać na aktualizowanie w module Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="565c7-117">Each ER format should be predefined and can be updated in ER.</span></span>

## <a name="generate-a-saf-accounting-books-file"></a><span data-ttu-id="565c7-118">Generowanie pliku ksiąg księgowania SAF</span><span class="sxs-lookup"><span data-stu-id="565c7-118">Generate a SAF Accounting books file</span></span>
<span data-ttu-id="565c7-119">Aby wygenerować plik ksiąg księgowania SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Księgi księgowania SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="565c7-119">To generate a SAF Accounting books file, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF Accounting books**, and set the following parameters.</span></span>

|<span data-ttu-id="565c7-120">Parametr</span><span class="sxs-lookup"><span data-stu-id="565c7-120">Parameter</span></span>                                        |  <span data-ttu-id="565c7-121">opis</span><span class="sxs-lookup"><span data-stu-id="565c7-121">Description</span></span>            |
|-------------------------------------------------|-------------------------|
| <span data-ttu-id="565c7-122">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-122">**From date**</span></span>                                   | <span data-ttu-id="565c7-123">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-123">Specify the first date to export reporting data for.</span></span> |
| <span data-ttu-id="565c7-124">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-124">**To date**</span></span>                                     | <span data-ttu-id="565c7-125">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-125">Specify the last date to export reporting data for.</span></span>  |
| <span data-ttu-id="565c7-126">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="565c7-126">**Authority identification**</span></span>                    | <span data-ttu-id="565c7-127">Określ identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-127">Specify the identifier of the tax authority to use in the export file.</span></span>|
| <span data-ttu-id="565c7-128">**Warstwa księgowania**</span><span class="sxs-lookup"><span data-stu-id="565c7-128">**Posting layer**</span></span>                               | <span data-ttu-id="565c7-129">Umożliwia wybranie warstwy księgowania, od której mają być uwzględniane transakcje.</span><span class="sxs-lookup"><span data-stu-id="565c7-129">Select the posting layer to consider transactions from.</span></span> <span data-ttu-id="565c7-130">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-130">This parameter affects only the ZOiS? part of the export file.</span></span> |
| <span data-ttu-id="565c7-131">**Czy saldo otwarcia ma być pokazywane jako obroty?**</span><span class="sxs-lookup"><span data-stu-id="565c7-131">**Should opening balance be shown by turnover**</span></span> | <span data-ttu-id="565c7-132">Jeśli ten parametr jest zaznaczony, transakcje otwarcia mają wpływ na obroty narastająco.</span><span class="sxs-lookup"><span data-stu-id="565c7-132">If this parameter is selected, opening transactions affect accumulated turnover.</span></span> <span data-ttu-id="565c7-133">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-133">This parameter affects only the ZOiS export file part.</span></span> |
| <span data-ttu-id="565c7-134">**Saldo rozwarte**</span><span class="sxs-lookup"><span data-stu-id="565c7-134">**Separate balance**</span></span>                            | <span data-ttu-id="565c7-135">Ten parametr można włączać dla kont głównych, w których jest oznaczony odnośny parametr.</span><span class="sxs-lookup"><span data-stu-id="565c7-135">This parameter can be considered for main accounts where the corresponding parameter is marked.</span></span> <span data-ttu-id="565c7-136">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-136">This parameter affects only the ZOiS export file part.</span></span>     |
| <span data-ttu-id="565c7-137">**Transakcje zamknięcia**</span><span class="sxs-lookup"><span data-stu-id="565c7-137">**Closing transactions**</span></span>                        | <span data-ttu-id="565c7-138">Jeśli ten parametr jest zaznaczony, transakcje zamknięcia będą uwzględnione w eksportowanych danych.</span><span class="sxs-lookup"><span data-stu-id="565c7-138">If this parameter is selected, closing transactions will be included in the data that is exported.</span></span> <span data-ttu-id="565c7-139">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-139">This parameter affects only the ZOiS? export file part.</span></span> |

<span data-ttu-id="565c7-140">Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="565c7-140">You can specify additional selection parameters by using **Filter** functionality on the **Records to include** tab.</span></span>

## <a name="generate-a-saf-bank-statement-file"></a><span data-ttu-id="565c7-141">Generowanie pliku wyciągu bankowego SAF</span><span class="sxs-lookup"><span data-stu-id="565c7-141">Generate a SAF Bank statement file</span></span>
<span data-ttu-id="565c7-142">Aby wygenerować plik wyciągu bankowego SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Wyciąg bankowy SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="565c7-142">To generate a SAF Bank statement file, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF Bank statement**, and set the following parameters.</span></span>

| <span data-ttu-id="565c7-143">Parametr</span><span class="sxs-lookup"><span data-stu-id="565c7-143">Parameter</span></span>                    | <span data-ttu-id="565c7-144">opis</span><span class="sxs-lookup"><span data-stu-id="565c7-144">Description</span></span>                                                                        |
|------------------------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="565c7-145">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-145">**From date**</span></span>                | <span data-ttu-id="565c7-146">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-146">Specify the first date to export reporting data for.</span></span>                               |
| <span data-ttu-id="565c7-147">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-147">**To date**</span></span>                  | <span data-ttu-id="565c7-148">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-148">Specify the last date to export reporting data for.</span></span>                                |
| <span data-ttu-id="565c7-149">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="565c7-149">**Authority identification**</span></span> | <span data-ttu-id="565c7-150">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-150">In the list, select the identifier of the tax authority to use in the export file.</span></span> |
| <span data-ttu-id="565c7-151">**Konto bankowe**</span><span class="sxs-lookup"><span data-stu-id="565c7-151">**Bank account**</span></span>             | <span data-ttu-id="565c7-152">Umożliwia określenie rachunku bankowego, dla którego mają zostać wyeksportowane transakcje.</span><span class="sxs-lookup"><span data-stu-id="565c7-152">Specify the bank account to export transactions for.</span></span>                               |

 

## <a name="generate-a-saf-inventory-file"></a><span data-ttu-id="565c7-153">Generowanie pliku zapasów SAF</span><span class="sxs-lookup"><span data-stu-id="565c7-153">Generate a SAF Inventory file</span></span>
<span data-ttu-id="565c7-154">Aby wygenerować plik zapasów SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Zapasy SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="565c7-154">To generate a SAF Inventory file, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF Inventory**, and set the following parameters.</span></span>

| <span data-ttu-id="565c7-155">Parametr</span><span class="sxs-lookup"><span data-stu-id="565c7-155">Parameter</span></span>                    | <span data-ttu-id="565c7-156">opis</span><span class="sxs-lookup"><span data-stu-id="565c7-156">Description</span></span>                                                                        |
|------------------------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="565c7-157">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-157">**From date**</span></span>                | <span data-ttu-id="565c7-158">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-158">Specify the first date to export reporting data for.</span></span>                               |
| <span data-ttu-id="565c7-159">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-159">**To date**</span></span>                  | <span data-ttu-id="565c7-160">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-160">Specify the last date to export reporting data for.</span></span>                                |
| <span data-ttu-id="565c7-161">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="565c7-161">**Authority identification**</span></span> | <span data-ttu-id="565c7-162">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-162">In the list, select the identifier of the tax authority to use in the export file.</span></span> |
| <span data-ttu-id="565c7-163">**Magazyn**</span><span class="sxs-lookup"><span data-stu-id="565c7-163">**Warehouse**</span></span>                | <span data-ttu-id="565c7-164">Określ magazyn, dla którego mają zostać wyeksportowane transakcje.</span><span class="sxs-lookup"><span data-stu-id="565c7-164">Specify the warehouse to export transactions for.</span></span>                                  |

### 

## <a name="generate-a-saf-vat-sales-and-purchase-register"></a><span data-ttu-id="565c7-165">Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT</span><span class="sxs-lookup"><span data-stu-id="565c7-165">Generate a SAF VAT sales and purchase register</span></span>
<span data-ttu-id="565c7-166">Zanim będzie można wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem od towarów i usług (VAT), należy wykonać następujące dodatkowe czynności konfiguracyjne:</span><span class="sxs-lookup"><span data-stu-id="565c7-166">Before you can generate a SAF value-added tax (VAT) sales and purchase register, you must complete the following additional setup:</span></span>

-   <span data-ttu-id="565c7-167">Skonfiguruj urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="565c7-167">Set up sales tax authorities.</span></span>
-   <span data-ttu-id="565c7-168">Konfigurowanie kodów podatków dla raportowania podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="565c7-168">Set up sales tax codes for VAT reporting.</span></span>
-   <span data-ttu-id="565c7-169">Ustawianie kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="565c7-169">Set up sales tax codes.</span></span>
-   <span data-ttu-id="565c7-170">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-170">Configure the ER model, and format for the report.</span></span>

<span data-ttu-id="565c7-171">Aby uzyskać więcej informacji o ustawieniach deklaracji VAT, zobacz [Raportowanie podatku VAT (UE)](emea-vat-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="565c7-171">For more information about the setup of VAT statements, see [(EU) VAT reporting](emea-vat-reporting.md).</span></span>

### <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="565c7-172">Konfigurowanie urzędów skarbowych</span><span class="sxs-lookup"><span data-stu-id="565c7-172">Set up sales tax authorities</span></span>

<span data-ttu-id="565c7-173">Aby uzyskać ogólne informacje dotyczące sposobu konfigurowania urzędu skarbowego, zobacz [Konfigurowanie urzędów skarbowych (przewodnik po zadaniu)](../general-ledger/tasks/set-up-sales-tax-authorities.md).</span><span class="sxs-lookup"><span data-stu-id="565c7-173">For general information about how to set up a sales tax authority, see [Set up sales tax authorities (Task guide)](../general-ledger/tasks/set-up-sales-tax-authorities.md).</span></span> <span data-ttu-id="565c7-174">Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT w wymaganym formacie dla odpowiedniego urzędu skarbowego, należy zdefiniować układ raportu dla urzędów skarbowych.</span><span class="sxs-lookup"><span data-stu-id="565c7-174">To generate a SAF VAT sales and purchase register in the required format for the appropriate tax authority, you must set up the report layout for sales tax authorities.</span></span> <span data-ttu-id="565c7-175">Na stronie **Urzędy skarbowe** (**Podatek > Podatki pośrednie > Podatek > Urzędy skarbowe**) w polu **Układ raportu** zaznacz wartość **Domyślnie**.</span><span class="sxs-lookup"><span data-stu-id="565c7-175">On the **Sales tax authorities** page (**Tax > Indirect taxes > Sales tax > Sales tax authorities**), set the **Report layout** field to **Default**.</span></span> <span data-ttu-id="565c7-176">Zaznacz ten sam urząd skarbowy dla okresu rozliczeniowego podatku, który będzie używany dla kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="565c7-176">Select the same sales tax authority for the sales tax settlement period that will be used for the sales tax codes.</span></span>

### <a name="set-up-sales-tax-codes-and-sales-tax-reporting-codes"></a><span data-ttu-id="565c7-177">Konfigurowanie kodów podatków i kodów sprawozdawczości podatkowej</span><span class="sxs-lookup"><span data-stu-id="565c7-177">Set up sales tax codes and sales tax reporting codes</span></span>

<span data-ttu-id="565c7-178">Kod raportowania jest liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="565c7-178">A reporting code is an integer value.</span></span> <span data-ttu-id="565c7-179">Kody raportowania powinny być numerowane zgodnie z regułami obowiązującymi w firmie.</span><span class="sxs-lookup"><span data-stu-id="565c7-179">Reporting codes should be numbered according to the company's rules.</span></span> <span data-ttu-id="565c7-180">Jednak zalecamy, aby różnicować kody według kierunku podatku.</span><span class="sxs-lookup"><span data-stu-id="565c7-180">However, we recommend that you vary the codes by tax direction.</span></span> <span data-ttu-id="565c7-181">Na przykład zdefiniuj kod 5-cyfrowy i tak ustaw kody dla wszystkich transakcji wychodzących, które powinny być odzwierciedlane w pierwszej części schematu podatku VAT, aby były mniejsze lub równe 19999.</span><span class="sxs-lookup"><span data-stu-id="565c7-181">For example, use a five-digit code, and set the codes for all outgoing transactions, which should be reflected in the first part of the VAT scheme, so that they are less than or equal to 19999.</span></span> <span data-ttu-id="565c7-182">Natomiast dla wszystkich transakcji przychodzących, które powinny być wykazywane w drugiej części systemu podatku VAT, ustaw kody tak, aby były większe lub równe 20000.</span><span class="sxs-lookup"><span data-stu-id="565c7-182">Set the codes for all incoming transactions, which should be reflected in the second part of the VAT scheme, so that they are more than or equal to 20000.</span></span> <span data-ttu-id="565c7-183">W ten sposób uprościsz konfigurację raportów i eksportu danych, która opiera się na transakcjach podatkowych agregowanych według kodów raportowania.</span><span class="sxs-lookup"><span data-stu-id="565c7-183">In this way, you simplify the setup for reports and for data export that is based on tax transactions that are aggregated by reporting codes.</span></span> <span data-ttu-id="565c7-184">Oto przykład pokazujący użycie kodów sprawozdawczości podatkowej do generowania rejestru SAF sprzedaży i zakupów objętych podatkiem VAT.</span><span class="sxs-lookup"><span data-stu-id="565c7-184">Here is an example that shows how you can use sales tax reporting codes to generate a SAF VAT sales and purchase register.</span></span> <span data-ttu-id="565c7-185">W tym przykładzie kody raportowania są w formacie *ABBCC*.</span><span class="sxs-lookup"><span data-stu-id="565c7-185">For this example, reporting codes are in the format *ABBCC*.</span></span> <span data-ttu-id="565c7-186">Ten format składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="565c7-186">This format consists of the following parts:</span></span>

-   <span data-ttu-id="565c7-187">**A** — Kierunek transakcji.</span><span class="sxs-lookup"><span data-stu-id="565c7-187">**A** - The transaction direction.</span></span> <span data-ttu-id="565c7-188">Wartość wynosi **1** dla podatków wychodzących, **2** dla podatków przychodzących i **3** dla korekt.</span><span class="sxs-lookup"><span data-stu-id="565c7-188">The value is **1** for outgoing, **2** for incoming, **3** for corrections.</span></span>
-   <span data-ttu-id="565c7-189">**BB** — Kod podatku.</span><span class="sxs-lookup"><span data-stu-id="565c7-189">**BB** - The tax code.</span></span> <span data-ttu-id="565c7-190">Numeracja zachowuje kolejność wśród wszystkich kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="565c7-190">The numbering is sequential among all tax codes.</span></span>
-   <span data-ttu-id="565c7-191">**CC** — Numer typu transakcji wewnątrz kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="565c7-191">**CC**-   The transaction type number within a tax code.</span></span> <span data-ttu-id="565c7-192">Parz tabela poniżej.</span><span class="sxs-lookup"><span data-stu-id="565c7-192">See the following table.</span></span>

| <span data-ttu-id="565c7-193">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="565c7-193">Transaction type</span></span>                      | <span data-ttu-id="565c7-194">Numer typu transakcji</span><span class="sxs-lookup"><span data-stu-id="565c7-194">Transaction type number</span></span>     |
|---------------------------------------|-----------------------------|
| <span data-ttu-id="565c7-195">**Sprzedaż opodatkowana**</span><span class="sxs-lookup"><span data-stu-id="565c7-195">**Taxable Sales**</span></span>                     | <span data-ttu-id="565c7-196">01</span><span class="sxs-lookup"><span data-stu-id="565c7-196">01</span></span>                          |
| <span data-ttu-id="565c7-197">**Sprzedaż wolna od podatku**</span><span class="sxs-lookup"><span data-stu-id="565c7-197">**Tax-free sales**</span></span>                    | <span data-ttu-id="565c7-198">02</span><span class="sxs-lookup"><span data-stu-id="565c7-198">02</span></span>                          |
| <span data-ttu-id="565c7-199">**Podatek należny**</span><span class="sxs-lookup"><span data-stu-id="565c7-199">**Sales tax payable**</span></span>                 | <span data-ttu-id="565c7-200">03</span><span class="sxs-lookup"><span data-stu-id="565c7-200">03</span></span>                          |
| <span data-ttu-id="565c7-201">**Opodatkowana faktura korygująca sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="565c7-201">**Taxable sales credit note**</span></span>         | <span data-ttu-id="565c7-202">04</span><span class="sxs-lookup"><span data-stu-id="565c7-202">04</span></span>                          |
| <span data-ttu-id="565c7-203">**Faktura korygująca sprzedaży zwolnionej z podatku**</span><span class="sxs-lookup"><span data-stu-id="565c7-203">**Tax exempt sales credit note**</span></span>      | <span data-ttu-id="565c7-204">05</span><span class="sxs-lookup"><span data-stu-id="565c7-204">05</span></span>                          |
| <span data-ttu-id="565c7-205">**Podatek od faktury korygującej sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="565c7-205">**Sales tax on sales credit note**</span></span>    | <span data-ttu-id="565c7-206">6</span><span class="sxs-lookup"><span data-stu-id="565c7-206">06</span></span>                          |
| <span data-ttu-id="565c7-207">**Zakup podlegający opodatkowaniu**</span><span class="sxs-lookup"><span data-stu-id="565c7-207">**Taxable purchases**</span></span>                 | <span data-ttu-id="565c7-208">07</span><span class="sxs-lookup"><span data-stu-id="565c7-208">07</span></span>                          |
| <span data-ttu-id="565c7-209">**Zakup wolny od podatku**</span><span class="sxs-lookup"><span data-stu-id="565c7-209">**Tax-free purchase**</span></span>                 | <span data-ttu-id="565c7-210">08</span><span class="sxs-lookup"><span data-stu-id="565c7-210">08</span></span>                          |
| <span data-ttu-id="565c7-211">**Podatek naliczony**</span><span class="sxs-lookup"><span data-stu-id="565c7-211">**Sales tax receivable**</span></span>              | <span data-ttu-id="565c7-212">09</span><span class="sxs-lookup"><span data-stu-id="565c7-212">09</span></span>                          |
| <span data-ttu-id="565c7-213">**Import opodatkowany**</span><span class="sxs-lookup"><span data-stu-id="565c7-213">**Taxable import**</span></span>                    | <span data-ttu-id="565c7-214">10</span><span class="sxs-lookup"><span data-stu-id="565c7-214">10</span></span>                          |
| <span data-ttu-id="565c7-215">**Przeciwstawna wartość importu podlegająca opodatkowaniu**</span><span class="sxs-lookup"><span data-stu-id="565c7-215">**Offset taxable import**</span></span>             | <span data-ttu-id="565c7-216">11</span><span class="sxs-lookup"><span data-stu-id="565c7-216">11</span></span>                          |
| <span data-ttu-id="565c7-217">**Podatek nienaliczony**</span><span class="sxs-lookup"><span data-stu-id="565c7-217">**Use tax**</span></span>                           | <span data-ttu-id="565c7-218">12</span><span class="sxs-lookup"><span data-stu-id="565c7-218">12</span></span>                          |
| <span data-ttu-id="565c7-219">**Konto przeciwstawne podatku nienaliczonego**</span><span class="sxs-lookup"><span data-stu-id="565c7-219">**Offset use tax**</span></span>                    | <span data-ttu-id="565c7-220">13</span><span class="sxs-lookup"><span data-stu-id="565c7-220">13</span></span>                          |
| <span data-ttu-id="565c7-221">**Opodatkowana faktura korygująca zakupu**</span><span class="sxs-lookup"><span data-stu-id="565c7-221">**Taxable purchase credit note**</span></span>      | <span data-ttu-id="565c7-222">14</span><span class="sxs-lookup"><span data-stu-id="565c7-222">14</span></span>                          |
| <span data-ttu-id="565c7-223">**Faktura korygująca zakupu zwolnionego z podatku**</span><span class="sxs-lookup"><span data-stu-id="565c7-223">**Tax exempt purchase credit note**</span></span>   | <span data-ttu-id="565c7-224">15</span><span class="sxs-lookup"><span data-stu-id="565c7-224">15</span></span>                          |
| <span data-ttu-id="565c7-225">**Podatek od faktury korygującej zakupu**</span><span class="sxs-lookup"><span data-stu-id="565c7-225">**Sales tax on purchase credit note**</span></span> | <span data-ttu-id="565c7-226">16</span><span class="sxs-lookup"><span data-stu-id="565c7-226">16</span></span>                          |
| <span data-ttu-id="565c7-227">**Opodatkowana faktura korygująca importu**</span><span class="sxs-lookup"><span data-stu-id="565c7-227">**Taxable import credit note**</span></span>        | <span data-ttu-id="565c7-228">17</span><span class="sxs-lookup"><span data-stu-id="565c7-228">17</span></span>                          |
| <span data-ttu-id="565c7-229">**Faktura korygująca przeciwstawnej wartości importu podlegającej opodatkowaniu**</span><span class="sxs-lookup"><span data-stu-id="565c7-229">**Offset taxable import credit note**</span></span> | <span data-ttu-id="565c7-230">18</span><span class="sxs-lookup"><span data-stu-id="565c7-230">18</span></span>                          |

<span data-ttu-id="565c7-231">W poniższej tabeli przedstawiono kody podatków i kody sprawozdawczości podatkowej dla tego przykładu.</span><span class="sxs-lookup"><span data-stu-id="565c7-231">The following table shows the sales tax codes and sales tax reporting codes for this example.</span></span>

<table width="100%">
<tbody>
<tr>
<td><span data-ttu-id="565c7-232"><strong>Kod podatku</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-232"><strong>Sales tax code</strong></span></span></td>
<td><span data-ttu-id="565c7-233"><strong>Kod raportowania podatku</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-233"><strong>Sales tax reporting code</strong></span></span></td>
<td><span data-ttu-id="565c7-234"><strong>Opis</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-234"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="565c7-235"><strong>Nazwa znacznika w podatku VAT SAF-T</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-235"><strong>Tag name in SAF-T VAT</strong></span></span></td>
<td><span data-ttu-id="565c7-236"><strong>Znak w podatku VAT SAF-T</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-236"><strong>Sign in SAF-T VAT</strong></span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="565c7-237"><strong>ExportCust</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-237"><strong>ExportCust</strong></span></span></td>
<td><span data-ttu-id="565c7-238">10101</span><span class="sxs-lookup"><span data-stu-id="565c7-238">10101</span></span></td>
<td><span data-ttu-id="565c7-239">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="565c7-239">Taxable sales</span></span></td>
<td><span data-ttu-id="565c7-240">K_11</span><span class="sxs-lookup"><span data-stu-id="565c7-240">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-241">10102</span><span class="sxs-lookup"><span data-stu-id="565c7-241">10102</span></span></td>
<td><span data-ttu-id="565c7-242">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-242">Tax-free sale</span></span></td>
<td><span data-ttu-id="565c7-243">K_11</span><span class="sxs-lookup"><span data-stu-id="565c7-243">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-244">10104</span><span class="sxs-lookup"><span data-stu-id="565c7-244">10104</span></span></td>
<td><span data-ttu-id="565c7-245">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-245">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="565c7-246">K_11</span><span class="sxs-lookup"><span data-stu-id="565c7-246">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-247">10105</span><span class="sxs-lookup"><span data-stu-id="565c7-247">10105</span></span></td>
<td><span data-ttu-id="565c7-248">Faktura korygująca sprzedaży zwolnionej z podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-248">Tax exempt sales credit note</span></span></td>
<td><span data-ttu-id="565c7-249">K_11</span><span class="sxs-lookup"><span data-stu-id="565c7-249">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="565c7-250"><strong>Art100</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-250"><strong>Art100</strong></span></span></td>
<td><span data-ttu-id="565c7-251">10201</span><span class="sxs-lookup"><span data-stu-id="565c7-251">10201</span></span></td>
<td><span data-ttu-id="565c7-252">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="565c7-252">Taxable sales</span></span></td>
<td><span data-ttu-id="565c7-253">K_12</span><span class="sxs-lookup"><span data-stu-id="565c7-253">K_12</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-254">10204</span><span class="sxs-lookup"><span data-stu-id="565c7-254">10204</span></span></td>
<td><span data-ttu-id="565c7-255">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-255">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="565c7-256">K_12</span><span class="sxs-lookup"><span data-stu-id="565c7-256">K_12</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="565c7-257"><strong>VAT22_23</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-257"><strong>VAT22_23</strong></span></span></td>
<td><span data-ttu-id="565c7-258">10301</span><span class="sxs-lookup"><span data-stu-id="565c7-258">10301</span></span></td>
<td><span data-ttu-id="565c7-259">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="565c7-259">Taxable sales</span></span></td>
<td><span data-ttu-id="565c7-260">K_19</span><span class="sxs-lookup"><span data-stu-id="565c7-260">K_19</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-261">10302</span><span class="sxs-lookup"><span data-stu-id="565c7-261">10302</span></span></td>
<td><span data-ttu-id="565c7-262">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-262">Tax-free sale</span></span></td>
<td><span data-ttu-id="565c7-263">K_10</span><span class="sxs-lookup"><span data-stu-id="565c7-263">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-264">10303</span><span class="sxs-lookup"><span data-stu-id="565c7-264">10303</span></span></td>
<td><span data-ttu-id="565c7-265">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="565c7-265">Sales tax payable</span></span></td>
<td><span data-ttu-id="565c7-266">K_20</span><span class="sxs-lookup"><span data-stu-id="565c7-266">K_20</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-267">10304</span><span class="sxs-lookup"><span data-stu-id="565c7-267">10304</span></span></td>
<td><span data-ttu-id="565c7-268">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-268">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="565c7-269">K_19</span><span class="sxs-lookup"><span data-stu-id="565c7-269">K_19</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-270">10306</span><span class="sxs-lookup"><span data-stu-id="565c7-270">10306</span></span></td>
<td><span data-ttu-id="565c7-271">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-271">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="565c7-272">K_20</span><span class="sxs-lookup"><span data-stu-id="565c7-272">K_20</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="565c7-273"><strong>VAT7_8</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-273"><strong>VAT7_8</strong></span></span></td>
<td><span data-ttu-id="565c7-274">10401</span><span class="sxs-lookup"><span data-stu-id="565c7-274">10401</span></span></td>
<td><span data-ttu-id="565c7-275">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="565c7-275">Taxable sales</span></span></td>
<td><span data-ttu-id="565c7-276">K_17</span><span class="sxs-lookup"><span data-stu-id="565c7-276">K_17</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-277">10402</span><span class="sxs-lookup"><span data-stu-id="565c7-277">10402</span></span></td>
<td><span data-ttu-id="565c7-278">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-278">Tax-free sale</span></span></td>
<td><span data-ttu-id="565c7-279">K_10</span><span class="sxs-lookup"><span data-stu-id="565c7-279">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-280">10403</span><span class="sxs-lookup"><span data-stu-id="565c7-280">10403</span></span></td>
<td><span data-ttu-id="565c7-281">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="565c7-281">Sales tax payable</span></span></td>
<td><span data-ttu-id="565c7-282">K_18</span><span class="sxs-lookup"><span data-stu-id="565c7-282">K_18</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-283">10404</span><span class="sxs-lookup"><span data-stu-id="565c7-283">10404</span></span></td>
<td><span data-ttu-id="565c7-284">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-284">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="565c7-285">K_17</span><span class="sxs-lookup"><span data-stu-id="565c7-285">K_17</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-286">10406</span><span class="sxs-lookup"><span data-stu-id="565c7-286">10406</span></span></td>
<td><span data-ttu-id="565c7-287">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-287">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="565c7-288">K_18</span><span class="sxs-lookup"><span data-stu-id="565c7-288">K_18</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="565c7-289"><strong>VAT5</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-289"><strong>VAT5</strong></span></span></td>
<td><span data-ttu-id="565c7-290">10501</span><span class="sxs-lookup"><span data-stu-id="565c7-290">10501</span></span></td>
<td><span data-ttu-id="565c7-291">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="565c7-291">Taxable sales</span></span></td>
<td><span data-ttu-id="565c7-292">K_15</span><span class="sxs-lookup"><span data-stu-id="565c7-292">K_15</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-293">10502</span><span class="sxs-lookup"><span data-stu-id="565c7-293">10502</span></span></td>
<td><span data-ttu-id="565c7-294">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-294">Tax-free sale</span></span></td>
<td><span data-ttu-id="565c7-295">K_10</span><span class="sxs-lookup"><span data-stu-id="565c7-295">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-296">10503</span><span class="sxs-lookup"><span data-stu-id="565c7-296">10503</span></span></td>
<td><span data-ttu-id="565c7-297">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="565c7-297">Sales tax payable</span></span></td>
<td><span data-ttu-id="565c7-298">K_16</span><span class="sxs-lookup"><span data-stu-id="565c7-298">K_16</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-299">10504</span><span class="sxs-lookup"><span data-stu-id="565c7-299">10504</span></span></td>
<td><span data-ttu-id="565c7-300">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-300">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="565c7-301">K_15</span><span class="sxs-lookup"><span data-stu-id="565c7-301">K_15</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-302">10506</span><span class="sxs-lookup"><span data-stu-id="565c7-302">10506</span></span></td>
<td><span data-ttu-id="565c7-303">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-303">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="565c7-304">K_16</span><span class="sxs-lookup"><span data-stu-id="565c7-304">K_16</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="565c7-305"><strong>VAT0</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-305"><strong>VAT0</strong></span></span></td>
<td><span data-ttu-id="565c7-306">10601</span><span class="sxs-lookup"><span data-stu-id="565c7-306">10601</span></span></td>
<td><span data-ttu-id="565c7-307">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="565c7-307">Taxable sales</span></span></td>
<td><span data-ttu-id="565c7-308">K_13</span><span class="sxs-lookup"><span data-stu-id="565c7-308">K_13</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-309">10602</span><span class="sxs-lookup"><span data-stu-id="565c7-309">10602</span></span></td>
<td><span data-ttu-id="565c7-310">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-310">Tax-free sale</span></span></td>
<td><span data-ttu-id="565c7-311">K_10</span><span class="sxs-lookup"><span data-stu-id="565c7-311">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-312">10604</span><span class="sxs-lookup"><span data-stu-id="565c7-312">10604</span></span></td>
<td><span data-ttu-id="565c7-313">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-313">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="565c7-314">K_13</span><span class="sxs-lookup"><span data-stu-id="565c7-314">K_13</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="565c7-315"><strong>ART129</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-315"><strong>ART129</strong></span></span></td>
<td><span data-ttu-id="565c7-316">10701</span><span class="sxs-lookup"><span data-stu-id="565c7-316">10701</span></span></td>
<td><span data-ttu-id="565c7-317">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="565c7-317">Taxable sales</span></span></td>
<td><span data-ttu-id="565c7-318">K_14</span><span class="sxs-lookup"><span data-stu-id="565c7-318">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-319">10702</span><span class="sxs-lookup"><span data-stu-id="565c7-319">10702</span></span></td>
<td><span data-ttu-id="565c7-320">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-320">Tax-free sale</span></span></td>
<td><span data-ttu-id="565c7-321">K_14</span><span class="sxs-lookup"><span data-stu-id="565c7-321">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-322">10704</span><span class="sxs-lookup"><span data-stu-id="565c7-322">10704</span></span></td>
<td><span data-ttu-id="565c7-323">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-323">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="565c7-324">K_14</span><span class="sxs-lookup"><span data-stu-id="565c7-324">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-325">10705</span><span class="sxs-lookup"><span data-stu-id="565c7-325">10705</span></span></td>
<td><span data-ttu-id="565c7-326">Faktura korygująca sprzedaży zwolnionej z podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-326">Tax exempt sales credit note</span></span></td>
<td><span data-ttu-id="565c7-327">K_14</span><span class="sxs-lookup"><span data-stu-id="565c7-327">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="565c7-328"><strong>IntraEUGoods</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-328"><strong>IntraEUGoods</strong></span></span></td>
<td><span data-ttu-id="565c7-329">10801</span><span class="sxs-lookup"><span data-stu-id="565c7-329">10801</span></span></td>
<td><span data-ttu-id="565c7-330">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-330">Tax-free sale</span></span></td>
<td><span data-ttu-id="565c7-331">K_21</span><span class="sxs-lookup"><span data-stu-id="565c7-331">K_21</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-332">10810</span><span class="sxs-lookup"><span data-stu-id="565c7-332">10810</span></span></td>
<td><span data-ttu-id="565c7-333">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="565c7-333">Taxable import</span></span></td>
<td><span data-ttu-id="565c7-334">K_23</span><span class="sxs-lookup"><span data-stu-id="565c7-334">K_23</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-335">10812</span><span class="sxs-lookup"><span data-stu-id="565c7-335">10812</span></span></td>
<td><span data-ttu-id="565c7-336">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="565c7-336">Use tax</span></span></td>
<td><span data-ttu-id="565c7-337">K_24</span><span class="sxs-lookup"><span data-stu-id="565c7-337">K_24</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="565c7-338"><strong>ExportOfGoods</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-338"><strong>ExportOfGoods</strong></span></span></td>
<td><span data-ttu-id="565c7-339">10901</span><span class="sxs-lookup"><span data-stu-id="565c7-339">10901</span></span></td>
<td><span data-ttu-id="565c7-340">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-340">Tax-free sale</span></span></td>
<td><span data-ttu-id="565c7-341">K_22</span><span class="sxs-lookup"><span data-stu-id="565c7-341">K_22</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-342">10905</span><span class="sxs-lookup"><span data-stu-id="565c7-342">10905</span></span></td>
<td><span data-ttu-id="565c7-343">Faktura korygująca sprzedaży zwolnionej z podatku</span><span class="sxs-lookup"><span data-stu-id="565c7-343">Tax exempt sales credit note</span></span></td>
<td><span data-ttu-id="565c7-344">K_22</span><span class="sxs-lookup"><span data-stu-id="565c7-344">K_22</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="565c7-345"><strong>ImportOfGoodsART33</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-345"><strong>ImportOfGoodsART33</strong></span></span></td>
<td><span data-ttu-id="565c7-346">20207</span><span class="sxs-lookup"><span data-stu-id="565c7-346">20207</span></span></td>
<td><span data-ttu-id="565c7-347">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="565c7-347">Taxable import</span></span></td>
<td><span data-ttu-id="565c7-348">K_45</span><span class="sxs-lookup"><span data-stu-id="565c7-348">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-349">11010</span><span class="sxs-lookup"><span data-stu-id="565c7-349">11010</span></span></td>
<td><span data-ttu-id="565c7-350">Przeciwstawna wartość importu podlegająca opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="565c7-350">Offset Taxable import</span></span></td>
<td><span data-ttu-id="565c7-351">K_25</span><span class="sxs-lookup"><span data-stu-id="565c7-351">K_25</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-352">20209</span><span class="sxs-lookup"><span data-stu-id="565c7-352">20209</span></span></td>
<td><span data-ttu-id="565c7-353">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="565c7-353">Use tax</span></span></td>
<td><span data-ttu-id="565c7-354">K_46</span><span class="sxs-lookup"><span data-stu-id="565c7-354">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-355">11012</span><span class="sxs-lookup"><span data-stu-id="565c7-355">11012</span></span></td>
<td><span data-ttu-id="565c7-356">Konto przeciwstawne podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="565c7-356">Offset use tax</span></span></td>
<td><span data-ttu-id="565c7-357">K_26</span><span class="sxs-lookup"><span data-stu-id="565c7-357">K_26</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="565c7-358"><strong>ImportOfServices</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-358"><strong>ImportOfServices</strong></span></span></td>
<td><span data-ttu-id="565c7-359">20207</span><span class="sxs-lookup"><span data-stu-id="565c7-359">20207</span></span></td>
<td><span data-ttu-id="565c7-360">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="565c7-360">Taxable import</span></span></td>
<td><span data-ttu-id="565c7-361">K_45</span><span class="sxs-lookup"><span data-stu-id="565c7-361">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-362">11110</span><span class="sxs-lookup"><span data-stu-id="565c7-362">11110</span></span></td>
<td><span data-ttu-id="565c7-363">Przeciwstawna wartość importu podlegająca opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="565c7-363">Offset Taxable import</span></span></td>
<td><span data-ttu-id="565c7-364">K_27</span><span class="sxs-lookup"><span data-stu-id="565c7-364">K_27</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-365">11117</span><span class="sxs-lookup"><span data-stu-id="565c7-365">11117</span></span></td>
<td><span data-ttu-id="565c7-366">Sprzedaż opodatkowana (opłata zwrotna)</span><span class="sxs-lookup"><span data-stu-id="565c7-366">Taxable sales (Reverse charge)</span></span></td>
<td><span data-ttu-id="565c7-367">K_27</span><span class="sxs-lookup"><span data-stu-id="565c7-367">K_27</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-368">20209</span><span class="sxs-lookup"><span data-stu-id="565c7-368">20209</span></span></td>
<td><span data-ttu-id="565c7-369">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="565c7-369">Use tax</span></span></td>
<td><span data-ttu-id="565c7-370">K_46</span><span class="sxs-lookup"><span data-stu-id="565c7-370">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-371">11112</span><span class="sxs-lookup"><span data-stu-id="565c7-371">11112</span></span></td>
<td><span data-ttu-id="565c7-372">Konto przeciwstawne podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="565c7-372">Offset use tax</span></span></td>
<td><span data-ttu-id="565c7-373">K_28</span><span class="sxs-lookup"><span data-stu-id="565c7-373">K_28</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="565c7-374"><strong>ImportART28</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-374"><strong>ImportART28</strong></span></span></td>
<td><span data-ttu-id="565c7-375">20207</span><span class="sxs-lookup"><span data-stu-id="565c7-375">20207</span></span></td>
<td><span data-ttu-id="565c7-376">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="565c7-376">Taxable import</span></span></td>
<td><span data-ttu-id="565c7-377">K_45</span><span class="sxs-lookup"><span data-stu-id="565c7-377">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-378">11210</span><span class="sxs-lookup"><span data-stu-id="565c7-378">11210</span></span></td>
<td><span data-ttu-id="565c7-379">Przeciwstawna wartość importu podlegająca opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="565c7-379">Offset Taxable import</span></span></td>
<td><span data-ttu-id="565c7-380">K_29</span><span class="sxs-lookup"><span data-stu-id="565c7-380">K_29</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-381">111119</span><span class="sxs-lookup"><span data-stu-id="565c7-381">111119</span></span></td>
<td><span data-ttu-id="565c7-382">Sprzedaż opodatkowana (opłata zwrotna)</span><span class="sxs-lookup"><span data-stu-id="565c7-382">Taxable sales (Reverse charge)</span></span></td>
<td><span data-ttu-id="565c7-383">K_29</span><span class="sxs-lookup"><span data-stu-id="565c7-383">K_29</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-384">20209</span><span class="sxs-lookup"><span data-stu-id="565c7-384">20209</span></span></td>
<td><span data-ttu-id="565c7-385">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="565c7-385">Use tax</span></span></td>
<td><span data-ttu-id="565c7-386">K_46</span><span class="sxs-lookup"><span data-stu-id="565c7-386">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-387">11212</span><span class="sxs-lookup"><span data-stu-id="565c7-387">11212</span></span></td>
<td><span data-ttu-id="565c7-388">Konto przeciwstawne podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="565c7-388">Offset use tax</span></span></td>
<td><span data-ttu-id="565c7-389">K_30</span><span class="sxs-lookup"><span data-stu-id="565c7-389">K_30</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="565c7-390"><strong>ReverseCharge</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-390"><strong>ReverseCharge</strong></span></span></td>
<td><span data-ttu-id="565c7-391">11301</span><span class="sxs-lookup"><span data-stu-id="565c7-391">11301</span></span></td>
<td><span data-ttu-id="565c7-392">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="565c7-392">Taxable sales</span></span></td>
<td><span data-ttu-id="565c7-393">K_34</span><span class="sxs-lookup"><span data-stu-id="565c7-393">K_34</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-394">11302</span><span class="sxs-lookup"><span data-stu-id="565c7-394">11302</span></span></td>
<td><span data-ttu-id="565c7-395">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="565c7-395">Sales tax payable</span></span></td>
<td><span data-ttu-id="565c7-396">K_35</span><span class="sxs-lookup"><span data-stu-id="565c7-396">K_35</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-397">11304</span><span class="sxs-lookup"><span data-stu-id="565c7-397">11304</span></span></td>
<td><span data-ttu-id="565c7-398">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-398">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="565c7-399">K_34</span><span class="sxs-lookup"><span data-stu-id="565c7-399">K_34</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-400">11306</span><span class="sxs-lookup"><span data-stu-id="565c7-400">11306</span></span></td>
<td><span data-ttu-id="565c7-401">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="565c7-401">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="565c7-402">K_35</span><span class="sxs-lookup"><span data-stu-id="565c7-402">K_35</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="565c7-403"><strong>FixedAssetPurch</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-403"><strong>FixedAssetPurch</strong></span></span></td>
<td><span data-ttu-id="565c7-404">20107</span><span class="sxs-lookup"><span data-stu-id="565c7-404">20107</span></span></td>
<td><span data-ttu-id="565c7-405">Zakup podlegający opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="565c7-405">Taxable purchases</span></span></td>
<td><span data-ttu-id="565c7-406">K_43</span><span class="sxs-lookup"><span data-stu-id="565c7-406">K_43</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-407">20109</span><span class="sxs-lookup"><span data-stu-id="565c7-407">20109</span></span></td>
<td><span data-ttu-id="565c7-408">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="565c7-408">Sales tax receivable</span></span></td>
<td><span data-ttu-id="565c7-409">K_44</span><span class="sxs-lookup"><span data-stu-id="565c7-409">K_44</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-410">20115</span><span class="sxs-lookup"><span data-stu-id="565c7-410">20115</span></span></td>
<td><span data-ttu-id="565c7-411">Opodatkowana faktura korygująca zakupu</span><span class="sxs-lookup"><span data-stu-id="565c7-411">Taxable purchase credit note</span></span></td>
<td><span data-ttu-id="565c7-412">K_43</span><span class="sxs-lookup"><span data-stu-id="565c7-412">K_43</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-413">20116</span><span class="sxs-lookup"><span data-stu-id="565c7-413">20116</span></span></td>
<td><span data-ttu-id="565c7-414">Podatek od faktury korygującej zakupu</span><span class="sxs-lookup"><span data-stu-id="565c7-414">Sales tax on purchase credit note</span></span></td>
<td><span data-ttu-id="565c7-415">K_47</span><span class="sxs-lookup"><span data-stu-id="565c7-415">K_47</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="565c7-416"><strong>GoodServPurch</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-416"><strong>GoodServPurch</strong></span></span></td>
<td><span data-ttu-id="565c7-417">20207</span><span class="sxs-lookup"><span data-stu-id="565c7-417">20207</span></span></td>
<td><span data-ttu-id="565c7-418">Zakup podlegający opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="565c7-418">Taxable purchases</span></span></td>
<td><span data-ttu-id="565c7-419">K_45</span><span class="sxs-lookup"><span data-stu-id="565c7-419">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-420">20209</span><span class="sxs-lookup"><span data-stu-id="565c7-420">20209</span></span></td>
<td><span data-ttu-id="565c7-421">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="565c7-421">Sales tax receivable</span></span></td>
<td><span data-ttu-id="565c7-422">K_46</span><span class="sxs-lookup"><span data-stu-id="565c7-422">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-423">20215</span><span class="sxs-lookup"><span data-stu-id="565c7-423">20215</span></span></td>
<td><span data-ttu-id="565c7-424">Opodatkowana faktura korygująca zakupu</span><span class="sxs-lookup"><span data-stu-id="565c7-424">Taxable purchase credit note</span></span></td>
<td><span data-ttu-id="565c7-425">K_45</span><span class="sxs-lookup"><span data-stu-id="565c7-425">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-426">20216</span><span class="sxs-lookup"><span data-stu-id="565c7-426">20216</span></span></td>
<td><span data-ttu-id="565c7-427">Podatek od faktury korygującej zakupu</span><span class="sxs-lookup"><span data-stu-id="565c7-427">Sales tax on purchase credit note</span></span></td>
<td><span data-ttu-id="565c7-428">K_48</span><span class="sxs-lookup"><span data-stu-id="565c7-428">K_48</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="565c7-429"><strong>CorrATR89b1</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-429"><strong>CorrATR89b1</strong></span></span></td>
<td><span data-ttu-id="565c7-430">30101</span><span class="sxs-lookup"><span data-stu-id="565c7-430">30101</span></span></td>
<td><span data-ttu-id="565c7-431">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="565c7-431">Sales tax payable</span></span></td>
<td><span data-ttu-id="565c7-432">K_49</span><span class="sxs-lookup"><span data-stu-id="565c7-432">K_49</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-433">30109</span><span class="sxs-lookup"><span data-stu-id="565c7-433">30109</span></span></td>
<td><span data-ttu-id="565c7-434">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="565c7-434">Sales tax receivable</span></span></td>
<td><span data-ttu-id="565c7-435">K_49</span><span class="sxs-lookup"><span data-stu-id="565c7-435">K_49</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="565c7-436"><strong>CorrATR89b4</strong></span><span class="sxs-lookup"><span data-stu-id="565c7-436"><strong>CorrATR89b4</strong></span></span></td>
<td><span data-ttu-id="565c7-437">30201</span><span class="sxs-lookup"><span data-stu-id="565c7-437">30201</span></span></td>
<td><span data-ttu-id="565c7-438">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="565c7-438">Sales tax payable</span></span></td>
<td><span data-ttu-id="565c7-439">K_50</span><span class="sxs-lookup"><span data-stu-id="565c7-439">K_50</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="565c7-440">30209</span><span class="sxs-lookup"><span data-stu-id="565c7-440">30209</span></span></td>
<td><span data-ttu-id="565c7-441">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="565c7-441">Sales tax receivable</span></span></td>
<td><span data-ttu-id="565c7-442">K_50</span><span class="sxs-lookup"><span data-stu-id="565c7-442">K_50</span></span></td>
<td>+</td>
</tr>
</tbody>
</table>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="565c7-443">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu</span><span class="sxs-lookup"><span data-stu-id="565c7-443">Configure the ER model, and format for the report</span></span>

<span data-ttu-id="565c7-444">Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**.</span><span class="sxs-lookup"><span data-stu-id="565c7-444">To review or change the configuration for the SAF VAT sales and purchase register, on the **Reporting configurations** page, in the list of models, select the **Standard Audit File (SAF-T)** model.</span></span> <span data-ttu-id="565c7-445">Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model.</span><span class="sxs-lookup"><span data-stu-id="565c7-445">Then click **Designer** to review or change the model.</span></span> <span data-ttu-id="565c7-446">Aby przejrzeć lub zmodyfikować format rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Rejestr VAT (PL)** i kliknij przycisk **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="565c7-446">To review or change the format for the SAF VAT sales and purchase register, on the **Reporting configurations** page, under **Standard Audit File (SAF-T)**, select **VAT Register (PL)**, and then click **Designer**.</span></span> <span data-ttu-id="565c7-447">Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="565c7-447">For more information about ER, see the following topics:</span></span>

-   [<span data-ttu-id="565c7-448">Omówienie Raportowania elektroniczne</span><span class="sxs-lookup"><span data-stu-id="565c7-448">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="565c7-449">Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="565c7-449">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="565c7-450">Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="565c7-450">Localization requirements - Create a ER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

<span data-ttu-id="565c7-451">Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej.</span><span class="sxs-lookup"><span data-stu-id="565c7-451">Initially, the configuration is an example of VAT Register based on Reporting codes described in table above.</span></span> <span data-ttu-id="565c7-452">Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="565c7-452">If you need to adopt the configuration to another set of reporting codes, you should derive the format of the configuration.</span></span> <span data-ttu-id="565c7-453">W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="565c7-453">To do so, select the format in the configuration's tree and click **Create configuration** in **Main menu**.</span></span> <span data-ttu-id="565c7-454">Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="565c7-454">**Mark Derive from name:...,** fill in **Name** and **Description** fields of a new format and click **Create configuration** button.</span></span> <span data-ttu-id="565c7-455">Utworzony format jest kopią formatu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="565c7-455">Created format is a copy of the parent format.</span></span> <span data-ttu-id="565c7-456">Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania.</span><span class="sxs-lookup"><span data-stu-id="565c7-456">Select the created format and click **Designer** on the **Main menu** to open format designer and update format with your reporting codes.</span></span> <span data-ttu-id="565c7-457">Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane).</span><span class="sxs-lookup"><span data-stu-id="565c7-457">Format designer window is divided into two parts: the left side â€“ is a format structure (in VAT register case it is a XML scheme); the right side â€“ is a Data Model (data).</span></span> <span data-ttu-id="565c7-458">Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**.</span><span class="sxs-lookup"><span data-stu-id="565c7-458">Press **Mapping** button in the right side to see the **Data model**.</span></span> <span data-ttu-id="565c7-459">Model danych zawiera wszystkie pola wszystkich raportów SAF-T.</span><span class="sxs-lookup"><span data-stu-id="565c7-459">The Data Model includes all the field for all the SAF-T reports.</span></span> <span data-ttu-id="565c7-460">Format rejestru VAT jest mapowany głównie do węzła **TaxTransaction**.</span><span class="sxs-lookup"><span data-stu-id="565c7-460">VAT register format is mapped mostly to the **TaxTransaction** node.</span></span> <span data-ttu-id="565c7-461">Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł.</span><span class="sxs-lookup"><span data-stu-id="565c7-461">Scroll down the tree to find and select it.</span></span> <span data-ttu-id="565c7-462">Wszystkie transakcje podatkowe są podzielone na dwie grupy: według znacznika **SprzedazWiersz** i według znacznika **ZakupWiersz**.</span><span class="sxs-lookup"><span data-stu-id="565c7-462">All tax transactions are grouped into two groups: for tag **SprzedazWiersz** and for tag **ZakupWiersz**.</span></span> <span data-ttu-id="565c7-463">Oraz zatytułowane odpowiednio **$SalesList** i **$PurchaseList**.</span><span class="sxs-lookup"><span data-stu-id="565c7-463">And called **$SalesList** and **$PurchaseList** respectively.</span></span> <span data-ttu-id="565c7-464">Są to listy rekordów obliczane (filtrowane) według formuł.</span><span class="sxs-lookup"><span data-stu-id="565c7-464">These are record lists calculated (filtered) by formulas.</span></span> <span data-ttu-id="565c7-465">Formuły można przeglądać i modyfikować w redaktorze formuł.</span><span class="sxs-lookup"><span data-stu-id="565c7-465">You can review and modify formula in formula redactor.</span></span> <span data-ttu-id="565c7-466">W tym celu należy zaznaczyć pole obliczeniowe lub listę rekordów (w tym konkretnym przypadku), a następnie w menu drzewa kliknąć przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="565c7-466">To do so, select calculated field or record list (in this particular case) and click **Edit** in tree menu.</span></span> <span data-ttu-id="565c7-467">Zmodyfikuj formuły dla grup **$SalesList** i **$PurchaseList** zgodnie z kodami raportowania używanymi w firmie, a następnie je zapisz.</span><span class="sxs-lookup"><span data-stu-id="565c7-467">Edit formulas for **$SalesList** and **$PurchaseList** according to your company's Reporting codes and save them.</span></span> <span data-ttu-id="565c7-468">Okno projektanta formuł po lewej stronie zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować.</span><span class="sxs-lookup"><span data-stu-id="565c7-468">Formula designer window in the left side shows the Data model where you can select fields or record lists and in the right side all the functions which you may implement.</span></span> <span data-ttu-id="565c7-469">(Więcej informacji o projektancie formatów — [Projektant formuł w raportowaniu elektronicznym](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md)).</span><span class="sxs-lookup"><span data-stu-id="565c7-469">(More information about Format designer - [Formula designer in Electronic reporting](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md)).</span></span> <span data-ttu-id="565c7-470">Po podzieleniu transakcji podatkowych na dwie grupy należy wewnątrz każdej grupy pogrupować transakcje dla każdego znacznika zgodnie z kodami raportowania używanymi w firmie.</span><span class="sxs-lookup"><span data-stu-id="565c7-470">After Tax transactions were divided into two groups, inside each of both groups Tax transactions should be grouped for each tag according to your company's Reporting codes.</span></span> <span data-ttu-id="565c7-471">Znajdź pola obliczeniowe „list\_K” w grupach **$SalesList** i **$PurchaseList** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł.</span><span class="sxs-lookup"><span data-stu-id="565c7-471">Find calculated fields "list\_K" under **$SalesList** and **$PurchaseList** and update their formulas with your Reporting codes using Formula Designer.</span></span> <span data-ttu-id="565c7-472">Po zaktualizowaniu formuł wszystkich węzłów „list\_K”</span><span class="sxs-lookup"><span data-stu-id="565c7-472">After all "list\_K"?</span></span> <span data-ttu-id="565c7-473">odszukaj i zmodyfikuj elementy **SalasCtrl** i **PurchCtrl** odpowiednio w grupach **$SalesList** i **$PurchaseList**.</span><span class="sxs-lookup"><span data-stu-id="565c7-473">nodes formulas were updated find and modify **SalasCtrl** and **PurchCtrl** under **$SalesList** and **$PurchaseList** respectively.</span></span> <span data-ttu-id="565c7-474">Te węzły są używane odpowiednio przez znaczniki **SprzedazCtrl** i **ZakupCtrl** .</span><span class="sxs-lookup"><span data-stu-id="565c7-474">These nodes are used for **SprzedazCtrl** and **ZakupCtrl**  tags respectively.</span></span> <span data-ttu-id="565c7-475">Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie.</span><span class="sxs-lookup"><span data-stu-id="565c7-475">Basically, no other modifications in the format are needed.</span></span> <span data-ttu-id="565c7-476">Zapisz format.</span><span class="sxs-lookup"><span data-stu-id="565c7-476">Save the format.</span></span> <span data-ttu-id="565c7-477">Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="565c7-477">Close it and complete the format using **Change status** &gt; **Complete** button on the versions menu on **Versions** FastTab on **Configurations**.</span></span>

### <a name="generate-a-saf-vat-sales-and-purchase-register"></a><span data-ttu-id="565c7-478">Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT</span><span class="sxs-lookup"><span data-stu-id="565c7-478">Generate a SAF VAT sales and purchase register</span></span>

<span data-ttu-id="565c7-479">Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Rejestr SAF sprzedaży i zakupów objętych podatkiem VAT** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="565c7-479">To generate a SAF VAT sales and purchase register, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF VAT sales and purchase register**, and set the following parameters.</span></span>

|   <span data-ttu-id="565c7-480">Parametr</span><span class="sxs-lookup"><span data-stu-id="565c7-480">Parameter</span></span>                  |   <span data-ttu-id="565c7-481">opis</span><span class="sxs-lookup"><span data-stu-id="565c7-481">Description</span></span>                                                                      |
|------------------------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="565c7-482">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-482">**From date**</span></span>                | <span data-ttu-id="565c7-483">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-483">Specify the first date to export reporting data for.</span></span>                               |
| <span data-ttu-id="565c7-484">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-484">**To date**</span></span>                  | <span data-ttu-id="565c7-485">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-485">Specify that last date to export reporting data for.</span></span>                               |
| <span data-ttu-id="565c7-486">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="565c7-486">**Authority identification**</span></span> | <span data-ttu-id="565c7-487">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-487">In the list, select the identifier of the tax authority to use in the export file.</span></span> |

<span data-ttu-id="565c7-488">Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="565c7-488">You can specify additional selection parameters by using the **Filter** functionality on the **Records to include** tab.</span></span>

### <a name="generate-a-saf-vat-invoices-file"></a><span data-ttu-id="565c7-489">Generowanie pliku faktur VAT SAF</span><span class="sxs-lookup"><span data-stu-id="565c7-489">Generate a SAF VAT invoices file</span></span>

<span data-ttu-id="565c7-490">Aby można było wygenerować plik faktur VAT SAF, należy wykonać następujące dodatkowe czynności konfiguracyjne:</span><span class="sxs-lookup"><span data-stu-id="565c7-490">Before you can generate a SAF VAT invoices file, you must complete the following additional setup.</span></span>

-   <span data-ttu-id="565c7-491">Skonfiguruj urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="565c7-491">Set up sales tax authorities.</span></span>
-   <span data-ttu-id="565c7-492">Kody podatków dla raportowania podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="565c7-492">Sales tax codes for VAT reporting.</span></span>
-   <span data-ttu-id="565c7-493">Ustawianie kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="565c7-493">Set up sales tax codes.</span></span>
-   <span data-ttu-id="565c7-494">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-494">Configure the ER model, and format for the report.</span></span>

<span data-ttu-id="565c7-495">To konfigurowanie przypomina dodatkowe konfigurowanie wykonane dla rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, z wyjątkiem czynności **Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu**.</span><span class="sxs-lookup"><span data-stu-id="565c7-495">This setup resembles the additional setup that you completed for the SAF VAT sales and purchase register excepting **Configure the ER model, and format for the report.**</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="565c7-496">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu</span><span class="sxs-lookup"><span data-stu-id="565c7-496">Configure the ER model, and format for the report</span></span>

<span data-ttu-id="565c7-497">Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**.</span><span class="sxs-lookup"><span data-stu-id="565c7-497">To review or change the configuration for the SAF VAT sales and purchase register, on the **Reporting configurations** page, in the list of models, select the **Standard Audit File (SAF-T)** model.</span></span> <span data-ttu-id="565c7-498">Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model.</span><span class="sxs-lookup"><span data-stu-id="565c7-498">Then click **Designer** to review or change the model.</span></span> <span data-ttu-id="565c7-499">Aby przejrzeć lub zmodyfikować faktury VAT SAF, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Faktury VAT (PL)** i kliknij przycisk **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="565c7-499">To review or change the format for the SAF VAT invoices, on the **Reporting configurations** page, under **Standard Audit File (SAF-T)**, select **VAT invoices (PL)**, and then click **Designer**.</span></span> <span data-ttu-id="565c7-500">Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="565c7-500">For more information about ER, see the following topics:</span></span>

-   [<span data-ttu-id="565c7-501">Omówienie Raportowania elektroniczne</span><span class="sxs-lookup"><span data-stu-id="565c7-501">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="565c7-502">Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="565c7-502">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="565c7-503">Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="565c7-503">Localization requirements - Create a ER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

<span data-ttu-id="565c7-504">Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej.</span><span class="sxs-lookup"><span data-stu-id="565c7-504">Initially, the configuration is an example of VAT Register based on Reporting codes described in table above.</span></span> <span data-ttu-id="565c7-505">Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="565c7-505">If you need to adopt the configuration to another set of reporting codes, you should derive the format of the configuration.</span></span> <span data-ttu-id="565c7-506">W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="565c7-506">To do so, select the format in the configuration's tree and click **Create configuration** in **Main menu**.</span></span> <span data-ttu-id="565c7-507">Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="565c7-507">**Mark Derive from name:...,** fill in **Name** and **Description** fields of a new format and click **Create configuration** button.</span></span> <span data-ttu-id="565c7-508">Utworzony format jest kopią formatu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="565c7-508">Created format is a copy of the parent format.</span></span> <span data-ttu-id="565c7-509">Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania.</span><span class="sxs-lookup"><span data-stu-id="565c7-509">Select the created format and click **Designer** on the **Main menu** to open format designer and update format with your reporting codes.</span></span> <span data-ttu-id="565c7-510">Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane).</span><span class="sxs-lookup"><span data-stu-id="565c7-510">Format designer window is divided into two parts: the left side is a format structure (in VAT register case it is a XML scheme); the right side is a Data Model (data).</span></span> <span data-ttu-id="565c7-511">Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**.</span><span class="sxs-lookup"><span data-stu-id="565c7-511">Press **Mapping** button in the right side to see the **Data model**.</span></span> <span data-ttu-id="565c7-512">Model danych zawiera wszystkie pola wszystkich raportów SAF-T.</span><span class="sxs-lookup"><span data-stu-id="565c7-512">The Data Model includes all the field for all the SAF-T reports.</span></span> <span data-ttu-id="565c7-513">Format **Faktury VAT** składa się z kilku sekcji z różnymi źródłami danych.</span><span class="sxs-lookup"><span data-stu-id="565c7-513">**VAT invoices** format includes several parts with different data sources.</span></span> <span data-ttu-id="565c7-514">Dane pod znacznikiem **Faktura** są mapowane głównie do węzła **Model &gt; SourceDocuments &gt; $Invoices**.</span><span class="sxs-lookup"><span data-stu-id="565c7-514">Data under tag **Faktura** is mapped mostly to the **Model &gt; SourceDocuments &gt; $Invoices** node.</span></span> <span data-ttu-id="565c7-515">Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł.</span><span class="sxs-lookup"><span data-stu-id="565c7-515">Scroll down the tree to find and select it.</span></span> <span data-ttu-id="565c7-516">Znajdź pola obliczeniowe **list\_P\_** w węźle **$Invoices** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł.</span><span class="sxs-lookup"><span data-stu-id="565c7-516">Find calculated fields **list\_P\_** under **$Invoices** node and update their formulas with your Reporting codes using Formula Designer.</span></span> <span data-ttu-id="565c7-517">Okno projektanta formuł zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować.</span><span class="sxs-lookup"><span data-stu-id="565c7-517">The Formula designer window shows the data model where you can select fields or record lists and in the right side all the functions which you may implement.</span></span> <span data-ttu-id="565c7-518">Aby uzyskać więcej informacji o projektancie formatów, zobacz [Projektant formuł w raportowaniu elektronicznym](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md).</span><span class="sxs-lookup"><span data-stu-id="565c7-518">For more information about Format designer, see [Formula designer in Electronic reporting](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md).</span></span> <span data-ttu-id="565c7-519">Wartości znaczników pod znacznikiem **StawkiPodatku** są stałe.</span><span class="sxs-lookup"><span data-stu-id="565c7-519">Values for tags under **StawkiPodatku** tag is constants.</span></span> <span data-ttu-id="565c7-520">Zaznacz węzeł wartości (ciąg) dla każdego znacznika pod znacznikiem **StawkiPodatku** i ustaw mu wartość w polu **Wartość** na karcie **Format** z prawej strony okna **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="565c7-520">Select value node (String) for each of tag under **StawkiPodatku** tag and set up its value in **Value** field on **Format** tab on the right side of the **Designer**.</span></span> <span data-ttu-id="565c7-521">Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie.</span><span class="sxs-lookup"><span data-stu-id="565c7-521">Basically, no other modifications in the format are needed.</span></span> <span data-ttu-id="565c7-522">Zapisz format.</span><span class="sxs-lookup"><span data-stu-id="565c7-522">Save the format.</span></span> <span data-ttu-id="565c7-523">Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="565c7-523">Close it and complete the format using **Change status** &gt; **Complete** button on the versions menu on **Versions** FastTab on **Configurations**.</span></span>

### <a name="generate-a-saf-vat-invoices"></a><span data-ttu-id="565c7-524">Generowanie faktur VAT SAF</span><span class="sxs-lookup"><span data-stu-id="565c7-524">Generate a SAF VAT invoices</span></span>

<span data-ttu-id="565c7-525">Aby wygenerować plik faktur VAT SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Faktury VAT SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="565c7-525">To generate a SAF VAT invoices file, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF VAT invoices**, and set the following parameters.</span></span>

|  <span data-ttu-id="565c7-526">Parametr</span><span class="sxs-lookup"><span data-stu-id="565c7-526">Parameter</span></span>                   | <span data-ttu-id="565c7-527">opis</span><span class="sxs-lookup"><span data-stu-id="565c7-527">Description</span></span>                                                                            |
|------------------------------|----------------------------------------------------------------------------------------|
| <span data-ttu-id="565c7-528">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-528">**From date**</span></span>                | <span data-ttu-id="565c7-529">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-529">Specify the first date to export reporting data for.</span></span>                                   |
| <span data-ttu-id="565c7-530">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="565c7-530">**To date**</span></span>                  | <span data-ttu-id="565c7-531">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="565c7-531">Specify the last date to export reporting data for.</span></span>                                    |
| <span data-ttu-id="565c7-532">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="565c7-532">**Authority identification**</span></span> | <span data-ttu-id="565c7-533">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="565c7-533">In the list, select the identifier of the tax authority to use in the export file.</span></span>     |
| <span data-ttu-id="565c7-534">**Identyfikator faktury Od/Do**</span><span class="sxs-lookup"><span data-stu-id="565c7-534">**Invoice ID From / To**</span></span>     | <span data-ttu-id="565c7-535">Określ zakres identyfikatorów faktur, aby ograniczyć ilość faktur wybieranych dla eksportu danych.</span><span class="sxs-lookup"><span data-stu-id="565c7-535">Specify a range of invoice IDs to limit the invoice that are selected for data export.</span></span> |

<span data-ttu-id="565c7-536">Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="565c7-536">You can specify additional selection parameters by using the **Filter** functionality on the **Records to include** tab.</span></span>

## <a name="using-batch-jobs-for-saft"></a><span data-ttu-id="565c7-537">Używanie zadań wsadowych dla raportów SAFT</span><span class="sxs-lookup"><span data-stu-id="565c7-537">Using batch jobs for SAFT</span></span>
<span data-ttu-id="565c7-538">Generowanie raportów SAF-T za długi okres, taki jak miesiąc lub kwartał, może powodować objęcie bardzo dużej ilości danych i zajmować dużo czasu.</span><span class="sxs-lookup"><span data-stu-id="565c7-538">Generating SAF-T reports for a long period such as month or a quarter can include a huge data and take a long time.</span></span> <span data-ttu-id="565c7-539">W takich przypadkach zaleca się używanie zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="565c7-539">For such cases, it is recommended to use batch jobs.</span></span> <span data-ttu-id="565c7-540">Okno dialogowe dla każdego raportu SAF-T zawiera kartę **Uruchom w tle**. Otwórz tę kartę, aby ustawić generowanie raportu w trybie wsadowym.</span><span class="sxs-lookup"><span data-stu-id="565c7-540">Dialog page for every SAF-T report has a **Run in the background** tab. Open this tab to set up report's generation in batch mode.</span></span> <span data-ttu-id="565c7-541">Zaznacz pole wyboru **Przetwarzanie wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="565c7-541">Select **Batch processing** check box.</span></span> <span data-ttu-id="565c7-542">Aby uzyskać więcej informacji na temat przetwarzania wsadowego, zobacz temat [Omówienie przetwarzania wsadowego](../../dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="565c7-542">To learn more about batch processing see the [Batch processing overview](../../dev-itpro/sysadmin/batch-processing-overview.md) topic.</span></span> <span data-ttu-id="565c7-543">Aby przejrzeć zadania wsadowe lub znaleźć wygenerowany plik, otwórz okno **Administrowanie organizacją** &gt; **Raportowanie elektroniczne** &gt; **Zadania raportowania elektronicznego** i znajdź wiersz związany z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="565c7-543">To review batch jobs or find generated file open **Organization administration** &gt; **Electronic reporting** &gt; **Electronic reporting jobs** and find a line related to your job.</span></span> <span data-ttu-id="565c7-544">W **menu głównym** kliknij przycisk **Pokaż dziennik**.</span><span class="sxs-lookup"><span data-stu-id="565c7-544">Click **Show log** button on the **Main menu**.</span></span> <span data-ttu-id="565c7-545">Jeżeli nic nie jest wyświetlane, oznacza to, że podczas generowania pliku nie zostały utworzone żadne komunikaty.</span><span class="sxs-lookup"><span data-stu-id="565c7-545">If nothing is shown it means that no messages were produced during the file generation.</span></span> <span data-ttu-id="565c7-546">Aby zobaczyć plik, w **menu głównym** kliknij przycisk **Pokaż pliki**, znajdź żądany plik i w **menu głównym** kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="565c7-546">To see the file click **Show files** button on **Main menu**, find a file that you need and click **Open** on the **Main menu** to review or save the file.</span></span>  

