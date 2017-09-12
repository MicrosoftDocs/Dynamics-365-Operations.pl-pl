---
title: Przeszacowanie waluty w konsolidowanej firmie
description: 
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 643af8d771685fe8fd652b353d41f2679e0bef8b
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="56a02-102">Przeszacowanie waluty w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="56a02-102">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="56a02-103">Podczas konsolidowania danych z jednej waluty rozliczeniowej do innej należy wykonać przeszacowanie waluty, jeśli nastąpiła zmiana kursów wymiany, tak aby salda kont zostały poprawnie przeszacowane.</span><span class="sxs-lookup"><span data-stu-id="56a02-103">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="56a02-104">Podczas pierwszej konsolidacji danych użyj karty **przeliczania waluty**, aby wybrać początkowe kursy wymiany do przeszacowania podczas procesu konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="56a02-104">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="56a02-105">Po wprowadzeniu nowego kursu wymiany (na przykład w kolejnym miesiącu) można przeszacować salda konta.</span><span class="sxs-lookup"><span data-stu-id="56a02-105">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="56a02-106">Niezrealizowane dodatnie różnice kursowe zostaną odpowiednio zaktualizowane na podstawie nowego kursu wymiany i daty.</span><span class="sxs-lookup"><span data-stu-id="56a02-106">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="56a02-107">Poniższy przykład ilustruje zapisy księgowe utworzone podczas tego procesu.</span><span class="sxs-lookup"><span data-stu-id="56a02-107">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="56a02-108">Konfiguracja firmy</span><span class="sxs-lookup"><span data-stu-id="56a02-108">Company setup</span></span>
-   <span data-ttu-id="56a02-109">**Źródło/ firma (USMF)** — jako waluta raportowania i księgowania używane są dolary amerykańskie (USD).</span><span class="sxs-lookup"><span data-stu-id="56a02-109">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="56a02-110">**Konsolidowana firma (CON)** — jako waluta raportowania i księgowania używane jest euro (EUR).</span><span class="sxs-lookup"><span data-stu-id="56a02-110">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="56a02-111">**Zrealizowana dodatnia różnica kursowa** — konto księgowe 801500</span><span class="sxs-lookup"><span data-stu-id="56a02-111">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="56a02-112">**Zrealizowana ujemna różnica kursowa**— konto księgowe 801600</span><span class="sxs-lookup"><span data-stu-id="56a02-112">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="56a02-113">**Niezrealizowana dodatnia różnica kursowa**— konto księgowe 801600</span><span class="sxs-lookup"><span data-stu-id="56a02-113">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="56a02-114">**Niezrealizowana ujemna różnica kursowa**— konto księgowe 801400</span><span class="sxs-lookup"><span data-stu-id="56a02-114">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="56a02-115">Oryginalne transakcje</span><span class="sxs-lookup"><span data-stu-id="56a02-115">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="56a02-116">Transakcje za pomocą blankietów kasowych w USMF</span><span class="sxs-lookup"><span data-stu-id="56a02-116">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="56a02-117">Data</span><span class="sxs-lookup"><span data-stu-id="56a02-117">Date</span></span>       | <span data-ttu-id="56a02-118">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="56a02-118">Ledger account</span></span>               | <span data-ttu-id="56a02-119">Waluta</span><span class="sxs-lookup"><span data-stu-id="56a02-119">Currency</span></span> | <span data-ttu-id="56a02-120">Kwota</span><span class="sxs-lookup"><span data-stu-id="56a02-120">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="56a02-121">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="56a02-121">10/11/2015</span></span> | <span data-ttu-id="56a02-122">110110 – Kasa</span><span class="sxs-lookup"><span data-stu-id="56a02-122">110110 – Cash</span></span>                | <span data-ttu-id="56a02-123">USD</span><span class="sxs-lookup"><span data-stu-id="56a02-123">USD</span></span>      | <span data-ttu-id="56a02-124">500</span><span class="sxs-lookup"><span data-stu-id="56a02-124">500</span></span>    |
| <span data-ttu-id="56a02-125">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="56a02-125">10/11/2015</span></span> | <span data-ttu-id="56a02-126">130100 – Rozrachunki z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="56a02-126">130100 – Accounts Receivable</span></span> | <span data-ttu-id="56a02-127">USD</span><span class="sxs-lookup"><span data-stu-id="56a02-127">USD</span></span>      | <span data-ttu-id="56a02-128">-500</span><span class="sxs-lookup"><span data-stu-id="56a02-128">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="56a02-129">Kursy wymiany</span><span class="sxs-lookup"><span data-stu-id="56a02-129">Exchange rates</span></span>
| <span data-ttu-id="56a02-130">Z waluty</span><span class="sxs-lookup"><span data-stu-id="56a02-130">From currency</span></span> | <span data-ttu-id="56a02-131">Na walutę</span><span class="sxs-lookup"><span data-stu-id="56a02-131">To currency</span></span> | <span data-ttu-id="56a02-132">Data początkowa</span><span class="sxs-lookup"><span data-stu-id="56a02-132">Start date</span></span> | <span data-ttu-id="56a02-133">Kurs wymiany</span><span class="sxs-lookup"><span data-stu-id="56a02-133">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="56a02-134">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-134">EUR</span></span>           | <span data-ttu-id="56a02-135">USD</span><span class="sxs-lookup"><span data-stu-id="56a02-135">USD</span></span>         | <span data-ttu-id="56a02-136">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="56a02-136">10/1/2015</span></span>  | <span data-ttu-id="56a02-137">200</span><span class="sxs-lookup"><span data-stu-id="56a02-137">200</span></span>           |
| <span data-ttu-id="56a02-138">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-138">EUR</span></span>           | <span data-ttu-id="56a02-139">USD</span><span class="sxs-lookup"><span data-stu-id="56a02-139">USD</span></span>         | <span data-ttu-id="56a02-140">11/1/2015</span><span class="sxs-lookup"><span data-stu-id="56a02-140">11/1/2015</span></span>  | <span data-ttu-id="56a02-141">150</span><span class="sxs-lookup"><span data-stu-id="56a02-141">150</span></span>           |
| <span data-ttu-id="56a02-142">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-142">EUR</span></span>           | <span data-ttu-id="56a02-143">USD</span><span class="sxs-lookup"><span data-stu-id="56a02-143">USD</span></span>         | <span data-ttu-id="56a02-144">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="56a02-144">12/1/2012</span></span>  | <span data-ttu-id="56a02-145">100</span><span class="sxs-lookup"><span data-stu-id="56a02-145">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="56a02-146">Wykonywanie konsolidacji dla października 2015</span><span class="sxs-lookup"><span data-stu-id="56a02-146">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="56a02-147">Salda w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="56a02-147">Balances in the consolidation company</span></span>

| <span data-ttu-id="56a02-148">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="56a02-148">Ledger account</span></span> | <span data-ttu-id="56a02-149">Waluta</span><span class="sxs-lookup"><span data-stu-id="56a02-149">Currency</span></span> | <span data-ttu-id="56a02-150">Kwota</span><span class="sxs-lookup"><span data-stu-id="56a02-150">Amount</span></span> | <span data-ttu-id="56a02-151">Obliczanie</span><span class="sxs-lookup"><span data-stu-id="56a02-151">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="56a02-152">110110</span><span class="sxs-lookup"><span data-stu-id="56a02-152">110110</span></span>         | <span data-ttu-id="56a02-153">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-153">EUR</span></span>      | <span data-ttu-id="56a02-154">250</span><span class="sxs-lookup"><span data-stu-id="56a02-154">250</span></span>    | <span data-ttu-id="56a02-155">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="56a02-155">500 USD × 50%</span></span>  |
| <span data-ttu-id="56a02-156">130100</span><span class="sxs-lookup"><span data-stu-id="56a02-156">130100</span></span>         | <span data-ttu-id="56a02-157">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-157">EUR</span></span>      | <span data-ttu-id="56a02-158">-250</span><span class="sxs-lookup"><span data-stu-id="56a02-158">-250</span></span>   | <span data-ttu-id="56a02-159">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="56a02-159">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="56a02-160">Wykonaj przeszacowanie w walucie dla kont od 1 października 2015 do 30 listopada 2015 roku.</span><span class="sxs-lookup"><span data-stu-id="56a02-160">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="56a02-161">Salda w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="56a02-161">Balances in the consolidation company</span></span>

| <span data-ttu-id="56a02-162">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="56a02-162">Ledger account</span></span> | <span data-ttu-id="56a02-163">Waluta</span><span class="sxs-lookup"><span data-stu-id="56a02-163">Currency</span></span> | <span data-ttu-id="56a02-164">Kwota</span><span class="sxs-lookup"><span data-stu-id="56a02-164">Amount</span></span>  | <span data-ttu-id="56a02-165">Obliczanie</span><span class="sxs-lookup"><span data-stu-id="56a02-165">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="56a02-166">110110</span><span class="sxs-lookup"><span data-stu-id="56a02-166">110110</span></span>         | <span data-ttu-id="56a02-167">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-167">EUR</span></span>      | <span data-ttu-id="56a02-168">333.33</span><span class="sxs-lookup"><span data-stu-id="56a02-168">333.33</span></span>  | <span data-ttu-id="56a02-169">Pierwotna kwota 500 × 66.6667%</span><span class="sxs-lookup"><span data-stu-id="56a02-169">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="56a02-170">130100</span><span class="sxs-lookup"><span data-stu-id="56a02-170">130100</span></span>         | <span data-ttu-id="56a02-171">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-171">EUR</span></span>      | <span data-ttu-id="56a02-172">-333.33</span><span class="sxs-lookup"><span data-stu-id="56a02-172">-333.33</span></span> | <span data-ttu-id="56a02-173">Pierwotna kwota -500 × 66.6667%</span><span class="sxs-lookup"><span data-stu-id="56a02-173">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="56a02-174">801400</span><span class="sxs-lookup"><span data-stu-id="56a02-174">801400</span></span>         | <span data-ttu-id="56a02-175">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-175">EUR</span></span>      | <span data-ttu-id="56a02-176">83.33</span><span class="sxs-lookup"><span data-stu-id="56a02-176">83.33</span></span>   | <span data-ttu-id="56a02-177">333.33 – 250</span><span class="sxs-lookup"><span data-stu-id="56a02-177">333.33 – 250</span></span>                       |
| <span data-ttu-id="56a02-178">801600</span><span class="sxs-lookup"><span data-stu-id="56a02-178">801600</span></span>         | <span data-ttu-id="56a02-179">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-179">EUR</span></span>      | <span data-ttu-id="56a02-180">-83.33</span><span class="sxs-lookup"><span data-stu-id="56a02-180">-83.33</span></span>  | <span data-ttu-id="56a02-181">-333.33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="56a02-181">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="56a02-182">Zobaczysz dodatkowe transakcje dla kwot w walucie raportowania.</span><span class="sxs-lookup"><span data-stu-id="56a02-182">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="56a02-183">Wykonaj przeszacowanie w walucie dla kont od 1 października 2015 do 31 grudnia 2015 roku.</span><span class="sxs-lookup"><span data-stu-id="56a02-183">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="56a02-184">Salda w konsolidowanej firmie</span><span class="sxs-lookup"><span data-stu-id="56a02-184">Balances in the consolidation company</span></span>

| <span data-ttu-id="56a02-185">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="56a02-185">Ledger account</span></span> | <span data-ttu-id="56a02-186">Waluta</span><span class="sxs-lookup"><span data-stu-id="56a02-186">Currency</span></span> | <span data-ttu-id="56a02-187">Kwota</span><span class="sxs-lookup"><span data-stu-id="56a02-187">Amount</span></span>  | <span data-ttu-id="56a02-188">Obliczanie</span><span class="sxs-lookup"><span data-stu-id="56a02-188">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="56a02-189">110110</span><span class="sxs-lookup"><span data-stu-id="56a02-189">110110</span></span>         | <span data-ttu-id="56a02-190">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-190">EUR</span></span>      | <span data-ttu-id="56a02-191">500,00</span><span class="sxs-lookup"><span data-stu-id="56a02-191">500.00</span></span>  | <span data-ttu-id="56a02-192">Pierwotna kwota 500 × 1</span><span class="sxs-lookup"><span data-stu-id="56a02-192">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="56a02-193">130100</span><span class="sxs-lookup"><span data-stu-id="56a02-193">130100</span></span>         | <span data-ttu-id="56a02-194">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-194">EUR</span></span>      | <span data-ttu-id="56a02-195">-500,00</span><span class="sxs-lookup"><span data-stu-id="56a02-195">-500.00</span></span> | <span data-ttu-id="56a02-196">Pierwotna kwota -500 × 1%</span><span class="sxs-lookup"><span data-stu-id="56a02-196">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="56a02-197">801400</span><span class="sxs-lookup"><span data-stu-id="56a02-197">801400</span></span>         | <span data-ttu-id="56a02-198">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-198">EUR</span></span>      | <span data-ttu-id="56a02-199">250</span><span class="sxs-lookup"><span data-stu-id="56a02-199">250</span></span>     | <span data-ttu-id="56a02-200">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span><span class="sxs-lookup"><span data-stu-id="56a02-200">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="56a02-201">801600</span><span class="sxs-lookup"><span data-stu-id="56a02-201">801600</span></span>         | <span data-ttu-id="56a02-202">EUR</span><span class="sxs-lookup"><span data-stu-id="56a02-202">EUR</span></span>      | <span data-ttu-id="56a02-203">-250</span><span class="sxs-lookup"><span data-stu-id="56a02-203">-250</span></span>    | <span data-ttu-id="56a02-204">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span><span class="sxs-lookup"><span data-stu-id="56a02-204">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






