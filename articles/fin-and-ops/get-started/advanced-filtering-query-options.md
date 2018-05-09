---
title: "Składnia zaawansowanego filtrowania i zapytań"
description: "W tym artykule opisano opcje filtrowania i kwerend dostępne dla operatora „dopasowania” w oknie dialogowym Zaawansowany filtr/sortowanie."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fa9c962ffce161365d1a030cf9995cce3ff19934
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="4d530-103">Składnia zaawansowanego filtrowania i zapytań</span><span class="sxs-lookup"><span data-stu-id="4d530-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d530-104">W tym artykule opisano opcje filtrowania i kwerend dostępne dla operatora „dopasowania” w oknie dialogowym Zaawansowany filtr/sortowanie.</span><span class="sxs-lookup"><span data-stu-id="4d530-104">This article describes the filtering and query options that are available when you use the "matches" operator in the Advanced filter/sort dialog.</span></span>

<a name="advanced-query-syntax"></a><span data-ttu-id="4d530-105">Składnia zaawansowanych zapytań</span><span class="sxs-lookup"><span data-stu-id="4d530-105">Advanced query syntax</span></span>
---------------------

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d530-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="4d530-106">Syntax</span></span></th>
<th><span data-ttu-id="4d530-107">Opis charakterystyki</span><span class="sxs-lookup"><span data-stu-id="4d530-107">Character description</span></span></th>
<th><span data-ttu-id="4d530-108">opis</span><span class="sxs-lookup"><span data-stu-id="4d530-108">Description</span></span></th>
<th><span data-ttu-id="4d530-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="4d530-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4d530-110"><em>wartość</em></span><span class="sxs-lookup"><span data-stu-id="4d530-110"><em>value</em></span></span></td>
<td><span data-ttu-id="4d530-111">Równa wartości, która została wprowadzona.</span><span class="sxs-lookup"><span data-stu-id="4d530-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4d530-112">Wpisz wartość, którą chcesz znaleźć.</span><span class="sxs-lookup"><span data-stu-id="4d530-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="4d530-113">Wyrażenie <strong>Nowak</strong> pozwala wyszukać wartość &quot;Nowak&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-114">!<em>wartość</em> (wykrzyknik)</span><span class="sxs-lookup"><span data-stu-id="4d530-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="4d530-115">Nie równa wartości, która została wprowadzona.</span><span class="sxs-lookup"><span data-stu-id="4d530-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4d530-116">Wpisz wykrzyknik i wartość którą chcesz wykluczyć.</span><span class="sxs-lookup"><span data-stu-id="4d530-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="4d530-117">Wyrażenie <strong>!Nowak</strong> pozwala wyszukać wszystkie wartości z wyjątkiem &quot;Nowak&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-118"><em>Od</em>..<em>Do</em> (dwie kropki)</span><span class="sxs-lookup"><span data-stu-id="4d530-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="4d530-119">Między wartościami rozdzielonymi dwoma kropkami</span><span class="sxs-lookup"><span data-stu-id="4d530-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="4d530-120">Wpisz wartość Od, a po niej dwie kropki i wartość Do.</span><span class="sxs-lookup"><span data-stu-id="4d530-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="4d530-121">Wyrażenie <strong>1..10</strong> pozwala wyszukać wszystkie wartości od 1 do 10.</span><span class="sxs-lookup"><span data-stu-id="4d530-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="4d530-122">Jednak w polu tekstowym wyrażenie <strong>A..C</strong> pozwala wyszukać wszystkie wartości rozpoczynające się od &quot;A&quot; i &quot;B&quot; oraz dokładnie równe &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="4d530-123">To zapytanie nie pozwala na przykład znaleźć wyrażenia &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-123">For example, this query won&#39;t find &quot;Ca&quot;.</span></span> <span data-ttu-id="4d530-124">Aby wyszukać wszystkie wartości od &quot;A<em>&quot; do &quot;C</em>&quot; włącznie, wpisz <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-125">..<em>wartość</em> (dwie kropki)</span><span class="sxs-lookup"><span data-stu-id="4d530-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="4d530-126">Mniejsze lub równe wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="4d530-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4d530-127">Wpisz dwie kropki, a następnie wartość.</span><span class="sxs-lookup"><span data-stu-id="4d530-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="4d530-128">Wyrażenie <strong>..1000</strong> pozwala wyszukać dowolną liczbę mniejszą lub równą 1000, na przykład &quot;100&quot;, &quot;999,95&quot; i &quot;1000&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-129"><em>wartość</em>..</span><span class="sxs-lookup"><span data-stu-id="4d530-129"><em>value</em>..</span></span> <span data-ttu-id="4d530-130">(dwie kropki)</span><span class="sxs-lookup"><span data-stu-id="4d530-130">(double period)</span></span></td>
<td><span data-ttu-id="4d530-131">Większe lub równe wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="4d530-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4d530-132">Wpisz wartość, a po niej dwie kropki.</span><span class="sxs-lookup"><span data-stu-id="4d530-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="4d530-133">Wyrażenie <strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="4d530-133"><strong>1000..</strong></span></span> <span data-ttu-id="4d530-134">pozwala wyszukać dowolną liczbę większą lub równą 1000, na przykład &quot;1000&quot;, &quot;1000,01&quot; i &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-135">&gt;<em>wartość</em> (znak „większe niż”)</span><span class="sxs-lookup"><span data-stu-id="4d530-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="4d530-136">Większe od wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="4d530-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="4d530-137">Wpisz znak „większe niż” (<strong>&gt;</strong>), a następnie wartość.</span><span class="sxs-lookup"><span data-stu-id="4d530-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="4d530-138">Wyrażenie <strong>&gt;1000</strong> pozwala wyszukać dowolną liczbę większą niż 1000, np. &quot;1000,01&quot;, &quot;20 000&quot; i &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-139">&lt;<em>wartość</em> (znak „mniejsze niż”)</span><span class="sxs-lookup"><span data-stu-id="4d530-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="4d530-140">Mniejsze od wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="4d530-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="4d530-141">Wpisz znak „mniejsze niż” (<strong>&lt;</strong>), a następnie wartość.</span><span class="sxs-lookup"><span data-stu-id="4d530-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="4d530-142">Wyrażenie <strong>&lt;1000</strong> pozwala wyszukać dowolną liczbę mniejszą niż 1000, np. &quot;999,99&quot;, &quot;1&quot; i &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-143"><em>wartość</em>\* (gwiazdka)</span><span class="sxs-lookup"><span data-stu-id="4d530-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="4d530-144">Począwszy od wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="4d530-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="4d530-145">Wpisz wartość początkową, a następnie gwiazdkę (<strong><em></strong>).</span><span class="sxs-lookup"><span data-stu-id="4d530-145">Type the starting value and then an asterisk (<strong><em></strong>).</span></span></td>
<td><span data-ttu-id="4d530-146">Wyrażenie <strong>S</em></strong> pozwala wyszukać wszystkie ciągi znaków rozpoczynające się literą &quot;S&quot;, takie jak &quot;Sztokholm&quot;, &quot;Sydney&quot; i &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-146"><strong>S</em></strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-147"><em><em>wartość</em> (gwiazdka)</span><span class="sxs-lookup"><span data-stu-id="4d530-147"><em><em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="4d530-148">Kończące się wprowadzoną wartością</span><span class="sxs-lookup"><span data-stu-id="4d530-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="4d530-149">Wpisz gwiazdkę, a następnie wartość końcową.</span><span class="sxs-lookup"><span data-stu-id="4d530-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="4d530-150">Wyrażenie <strong></em>chód</strong> pozwala wyszukać wszystkie ciągi znaków kończące się literami &quot;chód&quot;, jak &quot;Wschód&quot; i &quot;Zachód&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-150"><strong></em>east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-151"><em><em>wartość</em></em> (gwiazdka)</span><span class="sxs-lookup"><span data-stu-id="4d530-151"><em><em>value</em></em> (asterisk)</span></span></td>
<td><span data-ttu-id="4d530-152">Zawiera wprowadzoną wartość</span><span class="sxs-lookup"><span data-stu-id="4d530-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="4d530-153">Wpisz gwiazdkę, a po niej wartość i kolejną gwiazdkę.</span><span class="sxs-lookup"><span data-stu-id="4d530-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="4d530-154">Wyrażenie <strong><em>ch</em></strong> pozwala wyszukać wszystkie ciągi znaków zawierające litery &quot;ch&quot;, takie jak &quot;Wschód&quot; i &quot;Zachód&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-154"><strong><em>th</em></strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-155">?</span><span class="sxs-lookup"><span data-stu-id="4d530-155">?</span></span> <span data-ttu-id="4d530-156">(pytajnik)</span><span class="sxs-lookup"><span data-stu-id="4d530-156">(question mark)</span></span></td>
<td><span data-ttu-id="4d530-157">Posiadające co najmniej jeden nieznany znak.</span><span class="sxs-lookup"><span data-stu-id="4d530-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="4d530-158">Wpisz pytajnik w miejscu nieznanego znaku w wartości.</span><span class="sxs-lookup"><span data-stu-id="4d530-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="4d530-159">Wyrażenie <strong>Now?k</strong> pozwala wyszukać &quot;Nowak&quot; i &quot;Nowik&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-160"><em>wartość</em>,<em>wartość</em> (przecinek)</span><span class="sxs-lookup"><span data-stu-id="4d530-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="4d530-161">Zgodne z wprowadzonymi wartościami, rozdzielonymi przecinkami</span><span class="sxs-lookup"><span data-stu-id="4d530-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="4d530-162">Wpisz wszystkie kryteria, rozdzielając je przecinkami.</span><span class="sxs-lookup"><span data-stu-id="4d530-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="4d530-163">Wyrażenie <strong>A, D, F, G</strong> pozwala wyszukać dokładnie &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, i &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="4d530-164">Wyrażenie <strong>10, 20, 30, 100</strong> pozwala wyszukać dokładnie &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="4d530-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-165">(<span class="code">Instrukcji SQL</span>) (Instrukcja SQL w nawiasach okrągłych)</span><span class="sxs-lookup"><span data-stu-id="4d530-165">(<span class="code">SQL statement</span>) (SQL statement between parentheses)</span></span></td>
<td><span data-ttu-id="4d530-166">Zgodne ze wskazaną kwerendą.</span><span class="sxs-lookup"><span data-stu-id="4d530-166">Matching a defined query</span></span></td>
<td><span data-ttu-id="4d530-167">Wpisz kwerendę jako instrukcję SQL w nawiasach okrągłych.</span><span class="sxs-lookup"><span data-stu-id="4d530-167">Type a query as an SQL statement between parentheses.</span></span></td>
<td><span data-ttu-id="4d530-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span><span class="sxs-lookup"><span data-stu-id="4d530-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-169">T</span><span class="sxs-lookup"><span data-stu-id="4d530-169">T</span></span></td>
<td><span data-ttu-id="4d530-170">Data dzisiejsza</span><span class="sxs-lookup"><span data-stu-id="4d530-170">Today&#39;s date</span></span></td>
<td><span data-ttu-id="4d530-171">Wpisz <strong>T</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-171">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="4d530-172"><strong>T</strong> pasuje do bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="4d530-172"><strong>T</strong> matches today&#39;s date.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> metoda w nawiasach)</span><span class="sxs-lookup"><span data-stu-id="4d530-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="4d530-174">Dopasowanie wartości lub zakresu wartości określonych przez parametry metody <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="4d530-174">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="4d530-175">Wpisz metodę <strong>SysQueryRangeUtil</strong> z parametrami, które określają wartość lub zakres wartości.</span><span class="sxs-lookup"><span data-stu-id="4d530-175">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td><ol>
<li><span data-ttu-id="4d530-176">Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Otwarte faktury odbiorcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-176">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="4d530-177">Naciśnij kombinację klawiszy Ctrl + Shift + F3, aby otworzyć stronę <strong>Informacje</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-177">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="4d530-178">Na karcie <strong>Zakres</strong> kliknij przycisk <strong>Dodaj</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-178">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="4d530-179">W polu <strong>Tabela</strong> wybierz <strong>Otwarte transakcje odbiorcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-179">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="4d530-180">W polu <strong>Pole</strong> wybierz <strong>Termin</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-180">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="4d530-181">W polu <strong>Kryteria</strong> wpisz <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-181">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="4d530-182">Kliknij przycisk <strong>OK</strong></span><span class="sxs-lookup"><span data-stu-id="4d530-182">Click <strong>OK</strong>.</span></span> <span data-ttu-id="4d530-183">Strona listy jest aktualizowana i pojawiają się faktury pasujące do wpisanych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="4d530-183">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="4d530-184">W tym przykładzie faktury należne w ciągu ostatnich dwóch lat, są wymienione.</span><span class="sxs-lookup"><span data-stu-id="4d530-184">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="4d530-185">Zobacz tabelę w następnej sekcji, aby uzyskać szczegóły o metodzie wprowadzania daty <strong>SysQueryRangeUtil</strong> oraz kilka przykładów.</span><span class="sxs-lookup"><span data-stu-id="4d530-185">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="4d530-186">Zaawansowane kwerendy danych używające metod SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="4d530-186">Advanced date queries that use SysQueryRangeUtil methods</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d530-187">Metoda</span><span class="sxs-lookup"><span data-stu-id="4d530-187">Method</span></span></th>
<th><span data-ttu-id="4d530-188">Opis</span><span class="sxs-lookup"><span data-stu-id="4d530-188">Description</span></span></th>
<th><span data-ttu-id="4d530-189">Przykład</span><span class="sxs-lookup"><span data-stu-id="4d530-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4d530-190">Day (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="4d530-190">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="4d530-191">Znajdowanie daty względem daty sesji.</span><span class="sxs-lookup"><span data-stu-id="4d530-191">Find a date relative to the session date.</span></span> <span data-ttu-id="4d530-192">Wartości dodatnie wskazują na przyszłe daty, a wartości ujemne na daty w przeszłości.</span><span class="sxs-lookup"><span data-stu-id="4d530-192">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="4d530-193"><strong>Jutro</strong> — wpisz <strong>(Day(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-193"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="4d530-194"><strong>Dziś</strong> — wpisz <strong>(Day(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-194"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="4d530-195"><strong>Wczoraj</strong> — wpisz <strong>(Day(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-195"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="4d530-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="4d530-197">Znajdowanie zakresu dat względem daty sesji.</span><span class="sxs-lookup"><span data-stu-id="4d530-197">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="4d530-198">Wartości dodatnie wskazują na przyszłe daty, a wartości ujemne na daty w przeszłości.</span><span class="sxs-lookup"><span data-stu-id="4d530-198">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="4d530-199"><strong>Ostatnie 30 dni</strong> — wpisz <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-199"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="4d530-200"><strong>Poprzednie 30 dni i następne 30 dni</strong> — wpisz <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-200"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="4d530-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="4d530-202">Znajdowanie wszystkich dat po określonej dacie względnej.</span><span class="sxs-lookup"><span data-stu-id="4d530-202">Find all dates after the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="4d530-203"><strong>Więcej niż 30 dni od teraz</strong> — wpisz <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-203"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-204">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="4d530-204">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="4d530-205">Znajdowanie wpisów daty/godziny po godzinie bieżącej.</span><span class="sxs-lookup"><span data-stu-id="4d530-205">Find all date/time entries after the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="4d530-206"><strong>Wszystkie przyszłe daty/godziny</strong> — wpisz <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-206"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="4d530-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="4d530-208">Znajdowanie wszystkich dat przed określoną datą względną.</span><span class="sxs-lookup"><span data-stu-id="4d530-208">Find all dates before the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="4d530-209"><strong>Mniej niż siedem dni od teraz</strong> — wpisz <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-209"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-210">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="4d530-210">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="4d530-211">Znajdowanie wpisów daty/godziny przed godziną bieżącą.</span><span class="sxs-lookup"><span data-stu-id="4d530-211">Find all date/time entries before the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="4d530-212"><strong>Wszystkie od daty/godziny</strong> — wpisz <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-212"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d530-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="4d530-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="4d530-214">Znajdowanie zakresu dat według miesięcy względem bieżącego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="4d530-214">Find a range of dates, based on months relative to the current month.</span></span></td>
<td><ul>
<li><span data-ttu-id="4d530-215"><strong>Poprzednie dwa miesiące</strong> — wpisz <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-215"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="4d530-216"><strong>Następne trzy miesiące</strong> — wpisz <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-216"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d530-217">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="4d530-217">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="4d530-218">Znajdowanie zakresu dat według lat względem bieżącego roku.</span><span class="sxs-lookup"><span data-stu-id="4d530-218">Find a range of dates, based on years relative to the current year.</span></span></td>
<td><ul>
<li><span data-ttu-id="4d530-219"><strong>Następny roku</strong> — wpisz <strong>(YearRange (0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-219"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="4d530-220"><strong>Poprzedni roku</strong> — wpisz <strong>(YearRange (-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d530-220"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






