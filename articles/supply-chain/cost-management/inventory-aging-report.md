---
title: Przykłady i logika raportu wiekowania zapasów
description: W tym temacie przedstawiono przykłady przedstawiające sposób interpretacji wyników raportu wiekowania zapasów.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435204"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="28bfd-103">Przykłady i logika raportu wiekowania zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28bfd-104">W tym temacie przedstawiono przykłady przedstawiające sposób interpretacji wyników raportu **Wiekowania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="28bfd-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="28bfd-105">Ten raport umożliwia kategoryzowanie dostępnych ilości i wartości zapasów dla wybranego towaru lub grupy towarów do kilku przedziałów okresów.</span><span class="sxs-lookup"><span data-stu-id="28bfd-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="28bfd-106">W tym temacie przedstawiono również wewnętrzną logikę raportu.</span><span class="sxs-lookup"><span data-stu-id="28bfd-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="28bfd-107">W przykładach w tym temacie przedstawiono wyniki prezentowane w standardowym raporcie **Wiekowania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="28bfd-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="28bfd-108">Zasadniczo zalecamy jednak korzystanie z wersji [raportu przechowywania raportu o starzeniu się zapasów](inventory-aging-report-storage.md), zwłaszcza gdy masz wiele produktów i magazynów, które muszą zostać przetworzone.</span><span class="sxs-lookup"><span data-stu-id="28bfd-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="28bfd-109">Przechowywanie raportów wiekowania zapasów powoduje zapisanie wszystkich generowanych raportów, wyświetlenie wyników w postaci strony interakcyjnej i wykresu oraz umożliwia wyeksportowanie dowolnego zapisanego raportu.</span><span class="sxs-lookup"><span data-stu-id="28bfd-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="28bfd-110">Przykładowe dane używane w tych przykładach</span><span class="sxs-lookup"><span data-stu-id="28bfd-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="28bfd-111">Przykłady przedstawione w tym temacie są oparte na przykładowych danych transakcji magazynowych opisanych w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="28bfd-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="28bfd-112">Konfiguracja wymiarów magazynowania</span><span class="sxs-lookup"><span data-stu-id="28bfd-112">Storage dimension setup</span></span>

<span data-ttu-id="28bfd-113">Przykładowy system zawiera następujące ustawienia wymiarów magazynowania:</span><span class="sxs-lookup"><span data-stu-id="28bfd-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="28bfd-114">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="28bfd-114">Name</span></span>      | <span data-ttu-id="28bfd-115">Aktywna</span><span class="sxs-lookup"><span data-stu-id="28bfd-115">Active</span></span> | <span data-ttu-id="28bfd-116">Magazyn</span><span class="sxs-lookup"><span data-stu-id="28bfd-116">Physical inventory</span></span> | <span data-ttu-id="28bfd-117">Magazyn finansowy</span><span class="sxs-lookup"><span data-stu-id="28bfd-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="28bfd-118">Oddział</span><span class="sxs-lookup"><span data-stu-id="28bfd-118">Site</span></span>      | <span data-ttu-id="28bfd-119">Tak</span><span class="sxs-lookup"><span data-stu-id="28bfd-119">Yes</span></span>    | <span data-ttu-id="28bfd-120">Tak</span><span class="sxs-lookup"><span data-stu-id="28bfd-120">Yes</span></span>                | <span data-ttu-id="28bfd-121">Tak</span><span class="sxs-lookup"><span data-stu-id="28bfd-121">Yes</span></span>                 |
| <span data-ttu-id="28bfd-122">Magazyn</span><span class="sxs-lookup"><span data-stu-id="28bfd-122">Warehouse</span></span> | <span data-ttu-id="28bfd-123">Tak</span><span class="sxs-lookup"><span data-stu-id="28bfd-123">Yes</span></span>    | <span data-ttu-id="28bfd-124">Tak</span><span class="sxs-lookup"><span data-stu-id="28bfd-124">Yes</span></span>                | <span data-ttu-id="28bfd-125">Nr</span><span class="sxs-lookup"><span data-stu-id="28bfd-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="28bfd-126">Model magazynu</span><span class="sxs-lookup"><span data-stu-id="28bfd-126">Inventory model</span></span>

<span data-ttu-id="28bfd-127">W przypadku systemu przykładowego model magazynu dla zwolnionych produktów to *FIFO*, a ustawienie **Koszt własny** dla modelu magazynu to *Włączanie wartości fizycznej*.</span><span class="sxs-lookup"><span data-stu-id="28bfd-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="28bfd-128">Transakcje zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-128">Inventory transactions</span></span>

<span data-ttu-id="28bfd-129">Przykładowy system zawiera następujące transakcje magazynowe dla zwolnionego produktu o numerze towaru *1000*.</span><span class="sxs-lookup"><span data-stu-id="28bfd-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="28bfd-130">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="28bfd-130">Reference</span></span>      | <span data-ttu-id="28bfd-131">Oddział</span><span class="sxs-lookup"><span data-stu-id="28bfd-131">Site</span></span> | <span data-ttu-id="28bfd-132">Magazyn</span><span class="sxs-lookup"><span data-stu-id="28bfd-132">Warehouse</span></span> | <span data-ttu-id="28bfd-133">Przychód</span><span class="sxs-lookup"><span data-stu-id="28bfd-133">Receipt</span></span>   | <span data-ttu-id="28bfd-134">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="28bfd-134">Issue</span></span> | <span data-ttu-id="28bfd-135">Data fizycznej transakcji</span><span class="sxs-lookup"><span data-stu-id="28bfd-135">Physical date</span></span> | <span data-ttu-id="28bfd-136">Data finansowa</span><span class="sxs-lookup"><span data-stu-id="28bfd-136">Financial date</span></span> | <span data-ttu-id="28bfd-137">Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-137">Quantity</span></span> | <span data-ttu-id="28bfd-138">Kwota kosztu</span><span class="sxs-lookup"><span data-stu-id="28bfd-138">Cost amount</span></span> | <span data-ttu-id="28bfd-139">Fizyczna wartość kosztu</span><span class="sxs-lookup"><span data-stu-id="28bfd-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="28bfd-140">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="28bfd-140">Purchase order</span></span> | <span data-ttu-id="28bfd-141">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-141">1</span></span>    | <span data-ttu-id="28bfd-142">11</span><span class="sxs-lookup"><span data-stu-id="28bfd-142">11</span></span>        | <span data-ttu-id="28bfd-143">Zakupione</span><span class="sxs-lookup"><span data-stu-id="28bfd-143">Purchased</span></span> |       | <span data-ttu-id="28bfd-144">15 marca</span><span class="sxs-lookup"><span data-stu-id="28bfd-144">March 15</span></span>      | <span data-ttu-id="28bfd-145">15 marca</span><span class="sxs-lookup"><span data-stu-id="28bfd-145">March 15</span></span>       | <span data-ttu-id="28bfd-146">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-146">10</span></span>       | <span data-ttu-id="28bfd-147">1 000</span><span class="sxs-lookup"><span data-stu-id="28bfd-147">1,000</span></span>       | <span data-ttu-id="28bfd-148">1 000</span><span class="sxs-lookup"><span data-stu-id="28bfd-148">1,000</span></span>                |
| <span data-ttu-id="28bfd-149">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="28bfd-149">Purchase order</span></span> | <span data-ttu-id="28bfd-150">2</span><span class="sxs-lookup"><span data-stu-id="28bfd-150">2</span></span>    | <span data-ttu-id="28bfd-151">21</span><span class="sxs-lookup"><span data-stu-id="28bfd-151">21</span></span>        | <span data-ttu-id="28bfd-152">Zakupione</span><span class="sxs-lookup"><span data-stu-id="28bfd-152">Purchased</span></span> |       | <span data-ttu-id="28bfd-153">15 marca</span><span class="sxs-lookup"><span data-stu-id="28bfd-153">March 15</span></span>      | <span data-ttu-id="28bfd-154">15 marca</span><span class="sxs-lookup"><span data-stu-id="28bfd-154">March 15</span></span>       | <span data-ttu-id="28bfd-155">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-155">10</span></span>       | <span data-ttu-id="28bfd-156">2,000</span><span class="sxs-lookup"><span data-stu-id="28bfd-156">2,000</span></span>       | <span data-ttu-id="28bfd-157">2,000</span><span class="sxs-lookup"><span data-stu-id="28bfd-157">2,000</span></span>                |
| <span data-ttu-id="28bfd-158">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="28bfd-158">Purchase order</span></span> | <span data-ttu-id="28bfd-159">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-159">1</span></span>    | <span data-ttu-id="28bfd-160">11</span><span class="sxs-lookup"><span data-stu-id="28bfd-160">11</span></span>        | <span data-ttu-id="28bfd-161">Odebrane</span><span class="sxs-lookup"><span data-stu-id="28bfd-161">Received</span></span>  |       | <span data-ttu-id="28bfd-162">15 kwietnia</span><span class="sxs-lookup"><span data-stu-id="28bfd-162">April 15</span></span>      |                | <span data-ttu-id="28bfd-163">5</span><span class="sxs-lookup"><span data-stu-id="28bfd-163">5</span></span>        |             | <span data-ttu-id="28bfd-164">375</span><span class="sxs-lookup"><span data-stu-id="28bfd-164">375</span></span>                  |
| <span data-ttu-id="28bfd-165">Zamówienie przeniesienia</span><span class="sxs-lookup"><span data-stu-id="28bfd-165">Transfer order</span></span> | <span data-ttu-id="28bfd-166">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-166">1</span></span>    | <span data-ttu-id="28bfd-167">11</span><span class="sxs-lookup"><span data-stu-id="28bfd-167">11</span></span>        |           | <span data-ttu-id="28bfd-168">Sprzedane</span><span class="sxs-lookup"><span data-stu-id="28bfd-168">Sold</span></span>  | <span data-ttu-id="28bfd-169">2 maja</span><span class="sxs-lookup"><span data-stu-id="28bfd-169">May 2</span></span>         | <span data-ttu-id="28bfd-170">2 maja</span><span class="sxs-lookup"><span data-stu-id="28bfd-170">May 2</span></span>          | <span data-ttu-id="28bfd-171">-5</span><span class="sxs-lookup"><span data-stu-id="28bfd-171">-5</span></span>       | <span data-ttu-id="28bfd-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="28bfd-172">-458.33</span></span>     | <span data-ttu-id="28bfd-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="28bfd-173">-458.33</span></span>              |
| <span data-ttu-id="28bfd-174">Zamówienie przeniesienia</span><span class="sxs-lookup"><span data-stu-id="28bfd-174">Transfer order</span></span> | <span data-ttu-id="28bfd-175">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-175">1</span></span>    | <span data-ttu-id="28bfd-176">12</span><span class="sxs-lookup"><span data-stu-id="28bfd-176">12</span></span>        | <span data-ttu-id="28bfd-177">Zakupione</span><span class="sxs-lookup"><span data-stu-id="28bfd-177">Purchased</span></span> |       | <span data-ttu-id="28bfd-178">2 maja</span><span class="sxs-lookup"><span data-stu-id="28bfd-178">May 2</span></span>         | <span data-ttu-id="28bfd-179">2 maja</span><span class="sxs-lookup"><span data-stu-id="28bfd-179">May 2</span></span>          | <span data-ttu-id="28bfd-180">5</span><span class="sxs-lookup"><span data-stu-id="28bfd-180">5</span></span>        | <span data-ttu-id="28bfd-181">458.33</span><span class="sxs-lookup"><span data-stu-id="28bfd-181">458.33</span></span>      | <span data-ttu-id="28bfd-182">458.33</span><span class="sxs-lookup"><span data-stu-id="28bfd-182">458.33</span></span>               |
| <span data-ttu-id="28bfd-183">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="28bfd-183">Sales order</span></span>    | <span data-ttu-id="28bfd-184">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-184">1</span></span>    | <span data-ttu-id="28bfd-185">12</span><span class="sxs-lookup"><span data-stu-id="28bfd-185">12</span></span>        |           | <span data-ttu-id="28bfd-186">Sprzedane</span><span class="sxs-lookup"><span data-stu-id="28bfd-186">Sold</span></span>  | <span data-ttu-id="28bfd-187">3 maja</span><span class="sxs-lookup"><span data-stu-id="28bfd-187">May 3</span></span>         | <span data-ttu-id="28bfd-188">3 maja</span><span class="sxs-lookup"><span data-stu-id="28bfd-188">May 3</span></span>          | <span data-ttu-id="28bfd-189">-1</span><span class="sxs-lookup"><span data-stu-id="28bfd-189">-1</span></span>       | <span data-ttu-id="28bfd-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="28bfd-190">-91.67</span></span>      | <span data-ttu-id="28bfd-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="28bfd-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="28bfd-192">Sposób obliczania ilości i kwot w każdym przedziale okresów</span><span class="sxs-lookup"><span data-stu-id="28bfd-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="28bfd-193">Korzystając z przykładowych danych opisanych w poprzednich sekcjach, można uruchomić raport **Wiekowania zapasów**, który ma następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="28bfd-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="28bfd-194">**Data:** *9 maj 2020*</span><span class="sxs-lookup"><span data-stu-id="28bfd-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="28bfd-195">**Oddział:** *Widok*</span><span class="sxs-lookup"><span data-stu-id="28bfd-195">**Site:** *View*</span></span>
- <span data-ttu-id="28bfd-196">**Magazyn:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="28bfd-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="28bfd-197">**Kod pozycji:** *Razem*</span><span class="sxs-lookup"><span data-stu-id="28bfd-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="28bfd-198">**Okres wiekowania:** należy uzupełnić to pole, aby były generowane pakiety miesięczne.</span><span class="sxs-lookup"><span data-stu-id="28bfd-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="28bfd-199">W takim przypadku zawartość generowanego raportu będzie podobna do poniższego przykładu.</span><span class="sxs-lookup"><span data-stu-id="28bfd-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="28bfd-200">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="28bfd-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-201">Oddział</span><span class="sxs-lookup"><span data-stu-id="28bfd-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-202">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-203">Dostępna wartość</span><span class="sxs-lookup"><span data-stu-id="28bfd-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-204">Ilość wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-205">Wartość zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-206">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="28bfd-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="28bfd-207">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="28bfd-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="28bfd-208">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="28bfd-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="28bfd-209">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="28bfd-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="28bfd-210">P1:Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="28bfd-211">P1:Kwota</span><span class="sxs-lookup"><span data-stu-id="28bfd-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="28bfd-212">P2:Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="28bfd-213">P2:Kwota</span><span class="sxs-lookup"><span data-stu-id="28bfd-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="28bfd-214">P3:Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="28bfd-215">P3:Kwota</span><span class="sxs-lookup"><span data-stu-id="28bfd-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="28bfd-216">1000</span><span class="sxs-lookup"><span data-stu-id="28bfd-216">1000</span></span></td>
    <td><span data-ttu-id="28bfd-217">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-217">1</span></span></td>
    <td><span data-ttu-id="28bfd-218">14</span><span class="sxs-lookup"><span data-stu-id="28bfd-218">14</span></span></td>
    <td><span data-ttu-id="28bfd-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="28bfd-219">1,283.33</span></span></td>
    <td><span data-ttu-id="28bfd-220">14</span><span class="sxs-lookup"><span data-stu-id="28bfd-220">14</span></span></td>
    <td><span data-ttu-id="28bfd-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="28bfd-221">1,283.33</span></span></td>
    <td><span data-ttu-id="28bfd-222">91.67</span><span class="sxs-lookup"><span data-stu-id="28bfd-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-223">5.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-223">5.00</span></span></td>
    <td><span data-ttu-id="28bfd-224">458.33</span><span class="sxs-lookup"><span data-stu-id="28bfd-224">458.33</span></span></td>
    <td><span data-ttu-id="28bfd-225">9.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-225">9.00</span></span></td>
    <td><span data-ttu-id="28bfd-226">825.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="28bfd-227">1000</span><span class="sxs-lookup"><span data-stu-id="28bfd-227">1000</span></span></td>
    <td><span data-ttu-id="28bfd-228">2</span><span class="sxs-lookup"><span data-stu-id="28bfd-228">2</span></span></td>
    <td><span data-ttu-id="28bfd-229">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-229">10</span></span></td>
    <td><span data-ttu-id="28bfd-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-230">2,000.00</span></span></td>
    <td><span data-ttu-id="28bfd-231">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-231">10</span></span></td>
    <td><span data-ttu-id="28bfd-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-232">2,000.00</span></span></td>
    <td><span data-ttu-id="28bfd-233">200.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-234">10,00</span><span class="sxs-lookup"><span data-stu-id="28bfd-234">10.00</span></span></td>
    <td><span data-ttu-id="28bfd-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="28bfd-236"><strong>1000 Razem</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="28bfd-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="28bfd-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="28bfd-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="28bfd-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="28bfd-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="28bfd-243">W tym przykładzie przedstawiono następujące szczegóły:</span><span class="sxs-lookup"><span data-stu-id="28bfd-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="28bfd-244">Wartości **Ilość wartości zapasów**, **Wartość zapasów** oraz **Średnie koszty jednostkowe**, które są wyświetlane w raporcie, są wartościami dla wymiaru magazynu finansowego (w tym przypadku **Oddział**).</span><span class="sxs-lookup"><span data-stu-id="28bfd-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="28bfd-245">Na przykład w przypadku oddziału 1 raport zawiera następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="28bfd-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="28bfd-246">Wartość **Ilość wartości zapasów** wynosi *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="28bfd-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="28bfd-247">Wartość **Wartość zapasów** wynosi *1283,33* (= 1000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="28bfd-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="28bfd-248">Wartość **Średni koszt jednostkowy** wynosi *91,67*.</span><span class="sxs-lookup"><span data-stu-id="28bfd-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="28bfd-249">Wartość **Dostępna wartość** oraz wartość **Kwota** w każdym przedziale okresu są obliczane przy użyciu wartości **Średni koszt jednostkowy**.</span><span class="sxs-lookup"><span data-stu-id="28bfd-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="28bfd-250">Raport określa ilość zapasów dla każdego przedziału okresu, sumując łączną ilość zapasów dla każdego przedziału okresu.</span><span class="sxs-lookup"><span data-stu-id="28bfd-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="28bfd-251">Następnie stosuje regułę FIFO (First on) do odliczenia łącznej wydanej ilości, niezależnie od modelu magazynu, który jest używany przez towary.</span><span class="sxs-lookup"><span data-stu-id="28bfd-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="28bfd-252">Jeśli ten sam raport zostanie uruchomiony ponownie, ale tym razem ustaw pole **Oddział** i **Magazyn** na *Wyświetlanie*, nowy raport będzie wyglądał następująco.</span><span class="sxs-lookup"><span data-stu-id="28bfd-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="28bfd-253">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="28bfd-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-254">Oddział</span><span class="sxs-lookup"><span data-stu-id="28bfd-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-255">Magazyn</span><span class="sxs-lookup"><span data-stu-id="28bfd-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-256">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-257">Dostępna wartość</span><span class="sxs-lookup"><span data-stu-id="28bfd-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-258">Ilość wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-259">Wartość zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-260">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="28bfd-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="28bfd-261">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="28bfd-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="28bfd-262">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="28bfd-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="28bfd-263">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="28bfd-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="28bfd-264">P1:Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="28bfd-265">P1:Kwota</span><span class="sxs-lookup"><span data-stu-id="28bfd-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="28bfd-266">P2:Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="28bfd-267">P2:Kwota</span><span class="sxs-lookup"><span data-stu-id="28bfd-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="28bfd-268">P3:Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="28bfd-269">P3:Kwota</span><span class="sxs-lookup"><span data-stu-id="28bfd-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="28bfd-270">1000</span><span class="sxs-lookup"><span data-stu-id="28bfd-270">1000</span></span></td>
    <td><span data-ttu-id="28bfd-271">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-271">1</span></span></td>
    <td><span data-ttu-id="28bfd-272">11</span><span class="sxs-lookup"><span data-stu-id="28bfd-272">11</span></span></td>
    <td><span data-ttu-id="28bfd-273">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-273">10</span></span></td>
    <td><span data-ttu-id="28bfd-274">916.67</span><span class="sxs-lookup"><span data-stu-id="28bfd-274">916.67</span></span></td>
    <td><span data-ttu-id="28bfd-275">14</span><span class="sxs-lookup"><span data-stu-id="28bfd-275">14</span></span></td>
    <td><span data-ttu-id="28bfd-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="28bfd-276">1,283.33</span></span></td>
    <td><span data-ttu-id="28bfd-277">91.67</span><span class="sxs-lookup"><span data-stu-id="28bfd-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-278">5.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-278">5.00</span></span></td>
    <td><span data-ttu-id="28bfd-279">458.33</span><span class="sxs-lookup"><span data-stu-id="28bfd-279">458.33</span></span></td>
    <td><span data-ttu-id="28bfd-280">5.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-280">5.00</span></span></td>
    <td><span data-ttu-id="28bfd-281">458.33</span><span class="sxs-lookup"><span data-stu-id="28bfd-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="28bfd-282">1000</span><span class="sxs-lookup"><span data-stu-id="28bfd-282">1000</span></span></td>
    <td><span data-ttu-id="28bfd-283">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-283">1</span></span></td>
    <td><span data-ttu-id="28bfd-284">12</span><span class="sxs-lookup"><span data-stu-id="28bfd-284">12</span></span></td>
    <td><span data-ttu-id="28bfd-285">4</span><span class="sxs-lookup"><span data-stu-id="28bfd-285">4</span></span></td>
    <td><span data-ttu-id="28bfd-286">366.67</span><span class="sxs-lookup"><span data-stu-id="28bfd-286">366.67</span></span></td>
    <td><span data-ttu-id="28bfd-287">14</span><span class="sxs-lookup"><span data-stu-id="28bfd-287">14</span></span></td>
    <td><span data-ttu-id="28bfd-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="28bfd-288">1,283.33</span></span></td>
    <td><span data-ttu-id="28bfd-289">91.67</span><span class="sxs-lookup"><span data-stu-id="28bfd-289">91.67</span></span></td>
    <td><span data-ttu-id="28bfd-290">4.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-290">4.00</span></span></td>
    <td><span data-ttu-id="28bfd-291">366.67</span><span class="sxs-lookup"><span data-stu-id="28bfd-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="28bfd-292">1000</span><span class="sxs-lookup"><span data-stu-id="28bfd-292">1000</span></span></td>
    <td><span data-ttu-id="28bfd-293">2</span><span class="sxs-lookup"><span data-stu-id="28bfd-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="28bfd-294">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-294">10</span></span></td>
    <td><span data-ttu-id="28bfd-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-295">2,000.00</span></span></td>
    <td><span data-ttu-id="28bfd-296">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-296">10</span></span></td>
    <td><span data-ttu-id="28bfd-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-297">2,000.00</span></span></td>
    <td><span data-ttu-id="28bfd-298">200.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-299">10,00</span><span class="sxs-lookup"><span data-stu-id="28bfd-299">10.00</span></span></td>
    <td><span data-ttu-id="28bfd-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="28bfd-301"><strong>1000 Razem</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="28bfd-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="28bfd-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="28bfd-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="28bfd-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="28bfd-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="28bfd-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="28bfd-310">W tym momencie oddział 1 dzieli się na dwa wiersze, jeden dla magazynu 11 i drugi dla magazynu 12.</span><span class="sxs-lookup"><span data-stu-id="28bfd-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="28bfd-311">Jednak wartości **Ilość wartości zapasów**, **Wartość zapasów** oraz **Średnie koszty jednostkowe** są takie same, ponieważ **Magazyn** nie jest finansowym wymiarem magazynowym.</span><span class="sxs-lookup"><span data-stu-id="28bfd-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="28bfd-312">Ponadto należy zauważyć, że dystrybucja ilości oddziału 1 jest inna.</span><span class="sxs-lookup"><span data-stu-id="28bfd-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="28bfd-313">W pierwszym uruchomionym raporcie system zignorował zamówienie przeniesienia, które miało miejsce w tym samym oddziale, i odznaczył ilość na fakturze sprzedaży z przedziału czasu **31/3/2020-1/3/2020** w oddziale 1.</span><span class="sxs-lookup"><span data-stu-id="28bfd-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="28bfd-314">Jednak w nowym raporcie system odliczy ilość z faktury sprzedaży z przedziału czasu **8/5/2020-1/5/2020** w magazynie 12.</span><span class="sxs-lookup"><span data-stu-id="28bfd-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="28bfd-315">Skutki zamknięcia zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-315">Effects of inventory closing</span></span>

<span data-ttu-id="28bfd-316">W przypadku uruchomienia operacji zamykania magazynu w systemie można ponownie uruchomić poprzedni raport, ale w polu **Na dzień** zostanie ustawiona wartość *31 maja 2020*, zostaną przedstawione następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="28bfd-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="28bfd-317">Wartości w polach **Wartość zapasów** i **Średni koszt jednostkowy** są aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="28bfd-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="28bfd-318">Wartość **Dostępna wartość** i wszystkie wartości **Kwota** w każdym przedziale okresu są odpowiednio aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="28bfd-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="28bfd-319">Nowy raport będzie przypominał następujący przykład.</span><span class="sxs-lookup"><span data-stu-id="28bfd-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="28bfd-320">Identyfikator pozycji</span><span class="sxs-lookup"><span data-stu-id="28bfd-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-321">Oddział</span><span class="sxs-lookup"><span data-stu-id="28bfd-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-322">Magazyn</span><span class="sxs-lookup"><span data-stu-id="28bfd-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-323">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-324">Dostępna wartość</span><span class="sxs-lookup"><span data-stu-id="28bfd-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-325">Ilość wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-326">Wartość zapasów</span><span class="sxs-lookup"><span data-stu-id="28bfd-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="28bfd-327">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="28bfd-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="28bfd-328">31/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="28bfd-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="28bfd-329">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="28bfd-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="28bfd-330">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="28bfd-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="28bfd-331">P1:Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="28bfd-332">P1:Kwota</span><span class="sxs-lookup"><span data-stu-id="28bfd-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="28bfd-333">P2:Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="28bfd-334">P2:Kwota</span><span class="sxs-lookup"><span data-stu-id="28bfd-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="28bfd-335">P3:Ilość</span><span class="sxs-lookup"><span data-stu-id="28bfd-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="28bfd-336">P3:Kwota</span><span class="sxs-lookup"><span data-stu-id="28bfd-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="28bfd-337">1000</span><span class="sxs-lookup"><span data-stu-id="28bfd-337">1000</span></span></td>
    <td><span data-ttu-id="28bfd-338">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-338">1</span></span></td>
    <td><span data-ttu-id="28bfd-339">11</span><span class="sxs-lookup"><span data-stu-id="28bfd-339">11</span></span></td>
    <td><span data-ttu-id="28bfd-340">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-340">10</span></span></td>
    <td><span data-ttu-id="28bfd-341">910.70</span><span class="sxs-lookup"><span data-stu-id="28bfd-341">910.70</span></span></td>
    <td><span data-ttu-id="28bfd-342">14</span><span class="sxs-lookup"><span data-stu-id="28bfd-342">14</span></span></td>
    <td><span data-ttu-id="28bfd-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-343">1,275.00</span></span></td>
    <td><span data-ttu-id="28bfd-344">91.07</span><span class="sxs-lookup"><span data-stu-id="28bfd-344">91.07</span></span></td>
    <td><span data-ttu-id="28bfd-345">0,00</span><span class="sxs-lookup"><span data-stu-id="28bfd-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="28bfd-346">5.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-346">5.00</span></span></td>
    <td><span data-ttu-id="28bfd-347">455.36</span><span class="sxs-lookup"><span data-stu-id="28bfd-347">455.36</span></span></td>
    <td><span data-ttu-id="28bfd-348">5.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-348">5.00</span></span></td>
    <td><span data-ttu-id="28bfd-349">455.36</span><span class="sxs-lookup"><span data-stu-id="28bfd-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="28bfd-350">1000</span><span class="sxs-lookup"><span data-stu-id="28bfd-350">1000</span></span></td>
    <td><span data-ttu-id="28bfd-351">1</span><span class="sxs-lookup"><span data-stu-id="28bfd-351">1</span></span></td>
    <td><span data-ttu-id="28bfd-352">12</span><span class="sxs-lookup"><span data-stu-id="28bfd-352">12</span></span></td>
    <td><span data-ttu-id="28bfd-353">4</span><span class="sxs-lookup"><span data-stu-id="28bfd-353">4</span></span></td>
    <td><span data-ttu-id="28bfd-354">364.29</span><span class="sxs-lookup"><span data-stu-id="28bfd-354">364.29</span></span></td>
    <td><span data-ttu-id="28bfd-355">14</span><span class="sxs-lookup"><span data-stu-id="28bfd-355">14</span></span></td>
    <td><span data-ttu-id="28bfd-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-356">1,275.00</span></span></td>
    <td><span data-ttu-id="28bfd-357">91.07</span><span class="sxs-lookup"><span data-stu-id="28bfd-357">91.07</span></span></td>
    <td><span data-ttu-id="28bfd-358">4.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-358">4.00</span></span></td>
    <td><span data-ttu-id="28bfd-359">364.29</span><span class="sxs-lookup"><span data-stu-id="28bfd-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="28bfd-360">1000</span><span class="sxs-lookup"><span data-stu-id="28bfd-360">1000</span></span></td>
    <td><span data-ttu-id="28bfd-361">2</span><span class="sxs-lookup"><span data-stu-id="28bfd-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="28bfd-362">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-362">10</span></span></td>
    <td><span data-ttu-id="28bfd-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-363">2,000.00</span></span></td>
    <td><span data-ttu-id="28bfd-364">10</span><span class="sxs-lookup"><span data-stu-id="28bfd-364">10</span></span></td>
    <td><span data-ttu-id="28bfd-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-365">2,000.00</span></span></td>
    <td><span data-ttu-id="28bfd-366">200.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-367">10,00</span><span class="sxs-lookup"><span data-stu-id="28bfd-367">10.00</span></span></td>
    <td><span data-ttu-id="28bfd-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="28bfd-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="28bfd-369"><strong>1000 Razem</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="28bfd-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="28bfd-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="28bfd-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="28bfd-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="28bfd-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="28bfd-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="28bfd-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="28bfd-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
