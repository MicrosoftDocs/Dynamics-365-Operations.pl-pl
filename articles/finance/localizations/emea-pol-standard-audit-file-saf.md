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
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 274193
ms.assetid: b85c4019-f682-45bf-9a0d-c7549a2f1274
ms.search.region: Poland
ms.author: v-elgolu
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: a813c045998dea88334910f1191ee81ebcbcd70a
ms.sourcegitcommit: 0681a00d60c9f8cc8f7b9888b8c5ddf07279fc04
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3131748"
---
# <a name="standard-audit-file-saf-for-poland"></a><span data-ttu-id="133d8-104">Standardowy plik audytu (SAF) dla Polski</span><span class="sxs-lookup"><span data-stu-id="133d8-104">Standard audit file (SAF) for Poland</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="133d8-105">Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="133d8-105">Users in legal entities in Poland can generate a Standard Audit File for Tax (SAF-T) in XML format.</span></span> <span data-ttu-id="133d8-106">Ten temat zawiera informacje o formatach dla Polski.</span><span class="sxs-lookup"><span data-stu-id="133d8-106">This topic provides information about the formats for Poland.</span></span> 

<span data-ttu-id="133d8-107">Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="133d8-107">Users in legal entities in Poland can generate a Standard Audit File for Tax (SAF-T) in XML format.</span></span> <span data-ttu-id="133d8-108">Ten dokument zawiera informacje o formatach dla Polski.</span><span class="sxs-lookup"><span data-stu-id="133d8-108">This document provides information about the formats for Poland.</span></span> <span data-ttu-id="133d8-109">Niniejszy dokument odnosi się do funkcji, która nie została jeszcze wdrożona.</span><span class="sxs-lookup"><span data-stu-id="133d8-109">This document refers to functionality that has not yet been released.</span></span>

## <a name="set-up-the-standard-audit-file-for-tax-for-poland"></a><span data-ttu-id="133d8-110">Konfigurowanie standardowego pliku audytu dla podatku dla Polski</span><span class="sxs-lookup"><span data-stu-id="133d8-110">Set up the Standard Audit File for Tax for Poland</span></span>
<span data-ttu-id="133d8-111">Aby określić format raportowania elektronicznego (ER) dla każdego schematu SAF-T, kliknij przycisk kolejno opcje **Księga główna > Ustawienia księgi > Parametry księgi głównej**, a następnie na karcie **Standardowy plik audytu dla podatków (SAF-T)** skonfiguruj konkretne formaty dla każdego z następujących schematów:</span><span class="sxs-lookup"><span data-stu-id="133d8-111">To specify an Electronic reporting (ER) format for each SAF-T scheme, click **General ledger > Ledger setup > General ledger parameters**, and then, on the **Standard Audit File for Taxes (SAF-T)** tab, set up a specific format for each of the following schemes:</span></span>

-   <span data-ttu-id="133d8-112">Księgi księgowania SAF</span><span class="sxs-lookup"><span data-stu-id="133d8-112">SAF Accounting books</span></span>
-   <span data-ttu-id="133d8-113">Wyciągi bankowe SAF</span><span class="sxs-lookup"><span data-stu-id="133d8-113">SAF Bank statements</span></span>
-   <span data-ttu-id="133d8-114">Zapasy SAF</span><span class="sxs-lookup"><span data-stu-id="133d8-114">SAF Inventory</span></span>
-   <span data-ttu-id="133d8-115">Rejestry SAF zakupów i sprzedaży objętych podatkiem VAT</span><span class="sxs-lookup"><span data-stu-id="133d8-115">SAF VAT sale and purchase registers</span></span>
-   <span data-ttu-id="133d8-116">Faktury VAT SAF</span><span class="sxs-lookup"><span data-stu-id="133d8-116">SAF VAT invoices</span></span>

<span data-ttu-id="133d8-117">Każdy format raportowania elektronicznego powinien być wstępnie zdefiniowany i pozwalać na aktualizowanie w module Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="133d8-117">Each ER format should be predefined and can be updated in ER.</span></span>

## <a name="generate-a-saf-accounting-books-file"></a><span data-ttu-id="133d8-118">Generowanie pliku ksiąg księgowania SAF</span><span class="sxs-lookup"><span data-stu-id="133d8-118">Generate a SAF Accounting books file</span></span>
<span data-ttu-id="133d8-119">Aby wygenerować plik ksiąg księgowania SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Księgi księgowania SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="133d8-119">To generate a SAF Accounting books file, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF Accounting books**, and set the following parameters.</span></span>

|<span data-ttu-id="133d8-120">Parametr</span><span class="sxs-lookup"><span data-stu-id="133d8-120">Parameter</span></span>                                        |  <span data-ttu-id="133d8-121">opis</span><span class="sxs-lookup"><span data-stu-id="133d8-121">Description</span></span>            |
|-------------------------------------------------|-------------------------|
| <span data-ttu-id="133d8-122">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-122">**From date**</span></span>                                   | <span data-ttu-id="133d8-123">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-123">Specify the first date to export reporting data for.</span></span> |
| <span data-ttu-id="133d8-124">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-124">**To date**</span></span>                                     | <span data-ttu-id="133d8-125">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-125">Specify the last date to export reporting data for.</span></span>  |
| <span data-ttu-id="133d8-126">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="133d8-126">**Authority identification**</span></span>                    | <span data-ttu-id="133d8-127">Określ identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-127">Specify the identifier of the tax authority to use in the export file.</span></span>|
| <span data-ttu-id="133d8-128">**Warstwa księgowania**</span><span class="sxs-lookup"><span data-stu-id="133d8-128">**Posting layer**</span></span>                               | <span data-ttu-id="133d8-129">Umożliwia wybranie warstwy księgowania, od której mają być uwzględniane transakcje.</span><span class="sxs-lookup"><span data-stu-id="133d8-129">Select the posting layer to consider transactions from.</span></span> <span data-ttu-id="133d8-130">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-130">This parameter affects only the ZOiS? part of the export file.</span></span> |
| <span data-ttu-id="133d8-131">**Czy saldo otwarcia ma być pokazywane jako obroty?**</span><span class="sxs-lookup"><span data-stu-id="133d8-131">**Should opening balance be shown by turnover**</span></span> | <span data-ttu-id="133d8-132">Jeśli ten parametr jest zaznaczony, transakcje otwarcia mają wpływ na obroty narastająco.</span><span class="sxs-lookup"><span data-stu-id="133d8-132">If this parameter is selected, opening transactions affect accumulated turnover.</span></span> <span data-ttu-id="133d8-133">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-133">This parameter affects only the ZOiS export file part.</span></span> |
| <span data-ttu-id="133d8-134">**Saldo rozwarte**</span><span class="sxs-lookup"><span data-stu-id="133d8-134">**Separate balance**</span></span>                            | <span data-ttu-id="133d8-135">Ten parametr można włączać dla kont głównych, w których jest oznaczony odnośny parametr.</span><span class="sxs-lookup"><span data-stu-id="133d8-135">This parameter can be considered for main accounts where the corresponding parameter is marked.</span></span> <span data-ttu-id="133d8-136">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-136">This parameter affects only the ZOiS export file part.</span></span>     |
| <span data-ttu-id="133d8-137">**Transakcje zamknięcia**</span><span class="sxs-lookup"><span data-stu-id="133d8-137">**Closing transactions**</span></span>                        | <span data-ttu-id="133d8-138">Jeśli ten parametr jest zaznaczony, transakcje zamknięcia będą uwzględnione w eksportowanych danych.</span><span class="sxs-lookup"><span data-stu-id="133d8-138">If this parameter is selected, closing transactions will be included in the data that is exported.</span></span> <span data-ttu-id="133d8-139">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-139">This parameter affects only the ZOiS? export file part.</span></span> |

<span data-ttu-id="133d8-140">Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="133d8-140">You can specify additional selection parameters by using **Filter** functionality on the **Records to include** tab.</span></span>

## <a name="generate-a-saf-bank-statement-file"></a><span data-ttu-id="133d8-141">Generowanie pliku wyciągu bankowego SAF</span><span class="sxs-lookup"><span data-stu-id="133d8-141">Generate a SAF Bank statement file</span></span>
<span data-ttu-id="133d8-142">Aby wygenerować plik wyciągu bankowego SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Wyciąg bankowy SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="133d8-142">To generate a SAF Bank statement file, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF Bank statement**, and set the following parameters.</span></span>

| <span data-ttu-id="133d8-143">Parametr</span><span class="sxs-lookup"><span data-stu-id="133d8-143">Parameter</span></span>                    | <span data-ttu-id="133d8-144">opis</span><span class="sxs-lookup"><span data-stu-id="133d8-144">Description</span></span>                                                                        |
|------------------------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="133d8-145">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-145">**From date**</span></span>                | <span data-ttu-id="133d8-146">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-146">Specify the first date to export reporting data for.</span></span>                               |
| <span data-ttu-id="133d8-147">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-147">**To date**</span></span>                  | <span data-ttu-id="133d8-148">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-148">Specify the last date to export reporting data for.</span></span>                                |
| <span data-ttu-id="133d8-149">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="133d8-149">**Authority identification**</span></span> | <span data-ttu-id="133d8-150">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-150">In the list, select the identifier of the tax authority to use in the export file.</span></span> |
| <span data-ttu-id="133d8-151">**Konto bankowe**</span><span class="sxs-lookup"><span data-stu-id="133d8-151">**Bank account**</span></span>             | <span data-ttu-id="133d8-152">Umożliwia określenie rachunku bankowego, dla którego mają zostać wyeksportowane transakcje.</span><span class="sxs-lookup"><span data-stu-id="133d8-152">Specify the bank account to export transactions for.</span></span>                               |

 

## <a name="generate-a-saf-inventory-file"></a><span data-ttu-id="133d8-153">Generowanie pliku zapasów SAF</span><span class="sxs-lookup"><span data-stu-id="133d8-153">Generate a SAF Inventory file</span></span>
<span data-ttu-id="133d8-154">Aby wygenerować plik zapasów SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Zapasy SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="133d8-154">To generate a SAF Inventory file, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF Inventory**, and set the following parameters.</span></span>

| <span data-ttu-id="133d8-155">Parametr</span><span class="sxs-lookup"><span data-stu-id="133d8-155">Parameter</span></span>                    | <span data-ttu-id="133d8-156">opis</span><span class="sxs-lookup"><span data-stu-id="133d8-156">Description</span></span>                                                                        |
|------------------------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="133d8-157">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-157">**From date**</span></span>                | <span data-ttu-id="133d8-158">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-158">Specify the first date to export reporting data for.</span></span>                               |
| <span data-ttu-id="133d8-159">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-159">**To date**</span></span>                  | <span data-ttu-id="133d8-160">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-160">Specify the last date to export reporting data for.</span></span>                                |
| <span data-ttu-id="133d8-161">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="133d8-161">**Authority identification**</span></span> | <span data-ttu-id="133d8-162">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-162">In the list, select the identifier of the tax authority to use in the export file.</span></span> |
| <span data-ttu-id="133d8-163">**Magazyn**</span><span class="sxs-lookup"><span data-stu-id="133d8-163">**Warehouse**</span></span>                | <span data-ttu-id="133d8-164">Określ magazyn, dla którego mają zostać wyeksportowane transakcje.</span><span class="sxs-lookup"><span data-stu-id="133d8-164">Specify the warehouse to export transactions for.</span></span>                                  |

### 

## <a name="generate-a-saf-vat-sales-and-purchase-register"></a><span data-ttu-id="133d8-165">Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT</span><span class="sxs-lookup"><span data-stu-id="133d8-165">Generate a SAF VAT sales and purchase register</span></span>
<span data-ttu-id="133d8-166">Zanim będzie można wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem od towarów i usług (VAT), należy wykonać następujące dodatkowe czynności konfiguracyjne:</span><span class="sxs-lookup"><span data-stu-id="133d8-166">Before you can generate a SAF value-added tax (VAT) sales and purchase register, you must complete the following additional setup:</span></span>

-   <span data-ttu-id="133d8-167">Skonfiguruj urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="133d8-167">Set up sales tax authorities.</span></span>
-   <span data-ttu-id="133d8-168">Konfigurowanie kodów podatków dla raportowania podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="133d8-168">Set up sales tax codes for VAT reporting.</span></span>
-   <span data-ttu-id="133d8-169">Ustawianie kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="133d8-169">Set up sales tax codes.</span></span>
-   <span data-ttu-id="133d8-170">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-170">Configure the ER model, and format for the report.</span></span>

<span data-ttu-id="133d8-171">Aby uzyskać więcej informacji o ustawieniach deklaracji VAT, zobacz [Raportowanie podatku VAT w Europie](emea-vat-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="133d8-171">For more information about the setup of VAT statements, see [VAT reporting for Europe](emea-vat-reporting.md).</span></span>

### <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="133d8-172">Konfigurowanie urzędów skarbowych</span><span class="sxs-lookup"><span data-stu-id="133d8-172">Set up sales tax authorities</span></span>

<span data-ttu-id="133d8-173">Aby uzyskać ogólne informacje dotyczące sposobu konfigurowania urzędu skarbowego, zobacz [Konfigurowanie urzędów skarbowych](../general-ledger/tasks/set-up-sales-tax-authorities.md).</span><span class="sxs-lookup"><span data-stu-id="133d8-173">For general information about how to set up a sales tax authority, see [Set up sales tax authorities](../general-ledger/tasks/set-up-sales-tax-authorities.md).</span></span> <span data-ttu-id="133d8-174">Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT w wymaganym formacie dla odpowiedniego urzędu skarbowego, należy zdefiniować układ raportu dla urzędów skarbowych.</span><span class="sxs-lookup"><span data-stu-id="133d8-174">To generate a SAF VAT sales and purchase register in the required format for the appropriate tax authority, you must set up the report layout for sales tax authorities.</span></span> <span data-ttu-id="133d8-175">Na stronie **Urzędy skarbowe** (**Podatek > Podatki pośrednie > Podatek > Urzędy skarbowe**) w polu **Układ raportu** zaznacz wartość **Domyślnie**.</span><span class="sxs-lookup"><span data-stu-id="133d8-175">On the **Sales tax authorities** page (**Tax > Indirect taxes > Sales tax > Sales tax authorities**), set the **Report layout** field to **Default**.</span></span> <span data-ttu-id="133d8-176">Zaznacz ten sam urząd skarbowy dla okresu rozliczeniowego podatku, który będzie używany dla kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="133d8-176">Select the same sales tax authority for the sales tax settlement period that will be used for the sales tax codes.</span></span>

### <a name="set-up-sales-tax-codes-and-sales-tax-reporting-codes"></a><span data-ttu-id="133d8-177">Konfigurowanie kodów podatków i kodów sprawozdawczości podatkowej</span><span class="sxs-lookup"><span data-stu-id="133d8-177">Set up sales tax codes and sales tax reporting codes</span></span>

<span data-ttu-id="133d8-178">Kod raportowania jest liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="133d8-178">A reporting code is an integer value.</span></span> <span data-ttu-id="133d8-179">Kody raportowania powinny być numerowane zgodnie z regułami obowiązującymi w firmie.</span><span class="sxs-lookup"><span data-stu-id="133d8-179">Reporting codes should be numbered according to the company's rules.</span></span> <span data-ttu-id="133d8-180">Jednak zalecamy, aby różnicować kody według kierunku podatku.</span><span class="sxs-lookup"><span data-stu-id="133d8-180">However, we recommend that you vary the codes by tax direction.</span></span> <span data-ttu-id="133d8-181">Na przykład zdefiniuj kod 5-cyfrowy i tak ustaw kody dla wszystkich transakcji wychodzących, które powinny być odzwierciedlane w pierwszej części schematu podatku VAT, aby były mniejsze lub równe 19999.</span><span class="sxs-lookup"><span data-stu-id="133d8-181">For example, use a five-digit code, and set the codes for all outgoing transactions, which should be reflected in the first part of the VAT scheme, so that they are less than or equal to 19999.</span></span> <span data-ttu-id="133d8-182">Natomiast dla wszystkich transakcji przychodzących, które powinny być wykazywane w drugiej części systemu podatku VAT, ustaw kody tak, aby były większe lub równe 20000.</span><span class="sxs-lookup"><span data-stu-id="133d8-182">Set the codes for all incoming transactions, which should be reflected in the second part of the VAT scheme, so that they are more than or equal to 20000.</span></span> <span data-ttu-id="133d8-183">W ten sposób uprościsz konfigurację raportów i eksportu danych, która opiera się na transakcjach podatkowych agregowanych według kodów raportowania.</span><span class="sxs-lookup"><span data-stu-id="133d8-183">In this way, you simplify the setup for reports and for data export that is based on tax transactions that are aggregated by reporting codes.</span></span> <span data-ttu-id="133d8-184">Oto przykład pokazujący użycie kodów sprawozdawczości podatkowej do generowania rejestru SAF sprzedaży i zakupów objętych podatkiem VAT.</span><span class="sxs-lookup"><span data-stu-id="133d8-184">Here is an example that shows how you can use sales tax reporting codes to generate a SAF VAT sales and purchase register.</span></span> <span data-ttu-id="133d8-185">W tym przykładzie kody raportowania są w formacie *ABBCC*.</span><span class="sxs-lookup"><span data-stu-id="133d8-185">For this example, reporting codes are in the format *ABBCC*.</span></span> <span data-ttu-id="133d8-186">Ten format składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="133d8-186">This format consists of the following parts:</span></span>

-   <span data-ttu-id="133d8-187">**A** — Kierunek transakcji.</span><span class="sxs-lookup"><span data-stu-id="133d8-187">**A** - The transaction direction.</span></span> <span data-ttu-id="133d8-188">Wartość wynosi **1** dla podatków wychodzących, **2** dla podatków przychodzących i **3** dla korekt.</span><span class="sxs-lookup"><span data-stu-id="133d8-188">The value is **1** for outgoing, **2** for incoming, **3** for corrections.</span></span>
-   <span data-ttu-id="133d8-189">**BB** — Kod podatku.</span><span class="sxs-lookup"><span data-stu-id="133d8-189">**BB** - The tax code.</span></span> <span data-ttu-id="133d8-190">Numeracja zachowuje kolejność wśród wszystkich kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="133d8-190">The numbering is sequential among all tax codes.</span></span>
-   <span data-ttu-id="133d8-191">**CC** — Numer typu transakcji wewnątrz kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="133d8-191">**CC**-   The transaction type number within a tax code.</span></span> <span data-ttu-id="133d8-192">Parz tabela poniżej.</span><span class="sxs-lookup"><span data-stu-id="133d8-192">See the following table.</span></span>

| <span data-ttu-id="133d8-193">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="133d8-193">Transaction type</span></span>                      | <span data-ttu-id="133d8-194">Numer typu transakcji</span><span class="sxs-lookup"><span data-stu-id="133d8-194">Transaction type number</span></span>     |
|---------------------------------------|-----------------------------|
| <span data-ttu-id="133d8-195">**Sprzedaż opodatkowana**</span><span class="sxs-lookup"><span data-stu-id="133d8-195">**Taxable Sales**</span></span>                     | <span data-ttu-id="133d8-196">01</span><span class="sxs-lookup"><span data-stu-id="133d8-196">01</span></span>                          |
| <span data-ttu-id="133d8-197">**Sprzedaż wolna od podatku**</span><span class="sxs-lookup"><span data-stu-id="133d8-197">**Tax-free sales**</span></span>                    | <span data-ttu-id="133d8-198">02</span><span class="sxs-lookup"><span data-stu-id="133d8-198">02</span></span>                          |
| <span data-ttu-id="133d8-199">**Podatek należny**</span><span class="sxs-lookup"><span data-stu-id="133d8-199">**Sales tax payable**</span></span>                 | <span data-ttu-id="133d8-200">03</span><span class="sxs-lookup"><span data-stu-id="133d8-200">03</span></span>                          |
| <span data-ttu-id="133d8-201">**Opodatkowana faktura korygująca sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="133d8-201">**Taxable sales credit note**</span></span>         | <span data-ttu-id="133d8-202">04</span><span class="sxs-lookup"><span data-stu-id="133d8-202">04</span></span>                          |
| <span data-ttu-id="133d8-203">**Faktura korygująca sprzedaży zwolnionej z podatku**</span><span class="sxs-lookup"><span data-stu-id="133d8-203">**Tax exempt sales credit note**</span></span>      | <span data-ttu-id="133d8-204">05</span><span class="sxs-lookup"><span data-stu-id="133d8-204">05</span></span>                          |
| <span data-ttu-id="133d8-205">**Podatek od faktury korygującej sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="133d8-205">**Sales tax on sales credit note**</span></span>    | <span data-ttu-id="133d8-206">6</span><span class="sxs-lookup"><span data-stu-id="133d8-206">06</span></span>                          |
| <span data-ttu-id="133d8-207">**Zakup podlegający opodatkowaniu**</span><span class="sxs-lookup"><span data-stu-id="133d8-207">**Taxable purchases**</span></span>                 | <span data-ttu-id="133d8-208">07</span><span class="sxs-lookup"><span data-stu-id="133d8-208">07</span></span>                          |
| <span data-ttu-id="133d8-209">**Zakup wolny od podatku**</span><span class="sxs-lookup"><span data-stu-id="133d8-209">**Tax-free purchase**</span></span>                 | <span data-ttu-id="133d8-210">08</span><span class="sxs-lookup"><span data-stu-id="133d8-210">08</span></span>                          |
| <span data-ttu-id="133d8-211">**Podatek naliczony**</span><span class="sxs-lookup"><span data-stu-id="133d8-211">**Sales tax receivable**</span></span>              | <span data-ttu-id="133d8-212">09</span><span class="sxs-lookup"><span data-stu-id="133d8-212">09</span></span>                          |
| <span data-ttu-id="133d8-213">**Import opodatkowany**</span><span class="sxs-lookup"><span data-stu-id="133d8-213">**Taxable import**</span></span>                    | <span data-ttu-id="133d8-214">10</span><span class="sxs-lookup"><span data-stu-id="133d8-214">10</span></span>                          |
| <span data-ttu-id="133d8-215">**Przeciwstawna wartość importu podlegająca opodatkowaniu**</span><span class="sxs-lookup"><span data-stu-id="133d8-215">**Offset taxable import**</span></span>             | <span data-ttu-id="133d8-216">11</span><span class="sxs-lookup"><span data-stu-id="133d8-216">11</span></span>                          |
| <span data-ttu-id="133d8-217">**Podatek nienaliczony**</span><span class="sxs-lookup"><span data-stu-id="133d8-217">**Use tax**</span></span>                           | <span data-ttu-id="133d8-218">12</span><span class="sxs-lookup"><span data-stu-id="133d8-218">12</span></span>                          |
| <span data-ttu-id="133d8-219">**Konto przeciwstawne podatku nienaliczonego**</span><span class="sxs-lookup"><span data-stu-id="133d8-219">**Offset use tax**</span></span>                    | <span data-ttu-id="133d8-220">13</span><span class="sxs-lookup"><span data-stu-id="133d8-220">13</span></span>                          |
| <span data-ttu-id="133d8-221">**Opodatkowana faktura korygująca zakupu**</span><span class="sxs-lookup"><span data-stu-id="133d8-221">**Taxable purchase credit note**</span></span>      | <span data-ttu-id="133d8-222">14</span><span class="sxs-lookup"><span data-stu-id="133d8-222">14</span></span>                          |
| <span data-ttu-id="133d8-223">**Faktura korygująca zakupu zwolnionego z podatku**</span><span class="sxs-lookup"><span data-stu-id="133d8-223">**Tax exempt purchase credit note**</span></span>   | <span data-ttu-id="133d8-224">15</span><span class="sxs-lookup"><span data-stu-id="133d8-224">15</span></span>                          |
| <span data-ttu-id="133d8-225">**Podatek od faktury korygującej zakupu**</span><span class="sxs-lookup"><span data-stu-id="133d8-225">**Sales tax on purchase credit note**</span></span> | <span data-ttu-id="133d8-226">16</span><span class="sxs-lookup"><span data-stu-id="133d8-226">16</span></span>                          |
| <span data-ttu-id="133d8-227">**Opodatkowana faktura korygująca importu**</span><span class="sxs-lookup"><span data-stu-id="133d8-227">**Taxable import credit note**</span></span>        | <span data-ttu-id="133d8-228">17</span><span class="sxs-lookup"><span data-stu-id="133d8-228">17</span></span>                          |
| <span data-ttu-id="133d8-229">**Faktura korygująca przeciwstawnej wartości importu podlegającej opodatkowaniu**</span><span class="sxs-lookup"><span data-stu-id="133d8-229">**Offset taxable import credit note**</span></span> | <span data-ttu-id="133d8-230">18</span><span class="sxs-lookup"><span data-stu-id="133d8-230">18</span></span>                          |

<span data-ttu-id="133d8-231">W poniższej tabeli przedstawiono kody podatków i kody sprawozdawczości podatkowej dla tego przykładu.</span><span class="sxs-lookup"><span data-stu-id="133d8-231">The following table shows the sales tax codes and sales tax reporting codes for this example.</span></span>

<table width="100%">
<tbody>
<tr>
<td><span data-ttu-id="133d8-232"><strong>Kod podatku</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-232"><strong>Sales tax code</strong></span></span></td>
<td><span data-ttu-id="133d8-233"><strong>Kod raportowania podatku</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-233"><strong>Sales tax reporting code</strong></span></span></td>
<td><span data-ttu-id="133d8-234"><strong>Opis</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-234"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="133d8-235"><strong>Nazwa znacznika w podatku VAT SAF-T</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-235"><strong>Tag name in SAF-T VAT</strong></span></span></td>
<td><span data-ttu-id="133d8-236"><strong>Znak w podatku VAT SAF-T</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-236"><strong>Sign in SAF-T VAT</strong></span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="133d8-237"><strong>ExportCust</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-237"><strong>ExportCust</strong></span></span></td>
<td><span data-ttu-id="133d8-238">10101</span><span class="sxs-lookup"><span data-stu-id="133d8-238">10101</span></span></td>
<td><span data-ttu-id="133d8-239">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="133d8-239">Taxable sales</span></span></td>
<td><span data-ttu-id="133d8-240">K_11</span><span class="sxs-lookup"><span data-stu-id="133d8-240">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-241">10102</span><span class="sxs-lookup"><span data-stu-id="133d8-241">10102</span></span></td>
<td><span data-ttu-id="133d8-242">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-242">Tax-free sale</span></span></td>
<td><span data-ttu-id="133d8-243">K_11</span><span class="sxs-lookup"><span data-stu-id="133d8-243">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-244">10104</span><span class="sxs-lookup"><span data-stu-id="133d8-244">10104</span></span></td>
<td><span data-ttu-id="133d8-245">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-245">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="133d8-246">K_11</span><span class="sxs-lookup"><span data-stu-id="133d8-246">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-247">10105</span><span class="sxs-lookup"><span data-stu-id="133d8-247">10105</span></span></td>
<td><span data-ttu-id="133d8-248">Faktura korygująca sprzedaży zwolnionej z podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-248">Tax exempt sales credit note</span></span></td>
<td><span data-ttu-id="133d8-249">K_11</span><span class="sxs-lookup"><span data-stu-id="133d8-249">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="133d8-250"><strong>Art100</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-250"><strong>Art100</strong></span></span></td>
<td><span data-ttu-id="133d8-251">10201</span><span class="sxs-lookup"><span data-stu-id="133d8-251">10201</span></span></td>
<td><span data-ttu-id="133d8-252">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="133d8-252">Taxable sales</span></span></td>
<td><span data-ttu-id="133d8-253">K_12</span><span class="sxs-lookup"><span data-stu-id="133d8-253">K_12</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-254">10204</span><span class="sxs-lookup"><span data-stu-id="133d8-254">10204</span></span></td>
<td><span data-ttu-id="133d8-255">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-255">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="133d8-256">K_12</span><span class="sxs-lookup"><span data-stu-id="133d8-256">K_12</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="133d8-257"><strong>VAT22_23</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-257"><strong>VAT22_23</strong></span></span></td>
<td><span data-ttu-id="133d8-258">10301</span><span class="sxs-lookup"><span data-stu-id="133d8-258">10301</span></span></td>
<td><span data-ttu-id="133d8-259">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="133d8-259">Taxable sales</span></span></td>
<td><span data-ttu-id="133d8-260">K_19</span><span class="sxs-lookup"><span data-stu-id="133d8-260">K_19</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-261">10302</span><span class="sxs-lookup"><span data-stu-id="133d8-261">10302</span></span></td>
<td><span data-ttu-id="133d8-262">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-262">Tax-free sale</span></span></td>
<td><span data-ttu-id="133d8-263">K_10</span><span class="sxs-lookup"><span data-stu-id="133d8-263">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-264">10303</span><span class="sxs-lookup"><span data-stu-id="133d8-264">10303</span></span></td>
<td><span data-ttu-id="133d8-265">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="133d8-265">Sales tax payable</span></span></td>
<td><span data-ttu-id="133d8-266">K_20</span><span class="sxs-lookup"><span data-stu-id="133d8-266">K_20</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-267">10304</span><span class="sxs-lookup"><span data-stu-id="133d8-267">10304</span></span></td>
<td><span data-ttu-id="133d8-268">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-268">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="133d8-269">K_19</span><span class="sxs-lookup"><span data-stu-id="133d8-269">K_19</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-270">10306</span><span class="sxs-lookup"><span data-stu-id="133d8-270">10306</span></span></td>
<td><span data-ttu-id="133d8-271">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-271">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="133d8-272">K_20</span><span class="sxs-lookup"><span data-stu-id="133d8-272">K_20</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="133d8-273"><strong>VAT7_8</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-273"><strong>VAT7_8</strong></span></span></td>
<td><span data-ttu-id="133d8-274">10401</span><span class="sxs-lookup"><span data-stu-id="133d8-274">10401</span></span></td>
<td><span data-ttu-id="133d8-275">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="133d8-275">Taxable sales</span></span></td>
<td><span data-ttu-id="133d8-276">K_17</span><span class="sxs-lookup"><span data-stu-id="133d8-276">K_17</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-277">10402</span><span class="sxs-lookup"><span data-stu-id="133d8-277">10402</span></span></td>
<td><span data-ttu-id="133d8-278">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-278">Tax-free sale</span></span></td>
<td><span data-ttu-id="133d8-279">K_10</span><span class="sxs-lookup"><span data-stu-id="133d8-279">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-280">10403</span><span class="sxs-lookup"><span data-stu-id="133d8-280">10403</span></span></td>
<td><span data-ttu-id="133d8-281">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="133d8-281">Sales tax payable</span></span></td>
<td><span data-ttu-id="133d8-282">K_18</span><span class="sxs-lookup"><span data-stu-id="133d8-282">K_18</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-283">10404</span><span class="sxs-lookup"><span data-stu-id="133d8-283">10404</span></span></td>
<td><span data-ttu-id="133d8-284">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-284">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="133d8-285">K_17</span><span class="sxs-lookup"><span data-stu-id="133d8-285">K_17</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-286">10406</span><span class="sxs-lookup"><span data-stu-id="133d8-286">10406</span></span></td>
<td><span data-ttu-id="133d8-287">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-287">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="133d8-288">K_18</span><span class="sxs-lookup"><span data-stu-id="133d8-288">K_18</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="133d8-289"><strong>VAT5</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-289"><strong>VAT5</strong></span></span></td>
<td><span data-ttu-id="133d8-290">10501</span><span class="sxs-lookup"><span data-stu-id="133d8-290">10501</span></span></td>
<td><span data-ttu-id="133d8-291">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="133d8-291">Taxable sales</span></span></td>
<td><span data-ttu-id="133d8-292">K_15</span><span class="sxs-lookup"><span data-stu-id="133d8-292">K_15</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-293">10502</span><span class="sxs-lookup"><span data-stu-id="133d8-293">10502</span></span></td>
<td><span data-ttu-id="133d8-294">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-294">Tax-free sale</span></span></td>
<td><span data-ttu-id="133d8-295">K_10</span><span class="sxs-lookup"><span data-stu-id="133d8-295">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-296">10503</span><span class="sxs-lookup"><span data-stu-id="133d8-296">10503</span></span></td>
<td><span data-ttu-id="133d8-297">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="133d8-297">Sales tax payable</span></span></td>
<td><span data-ttu-id="133d8-298">K_16</span><span class="sxs-lookup"><span data-stu-id="133d8-298">K_16</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-299">10504</span><span class="sxs-lookup"><span data-stu-id="133d8-299">10504</span></span></td>
<td><span data-ttu-id="133d8-300">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-300">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="133d8-301">K_15</span><span class="sxs-lookup"><span data-stu-id="133d8-301">K_15</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-302">10506</span><span class="sxs-lookup"><span data-stu-id="133d8-302">10506</span></span></td>
<td><span data-ttu-id="133d8-303">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-303">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="133d8-304">K_16</span><span class="sxs-lookup"><span data-stu-id="133d8-304">K_16</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="133d8-305"><strong>VAT0</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-305"><strong>VAT0</strong></span></span></td>
<td><span data-ttu-id="133d8-306">10601</span><span class="sxs-lookup"><span data-stu-id="133d8-306">10601</span></span></td>
<td><span data-ttu-id="133d8-307">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="133d8-307">Taxable sales</span></span></td>
<td><span data-ttu-id="133d8-308">K_13</span><span class="sxs-lookup"><span data-stu-id="133d8-308">K_13</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-309">10602</span><span class="sxs-lookup"><span data-stu-id="133d8-309">10602</span></span></td>
<td><span data-ttu-id="133d8-310">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-310">Tax-free sale</span></span></td>
<td><span data-ttu-id="133d8-311">K_10</span><span class="sxs-lookup"><span data-stu-id="133d8-311">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-312">10604</span><span class="sxs-lookup"><span data-stu-id="133d8-312">10604</span></span></td>
<td><span data-ttu-id="133d8-313">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-313">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="133d8-314">K_13</span><span class="sxs-lookup"><span data-stu-id="133d8-314">K_13</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="133d8-315"><strong>ART129</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-315"><strong>ART129</strong></span></span></td>
<td><span data-ttu-id="133d8-316">10701</span><span class="sxs-lookup"><span data-stu-id="133d8-316">10701</span></span></td>
<td><span data-ttu-id="133d8-317">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="133d8-317">Taxable sales</span></span></td>
<td><span data-ttu-id="133d8-318">K_14</span><span class="sxs-lookup"><span data-stu-id="133d8-318">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-319">10702</span><span class="sxs-lookup"><span data-stu-id="133d8-319">10702</span></span></td>
<td><span data-ttu-id="133d8-320">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-320">Tax-free sale</span></span></td>
<td><span data-ttu-id="133d8-321">K_14</span><span class="sxs-lookup"><span data-stu-id="133d8-321">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-322">10704</span><span class="sxs-lookup"><span data-stu-id="133d8-322">10704</span></span></td>
<td><span data-ttu-id="133d8-323">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-323">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="133d8-324">K_14</span><span class="sxs-lookup"><span data-stu-id="133d8-324">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-325">10705</span><span class="sxs-lookup"><span data-stu-id="133d8-325">10705</span></span></td>
<td><span data-ttu-id="133d8-326">Faktura korygująca sprzedaży zwolnionej z podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-326">Tax exempt sales credit note</span></span></td>
<td><span data-ttu-id="133d8-327">K_14</span><span class="sxs-lookup"><span data-stu-id="133d8-327">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="133d8-328"><strong>IntraEUGoods</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-328"><strong>IntraEUGoods</strong></span></span></td>
<td><span data-ttu-id="133d8-329">10801</span><span class="sxs-lookup"><span data-stu-id="133d8-329">10801</span></span></td>
<td><span data-ttu-id="133d8-330">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-330">Tax-free sale</span></span></td>
<td><span data-ttu-id="133d8-331">K_21</span><span class="sxs-lookup"><span data-stu-id="133d8-331">K_21</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-332">10810</span><span class="sxs-lookup"><span data-stu-id="133d8-332">10810</span></span></td>
<td><span data-ttu-id="133d8-333">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="133d8-333">Taxable import</span></span></td>
<td><span data-ttu-id="133d8-334">K_23</span><span class="sxs-lookup"><span data-stu-id="133d8-334">K_23</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-335">10811</span><span class="sxs-lookup"><span data-stu-id="133d8-335">10811</span></span></td>
<td><span data-ttu-id="133d8-336">Sprzedaż opodatkowana (opłata zwrotna)</span><span class="sxs-lookup"><span data-stu-id="133d8-336">Taxable sales (Reverse charge)</span></span></td>
<td><span data-ttu-id="133d8-337">K_23</span><span class="sxs-lookup"><span data-stu-id="133d8-337">K_23</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-338">10812</span><span class="sxs-lookup"><span data-stu-id="133d8-338">10812</span></span></td>
<td><span data-ttu-id="133d8-339">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="133d8-339">Use tax</span></span></td>
<td><span data-ttu-id="133d8-340">K_24</span><span class="sxs-lookup"><span data-stu-id="133d8-340">K_24</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="133d8-341"><strong>ExportOfGoods</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-341"><strong>ExportOfGoods</strong></span></span></td>
<td><span data-ttu-id="133d8-342">10901</span><span class="sxs-lookup"><span data-stu-id="133d8-342">10901</span></span></td>
<td><span data-ttu-id="133d8-343">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-343">Tax-free sale</span></span></td>
<td><span data-ttu-id="133d8-344">K_22</span><span class="sxs-lookup"><span data-stu-id="133d8-344">K_22</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-345">10905</span><span class="sxs-lookup"><span data-stu-id="133d8-345">10905</span></span></td>
<td><span data-ttu-id="133d8-346">Faktura korygująca sprzedaży zwolnionej z podatku</span><span class="sxs-lookup"><span data-stu-id="133d8-346">Tax exempt sales credit note</span></span></td>
<td><span data-ttu-id="133d8-347">K_22</span><span class="sxs-lookup"><span data-stu-id="133d8-347">K_22</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="133d8-348"><strong>ImportOfGoodsART33</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-348"><strong>ImportOfGoodsART33</strong></span></span></td>
<td><span data-ttu-id="133d8-349">20207</span><span class="sxs-lookup"><span data-stu-id="133d8-349">20207</span></span></td>
<td><span data-ttu-id="133d8-350">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="133d8-350">Taxable import</span></span></td>
<td><span data-ttu-id="133d8-351">K_45</span><span class="sxs-lookup"><span data-stu-id="133d8-351">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-352">11010</span><span class="sxs-lookup"><span data-stu-id="133d8-352">11010</span></span></td>
<td><span data-ttu-id="133d8-353">Przeciwstawna wartość importu podlegająca opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="133d8-353">Offset Taxable import</span></span></td>
<td><span data-ttu-id="133d8-354">K_25</span><span class="sxs-lookup"><span data-stu-id="133d8-354">K_25</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-355">20209</span><span class="sxs-lookup"><span data-stu-id="133d8-355">20209</span></span></td>
<td><span data-ttu-id="133d8-356">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="133d8-356">Use tax</span></span></td>
<td><span data-ttu-id="133d8-357">K_46</span><span class="sxs-lookup"><span data-stu-id="133d8-357">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-358">11012</span><span class="sxs-lookup"><span data-stu-id="133d8-358">11012</span></span></td>
<td><span data-ttu-id="133d8-359">Konto przeciwstawne podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="133d8-359">Offset use tax</span></span></td>
<td><span data-ttu-id="133d8-360">K_26</span><span class="sxs-lookup"><span data-stu-id="133d8-360">K_26</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="133d8-361"><strong>ImportOfServices</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-361"><strong>ImportOfServices</strong></span></span></td>
<td><span data-ttu-id="133d8-362">20207</span><span class="sxs-lookup"><span data-stu-id="133d8-362">20207</span></span></td>
<td><span data-ttu-id="133d8-363">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="133d8-363">Taxable import</span></span></td>
<td><span data-ttu-id="133d8-364">K_45</span><span class="sxs-lookup"><span data-stu-id="133d8-364">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-365">11110</span><span class="sxs-lookup"><span data-stu-id="133d8-365">11110</span></span></td>
<td><span data-ttu-id="133d8-366">Przeciwstawna wartość importu podlegająca opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="133d8-366">Offset Taxable import</span></span></td>
<td><span data-ttu-id="133d8-367">K_27</span><span class="sxs-lookup"><span data-stu-id="133d8-367">K_27</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-368">11117</span><span class="sxs-lookup"><span data-stu-id="133d8-368">11117</span></span></td>
<td><span data-ttu-id="133d8-369">Sprzedaż opodatkowana (opłata zwrotna)</span><span class="sxs-lookup"><span data-stu-id="133d8-369">Taxable sales (Reverse charge)</span></span></td>
<td><span data-ttu-id="133d8-370">K_27</span><span class="sxs-lookup"><span data-stu-id="133d8-370">K_27</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-371">20209</span><span class="sxs-lookup"><span data-stu-id="133d8-371">20209</span></span></td>
<td><span data-ttu-id="133d8-372">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="133d8-372">Use tax</span></span></td>
<td><span data-ttu-id="133d8-373">K_46</span><span class="sxs-lookup"><span data-stu-id="133d8-373">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-374">11112</span><span class="sxs-lookup"><span data-stu-id="133d8-374">11112</span></span></td>
<td><span data-ttu-id="133d8-375">Konto przeciwstawne podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="133d8-375">Offset use tax</span></span></td>
<td><span data-ttu-id="133d8-376">K_28</span><span class="sxs-lookup"><span data-stu-id="133d8-376">K_28</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="133d8-377"><strong>ImportART28</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-377"><strong>ImportART28</strong></span></span></td>
<td><span data-ttu-id="133d8-378">20207</span><span class="sxs-lookup"><span data-stu-id="133d8-378">20207</span></span></td>
<td><span data-ttu-id="133d8-379">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="133d8-379">Taxable import</span></span></td>
<td><span data-ttu-id="133d8-380">K_45</span><span class="sxs-lookup"><span data-stu-id="133d8-380">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-381">11210</span><span class="sxs-lookup"><span data-stu-id="133d8-381">11210</span></span></td>
<td><span data-ttu-id="133d8-382">Przeciwstawna wartość importu podlegająca opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="133d8-382">Offset Taxable import</span></span></td>
<td><span data-ttu-id="133d8-383">K_29</span><span class="sxs-lookup"><span data-stu-id="133d8-383">K_29</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-384">111119</span><span class="sxs-lookup"><span data-stu-id="133d8-384">111119</span></span></td>
<td><span data-ttu-id="133d8-385">Sprzedaż opodatkowana (opłata zwrotna)</span><span class="sxs-lookup"><span data-stu-id="133d8-385">Taxable sales (Reverse charge)</span></span></td>
<td><span data-ttu-id="133d8-386">K_29</span><span class="sxs-lookup"><span data-stu-id="133d8-386">K_29</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-387">20209</span><span class="sxs-lookup"><span data-stu-id="133d8-387">20209</span></span></td>
<td><span data-ttu-id="133d8-388">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="133d8-388">Use tax</span></span></td>
<td><span data-ttu-id="133d8-389">K_46</span><span class="sxs-lookup"><span data-stu-id="133d8-389">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-390">11212</span><span class="sxs-lookup"><span data-stu-id="133d8-390">11212</span></span></td>
<td><span data-ttu-id="133d8-391">Konto przeciwstawne podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="133d8-391">Offset use tax</span></span></td>
<td><span data-ttu-id="133d8-392">K_30</span><span class="sxs-lookup"><span data-stu-id="133d8-392">K_30</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="133d8-393"><strong>ReverseCharge</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-393"><strong>ReverseCharge</strong></span></span></td>
<td><span data-ttu-id="133d8-394">11301</span><span class="sxs-lookup"><span data-stu-id="133d8-394">11301</span></span></td>
<td><span data-ttu-id="133d8-395">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="133d8-395">Taxable sales</span></span></td>
<td><span data-ttu-id="133d8-396">K_34</span><span class="sxs-lookup"><span data-stu-id="133d8-396">K_34</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-397">11302</span><span class="sxs-lookup"><span data-stu-id="133d8-397">11302</span></span></td>
<td><span data-ttu-id="133d8-398">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="133d8-398">Sales tax payable</span></span></td>
<td><span data-ttu-id="133d8-399">K_35</span><span class="sxs-lookup"><span data-stu-id="133d8-399">K_35</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-400">11304</span><span class="sxs-lookup"><span data-stu-id="133d8-400">11304</span></span></td>
<td><span data-ttu-id="133d8-401">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-401">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="133d8-402">K_34</span><span class="sxs-lookup"><span data-stu-id="133d8-402">K_34</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-403">11306</span><span class="sxs-lookup"><span data-stu-id="133d8-403">11306</span></span></td>
<td><span data-ttu-id="133d8-404">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="133d8-404">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="133d8-405">K_35</span><span class="sxs-lookup"><span data-stu-id="133d8-405">K_35</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="133d8-406"><strong>FixedAssetPurch</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-406"><strong>FixedAssetPurch</strong></span></span></td>
<td><span data-ttu-id="133d8-407">20107</span><span class="sxs-lookup"><span data-stu-id="133d8-407">20107</span></span></td>
<td><span data-ttu-id="133d8-408">Zakup podlegający opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="133d8-408">Taxable purchases</span></span></td>
<td><span data-ttu-id="133d8-409">K_43</span><span class="sxs-lookup"><span data-stu-id="133d8-409">K_43</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-410">20109</span><span class="sxs-lookup"><span data-stu-id="133d8-410">20109</span></span></td>
<td><span data-ttu-id="133d8-411">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="133d8-411">Sales tax receivable</span></span></td>
<td><span data-ttu-id="133d8-412">K_44</span><span class="sxs-lookup"><span data-stu-id="133d8-412">K_44</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-413">20115</span><span class="sxs-lookup"><span data-stu-id="133d8-413">20115</span></span></td>
<td><span data-ttu-id="133d8-414">Opodatkowana faktura korygująca zakupu</span><span class="sxs-lookup"><span data-stu-id="133d8-414">Taxable purchase credit note</span></span></td>
<td><span data-ttu-id="133d8-415">K_43</span><span class="sxs-lookup"><span data-stu-id="133d8-415">K_43</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-416">20116</span><span class="sxs-lookup"><span data-stu-id="133d8-416">20116</span></span></td>
<td><span data-ttu-id="133d8-417">Podatek od faktury korygującej zakupu</span><span class="sxs-lookup"><span data-stu-id="133d8-417">Sales tax on purchase credit note</span></span></td>
<td><span data-ttu-id="133d8-418">K_47</span><span class="sxs-lookup"><span data-stu-id="133d8-418">K_47</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="133d8-419"><strong>GoodServPurch</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-419"><strong>GoodServPurch</strong></span></span></td>
<td><span data-ttu-id="133d8-420">20207</span><span class="sxs-lookup"><span data-stu-id="133d8-420">20207</span></span></td>
<td><span data-ttu-id="133d8-421">Zakup podlegający opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="133d8-421">Taxable purchases</span></span></td>
<td><span data-ttu-id="133d8-422">K_45</span><span class="sxs-lookup"><span data-stu-id="133d8-422">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-423">20209</span><span class="sxs-lookup"><span data-stu-id="133d8-423">20209</span></span></td>
<td><span data-ttu-id="133d8-424">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="133d8-424">Sales tax receivable</span></span></td>
<td><span data-ttu-id="133d8-425">K_46</span><span class="sxs-lookup"><span data-stu-id="133d8-425">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-426">20215</span><span class="sxs-lookup"><span data-stu-id="133d8-426">20215</span></span></td>
<td><span data-ttu-id="133d8-427">Opodatkowana faktura korygująca zakupu</span><span class="sxs-lookup"><span data-stu-id="133d8-427">Taxable purchase credit note</span></span></td>
<td><span data-ttu-id="133d8-428">K_45</span><span class="sxs-lookup"><span data-stu-id="133d8-428">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-429">20216</span><span class="sxs-lookup"><span data-stu-id="133d8-429">20216</span></span></td>
<td><span data-ttu-id="133d8-430">Podatek od faktury korygującej zakupu</span><span class="sxs-lookup"><span data-stu-id="133d8-430">Sales tax on purchase credit note</span></span></td>
<td><span data-ttu-id="133d8-431">K_48</span><span class="sxs-lookup"><span data-stu-id="133d8-431">K_48</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="133d8-432"><strong>CorrATR89b1</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-432"><strong>CorrATR89b1</strong></span></span></td>
<td><span data-ttu-id="133d8-433">30101</span><span class="sxs-lookup"><span data-stu-id="133d8-433">30101</span></span></td>
<td><span data-ttu-id="133d8-434">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="133d8-434">Sales tax payable</span></span></td>
<td><span data-ttu-id="133d8-435">K_49</span><span class="sxs-lookup"><span data-stu-id="133d8-435">K_49</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-436">30109</span><span class="sxs-lookup"><span data-stu-id="133d8-436">30109</span></span></td>
<td><span data-ttu-id="133d8-437">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="133d8-437">Sales tax receivable</span></span></td>
<td><span data-ttu-id="133d8-438">K_49</span><span class="sxs-lookup"><span data-stu-id="133d8-438">K_49</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="133d8-439"><strong>CorrATR89b4</strong></span><span class="sxs-lookup"><span data-stu-id="133d8-439"><strong>CorrATR89b4</strong></span></span></td>
<td><span data-ttu-id="133d8-440">30201</span><span class="sxs-lookup"><span data-stu-id="133d8-440">30201</span></span></td>
<td><span data-ttu-id="133d8-441">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="133d8-441">Sales tax payable</span></span></td>
<td><span data-ttu-id="133d8-442">K_50</span><span class="sxs-lookup"><span data-stu-id="133d8-442">K_50</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="133d8-443">30209</span><span class="sxs-lookup"><span data-stu-id="133d8-443">30209</span></span></td>
<td><span data-ttu-id="133d8-444">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="133d8-444">Sales tax receivable</span></span></td>
<td><span data-ttu-id="133d8-445">K_50</span><span class="sxs-lookup"><span data-stu-id="133d8-445">K_50</span></span></td>
<td>+</td>
</tr>
</tbody>
</table>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="133d8-446">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu</span><span class="sxs-lookup"><span data-stu-id="133d8-446">Configure the ER model, and format for the report</span></span>

<span data-ttu-id="133d8-447">Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**.</span><span class="sxs-lookup"><span data-stu-id="133d8-447">To review or change the configuration for the SAF VAT sales and purchase register, on the **Reporting configurations** page, in the list of models, select the **Standard Audit File (SAF-T)** model.</span></span> <span data-ttu-id="133d8-448">Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model.</span><span class="sxs-lookup"><span data-stu-id="133d8-448">Then click **Designer** to review or change the model.</span></span> <span data-ttu-id="133d8-449">Aby przejrzeć lub zmodyfikować format rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Rejestr VAT (PL)** i kliknij przycisk **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="133d8-449">To review or change the format for the SAF VAT sales and purchase register, on the **Reporting configurations** page, under **Standard Audit File (SAF-T)**, select **VAT Register (PL)**, and then click **Designer**.</span></span> <span data-ttu-id="133d8-450">Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="133d8-450">For more information about ER, see the following topics:</span></span>

-   [<span data-ttu-id="133d8-451">Omówienie Raportowania elektroniczne</span><span class="sxs-lookup"><span data-stu-id="133d8-451">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="133d8-452">Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="133d8-452">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="133d8-453">Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="133d8-453">Localization requirements - Create a ER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

<span data-ttu-id="133d8-454">Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej.</span><span class="sxs-lookup"><span data-stu-id="133d8-454">Initially, the configuration is an example of VAT Register based on Reporting codes described in table above.</span></span> <span data-ttu-id="133d8-455">Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="133d8-455">If you need to adopt the configuration to another set of reporting codes, you should derive the format of the configuration.</span></span> <span data-ttu-id="133d8-456">W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="133d8-456">To do so, select the format in the configuration's tree and click **Create configuration** in **Main menu**.</span></span> <span data-ttu-id="133d8-457">Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="133d8-457">**Mark Derive from name:...,** fill in **Name** and **Description** fields of a new format and click **Create configuration** button.</span></span> <span data-ttu-id="133d8-458">Utworzony format jest kopią formatu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="133d8-458">Created format is a copy of the parent format.</span></span> <span data-ttu-id="133d8-459">Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania.</span><span class="sxs-lookup"><span data-stu-id="133d8-459">Select the created format and click **Designer** on the **Main menu** to open format designer and update format with your reporting codes.</span></span> <span data-ttu-id="133d8-460">Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane).</span><span class="sxs-lookup"><span data-stu-id="133d8-460">Format designer window is divided into two parts: the left side â€“ is a format structure (in VAT register case it is a XML scheme); the right side â€“ is a Data Model (data).</span></span> <span data-ttu-id="133d8-461">Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**.</span><span class="sxs-lookup"><span data-stu-id="133d8-461">Press **Mapping** button in the right side to see the **Data model**.</span></span> <span data-ttu-id="133d8-462">Model danych zawiera wszystkie pola wszystkich raportów SAF-T.</span><span class="sxs-lookup"><span data-stu-id="133d8-462">The Data Model includes all the field for all the SAF-T reports.</span></span> <span data-ttu-id="133d8-463">Format rejestru VAT jest mapowany głównie do węzła **TaxTransaction**.</span><span class="sxs-lookup"><span data-stu-id="133d8-463">VAT register format is mapped mostly to the **TaxTransaction** node.</span></span> <span data-ttu-id="133d8-464">Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł.</span><span class="sxs-lookup"><span data-stu-id="133d8-464">Scroll down the tree to find and select it.</span></span> <span data-ttu-id="133d8-465">Wszystkie transakcje podatkowe są podzielone na dwie grupy: według znacznika **SprzedazWiersz** i według znacznika **ZakupWiersz**.</span><span class="sxs-lookup"><span data-stu-id="133d8-465">All tax transactions are grouped into two groups: for tag **SprzedazWiersz** and for tag **ZakupWiersz**.</span></span> <span data-ttu-id="133d8-466">Oraz zatytułowane odpowiednio **$SalesList** i **$PurchaseList**.</span><span class="sxs-lookup"><span data-stu-id="133d8-466">And called **$SalesList** and **$PurchaseList** respectively.</span></span> <span data-ttu-id="133d8-467">Są to listy rekordów obliczane (filtrowane) według formuł.</span><span class="sxs-lookup"><span data-stu-id="133d8-467">These are record lists calculated (filtered) by formulas.</span></span> <span data-ttu-id="133d8-468">Formuły można przeglądać i modyfikować w redaktorze formuł.</span><span class="sxs-lookup"><span data-stu-id="133d8-468">You can review and modify formula in formula redactor.</span></span> <span data-ttu-id="133d8-469">W tym celu należy zaznaczyć pole obliczeniowe lub listę rekordów (w tym konkretnym przypadku), a następnie w menu drzewa kliknąć przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="133d8-469">To do so, select calculated field or record list (in this particular case) and click **Edit** in tree menu.</span></span> <span data-ttu-id="133d8-470">Zmodyfikuj formuły dla grup **$SalesList** i **$PurchaseList** zgodnie z kodami raportowania używanymi w firmie, a następnie je zapisz.</span><span class="sxs-lookup"><span data-stu-id="133d8-470">Edit formulas for **$SalesList** and **$PurchaseList** according to your company's Reporting codes and save them.</span></span> <span data-ttu-id="133d8-471">Okno projektanta formuł po lewej stronie zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować.</span><span class="sxs-lookup"><span data-stu-id="133d8-471">Formula designer window in the left side shows the Data model where you can select fields or record lists and in the right side all the functions which you may implement.</span></span> <span data-ttu-id="133d8-472">(Więcej informacji o projektancie formatów — [Projektant formuł w raportowaniu elektronicznym](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md)).</span><span class="sxs-lookup"><span data-stu-id="133d8-472">(More information about Format designer - [Formula designer in Electronic reporting](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md)).</span></span> <span data-ttu-id="133d8-473">Po podzieleniu transakcji podatkowych na dwie grupy należy wewnątrz każdej grupy pogrupować transakcje dla każdego znacznika zgodnie z kodami raportowania używanymi w firmie.</span><span class="sxs-lookup"><span data-stu-id="133d8-473">After Tax transactions were divided into two groups, inside each of both groups Tax transactions should be grouped for each tag according to your company's Reporting codes.</span></span> <span data-ttu-id="133d8-474">Znajdź pola obliczeniowe „list\_K” w grupach **$SalesList** i **$PurchaseList** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł.</span><span class="sxs-lookup"><span data-stu-id="133d8-474">Find calculated fields "list\_K" under **$SalesList** and **$PurchaseList** and update their formulas with your Reporting codes using Formula Designer.</span></span> <span data-ttu-id="133d8-475">Po zaktualizowaniu formuł wszystkich węzłów „list\_K”</span><span class="sxs-lookup"><span data-stu-id="133d8-475">After all "list\_K"?</span></span> <span data-ttu-id="133d8-476">odszukaj i zmodyfikuj elementy **SalasCtrl** i **PurchCtrl** odpowiednio w grupach **$SalesList** i **$PurchaseList**.</span><span class="sxs-lookup"><span data-stu-id="133d8-476">nodes formulas were updated find and modify **SalasCtrl** and **PurchCtrl** under **$SalesList** and **$PurchaseList** respectively.</span></span> <span data-ttu-id="133d8-477">Te węzły są używane odpowiednio przez znaczniki **SprzedazCtrl** i **ZakupCtrl** .</span><span class="sxs-lookup"><span data-stu-id="133d8-477">These nodes are used for **SprzedazCtrl** and **ZakupCtrl**  tags respectively.</span></span> <span data-ttu-id="133d8-478">Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie.</span><span class="sxs-lookup"><span data-stu-id="133d8-478">Basically, no other modifications in the format are needed.</span></span> <span data-ttu-id="133d8-479">Zapisz format.</span><span class="sxs-lookup"><span data-stu-id="133d8-479">Save the format.</span></span> <span data-ttu-id="133d8-480">Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="133d8-480">Close it and complete the format using **Change status** &gt; **Complete** button on the versions menu on **Versions** FastTab on **Configurations**.</span></span>

### <a name="generate-a-saf-vat-sales-and-purchase-register"></a><span data-ttu-id="133d8-481">Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT</span><span class="sxs-lookup"><span data-stu-id="133d8-481">Generate a SAF VAT sales and purchase register</span></span>

<span data-ttu-id="133d8-482">Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Rejestr SAF sprzedaży i zakupów objętych podatkiem VAT** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="133d8-482">To generate a SAF VAT sales and purchase register, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF VAT sales and purchase register**, and set the following parameters.</span></span>

|   <span data-ttu-id="133d8-483">Parametr</span><span class="sxs-lookup"><span data-stu-id="133d8-483">Parameter</span></span>                  |   <span data-ttu-id="133d8-484">opis</span><span class="sxs-lookup"><span data-stu-id="133d8-484">Description</span></span>                                                                      |
|------------------------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="133d8-485">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-485">**From date**</span></span>                | <span data-ttu-id="133d8-486">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-486">Specify the first date to export reporting data for.</span></span>                               |
| <span data-ttu-id="133d8-487">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-487">**To date**</span></span>                  | <span data-ttu-id="133d8-488">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-488">Specify that last date to export reporting data for.</span></span>                               |
| <span data-ttu-id="133d8-489">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="133d8-489">**Authority identification**</span></span> | <span data-ttu-id="133d8-490">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-490">In the list, select the identifier of the tax authority to use in the export file.</span></span> |

<span data-ttu-id="133d8-491">Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="133d8-491">You can specify additional selection parameters by using the **Filter** functionality on the **Records to include** tab.</span></span>

### <a name="generate-a-saf-vat-invoices-file"></a><span data-ttu-id="133d8-492">Generowanie pliku faktur VAT SAF</span><span class="sxs-lookup"><span data-stu-id="133d8-492">Generate a SAF VAT invoices file</span></span>

<span data-ttu-id="133d8-493">Aby można było wygenerować plik faktur VAT SAF, należy wykonać następujące dodatkowe czynności konfiguracyjne:</span><span class="sxs-lookup"><span data-stu-id="133d8-493">Before you can generate a SAF VAT invoices file, you must complete the following additional setup.</span></span>

-   <span data-ttu-id="133d8-494">Skonfiguruj urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="133d8-494">Set up sales tax authorities.</span></span>
-   <span data-ttu-id="133d8-495">Kody podatków dla raportowania podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="133d8-495">Sales tax codes for VAT reporting.</span></span>
-   <span data-ttu-id="133d8-496">Ustawianie kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="133d8-496">Set up sales tax codes.</span></span>
-   <span data-ttu-id="133d8-497">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-497">Configure the ER model, and format for the report.</span></span>

<span data-ttu-id="133d8-498">To konfigurowanie przypomina dodatkowe konfigurowanie wykonane dla rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, z wyjątkiem czynności **Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu**.</span><span class="sxs-lookup"><span data-stu-id="133d8-498">This setup resembles the additional setup that you completed for the SAF VAT sales and purchase register excepting **Configure the ER model, and format for the report.**</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="133d8-499">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu</span><span class="sxs-lookup"><span data-stu-id="133d8-499">Configure the ER model, and format for the report</span></span>

<span data-ttu-id="133d8-500">Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**.</span><span class="sxs-lookup"><span data-stu-id="133d8-500">To review or change the configuration for the SAF VAT sales and purchase register, on the **Reporting configurations** page, in the list of models, select the **Standard Audit File (SAF-T)** model.</span></span> <span data-ttu-id="133d8-501">Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model.</span><span class="sxs-lookup"><span data-stu-id="133d8-501">Then click **Designer** to review or change the model.</span></span> <span data-ttu-id="133d8-502">Aby przejrzeć lub zmodyfikować faktury VAT SAF, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Faktury VAT (PL)** i kliknij przycisk **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="133d8-502">To review or change the format for the SAF VAT invoices, on the **Reporting configurations** page, under **Standard Audit File (SAF-T)**, select **VAT invoices (PL)**, and then click **Designer**.</span></span> <span data-ttu-id="133d8-503">Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="133d8-503">For more information about ER, see the following topics:</span></span>

-   [<span data-ttu-id="133d8-504">Omówienie Raportowania elektroniczne</span><span class="sxs-lookup"><span data-stu-id="133d8-504">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="133d8-505">Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="133d8-505">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="133d8-506">Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="133d8-506">Localization requirements - Create a ER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

<span data-ttu-id="133d8-507">Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej.</span><span class="sxs-lookup"><span data-stu-id="133d8-507">Initially, the configuration is an example of VAT Register based on Reporting codes described in table above.</span></span> <span data-ttu-id="133d8-508">Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="133d8-508">If you need to adopt the configuration to another set of reporting codes, you should derive the format of the configuration.</span></span> <span data-ttu-id="133d8-509">W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="133d8-509">To do so, select the format in the configuration's tree and click **Create configuration** in **Main menu**.</span></span> <span data-ttu-id="133d8-510">Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="133d8-510">**Mark Derive from name:...,** fill in **Name** and **Description** fields of a new format and click **Create configuration** button.</span></span> <span data-ttu-id="133d8-511">Utworzony format jest kopią formatu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="133d8-511">Created format is a copy of the parent format.</span></span> <span data-ttu-id="133d8-512">Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania.</span><span class="sxs-lookup"><span data-stu-id="133d8-512">Select the created format and click **Designer** on the **Main menu** to open format designer and update format with your reporting codes.</span></span> <span data-ttu-id="133d8-513">Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane).</span><span class="sxs-lookup"><span data-stu-id="133d8-513">Format designer window is divided into two parts: the left side is a format structure (in VAT register case it is a XML scheme); the right side is a Data Model (data).</span></span> <span data-ttu-id="133d8-514">Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**.</span><span class="sxs-lookup"><span data-stu-id="133d8-514">Press **Mapping** button in the right side to see the **Data model**.</span></span> <span data-ttu-id="133d8-515">Model danych zawiera wszystkie pola wszystkich raportów SAF-T.</span><span class="sxs-lookup"><span data-stu-id="133d8-515">The Data Model includes all the field for all the SAF-T reports.</span></span> <span data-ttu-id="133d8-516">Format **Faktury VAT** składa się z kilku sekcji z różnymi źródłami danych.</span><span class="sxs-lookup"><span data-stu-id="133d8-516">**VAT invoices** format includes several parts with different data sources.</span></span> <span data-ttu-id="133d8-517">Dane pod znacznikiem **Faktura** są mapowane głównie do węzła **Model &gt; SourceDocuments &gt; $Invoices**.</span><span class="sxs-lookup"><span data-stu-id="133d8-517">Data under tag **Faktura** is mapped mostly to the **Model &gt; SourceDocuments &gt; $Invoices** node.</span></span> <span data-ttu-id="133d8-518">Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł.</span><span class="sxs-lookup"><span data-stu-id="133d8-518">Scroll down the tree to find and select it.</span></span> <span data-ttu-id="133d8-519">Znajdź pola obliczeniowe **list\_P\_** w węźle **$Invoices** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł.</span><span class="sxs-lookup"><span data-stu-id="133d8-519">Find calculated fields **list\_P\_** under **$Invoices** node and update their formulas with your Reporting codes using Formula Designer.</span></span> <span data-ttu-id="133d8-520">Okno projektanta formuł zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować.</span><span class="sxs-lookup"><span data-stu-id="133d8-520">The Formula designer window shows the data model where you can select fields or record lists and in the right side all the functions which you may implement.</span></span> <span data-ttu-id="133d8-521">Aby uzyskać więcej informacji o projektancie formatów, zobacz [Projektant formuł w raportowaniu elektronicznym](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md).</span><span class="sxs-lookup"><span data-stu-id="133d8-521">For more information about Format designer, see [Formula designer in Electronic reporting](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md).</span></span> <span data-ttu-id="133d8-522">Wartości znaczników pod znacznikiem **StawkiPodatku** są stałe.</span><span class="sxs-lookup"><span data-stu-id="133d8-522">Values for tags under **StawkiPodatku** tag is constants.</span></span> <span data-ttu-id="133d8-523">Zaznacz węzeł wartości (ciąg) dla każdego znacznika pod znacznikiem **StawkiPodatku** i ustaw mu wartość w polu **Wartość** na karcie **Format** z prawej strony okna **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="133d8-523">Select value node (String) for each of tag under **StawkiPodatku** tag and set up its value in **Value** field on **Format** tab on the right side of the **Designer**.</span></span> <span data-ttu-id="133d8-524">Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie.</span><span class="sxs-lookup"><span data-stu-id="133d8-524">Basically, no other modifications in the format are needed.</span></span> <span data-ttu-id="133d8-525">Zapisz format.</span><span class="sxs-lookup"><span data-stu-id="133d8-525">Save the format.</span></span> <span data-ttu-id="133d8-526">Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="133d8-526">Close it and complete the format using **Change status** &gt; **Complete** button on the versions menu on **Versions** FastTab on **Configurations**.</span></span>

### <a name="generate-a-saf-vat-invoices"></a><span data-ttu-id="133d8-527">Generowanie faktur VAT SAF</span><span class="sxs-lookup"><span data-stu-id="133d8-527">Generate a SAF VAT invoices</span></span>

<span data-ttu-id="133d8-528">Aby wygenerować plik faktur VAT SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Faktury VAT SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="133d8-528">To generate a SAF VAT invoices file, click **General ledger > Inquiries and reports > Standard Audit File for Tax (SAF-T) > SAF VAT invoices**, and set the following parameters.</span></span>

|  <span data-ttu-id="133d8-529">Parametr</span><span class="sxs-lookup"><span data-stu-id="133d8-529">Parameter</span></span>                   | <span data-ttu-id="133d8-530">opis</span><span class="sxs-lookup"><span data-stu-id="133d8-530">Description</span></span>                                                                            |
|------------------------------|----------------------------------------------------------------------------------------|
| <span data-ttu-id="133d8-531">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-531">**From date**</span></span>                | <span data-ttu-id="133d8-532">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-532">Specify the first date to export reporting data for.</span></span>                                   |
| <span data-ttu-id="133d8-533">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="133d8-533">**To date**</span></span>                  | <span data-ttu-id="133d8-534">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="133d8-534">Specify the last date to export reporting data for.</span></span>                                    |
| <span data-ttu-id="133d8-535">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="133d8-535">**Authority identification**</span></span> | <span data-ttu-id="133d8-536">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="133d8-536">In the list, select the identifier of the tax authority to use in the export file.</span></span>     |
| <span data-ttu-id="133d8-537">**Identyfikator faktury Od/Do**</span><span class="sxs-lookup"><span data-stu-id="133d8-537">**Invoice ID From / To**</span></span>     | <span data-ttu-id="133d8-538">Określ zakres identyfikatorów faktur, aby ograniczyć ilość faktur wybieranych dla eksportu danych.</span><span class="sxs-lookup"><span data-stu-id="133d8-538">Specify a range of invoice IDs to limit the invoice that are selected for data export.</span></span> |

<span data-ttu-id="133d8-539">Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="133d8-539">You can specify additional selection parameters by using the **Filter** functionality on the **Records to include** tab.</span></span>

## <a name="using-batch-jobs-for-saft"></a><span data-ttu-id="133d8-540">Używanie zadań wsadowych dla raportów SAFT</span><span class="sxs-lookup"><span data-stu-id="133d8-540">Using batch jobs for SAFT</span></span>
<span data-ttu-id="133d8-541">Generowanie raportów SAF-T za długi okres, taki jak miesiąc lub kwartał, może powodować objęcie bardzo dużej ilości danych i zajmować dużo czasu.</span><span class="sxs-lookup"><span data-stu-id="133d8-541">Generating SAF-T reports for a long period such as month or a quarter can include a huge data and take a long time.</span></span> <span data-ttu-id="133d8-542">W takich przypadkach zaleca się używanie zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="133d8-542">For such cases, it is recommended to use batch jobs.</span></span> <span data-ttu-id="133d8-543">Okno dialogowe dla każdego raportu SAF-T zawiera kartę **Uruchom w tle**. Otwórz tę kartę, aby ustawić generowanie raportu w trybie wsadowym.</span><span class="sxs-lookup"><span data-stu-id="133d8-543">Dialog page for every SAF-T report has a **Run in the background** tab. Open this tab to set up report's generation in batch mode.</span></span> <span data-ttu-id="133d8-544">Zaznacz pole wyboru **Przetwarzanie wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="133d8-544">Select **Batch processing** check box.</span></span> <span data-ttu-id="133d8-545">Aby uzyskać więcej informacji na temat przetwarzania wsadowego, zobacz temat [Omówienie przetwarzania wsadowego](../../dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="133d8-545">To learn more about batch processing see the [Batch processing overview](../../dev-itpro/sysadmin/batch-processing-overview.md) topic.</span></span> <span data-ttu-id="133d8-546">Aby przejrzeć zadania wsadowe lub znaleźć wygenerowany plik, otwórz okno **Administrowanie organizacją** &gt; **Raportowanie elektroniczne** &gt; **Zadania raportowania elektronicznego** i znajdź wiersz związany z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="133d8-546">To review batch jobs or find generated file open **Organization administration** &gt; **Electronic reporting** &gt; **Electronic reporting jobs** and find a line related to your job.</span></span> <span data-ttu-id="133d8-547">W **menu głównym** kliknij przycisk **Pokaż dziennik**.</span><span class="sxs-lookup"><span data-stu-id="133d8-547">Click **Show log** button on the **Main menu**.</span></span> <span data-ttu-id="133d8-548">Jeżeli nic nie jest wyświetlane, oznacza to, że podczas generowania pliku nie zostały utworzone żadne komunikaty.</span><span class="sxs-lookup"><span data-stu-id="133d8-548">If nothing is shown it means that no messages were produced during the file generation.</span></span> <span data-ttu-id="133d8-549">Aby zobaczyć plik, w **menu głównym** kliknij przycisk **Pokaż pliki**, znajdź żądany plik i w **menu głównym** kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="133d8-549">To see the file click **Show files** button on **Main menu**, find a file that you need and click **Open** on the **Main menu** to review or save the file.</span></span>  

