---
title: Standardowy plik audytu (SAF) dla Polski
description: "Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML. Ten temat zawiera informacje o formatach dla Polski."
author: LizaGolub
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 274193
ms.assetid: b85c4019-f682-45bf-9a0d-c7549a2f1274
ms.search.region: Poland
ms.author: v-elgolu
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 38c218fb0e16ed94c65292bc06d438e6438a350e
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="standard-audit-file-saf-for-poland"></a><span data-ttu-id="2e77f-104">Standardowy plik audytu (SAF) dla Polski</span><span class="sxs-lookup"><span data-stu-id="2e77f-104">Standard audit file (SAF) for Poland</span></span>

<span data-ttu-id="2e77f-105">Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="2e77f-105">Users in legal entities in Poland can generate a Standard Audit File for Tax (SAF-T) in XML format.</span></span> <span data-ttu-id="2e77f-106">Ten temat zawiera informacje o formatach dla Polski.</span><span class="sxs-lookup"><span data-stu-id="2e77f-106">This topic provides information about the formats for Poland.</span></span> 

<span data-ttu-id="2e77f-107">Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="2e77f-107">Users in legal entities in Poland can generate a Standard Audit File for Tax (SAF-T) in XML format.</span></span> <span data-ttu-id="2e77f-108">Ten dokument zawiera informacje o formatach dla Polski.</span><span class="sxs-lookup"><span data-stu-id="2e77f-108">This document provides information about the formats for Poland.</span></span> <span data-ttu-id="2e77f-109">Niniejszy dokument odnosi się do funkcji, która nie została jeszcze wdrożona.</span><span class="sxs-lookup"><span data-stu-id="2e77f-109">This document refers to functionality that has not yet been released.</span></span>

## <a name="set-up-the-standard-audit-file-for-tax-for-poland"></a><span data-ttu-id="2e77f-110">Konfigurowanie standardowego pliku audytu dla podatku dla Polski</span><span class="sxs-lookup"><span data-stu-id="2e77f-110">Set up the Standard Audit File for Tax for Poland</span></span>
<span data-ttu-id="2e77f-111">Aby określić format raportowania elektronicznego (ER) dla każdego schematu SAF-T, kliknij przycisk kolejno opcje **Księga główna** &gt; **Ustawienia księgi** &gt; **Parametry księgi głównej**, a następnie na karcie **Standardowy plik audytu dla podatków (SAF-T)** skonfiguruj konkretne formaty dla każdego z następujących schematów:</span><span class="sxs-lookup"><span data-stu-id="2e77f-111">To specify an Electronic reporting (ER) format for each SAF-T scheme, click **General ledger** &gt; **Ledger setup** &gt; **General ledger parameters**, and then, on the **Standard Audit File for Taxes (SAF-T)** tab, set up a specific format for each of the following schemes:</span></span>

-   <span data-ttu-id="2e77f-112">Księgi księgowania SAF</span><span class="sxs-lookup"><span data-stu-id="2e77f-112">SAF Accounting books</span></span>
-   <span data-ttu-id="2e77f-113">Wyciągi bankowe SAF</span><span class="sxs-lookup"><span data-stu-id="2e77f-113">SAF Bank statements</span></span>
-   <span data-ttu-id="2e77f-114">Zapasy SAF</span><span class="sxs-lookup"><span data-stu-id="2e77f-114">SAF Inventory</span></span>
-   <span data-ttu-id="2e77f-115">Rejestry SAF zakupów i sprzedaży objętych podatkiem VAT</span><span class="sxs-lookup"><span data-stu-id="2e77f-115">SAF VAT sale and purchase registers</span></span>
-   <span data-ttu-id="2e77f-116">Faktury VAT SAF</span><span class="sxs-lookup"><span data-stu-id="2e77f-116">SAF VAT invoices</span></span>

<span data-ttu-id="2e77f-117">Każdy format raportowania elektronicznego powinien być wstępnie zdefiniowany i pozwalać na aktualizowanie w module Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="2e77f-117">Each ER format should be predefined and can be updated in ER.</span></span>

## <a name="generate-a-saf-accounting-books-file"></a><span data-ttu-id="2e77f-118">Generowanie pliku ksiąg księgowania SAF</span><span class="sxs-lookup"><span data-stu-id="2e77f-118">Generate a SAF Accounting books file</span></span>
<span data-ttu-id="2e77f-119">Aby wygenerować plik ksiąg księgowania SAF, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Księgi księgowania SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="2e77f-119">To generate a SAF Accounting books file, click **General ledger** &gt; **Inquiries and reports** &gt; **Standard Audit File for Tax (SAF-T)** &gt; **SAF Accounting books**, and set the following parameters.</span></span>

|                                                 |                                                                                                                                                            |
|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2e77f-120">**Parametr**</span><span class="sxs-lookup"><span data-stu-id="2e77f-120">**Parameter**</span></span>                                   | <span data-ttu-id="2e77f-121">**Opis**</span><span class="sxs-lookup"><span data-stu-id="2e77f-121">**Description**</span></span>                                                                                                                                            |
| <span data-ttu-id="2e77f-122">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-122">**From date**</span></span>                                   | <span data-ttu-id="2e77f-123">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-123">Specify the first date to export reporting data for.</span></span>                                                                                                       |
| <span data-ttu-id="2e77f-124">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-124">**To date**</span></span>                                     | <span data-ttu-id="2e77f-125">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-125">Specify the last date to export reporting data for.</span></span>                                                                                                        |
| <span data-ttu-id="2e77f-126">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-126">**Authority identification**</span></span>                    | <span data-ttu-id="2e77f-127">Określ identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-127">Specify the identifier of the tax authority to use in the export file.</span></span>                                                                                     |
| <span data-ttu-id="2e77f-128">**Warstwa księgowania**</span><span class="sxs-lookup"><span data-stu-id="2e77f-128">**Posting layer**</span></span>                               | <span data-ttu-id="2e77f-129">Umożliwia wybranie warstwy księgowania, od której mają być uwzględniane transakcje.</span><span class="sxs-lookup"><span data-stu-id="2e77f-129">Select the posting layer to consider transactions from.</span></span> <span data-ttu-id="2e77f-130">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-130">This parameter affects only the ZOiS? part of the export file.</span></span>                                     |
| <span data-ttu-id="2e77f-131">**Czy saldo otwarcia ma być pokazywane jako obroty?**</span><span class="sxs-lookup"><span data-stu-id="2e77f-131">**Should opening balance be shown by turnover**</span></span> | <span data-ttu-id="2e77f-132">Jeśli ten parametr jest zaznaczony, transakcje otwarcia mają wpływ na obroty narastająco.</span><span class="sxs-lookup"><span data-stu-id="2e77f-132">If this parameter is selected, opening transactions affect accumulated turnover.</span></span> <span data-ttu-id="2e77f-133">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-133">This parameter affects only the ZOiS export file part.</span></span>                    |
| <span data-ttu-id="2e77f-134">**Saldo rozwarte**</span><span class="sxs-lookup"><span data-stu-id="2e77f-134">**Separate balance**</span></span>                            | <span data-ttu-id="2e77f-135">Ten parametr można włączać dla kont głównych, w których jest oznaczony odnośny parametr.</span><span class="sxs-lookup"><span data-stu-id="2e77f-135">This parameter can be considered for main accounts where the corresponding parameter is marked.</span></span> <span data-ttu-id="2e77f-136">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-136">This parameter affects only the ZOiS export file part.</span></span>     |
| <span data-ttu-id="2e77f-137">**Transakcje zamknięcia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-137">**Closing transactions**</span></span>                        | <span data-ttu-id="2e77f-138">Jeśli ten parametr jest zaznaczony, transakcje zamknięcia będą uwzględnione w eksportowanych danych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-138">If this parameter is selected, closing transactions will be included in the data that is exported.</span></span> <span data-ttu-id="2e77f-139">Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-139">This parameter affects only the ZOiS? export file part.</span></span> |

<span data-ttu-id="2e77f-140">Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-140">You can specify additional selection parameters by using **Filter** functionality on the **Records to include** tab.</span></span>

## <a name="generate-a-saf-bank-statement-file"></a><span data-ttu-id="2e77f-141">Generowanie pliku wyciągu bankowego SAF</span><span class="sxs-lookup"><span data-stu-id="2e77f-141">Generate a SAF Bank statement file</span></span>
<span data-ttu-id="2e77f-142">Aby wygenerować plik wyciągu bankowego SAF, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Wyciąg bankowy SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="2e77f-142">To generate a SAF Bank statement file, click **General ledger** &gt; **Inquiries and reports** &gt; **Standard Audit File for Tax (SAF-T)** &gt; **SAF Bank statement**, and set the following parameters.</span></span>

|                              |                                                                                    |
|------------------------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="2e77f-143">**Parametr**</span><span class="sxs-lookup"><span data-stu-id="2e77f-143">**Parameter**</span></span>                | <span data-ttu-id="2e77f-144">**Opis**</span><span class="sxs-lookup"><span data-stu-id="2e77f-144">**Description**</span></span>                                                                    |
| <span data-ttu-id="2e77f-145">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-145">**From date**</span></span>                | <span data-ttu-id="2e77f-146">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-146">Specify the first date to export reporting data for.</span></span>                               |
| <span data-ttu-id="2e77f-147">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-147">**To date**</span></span>                  | <span data-ttu-id="2e77f-148">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-148">Specify the last date to export reporting data for.</span></span>                                |
| <span data-ttu-id="2e77f-149">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-149">**Authority identification**</span></span> | <span data-ttu-id="2e77f-150">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-150">In the list, select the identifier of the tax authority to use in the export file.</span></span> |
| <span data-ttu-id="2e77f-151">**Konto bankowe**</span><span class="sxs-lookup"><span data-stu-id="2e77f-151">**Bank account**</span></span>             | <span data-ttu-id="2e77f-152">Umożliwia określenie rachunku bankowego, dla którego mają zostać wyeksportowane transakcje.</span><span class="sxs-lookup"><span data-stu-id="2e77f-152">Specify the bank account to export transactions for.</span></span>                               |

 

## <a name="generate-a-saf-inventory-file"></a><span data-ttu-id="2e77f-153">Generowanie pliku zapasów SAF</span><span class="sxs-lookup"><span data-stu-id="2e77f-153">Generate a SAF Inventory file</span></span>
<span data-ttu-id="2e77f-154">Aby wygenerować plik zapasów SAF, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Zapasy SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="2e77f-154">To generate a SAF Inventory file, click **General ledger** &gt; **Inquiries and reports** &gt; **Standard Audit File for Tax (SAF-T)** &gt; **SAF Inventory**, and set the following parameters.</span></span>

|                              |                                                                                    |
|------------------------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="2e77f-155">**Parametr**</span><span class="sxs-lookup"><span data-stu-id="2e77f-155">**Parameter**</span></span>                | <span data-ttu-id="2e77f-156">**Opis**</span><span class="sxs-lookup"><span data-stu-id="2e77f-156">**Description**</span></span>                                                                    |
| <span data-ttu-id="2e77f-157">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-157">**From date**</span></span>                | <span data-ttu-id="2e77f-158">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-158">Specify the first date to export reporting data for.</span></span>                               |
| <span data-ttu-id="2e77f-159">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-159">**To date**</span></span>                  | <span data-ttu-id="2e77f-160">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-160">Specify the last date to export reporting data for.</span></span>                                |
| <span data-ttu-id="2e77f-161">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-161">**Authority identification**</span></span> | <span data-ttu-id="2e77f-162">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-162">In the list, select the identifier of the tax authority to use in the export file.</span></span> |
| <span data-ttu-id="2e77f-163">**Magazyn**</span><span class="sxs-lookup"><span data-stu-id="2e77f-163">**Warehouse**</span></span>                | <span data-ttu-id="2e77f-164">Określ magazyn, dla którego mają zostać wyeksportowane transakcje.</span><span class="sxs-lookup"><span data-stu-id="2e77f-164">Specify the warehouse to export transactions for.</span></span>                                  |

### 

## <a name="generate-a-saf-vat-sales-and-purchase-register"></a><span data-ttu-id="2e77f-165">Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT</span><span class="sxs-lookup"><span data-stu-id="2e77f-165">Generate a SAF VAT sales and purchase register</span></span>
<span data-ttu-id="2e77f-166">Zanim będzie można wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem od towarów i usług (VAT), należy wykonać następujące dodatkowe czynności konfiguracyjne:</span><span class="sxs-lookup"><span data-stu-id="2e77f-166">Before you can generate a SAF value-added tax (VAT) sales and purchase register, you must complete the following additional setup:</span></span>

-   <span data-ttu-id="2e77f-167">Skonfiguruj urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="2e77f-167">Set up sales tax authorities.</span></span>
-   <span data-ttu-id="2e77f-168">Konfigurowanie kodów podatków dla raportowania podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="2e77f-168">Set up sales tax codes for VAT reporting.</span></span>
-   <span data-ttu-id="2e77f-169">Ustawianie kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="2e77f-169">Set up sales tax codes.</span></span>
-   <span data-ttu-id="2e77f-170">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-170">Configure the ER model, and format for the report.</span></span>

<span data-ttu-id="2e77f-171">Aby uzyskać więcej informacji o ustawieniach deklaracji VAT, zobacz [Raportowanie podatku VAT (UE)](emea-vat-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="2e77f-171">For more information about the setup of VAT statements, see [(EU) VAT reporting](emea-vat-reporting.md).</span></span>

### <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="2e77f-172">Konfigurowanie urzędów skarbowych</span><span class="sxs-lookup"><span data-stu-id="2e77f-172">Set up sales tax authorities</span></span>

<span data-ttu-id="2e77f-173">Aby uzyskać ogólne informacje dotyczące sposobu konfigurowania urzędu skarbowego, zobacz [Konfigurowanie urzędów skarbowych (przewodnik po zadaniu)](../general-ledger/tasks/set-up-sales-tax-authorities.md).</span><span class="sxs-lookup"><span data-stu-id="2e77f-173">For general information about how to set up a sales tax authority, see [Set up sales tax authorities (Task guide)](../general-ledger/tasks/set-up-sales-tax-authorities.md).</span></span> <span data-ttu-id="2e77f-174">Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT w wymaganym formacie dla odpowiedniego urzędu skarbowego, należy zdefiniować układ raportu dla urzędów skarbowych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-174">To generate a SAF VAT sales and purchase register in the required format for the appropriate tax authority, you must set up the report layout for sales tax authorities.</span></span> <span data-ttu-id="2e77f-175">Na stronie **Urzędy skarbowe** (**Podatek** &gt; **Podatki pośrednie** &gt; **Podatek** &gt; **Urzędy skarbowe**) w polu **Układ raportu** zaznacz wartość **Domyślnie**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-175">On the **Sales tax authorities** page (**Tax** &gt; **Indirect taxes** &gt; **Sales tax** &gt; **Sales tax authorities**), set the **Report layout** field to **Default**.</span></span> <span data-ttu-id="2e77f-176">Zaznacz ten sam urząd skarbowy dla okresu rozliczeniowego podatku, który będzie używany dla kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="2e77f-176">Select the same sales tax authority for the sales tax settlement period that will be used for the sales tax codes.</span></span>

### <a name="set-up-sales-tax-codes-and-sales-tax-reporting-codes"></a><span data-ttu-id="2e77f-177">Konfigurowanie kodów podatków i kodów sprawozdawczości podatkowej</span><span class="sxs-lookup"><span data-stu-id="2e77f-177">Set up sales tax codes and sales tax reporting codes</span></span>

<span data-ttu-id="2e77f-178">Kod raportowania jest liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="2e77f-178">A reporting code is an integer value.</span></span> <span data-ttu-id="2e77f-179">Kody raportowania powinny być numerowane zgodnie z regułami obowiązującymi w firmie.</span><span class="sxs-lookup"><span data-stu-id="2e77f-179">Reporting codes should be numbered according to the company's rules.</span></span> <span data-ttu-id="2e77f-180">Jednak zalecamy, aby różnicować kody według kierunku podatku.</span><span class="sxs-lookup"><span data-stu-id="2e77f-180">However, we recommend that you vary the codes by tax direction.</span></span> <span data-ttu-id="2e77f-181">Na przykład zdefiniuj kod 5-cyfrowy i tak ustaw kody dla wszystkich transakcji wychodzących, które powinny być odzwierciedlane w pierwszej części schematu podatku VAT, aby były mniejsze lub równe 19999.</span><span class="sxs-lookup"><span data-stu-id="2e77f-181">For example, use a five-digit code, and set the codes for all outgoing transactions, which should be reflected in the first part of the VAT scheme, so that they are less than or equal to 19999.</span></span> <span data-ttu-id="2e77f-182">Natomiast dla wszystkich transakcji przychodzących, które powinny być wykazywane w drugiej części systemu podatku VAT, ustaw kody tak, aby były większe lub równe 20000.</span><span class="sxs-lookup"><span data-stu-id="2e77f-182">Set the codes for all incoming transactions, which should be reflected in the second part of the VAT scheme, so that they are more than or equal to 20000.</span></span> <span data-ttu-id="2e77f-183">W ten sposób uprościsz konfigurację raportów i eksportu danych, która opiera się na transakcjach podatkowych agregowanych według kodów raportowania.</span><span class="sxs-lookup"><span data-stu-id="2e77f-183">In this way, you simplify the setup for reports and for data export that is based on tax transactions that are aggregated by reporting codes.</span></span> <span data-ttu-id="2e77f-184">Oto przykład pokazujący użycie kodów sprawozdawczości podatkowej do generowania rejestru SAF sprzedaży i zakupów objętych podatkiem VAT.</span><span class="sxs-lookup"><span data-stu-id="2e77f-184">Here is an example that shows how you can use sales tax reporting codes to generate a SAF VAT sales and purchase register.</span></span> <span data-ttu-id="2e77f-185">W tym przykładzie kody raportowania są w formacie *ABBCC*.</span><span class="sxs-lookup"><span data-stu-id="2e77f-185">For this example, reporting codes are in the format *ABBCC*.</span></span> <span data-ttu-id="2e77f-186">Ten format składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="2e77f-186">This format consists of the following parts:</span></span>

-   <span data-ttu-id="2e77f-187">**A** — Kierunek transakcji.</span><span class="sxs-lookup"><span data-stu-id="2e77f-187">**A** - The transaction direction.</span></span> <span data-ttu-id="2e77f-188">Wartość wynosi **1** dla podatków wychodzących, **2** dla podatków przychodzących i **3** dla korekt.</span><span class="sxs-lookup"><span data-stu-id="2e77f-188">The value is **1** for outgoing, **2** for incoming, **3** for corrections.</span></span>
-   <span data-ttu-id="2e77f-189">**BB** — Kod podatku.</span><span class="sxs-lookup"><span data-stu-id="2e77f-189">**BB** - The tax code.</span></span> <span data-ttu-id="2e77f-190">Numeracja zachowuje kolejność wśród wszystkich kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="2e77f-190">The numbering is sequential among all tax codes.</span></span>
-   <span data-ttu-id="2e77f-191">**CC** — Numer typu transakcji wewnątrz kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="2e77f-191">**CC**-   The transaction type number within a tax code.</span></span> <span data-ttu-id="2e77f-192">Parz tabela poniżej.</span><span class="sxs-lookup"><span data-stu-id="2e77f-192">See the following table.</span></span>

|                                       |                             |
|---------------------------------------|-----------------------------|
| <span data-ttu-id="2e77f-193">**Typ transakcji**</span><span class="sxs-lookup"><span data-stu-id="2e77f-193">**Transaction type**</span></span>                  | <span data-ttu-id="2e77f-194">**Numer typu transakcji**</span><span class="sxs-lookup"><span data-stu-id="2e77f-194">**Transaction type number**</span></span> |
| <span data-ttu-id="2e77f-195">**Sprzedaż opodatkowana**</span><span class="sxs-lookup"><span data-stu-id="2e77f-195">**Taxable Sales**</span></span>                     | <span data-ttu-id="2e77f-196">01</span><span class="sxs-lookup"><span data-stu-id="2e77f-196">01</span></span>                          |
| <span data-ttu-id="2e77f-197">**Sprzedaż wolna od podatku**</span><span class="sxs-lookup"><span data-stu-id="2e77f-197">**Tax-free sales**</span></span>                    | <span data-ttu-id="2e77f-198">02</span><span class="sxs-lookup"><span data-stu-id="2e77f-198">02</span></span>                          |
| <span data-ttu-id="2e77f-199">**Podatek należny**</span><span class="sxs-lookup"><span data-stu-id="2e77f-199">**Sales tax payable**</span></span>                 | <span data-ttu-id="2e77f-200">03</span><span class="sxs-lookup"><span data-stu-id="2e77f-200">03</span></span>                          |
| <span data-ttu-id="2e77f-201">**Opodatkowana faktura korygująca sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="2e77f-201">**Taxable sales credit note**</span></span>         | <span data-ttu-id="2e77f-202">04</span><span class="sxs-lookup"><span data-stu-id="2e77f-202">04</span></span>                          |
| <span data-ttu-id="2e77f-203">**Faktura korygująca sprzedaży zwolnionej z podatku**</span><span class="sxs-lookup"><span data-stu-id="2e77f-203">**Tax exempt sales credit note**</span></span>      | <span data-ttu-id="2e77f-204">05</span><span class="sxs-lookup"><span data-stu-id="2e77f-204">05</span></span>                          |
| <span data-ttu-id="2e77f-205">**Podatek od faktury korygującej sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="2e77f-205">**Sales tax on sales credit note**</span></span>    | <span data-ttu-id="2e77f-206">6</span><span class="sxs-lookup"><span data-stu-id="2e77f-206">06</span></span>                          |
| <span data-ttu-id="2e77f-207">**Zakup podlegający opodatkowaniu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-207">**Taxable purchases**</span></span>                 | <span data-ttu-id="2e77f-208">07</span><span class="sxs-lookup"><span data-stu-id="2e77f-208">07</span></span>                          |
| <span data-ttu-id="2e77f-209">**Zakup wolny od podatku**</span><span class="sxs-lookup"><span data-stu-id="2e77f-209">**Tax-free purchase**</span></span>                 | <span data-ttu-id="2e77f-210">08</span><span class="sxs-lookup"><span data-stu-id="2e77f-210">08</span></span>                          |
| <span data-ttu-id="2e77f-211">**Podatek naliczony**</span><span class="sxs-lookup"><span data-stu-id="2e77f-211">**Sales tax receivable**</span></span>              | <span data-ttu-id="2e77f-212">09</span><span class="sxs-lookup"><span data-stu-id="2e77f-212">09</span></span>                          |
| <span data-ttu-id="2e77f-213">**Import opodatkowany**</span><span class="sxs-lookup"><span data-stu-id="2e77f-213">**Taxable import**</span></span>                    | <span data-ttu-id="2e77f-214">10</span><span class="sxs-lookup"><span data-stu-id="2e77f-214">10</span></span>                          |
| <span data-ttu-id="2e77f-215">**Przeciwstawna wartość importu podlegająca opodatkowaniu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-215">**Offset taxable import**</span></span>             | <span data-ttu-id="2e77f-216">11</span><span class="sxs-lookup"><span data-stu-id="2e77f-216">11</span></span>                          |
| <span data-ttu-id="2e77f-217">**Podatek nienaliczony**</span><span class="sxs-lookup"><span data-stu-id="2e77f-217">**Use tax**</span></span>                           | <span data-ttu-id="2e77f-218">12</span><span class="sxs-lookup"><span data-stu-id="2e77f-218">12</span></span>                          |
| <span data-ttu-id="2e77f-219">**Konto przeciwstawne podatku nienaliczonego**</span><span class="sxs-lookup"><span data-stu-id="2e77f-219">**Offset use tax**</span></span>                    | <span data-ttu-id="2e77f-220">13</span><span class="sxs-lookup"><span data-stu-id="2e77f-220">13</span></span>                          |
| <span data-ttu-id="2e77f-221">**Opodatkowana faktura korygująca zakupu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-221">**Taxable purchase credit note**</span></span>      | <span data-ttu-id="2e77f-222">14</span><span class="sxs-lookup"><span data-stu-id="2e77f-222">14</span></span>                          |
| <span data-ttu-id="2e77f-223">**Faktura korygująca zakupu zwolnionego z podatku**</span><span class="sxs-lookup"><span data-stu-id="2e77f-223">**Tax exempt purchase credit note**</span></span>   | <span data-ttu-id="2e77f-224">15</span><span class="sxs-lookup"><span data-stu-id="2e77f-224">15</span></span>                          |
| <span data-ttu-id="2e77f-225">**Podatek od faktury korygującej zakupu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-225">**Sales tax on purchase credit note**</span></span> | <span data-ttu-id="2e77f-226">16</span><span class="sxs-lookup"><span data-stu-id="2e77f-226">16</span></span>                          |
| <span data-ttu-id="2e77f-227">**Opodatkowana faktura korygująca importu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-227">**Taxable import credit note**</span></span>        | <span data-ttu-id="2e77f-228">17</span><span class="sxs-lookup"><span data-stu-id="2e77f-228">17</span></span>                          |
| <span data-ttu-id="2e77f-229">**Faktura korygująca przeciwstawnej wartości importu podlegającej opodatkowaniu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-229">**Offset taxable import credit note**</span></span> | <span data-ttu-id="2e77f-230">18</span><span class="sxs-lookup"><span data-stu-id="2e77f-230">18</span></span>                          |

<span data-ttu-id="2e77f-231">W poniższej tabeli przedstawiono kody podatków i kody sprawozdawczości podatkowej dla tego przykładu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-231">The following table shows the sales tax codes and sales tax reporting codes for this example.</span></span>

<table width="100%">
<tbody>
<tr>
<td><span data-ttu-id="2e77f-232"><strong>Kod podatku</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-232"><strong>Sales tax code</strong></span></span></td>
<td><span data-ttu-id="2e77f-233"><strong>Kod raportowania podatku</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-233"><strong>Sales tax reporting code</strong></span></span></td>
<td><span data-ttu-id="2e77f-234"><strong>Opis</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-234"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="2e77f-235"><strong>Nazwa znacznika w podatku VAT SAF-T</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-235"><strong>Tag name in SAF-T VAT</strong></span></span></td>
<td><span data-ttu-id="2e77f-236"><strong>Znak w podatku VAT SAF-T</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-236"><strong>Sign in SAF-T VAT</strong></span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="2e77f-237"><strong>ExportCust</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-237"><strong>ExportCust</strong></span></span></td>
<td><span data-ttu-id="2e77f-238">10101</span><span class="sxs-lookup"><span data-stu-id="2e77f-238">10101</span></span></td>
<td><span data-ttu-id="2e77f-239">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="2e77f-239">Taxable sales</span></span></td>
<td><span data-ttu-id="2e77f-240">K_11</span><span class="sxs-lookup"><span data-stu-id="2e77f-240">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-241">10102</span><span class="sxs-lookup"><span data-stu-id="2e77f-241">10102</span></span></td>
<td><span data-ttu-id="2e77f-242">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-242">Tax-free sale</span></span></td>
<td><span data-ttu-id="2e77f-243">K_11</span><span class="sxs-lookup"><span data-stu-id="2e77f-243">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-244">10104</span><span class="sxs-lookup"><span data-stu-id="2e77f-244">10104</span></span></td>
<td><span data-ttu-id="2e77f-245">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-245">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-246">K_11</span><span class="sxs-lookup"><span data-stu-id="2e77f-246">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-247">10105</span><span class="sxs-lookup"><span data-stu-id="2e77f-247">10105</span></span></td>
<td><span data-ttu-id="2e77f-248">Faktura korygująca sprzedaży zwolnionej z podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-248">Tax exempt sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-249">K_11</span><span class="sxs-lookup"><span data-stu-id="2e77f-249">K_11</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="2e77f-250"><strong>Art100</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-250"><strong>Art100</strong></span></span></td>
<td><span data-ttu-id="2e77f-251">10201</span><span class="sxs-lookup"><span data-stu-id="2e77f-251">10201</span></span></td>
<td><span data-ttu-id="2e77f-252">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="2e77f-252">Taxable sales</span></span></td>
<td><span data-ttu-id="2e77f-253">K_12</span><span class="sxs-lookup"><span data-stu-id="2e77f-253">K_12</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-254">10204</span><span class="sxs-lookup"><span data-stu-id="2e77f-254">10204</span></span></td>
<td><span data-ttu-id="2e77f-255">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-255">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-256">K_12</span><span class="sxs-lookup"><span data-stu-id="2e77f-256">K_12</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="2e77f-257"><strong>VAT22_23</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-257"><strong>VAT22_23</strong></span></span></td>
<td><span data-ttu-id="2e77f-258">10301</span><span class="sxs-lookup"><span data-stu-id="2e77f-258">10301</span></span></td>
<td><span data-ttu-id="2e77f-259">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="2e77f-259">Taxable sales</span></span></td>
<td><span data-ttu-id="2e77f-260">K_19</span><span class="sxs-lookup"><span data-stu-id="2e77f-260">K_19</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-261">10302</span><span class="sxs-lookup"><span data-stu-id="2e77f-261">10302</span></span></td>
<td><span data-ttu-id="2e77f-262">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-262">Tax-free sale</span></span></td>
<td><span data-ttu-id="2e77f-263">K_10</span><span class="sxs-lookup"><span data-stu-id="2e77f-263">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-264">10303</span><span class="sxs-lookup"><span data-stu-id="2e77f-264">10303</span></span></td>
<td><span data-ttu-id="2e77f-265">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="2e77f-265">Sales tax payable</span></span></td>
<td><span data-ttu-id="2e77f-266">K_20</span><span class="sxs-lookup"><span data-stu-id="2e77f-266">K_20</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-267">10304</span><span class="sxs-lookup"><span data-stu-id="2e77f-267">10304</span></span></td>
<td><span data-ttu-id="2e77f-268">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-268">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-269">K_19</span><span class="sxs-lookup"><span data-stu-id="2e77f-269">K_19</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-270">10306</span><span class="sxs-lookup"><span data-stu-id="2e77f-270">10306</span></span></td>
<td><span data-ttu-id="2e77f-271">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-271">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-272">K_20</span><span class="sxs-lookup"><span data-stu-id="2e77f-272">K_20</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="2e77f-273"><strong>VAT7_8</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-273"><strong>VAT7_8</strong></span></span></td>
<td><span data-ttu-id="2e77f-274">10401</span><span class="sxs-lookup"><span data-stu-id="2e77f-274">10401</span></span></td>
<td><span data-ttu-id="2e77f-275">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="2e77f-275">Taxable sales</span></span></td>
<td><span data-ttu-id="2e77f-276">K_17</span><span class="sxs-lookup"><span data-stu-id="2e77f-276">K_17</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-277">10402</span><span class="sxs-lookup"><span data-stu-id="2e77f-277">10402</span></span></td>
<td><span data-ttu-id="2e77f-278">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-278">Tax-free sale</span></span></td>
<td><span data-ttu-id="2e77f-279">K_10</span><span class="sxs-lookup"><span data-stu-id="2e77f-279">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-280">10403</span><span class="sxs-lookup"><span data-stu-id="2e77f-280">10403</span></span></td>
<td><span data-ttu-id="2e77f-281">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="2e77f-281">Sales tax payable</span></span></td>
<td><span data-ttu-id="2e77f-282">K_18</span><span class="sxs-lookup"><span data-stu-id="2e77f-282">K_18</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-283">10404</span><span class="sxs-lookup"><span data-stu-id="2e77f-283">10404</span></span></td>
<td><span data-ttu-id="2e77f-284">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-284">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-285">K_17</span><span class="sxs-lookup"><span data-stu-id="2e77f-285">K_17</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-286">10406</span><span class="sxs-lookup"><span data-stu-id="2e77f-286">10406</span></span></td>
<td><span data-ttu-id="2e77f-287">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-287">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-288">K_18</span><span class="sxs-lookup"><span data-stu-id="2e77f-288">K_18</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="2e77f-289"><strong>VAT5</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-289"><strong>VAT5</strong></span></span></td>
<td><span data-ttu-id="2e77f-290">10501</span><span class="sxs-lookup"><span data-stu-id="2e77f-290">10501</span></span></td>
<td><span data-ttu-id="2e77f-291">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="2e77f-291">Taxable sales</span></span></td>
<td><span data-ttu-id="2e77f-292">K_15</span><span class="sxs-lookup"><span data-stu-id="2e77f-292">K_15</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-293">10502</span><span class="sxs-lookup"><span data-stu-id="2e77f-293">10502</span></span></td>
<td><span data-ttu-id="2e77f-294">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-294">Tax-free sale</span></span></td>
<td><span data-ttu-id="2e77f-295">K_10</span><span class="sxs-lookup"><span data-stu-id="2e77f-295">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-296">10503</span><span class="sxs-lookup"><span data-stu-id="2e77f-296">10503</span></span></td>
<td><span data-ttu-id="2e77f-297">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="2e77f-297">Sales tax payable</span></span></td>
<td><span data-ttu-id="2e77f-298">K_16</span><span class="sxs-lookup"><span data-stu-id="2e77f-298">K_16</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-299">10504</span><span class="sxs-lookup"><span data-stu-id="2e77f-299">10504</span></span></td>
<td><span data-ttu-id="2e77f-300">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-300">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-301">K_15</span><span class="sxs-lookup"><span data-stu-id="2e77f-301">K_15</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-302">10506</span><span class="sxs-lookup"><span data-stu-id="2e77f-302">10506</span></span></td>
<td><span data-ttu-id="2e77f-303">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-303">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-304">K_16</span><span class="sxs-lookup"><span data-stu-id="2e77f-304">K_16</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="2e77f-305"><strong>VAT0</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-305"><strong>VAT0</strong></span></span></td>
<td><span data-ttu-id="2e77f-306">10601</span><span class="sxs-lookup"><span data-stu-id="2e77f-306">10601</span></span></td>
<td><span data-ttu-id="2e77f-307">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="2e77f-307">Taxable sales</span></span></td>
<td><span data-ttu-id="2e77f-308">K_13</span><span class="sxs-lookup"><span data-stu-id="2e77f-308">K_13</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-309">10602</span><span class="sxs-lookup"><span data-stu-id="2e77f-309">10602</span></span></td>
<td><span data-ttu-id="2e77f-310">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-310">Tax-free sale</span></span></td>
<td><span data-ttu-id="2e77f-311">K_10</span><span class="sxs-lookup"><span data-stu-id="2e77f-311">K_10</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-312">10604</span><span class="sxs-lookup"><span data-stu-id="2e77f-312">10604</span></span></td>
<td><span data-ttu-id="2e77f-313">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-313">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-314">K_13</span><span class="sxs-lookup"><span data-stu-id="2e77f-314">K_13</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="2e77f-315"><strong>ART129</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-315"><strong>ART129</strong></span></span></td>
<td><span data-ttu-id="2e77f-316">10701</span><span class="sxs-lookup"><span data-stu-id="2e77f-316">10701</span></span></td>
<td><span data-ttu-id="2e77f-317">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="2e77f-317">Taxable sales</span></span></td>
<td><span data-ttu-id="2e77f-318">K_14</span><span class="sxs-lookup"><span data-stu-id="2e77f-318">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-319">10702</span><span class="sxs-lookup"><span data-stu-id="2e77f-319">10702</span></span></td>
<td><span data-ttu-id="2e77f-320">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-320">Tax-free sale</span></span></td>
<td><span data-ttu-id="2e77f-321">K_14</span><span class="sxs-lookup"><span data-stu-id="2e77f-321">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-322">10704</span><span class="sxs-lookup"><span data-stu-id="2e77f-322">10704</span></span></td>
<td><span data-ttu-id="2e77f-323">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-323">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-324">K_14</span><span class="sxs-lookup"><span data-stu-id="2e77f-324">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-325">10705</span><span class="sxs-lookup"><span data-stu-id="2e77f-325">10705</span></span></td>
<td><span data-ttu-id="2e77f-326">Faktura korygująca sprzedaży zwolnionej z podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-326">Tax exempt sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-327">K_14</span><span class="sxs-lookup"><span data-stu-id="2e77f-327">K_14</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="2e77f-328"><strong>IntraEUGoods</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-328"><strong>IntraEUGoods</strong></span></span></td>
<td><span data-ttu-id="2e77f-329">10801</span><span class="sxs-lookup"><span data-stu-id="2e77f-329">10801</span></span></td>
<td><span data-ttu-id="2e77f-330">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-330">Tax-free sale</span></span></td>
<td><span data-ttu-id="2e77f-331">K_21</span><span class="sxs-lookup"><span data-stu-id="2e77f-331">K_21</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-332">10810</span><span class="sxs-lookup"><span data-stu-id="2e77f-332">10810</span></span></td>
<td><span data-ttu-id="2e77f-333">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="2e77f-333">Taxable import</span></span></td>
<td><span data-ttu-id="2e77f-334">K_23</span><span class="sxs-lookup"><span data-stu-id="2e77f-334">K_23</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-335">10812</span><span class="sxs-lookup"><span data-stu-id="2e77f-335">10812</span></span></td>
<td><span data-ttu-id="2e77f-336">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="2e77f-336">Use tax</span></span></td>
<td><span data-ttu-id="2e77f-337">K_24</span><span class="sxs-lookup"><span data-stu-id="2e77f-337">K_24</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="2e77f-338"><strong>ExportOfGoods</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-338"><strong>ExportOfGoods</strong></span></span></td>
<td><span data-ttu-id="2e77f-339">10901</span><span class="sxs-lookup"><span data-stu-id="2e77f-339">10901</span></span></td>
<td><span data-ttu-id="2e77f-340">Sprzedaż wolna od podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-340">Tax-free sale</span></span></td>
<td><span data-ttu-id="2e77f-341">K_22</span><span class="sxs-lookup"><span data-stu-id="2e77f-341">K_22</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-342">10905</span><span class="sxs-lookup"><span data-stu-id="2e77f-342">10905</span></span></td>
<td><span data-ttu-id="2e77f-343">Faktura korygująca sprzedaży zwolnionej z podatku</span><span class="sxs-lookup"><span data-stu-id="2e77f-343">Tax exempt sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-344">K_22</span><span class="sxs-lookup"><span data-stu-id="2e77f-344">K_22</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="2e77f-345"><strong>ImportOfGoodsART33</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-345"><strong>ImportOfGoodsART33</strong></span></span></td>
<td><span data-ttu-id="2e77f-346">20207</span><span class="sxs-lookup"><span data-stu-id="2e77f-346">20207</span></span></td>
<td><span data-ttu-id="2e77f-347">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="2e77f-347">Taxable import</span></span></td>
<td><span data-ttu-id="2e77f-348">K_45</span><span class="sxs-lookup"><span data-stu-id="2e77f-348">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-349">11010</span><span class="sxs-lookup"><span data-stu-id="2e77f-349">11010</span></span></td>
<td><span data-ttu-id="2e77f-350">Przeciwstawna wartość importu podlegająca opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="2e77f-350">Offset Taxable import</span></span></td>
<td><span data-ttu-id="2e77f-351">K_25</span><span class="sxs-lookup"><span data-stu-id="2e77f-351">K_25</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-352">20209</span><span class="sxs-lookup"><span data-stu-id="2e77f-352">20209</span></span></td>
<td><span data-ttu-id="2e77f-353">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="2e77f-353">Use tax</span></span></td>
<td><span data-ttu-id="2e77f-354">K_46</span><span class="sxs-lookup"><span data-stu-id="2e77f-354">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-355">11012</span><span class="sxs-lookup"><span data-stu-id="2e77f-355">11012</span></span></td>
<td><span data-ttu-id="2e77f-356">Konto przeciwstawne podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="2e77f-356">Offset use tax</span></span></td>
<td><span data-ttu-id="2e77f-357">K_26</span><span class="sxs-lookup"><span data-stu-id="2e77f-357">K_26</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="2e77f-358"><strong>ImportOfServices</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-358"><strong>ImportOfServices</strong></span></span></td>
<td><span data-ttu-id="2e77f-359">20207</span><span class="sxs-lookup"><span data-stu-id="2e77f-359">20207</span></span></td>
<td><span data-ttu-id="2e77f-360">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="2e77f-360">Taxable import</span></span></td>
<td><span data-ttu-id="2e77f-361">K_45</span><span class="sxs-lookup"><span data-stu-id="2e77f-361">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-362">11110</span><span class="sxs-lookup"><span data-stu-id="2e77f-362">11110</span></span></td>
<td><span data-ttu-id="2e77f-363">Przeciwstawna wartość importu podlegająca opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="2e77f-363">Offset Taxable import</span></span></td>
<td><span data-ttu-id="2e77f-364">K_27</span><span class="sxs-lookup"><span data-stu-id="2e77f-364">K_27</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-365">20209</span><span class="sxs-lookup"><span data-stu-id="2e77f-365">20209</span></span></td>
<td><span data-ttu-id="2e77f-366">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="2e77f-366">Use tax</span></span></td>
<td><span data-ttu-id="2e77f-367">K_46</span><span class="sxs-lookup"><span data-stu-id="2e77f-367">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-368">11112</span><span class="sxs-lookup"><span data-stu-id="2e77f-368">11112</span></span></td>
<td><span data-ttu-id="2e77f-369">Konto przeciwstawne podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="2e77f-369">Offset use tax</span></span></td>
<td><span data-ttu-id="2e77f-370">K_28</span><span class="sxs-lookup"><span data-stu-id="2e77f-370">K_28</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="2e77f-371"><strong>ImportART28</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-371"><strong>ImportART28</strong></span></span></td>
<td><span data-ttu-id="2e77f-372">20207</span><span class="sxs-lookup"><span data-stu-id="2e77f-372">20207</span></span></td>
<td><span data-ttu-id="2e77f-373">Import opodatkowany</span><span class="sxs-lookup"><span data-stu-id="2e77f-373">Taxable import</span></span></td>
<td><span data-ttu-id="2e77f-374">K_45</span><span class="sxs-lookup"><span data-stu-id="2e77f-374">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-375">11210</span><span class="sxs-lookup"><span data-stu-id="2e77f-375">11210</span></span></td>
<td><span data-ttu-id="2e77f-376">Przeciwstawna wartość importu podlegająca opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="2e77f-376">Offset Taxable import</span></span></td>
<td><span data-ttu-id="2e77f-377">K_29</span><span class="sxs-lookup"><span data-stu-id="2e77f-377">K_29</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-378">20209</span><span class="sxs-lookup"><span data-stu-id="2e77f-378">20209</span></span></td>
<td><span data-ttu-id="2e77f-379">Podatek nienaliczony</span><span class="sxs-lookup"><span data-stu-id="2e77f-379">Use tax</span></span></td>
<td><span data-ttu-id="2e77f-380">K_46</span><span class="sxs-lookup"><span data-stu-id="2e77f-380">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-381">11212</span><span class="sxs-lookup"><span data-stu-id="2e77f-381">11212</span></span></td>
<td><span data-ttu-id="2e77f-382">Konto przeciwstawne podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="2e77f-382">Offset use tax</span></span></td>
<td><span data-ttu-id="2e77f-383">K_30</span><span class="sxs-lookup"><span data-stu-id="2e77f-383">K_30</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="2e77f-384"><strong>ReverseCharge</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-384"><strong>ReverseCharge</strong></span></span></td>
<td><span data-ttu-id="2e77f-385">11301</span><span class="sxs-lookup"><span data-stu-id="2e77f-385">11301</span></span></td>
<td><span data-ttu-id="2e77f-386">Sprzedaż opodatkowana</span><span class="sxs-lookup"><span data-stu-id="2e77f-386">Taxable sales</span></span></td>
<td><span data-ttu-id="2e77f-387">K_31</span><span class="sxs-lookup"><span data-stu-id="2e77f-387">K_31</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-388">11302</span><span class="sxs-lookup"><span data-stu-id="2e77f-388">11302</span></span></td>
<td><span data-ttu-id="2e77f-389">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="2e77f-389">Sales tax payable</span></span></td>
<td><span data-ttu-id="2e77f-390">K_35</span><span class="sxs-lookup"><span data-stu-id="2e77f-390">K_35</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-391">11304</span><span class="sxs-lookup"><span data-stu-id="2e77f-391">11304</span></span></td>
<td><span data-ttu-id="2e77f-392">Opodatkowana faktura korygująca sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-392">Taxable sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-393">K_31</span><span class="sxs-lookup"><span data-stu-id="2e77f-393">K_31</span></span></td>
<td>-</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-394">11306</span><span class="sxs-lookup"><span data-stu-id="2e77f-394">11306</span></span></td>
<td><span data-ttu-id="2e77f-395">Podatek od faktury korygującej sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2e77f-395">Sales tax on sales credit note</span></span></td>
<td><span data-ttu-id="2e77f-396">K_35</span><span class="sxs-lookup"><span data-stu-id="2e77f-396">K_35</span></span></td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="2e77f-397"><strong>FixedAssetPurch</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-397"><strong>FixedAssetPurch</strong></span></span></td>
<td><span data-ttu-id="2e77f-398">20107</span><span class="sxs-lookup"><span data-stu-id="2e77f-398">20107</span></span></td>
<td><span data-ttu-id="2e77f-399">Zakup podlegający opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="2e77f-399">Taxable purchases</span></span></td>
<td><span data-ttu-id="2e77f-400">K_43</span><span class="sxs-lookup"><span data-stu-id="2e77f-400">K_43</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-401">20109</span><span class="sxs-lookup"><span data-stu-id="2e77f-401">20109</span></span></td>
<td><span data-ttu-id="2e77f-402">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="2e77f-402">Sales tax receivable</span></span></td>
<td><span data-ttu-id="2e77f-403">K_44</span><span class="sxs-lookup"><span data-stu-id="2e77f-403">K_44</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-404">20115</span><span class="sxs-lookup"><span data-stu-id="2e77f-404">20115</span></span></td>
<td><span data-ttu-id="2e77f-405">Opodatkowana faktura korygująca zakupu</span><span class="sxs-lookup"><span data-stu-id="2e77f-405">Taxable purchase credit note</span></span></td>
<td><span data-ttu-id="2e77f-406">K_43</span><span class="sxs-lookup"><span data-stu-id="2e77f-406">K_43</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-407">20116</span><span class="sxs-lookup"><span data-stu-id="2e77f-407">20116</span></span></td>
<td><span data-ttu-id="2e77f-408">Podatek od faktury korygującej zakupu</span><span class="sxs-lookup"><span data-stu-id="2e77f-408">Sales tax on purchase credit note</span></span></td>
<td><span data-ttu-id="2e77f-409">K_47</span><span class="sxs-lookup"><span data-stu-id="2e77f-409">K_47</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="2e77f-410"><strong>GoodServPurch</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-410"><strong>GoodServPurch</strong></span></span></td>
<td><span data-ttu-id="2e77f-411">20207</span><span class="sxs-lookup"><span data-stu-id="2e77f-411">20207</span></span></td>
<td><span data-ttu-id="2e77f-412">Zakup podlegający opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="2e77f-412">Taxable purchases</span></span></td>
<td><span data-ttu-id="2e77f-413">K_45</span><span class="sxs-lookup"><span data-stu-id="2e77f-413">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-414">20209</span><span class="sxs-lookup"><span data-stu-id="2e77f-414">20209</span></span></td>
<td><span data-ttu-id="2e77f-415">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="2e77f-415">Sales tax receivable</span></span></td>
<td><span data-ttu-id="2e77f-416">K_46</span><span class="sxs-lookup"><span data-stu-id="2e77f-416">K_46</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-417">20215</span><span class="sxs-lookup"><span data-stu-id="2e77f-417">20215</span></span></td>
<td><span data-ttu-id="2e77f-418">Opodatkowana faktura korygująca zakupu</span><span class="sxs-lookup"><span data-stu-id="2e77f-418">Taxable purchase credit note</span></span></td>
<td><span data-ttu-id="2e77f-419">K_45</span><span class="sxs-lookup"><span data-stu-id="2e77f-419">K_45</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-420">20216</span><span class="sxs-lookup"><span data-stu-id="2e77f-420">20216</span></span></td>
<td><span data-ttu-id="2e77f-421">Podatek od faktury korygującej zakupu</span><span class="sxs-lookup"><span data-stu-id="2e77f-421">Sales tax on purchase credit note</span></span></td>
<td><span data-ttu-id="2e77f-422">K_48</span><span class="sxs-lookup"><span data-stu-id="2e77f-422">K_48</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="2e77f-423"><strong>CorrATR89b1</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-423"><strong>CorrATR89b1</strong></span></span></td>
<td><span data-ttu-id="2e77f-424">30101</span><span class="sxs-lookup"><span data-stu-id="2e77f-424">30101</span></span></td>
<td><span data-ttu-id="2e77f-425">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="2e77f-425">Sales tax payable</span></span></td>
<td><span data-ttu-id="2e77f-426">K_49</span><span class="sxs-lookup"><span data-stu-id="2e77f-426">K_49</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-427">30109</span><span class="sxs-lookup"><span data-stu-id="2e77f-427">30109</span></span></td>
<td><span data-ttu-id="2e77f-428">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="2e77f-428">Sales tax receivable</span></span></td>
<td><span data-ttu-id="2e77f-429">K_49</span><span class="sxs-lookup"><span data-stu-id="2e77f-429">K_49</span></span></td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="2e77f-430"><strong>CorrATR89b4</strong></span><span class="sxs-lookup"><span data-stu-id="2e77f-430"><strong>CorrATR89b4</strong></span></span></td>
<td><span data-ttu-id="2e77f-431">30201</span><span class="sxs-lookup"><span data-stu-id="2e77f-431">30201</span></span></td>
<td><span data-ttu-id="2e77f-432">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="2e77f-432">Sales tax payable</span></span></td>
<td><span data-ttu-id="2e77f-433">K_50</span><span class="sxs-lookup"><span data-stu-id="2e77f-433">K_50</span></span></td>
<td>+</td>
</tr>
<tr>
<td><span data-ttu-id="2e77f-434">30209</span><span class="sxs-lookup"><span data-stu-id="2e77f-434">30209</span></span></td>
<td><span data-ttu-id="2e77f-435">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="2e77f-435">Sales tax receivable</span></span></td>
<td><span data-ttu-id="2e77f-436">K_50</span><span class="sxs-lookup"><span data-stu-id="2e77f-436">K_50</span></span></td>
<td>+</td>
</tr>
</tbody>
</table>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="2e77f-437">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu</span><span class="sxs-lookup"><span data-stu-id="2e77f-437">Configure the ER model, and format for the report</span></span>

<span data-ttu-id="2e77f-438">Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-438">To review or change the configuration for the SAF VAT sales and purchase register, on the **Reporting configurations** page, in the list of models, select the **Standard Audit File (SAF-T)** model.</span></span> <span data-ttu-id="2e77f-439">Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model.</span><span class="sxs-lookup"><span data-stu-id="2e77f-439">Then click **Designer** to review or change the model.</span></span> <span data-ttu-id="2e77f-440">Aby przejrzeć lub zmodyfikować format rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Rejestr VAT (PL)** i kliknij przycisk **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-440">To review or change the format for the SAF VAT sales and purchase register, on the **Reporting configurations** page, under **Standard Audit File (SAF-T)**, select **VAT Register (PL)**, and then click **Designer**.</span></span> <span data-ttu-id="2e77f-441">Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="2e77f-441">For more information about ER, see the following topics:</span></span>

-   [<span data-ttu-id="2e77f-442">Omówienie Raportowania elektroniczne</span><span class="sxs-lookup"><span data-stu-id="2e77f-442">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="2e77f-443">Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="2e77f-443">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="2e77f-444">Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="2e77f-444">Localization requirements - Create a ER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

<span data-ttu-id="2e77f-445">Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej.</span><span class="sxs-lookup"><span data-stu-id="2e77f-445">Initially, the configuration is an example of VAT Register based on Reporting codes described in table above.</span></span> <span data-ttu-id="2e77f-446">Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2e77f-446">If you need to adopt the configuration to another set of reporting codes, you should derive the format of the configuration.</span></span> <span data-ttu-id="2e77f-447">W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-447">To do so, select the format in the configuration's tree and click **Create configuration** in **Main menu**.</span></span> <span data-ttu-id="2e77f-448">Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-448">**Mark Derive from name:...,** fill in **Name** and **Description** fields of a new format and click **Create configuration** button.</span></span> <span data-ttu-id="2e77f-449">Utworzony format jest kopią formatu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="2e77f-449">Created format is a copy of the parent format.</span></span> <span data-ttu-id="2e77f-450">Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania.</span><span class="sxs-lookup"><span data-stu-id="2e77f-450">Select the created format and click **Designer** on the **Main menu** to open format designer and update format with your reporting codes.</span></span> <span data-ttu-id="2e77f-451">Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane).</span><span class="sxs-lookup"><span data-stu-id="2e77f-451">Format designer window is divided into two parts: the left side â€“ is a format structure (in VAT register case it is a XML scheme); the right side â€“ is a Data Model (data).</span></span> <span data-ttu-id="2e77f-452">Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-452">Press **Mapping** button in the right side to see the **Data model**.</span></span> <span data-ttu-id="2e77f-453">Model danych zawiera wszystkie pola wszystkich raportów SAF-T.</span><span class="sxs-lookup"><span data-stu-id="2e77f-453">The Data Model includes all the field for all the SAF-T reports.</span></span> <span data-ttu-id="2e77f-454">Format rejestru VAT jest mapowany głównie do węzła **TaxTransaction**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-454">VAT register format is mapped mostly to the **TaxTransaction** node.</span></span> <span data-ttu-id="2e77f-455">Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł.</span><span class="sxs-lookup"><span data-stu-id="2e77f-455">Scroll down the tree to find and select it.</span></span> <span data-ttu-id="2e77f-456">Wszystkie transakcje podatkowe są podzielone na dwie grupy: według znacznika **SprzedazWiersz** i według znacznika **ZakupWiersz**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-456">All tax transactions are grouped into two groups: for tag **SprzedazWiersz** and for tag **ZakupWiersz**.</span></span> <span data-ttu-id="2e77f-457">Oraz zatytułowane odpowiednio **$SalesList** i **$PurchaseList**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-457">And called **$SalesList** and **$PurchaseList** respectively.</span></span> <span data-ttu-id="2e77f-458">Są to listy rekordów obliczane (filtrowane) według formuł.</span><span class="sxs-lookup"><span data-stu-id="2e77f-458">These are record lists calculated (filtered) by formulas.</span></span> <span data-ttu-id="2e77f-459">Formuły można przeglądać i modyfikować w redaktorze formuł.</span><span class="sxs-lookup"><span data-stu-id="2e77f-459">You can review and modify formula in formula redactor.</span></span> <span data-ttu-id="2e77f-460">W tym celu należy zaznaczyć pole obliczeniowe lub listę rekordów (w tym konkretnym przypadku), a następnie w menu drzewa kliknąć przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-460">To do so, select calculated field or record list (in this particular case) and click **Edit** in tree menu.</span></span> <span data-ttu-id="2e77f-461">Zmodyfikuj formuły dla grup **$SalesList** i **$PurchaseList** zgodnie z kodami raportowania używanymi w firmie, a następnie je zapisz.</span><span class="sxs-lookup"><span data-stu-id="2e77f-461">Edit formulas for **$SalesList** and **$PurchaseList** according to your company's Reporting codes and save them.</span></span> <span data-ttu-id="2e77f-462">Okno projektanta formuł po lewej stronie zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować.</span><span class="sxs-lookup"><span data-stu-id="2e77f-462">Formula designer window in the left side shows the Data model where you can select fields or record lists and in the right side all the functions which you may implement.</span></span> <span data-ttu-id="2e77f-463">(Więcej informacji o projektancie formatów — [Projektant formuł w raportowaniu elektronicznym](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md)).</span><span class="sxs-lookup"><span data-stu-id="2e77f-463">(More information about Format designer - [Formula designer in Electronic reporting](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md)).</span></span> <span data-ttu-id="2e77f-464">Po podzieleniu transakcji podatkowych na dwie grupy należy wewnątrz każdej grupy pogrupować transakcje dla każdego znacznika zgodnie z kodami raportowania używanymi w firmie.</span><span class="sxs-lookup"><span data-stu-id="2e77f-464">After Tax transactions were divided into two groups, inside each of both groups Tax transactions should be grouped for each tag according to your company's Reporting codes.</span></span> <span data-ttu-id="2e77f-465">Znajdź pola obliczeniowe „list\_K” w grupach **$SalesList** i **$PurchaseList** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł.</span><span class="sxs-lookup"><span data-stu-id="2e77f-465">Find calculated fields "list\_K" under **$SalesList** and **$PurchaseList** and update their formulas with your Reporting codes using Formula Designer.</span></span> <span data-ttu-id="2e77f-466">Po zaktualizowaniu formuł wszystkich węzłów „list\_K”</span><span class="sxs-lookup"><span data-stu-id="2e77f-466">After all "list\_K"?</span></span> <span data-ttu-id="2e77f-467">odszukaj i zmodyfikuj elementy **SalasCtrl** i **PurchCtrl** odpowiednio w grupach **$SalesList** i **$PurchaseList**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-467">nodes formulas were updated find and modify **SalasCtrl** and **PurchCtrl** under **$SalesList** and **$PurchaseList** respectively.</span></span> <span data-ttu-id="2e77f-468">Te węzły są używane odpowiednio przez znaczniki **SprzedazCtrl** i **ZakupCtrl**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-468">These nodes are used for **SprzedazCtrl** and **ZakupCtrl**  tags respectively.</span></span> <span data-ttu-id="2e77f-469">Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie.</span><span class="sxs-lookup"><span data-stu-id="2e77f-469">Basically, no other modifications in the format are needed.</span></span> <span data-ttu-id="2e77f-470">Zapisz format.</span><span class="sxs-lookup"><span data-stu-id="2e77f-470">Save the format.</span></span> <span data-ttu-id="2e77f-471">Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-471">Close it and complete the format using **Change status** &gt; **Complete** button on the versions menu on **Versions** FastTab on **Configurations**.</span></span>

### <a name="generate-a-saf-vat-sales-and-purchase-register"></a><span data-ttu-id="2e77f-472">Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT</span><span class="sxs-lookup"><span data-stu-id="2e77f-472">Generate a SAF VAT sales and purchase register</span></span>

<span data-ttu-id="2e77f-473">Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Rejestr SAF sprzedaży i zakupów objętych podatkiem VAT** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="2e77f-473">To generate a SAF VAT sales and purchase register, click **General ledger** &gt; **Inquiries and reports** &gt; **Standard Audit File for Tax (SAF-T)** &gt; **SAF VAT sales and purchase register**, and set the following parameters.</span></span>

|                              |                                                                                    |
|------------------------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="2e77f-474">**Parametr**</span><span class="sxs-lookup"><span data-stu-id="2e77f-474">**Parameter**</span></span>                | <span data-ttu-id="2e77f-475">**Opis**</span><span class="sxs-lookup"><span data-stu-id="2e77f-475">**Description**</span></span>                                                                    |
| <span data-ttu-id="2e77f-476">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-476">**From date**</span></span>                | <span data-ttu-id="2e77f-477">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-477">Specify the first date to export reporting data for.</span></span>                               |
| <span data-ttu-id="2e77f-478">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-478">**To date**</span></span>                  | <span data-ttu-id="2e77f-479">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-479">Specify that last date to export reporting data for.</span></span>                               |
| <span data-ttu-id="2e77f-480">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-480">**Authority identification**</span></span> | <span data-ttu-id="2e77f-481">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-481">In the list, select the identifier of the tax authority to use in the export file.</span></span> |

<span data-ttu-id="2e77f-482">Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-482">You can specify additional selection parameters by using the **Filter** functionality on the **Records to include** tab.</span></span>

### <a name="generate-a-saf-vat-invoices-file"></a><span data-ttu-id="2e77f-483">Generowanie pliku faktur VAT SAF</span><span class="sxs-lookup"><span data-stu-id="2e77f-483">Generate a SAF VAT invoices file</span></span>

<span data-ttu-id="2e77f-484">Aby można było wygenerować plik faktur VAT SAF, należy wykonać następujące dodatkowe czynności konfiguracyjne:</span><span class="sxs-lookup"><span data-stu-id="2e77f-484">Before you can generate a SAF VAT invoices file, you must complete the following additional setup.</span></span>

-   <span data-ttu-id="2e77f-485">Skonfiguruj urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="2e77f-485">Set up sales tax authorities.</span></span>
-   <span data-ttu-id="2e77f-486">Kody podatków dla raportowania podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="2e77f-486">Sales tax codes for VAT reporting.</span></span>
-   <span data-ttu-id="2e77f-487">Ustawianie kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="2e77f-487">Set up sales tax codes.</span></span>
-   <span data-ttu-id="2e77f-488">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-488">Configure the ER model, and format for the report.</span></span>

<span data-ttu-id="2e77f-489">To konfigurowanie przypomina dodatkowe konfigurowanie wykonane dla rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, z wyjątkiem czynności **Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-489">This setup resembles the additional setup that you completed for the SAF VAT sales and purchase register excepting **Configure the ER model, and format for the report.**</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="2e77f-490">Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu</span><span class="sxs-lookup"><span data-stu-id="2e77f-490">Configure the ER model, and format for the report</span></span>

<span data-ttu-id="2e77f-491">Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-491">To review or change the configuration for the SAF VAT sales and purchase register, on the **Reporting configurations** page, in the list of models, select the **Standard Audit File (SAF-T)** model.</span></span> <span data-ttu-id="2e77f-492">Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model.</span><span class="sxs-lookup"><span data-stu-id="2e77f-492">Then click **Designer** to review or change the model.</span></span> <span data-ttu-id="2e77f-493">Aby przejrzeć lub zmodyfikować faktury VAT SAF, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Faktury VAT (PL)** i kliknij przycisk **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-493">To review or change the format for the SAF VAT invoices, on the **Reporting configurations** page, under **Standard Audit File (SAF-T)**, select **VAT invoices (PL)**, and then click **Designer**.</span></span> <span data-ttu-id="2e77f-494">Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="2e77f-494">For more information about ER, see the following topics:</span></span>

-   [<span data-ttu-id="2e77f-495">Omówienie Raportowania elektroniczne</span><span class="sxs-lookup"><span data-stu-id="2e77f-495">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="2e77f-496">Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="2e77f-496">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="2e77f-497">Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="2e77f-497">Localization requirements - Create a ER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

<span data-ttu-id="2e77f-498">Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej.</span><span class="sxs-lookup"><span data-stu-id="2e77f-498">Initially, the configuration is an example of VAT Register based on Reporting codes described in table above.</span></span> <span data-ttu-id="2e77f-499">Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2e77f-499">If you need to adopt the configuration to another set of reporting codes, you should derive the format of the configuration.</span></span> <span data-ttu-id="2e77f-500">W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-500">To do so, select the format in the configuration's tree and click **Create configuration** in **Main menu**.</span></span> <span data-ttu-id="2e77f-501">Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-501">**Mark Derive from name:...,** fill in **Name** and **Description** fields of a new format and click **Create configuration** button.</span></span> <span data-ttu-id="2e77f-502">Utworzony format jest kopią formatu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="2e77f-502">Created format is a copy of the parent format.</span></span> <span data-ttu-id="2e77f-503">Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania.</span><span class="sxs-lookup"><span data-stu-id="2e77f-503">Select the created format and click **Designer** on the **Main menu** to open format designer and update format with your reporting codes.</span></span> <span data-ttu-id="2e77f-504">Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane).</span><span class="sxs-lookup"><span data-stu-id="2e77f-504">Format designer window is divided into two parts: the left side is a format structure (in VAT register case it is a XML scheme); the right side is a Data Model (data).</span></span> <span data-ttu-id="2e77f-505">Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-505">Press **Mapping** button in the right side to see the **Data model**.</span></span> <span data-ttu-id="2e77f-506">Model danych zawiera wszystkie pola wszystkich raportów SAF-T.</span><span class="sxs-lookup"><span data-stu-id="2e77f-506">The Data Model includes all the field for all the SAF-T reports.</span></span> <span data-ttu-id="2e77f-507">Format **Faktury VAT** składa się z kilku sekcji z różnymi źródłami danych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-507">**VAT invoices** format includes several parts with different data sources.</span></span> <span data-ttu-id="2e77f-508">Dane pod znacznikiem **Faktura** są mapowane głównie do węzła **Model &gt; SourceDocuments &gt; $Invoices**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-508">Data under tag **Faktura** is mapped mostly to the **Model &gt; SourceDocuments &gt; $Invoices** node.</span></span> <span data-ttu-id="2e77f-509">Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł.</span><span class="sxs-lookup"><span data-stu-id="2e77f-509">Scroll down the tree to find and select it.</span></span> <span data-ttu-id="2e77f-510">Znajdź pola obliczeniowe **list\_P\_** w węźle **$Invoices** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł.</span><span class="sxs-lookup"><span data-stu-id="2e77f-510">Find calculated fields **list\_P\_** under **$Invoices** node and update their formulas with your Reporting codes using Formula Designer.</span></span> <span data-ttu-id="2e77f-511">Okno projektanta formuł zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować.</span><span class="sxs-lookup"><span data-stu-id="2e77f-511">The Formula designer window shows the data model where you can select fields or record lists and in the right side all the functions which you may implement.</span></span> <span data-ttu-id="2e77f-512">Aby uzyskać więcej informacji o projektancie formatów, zobacz [Projektant formuł w raportowaniu elektronicznym](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md).</span><span class="sxs-lookup"><span data-stu-id="2e77f-512">For more information about Format designer, see [Formula designer in Electronic reporting](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md).</span></span> <span data-ttu-id="2e77f-513">Wartości znaczników pod znacznikiem **StawkiPodatku** są stałe.</span><span class="sxs-lookup"><span data-stu-id="2e77f-513">Values for tags under **StawkiPodatku** tag is constants.</span></span> <span data-ttu-id="2e77f-514">Zaznacz węzeł wartości (ciąg) dla każdego znacznika pod znacznikiem **StawkiPodatku** i ustaw mu wartość w polu **Wartość** na karcie **Format** z prawej strony okna **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-514">Select value node (String) for each of tag under **StawkiPodatku** tag and set up its value in **Value** field on **Format** tab on the right side of the **Designer**.</span></span> <span data-ttu-id="2e77f-515">Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie.</span><span class="sxs-lookup"><span data-stu-id="2e77f-515">Basically, no other modifications in the format are needed.</span></span> <span data-ttu-id="2e77f-516">Zapisz format.</span><span class="sxs-lookup"><span data-stu-id="2e77f-516">Save the format.</span></span> <span data-ttu-id="2e77f-517">Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-517">Close it and complete the format using **Change status** &gt; **Complete** button on the versions menu on **Versions** FastTab on **Configurations**.</span></span>

### <a name="generate-a-saf-vat-invoices"></a><span data-ttu-id="2e77f-518">Generowanie faktur VAT SAF</span><span class="sxs-lookup"><span data-stu-id="2e77f-518">Generate a SAF VAT invoices</span></span>

<span data-ttu-id="2e77f-519">Aby wygenerować plik faktur VAT SAF, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Faktury VAT SAF** i ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="2e77f-519">To generate a SAF VAT invoices file, click **General ledger** &gt; **Inquiries and reports** &gt; **Standard Audit File for Tax (SAF-T)** &gt; **SAF VAT invoices**, and set the following parameters.</span></span>

|                              |                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------|
| <span data-ttu-id="2e77f-520">Parametr</span><span class="sxs-lookup"><span data-stu-id="2e77f-520">Parameter</span></span>                    | <span data-ttu-id="2e77f-521">opis</span><span class="sxs-lookup"><span data-stu-id="2e77f-521">Description</span></span>                                                                            |
| <span data-ttu-id="2e77f-522">**Od dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-522">**From date**</span></span>                | <span data-ttu-id="2e77f-523">Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-523">Specify the first date to export reporting data for.</span></span>                                   |
| <span data-ttu-id="2e77f-524">**Do dnia**</span><span class="sxs-lookup"><span data-stu-id="2e77f-524">**To date**</span></span>                  | <span data-ttu-id="2e77f-525">Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-525">Specify the last date to export reporting data for.</span></span>                                    |
| <span data-ttu-id="2e77f-526">**Identyfikacja urzędu**</span><span class="sxs-lookup"><span data-stu-id="2e77f-526">**Authority identification**</span></span> | <span data-ttu-id="2e77f-527">Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-527">In the list, select the identifier of the tax authority to use in the export file.</span></span>     |
| <span data-ttu-id="2e77f-528">**Identyfikator faktury Od/Do**</span><span class="sxs-lookup"><span data-stu-id="2e77f-528">**Invoice ID From / To**</span></span>     | <span data-ttu-id="2e77f-529">Określ zakres identyfikatorów faktur, aby ograniczyć ilość faktur wybieranych dla eksportu danych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-529">Specify a range of invoice IDs to limit the invoice that are selected for data export.</span></span> |

<span data-ttu-id="2e77f-530">Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-530">You can specify additional selection parameters by using the **Filter** functionality on the **Records to include** tab.</span></span>

## <a name="using-batch-jobs-for-saft"></a><span data-ttu-id="2e77f-531">Używanie zadań wsadowych dla raportów SAFT</span><span class="sxs-lookup"><span data-stu-id="2e77f-531">Using batch jobs for SAFT</span></span>
<span data-ttu-id="2e77f-532">Generowanie raportów SAF-T za długi okres, taki jak miesiąc lub kwartał, może powodować objęcie bardzo dużej ilości danych i zajmować dużo czasu.</span><span class="sxs-lookup"><span data-stu-id="2e77f-532">Generating SAF-T reports for a long period such as month or a quarter can include a huge data and take a long time.</span></span> <span data-ttu-id="2e77f-533">W takich przypadkach zaleca się używanie zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="2e77f-533">For such cases, it is recommended to use batch jobs.</span></span> <span data-ttu-id="2e77f-534">Okno dialogowe dla każdego raportu SAF-T zawiera kartę **Uruchom w tle**. Otwórz tę kartę, aby ustawić generowanie raportu w trybie wsadowym.</span><span class="sxs-lookup"><span data-stu-id="2e77f-534">Dialog page for every SAF-T report has a **Run in the background** tab. Open this tab to set up report's generation in batch mode.</span></span> <span data-ttu-id="2e77f-535">Zaznacz pole wyboru **Przetwarzanie wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-535">Select **Batch processing** check box.</span></span> <span data-ttu-id="2e77f-536">Aby uzyskać więcej informacji na temat przetwarzania wsadowego, zobacz temat [Omówienie przetwarzania wsadowego](../../dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2e77f-536">To learn more about batch processing see the [Batch processing overview](../../dev-itpro/sysadmin/batch-processing-overview.md) topic.</span></span> <span data-ttu-id="2e77f-537">Aby przejrzeć zadania wsadowe lub znaleźć wygenerowany plik, otwórz okno **Administrowanie organizacją** &gt; **Raportowanie elektroniczne** &gt; **Zadania raportowania elektronicznego** i znajdź wiersz związany z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="2e77f-537">To review batch jobs or find generated file open **Organization administration** &gt; **Electronic reporting** &gt; **Electronic reporting jobs** and find a line related to your job.</span></span> <span data-ttu-id="2e77f-538">W **menu głównym** kliknij przycisk **Pokaż dziennik**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-538">Click **Show log** button on the **Main menu**.</span></span> <span data-ttu-id="2e77f-539">Jeżeli nic nie jest wyświetlane, oznacza to, że podczas generowania pliku nie zostały utworzone żadne komunikaty.</span><span class="sxs-lookup"><span data-stu-id="2e77f-539">If nothing is shown it means that no messages were produced during the file generation.</span></span> <span data-ttu-id="2e77f-540">Aby zobaczyć plik, w **menu głównym** kliknij przycisk **Pokaż pliki**, znajdź żądany plik i w **menu głównym** kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="2e77f-540">To see the file click **Show files** button on **Main menu**, find a file that you need and click **Open** on the **Main menu** to review or save the file.</span></span>  


