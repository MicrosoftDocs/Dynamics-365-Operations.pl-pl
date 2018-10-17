---
title: Przeszacowanie waluty w konsolidowanej firmie
description: "W tym temacie opisano sposób przeszacowania waluty w konsolidowanej firmie."
author: ShylaThompson
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ad0083018d2734cb1e36cbf5f94105376c57cdf9
ms.openlocfilehash: 76290564037ab6f5c7a1cd4508a819bd603e8148
ms.contentlocale: pl-pl
ms.lasthandoff: 10/02/2018

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="279e0-103">Przeszacowanie waluty w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="279e0-103">Currency revaluation in a consolidation company</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="279e0-104">Podczas konsolidowania danych z jednej waluty rozliczeniowej do innej należy wykonać przeszacowanie waluty, jeśli nastąpiła zmiana kursów wymiany, tak aby salda kont zostały poprawnie przeszacowane.</span><span class="sxs-lookup"><span data-stu-id="279e0-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="279e0-105">Podczas pierwszej konsolidacji danych użyj karty **przeliczania waluty**, aby wybrać początkowe kursy wymiany do przeszacowania podczas procesu konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="279e0-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="279e0-106">Po wprowadzeniu nowego kursu wymiany (na przykład w kolejnym miesiącu) można przeszacować salda konta.</span><span class="sxs-lookup"><span data-stu-id="279e0-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="279e0-107">Niezrealizowane dodatnie różnice kursowe zostaną odpowiednio zaktualizowane na podstawie nowego kursu wymiany i daty.</span><span class="sxs-lookup"><span data-stu-id="279e0-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="279e0-108">Poniższy przykład ilustruje zapisy księgowe utworzone podczas tego procesu.</span><span class="sxs-lookup"><span data-stu-id="279e0-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="279e0-109">Konfiguracja firmy</span><span class="sxs-lookup"><span data-stu-id="279e0-109">Company setup</span></span>
-   <span data-ttu-id="279e0-110">**Źródło/ firma (USMF)** — jako waluta raportowania i księgowania używane są dolary amerykańskie (USD).</span><span class="sxs-lookup"><span data-stu-id="279e0-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="279e0-111">**Konsolidowana firma (CON)** — jako waluta raportowania i księgowania używane jest euro (EUR).</span><span class="sxs-lookup"><span data-stu-id="279e0-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="279e0-112">**Zrealizowana dodatnia różnica kursowa** — konto księgowe 801500</span><span class="sxs-lookup"><span data-stu-id="279e0-112">**Realized gain**– Ledger account 801500</span></span>
    -   <span data-ttu-id="279e0-113">**Zrealizowana ujemna różnica kursowa** — konto księgowe 801600</span><span class="sxs-lookup"><span data-stu-id="279e0-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="279e0-114">**Niezrealizowana dodatnia różnica kursowa**— konto księgowe 801600</span><span class="sxs-lookup"><span data-stu-id="279e0-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="279e0-115">**Niezrealizowana ujemna różnica kursowa**— konto księgowe 801400</span><span class="sxs-lookup"><span data-stu-id="279e0-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="279e0-116">Oryginalne transakcje</span><span class="sxs-lookup"><span data-stu-id="279e0-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="279e0-117">Transakcje za pomocą blankietów kasowych w USMF</span><span class="sxs-lookup"><span data-stu-id="279e0-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="279e0-118">Data</span><span class="sxs-lookup"><span data-stu-id="279e0-118">Date</span></span>       | <span data-ttu-id="279e0-119">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="279e0-119">Ledger account</span></span>               | <span data-ttu-id="279e0-120">Waluta</span><span class="sxs-lookup"><span data-stu-id="279e0-120">Currency</span></span> | <span data-ttu-id="279e0-121">Kwota</span><span class="sxs-lookup"><span data-stu-id="279e0-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="279e0-122">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="279e0-122">10/11/2015</span></span> | <span data-ttu-id="279e0-123">110110 – Kasa</span><span class="sxs-lookup"><span data-stu-id="279e0-123">110110 – Cash</span></span>                | <span data-ttu-id="279e0-124">USD</span><span class="sxs-lookup"><span data-stu-id="279e0-124">USD</span></span>      | <span data-ttu-id="279e0-125">500</span><span class="sxs-lookup"><span data-stu-id="279e0-125">500</span></span>    |
| <span data-ttu-id="279e0-126">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="279e0-126">10/11/2015</span></span> | <span data-ttu-id="279e0-127">130100 – Rozrachunki z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="279e0-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="279e0-128">USD</span><span class="sxs-lookup"><span data-stu-id="279e0-128">USD</span></span>      | <span data-ttu-id="279e0-129">-500</span><span class="sxs-lookup"><span data-stu-id="279e0-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="279e0-130">Kursy wymiany</span><span class="sxs-lookup"><span data-stu-id="279e0-130">Exchange rates</span></span>

| <span data-ttu-id="279e0-131">Z waluty</span><span class="sxs-lookup"><span data-stu-id="279e0-131">From currency</span></span> | <span data-ttu-id="279e0-132">Na walutę</span><span class="sxs-lookup"><span data-stu-id="279e0-132">To currency</span></span> | <span data-ttu-id="279e0-133">Data początkowa</span><span class="sxs-lookup"><span data-stu-id="279e0-133">Start date</span></span> | <span data-ttu-id="279e0-134">Kurs wymiany</span><span class="sxs-lookup"><span data-stu-id="279e0-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="279e0-135">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-135">EUR</span></span>           | <span data-ttu-id="279e0-136">USD</span><span class="sxs-lookup"><span data-stu-id="279e0-136">USD</span></span>         | <span data-ttu-id="279e0-137">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="279e0-137">10/1/2015</span></span>  | <span data-ttu-id="279e0-138">200</span><span class="sxs-lookup"><span data-stu-id="279e0-138">200</span></span>           |
| <span data-ttu-id="279e0-139">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-139">EUR</span></span>           | <span data-ttu-id="279e0-140">USD</span><span class="sxs-lookup"><span data-stu-id="279e0-140">USD</span></span>         | <span data-ttu-id="279e0-141">11/1/2015</span><span class="sxs-lookup"><span data-stu-id="279e0-141">11/1/2015</span></span>  | <span data-ttu-id="279e0-142">150</span><span class="sxs-lookup"><span data-stu-id="279e0-142">150</span></span>           |
| <span data-ttu-id="279e0-143">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-143">EUR</span></span>           | <span data-ttu-id="279e0-144">USD</span><span class="sxs-lookup"><span data-stu-id="279e0-144">USD</span></span>         | <span data-ttu-id="279e0-145">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="279e0-145">12/1/2012</span></span>  | <span data-ttu-id="279e0-146">100</span><span class="sxs-lookup"><span data-stu-id="279e0-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="279e0-147">Wykonywanie konsolidacji dla października 2015</span><span class="sxs-lookup"><span data-stu-id="279e0-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="279e0-148">Salda w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="279e0-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="279e0-149">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="279e0-149">Ledger account</span></span> | <span data-ttu-id="279e0-150">Waluta</span><span class="sxs-lookup"><span data-stu-id="279e0-150">Currency</span></span> | <span data-ttu-id="279e0-151">Kwota</span><span class="sxs-lookup"><span data-stu-id="279e0-151">Amount</span></span> | <span data-ttu-id="279e0-152">Obliczanie</span><span class="sxs-lookup"><span data-stu-id="279e0-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="279e0-153">110110</span><span class="sxs-lookup"><span data-stu-id="279e0-153">110110</span></span>         | <span data-ttu-id="279e0-154">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-154">EUR</span></span>      | <span data-ttu-id="279e0-155">250</span><span class="sxs-lookup"><span data-stu-id="279e0-155">250</span></span>    | <span data-ttu-id="279e0-156">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="279e0-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="279e0-157">130100</span><span class="sxs-lookup"><span data-stu-id="279e0-157">130100</span></span>         | <span data-ttu-id="279e0-158">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-158">EUR</span></span>      | <span data-ttu-id="279e0-159">-250</span><span class="sxs-lookup"><span data-stu-id="279e0-159">-250</span></span>   | <span data-ttu-id="279e0-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="279e0-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="279e0-161">Wykonaj przeszacowanie w walucie dla kont od 1 października 2015 do 30 listopada 2015 roku.</span><span class="sxs-lookup"><span data-stu-id="279e0-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="279e0-162">Salda w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="279e0-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="279e0-163">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="279e0-163">Ledger account</span></span> | <span data-ttu-id="279e0-164">Waluta</span><span class="sxs-lookup"><span data-stu-id="279e0-164">Currency</span></span> | <span data-ttu-id="279e0-165">Kwota</span><span class="sxs-lookup"><span data-stu-id="279e0-165">Amount</span></span>  | <span data-ttu-id="279e0-166">Obliczanie</span><span class="sxs-lookup"><span data-stu-id="279e0-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="279e0-167">110110</span><span class="sxs-lookup"><span data-stu-id="279e0-167">110110</span></span>         | <span data-ttu-id="279e0-168">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-168">EUR</span></span>      | <span data-ttu-id="279e0-169">333.33</span><span class="sxs-lookup"><span data-stu-id="279e0-169">333.33</span></span>  | <span data-ttu-id="279e0-170">Pierwotna kwota 500 × 66.6667%</span><span class="sxs-lookup"><span data-stu-id="279e0-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="279e0-171">130100</span><span class="sxs-lookup"><span data-stu-id="279e0-171">130100</span></span>         | <span data-ttu-id="279e0-172">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-172">EUR</span></span>      | <span data-ttu-id="279e0-173">-333.33</span><span class="sxs-lookup"><span data-stu-id="279e0-173">-333.33</span></span> | <span data-ttu-id="279e0-174">Pierwotna kwota -500 × 66.6667%</span><span class="sxs-lookup"><span data-stu-id="279e0-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="279e0-175">801400</span><span class="sxs-lookup"><span data-stu-id="279e0-175">801400</span></span>         | <span data-ttu-id="279e0-176">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-176">EUR</span></span>      | <span data-ttu-id="279e0-177">83.33</span><span class="sxs-lookup"><span data-stu-id="279e0-177">83.33</span></span>   | <span data-ttu-id="279e0-178">333.33 – 250</span><span class="sxs-lookup"><span data-stu-id="279e0-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="279e0-179">801600</span><span class="sxs-lookup"><span data-stu-id="279e0-179">801600</span></span>         | <span data-ttu-id="279e0-180">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-180">EUR</span></span>      | <span data-ttu-id="279e0-181">-83.33</span><span class="sxs-lookup"><span data-stu-id="279e0-181">-83.33</span></span>  | <span data-ttu-id="279e0-182">-333.33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="279e0-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="279e0-183">Zobaczysz dodatkowe transakcje dla kwot w walucie raportowania.</span><span class="sxs-lookup"><span data-stu-id="279e0-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="279e0-184">Wykonaj przeszacowanie w walucie dla kont od 1 października 2015 do 31 grudnia 2015 roku.</span><span class="sxs-lookup"><span data-stu-id="279e0-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="279e0-185">Salda w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="279e0-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="279e0-186">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="279e0-186">Ledger account</span></span> | <span data-ttu-id="279e0-187">Waluta</span><span class="sxs-lookup"><span data-stu-id="279e0-187">Currency</span></span> | <span data-ttu-id="279e0-188">Kwota</span><span class="sxs-lookup"><span data-stu-id="279e0-188">Amount</span></span>  | <span data-ttu-id="279e0-189">Obliczanie</span><span class="sxs-lookup"><span data-stu-id="279e0-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="279e0-190">110110</span><span class="sxs-lookup"><span data-stu-id="279e0-190">110110</span></span>         | <span data-ttu-id="279e0-191">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-191">EUR</span></span>      | <span data-ttu-id="279e0-192">500,00</span><span class="sxs-lookup"><span data-stu-id="279e0-192">500.00</span></span>  | <span data-ttu-id="279e0-193">Pierwotna kwota 500 × 1</span><span class="sxs-lookup"><span data-stu-id="279e0-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="279e0-194">130100</span><span class="sxs-lookup"><span data-stu-id="279e0-194">130100</span></span>         | <span data-ttu-id="279e0-195">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-195">EUR</span></span>      | <span data-ttu-id="279e0-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="279e0-196">-500.00</span></span> | <span data-ttu-id="279e0-197">Pierwotna kwota -500 × 1%</span><span class="sxs-lookup"><span data-stu-id="279e0-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="279e0-198">801400</span><span class="sxs-lookup"><span data-stu-id="279e0-198">801400</span></span>         | <span data-ttu-id="279e0-199">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-199">EUR</span></span>      | <span data-ttu-id="279e0-200">250</span><span class="sxs-lookup"><span data-stu-id="279e0-200">250</span></span>     | <span data-ttu-id="279e0-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span><span class="sxs-lookup"><span data-stu-id="279e0-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="279e0-202">801600</span><span class="sxs-lookup"><span data-stu-id="279e0-202">801600</span></span>         | <span data-ttu-id="279e0-203">EUR</span><span class="sxs-lookup"><span data-stu-id="279e0-203">EUR</span></span>      | <span data-ttu-id="279e0-204">-250</span><span class="sxs-lookup"><span data-stu-id="279e0-204">-250</span></span>    | <span data-ttu-id="279e0-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span><span class="sxs-lookup"><span data-stu-id="279e0-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






