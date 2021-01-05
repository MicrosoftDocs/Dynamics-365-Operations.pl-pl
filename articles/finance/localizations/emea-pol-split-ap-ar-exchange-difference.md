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
ms.author: roschlom
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-04-01
ms.openlocfilehash: 934fa7f933bfb0a1d069472f182f70c48cbf4fdf
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408388"
---
# <a name="split-the-realized-exchange-difference-amount-into-the-difference-of-the-invoice-net-value-and-the-vat-amount"></a><span data-ttu-id="dced6-103">Podziel zrealizowaną różnicę kursów kwoty na różnicę wartości netto faktury i kwoty VAT</span><span class="sxs-lookup"><span data-stu-id="dced6-103">Split the realized exchange difference amount into the difference of the invoice net value and the VAT amount</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dced6-104">Funkcja **Podziel zrealizowaną różnicę kursową AP/AR na różnicę między wartością netto faktury i kwotą VAT** pozwala podzielić kwotę rozrachunków z dostawcami (punkt dostępu) i Rozrachunki z odbiorcami (AR) przeszacowanie w walucie obcej na dwie części:</span><span class="sxs-lookup"><span data-stu-id="dced6-104">The **Split the AP/AR realized exchange difference amount into the difference of the invoice net value and the VAT amount** feature lets you split the amount of an Accounts payable (AP) and Accounts receivable (AR) foreign currency revaluation into two parts:</span></span>

- <span data-ttu-id="dced6-105">Różnica kursowa związana z wartością netto faktury (zadłużenie odbiorcy i zobowiązania dostawcy)</span><span class="sxs-lookup"><span data-stu-id="dced6-105">The exchange difference that is related to the net value of the invoice (customer debts and vendor liabilities)</span></span>
- <span data-ttu-id="dced6-106">Różnica kursowa powiązana z kwotą podatku VAT na fakturze</span><span class="sxs-lookup"><span data-stu-id="dced6-106">The exchange difference that is related to the value-added tax (VAT) amount of the invoice</span></span>

<span data-ttu-id="dced6-107">Można również zaksięgować różnice kursowe powiązane z kwotą faktury VAT na oddzielne konto księgowe zrealizowanych zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="dced6-107">You can also post the exchange differences that are related to the VAT invoice amount to a separate ledger account of realized gains and losses.</span></span>

<span data-ttu-id="dced6-108">Ta funkcja jest dostępna tylko w firmach z polskim kontekstem kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="dced6-108">This feature is available only in legal entities that have a Polish country/region context.</span></span>

## <a name="setup"></a><span data-ttu-id="dced6-109">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="dced6-109">Setup</span></span>

### <a name="activate-the-feature"></a><span data-ttu-id="dced6-110">Aktywowanie funkcji</span><span class="sxs-lookup"><span data-stu-id="dced6-110">Activate the feature</span></span>

<span data-ttu-id="dced6-111">W obszarze roboczym **Zarządzanie funkcjami** włącz następującą funkcję: **(Polska) Podziel zrealizowaną różnicę kursową AP/AR na różnicę między wartością netto faktury i kwotą VAT**.</span><span class="sxs-lookup"><span data-stu-id="dced6-111">In the **Feature management** workspace, turn on the following feature: **(Poland) Split the AP/AR realized exchange difference amount into the difference of the invoice net value and the VAT amount**.</span></span>

### <a name="set-up-ledger-accounts"></a><span data-ttu-id="dced6-112">Konfigurowanie kont księgi</span><span class="sxs-lookup"><span data-stu-id="dced6-112">Set up ledger accounts</span></span>

<span data-ttu-id="dced6-113">Wykonaj poniższe kroki, aby skonfigurować konto księgowe, za pomocą którego można księgować kwotę różnicy kursowej powiązaną z kwotą podatku na fakturze.</span><span class="sxs-lookup"><span data-stu-id="dced6-113">Follow these steps to set up a ledger account that can be used to post the exchange difference amount that is related to the tax amount of the invoice.</span></span>

1. <span data-ttu-id="dced6-114">Przejdź do **Księga główna** \> **Waluty** \> **Konta przeszacowania waluty**.</span><span class="sxs-lookup"><span data-stu-id="dced6-114">Go to **General ledger** \> **Currencies** \> **Currency revaluation accounts**.</span></span> 
2. <span data-ttu-id="dced6-115">Na stronie **Konta przeszacowania waluty** wybierz kod waluty, a następnie w polu **Księga** wybierz kod firmy.</span><span class="sxs-lookup"><span data-stu-id="dced6-115">On the **Currency revaluation accounts** page, select the currency code, and then, in the **Ledger** field, select the code of the legal entity.</span></span>

    ![Strona Konta przeszacowania waluty](media/Currency-revaluation-accounts.png)

2. <span data-ttu-id="dced6-117">Wybierz wiersz, w którym pole **Księgowanie** jest ustawione jako **Zrealizowana dodatnia różnica kursowa** lub **Zrealizowana ujemna różnica kursowa**.</span><span class="sxs-lookup"><span data-stu-id="dced6-117">Select a line where the **Posting** field is set to **Realized gain** or **Realized loss**.</span></span>
3. <span data-ttu-id="dced6-118">Skonfiguruj konto główne i wybierz konto księgowe, na które chcesz zaksięgować zrealizowaną różnicę kursową.</span><span class="sxs-lookup"><span data-stu-id="dced6-118">Set up the main account, and select the ledger account to post the realized exchange difference to.</span></span>
4. <span data-ttu-id="dced6-119">W polu **Podatki** wybierz opcję **Wydatek**, aby zaksięgować część kwoty zrealizowanej różnicy kursowej powiązaną z kwotą podatku faktury na osobne konto księgowe wydatków.</span><span class="sxs-lookup"><span data-stu-id="dced6-119">In the **Sales taxes** field, select **Expense** to post part of the realized exchange difference amount that is related to the tax amount of the invoice to a separate expense ledger account.</span></span> 
5. <span data-ttu-id="dced6-120">W polu **Konto księgowania podatku** wybierz to samo konto księgowe wydatków.</span><span class="sxs-lookup"><span data-stu-id="dced6-120">In the **Tax posting account** field, select the same expense ledger account.</span></span>

## <a name="post-and-settle-customer-and-vendor-transactions"></a><span data-ttu-id="dced6-121">Księgowanie i rozliczanie transakcji odbiorcy i dostawcy</span><span class="sxs-lookup"><span data-stu-id="dced6-121">Post and settle customer and vendor transactions</span></span>

<span data-ttu-id="dced6-122">Umożliwia księgowanie i rozliczanie dokumentów w zwykły sposób.</span><span class="sxs-lookup"><span data-stu-id="dced6-122">Post and settle documents in the usual way.</span></span> <span data-ttu-id="dced6-123">Transakcja różnic kursowych tworzona podczas rozliczania spowoduje wygenerowanie załącznika, w którym kwota różnicy kursowej powiązana z kwotą podatku jest księgowana oddzielnie na koncie księgowym wybranym w polu **Konto księgowania podatku** na stronie **Konta przeszacowania waluty**.</span><span class="sxs-lookup"><span data-stu-id="dced6-123">The exchange difference transaction that is created during settlement will generate a voucher, where the exchange difference amount that is related to the tax amount is posted separately to the ledger account that you selected in the **Tax posting account** field on the **Currency revaluation accounts** page.</span></span>

## <a name="examples"></a><span data-ttu-id="dced6-124">Przykłady</span><span class="sxs-lookup"><span data-stu-id="dced6-124">Examples</span></span>

<span data-ttu-id="dced6-125">W poniższych dwóch przykładach są wyświetlane wynikowe transakcje finansowe.</span><span class="sxs-lookup"><span data-stu-id="dced6-125">The following two examples show the resulting ledger transactions.</span></span>

### <a name="example-1"></a><span data-ttu-id="dced6-126">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="dced6-126">Example 1</span></span>

<span data-ttu-id="dced6-127">Wykonaj następujące czynności konfiguracyjne w firmie **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="dced6-127">Complete the following setup in the **DEMF** legal entity.</span></span>

1. <span data-ttu-id="dced6-128">Zmień kraj/region na **POL**.</span><span class="sxs-lookup"><span data-stu-id="dced6-128">Change the country/region to **POL**.</span></span>
2. <span data-ttu-id="dced6-129">Na stronie **Księga** sprawdź, czy w polu **Waluta rozliczeniowa** określono wartość **EUR**.</span><span class="sxs-lookup"><span data-stu-id="dced6-129">On the **Ledger** page, verify that the **Accounting currency** field is set to **EUR**.</span></span>
3. <span data-ttu-id="dced6-130">Umożliwia konfigurowanie kursów wymiany walut dla **Domyślnego** typu kursu wymiany, co przedstawiono w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dced6-130">Set up currency exchange rates for the **Default** exchange rate type, as shown in the following table.</span></span>

    | <span data-ttu-id="dced6-131">Data</span><span class="sxs-lookup"><span data-stu-id="dced6-131">Date</span></span>             | <span data-ttu-id="dced6-132">Dolary amerykańskie (USD)</span><span class="sxs-lookup"><span data-stu-id="dced6-132">US dollars (USD)</span></span> | <span data-ttu-id="dced6-133">Euro (EUR)</span><span class="sxs-lookup"><span data-stu-id="dced6-133">Euros (EUR)</span></span> | <span data-ttu-id="dced6-134">opis</span><span class="sxs-lookup"><span data-stu-id="dced6-134">Description</span></span>        |
    |------------------|------------------|-------------|--------------------|
    | <span data-ttu-id="dced6-135">1 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-135">January 1, 2020</span></span>  | <span data-ttu-id="dced6-136">100</span><span class="sxs-lookup"><span data-stu-id="dced6-136">100</span></span>              | <span data-ttu-id="dced6-137">80</span><span class="sxs-lookup"><span data-stu-id="dced6-137">80</span></span>          | <span data-ttu-id="dced6-138">100 USD za 80 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-138">100 USD for 80 EUR</span></span> |
    | <span data-ttu-id="dced6-139">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-139">January 10, 2020</span></span> | <span data-ttu-id="dced6-140">100</span><span class="sxs-lookup"><span data-stu-id="dced6-140">100</span></span>              | <span data-ttu-id="dced6-141">90</span><span class="sxs-lookup"><span data-stu-id="dced6-141">90</span></span>          | <span data-ttu-id="dced6-142">100 USD za 90 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-142">100 USD for 90 EUR</span></span> |

4. <span data-ttu-id="dced6-143">Skonfiguruj konta księgo dla zrealizowanej różnicy kursowej na kocnie głównym i koncie księgowania podatku.</span><span class="sxs-lookup"><span data-stu-id="dced6-143">Set up ledger accounts for the realized exchange difference in the main account and the tax posting account.</span></span>

<span data-ttu-id="dced6-144">Zaksięguj poniższe transakcje.</span><span class="sxs-lookup"><span data-stu-id="dced6-144">Post the following transactions.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dced6-145">Wydruk pokwitowania</span><span class="sxs-lookup"><span data-stu-id="dced6-145">Document</span></span></th>
<th><span data-ttu-id="dced6-146">Data</span><span class="sxs-lookup"><span data-stu-id="dced6-146">Date</span></span></th>
<th><span data-ttu-id="dced6-147">Kwota w dolarach USD</span><span class="sxs-lookup"><span data-stu-id="dced6-147">Amount in USD</span></span></th>
<th><span data-ttu-id="dced6-148">Kwota w dolarach EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-148">Amount in EUR</span></span></th>
<th><span data-ttu-id="dced6-149">Załącznik</span><span class="sxs-lookup"><span data-stu-id="dced6-149">Voucher</span></span></th>
<th><span data-ttu-id="dced6-150">Kwota załącznika</span><span class="sxs-lookup"><span data-stu-id="dced6-150">Voucher amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='3'><span data-ttu-id="dced6-151">Faktura dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="dced6-151">Customer invoice</span></span></td>
<td rowspan='3'><span data-ttu-id="dced6-152">1 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-152">January 1, 2020</span></span></td>
<td rowspan='3'><span data-ttu-id="dced6-153">119 USD, która zawiera kwotę podatku VAT 19 USD</span><span class="sxs-lookup"><span data-stu-id="dced6-153">119 USD, which includes a VAT amount of 19 USD</span></span></td>
<td rowspan='3'><span data-ttu-id="dced6-154">95.20 EUR, która zawiera kwotę podatku VAT 15.20 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-154">95.20 EUR, which includes a VAT amount of 15.20 EUR</span></span></td>
<td><span data-ttu-id="dced6-155">Debet <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="dced6-155">Debit <em>AR</em></span></span></td>
<td><span data-ttu-id="dced6-156">95.20</span><span class="sxs-lookup"><span data-stu-id="dced6-156">95.20</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-157">Kredyt <em>Wydatki</em></span><span class="sxs-lookup"><span data-stu-id="dced6-157">Credit <em>Expense</em></span></span></td>
<td><span data-ttu-id="dced6-158">80.00</span><span class="sxs-lookup"><span data-stu-id="dced6-158">80.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-159">Kredyt <em>VAT</em></span><span class="sxs-lookup"><span data-stu-id="dced6-159">Credit <em>VAT</em></span></span></td>
<td><span data-ttu-id="dced6-160">15.20</span><span class="sxs-lookup"><span data-stu-id="dced6-160">15.20</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="dced6-161">Płatność od odbiorcy</span><span class="sxs-lookup"><span data-stu-id="dced6-161">Customer payment</span></span></td>
<td rowspan='2'><span data-ttu-id="dced6-162">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-162">January 10, 2020</span></span></td>
<td rowspan='2'><span data-ttu-id="dced6-163">119 USD</span><span class="sxs-lookup"><span data-stu-id="dced6-163">119 USD</span></span></td>
<td rowspan='2'><span data-ttu-id="dced6-164">107,10 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-164">107.10 EUR</span></span></td>
<td><span data-ttu-id="dced6-165">Debet <em>Bank</em></span><span class="sxs-lookup"><span data-stu-id="dced6-165">Debit <em>Bank</em></span></span></td>
<td><span data-ttu-id="dced6-166">107.10</span><span class="sxs-lookup"><span data-stu-id="dced6-166">107.10</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-167">Kredyt <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="dced6-167">Credit <em>AR</em></span></span></td>
<td><span data-ttu-id="dced6-168">107.10</span><span class="sxs-lookup"><span data-stu-id="dced6-168">107.10</span></span></td>
</tr>
<tr>
<td rowspan='3'><span data-ttu-id="dced6-169">Faktura i rozliczenie płatności</span><span class="sxs-lookup"><span data-stu-id="dced6-169">Invoice and payment settlement</span></span></td>
<td rowspan='3'><span data-ttu-id="dced6-170">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-170">January 10, 2020</span></span></td>
<td rowspan='3'><span data-ttu-id="dced6-171">0 USD</span><span class="sxs-lookup"><span data-stu-id="dced6-171">0 USD</span></span></td>
<td rowspan='3'><span data-ttu-id="dced6-172">11,90 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-172">11.90 EUR</span></span></td>
<td><span data-ttu-id="dced6-173">Debet <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="dced6-173">Debit <em>AR</em></span></span></td>
<td><span data-ttu-id="dced6-174">11.90</span><span class="sxs-lookup"><span data-stu-id="dced6-174">11.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-175">Kredyt <em>Różnica kursowa – konto główne</em></span><span class="sxs-lookup"><span data-stu-id="dced6-175">Credit <em>Exchange difference – main account</em></span></span></td>
<td><span data-ttu-id="dced6-176">10,00</span><span class="sxs-lookup"><span data-stu-id="dced6-176">10.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-177">Kredyt <em>Różnica kursowa – konto księgowania podatku</em></span><span class="sxs-lookup"><span data-stu-id="dced6-177">Credit <em>Exchange difference – tax posting account</em></span></span></td>
<td><span data-ttu-id="dced6-178">1.90</span><span class="sxs-lookup"><span data-stu-id="dced6-178">1.90</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dced6-179">W tym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="dced6-179">In this example:</span></span>

- <span data-ttu-id="dced6-180">10.00 (= 11.90 × 80.00 ÷ 95.20) to różnica kursowa powiązana z wartością netto na fakturze.</span><span class="sxs-lookup"><span data-stu-id="dced6-180">10.00 (= 11.90 × 80.00 ÷ 95.20) is the exchange difference that is related to the net value of the invoice.</span></span>
- <span data-ttu-id="dced6-181">1.90 (= 11.90 – 10.00) to różnica kursowa powiązana z wartością podatku na fakturze.</span><span class="sxs-lookup"><span data-stu-id="dced6-181">1.90 (= 11.90 – 10.00) is the exchange difference that is related to the tax amount of the invoice.</span></span>

### <a name="example-2"></a><span data-ttu-id="dced6-182">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="dced6-182">Example 2</span></span>

<span data-ttu-id="dced6-183">Uzupełnij poniższe ustawienia, oprócz ustawień wykonanych dla przykładu 1.</span><span class="sxs-lookup"><span data-stu-id="dced6-183">Complete the following setup in addition to the setup that you completed for example 1.</span></span>

1. <span data-ttu-id="dced6-184">Na stronie **Księga** w polu **Kurs wymiany banku** wybierz opcję **Średnia**.</span><span class="sxs-lookup"><span data-stu-id="dced6-184">On the **Ledger** page, in the **Bank exchange rate** field, select **Average**.</span></span> <span data-ttu-id="dced6-185">Ten kurs będzie używany do obliczania kwot podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="dced6-185">This rate will be used to calculate VAT amounts.</span></span>
2. <span data-ttu-id="dced6-186">Umożliwia konfigurowanie kursów wymiany walut dla **Średniego** typu kursu wymiany, co przedstawiono w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dced6-186">Set up the currency exchange rate for the **Average** exchange rate type, as shown in the following table.</span></span>

    | <span data-ttu-id="dced6-187">Data</span><span class="sxs-lookup"><span data-stu-id="dced6-187">Date</span></span>             | <span data-ttu-id="dced6-188">USD</span><span class="sxs-lookup"><span data-stu-id="dced6-188">USD</span></span> | <span data-ttu-id="dced6-189">EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-189">EUR</span></span> | <span data-ttu-id="dced6-190">opis</span><span class="sxs-lookup"><span data-stu-id="dced6-190">Description</span></span>         |
    |------------------|-----|-----|---------------------|
    | <span data-ttu-id="dced6-191">1 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-191">January 1, 2020</span></span>  | <span data-ttu-id="dced6-192">100</span><span class="sxs-lookup"><span data-stu-id="dced6-192">100</span></span> | <span data-ttu-id="dced6-193">100</span><span class="sxs-lookup"><span data-stu-id="dced6-193">100</span></span> | <span data-ttu-id="dced6-194">100 USD za 100 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-194">100 USD for 100 EUR</span></span> |
    | <span data-ttu-id="dced6-195">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-195">January 10, 2020</span></span> | <span data-ttu-id="dced6-196">100</span><span class="sxs-lookup"><span data-stu-id="dced6-196">100</span></span> | <span data-ttu-id="dced6-197">110</span><span class="sxs-lookup"><span data-stu-id="dced6-197">110</span></span> | <span data-ttu-id="dced6-198">100 USD za 110 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-198">100 USD for 110 EUR</span></span> |

<span data-ttu-id="dced6-199">Zaksięguj poniższe transakcje.</span><span class="sxs-lookup"><span data-stu-id="dced6-199">Post the following transactions.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dced6-200">Wydruk pokwitowania</span><span class="sxs-lookup"><span data-stu-id="dced6-200">Document</span></span></th>
<th><span data-ttu-id="dced6-201">Data</span><span class="sxs-lookup"><span data-stu-id="dced6-201">Date</span></span></th>
<th><span data-ttu-id="dced6-202">Kwota w dolarach USD</span><span class="sxs-lookup"><span data-stu-id="dced6-202">Amount in USD</span></span></th>
<th><span data-ttu-id="dced6-203">Kwota w dolarach EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-203">Amount in EUR</span></span></th>
<th><span data-ttu-id="dced6-204">Załącznik</span><span class="sxs-lookup"><span data-stu-id="dced6-204">Voucher</span></span></th>
<th><span data-ttu-id="dced6-205">Kwota załącznika</span><span class="sxs-lookup"><span data-stu-id="dced6-205">Voucher amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='5'><span data-ttu-id="dced6-206">Faktura dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="dced6-206">Customer invoice</span></span></td>
<td rowspan='5'><span data-ttu-id="dced6-207">1 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-207">January 1, 2020</span></span></td>
<td rowspan='5'><span data-ttu-id="dced6-208">119 USD, która zawiera kwotę podatku VAT 19 USD</span><span class="sxs-lookup"><span data-stu-id="dced6-208">119 USD, which includes a VAT amount of 19 USD</span></span></td>
<td rowspan='5'><span data-ttu-id="dced6-209">95.20 EUR, która zawiera kwotę podatku VAT 19.00 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-209">95.20 EUR, which includes a VAT amount of 19.00 EUR</span></span></td>
<td><span data-ttu-id="dced6-210">Debet <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="dced6-210">Debit <em>AR</em></span></span></td>
<td><span data-ttu-id="dced6-211">95.20</span><span class="sxs-lookup"><span data-stu-id="dced6-211">95.20</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-212">Kredyt <em>Wydatki</em></span><span class="sxs-lookup"><span data-stu-id="dced6-212">Credit <em>Expense</em></span></span></td>
<td><span data-ttu-id="dced6-213">80.00</span><span class="sxs-lookup"><span data-stu-id="dced6-213">80.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-214">Kredyt <em>VAT</em></span><span class="sxs-lookup"><span data-stu-id="dced6-214">Credit <em>VAT</em></span></span></td>
<td><span data-ttu-id="dced6-215">15.20</span><span class="sxs-lookup"><span data-stu-id="dced6-215">15.20</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-216">Debet <em>różnica podatki AR</em></span><span class="sxs-lookup"><span data-stu-id="dced6-216">Debit <em>AR tax difference</em></span></span></td>
<td><span data-ttu-id="dced6-217">3.80</span><span class="sxs-lookup"><span data-stu-id="dced6-217">3.80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-218">Kredyt <em>różnica podatku VAT</em></span><span class="sxs-lookup"><span data-stu-id="dced6-218">Credit <em>VAT tax difference</em></span></span></td>
<td><span data-ttu-id="dced6-219">3.80</span><span class="sxs-lookup"><span data-stu-id="dced6-219">3.80</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="dced6-220">Płatność od odbiorcy</span><span class="sxs-lookup"><span data-stu-id="dced6-220">Customer payment</span></span></td>
<td rowspan='2'><span data-ttu-id="dced6-221">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-221">January 10, 2020</span></span></td>
<td rowspan='2'><span data-ttu-id="dced6-222">119 USD</span><span class="sxs-lookup"><span data-stu-id="dced6-222">119 USD</span></span></td>
<td rowspan='2'><span data-ttu-id="dced6-223">107,10 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-223">107.10 EUR</span></span></td>
<td><span data-ttu-id="dced6-224">Debet <em>Bank</em></span><span class="sxs-lookup"><span data-stu-id="dced6-224">Debit <em>Bank</em></span></span></td>
<td><span data-ttu-id="dced6-225">107.10</span><span class="sxs-lookup"><span data-stu-id="dced6-225">107.10</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-226">Kredyt <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="dced6-226">Credit <em>AR</em></span></span></td>
<td><span data-ttu-id="dced6-227">107.10</span><span class="sxs-lookup"><span data-stu-id="dced6-227">107.10</span></span></td>
</tr>
<tr>
<td rowspan='3'><span data-ttu-id="dced6-228">Faktura i rozliczenie płatności</span><span class="sxs-lookup"><span data-stu-id="dced6-228">Invoice and payment settlement</span></span></td>
<td rowspan='3'><span data-ttu-id="dced6-229">10 stycznia 2020 r.</span><span class="sxs-lookup"><span data-stu-id="dced6-229">January 10, 2020</span></span></td>
<td rowspan='3'><span data-ttu-id="dced6-230">0 USD</span><span class="sxs-lookup"><span data-stu-id="dced6-230">0 USD</span></span></td>
<td rowspan='3'><span data-ttu-id="dced6-231">11,90 EUR</span><span class="sxs-lookup"><span data-stu-id="dced6-231">11.90 EUR</span></span></td>
<td><span data-ttu-id="dced6-232">Debet <em>AR</em></span><span class="sxs-lookup"><span data-stu-id="dced6-232">Debit <em>AR</em></span></span></td>
<td><span data-ttu-id="dced6-233">11.90</span><span class="sxs-lookup"><span data-stu-id="dced6-233">11.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-234">Kredyt <em>Różnica kursowa – konto główne</em></span><span class="sxs-lookup"><span data-stu-id="dced6-234">Credit <em>Exchange difference – main account</em></span></span></td>
<td><span data-ttu-id="dced6-235">10,00</span><span class="sxs-lookup"><span data-stu-id="dced6-235">10.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dced6-236">Kredyt <em>Różnica kursowa – konto księgowania podatku</em></span><span class="sxs-lookup"><span data-stu-id="dced6-236">Credit <em>Exchange difference – tax posting account</em></span></span></td>
<td><span data-ttu-id="dced6-237">1.90</span><span class="sxs-lookup"><span data-stu-id="dced6-237">1.90</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dced6-238">W tym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="dced6-238">In this example:</span></span>

- <span data-ttu-id="dced6-239">10.00 (= 11.90 × 80.00 ÷ 95.20) to różnica kursowa powiązana z wartością netto na fakturze.</span><span class="sxs-lookup"><span data-stu-id="dced6-239">10.00 (= 11.90 × 80.00 ÷ 95.20) is the exchange difference that is related to the net value of the invoice.</span></span>
- <span data-ttu-id="dced6-240">1.90 (= 11.90 – 10.00) to różnica kursowa powiązana z wartością podatku na fakturze.</span><span class="sxs-lookup"><span data-stu-id="dced6-240">1.90 (= 11.90 – 10.00) is the exchange difference that is related to the tax amount of the invoice.</span></span>
