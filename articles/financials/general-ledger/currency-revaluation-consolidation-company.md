---
title: Przeszacowanie waluty w konsolidowanej firmie
description: "W tym temacie opisano sposób przeszacowania waluty w konsolidowanej firmie."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 06490f14ed01c3061b20a0e6977746e9fd2a6ffa
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="54e77-103">Przeszacowanie waluty w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="54e77-103">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="54e77-104">Podczas konsolidowania danych z jednej waluty rozliczeniowej do innej należy wykonać przeszacowanie waluty, jeśli nastąpiła zmiana kursów wymiany, tak aby salda kont zostały poprawnie przeszacowane.</span><span class="sxs-lookup"><span data-stu-id="54e77-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="54e77-105">Podczas pierwszej konsolidacji danych użyj karty **przeliczania waluty**, aby wybrać początkowe kursy wymiany do przeszacowania podczas procesu konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="54e77-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="54e77-106">Po wprowadzeniu nowego kursu wymiany (na przykład w kolejnym miesiącu) można przeszacować salda konta.</span><span class="sxs-lookup"><span data-stu-id="54e77-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="54e77-107">Niezrealizowane dodatnie różnice kursowe zostaną odpowiednio zaktualizowane na podstawie nowego kursu wymiany i daty.</span><span class="sxs-lookup"><span data-stu-id="54e77-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="54e77-108">Poniższy przykład ilustruje zapisy księgowe utworzone podczas tego procesu.</span><span class="sxs-lookup"><span data-stu-id="54e77-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="54e77-109">Konfiguracja firmy</span><span class="sxs-lookup"><span data-stu-id="54e77-109">Company setup</span></span>
-   <span data-ttu-id="54e77-110">**Źródło/ firma (USMF)** — jako waluta raportowania i księgowania używane są dolary amerykańskie (USD).</span><span class="sxs-lookup"><span data-stu-id="54e77-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="54e77-111">**Konsolidowana firma (CON)** — jako waluta raportowania i księgowania używane jest euro (EUR).</span><span class="sxs-lookup"><span data-stu-id="54e77-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="54e77-112">**Zrealizowana dodatnia różnica kursowa** — konto księgowe 801500</span><span class="sxs-lookup"><span data-stu-id="54e77-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="54e77-113">**Zrealizowana ujemna różnica kursowa**— konto księgowe 801600</span><span class="sxs-lookup"><span data-stu-id="54e77-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="54e77-114">**Niezrealizowana dodatnia różnica kursowa**— konto księgowe 801600</span><span class="sxs-lookup"><span data-stu-id="54e77-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="54e77-115">**Niezrealizowana ujemna różnica kursowa**— konto księgowe 801400</span><span class="sxs-lookup"><span data-stu-id="54e77-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="54e77-116">Oryginalne transakcje</span><span class="sxs-lookup"><span data-stu-id="54e77-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="54e77-117">Transakcje za pomocą blankietów kasowych w USMF</span><span class="sxs-lookup"><span data-stu-id="54e77-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="54e77-118">Data</span><span class="sxs-lookup"><span data-stu-id="54e77-118">Date</span></span>       | <span data-ttu-id="54e77-119">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="54e77-119">Ledger account</span></span>               | <span data-ttu-id="54e77-120">Waluta</span><span class="sxs-lookup"><span data-stu-id="54e77-120">Currency</span></span> | <span data-ttu-id="54e77-121">Kwota</span><span class="sxs-lookup"><span data-stu-id="54e77-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="54e77-122">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="54e77-122">10/11/2015</span></span> | <span data-ttu-id="54e77-123">110110 – Kasa</span><span class="sxs-lookup"><span data-stu-id="54e77-123">110110 – Cash</span></span>                | <span data-ttu-id="54e77-124">USD</span><span class="sxs-lookup"><span data-stu-id="54e77-124">USD</span></span>      | <span data-ttu-id="54e77-125">500</span><span class="sxs-lookup"><span data-stu-id="54e77-125">500</span></span>    |
| <span data-ttu-id="54e77-126">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="54e77-126">10/11/2015</span></span> | <span data-ttu-id="54e77-127">130100 – Rozrachunki z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="54e77-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="54e77-128">USD</span><span class="sxs-lookup"><span data-stu-id="54e77-128">USD</span></span>      | <span data-ttu-id="54e77-129">-500</span><span class="sxs-lookup"><span data-stu-id="54e77-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="54e77-130">Kursy wymiany</span><span class="sxs-lookup"><span data-stu-id="54e77-130">Exchange rates</span></span>
| <span data-ttu-id="54e77-131">Z waluty</span><span class="sxs-lookup"><span data-stu-id="54e77-131">From currency</span></span> | <span data-ttu-id="54e77-132">Na walutę</span><span class="sxs-lookup"><span data-stu-id="54e77-132">To currency</span></span> | <span data-ttu-id="54e77-133">Data początkowa</span><span class="sxs-lookup"><span data-stu-id="54e77-133">Start date</span></span> | <span data-ttu-id="54e77-134">Kurs wymiany</span><span class="sxs-lookup"><span data-stu-id="54e77-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="54e77-135">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-135">EUR</span></span>           | <span data-ttu-id="54e77-136">USD</span><span class="sxs-lookup"><span data-stu-id="54e77-136">USD</span></span>         | <span data-ttu-id="54e77-137">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="54e77-137">10/1/2015</span></span>  | <span data-ttu-id="54e77-138">200</span><span class="sxs-lookup"><span data-stu-id="54e77-138">200</span></span>           |
| <span data-ttu-id="54e77-139">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-139">EUR</span></span>           | <span data-ttu-id="54e77-140">USD</span><span class="sxs-lookup"><span data-stu-id="54e77-140">USD</span></span>         | <span data-ttu-id="54e77-141">11/1/2015</span><span class="sxs-lookup"><span data-stu-id="54e77-141">11/1/2015</span></span>  | <span data-ttu-id="54e77-142">150</span><span class="sxs-lookup"><span data-stu-id="54e77-142">150</span></span>           |
| <span data-ttu-id="54e77-143">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-143">EUR</span></span>           | <span data-ttu-id="54e77-144">USD</span><span class="sxs-lookup"><span data-stu-id="54e77-144">USD</span></span>         | <span data-ttu-id="54e77-145">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="54e77-145">12/1/2012</span></span>  | <span data-ttu-id="54e77-146">100</span><span class="sxs-lookup"><span data-stu-id="54e77-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="54e77-147">Wykonywanie konsolidacji dla października 2015</span><span class="sxs-lookup"><span data-stu-id="54e77-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="54e77-148">Salda w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="54e77-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="54e77-149">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="54e77-149">Ledger account</span></span> | <span data-ttu-id="54e77-150">Waluta</span><span class="sxs-lookup"><span data-stu-id="54e77-150">Currency</span></span> | <span data-ttu-id="54e77-151">Kwota</span><span class="sxs-lookup"><span data-stu-id="54e77-151">Amount</span></span> | <span data-ttu-id="54e77-152">Obliczanie</span><span class="sxs-lookup"><span data-stu-id="54e77-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="54e77-153">110110</span><span class="sxs-lookup"><span data-stu-id="54e77-153">110110</span></span>         | <span data-ttu-id="54e77-154">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-154">EUR</span></span>      | <span data-ttu-id="54e77-155">250</span><span class="sxs-lookup"><span data-stu-id="54e77-155">250</span></span>    | <span data-ttu-id="54e77-156">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="54e77-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="54e77-157">130100</span><span class="sxs-lookup"><span data-stu-id="54e77-157">130100</span></span>         | <span data-ttu-id="54e77-158">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-158">EUR</span></span>      | <span data-ttu-id="54e77-159">-250</span><span class="sxs-lookup"><span data-stu-id="54e77-159">-250</span></span>   | <span data-ttu-id="54e77-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="54e77-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="54e77-161">Wykonaj przeszacowanie w walucie dla kont od 1 października 2015 do 30 listopada 2015 roku.</span><span class="sxs-lookup"><span data-stu-id="54e77-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="54e77-162">Salda w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="54e77-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="54e77-163">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="54e77-163">Ledger account</span></span> | <span data-ttu-id="54e77-164">Waluta</span><span class="sxs-lookup"><span data-stu-id="54e77-164">Currency</span></span> | <span data-ttu-id="54e77-165">Kwota</span><span class="sxs-lookup"><span data-stu-id="54e77-165">Amount</span></span>  | <span data-ttu-id="54e77-166">Obliczanie</span><span class="sxs-lookup"><span data-stu-id="54e77-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="54e77-167">110110</span><span class="sxs-lookup"><span data-stu-id="54e77-167">110110</span></span>         | <span data-ttu-id="54e77-168">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-168">EUR</span></span>      | <span data-ttu-id="54e77-169">333.33</span><span class="sxs-lookup"><span data-stu-id="54e77-169">333.33</span></span>  | <span data-ttu-id="54e77-170">Pierwotna kwota 500 × 66.6667%</span><span class="sxs-lookup"><span data-stu-id="54e77-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="54e77-171">130100</span><span class="sxs-lookup"><span data-stu-id="54e77-171">130100</span></span>         | <span data-ttu-id="54e77-172">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-172">EUR</span></span>      | <span data-ttu-id="54e77-173">-333.33</span><span class="sxs-lookup"><span data-stu-id="54e77-173">-333.33</span></span> | <span data-ttu-id="54e77-174">Pierwotna kwota -500 × 66.6667%</span><span class="sxs-lookup"><span data-stu-id="54e77-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="54e77-175">801400</span><span class="sxs-lookup"><span data-stu-id="54e77-175">801400</span></span>         | <span data-ttu-id="54e77-176">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-176">EUR</span></span>      | <span data-ttu-id="54e77-177">83.33</span><span class="sxs-lookup"><span data-stu-id="54e77-177">83.33</span></span>   | <span data-ttu-id="54e77-178">333.33 – 250</span><span class="sxs-lookup"><span data-stu-id="54e77-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="54e77-179">801600</span><span class="sxs-lookup"><span data-stu-id="54e77-179">801600</span></span>         | <span data-ttu-id="54e77-180">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-180">EUR</span></span>      | <span data-ttu-id="54e77-181">-83.33</span><span class="sxs-lookup"><span data-stu-id="54e77-181">-83.33</span></span>  | <span data-ttu-id="54e77-182">-333.33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="54e77-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="54e77-183">Zobaczysz dodatkowe transakcje dla kwot w walucie raportowania.</span><span class="sxs-lookup"><span data-stu-id="54e77-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="54e77-184">Wykonaj przeszacowanie w walucie dla kont od 1 października 2015 do 31 grudnia 2015 roku.</span><span class="sxs-lookup"><span data-stu-id="54e77-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="54e77-185">Salda w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="54e77-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="54e77-186">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="54e77-186">Ledger account</span></span> | <span data-ttu-id="54e77-187">Waluta</span><span class="sxs-lookup"><span data-stu-id="54e77-187">Currency</span></span> | <span data-ttu-id="54e77-188">Kwota</span><span class="sxs-lookup"><span data-stu-id="54e77-188">Amount</span></span>  | <span data-ttu-id="54e77-189">Obliczanie</span><span class="sxs-lookup"><span data-stu-id="54e77-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="54e77-190">110110</span><span class="sxs-lookup"><span data-stu-id="54e77-190">110110</span></span>         | <span data-ttu-id="54e77-191">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-191">EUR</span></span>      | <span data-ttu-id="54e77-192">500,00</span><span class="sxs-lookup"><span data-stu-id="54e77-192">500.00</span></span>  | <span data-ttu-id="54e77-193">Pierwotna kwota 500 × 1</span><span class="sxs-lookup"><span data-stu-id="54e77-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="54e77-194">130100</span><span class="sxs-lookup"><span data-stu-id="54e77-194">130100</span></span>         | <span data-ttu-id="54e77-195">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-195">EUR</span></span>      | <span data-ttu-id="54e77-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="54e77-196">-500.00</span></span> | <span data-ttu-id="54e77-197">Pierwotna kwota -500 × 1%</span><span class="sxs-lookup"><span data-stu-id="54e77-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="54e77-198">801400</span><span class="sxs-lookup"><span data-stu-id="54e77-198">801400</span></span>         | <span data-ttu-id="54e77-199">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-199">EUR</span></span>      | <span data-ttu-id="54e77-200">250</span><span class="sxs-lookup"><span data-stu-id="54e77-200">250</span></span>     | <span data-ttu-id="54e77-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span><span class="sxs-lookup"><span data-stu-id="54e77-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="54e77-202">801600</span><span class="sxs-lookup"><span data-stu-id="54e77-202">801600</span></span>         | <span data-ttu-id="54e77-203">EUR</span><span class="sxs-lookup"><span data-stu-id="54e77-203">EUR</span></span>      | <span data-ttu-id="54e77-204">-250</span><span class="sxs-lookup"><span data-stu-id="54e77-204">-250</span></span>    | <span data-ttu-id="54e77-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span><span class="sxs-lookup"><span data-stu-id="54e77-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






