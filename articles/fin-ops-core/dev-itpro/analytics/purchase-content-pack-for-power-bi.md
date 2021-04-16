---
title: Pakiet zawartości usługi Power BI Analiza wydatków zakupowych
description: W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Analiza wydatków zakupowych.
author: FrankDahl
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f9741b5f30f5e62b9e80000953113377fe016253
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749376"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="aee2b-103">Pakiet zawartości usługi Power BI Analiza wydatków zakupowych</span><span class="sxs-lookup"><span data-stu-id="aee2b-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aee2b-104">W tym temacie opisano, co się znajduje w pakiecie zawartości **Analiza wydatków zakupowych** usługi Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="aee2b-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="aee2b-105">Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.</span><span class="sxs-lookup"><span data-stu-id="aee2b-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="aee2b-106">Przegląd</span><span class="sxs-lookup"><span data-stu-id="aee2b-106">Overview</span></span>

<span data-ttu-id="aee2b-107">Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** został zaprojektowany, aby pomóc kierownikom ds. zakupów i menedżerom odpowiedzialnym za budżety monitorować wydatki zakupowe.</span><span class="sxs-lookup"><span data-stu-id="aee2b-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="aee2b-108">Menedżerowie mogą analizować wydatki zakupowe w następujące sposoby:</span><span class="sxs-lookup"><span data-stu-id="aee2b-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="aee2b-109">Zakupy od początku roku (według grupy dostawców i indywidualnych dostawców, kategorii zaopatrzenia, poszczególnych produktów i lokalizacji dostawców)</span><span class="sxs-lookup"><span data-stu-id="aee2b-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="aee2b-110">Zmiany wydatków zakupowych rok do roku (według grup dostawców i kategorii zaopatrzenia)</span><span class="sxs-lookup"><span data-stu-id="aee2b-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="aee2b-111">Pakiet zawartości wykorzystuje dane transakcyjne zakupów i przedstawia zarówno zagregowany widok danych zakupowych w całej firmie, jak i podział wydatków zakupowych na dostawców i produkty.</span><span class="sxs-lookup"><span data-stu-id="aee2b-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="aee2b-112">Raporty eksponują zmiany wydatków zakupowych w horyzoncie czasowym.</span><span class="sxs-lookup"><span data-stu-id="aee2b-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="aee2b-113">W związku z tym raporty mogą służyć do ostrzegania menedżerów o pozytywnych i negatywnych trendach wydatków dla poszczególnych dostawców i produktów.</span><span class="sxs-lookup"><span data-stu-id="aee2b-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="aee2b-114">Dodatkowo wykresy pokazują wydatki zakupowe dla różnych kategorii zaopatrzenia i grup dostawców.</span><span class="sxs-lookup"><span data-stu-id="aee2b-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="aee2b-115">W związku z tym menedżerowie kategorii i kierownicy regionalni mogą używać tych wykresów do identyfikowania zmian w zachowaniach wydatkowych.</span><span class="sxs-lookup"><span data-stu-id="aee2b-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="aee2b-116">Przechodzenie do pakietu zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="aee2b-116">Accessing the Power BI content</span></span>
<span data-ttu-id="aee2b-117">Pakiet zawartości usługi Power BI **Analiza wydatków związanych z zakupami** jest wyświetlany na stronie **Analiza wydatków i zakupów** (**Zaopatrzenie i sourcing** \> **Zapytania i raporty** \> **Analiza wydajności zakupów** \> **Analiza wydatków i zakupów**).</span><span class="sxs-lookup"><span data-stu-id="aee2b-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="aee2b-118">Wskaźniki umieszczone w pakiecie zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="aee2b-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="aee2b-119">Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** obejmuje raport zawierający zestaw wskaźników.</span><span class="sxs-lookup"><span data-stu-id="aee2b-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="aee2b-120">Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele.</span><span class="sxs-lookup"><span data-stu-id="aee2b-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="aee2b-121">Następująca sekcja zawiera przegląd dostępnych wizualizacji.</span><span class="sxs-lookup"><span data-stu-id="aee2b-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="aee2b-122">Strona raportu o zakupach wg dostawcy</span><span class="sxs-lookup"><span data-stu-id="aee2b-122">Purchase by vendor report page</span></span>
<span data-ttu-id="aee2b-123">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="aee2b-123">**Charts**</span></span>
- <span data-ttu-id="aee2b-124">10 najważniejszych dostawców wg wartości zakupów (wykres skumulowany słupkowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="aee2b-125">Łączne zakupy wg grupy dostawców/kraju/nazwy (wykres kołowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="aee2b-126">Zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="aee2b-127">Średnie zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="aee2b-128">**Kafelki**</span><span class="sxs-lookup"><span data-stu-id="aee2b-128">**Tiles**</span></span>
- <span data-ttu-id="aee2b-129">Suma zakupów</span><span class="sxs-lookup"><span data-stu-id="aee2b-129">Total purchase</span></span>
- <span data-ttu-id="aee2b-130">Wzrost zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="aee2b-130">YOY purchase growth</span></span>
- <span data-ttu-id="aee2b-131">Łączna liczba dostawców</span><span class="sxs-lookup"><span data-stu-id="aee2b-131">Total # vendors</span></span>
- <span data-ttu-id="aee2b-132">Łączna liczba aktywnych dostawców</span><span class="sxs-lookup"><span data-stu-id="aee2b-132">Total # of active vendors</span></span>

<span data-ttu-id="aee2b-133">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="aee2b-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="aee2b-134">Strona raportu o produktach wg dostawcy</span><span class="sxs-lookup"><span data-stu-id="aee2b-134">Purchase by product report page</span></span>

<span data-ttu-id="aee2b-135">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="aee2b-135">**Charts**</span></span>
- <span data-ttu-id="aee2b-136">Zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="aee2b-137">Łączne zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kołowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="aee2b-138">10 najważniejszych produktów wg wartości zakupów (wykres skumulowany słupkowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="aee2b-139">**Kafelki**</span><span class="sxs-lookup"><span data-stu-id="aee2b-139">**Tiles**</span></span>
- <span data-ttu-id="aee2b-140">Łączna liczba produktów</span><span class="sxs-lookup"><span data-stu-id="aee2b-140">Total # of products</span></span></li>
- <span data-ttu-id="aee2b-141">Procent aktywnych produktów w łącznej liczbie produktów</span><span class="sxs-lookup"><span data-stu-id="aee2b-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="aee2b-142">Liczba produktów odpowiedzialnych za 80% zakupów</span><span class="sxs-lookup"><span data-stu-id="aee2b-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="aee2b-143">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="aee2b-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="aee2b-144">Strona raportu o okresie wg dostawcy</span><span class="sxs-lookup"><span data-stu-id="aee2b-144">Purchase by period report page</span></span>
<span data-ttu-id="aee2b-145">Ta strona pokazuje zakupy w tym i ubiegłym roku oraz wzrost według kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="aee2b-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="aee2b-146">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="aee2b-146">**Charts**</span></span> 
- <span data-ttu-id="aee2b-147">Zakupy wg miesiąca/dnia (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="aee2b-148">Odchylenie łącznych zakupów r/r (wykres kaskadowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="aee2b-149">Wzrost łącznych zakupów r/r (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="aee2b-150">Zestawienie zaopatrzenia (macierz)</span><span class="sxs-lookup"><span data-stu-id="aee2b-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="aee2b-151">**Kafelki**</span><span class="sxs-lookup"><span data-stu-id="aee2b-151">**Tiles**</span></span>
- <span data-ttu-id="aee2b-152">Wzrost zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="aee2b-152">YOY purchase growth</span></span>
- <span data-ttu-id="aee2b-153">% wzrostu zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="aee2b-153">YOY purchase growth %</span></span>

<span data-ttu-id="aee2b-154">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="aee2b-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="aee2b-155">Strona raportu o zakupach wg lokalizacji dostawcy</span><span class="sxs-lookup"><span data-stu-id="aee2b-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="aee2b-156">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="aee2b-156">**Charts**</span></span>
- <span data-ttu-id="aee2b-157">Zakupy wg miejscowości</span><span class="sxs-lookup"><span data-stu-id="aee2b-157">Purchase by city</span></span>
- <span data-ttu-id="aee2b-158">% wzrostu zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="aee2b-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="aee2b-159">Zakupy wg krajów</span><span class="sxs-lookup"><span data-stu-id="aee2b-159">Purchase by country</span></span>

<span data-ttu-id="aee2b-160">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="aee2b-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="aee2b-161">Analiza wydatków zakupowych wg strony raportu</span><span class="sxs-lookup"><span data-stu-id="aee2b-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="aee2b-162">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="aee2b-162">**Charts**</span></span> 
- <span data-ttu-id="aee2b-163">Zakupy w bieżącym roku wg miesiąca/dnia (wykres liniowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="aee2b-164">Zakupy w bieżącym i ubiegłym roku (wykres liniowy i kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="aee2b-165">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="aee2b-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="aee2b-166">Analiza wydatków zakupowych wg strony raportu dot. dostawcy</span><span class="sxs-lookup"><span data-stu-id="aee2b-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="aee2b-167">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="aee2b-167">**Charts**</span></span> 
- <span data-ttu-id="aee2b-168">% udziału 10 najważniejszych dostawców w zakupach (wykres lejkowy)</span><span class="sxs-lookup"><span data-stu-id="aee2b-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="aee2b-169">10 dostawców z największym wzrostem wydatków r/r</span><span class="sxs-lookup"><span data-stu-id="aee2b-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="aee2b-170">10 dostawców z największym spadkiem wydatków r/r</span><span class="sxs-lookup"><span data-stu-id="aee2b-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="aee2b-171">**Przykład** 
</span><span class="sxs-lookup"><span data-stu-id="aee2b-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="aee2b-172">Model i jednostki danych</span><span class="sxs-lookup"><span data-stu-id="aee2b-172">Data model and entities</span></span>
<span data-ttu-id="aee2b-173">Następujące dane są używane do wypełniania stron raportów w pakiecie zawartości **Analiza wydatków zakupowych** dla usługi Power BI.</span><span class="sxs-lookup"><span data-stu-id="aee2b-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="aee2b-174">Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek.</span><span class="sxs-lookup"><span data-stu-id="aee2b-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="aee2b-175">Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz.</span><span class="sxs-lookup"><span data-stu-id="aee2b-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="aee2b-176">Aby uzyskać więcej informacji, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="aee2b-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="aee2b-177">Zagregowane miary w tym pakiecie zawartości są podzbiorem zagregowanych miar, które były dostępne w module Zakupy w programach Microsoft Dynamics AX 2012 i Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="aee2b-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="aee2b-178">Aby zagregowane miary modułu można było umieścić w magazynie jednostek, trzeba ustawić te miary jako wdrażalne.</span><span class="sxs-lookup"><span data-stu-id="aee2b-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="aee2b-179">Aby uzyskać więcej informacji, zobacz procedurę umieszczania zagregowanych miar w magazynie jednostek w temacie [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="aee2b-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="aee2b-180">Następujące najważniejsze zagregowane miary są dostępne bezpośrednio w jednostce Wiersze faktury i używane jako podstawa w pakiecie zawartości:</span><span class="sxs-lookup"><span data-stu-id="aee2b-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="aee2b-181">Jednostka</span><span class="sxs-lookup"><span data-stu-id="aee2b-181">Entity</span></span>        | <span data-ttu-id="aee2b-182">Najważniejsze zagregowane miary</span><span class="sxs-lookup"><span data-stu-id="aee2b-182">Key aggregate measurements</span></span> | <span data-ttu-id="aee2b-183">Źródło danych</span><span class="sxs-lookup"><span data-stu-id="aee2b-183">Data source</span></span>                                 | <span data-ttu-id="aee2b-184">Pole</span><span class="sxs-lookup"><span data-stu-id="aee2b-184">Field</span></span>              | <span data-ttu-id="aee2b-185">opis</span><span class="sxs-lookup"><span data-stu-id="aee2b-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="aee2b-186">Wiersze faktury</span><span class="sxs-lookup"><span data-stu-id="aee2b-186">Invoice lines</span></span> | <span data-ttu-id="aee2b-187">Zakup</span><span class="sxs-lookup"><span data-stu-id="aee2b-187">Purchase</span></span>                   | <span data-ttu-id="aee2b-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="aee2b-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="aee2b-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="aee2b-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="aee2b-190">Kwota w walucie rozliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="aee2b-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="aee2b-191">W poniższej tabeli przedstawiono najważniejsze miary w pakiecie zawartości, które są obliczane na podstawie jednostki Wiersze faktury.</span><span class="sxs-lookup"><span data-stu-id="aee2b-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="aee2b-192">Pomiar</span><span class="sxs-lookup"><span data-stu-id="aee2b-192">Measure</span></span>               | <span data-ttu-id="aee2b-193">Obliczenie</span><span class="sxs-lookup"><span data-stu-id="aee2b-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="aee2b-194">Zakupy w bieżącym roku</span><span class="sxs-lookup"><span data-stu-id="aee2b-194">Purchase current year</span></span> | <span data-ttu-id="aee2b-195">Zakupy w bieżącym roku = SUM('Wiersze faktury'\[Zakupy\])</span><span class="sxs-lookup"><span data-stu-id="aee2b-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="aee2b-196">Zakupy w ubiegłym roku</span><span class="sxs-lookup"><span data-stu-id="aee2b-196">Purchase last year</span></span>    | <span data-ttu-id="aee2b-197">Zakupy w ubiegłym roku = CALCULATE(SUM('Wiersze faktury'\[Zakupy\]), SAMEPERIODLASTYEAR(Daty\[Data\]))</span><span class="sxs-lookup"><span data-stu-id="aee2b-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="aee2b-198">Wzrost zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="aee2b-198">YOY purchase growth</span></span>   | <span data-ttu-id="aee2b-199">Wzrost zakupów r/r = \[Zakupy w bieżącym roku\] – \[Zakupy w ubiegłym roku\]</span><span class="sxs-lookup"><span data-stu-id="aee2b-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="aee2b-200">Następujące najważniejsze wymiary w pakiecie zawartości są używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i lepszego wglądu analitycznego.</span><span class="sxs-lookup"><span data-stu-id="aee2b-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="aee2b-201">Jednostka</span><span class="sxs-lookup"><span data-stu-id="aee2b-201">Entity</span></span>                 | <span data-ttu-id="aee2b-202">Przykłady atrybutów</span><span class="sxs-lookup"><span data-stu-id="aee2b-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="aee2b-203">Dostawcy</span><span class="sxs-lookup"><span data-stu-id="aee2b-203">Vendors</span></span>                | <span data-ttu-id="aee2b-204">Grupa dostawców, Kraj/region dostawcy, Nazwa dostawcy</span><span class="sxs-lookup"><span data-stu-id="aee2b-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="aee2b-205">Produkty</span><span class="sxs-lookup"><span data-stu-id="aee2b-205">Products</span></span>               | <span data-ttu-id="aee2b-206">Numer produktu, Nazwa produktu, Nazwa grupy pozycji</span><span class="sxs-lookup"><span data-stu-id="aee2b-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="aee2b-207">Kategorie zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="aee2b-207">Procurement categories</span></span> | <span data-ttu-id="aee2b-208">Kategoria zaopatrzenia, Nazwa kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="aee2b-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="aee2b-209">Firmy</span><span class="sxs-lookup"><span data-stu-id="aee2b-209">Legal entities</span></span>         | <span data-ttu-id="aee2b-210">Nazwa firmy</span><span class="sxs-lookup"><span data-stu-id="aee2b-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="aee2b-211">Daty</span><span class="sxs-lookup"><span data-stu-id="aee2b-211">Dates</span></span>                  | <span data-ttu-id="aee2b-212">Daty, Przesunięcie roku</span><span class="sxs-lookup"><span data-stu-id="aee2b-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="aee2b-213">Domyślnie pakiet zawartości przestawia dane bieżącego roku kalendarzowego.</span><span class="sxs-lookup"><span data-stu-id="aee2b-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="aee2b-214">Można jednak zmienić wartość filtra dat w sekcji filtrów raportu.</span><span class="sxs-lookup"><span data-stu-id="aee2b-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="aee2b-215">Można również zmienić wartość filtra firm.</span><span class="sxs-lookup"><span data-stu-id="aee2b-215">You can also change the company filter.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]