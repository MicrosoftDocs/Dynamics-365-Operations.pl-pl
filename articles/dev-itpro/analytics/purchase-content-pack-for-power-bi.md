---
title: "Pakiet zawartości usługi Power BI Analiza wydatków zakupowych"
description: "W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Analiza wydatków zakupowych. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: FrankDahl
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6485f36802fc4e327e223f47d65c4bdca11c1609
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="e7e21-104">Pakiet zawartości usługi Power BI Analiza wydatków zakupowych</span><span class="sxs-lookup"><span data-stu-id="e7e21-104">Purchase spend analysis Power BI content</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e7e21-105">W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Analiza wydatków zakupowych**.</span><span class="sxs-lookup"><span data-stu-id="e7e21-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="e7e21-106">Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.</span><span class="sxs-lookup"><span data-stu-id="e7e21-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="e7e21-107">Przegląd</span><span class="sxs-lookup"><span data-stu-id="e7e21-107">Overview</span></span>

<span data-ttu-id="e7e21-108">Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** został zaprojektowany, aby pomóc kierownikom ds. zakupów i menedżerom odpowiedzialnym za budżety monitorować wydatki zakupowe.</span><span class="sxs-lookup"><span data-stu-id="e7e21-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="e7e21-109">Menedżerowie mogą analizować wydatki zakupowe w następujące sposoby:</span><span class="sxs-lookup"><span data-stu-id="e7e21-109">Managers can analyze purchase spending in the following ways:</span></span>

-   <span data-ttu-id="e7e21-110">Zakupy od początku roku (według grupy dostawców i indywidualnych dostawców, kategorii zaopatrzenia, poszczególnych produktów i lokalizacji dostawców)</span><span class="sxs-lookup"><span data-stu-id="e7e21-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
-   <span data-ttu-id="e7e21-111">Zmiany wydatków zakupowych rok do roku (według grup dostawców i kategorii zaopatrzenia)</span><span class="sxs-lookup"><span data-stu-id="e7e21-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="e7e21-112">Pakiet zawartości wykorzystuje dane transakcyjne zakupów i przedstawia zarówno zagregowany widok danych zakupowych w całej firmie, jak i podział wydatków zakupowych na dostawców i produkty.</span><span class="sxs-lookup"><span data-stu-id="e7e21-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="e7e21-113">Raporty eksponują zmiany wydatków zakupowych w horyzoncie czasowym.</span><span class="sxs-lookup"><span data-stu-id="e7e21-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="e7e21-114">W związku z tym raporty mogą służyć do ostrzegania menedżerów o pozytywnych i negatywnych trendach wydatków dla poszczególnych dostawców i produktów.</span><span class="sxs-lookup"><span data-stu-id="e7e21-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="e7e21-115">Dodatkowo wykresy pokazują wydatki zakupowe dla różnych kategorii zaopatrzenia i grup dostawców.</span><span class="sxs-lookup"><span data-stu-id="e7e21-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="e7e21-116">W związku z tym menedżerowie kategorii i kierownicy regionalni mogą używać tych wykresów do identyfikowania zmian w zachowaniach wydatkowych.</span><span class="sxs-lookup"><span data-stu-id="e7e21-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="e7e21-117">Przechodzenie do pakietu zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="e7e21-117">Accessing the Power BI content</span></span>
<span data-ttu-id="e7e21-118">Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017 r.), pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** jest wyświetlany na stronie **Analiza wydatków i zakupów** (**Zaopatrzenie i sourcing** > **Zapytania i raporty** > **Analiza wydajności zakupów** > **Analiza wydatków i zakupów**).</span><span class="sxs-lookup"><span data-stu-id="e7e21-118">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), the **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** > **Inquiries and reports** > **Purchase performance analysis** > **Purchase and spend analysis**).</span></span> 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="e7e21-119">Wskaźniki umieszczone w pakiecie zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="e7e21-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="e7e21-120">Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** obejmuje raport zawierający zestaw wskaźników.</span><span class="sxs-lookup"><span data-stu-id="e7e21-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="e7e21-121">Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele.</span><span class="sxs-lookup"><span data-stu-id="e7e21-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="e7e21-122">Następująca tabela zawiera przegląd dostępnych wizualizacji.</span><span class="sxs-lookup"><span data-stu-id="e7e21-122">The following table provides an overview of the visualizations.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7e21-123">Strona raportu</span><span class="sxs-lookup"><span data-stu-id="e7e21-123">Report page</span></span></th>
<th><span data-ttu-id="e7e21-124">Wykresy</span><span class="sxs-lookup"><span data-stu-id="e7e21-124">Charts</span></span></th>
<th><span data-ttu-id="e7e21-125">Kafelki</span><span class="sxs-lookup"><span data-stu-id="e7e21-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e7e21-126">Zakupy wg dostawców</span><span class="sxs-lookup"><span data-stu-id="e7e21-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="e7e21-127">10 najważniejszych dostawców wg wartości zakupów (wykres skumulowany słupkowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="e7e21-128">Łączne zakupy wg grupy dostawców/kraju/nazwy (wykres kołowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="e7e21-129">Zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="e7e21-130">Średnie zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e7e21-131">Suma zakupów</span><span class="sxs-lookup"><span data-stu-id="e7e21-131">Total purchase</span></span></li>
<li><span data-ttu-id="e7e21-132">Wzrost zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="e7e21-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="e7e21-133">Łączna liczba dostawców</span><span class="sxs-lookup"><span data-stu-id="e7e21-133">Total # vendors</span></span></li>
<li><span data-ttu-id="e7e21-134">Łączna liczba aktywnych dostawców</span><span class="sxs-lookup"><span data-stu-id="e7e21-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e7e21-135">Zakupy wg produktów</span><span class="sxs-lookup"><span data-stu-id="e7e21-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="e7e21-136">Zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="e7e21-137">Łączne zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kołowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="e7e21-138">10 najważniejszych produktów wg wartości zakupów (wykres skumulowany słupkowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e7e21-139">Łączna liczba produktów</span><span class="sxs-lookup"><span data-stu-id="e7e21-139">Total # of products</span></span></li>
<li><span data-ttu-id="e7e21-140">Procent aktywnych produktów w łącznej liczbie produktów</span><span class="sxs-lookup"><span data-stu-id="e7e21-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="e7e21-141">Liczba produktów odpowiedzialnych za 80% zakupów</span><span class="sxs-lookup"><span data-stu-id="e7e21-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e7e21-142">Zakupy wg okresu*</span><span class="sxs-lookup"><span data-stu-id="e7e21-142">Purchase by period*</span></span></td>
<td><ul>
<li><span data-ttu-id="e7e21-143">Zakupy wg miesiąca/dnia (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="e7e21-144">Odchylenie łącznych zakupów r/r (wykres kaskadowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="e7e21-145">Wzrost łącznych zakupów r/r (wykres kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="e7e21-146">Zestawienie zaopatrzenia (macierz)</span><span class="sxs-lookup"><span data-stu-id="e7e21-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e7e21-147">Wzrost zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="e7e21-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="e7e21-148">% wzrostu zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="e7e21-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e7e21-149">Zakupy wg lokalizacji dostawców</span><span class="sxs-lookup"><span data-stu-id="e7e21-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="e7e21-150">Zakupy wg miejscowości</span><span class="sxs-lookup"><span data-stu-id="e7e21-150">Purchase by city</span></span></li>
<li><span data-ttu-id="e7e21-151">% wzrostu zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="e7e21-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="e7e21-152">Zakupy wg krajów</span><span class="sxs-lookup"><span data-stu-id="e7e21-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e7e21-153">Analiza wydatków zakupowych wg okresów</span><span class="sxs-lookup"><span data-stu-id="e7e21-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="e7e21-154">Zakupy w bieżącym roku wg miesiąca/dnia (wykres liniowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="e7e21-155">Zakupy w bieżącym i ubiegłym roku (wykres liniowy i kolumnowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e7e21-156">Analiza wydatków zakupowych wg dostawców</span><span class="sxs-lookup"><span data-stu-id="e7e21-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="e7e21-157">% udziału 10 najważniejszych dostawców w zakupach (wykres lejkowy)</span><span class="sxs-lookup"><span data-stu-id="e7e21-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="e7e21-158">10 dostawców z największym wzrostem wydatków r/r</span><span class="sxs-lookup"><span data-stu-id="e7e21-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="e7e21-159">10 dostawców z największym spadkiem wydatków r/r</span><span class="sxs-lookup"><span data-stu-id="e7e21-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e7e21-160">\* Zakupy w tym i ubiegłym roku oraz wzrost według kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="e7e21-160">\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="e7e21-161">Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="e7e21-161">Extending the Power BI content</span></span>
<span data-ttu-id="e7e21-162">Za pomocą pakietów zawartości dostępnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) można dostarczać zaawansowane funkcje analityczne osobom, które się nie logują w programie Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7e21-162">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="e7e21-163">Te pakiety zawartości można modyfikować, tak aby zawierały inne raporty lub wizualizacje, a następnie publikować je w swojej dzierżawie usługi Power BI.com na potrzeby wykonywania analiz.</span><span class="sxs-lookup"><span data-stu-id="e7e21-163">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="e7e21-164">Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** znajduje się w bibliotece zasobów wspólnych w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="e7e21-164">You can find the **Purchase spend analysis** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="e7e21-165">Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="e7e21-165">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="e7e21-166">Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).</span><span class="sxs-lookup"><span data-stu-id="e7e21-166">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

<span data-ttu-id="e7e21-167">Uważaj, aby pobrać pakiet zawartości **Analiza wydatków zakupowych** mający zastosowanie do używanej wersji systemu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7e21-167">Be sure to download the **Purchase spend analysis** content that applies to the version of Dynamics 365 that you're using.</span></span>

> [!NOTE]
> <span data-ttu-id="e7e21-168">Jeśli używasz programu Microsoft Dynamics 365 for Operations w wersji 1611, ten pakiet zawartości usługi Power BI wymaga poprawki KB 4011327.</span><span class="sxs-lookup"><span data-stu-id="e7e21-168">If you're using Microsoft Dynamics 365 for Operations version 1611, KB 4011327 is a prerequisite for this Power BI content.</span></span> <span data-ttu-id="e7e21-169">Po zalogowaniu się w usłudze LCS można uzyskać dostęp do tej poprawki KB tutaj: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span><span class="sxs-lookup"><span data-stu-id="e7e21-169">After you sign in to LCS, you can access the KB at https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="e7e21-170">Model i jednostki danych</span><span class="sxs-lookup"><span data-stu-id="e7e21-170">Data model and entities</span></span>
<span data-ttu-id="e7e21-171">Następujące dane są używane do wypełniania stron raportów w pakiecie zawartości **Analiza wydatków zakupowych** dla usługi Power BI.</span><span class="sxs-lookup"><span data-stu-id="e7e21-171">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="e7e21-172">Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek.</span><span class="sxs-lookup"><span data-stu-id="e7e21-172">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="e7e21-173">Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz.</span><span class="sxs-lookup"><span data-stu-id="e7e21-173">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="e7e21-174">Aby uzyskać więcej informacji, zobacz [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="e7e21-174">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="e7e21-175">Zagregowane miary w tym pakiecie zawartości są podzbiorem zagregowanych miar, które były dostępne w module Zakupy w programach Microsoft Dynamics AX 2012 i Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="e7e21-175">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="e7e21-176">Aby zagregowane miary modułu można było umieścić w magazynie jednostek, trzeba ustawić te miary jako wdrażalne.</span><span class="sxs-lookup"><span data-stu-id="e7e21-176">To stage the cube’s aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="e7e21-177">Aby uzyskać więcej informacji, zobacz procedurę umieszczania zagregowanych miar w magazynie jednostek w temacie [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="e7e21-177">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="e7e21-178">Następujące najważniejsze zagregowane miary są dostępne bezpośrednio w jednostce Wiersze faktury i używane jako podstawa w pakiecie zawartości:</span><span class="sxs-lookup"><span data-stu-id="e7e21-178">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="e7e21-179">Jednostka</span><span class="sxs-lookup"><span data-stu-id="e7e21-179">Entity</span></span>        | <span data-ttu-id="e7e21-180">Najważniejsze zagregowane miary</span><span class="sxs-lookup"><span data-stu-id="e7e21-180">Key aggregate measurements</span></span> | <span data-ttu-id="e7e21-181">Źródło danych</span><span class="sxs-lookup"><span data-stu-id="e7e21-181">Data source</span></span>                                 | <span data-ttu-id="e7e21-182">Pole</span><span class="sxs-lookup"><span data-stu-id="e7e21-182">Field</span></span>              | <span data-ttu-id="e7e21-183">opis</span><span class="sxs-lookup"><span data-stu-id="e7e21-183">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="e7e21-184">Wiersze faktury</span><span class="sxs-lookup"><span data-stu-id="e7e21-184">Invoice lines</span></span> | <span data-ttu-id="e7e21-185">Zakup</span><span class="sxs-lookup"><span data-stu-id="e7e21-185">Purchase</span></span>                   | <span data-ttu-id="e7e21-186">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="e7e21-186">VendInvoiceTrans</span></span>                            | <span data-ttu-id="e7e21-187">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="e7e21-187">SUM(LineAmountMST)</span></span> | <span data-ttu-id="e7e21-188">Kwota w walucie rozliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="e7e21-188">The amount in the accounting currency.</span></span> |

<span data-ttu-id="e7e21-189">W poniższej tabeli przedstawiono najważniejsze miary w pakiecie zawartości, które są obliczane na podstawie jednostki Wiersze faktury.</span><span class="sxs-lookup"><span data-stu-id="e7e21-189">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="e7e21-190">Pomiar</span><span class="sxs-lookup"><span data-stu-id="e7e21-190">Measure</span></span>               | <span data-ttu-id="e7e21-191">Obliczenie</span><span class="sxs-lookup"><span data-stu-id="e7e21-191">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e7e21-192">Zakupy w bieżącym roku</span><span class="sxs-lookup"><span data-stu-id="e7e21-192">Purchase current year</span></span> | <span data-ttu-id="e7e21-193">Zakupy w bieżącym roku = SUM('Wiersze faktury'\[Zakupy\])</span><span class="sxs-lookup"><span data-stu-id="e7e21-193">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="e7e21-194">Zakupy w ubiegłym roku</span><span class="sxs-lookup"><span data-stu-id="e7e21-194">Purchase last year</span></span>    | <span data-ttu-id="e7e21-195">Zakupy w ubiegłym roku = CALCULATE(SUM('Wiersze faktury'\[Zakupy\]), SAMEPERIODLASTYEAR(Daty\[Data\]))</span><span class="sxs-lookup"><span data-stu-id="e7e21-195">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="e7e21-196">Wzrost zakupów r/r</span><span class="sxs-lookup"><span data-stu-id="e7e21-196">YOY purchase growth</span></span>   | <span data-ttu-id="e7e21-197">Wzrost zakupów r/r = \[Zakupy w bieżącym roku\] – \[Zakupy w ubiegłym roku\]</span><span class="sxs-lookup"><span data-stu-id="e7e21-197">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="e7e21-198">Następujące najważniejsze wymiary w pakiecie zawartości są używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i lepszego wglądu analitycznego.</span><span class="sxs-lookup"><span data-stu-id="e7e21-198">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="e7e21-199">Jednostka</span><span class="sxs-lookup"><span data-stu-id="e7e21-199">Entity</span></span>                 | <span data-ttu-id="e7e21-200">Przykłady atrybutów</span><span class="sxs-lookup"><span data-stu-id="e7e21-200">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="e7e21-201">Dostawcy</span><span class="sxs-lookup"><span data-stu-id="e7e21-201">Vendors</span></span>                | <span data-ttu-id="e7e21-202">Grupa dostawców, Kraj/region dostawcy, Nazwa dostawcy</span><span class="sxs-lookup"><span data-stu-id="e7e21-202">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="e7e21-203">Produkty</span><span class="sxs-lookup"><span data-stu-id="e7e21-203">Products</span></span>               | <span data-ttu-id="e7e21-204">Numer produktu, Nazwa produktu, Nazwa grupy pozycji</span><span class="sxs-lookup"><span data-stu-id="e7e21-204">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="e7e21-205">Kategorie zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="e7e21-205">Procurement categories</span></span> | <span data-ttu-id="e7e21-206">Kategoria zaopatrzenia, Nazwa kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="e7e21-206">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="e7e21-207">Firmy</span><span class="sxs-lookup"><span data-stu-id="e7e21-207">Legal entities</span></span>         | <span data-ttu-id="e7e21-208">Nazwa firmy</span><span class="sxs-lookup"><span data-stu-id="e7e21-208">Legal entity name</span></span>                                     |
| <span data-ttu-id="e7e21-209">Daty</span><span class="sxs-lookup"><span data-stu-id="e7e21-209">Dates</span></span>                  | <span data-ttu-id="e7e21-210">Daty, Przesunięcie roku</span><span class="sxs-lookup"><span data-stu-id="e7e21-210">Dates, Year offset</span></span>                                    |

<span data-ttu-id="e7e21-211">Domyślnie pakiet zawartości przestawia dane bieżącego roku kalendarzowego.</span><span class="sxs-lookup"><span data-stu-id="e7e21-211">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="e7e21-212">Można jednak zmienić wartość filtra dat w sekcji filtrów raportu.</span><span class="sxs-lookup"><span data-stu-id="e7e21-212">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="e7e21-213">Można również zmienić wartość filtra firm.</span><span class="sxs-lookup"><span data-stu-id="e7e21-213">You can also change the company filter.</span></span>

