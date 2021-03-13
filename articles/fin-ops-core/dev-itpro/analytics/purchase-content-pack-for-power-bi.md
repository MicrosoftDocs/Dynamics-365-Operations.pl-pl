---
title: Pakiet zawartości usługi Power BI Analiza wydatków zakupowych
description: W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Analiza wydatków zakupowych.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 5914abaafab509e278d7a85441928feddb0b5164
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093449"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="dfe7e-103">Pakiet zawartości usługi Power BI Analiza wydatków zakupowych</span><span class="sxs-lookup"><span data-stu-id="dfe7e-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dfe7e-104">W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Analiza wydatków zakupowych**.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="dfe7e-105">Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="dfe7e-106">Przegląd</span><span class="sxs-lookup"><span data-stu-id="dfe7e-106">Overview</span></span>

<span data-ttu-id="dfe7e-107">Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** został zaprojektowany, aby pomóc kierownikom ds. zakupów i menedżerom odpowiedzialnym za budżety monitorować wydatki zakupowe.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="dfe7e-108">Menedżerowie mogą analizować wydatki zakupowe w następujące sposoby:</span><span class="sxs-lookup"><span data-stu-id="dfe7e-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="dfe7e-109">Zakupy od początku roku (według grupy dostawców i indywidualnych dostawców, kategorii zaopatrzenia, poszczególnych produktów i lokalizacji dostawców)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="dfe7e-110">Zmiany wydatków zakupowych rok do roku (według grup dostawców i kategorii zaopatrzenia)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="dfe7e-111">Pakiet zawartości wykorzystuje dane transakcyjne zakupów i przedstawia zarówno zagregowany widok danych zakupowych w całej firmie, jak i podział wydatków zakupowych na dostawców i produkty.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="dfe7e-112">Raporty eksponują zmiany wydatków zakupowych w horyzoncie czasowym.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="dfe7e-113">W związku z tym raporty mogą służyć do ostrzegania menedżerów o pozytywnych i negatywnych trendach wydatków dla poszczególnych dostawców i produktów.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="dfe7e-114">Dodatkowo wykresy pokazują wydatki zakupowe dla różnych kategorii zaopatrzenia i grup dostawców.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="dfe7e-115">W związku z tym menedżerowie kategorii i kierownicy regionalni mogą używać tych wykresów do identyfikowania zmian w zachowaniach wydatkowych.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="dfe7e-116">Przechodzenie do pakietu zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="dfe7e-116">Accessing the Power BI content</span></span>
<span data-ttu-id="dfe7e-117">Pakiet zawartości usługi Power BI **Analiza wydatków związanych z zakupami** jest wyświetlany na stronie **Analiza wydatków i zakupów** (**Zaopatrzenie i sourcing** \> **Zapytania i raporty** \> **Analiza wydajności zakupów** \> **Analiza wydatków i zakupów**).</span><span class="sxs-lookup"><span data-stu-id="dfe7e-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="dfe7e-118">Wskaźniki umieszczone w pakiecie zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="dfe7e-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="dfe7e-119">Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** obejmuje raport zawierający zestaw wskaźników.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="dfe7e-120">Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="dfe7e-121">Następująca sekcja zawiera przegląd dostępnych wizualizacji.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="dfe7e-122">Strona raportu o zakupach wg dostawcy</span><span class="sxs-lookup"><span data-stu-id="dfe7e-122">Purchase by vendor report page</span></span>
<span data-ttu-id="dfe7e-123">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-123">**Charts**</span></span>
- <span data-ttu-id="dfe7e-124">10 najważniejszych dostawców wg wartości zakupów (wykres skumulowany słupkowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="dfe7e-125">Łączne zakupy wg grupy dostawców/kraju/nazwy (wykres kołowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="dfe7e-126">Zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="dfe7e-127">Średnie zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="dfe7e-128">**Kafelki**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-128">**Tiles**</span></span>
- <span data-ttu-id="dfe7e-129">Suma zakupów</span><span class="sxs-lookup"><span data-stu-id="dfe7e-129">Total purchase</span></span>
- <span data-ttu-id="dfe7e-130">Wzrost zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="dfe7e-130">YOY purchase growth</span></span>
- <span data-ttu-id="dfe7e-131">Łączna liczba dostawców</span><span class="sxs-lookup"><span data-stu-id="dfe7e-131">Total # vendors</span></span>
- <span data-ttu-id="dfe7e-132">Łączna liczba aktywnych dostawców</span><span class="sxs-lookup"><span data-stu-id="dfe7e-132">Total # of active vendors</span></span>

<span data-ttu-id="dfe7e-133">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="dfe7e-134">Strona raportu o produktach wg dostawcy</span><span class="sxs-lookup"><span data-stu-id="dfe7e-134">Purchase by product report page</span></span>

<span data-ttu-id="dfe7e-135">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-135">**Charts**</span></span>
- <span data-ttu-id="dfe7e-136">Zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="dfe7e-137">Łączne zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kołowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="dfe7e-138">10 najważniejszych produktów wg wartości zakupów (wykres skumulowany słupkowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="dfe7e-139">**Kafelki**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-139">**Tiles**</span></span>
- <span data-ttu-id="dfe7e-140">Łączna liczba produktów</span><span class="sxs-lookup"><span data-stu-id="dfe7e-140">Total # of products</span></span></li>
- <span data-ttu-id="dfe7e-141">Procent aktywnych produktów w łącznej liczbie produktów</span><span class="sxs-lookup"><span data-stu-id="dfe7e-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="dfe7e-142">Liczba produktów odpowiedzialnych za 80% zakupów</span><span class="sxs-lookup"><span data-stu-id="dfe7e-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="dfe7e-143">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="dfe7e-144">Strona raportu o okresie wg dostawcy</span><span class="sxs-lookup"><span data-stu-id="dfe7e-144">Purchase by period report page</span></span>
<span data-ttu-id="dfe7e-145">Ta strona pokazuje zakupy w tym i ubiegłym roku oraz wzrost według kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="dfe7e-146">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-146">**Charts**</span></span> 
- <span data-ttu-id="dfe7e-147">Zakupy wg miesiąca/dnia (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="dfe7e-148">Odchylenie łącznych zakupów r/r (wykres kaskadowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="dfe7e-149">Wzrost łącznych zakupów r/r (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="dfe7e-150">Zestawienie zaopatrzenia (macierz)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="dfe7e-151">**Kafelki**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-151">**Tiles**</span></span>
- <span data-ttu-id="dfe7e-152">Wzrost zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="dfe7e-152">YOY purchase growth</span></span>
- <span data-ttu-id="dfe7e-153">% wzrostu zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="dfe7e-153">YOY purchase growth %</span></span>

<span data-ttu-id="dfe7e-154">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="dfe7e-155">Strona raportu o zakupach wg lokalizacji dostawcy</span><span class="sxs-lookup"><span data-stu-id="dfe7e-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="dfe7e-156">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-156">**Charts**</span></span>
- <span data-ttu-id="dfe7e-157">Zakupy wg miejscowości</span><span class="sxs-lookup"><span data-stu-id="dfe7e-157">Purchase by city</span></span>
- <span data-ttu-id="dfe7e-158">% wzrostu zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="dfe7e-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="dfe7e-159">Zakupy wg krajów</span><span class="sxs-lookup"><span data-stu-id="dfe7e-159">Purchase by country</span></span>

<span data-ttu-id="dfe7e-160">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="dfe7e-161">Analiza wydatków zakupowych wg strony raportu</span><span class="sxs-lookup"><span data-stu-id="dfe7e-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="dfe7e-162">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-162">**Charts**</span></span> 
- <span data-ttu-id="dfe7e-163">Zakupy w bieżącym roku wg miesiąca/dnia (wykres liniowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="dfe7e-164">Zakupy w bieżącym i ubiegłym roku (wykres liniowy i kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="dfe7e-165">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="dfe7e-166">Analiza wydatków zakupowych wg strony raportu dot. dostawcy</span><span class="sxs-lookup"><span data-stu-id="dfe7e-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="dfe7e-167">**Wykresy**</span><span class="sxs-lookup"><span data-stu-id="dfe7e-167">**Charts**</span></span> 
- <span data-ttu-id="dfe7e-168">% udziału 10 najważniejszych dostawców w zakupach (wykres lejkowy)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="dfe7e-169">10 dostawców z największym wzrostem wydatków r/r</span><span class="sxs-lookup"><span data-stu-id="dfe7e-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="dfe7e-170">10 dostawców z największym spadkiem wydatków r/r</span><span class="sxs-lookup"><span data-stu-id="dfe7e-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="dfe7e-171">**Przykład** 
</span><span class="sxs-lookup"><span data-stu-id="dfe7e-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="dfe7e-172">Model i jednostki danych</span><span class="sxs-lookup"><span data-stu-id="dfe7e-172">Data model and entities</span></span>
<span data-ttu-id="dfe7e-173">Następujące dane są używane do wypełniania stron raportów w pakiecie zawartości **Analiza wydatków zakupowych** dla usługi Power BI.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="dfe7e-174">Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="dfe7e-175">Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="dfe7e-176">Aby uzyskać więcej informacji, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="dfe7e-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="dfe7e-177">Zagregowane miary w tym pakiecie zawartości są podzbiorem zagregowanych miar, które były dostępne w module Zakupy w programach Microsoft Dynamics AX 2012 i Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="dfe7e-178">Aby zagregowane miary modułu można było umieścić w magazynie jednostek, trzeba ustawić te miary jako wdrażalne.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="dfe7e-179">Aby uzyskać więcej informacji, zobacz procedurę umieszczania zagregowanych miar w magazynie jednostek w temacie [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="dfe7e-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="dfe7e-180">Następujące najważniejsze zagregowane miary są dostępne bezpośrednio w jednostce Wiersze faktury i używane jako podstawa w pakiecie zawartości:</span><span class="sxs-lookup"><span data-stu-id="dfe7e-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="dfe7e-181">Jednostka</span><span class="sxs-lookup"><span data-stu-id="dfe7e-181">Entity</span></span>        | <span data-ttu-id="dfe7e-182">Najważniejsze zagregowane miary</span><span class="sxs-lookup"><span data-stu-id="dfe7e-182">Key aggregate measurements</span></span> | <span data-ttu-id="dfe7e-183">Źródło danych</span><span class="sxs-lookup"><span data-stu-id="dfe7e-183">Data source</span></span>                                 | <span data-ttu-id="dfe7e-184">Pole</span><span class="sxs-lookup"><span data-stu-id="dfe7e-184">Field</span></span>              | <span data-ttu-id="dfe7e-185">opis</span><span class="sxs-lookup"><span data-stu-id="dfe7e-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="dfe7e-186">Wiersze faktury</span><span class="sxs-lookup"><span data-stu-id="dfe7e-186">Invoice lines</span></span> | <span data-ttu-id="dfe7e-187">Zakup</span><span class="sxs-lookup"><span data-stu-id="dfe7e-187">Purchase</span></span>                   | <span data-ttu-id="dfe7e-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="dfe7e-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="dfe7e-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="dfe7e-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="dfe7e-190">Kwota w walucie rozliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="dfe7e-191">W poniższej tabeli przedstawiono najważniejsze miary w pakiecie zawartości, które są obliczane na podstawie jednostki Wiersze faktury.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="dfe7e-192">Pomiar</span><span class="sxs-lookup"><span data-stu-id="dfe7e-192">Measure</span></span>               | <span data-ttu-id="dfe7e-193">Obliczenie</span><span class="sxs-lookup"><span data-stu-id="dfe7e-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="dfe7e-194">Zakupy w bieżącym roku</span><span class="sxs-lookup"><span data-stu-id="dfe7e-194">Purchase current year</span></span> | <span data-ttu-id="dfe7e-195">Zakupy w bieżącym roku = SUM('Wiersze faktury'\[Zakupy\])</span><span class="sxs-lookup"><span data-stu-id="dfe7e-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="dfe7e-196">Zakupy w ubiegłym roku</span><span class="sxs-lookup"><span data-stu-id="dfe7e-196">Purchase last year</span></span>    | <span data-ttu-id="dfe7e-197">Zakupy w ubiegłym roku = CALCULATE(SUM('Wiersze faktury'\[Zakupy\]), SAMEPERIODLASTYEAR(Daty\[Data\]))</span><span class="sxs-lookup"><span data-stu-id="dfe7e-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="dfe7e-198">Wzrost zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="dfe7e-198">YOY purchase growth</span></span>   | <span data-ttu-id="dfe7e-199">Wzrost zakupów r/r = \[Zakupy w bieżącym roku\] – \[Zakupy w ubiegłym roku\]</span><span class="sxs-lookup"><span data-stu-id="dfe7e-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="dfe7e-200">Następujące najważniejsze wymiary w pakiecie zawartości są używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i lepszego wglądu analitycznego.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="dfe7e-201">Jednostka</span><span class="sxs-lookup"><span data-stu-id="dfe7e-201">Entity</span></span>                 | <span data-ttu-id="dfe7e-202">Przykłady atrybutów</span><span class="sxs-lookup"><span data-stu-id="dfe7e-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="dfe7e-203">Dostawcy</span><span class="sxs-lookup"><span data-stu-id="dfe7e-203">Vendors</span></span>                | <span data-ttu-id="dfe7e-204">Grupa dostawców, Kraj/region dostawcy, Nazwa dostawcy</span><span class="sxs-lookup"><span data-stu-id="dfe7e-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="dfe7e-205">Produkty</span><span class="sxs-lookup"><span data-stu-id="dfe7e-205">Products</span></span>               | <span data-ttu-id="dfe7e-206">Numer produktu, Nazwa produktu, Nazwa grupy pozycji</span><span class="sxs-lookup"><span data-stu-id="dfe7e-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="dfe7e-207">Kategorie zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="dfe7e-207">Procurement categories</span></span> | <span data-ttu-id="dfe7e-208">Kategoria zaopatrzenia, Nazwa kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="dfe7e-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="dfe7e-209">Firmy</span><span class="sxs-lookup"><span data-stu-id="dfe7e-209">Legal entities</span></span>         | <span data-ttu-id="dfe7e-210">Nazwa firmy</span><span class="sxs-lookup"><span data-stu-id="dfe7e-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="dfe7e-211">Daty</span><span class="sxs-lookup"><span data-stu-id="dfe7e-211">Dates</span></span>                  | <span data-ttu-id="dfe7e-212">Daty, Przesunięcie roku</span><span class="sxs-lookup"><span data-stu-id="dfe7e-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="dfe7e-213">Domyślnie pakiet zawartości przestawia dane bieżącego roku kalendarzowego.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="dfe7e-214">Można jednak zmienić wartość filtra dat w sekcji filtrów raportu.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="dfe7e-215">Można również zmienić wartość filtra firm.</span><span class="sxs-lookup"><span data-stu-id="dfe7e-215">You can also change the company filter.</span></span>
