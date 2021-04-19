---
title: Przykłady i logika raportu wiekowania zapasów
description: W tym temacie przedstawiono przykłady przedstawiające sposób interpretacji wyników raportu wiekowania zapasów.
author: AndersGirke
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: edc974bcbd72ef62438fd6271a6fd0e56143f976
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821592"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="c622e-103">Przykłady i logika raportu wiekowania zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c622e-104">W tym temacie przedstawiono przykłady przedstawiające sposób interpretacji wyników raportu **Wiekowania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c622e-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="c622e-105">Ten raport umożliwia kategoryzowanie dostępnych ilości i wartości zapasów dla wybranego towaru lub grupy towarów do kilku przedziałów okresów.</span><span class="sxs-lookup"><span data-stu-id="c622e-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="c622e-106">W tym temacie przedstawiono również wewnętrzną logikę raportu.</span><span class="sxs-lookup"><span data-stu-id="c622e-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="c622e-107">W przykładach w tym temacie przedstawiono wyniki prezentowane w standardowym raporcie **Wiekowania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c622e-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="c622e-108">Zasadniczo zalecamy jednak korzystanie z wersji [raportu przechowywania raportu o starzeniu się zapasów](inventory-aging-report-storage.md), zwłaszcza gdy masz wiele produktów i magazynów, które muszą zostać przetworzone.</span><span class="sxs-lookup"><span data-stu-id="c622e-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="c622e-109">Przechowywanie raportów wiekowania zapasów powoduje zapisanie wszystkich generowanych raportów, wyświetlenie wyników w postaci strony interakcyjnej i wykresu oraz umożliwia wyeksportowanie dowolnego zapisanego raportu.</span><span class="sxs-lookup"><span data-stu-id="c622e-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="c622e-110">Przykładowe dane używane w tych przykładach</span><span class="sxs-lookup"><span data-stu-id="c622e-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="c622e-111">Przykłady przedstawione w tym temacie są oparte na przykładowych danych transakcji magazynowych opisanych w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="c622e-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="c622e-112">Konfiguracja wymiarów magazynowania</span><span class="sxs-lookup"><span data-stu-id="c622e-112">Storage dimension setup</span></span>

<span data-ttu-id="c622e-113">Przykładowy system zawiera następujące ustawienia wymiarów magazynowania:</span><span class="sxs-lookup"><span data-stu-id="c622e-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="c622e-114">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="c622e-114">Name</span></span>      | <span data-ttu-id="c622e-115">Aktywna</span><span class="sxs-lookup"><span data-stu-id="c622e-115">Active</span></span> | <span data-ttu-id="c622e-116">Magazyn</span><span class="sxs-lookup"><span data-stu-id="c622e-116">Physical inventory</span></span> | <span data-ttu-id="c622e-117">Magazyn finansowy</span><span class="sxs-lookup"><span data-stu-id="c622e-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="c622e-118">Oddział</span><span class="sxs-lookup"><span data-stu-id="c622e-118">Site</span></span>      | <span data-ttu-id="c622e-119">Tak</span><span class="sxs-lookup"><span data-stu-id="c622e-119">Yes</span></span>    | <span data-ttu-id="c622e-120">Tak</span><span class="sxs-lookup"><span data-stu-id="c622e-120">Yes</span></span>                | <span data-ttu-id="c622e-121">Tak</span><span class="sxs-lookup"><span data-stu-id="c622e-121">Yes</span></span>                 |
| <span data-ttu-id="c622e-122">Magazyn</span><span class="sxs-lookup"><span data-stu-id="c622e-122">Warehouse</span></span> | <span data-ttu-id="c622e-123">Tak</span><span class="sxs-lookup"><span data-stu-id="c622e-123">Yes</span></span>    | <span data-ttu-id="c622e-124">Tak</span><span class="sxs-lookup"><span data-stu-id="c622e-124">Yes</span></span>                | <span data-ttu-id="c622e-125">Nr</span><span class="sxs-lookup"><span data-stu-id="c622e-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="c622e-126">Model magazynu</span><span class="sxs-lookup"><span data-stu-id="c622e-126">Inventory model</span></span>

<span data-ttu-id="c622e-127">W przypadku systemu przykładowego model magazynu dla zwolnionych produktów to *FIFO*, a ustawienie **Koszt własny** dla modelu magazynu to *Włączanie wartości fizycznej*.</span><span class="sxs-lookup"><span data-stu-id="c622e-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="c622e-128">Transakcje zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-128">Inventory transactions</span></span>

<span data-ttu-id="c622e-129">Przykładowy system zawiera następujące transakcje magazynowe dla zwolnionego produktu o numerze towaru *1000*.</span><span class="sxs-lookup"><span data-stu-id="c622e-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="c622e-130">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="c622e-130">Reference</span></span>      | <span data-ttu-id="c622e-131">Oddział</span><span class="sxs-lookup"><span data-stu-id="c622e-131">Site</span></span> | <span data-ttu-id="c622e-132">Magazyn</span><span class="sxs-lookup"><span data-stu-id="c622e-132">Warehouse</span></span> | <span data-ttu-id="c622e-133">Przychód</span><span class="sxs-lookup"><span data-stu-id="c622e-133">Receipt</span></span>   | <span data-ttu-id="c622e-134">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="c622e-134">Issue</span></span> | <span data-ttu-id="c622e-135">Data fizycznej transakcji</span><span class="sxs-lookup"><span data-stu-id="c622e-135">Physical date</span></span> | <span data-ttu-id="c622e-136">Data finansowa</span><span class="sxs-lookup"><span data-stu-id="c622e-136">Financial date</span></span> | <span data-ttu-id="c622e-137">Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-137">Quantity</span></span> | <span data-ttu-id="c622e-138">Kwota kosztu</span><span class="sxs-lookup"><span data-stu-id="c622e-138">Cost amount</span></span> | <span data-ttu-id="c622e-139">Fizyczna wartość kosztu</span><span class="sxs-lookup"><span data-stu-id="c622e-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="c622e-140">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="c622e-140">Purchase order</span></span> | <span data-ttu-id="c622e-141">1</span><span class="sxs-lookup"><span data-stu-id="c622e-141">1</span></span>    | <span data-ttu-id="c622e-142">11</span><span class="sxs-lookup"><span data-stu-id="c622e-142">11</span></span>        | <span data-ttu-id="c622e-143">Zakupione</span><span class="sxs-lookup"><span data-stu-id="c622e-143">Purchased</span></span> |       | <span data-ttu-id="c622e-144">15 marca</span><span class="sxs-lookup"><span data-stu-id="c622e-144">March 15</span></span>      | <span data-ttu-id="c622e-145">15 marca</span><span class="sxs-lookup"><span data-stu-id="c622e-145">March 15</span></span>       | <span data-ttu-id="c622e-146">10</span><span class="sxs-lookup"><span data-stu-id="c622e-146">10</span></span>       | <span data-ttu-id="c622e-147">1 000</span><span class="sxs-lookup"><span data-stu-id="c622e-147">1,000</span></span>       | <span data-ttu-id="c622e-148">1 000</span><span class="sxs-lookup"><span data-stu-id="c622e-148">1,000</span></span>                |
| <span data-ttu-id="c622e-149">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="c622e-149">Purchase order</span></span> | <span data-ttu-id="c622e-150">2</span><span class="sxs-lookup"><span data-stu-id="c622e-150">2</span></span>    | <span data-ttu-id="c622e-151">21</span><span class="sxs-lookup"><span data-stu-id="c622e-151">21</span></span>        | <span data-ttu-id="c622e-152">Zakupione</span><span class="sxs-lookup"><span data-stu-id="c622e-152">Purchased</span></span> |       | <span data-ttu-id="c622e-153">15 marca</span><span class="sxs-lookup"><span data-stu-id="c622e-153">March 15</span></span>      | <span data-ttu-id="c622e-154">15 marca</span><span class="sxs-lookup"><span data-stu-id="c622e-154">March 15</span></span>       | <span data-ttu-id="c622e-155">10</span><span class="sxs-lookup"><span data-stu-id="c622e-155">10</span></span>       | <span data-ttu-id="c622e-156">2,000</span><span class="sxs-lookup"><span data-stu-id="c622e-156">2,000</span></span>       | <span data-ttu-id="c622e-157">2,000</span><span class="sxs-lookup"><span data-stu-id="c622e-157">2,000</span></span>                |
| <span data-ttu-id="c622e-158">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="c622e-158">Purchase order</span></span> | <span data-ttu-id="c622e-159">1</span><span class="sxs-lookup"><span data-stu-id="c622e-159">1</span></span>    | <span data-ttu-id="c622e-160">11</span><span class="sxs-lookup"><span data-stu-id="c622e-160">11</span></span>        | <span data-ttu-id="c622e-161">Odebrane</span><span class="sxs-lookup"><span data-stu-id="c622e-161">Received</span></span>  |       | <span data-ttu-id="c622e-162">15 kwietnia</span><span class="sxs-lookup"><span data-stu-id="c622e-162">April 15</span></span>      |                | <span data-ttu-id="c622e-163">5</span><span class="sxs-lookup"><span data-stu-id="c622e-163">5</span></span>        |             | <span data-ttu-id="c622e-164">375</span><span class="sxs-lookup"><span data-stu-id="c622e-164">375</span></span>                  |
| <span data-ttu-id="c622e-165">Zamówienie przeniesienia</span><span class="sxs-lookup"><span data-stu-id="c622e-165">Transfer order</span></span> | <span data-ttu-id="c622e-166">1</span><span class="sxs-lookup"><span data-stu-id="c622e-166">1</span></span>    | <span data-ttu-id="c622e-167">11</span><span class="sxs-lookup"><span data-stu-id="c622e-167">11</span></span>        |           | <span data-ttu-id="c622e-168">Sprzedane</span><span class="sxs-lookup"><span data-stu-id="c622e-168">Sold</span></span>  | <span data-ttu-id="c622e-169">2 maja</span><span class="sxs-lookup"><span data-stu-id="c622e-169">May 2</span></span>         | <span data-ttu-id="c622e-170">2 maja</span><span class="sxs-lookup"><span data-stu-id="c622e-170">May 2</span></span>          | <span data-ttu-id="c622e-171">-5</span><span class="sxs-lookup"><span data-stu-id="c622e-171">-5</span></span>       | <span data-ttu-id="c622e-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="c622e-172">-458.33</span></span>     | <span data-ttu-id="c622e-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="c622e-173">-458.33</span></span>              |
| <span data-ttu-id="c622e-174">Zamówienie przeniesienia</span><span class="sxs-lookup"><span data-stu-id="c622e-174">Transfer order</span></span> | <span data-ttu-id="c622e-175">1</span><span class="sxs-lookup"><span data-stu-id="c622e-175">1</span></span>    | <span data-ttu-id="c622e-176">12</span><span class="sxs-lookup"><span data-stu-id="c622e-176">12</span></span>        | <span data-ttu-id="c622e-177">Zakupione</span><span class="sxs-lookup"><span data-stu-id="c622e-177">Purchased</span></span> |       | <span data-ttu-id="c622e-178">2 maja</span><span class="sxs-lookup"><span data-stu-id="c622e-178">May 2</span></span>         | <span data-ttu-id="c622e-179">2 maja</span><span class="sxs-lookup"><span data-stu-id="c622e-179">May 2</span></span>          | <span data-ttu-id="c622e-180">5</span><span class="sxs-lookup"><span data-stu-id="c622e-180">5</span></span>        | <span data-ttu-id="c622e-181">458.33</span><span class="sxs-lookup"><span data-stu-id="c622e-181">458.33</span></span>      | <span data-ttu-id="c622e-182">458.33</span><span class="sxs-lookup"><span data-stu-id="c622e-182">458.33</span></span>               |
| <span data-ttu-id="c622e-183">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c622e-183">Sales order</span></span>    | <span data-ttu-id="c622e-184">1</span><span class="sxs-lookup"><span data-stu-id="c622e-184">1</span></span>    | <span data-ttu-id="c622e-185">12</span><span class="sxs-lookup"><span data-stu-id="c622e-185">12</span></span>        |           | <span data-ttu-id="c622e-186">Sprzedane</span><span class="sxs-lookup"><span data-stu-id="c622e-186">Sold</span></span>  | <span data-ttu-id="c622e-187">3 maja</span><span class="sxs-lookup"><span data-stu-id="c622e-187">May 3</span></span>         | <span data-ttu-id="c622e-188">3 maja</span><span class="sxs-lookup"><span data-stu-id="c622e-188">May 3</span></span>          | <span data-ttu-id="c622e-189">-1</span><span class="sxs-lookup"><span data-stu-id="c622e-189">-1</span></span>       | <span data-ttu-id="c622e-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="c622e-190">-91.67</span></span>      | <span data-ttu-id="c622e-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="c622e-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="c622e-192">Sposób obliczania ilości i kwot w każdym przedziale okresów</span><span class="sxs-lookup"><span data-stu-id="c622e-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="c622e-193">Korzystając z przykładowych danych opisanych w poprzednich sekcjach, można uruchomić raport **Wiekowania zapasów**, który ma następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="c622e-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="c622e-194">**Data:** *9 maj 2020*</span><span class="sxs-lookup"><span data-stu-id="c622e-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="c622e-195">**Oddział:** *Widok*</span><span class="sxs-lookup"><span data-stu-id="c622e-195">**Site:** *View*</span></span>
- <span data-ttu-id="c622e-196">**Magazyn:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="c622e-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="c622e-197">**Kod pozycji:** *Razem*</span><span class="sxs-lookup"><span data-stu-id="c622e-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="c622e-198">**Okres wiekowania:** należy uzupełnić to pole, aby były generowane pakiety miesięczne.</span><span class="sxs-lookup"><span data-stu-id="c622e-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="c622e-199">W takim przypadku zawartość generowanego raportu będzie podobna do poniższego przykładu.</span><span class="sxs-lookup"><span data-stu-id="c622e-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="c622e-200">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="c622e-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-201">Oddział</span><span class="sxs-lookup"><span data-stu-id="c622e-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-202">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-203">Dostępna wartość</span><span class="sxs-lookup"><span data-stu-id="c622e-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-204">Ilość wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-205">Wartość zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-206">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="c622e-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="c622e-207">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="c622e-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="c622e-208">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="c622e-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="c622e-209">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="c622e-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="c622e-210">P1:Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="c622e-211">P1:Kwota</span><span class="sxs-lookup"><span data-stu-id="c622e-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="c622e-212">P2:Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="c622e-213">P2:Kwota</span><span class="sxs-lookup"><span data-stu-id="c622e-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="c622e-214">P3:Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="c622e-215">P3:Kwota</span><span class="sxs-lookup"><span data-stu-id="c622e-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="c622e-216">1000</span><span class="sxs-lookup"><span data-stu-id="c622e-216">1000</span></span></td>
    <td><span data-ttu-id="c622e-217">1</span><span class="sxs-lookup"><span data-stu-id="c622e-217">1</span></span></td>
    <td><span data-ttu-id="c622e-218">14</span><span class="sxs-lookup"><span data-stu-id="c622e-218">14</span></span></td>
    <td><span data-ttu-id="c622e-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="c622e-219">1,283.33</span></span></td>
    <td><span data-ttu-id="c622e-220">14</span><span class="sxs-lookup"><span data-stu-id="c622e-220">14</span></span></td>
    <td><span data-ttu-id="c622e-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="c622e-221">1,283.33</span></span></td>
    <td><span data-ttu-id="c622e-222">91.67</span><span class="sxs-lookup"><span data-stu-id="c622e-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-223">5.00</span><span class="sxs-lookup"><span data-stu-id="c622e-223">5.00</span></span></td>
    <td><span data-ttu-id="c622e-224">458.33</span><span class="sxs-lookup"><span data-stu-id="c622e-224">458.33</span></span></td>
    <td><span data-ttu-id="c622e-225">9.00</span><span class="sxs-lookup"><span data-stu-id="c622e-225">9.00</span></span></td>
    <td><span data-ttu-id="c622e-226">825.00</span><span class="sxs-lookup"><span data-stu-id="c622e-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="c622e-227">1000</span><span class="sxs-lookup"><span data-stu-id="c622e-227">1000</span></span></td>
    <td><span data-ttu-id="c622e-228">2</span><span class="sxs-lookup"><span data-stu-id="c622e-228">2</span></span></td>
    <td><span data-ttu-id="c622e-229">10</span><span class="sxs-lookup"><span data-stu-id="c622e-229">10</span></span></td>
    <td><span data-ttu-id="c622e-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="c622e-230">2,000.00</span></span></td>
    <td><span data-ttu-id="c622e-231">10</span><span class="sxs-lookup"><span data-stu-id="c622e-231">10</span></span></td>
    <td><span data-ttu-id="c622e-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="c622e-232">2,000.00</span></span></td>
    <td><span data-ttu-id="c622e-233">200.00</span><span class="sxs-lookup"><span data-stu-id="c622e-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-234">10,00</span><span class="sxs-lookup"><span data-stu-id="c622e-234">10.00</span></span></td>
    <td><span data-ttu-id="c622e-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="c622e-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="c622e-236"><strong>1000 Razem</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="c622e-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="c622e-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="c622e-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="c622e-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="c622e-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="c622e-243">W tym przykładzie przedstawiono następujące szczegóły:</span><span class="sxs-lookup"><span data-stu-id="c622e-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="c622e-244">Wartości **Ilość wartości zapasów**, **Wartość zapasów** oraz **Średnie koszty jednostkowe**, które są wyświetlane w raporcie, są wartościami dla wymiaru magazynu finansowego (w tym przypadku **Oddział**).</span><span class="sxs-lookup"><span data-stu-id="c622e-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="c622e-245">Na przykład w przypadku oddziału 1 raport zawiera następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="c622e-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="c622e-246">Wartość **Ilość wartości zapasów** wynosi *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="c622e-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="c622e-247">Wartość **Wartość zapasów** wynosi *1283,33* (= 1000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="c622e-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="c622e-248">Wartość **Średni koszt jednostkowy** wynosi *91,67*.</span><span class="sxs-lookup"><span data-stu-id="c622e-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="c622e-249">Wartość **Dostępna wartość** oraz wartość **Kwota** w każdym przedziale okresu są obliczane przy użyciu wartości **Średni koszt jednostkowy**.</span><span class="sxs-lookup"><span data-stu-id="c622e-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="c622e-250">Raport określa ilość zapasów dla każdego przedziału okresu, sumując łączną ilość zapasów dla każdego przedziału okresu.</span><span class="sxs-lookup"><span data-stu-id="c622e-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="c622e-251">Następnie stosuje regułę FIFO (First on) do odliczenia łącznej wydanej ilości, niezależnie od modelu magazynu, który jest używany przez towary.</span><span class="sxs-lookup"><span data-stu-id="c622e-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="c622e-252">Jeśli ten sam raport zostanie uruchomiony ponownie, ale tym razem ustaw pole **Oddział** i **Magazyn** na *Wyświetlanie*, nowy raport będzie wyglądał następująco.</span><span class="sxs-lookup"><span data-stu-id="c622e-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="c622e-253">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="c622e-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-254">Oddział</span><span class="sxs-lookup"><span data-stu-id="c622e-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-255">Magazyn</span><span class="sxs-lookup"><span data-stu-id="c622e-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-256">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-257">Dostępna wartość</span><span class="sxs-lookup"><span data-stu-id="c622e-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-258">Ilość wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-259">Wartość zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-260">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="c622e-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="c622e-261">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="c622e-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="c622e-262">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="c622e-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="c622e-263">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="c622e-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="c622e-264">P1:Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="c622e-265">P1:Kwota</span><span class="sxs-lookup"><span data-stu-id="c622e-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="c622e-266">P2:Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="c622e-267">P2:Kwota</span><span class="sxs-lookup"><span data-stu-id="c622e-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="c622e-268">P3:Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="c622e-269">P3:Kwota</span><span class="sxs-lookup"><span data-stu-id="c622e-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="c622e-270">1000</span><span class="sxs-lookup"><span data-stu-id="c622e-270">1000</span></span></td>
    <td><span data-ttu-id="c622e-271">1</span><span class="sxs-lookup"><span data-stu-id="c622e-271">1</span></span></td>
    <td><span data-ttu-id="c622e-272">11</span><span class="sxs-lookup"><span data-stu-id="c622e-272">11</span></span></td>
    <td><span data-ttu-id="c622e-273">10</span><span class="sxs-lookup"><span data-stu-id="c622e-273">10</span></span></td>
    <td><span data-ttu-id="c622e-274">916.67</span><span class="sxs-lookup"><span data-stu-id="c622e-274">916.67</span></span></td>
    <td><span data-ttu-id="c622e-275">14</span><span class="sxs-lookup"><span data-stu-id="c622e-275">14</span></span></td>
    <td><span data-ttu-id="c622e-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="c622e-276">1,283.33</span></span></td>
    <td><span data-ttu-id="c622e-277">91.67</span><span class="sxs-lookup"><span data-stu-id="c622e-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-278">5.00</span><span class="sxs-lookup"><span data-stu-id="c622e-278">5.00</span></span></td>
    <td><span data-ttu-id="c622e-279">458.33</span><span class="sxs-lookup"><span data-stu-id="c622e-279">458.33</span></span></td>
    <td><span data-ttu-id="c622e-280">5.00</span><span class="sxs-lookup"><span data-stu-id="c622e-280">5.00</span></span></td>
    <td><span data-ttu-id="c622e-281">458.33</span><span class="sxs-lookup"><span data-stu-id="c622e-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="c622e-282">1000</span><span class="sxs-lookup"><span data-stu-id="c622e-282">1000</span></span></td>
    <td><span data-ttu-id="c622e-283">1</span><span class="sxs-lookup"><span data-stu-id="c622e-283">1</span></span></td>
    <td><span data-ttu-id="c622e-284">12</span><span class="sxs-lookup"><span data-stu-id="c622e-284">12</span></span></td>
    <td><span data-ttu-id="c622e-285">4</span><span class="sxs-lookup"><span data-stu-id="c622e-285">4</span></span></td>
    <td><span data-ttu-id="c622e-286">366.67</span><span class="sxs-lookup"><span data-stu-id="c622e-286">366.67</span></span></td>
    <td><span data-ttu-id="c622e-287">14</span><span class="sxs-lookup"><span data-stu-id="c622e-287">14</span></span></td>
    <td><span data-ttu-id="c622e-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="c622e-288">1,283.33</span></span></td>
    <td><span data-ttu-id="c622e-289">91.67</span><span class="sxs-lookup"><span data-stu-id="c622e-289">91.67</span></span></td>
    <td><span data-ttu-id="c622e-290">4.00</span><span class="sxs-lookup"><span data-stu-id="c622e-290">4.00</span></span></td>
    <td><span data-ttu-id="c622e-291">366.67</span><span class="sxs-lookup"><span data-stu-id="c622e-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="c622e-292">1000</span><span class="sxs-lookup"><span data-stu-id="c622e-292">1000</span></span></td>
    <td><span data-ttu-id="c622e-293">2</span><span class="sxs-lookup"><span data-stu-id="c622e-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="c622e-294">10</span><span class="sxs-lookup"><span data-stu-id="c622e-294">10</span></span></td>
    <td><span data-ttu-id="c622e-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="c622e-295">2,000.00</span></span></td>
    <td><span data-ttu-id="c622e-296">10</span><span class="sxs-lookup"><span data-stu-id="c622e-296">10</span></span></td>
    <td><span data-ttu-id="c622e-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="c622e-297">2,000.00</span></span></td>
    <td><span data-ttu-id="c622e-298">200.00</span><span class="sxs-lookup"><span data-stu-id="c622e-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-299">10,00</span><span class="sxs-lookup"><span data-stu-id="c622e-299">10.00</span></span></td>
    <td><span data-ttu-id="c622e-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="c622e-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="c622e-301"><strong>1000 Razem</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="c622e-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="c622e-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="c622e-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="c622e-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="c622e-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="c622e-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="c622e-310">W tym momencie oddział 1 dzieli się na dwa wiersze, jeden dla magazynu 11 i drugi dla magazynu 12.</span><span class="sxs-lookup"><span data-stu-id="c622e-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="c622e-311">Jednak wartości **Ilość wartości zapasów**, **Wartość zapasów** oraz **Średnie koszty jednostkowe** są takie same, ponieważ **Magazyn** nie jest finansowym wymiarem magazynowym.</span><span class="sxs-lookup"><span data-stu-id="c622e-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="c622e-312">Ponadto należy zauważyć, że dystrybucja ilości oddziału 1 jest inna.</span><span class="sxs-lookup"><span data-stu-id="c622e-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="c622e-313">W pierwszym uruchomionym raporcie system zignorował zamówienie przeniesienia, które miało miejsce w tym samym oddziale, i odznaczył ilość na fakturze sprzedaży z przedziału czasu **31/3/2020-1/3/2020** w oddziale 1.</span><span class="sxs-lookup"><span data-stu-id="c622e-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="c622e-314">Jednak w nowym raporcie system odliczy ilość z faktury sprzedaży z przedziału czasu **8/5/2020-1/5/2020** w magazynie 12.</span><span class="sxs-lookup"><span data-stu-id="c622e-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="c622e-315">Skutki zamknięcia zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-315">Effects of inventory closing</span></span>

<span data-ttu-id="c622e-316">W przypadku uruchomienia operacji zamykania magazynu w systemie można ponownie uruchomić poprzedni raport, ale w polu **Na dzień** zostanie ustawiona wartość *31 maja 2020*, zostaną przedstawione następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="c622e-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="c622e-317">Wartości w polach **Wartość zapasów** i **Średni koszt jednostkowy** są aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="c622e-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="c622e-318">Wartość **Dostępna wartość** i wszystkie wartości **Kwota** w każdym przedziale okresu są odpowiednio aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="c622e-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="c622e-319">Nowy raport będzie przypominał następujący przykład.</span><span class="sxs-lookup"><span data-stu-id="c622e-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="c622e-320">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="c622e-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-321">Oddział</span><span class="sxs-lookup"><span data-stu-id="c622e-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-322">Magazyn</span><span class="sxs-lookup"><span data-stu-id="c622e-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-323">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-324">Dostępna wartość</span><span class="sxs-lookup"><span data-stu-id="c622e-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-325">Ilość wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-326">Wartość zapasów</span><span class="sxs-lookup"><span data-stu-id="c622e-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="c622e-327">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="c622e-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="c622e-328">31/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="c622e-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="c622e-329">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="c622e-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="c622e-330">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="c622e-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="c622e-331">P1:Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="c622e-332">P1:Kwota</span><span class="sxs-lookup"><span data-stu-id="c622e-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="c622e-333">P2:Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="c622e-334">P2:Kwota</span><span class="sxs-lookup"><span data-stu-id="c622e-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="c622e-335">P3:Ilość</span><span class="sxs-lookup"><span data-stu-id="c622e-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="c622e-336">P3:Kwota</span><span class="sxs-lookup"><span data-stu-id="c622e-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="c622e-337">1000</span><span class="sxs-lookup"><span data-stu-id="c622e-337">1000</span></span></td>
    <td><span data-ttu-id="c622e-338">1</span><span class="sxs-lookup"><span data-stu-id="c622e-338">1</span></span></td>
    <td><span data-ttu-id="c622e-339">11</span><span class="sxs-lookup"><span data-stu-id="c622e-339">11</span></span></td>
    <td><span data-ttu-id="c622e-340">10</span><span class="sxs-lookup"><span data-stu-id="c622e-340">10</span></span></td>
    <td><span data-ttu-id="c622e-341">910.70</span><span class="sxs-lookup"><span data-stu-id="c622e-341">910.70</span></span></td>
    <td><span data-ttu-id="c622e-342">14</span><span class="sxs-lookup"><span data-stu-id="c622e-342">14</span></span></td>
    <td><span data-ttu-id="c622e-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="c622e-343">1,275.00</span></span></td>
    <td><span data-ttu-id="c622e-344">91.07</span><span class="sxs-lookup"><span data-stu-id="c622e-344">91.07</span></span></td>
    <td><span data-ttu-id="c622e-345">0,00</span><span class="sxs-lookup"><span data-stu-id="c622e-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="c622e-346">5.00</span><span class="sxs-lookup"><span data-stu-id="c622e-346">5.00</span></span></td>
    <td><span data-ttu-id="c622e-347">455.36</span><span class="sxs-lookup"><span data-stu-id="c622e-347">455.36</span></span></td>
    <td><span data-ttu-id="c622e-348">5.00</span><span class="sxs-lookup"><span data-stu-id="c622e-348">5.00</span></span></td>
    <td><span data-ttu-id="c622e-349">455.36</span><span class="sxs-lookup"><span data-stu-id="c622e-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="c622e-350">1000</span><span class="sxs-lookup"><span data-stu-id="c622e-350">1000</span></span></td>
    <td><span data-ttu-id="c622e-351">1</span><span class="sxs-lookup"><span data-stu-id="c622e-351">1</span></span></td>
    <td><span data-ttu-id="c622e-352">12</span><span class="sxs-lookup"><span data-stu-id="c622e-352">12</span></span></td>
    <td><span data-ttu-id="c622e-353">4</span><span class="sxs-lookup"><span data-stu-id="c622e-353">4</span></span></td>
    <td><span data-ttu-id="c622e-354">364.29</span><span class="sxs-lookup"><span data-stu-id="c622e-354">364.29</span></span></td>
    <td><span data-ttu-id="c622e-355">14</span><span class="sxs-lookup"><span data-stu-id="c622e-355">14</span></span></td>
    <td><span data-ttu-id="c622e-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="c622e-356">1,275.00</span></span></td>
    <td><span data-ttu-id="c622e-357">91.07</span><span class="sxs-lookup"><span data-stu-id="c622e-357">91.07</span></span></td>
    <td><span data-ttu-id="c622e-358">4.00</span><span class="sxs-lookup"><span data-stu-id="c622e-358">4.00</span></span></td>
    <td><span data-ttu-id="c622e-359">364.29</span><span class="sxs-lookup"><span data-stu-id="c622e-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="c622e-360">1000</span><span class="sxs-lookup"><span data-stu-id="c622e-360">1000</span></span></td>
    <td><span data-ttu-id="c622e-361">2</span><span class="sxs-lookup"><span data-stu-id="c622e-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="c622e-362">10</span><span class="sxs-lookup"><span data-stu-id="c622e-362">10</span></span></td>
    <td><span data-ttu-id="c622e-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="c622e-363">2,000.00</span></span></td>
    <td><span data-ttu-id="c622e-364">10</span><span class="sxs-lookup"><span data-stu-id="c622e-364">10</span></span></td>
    <td><span data-ttu-id="c622e-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="c622e-365">2,000.00</span></span></td>
    <td><span data-ttu-id="c622e-366">200.00</span><span class="sxs-lookup"><span data-stu-id="c622e-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-367">10,00</span><span class="sxs-lookup"><span data-stu-id="c622e-367">10.00</span></span></td>
    <td><span data-ttu-id="c622e-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="c622e-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="c622e-369"><strong>1000 Razem</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="c622e-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="c622e-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="c622e-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="c622e-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="c622e-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="c622e-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="c622e-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="c622e-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]