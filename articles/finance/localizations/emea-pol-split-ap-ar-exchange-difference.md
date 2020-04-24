---
title: Podziel zrealizowaną różnicę kursów kwoty na różnicę wartości netto faktury i kwoty VAT
description: W tym temacie opisano, jak podzielić zrealizowaną różnicę kursów kwoty na różnicę wartości netto faktury i kwoty podatku od towarów i usług (VAT).
author: anasyash
manager: ''
ms.date: 04/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 414136
ms.search.region: Poland
ms.author: shylaw
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-04-01
ms.openlocfilehash: de917429372daa261b96b1de0df7fe27f1b4e929
ms.sourcegitcommit: 88347d0f0ac862a77f269a05f1801d30dc93586e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2020
ms.locfileid: "3260244"
---
# <a name="split-the-realized-exchange-difference-amount-into-the-difference-of-the-invoice-net-value-and-the-vat-amount"></a><span data-ttu-id="e0983-103">Podziel zrealizowaną różnicę kursów kwoty na różnicę wartości netto faktury i kwoty VAT</span><span class="sxs-lookup"><span data-stu-id="e0983-103">Split the realized exchange difference amount into the difference of the invoice net value and the VAT amount</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0983-104">Funkcja **Podziel zrealizowaną różnicę kursową AP/AR na różnicę między wartością netto faktury i kwotą VAT** pozwala podzielić kwotę rozrachunków z dostawcami (punkt dostępu) i Rozrachunki z odbiorcami (AR) przeszacowanie w walucie obcej na dwie części:</span><span class="sxs-lookup"><span data-stu-id="e0983-104">The **Split the AP/AR realized exchange difference amount into the difference of the invoice net value and the VAT amount** feature lets you split the amount of an Accounts payable (AP) and Accounts receivable (AR) foreign currency revaluation into two parts:</span></span>

- <span data-ttu-id="e0983-105">Różnica kursowa związana z wartością netto faktury (zadłużenie odbiorcy i zobowiązania dostawcy)</span><span class="sxs-lookup"><span data-stu-id="e0983-105">The exchange difference that is related to the net value of the invoice (customer debts and vendor liabilities)</span></span>
- <span data-ttu-id="e0983-106">Różnica kursowa powiązana z kwotą podatku VAT na fakturze</span><span class="sxs-lookup"><span data-stu-id="e0983-106">The exchange difference that is related to the value-added tax (VAT) amount of the invoice</span></span>

<span data-ttu-id="e0983-107">Można również zaksięgować różnice kursowe powiązane z kwotą faktury VAT na oddzielne konto księgowe zrealizowanych zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="e0983-107">You can also post the exchange differences that are related to the VAT invoice amount to a separate ledger account of realized gains and losses.</span></span>

<span data-ttu-id="e0983-108">Ta funkcja jest dostępna tylko w firmach z polskim kontekstem kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="e0983-108">This feature is available only in legal entities that have a Polish country/region context.</span></span>

## <a name="setup"></a><span data-ttu-id="e0983-109">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="e0983-109">Setup</span></span>

### <a name="activate-the-feature"></a><span data-ttu-id="e0983-110">Aktywowanie funkcji</span><span class="sxs-lookup"><span data-stu-id="e0983-110">Activate the feature</span></span>

<span data-ttu-id="e0983-111">W obszarze roboczym **Zarządzanie funkcjami** włącz następującą funkcję: **(Polska) Podziel zrealizowaną różnicę kursową AP/AR na różnicę między wartością netto faktury i kwotą VAT**.</span><span class="sxs-lookup"><span data-stu-id="e0983-111">In the **Feature management** workspace, turn on the following feature: **(Poland) Split the AP/AR realized exchange difference amount into the difference of the invoice net value and the VAT amount**.</span></span>

### <a name="set-up-ledger-accounts"></a><span data-ttu-id="e0983-112">Konfigurowanie kont księgi</span><span class="sxs-lookup"><span data-stu-id="e0983-112">Set up ledger accounts</span></span>

<span data-ttu-id="e0983-113">Wykonaj poniższe kroki, aby skonfigurować konto księgowe, za pomocą którego można księgować kwotę różnicy kursowej powiązaną z kwotą podatku na fakturze.</span><span class="sxs-lookup"><span data-stu-id="e0983-113">Follow these steps to set up a ledger account that can be used to post the exchange difference amount that is related to the tax amount of the invoice.</span></span>

1. <span data-ttu-id="e0983-114">Przejdź do **Księga główna** \> **Waluty** \> **Konta przeszacowania waluty**.</span><span class="sxs-lookup"><span data-stu-id="e0983-114">Go to **General ledger** \> **Currencies** \> **Currency revaluation accounts**.</span></span> 
2. <span data-ttu-id="e0983-115">Na stronie **Konta przeszacowania waluty** wybierz kod waluty, a następnie w polu **Księga** wybierz kod firmy.</span><span class="sxs-lookup"><span data-stu-id="e0983-115">On the **Currency revaluation accounts** page, select the currency code, and then, in the **Ledger** field, select the code of the legal entity.</span></span>

    ![Strona Konta przeszacowania waluty](media/Currency-revaluation-accounts.png)

2. <span data-ttu-id="e0983-117">Wybierz wiersz, w którym pole **Księgowanie** jest ustawione jako **Zrealizowana dodatnia różnica kursowa** lub **Zrealizowana ujemna różnica kursowa**.</span><span class="sxs-lookup"><span data-stu-id="e0983-117">Select a line where the **Posting** field is set to **Realized gain** or **Realized loss**.</span></span>
3. <span data-ttu-id="e0983-118">Skonfiguruj konto główne i wybierz konto księgowe, na które chcesz zaksięgować zrealizowaną różnicę kursową.</span><span class="sxs-lookup"><span data-stu-id="e0983-118">Set up the main account, and select the ledger account to post the realized exchange difference to.</span></span>
4. <span data-ttu-id="e0983-119">W polu **Podatki** wybierz opcję **Wydatek**, aby zaksięgować część kwoty zrealizowanej różnicy kursowej powiązaną z kwotą podatku faktury na osobne konto księgowe wydatków.</span><span class="sxs-lookup"><span data-stu-id="e0983-119">In the **Sales taxes** field, select **Expense** to post part of the realized exchange difference amount that is related to the tax amount of the invoice to a separate expense ledger account.</span></span> 
5. <span data-ttu-id="e0983-120">W polu **Konto księgowania podatku** wybierz to samo konto księgowe wydatków.</span><span class="sxs-lookup"><span data-stu-id="e0983-120">In the **Tax posting account** field, select the same expense ledger account.</span></span>

## <a name="post-and-settle-customer-and-vendor-transactions"></a><span data-ttu-id="e0983-121">Księgowanie i rozliczanie transakcji odbiorcy i dostawcy</span><span class="sxs-lookup"><span data-stu-id="e0983-121">Post and settle customer and vendor transactions</span></span>

<span data-ttu-id="e0983-122">Umożliwia księgowanie i rozliczanie dokumentów w zwykły sposób.</span><span class="sxs-lookup"><span data-stu-id="e0983-122">Post and settle documents in the usual way.</span></span> <span data-ttu-id="e0983-123">Transakcja różnic kursowych tworzona podczas rozliczania spowoduje wygenerowanie załącznika, w którym kwota różnicy kursowej powiązana z kwotą podatku jest księgowana oddzielnie na koncie księgowym wybranym w polu **Konto księgowania podatku** na stronie **Konta przeszacowania waluty**.</span><span class="sxs-lookup"><span data-stu-id="e0983-123">The exchange difference transaction that is created during settlement will generate a voucher, where the exchange difference amount that is related to the tax amount is posted separately to the ledger account that you selected in the **Tax posting account** field on the **Currency revaluation accounts** page.</span></span>

## <a name="examples"></a><span data-ttu-id="e0983-124">Przykłady</span><span class="sxs-lookup"><span data-stu-id="e0983-124">Examples</span></span>

<span data-ttu-id="e0983-125">W poniższych dwóch przykładach są wyświetlane wynikowe transakcje finansowe.</span><span class="sxs-lookup"><span data-stu-id="e0983-125">The following two examples show the resulting ledger transactions.</span></span>

### <a name="example-1"></a><span data-ttu-id="e0983-126">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="e0983-126">Example 1</span></span>

<span data-ttu-id="e0983-127">Wykonaj następujące czynności konfiguracyjne w firmie **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="e0983-127">Complete the following setup in the **DEMF** legal entity.</span></span>

1. <span data-ttu-id="e0983-128">Zmień kraj/region na **POL**.</span><span class="sxs-lookup"><span data-stu-id="e0983-128">Change the country/region to **POL**.</span></span>
2. <span data-ttu-id="e0983-129">Na stronie **Księga** sprawdź, czy w polu **Waluta rozliczeniowa** określono wartość **EUR**.</span><span class="sxs-lookup"><span data-stu-id="e0983-129">On the **Ledger** page, verify that the **Accounting currency** field is set to **EUR**.</span></span>
3. <span data-ttu-id="e0983-130">Umożliwia konfigurowanie kursów wymiany walut dla **Domyślnego** typu kursu wymiany, co przedstawiono w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="e0983-130">Set up currency exchange rates for the **Default** exchange rate type, as shown in the following table.</span></span>

    | <span data-ttu-id="e0983-131">Data</span><span class="sxs-lookup"><span data-stu-id="e0983-131">Date</span></span>             | <span data-ttu-id="e0983-132">Dolary amerykańskie (USD)</span><span class="sxs-lookup"><span data-stu-id="e0983-132">US dollars (USD)</span></span> | <span data-ttu-id="e0983-133">Euro (EUR)</span><span class="sxs-lookup"><span data-stu-id="e0983-133">Euros (EUR)</span></span> | <span data-ttu-id="e0983-134">opis</span><span class="sxs-lookup"><span data-stu-id="e0983-134">Description</span></span>        |
    |------------------|------------------|-------------|--------------------|
    | <span data-ttu-id="e0983-135">1 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-135">January 1, 2020</span></span>  | <span data-ttu-id="e0983-136">100</span><span class="sxs-lookup"><span data-stu-id="e0983-136">100</span></span>              | <span data-ttu-id="e0983-137">80</span><span class="sxs-lookup"><span data-stu-id="e0983-137">80</span></span>          | <span data-ttu-id="e0983-138">100 USD za 80 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-138">100 USD for 80 EUR</span></span> |
    | <span data-ttu-id="e0983-139">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-139">January 10, 2020</span></span> | <span data-ttu-id="e0983-140">100</span><span class="sxs-lookup"><span data-stu-id="e0983-140">100</span></span>              | <span data-ttu-id="e0983-141">90</span><span class="sxs-lookup"><span data-stu-id="e0983-141">90</span></span>          | <span data-ttu-id="e0983-142">100 USD za 90 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-142">100 USD for 90 EUR</span></span> |

4. <span data-ttu-id="e0983-143">Skonfiguruj konta księgo dla zrealizowanej różnicy kursowej na kocnie głównym i koncie księgowania podatku.</span><span class="sxs-lookup"><span data-stu-id="e0983-143">Set up ledger accounts for the realized exchange difference in the main account and the tax posting account.</span></span>

<span data-ttu-id="e0983-144">Zaksięguj poniższe transakcje.</span><span class="sxs-lookup"><span data-stu-id="e0983-144">Post the following transactions.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0983-145">Wydruk pokwitowania</span><span class="sxs-lookup"><span data-stu-id="e0983-145">Document</span></span></th>
<th><span data-ttu-id="e0983-146">Data</span><span class="sxs-lookup"><span data-stu-id="e0983-146">Date</span></span></th>
<th><span data-ttu-id="e0983-147">Kwota w dolarach USD</span><span class="sxs-lookup"><span data-stu-id="e0983-147">Amount in USD</span></span></th>
<th><span data-ttu-id="e0983-148">Kwota w dolarach EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-148">Amount in EUR</span></span></th>
<th><span data-ttu-id="e0983-149">Załącznik</span><span class="sxs-lookup"><span data-stu-id="e0983-149">Voucher</span></span></th>
<th><span data-ttu-id="e0983-150">Kwota załącznika</span><span class="sxs-lookup"><span data-stu-id="e0983-150">Voucher amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='3'><span data-ttu-id="e0983-151">Faktura dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e0983-151">Customer invoice</span></span></td>
<td rowspan='3'><span data-ttu-id="e0983-152">1 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-152">January 1, 2020</span></span></td>
<td rowspan='3'><span data-ttu-id="e0983-153">119 USD, która zawiera kwotę podatku VAT 19 USD</span><span class="sxs-lookup"><span data-stu-id="e0983-153">119 USD, which includes a VAT amount of 19 USD</span></span></td>
<td rowspan='3'><span data-ttu-id="e0983-154">95.20 EUR, która zawiera kwotę podatku VAT 15.20 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-154">95.20 EUR, which includes a VAT amount of 15.20 EUR</span></span></td>
<td><span data-ttu-id="e0983-155">Debet <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="e0983-155">Debit <em>AR</em></span></span></td>
<td><span data-ttu-id="e0983-156">95.20</span><span class="sxs-lookup"><span data-stu-id="e0983-156">95.20</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-157">Kredyt <em>Wydatki</em></span><span class="sxs-lookup"><span data-stu-id="e0983-157">Credit <em>Expense</em></span></span></td>
<td><span data-ttu-id="e0983-158">80.00</span><span class="sxs-lookup"><span data-stu-id="e0983-158">80.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-159">Kredyt <em>VAT</em></span><span class="sxs-lookup"><span data-stu-id="e0983-159">Credit <em>VAT</em></span></span></td>
<td><span data-ttu-id="e0983-160">15.20</span><span class="sxs-lookup"><span data-stu-id="e0983-160">15.20</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="e0983-161">Płatność od odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e0983-161">Customer payment</span></span></td>
<td rowspan='2'><span data-ttu-id="e0983-162">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-162">January 10, 2020</span></span></td>
<td rowspan='2'><span data-ttu-id="e0983-163">119 USD</span><span class="sxs-lookup"><span data-stu-id="e0983-163">119 USD</span></span></td>
<td rowspan='2'><span data-ttu-id="e0983-164">107,10 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-164">107.10 EUR</span></span></td>
<td><span data-ttu-id="e0983-165">Debet <em>Bank</em></span><span class="sxs-lookup"><span data-stu-id="e0983-165">Debit <em>Bank</em></span></span></td>
<td><span data-ttu-id="e0983-166">107.10</span><span class="sxs-lookup"><span data-stu-id="e0983-166">107.10</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-167">Kredyt <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="e0983-167">Credit <em>AR</em></span></span></td>
<td><span data-ttu-id="e0983-168">107.10</span><span class="sxs-lookup"><span data-stu-id="e0983-168">107.10</span></span></td>
</tr>
<tr>
<td rowspan='3'><span data-ttu-id="e0983-169">Faktura i rozliczenie płatności</span><span class="sxs-lookup"><span data-stu-id="e0983-169">Invoice and payment settlement</span></span></td>
<td rowspan='3'><span data-ttu-id="e0983-170">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-170">January 10, 2020</span></span></td>
<td rowspan='3'><span data-ttu-id="e0983-171">0 USD</span><span class="sxs-lookup"><span data-stu-id="e0983-171">0 USD</span></span></td>
<td rowspan='3'><span data-ttu-id="e0983-172">11,90 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-172">11.90 EUR</span></span></td>
<td><span data-ttu-id="e0983-173">Debet <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="e0983-173">Debit <em>AR</em></span></span></td>
<td><span data-ttu-id="e0983-174">11.90</span><span class="sxs-lookup"><span data-stu-id="e0983-174">11.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-175">Kredyt <em>Różnica kursowa – konto główne</em></span><span class="sxs-lookup"><span data-stu-id="e0983-175">Credit <em>Exchange difference – main account</em></span></span></td>
<td><span data-ttu-id="e0983-176">10,00</span><span class="sxs-lookup"><span data-stu-id="e0983-176">10.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-177">Kredyt <em>Różnica kursowa – konto księgowania podatku</em></span><span class="sxs-lookup"><span data-stu-id="e0983-177">Credit <em>Exchange difference – tax posting account</em></span></span></td>
<td><span data-ttu-id="e0983-178">1.90</span><span class="sxs-lookup"><span data-stu-id="e0983-178">1.90</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0983-179">W tym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="e0983-179">In this example:</span></span>

- <span data-ttu-id="e0983-180">10.00 (= 11.90 × 80.00 ÷ 95.20) to różnica kursowa powiązana z wartością netto na fakturze.</span><span class="sxs-lookup"><span data-stu-id="e0983-180">10.00 (= 11.90 × 80.00 ÷ 95.20) is the exchange difference that is related to the net value of the invoice.</span></span>
- <span data-ttu-id="e0983-181">1.90 (= 11.90 – 10.00) to różnica kursowa powiązana z wartością podatku na fakturze.</span><span class="sxs-lookup"><span data-stu-id="e0983-181">1.90 (= 11.90 – 10.00) is the exchange difference that is related to the tax amount of the invoice.</span></span>

### <a name="example-2"></a><span data-ttu-id="e0983-182">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="e0983-182">Example 2</span></span>

<span data-ttu-id="e0983-183">Uzupełnij poniższe ustawienia, oprócz ustawień wykonanych dla przykładu 1.</span><span class="sxs-lookup"><span data-stu-id="e0983-183">Complete the following setup in addition to the setup that you completed for example 1.</span></span>

1. <span data-ttu-id="e0983-184">Na stronie **Księga** w polu **Kurs wymiany banku** wybierz opcję **Średnia**.</span><span class="sxs-lookup"><span data-stu-id="e0983-184">On the **Ledger** page, in the **Bank exchange rate** field, select **Average**.</span></span> <span data-ttu-id="e0983-185">Ten kurs będzie używany do obliczania kwot podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="e0983-185">This rate will be used to calculate VAT amounts.</span></span>
2. <span data-ttu-id="e0983-186">Umożliwia konfigurowanie kursów wymiany walut dla **Średniego** typu kursu wymiany, co przedstawiono w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="e0983-186">Set up the currency exchange rate for the **Average** exchange rate type, as shown in the following table.</span></span>

    | <span data-ttu-id="e0983-187">Data</span><span class="sxs-lookup"><span data-stu-id="e0983-187">Date</span></span>             | <span data-ttu-id="e0983-188">USD</span><span class="sxs-lookup"><span data-stu-id="e0983-188">USD</span></span> | <span data-ttu-id="e0983-189">EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-189">EUR</span></span> | <span data-ttu-id="e0983-190">opis</span><span class="sxs-lookup"><span data-stu-id="e0983-190">Description</span></span>         |
    |------------------|-----|-----|---------------------|
    | <span data-ttu-id="e0983-191">1 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-191">January 1, 2020</span></span>  | <span data-ttu-id="e0983-192">100</span><span class="sxs-lookup"><span data-stu-id="e0983-192">100</span></span> | <span data-ttu-id="e0983-193">100</span><span class="sxs-lookup"><span data-stu-id="e0983-193">100</span></span> | <span data-ttu-id="e0983-194">100 USD za 100 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-194">100 USD for 100 EUR</span></span> |
    | <span data-ttu-id="e0983-195">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-195">January 10, 2020</span></span> | <span data-ttu-id="e0983-196">100</span><span class="sxs-lookup"><span data-stu-id="e0983-196">100</span></span> | <span data-ttu-id="e0983-197">110</span><span class="sxs-lookup"><span data-stu-id="e0983-197">110</span></span> | <span data-ttu-id="e0983-198">100 USD za 110 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-198">100 USD for 110 EUR</span></span> |

<span data-ttu-id="e0983-199">Zaksięguj poniższe transakcje.</span><span class="sxs-lookup"><span data-stu-id="e0983-199">Post the following transactions.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0983-200">Wydruk pokwitowania</span><span class="sxs-lookup"><span data-stu-id="e0983-200">Document</span></span></th>
<th><span data-ttu-id="e0983-201">Data</span><span class="sxs-lookup"><span data-stu-id="e0983-201">Date</span></span></th>
<th><span data-ttu-id="e0983-202">Kwota w dolarach USD</span><span class="sxs-lookup"><span data-stu-id="e0983-202">Amount in USD</span></span></th>
<th><span data-ttu-id="e0983-203">Kwota w dolarach EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-203">Amount in EUR</span></span></th>
<th><span data-ttu-id="e0983-204">Załącznik</span><span class="sxs-lookup"><span data-stu-id="e0983-204">Voucher</span></span></th>
<th><span data-ttu-id="e0983-205">Kwota załącznika</span><span class="sxs-lookup"><span data-stu-id="e0983-205">Voucher amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='5'><span data-ttu-id="e0983-206">Faktura dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e0983-206">Customer invoice</span></span></td>
<td rowspan='5'><span data-ttu-id="e0983-207">1 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-207">January 1, 2020</span></span></td>
<td rowspan='5'><span data-ttu-id="e0983-208">119 USD, która zawiera kwotę podatku VAT 19 USD</span><span class="sxs-lookup"><span data-stu-id="e0983-208">119 USD, which includes a VAT amount of 19 USD</span></span></td>
<td rowspan='5'><span data-ttu-id="e0983-209">95.20 EUR, która zawiera kwotę podatku VAT 19.00 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-209">95.20 EUR, which includes a VAT amount of 19.00 EUR</span></span></td>
<td><span data-ttu-id="e0983-210">Debet <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="e0983-210">Debit <em>AR</em></span></span></td>
<td><span data-ttu-id="e0983-211">95.20</span><span class="sxs-lookup"><span data-stu-id="e0983-211">95.20</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-212">Kredyt <em>Wydatki</em></span><span class="sxs-lookup"><span data-stu-id="e0983-212">Credit <em>Expense</em></span></span></td>
<td><span data-ttu-id="e0983-213">80.00</span><span class="sxs-lookup"><span data-stu-id="e0983-213">80.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-214">Kredyt <em>VAT</em></span><span class="sxs-lookup"><span data-stu-id="e0983-214">Credit <em>VAT</em></span></span></td>
<td><span data-ttu-id="e0983-215">15.20</span><span class="sxs-lookup"><span data-stu-id="e0983-215">15.20</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-216">Debet <em>różnica podatki AR</em></span><span class="sxs-lookup"><span data-stu-id="e0983-216">Debit <em>AR tax difference</em></span></span></td>
<td><span data-ttu-id="e0983-217">3.80</span><span class="sxs-lookup"><span data-stu-id="e0983-217">3.80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-218">Kredyt <em>różnica podatku VAT</em></span><span class="sxs-lookup"><span data-stu-id="e0983-218">Credit <em>VAT tax difference</em></span></span></td>
<td><span data-ttu-id="e0983-219">3.80</span><span class="sxs-lookup"><span data-stu-id="e0983-219">3.80</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="e0983-220">Płatność od odbiorcy</span><span class="sxs-lookup"><span data-stu-id="e0983-220">Customer payment</span></span></td>
<td rowspan='2'><span data-ttu-id="e0983-221">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-221">January 10, 2020</span></span></td>
<td rowspan='2'><span data-ttu-id="e0983-222">119 USD</span><span class="sxs-lookup"><span data-stu-id="e0983-222">119 USD</span></span></td>
<td rowspan='2'><span data-ttu-id="e0983-223">107,10 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-223">107.10 EUR</span></span></td>
<td><span data-ttu-id="e0983-224">Debet <em>Bank</em></span><span class="sxs-lookup"><span data-stu-id="e0983-224">Debit <em>Bank</em></span></span></td>
<td><span data-ttu-id="e0983-225">107.10</span><span class="sxs-lookup"><span data-stu-id="e0983-225">107.10</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-226">Kredyt <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="e0983-226">Credit <em>AR</em></span></span></td>
<td><span data-ttu-id="e0983-227">107.10</span><span class="sxs-lookup"><span data-stu-id="e0983-227">107.10</span></span></td>
</tr>
<tr>
<td rowspan='3'><span data-ttu-id="e0983-228">Faktura i rozliczenie płatności</span><span class="sxs-lookup"><span data-stu-id="e0983-228">Invoice and payment settlement</span></span></td>
<td rowspan='3'><span data-ttu-id="e0983-229">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="e0983-229">January 10, 2020</span></span></td>
<td rowspan='3'><span data-ttu-id="e0983-230">0 USD</span><span class="sxs-lookup"><span data-stu-id="e0983-230">0 USD</span></span></td>
<td rowspan='3'><span data-ttu-id="e0983-231">11,90 EUR</span><span class="sxs-lookup"><span data-stu-id="e0983-231">11.90 EUR</span></span></td>
<td><span data-ttu-id="e0983-232">Debet <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="e0983-232">Debit <em>AR</em></span></span></td>
<td><span data-ttu-id="e0983-233">11.90</span><span class="sxs-lookup"><span data-stu-id="e0983-233">11.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-234">Kredyt <em>Różnica kursowa – konto główne</em></span><span class="sxs-lookup"><span data-stu-id="e0983-234">Credit <em>Exchange difference – main account</em></span></span></td>
<td><span data-ttu-id="e0983-235">10,00</span><span class="sxs-lookup"><span data-stu-id="e0983-235">10.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0983-236">Kredyt <em>Różnica kursowa – konto księgowania podatku</em></span><span class="sxs-lookup"><span data-stu-id="e0983-236">Credit <em>Exchange difference – tax posting account</em></span></span></td>
<td><span data-ttu-id="e0983-237">1.90</span><span class="sxs-lookup"><span data-stu-id="e0983-237">1.90</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0983-238">W tym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="e0983-238">In this example:</span></span>

- <span data-ttu-id="e0983-239">10.00 (= 11.90 × 80.00 ÷ 95.20) to różnica kursowa powiązana z wartością netto na fakturze.</span><span class="sxs-lookup"><span data-stu-id="e0983-239">10.00 (= 11.90 × 80.00 ÷ 95.20) is the exchange difference that is related to the net value of the invoice.</span></span>
- <span data-ttu-id="e0983-240">1.90 (= 11.90 – 10.00) to różnica kursowa powiązana z wartością podatku na fakturze.</span><span class="sxs-lookup"><span data-stu-id="e0983-240">1.90 (= 11.90 – 10.00) is the exchange difference that is related to the tax amount of the invoice.</span></span>
