---
title: Filtrowanie zaawansowane i składnia zapytań
description: W tym temacie opisano opcje filtrowania i zapytań dla okna dialogowego Zaawansowane filtrowanie/sortowanie lub operatora jest zgodne z w okienku Filtr lub filtrach nagłówków kolumn siatki.
author: jasongre
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdb55a9552759e5f2b670a4eeb4e5d6572ebfb77
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744106"
---
# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="198c5-103">Filtrowanie zaawansowane i składnia zapytań</span><span class="sxs-lookup"><span data-stu-id="198c5-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="198c5-104">W tym temacie opisano opcje filtrowania i zapytań dostępne podczas używania okna dialogowego Zaawansowane filtrowanie/sortowanie lub operatora **jest zgodne** z w okienku Filtr lub filtrach nagłówków kolumn siatki.</span><span class="sxs-lookup"><span data-stu-id="198c5-104">This topic describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span>

## <a name="advanced-query-syntax"></a><span data-ttu-id="198c5-105">Składnia zaawansowanych zapytań</span><span class="sxs-lookup"><span data-stu-id="198c5-105">Advanced query syntax</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="198c5-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="198c5-106">Syntax</span></span></th>
<th><span data-ttu-id="198c5-107">Opis charakterystyki</span><span class="sxs-lookup"><span data-stu-id="198c5-107">Character description</span></span></th>
<th><span data-ttu-id="198c5-108">opis</span><span class="sxs-lookup"><span data-stu-id="198c5-108">Description</span></span></th>
<th><span data-ttu-id="198c5-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="198c5-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="198c5-110"><em>wartość</em></span><span class="sxs-lookup"><span data-stu-id="198c5-110"><em>value</em></span></span></td>
<td><span data-ttu-id="198c5-111">Równa wartości, która została wprowadzona.</span><span class="sxs-lookup"><span data-stu-id="198c5-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="198c5-112">Wpisz wartość, którą chcesz znaleźć.</span><span class="sxs-lookup"><span data-stu-id="198c5-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="198c5-113">Wyrażenie <strong>Nowak</strong> pozwala wyszukać wartość &quot;Nowak&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-114">!<em>wartość</em> (wykrzyknik)</span><span class="sxs-lookup"><span data-stu-id="198c5-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="198c5-115">Nie równa wartości, która została wprowadzona.</span><span class="sxs-lookup"><span data-stu-id="198c5-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="198c5-116">Wpisz wykrzyknik i wartość którą chcesz wykluczyć.</span><span class="sxs-lookup"><span data-stu-id="198c5-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="198c5-117">Wyrażenie <strong>!Nowak</strong> pozwala wyszukać wszystkie wartości z wyjątkiem &quot;Nowak&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-118"><em>Od</em>..<em>Do</em> (dwie kropki)</span><span class="sxs-lookup"><span data-stu-id="198c5-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="198c5-119">Między wartościami rozdzielonymi dwoma kropkami</span><span class="sxs-lookup"><span data-stu-id="198c5-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="198c5-120">Wpisz wartość Od, a po niej dwie kropki i wartość Do.</span><span class="sxs-lookup"><span data-stu-id="198c5-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="198c5-121">Wyrażenie <strong>1..10</strong> pozwala wyszukać wszystkie wartości od 1 do 10.</span><span class="sxs-lookup"><span data-stu-id="198c5-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="198c5-122">Jednak w polu tekstowym wyrażenie <strong>A..C</strong> pozwala wyszukać wszystkie wartości rozpoczynające się od &quot;A&quot; i &quot;B&quot; oraz dokładnie równe &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="198c5-123">To zapytanie nie pozwala na przykład znaleźć wyrażenia &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="198c5-124">Aby wyszukać wszystkie wartości od &quot;A<em>&quot; do &quot;C</em>&quot; włącznie, wpisz <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-125">..<em>wartość</em> (dwie kropki)</span><span class="sxs-lookup"><span data-stu-id="198c5-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="198c5-126">Mniejsze lub równe wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="198c5-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="198c5-127">Wpisz dwie kropki, a następnie wartość.</span><span class="sxs-lookup"><span data-stu-id="198c5-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="198c5-128">Wyrażenie <strong>..1000</strong> pozwala wyszukać dowolną liczbę mniejszą lub równą 1000, na przykład &quot;100&quot;, &quot;999,95&quot; i &quot;1000&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-129"><em>wartość</em>..</span><span class="sxs-lookup"><span data-stu-id="198c5-129"><em>value</em>..</span></span> <span data-ttu-id="198c5-130">(dwie kropki)</span><span class="sxs-lookup"><span data-stu-id="198c5-130">(double period)</span></span></td>
<td><span data-ttu-id="198c5-131">Większe lub równe wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="198c5-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="198c5-132">Wpisz wartość, a po niej dwie kropki.</span><span class="sxs-lookup"><span data-stu-id="198c5-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="198c5-133">Wyrażenie <strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="198c5-133"><strong>1000..</strong></span></span> <span data-ttu-id="198c5-134">pozwala wyszukać dowolną liczbę większą lub równą 1000, na przykład &quot;1000&quot;, &quot;1000,01&quot; i &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-135">&gt;<em>wartość</em> (znak „większe niż”)</span><span class="sxs-lookup"><span data-stu-id="198c5-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="198c5-136">Większe od wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="198c5-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="198c5-137">Wpisz znak „większe niż” (<strong>&gt;</strong>), a następnie wartość.</span><span class="sxs-lookup"><span data-stu-id="198c5-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="198c5-138">Wyrażenie <strong>&gt;1000</strong> pozwala wyszukać dowolną liczbę większą niż 1000, np. &quot;1000,01&quot;, &quot;20 000&quot; i &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-139">&lt;<em>wartość</em> (znak „mniejsze niż”)</span><span class="sxs-lookup"><span data-stu-id="198c5-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="198c5-140">Mniejsze od wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="198c5-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="198c5-141">Wpisz znak „mniejsze niż” (<strong>&lt;</strong>), a następnie wartość.</span><span class="sxs-lookup"><span data-stu-id="198c5-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="198c5-142">Wyrażenie <strong>&lt;1000</strong> pozwala wyszukać dowolną liczbę mniejszą niż 1000, np. &quot;999,99&quot;, &quot;1&quot; i &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-143"><em>wartość</em>\* (gwiazdka)</span><span class="sxs-lookup"><span data-stu-id="198c5-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="198c5-144">Począwszy od wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="198c5-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="198c5-145">Wpisz wartość początkową, a następnie gwiazdkę (<strong>\*</strong>).</span><span class="sxs-lookup"><span data-stu-id="198c5-145">Type the starting value and then an asterisk (<strong>\*</strong>).</span></span></td>
<td><span data-ttu-id="198c5-146">Wyrażenie <strong>S\*</strong> pozwala wyszukać wszystkie ciągi znaków rozpoczynające się literą &quot;S&quot;, takie jak &quot;Sztokholm&quot;, &quot;Sydney&quot; i &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-146"><strong>S\*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-147">\*<em>wartość</em> (gwiazdka)</span><span class="sxs-lookup"><span data-stu-id="198c5-147">\*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="198c5-148">Kończące się wprowadzoną wartością</span><span class="sxs-lookup"><span data-stu-id="198c5-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="198c5-149">Wpisz gwiazdkę, a następnie wartość końcową.</span><span class="sxs-lookup"><span data-stu-id="198c5-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="198c5-150">Wyrażenie <strong>\*chód</strong> pozwala wyszukać wszystkie ciągi znaków kończące się literami &quot;chód&quot;, takie jak &quot;Wschód&quot; i &quot;Zachód&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-150"><strong>\*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-151">*<em>wartość</em>* (gwiazdka)</span><span class="sxs-lookup"><span data-stu-id="198c5-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="198c5-152">Zawiera wprowadzoną wartość</span><span class="sxs-lookup"><span data-stu-id="198c5-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="198c5-153">Wpisz gwiazdkę, a po niej wartość i kolejną gwiazdkę.</span><span class="sxs-lookup"><span data-stu-id="198c5-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="198c5-154">Wyrażenie <strong>*ch*</strong> pozwala wyszukać wszystkie ciągi znaków zawierające litery &quot;ch&quot;, takie jak &quot;Wschód&quot; i &quot;Zachód&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-155">?</span><span class="sxs-lookup"><span data-stu-id="198c5-155">?</span></span> <span data-ttu-id="198c5-156">(pytajnik)</span><span class="sxs-lookup"><span data-stu-id="198c5-156">(question mark)</span></span></td>
<td><span data-ttu-id="198c5-157">Posiadające co najmniej jeden nieznany znak.</span><span class="sxs-lookup"><span data-stu-id="198c5-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="198c5-158">Wpisz pytajnik w miejscu nieznanego znaku w wartości.</span><span class="sxs-lookup"><span data-stu-id="198c5-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="198c5-159">Wyrażenie <strong>Now?k</strong> pozwala wyszukać &quot;Nowak&quot; i &quot;Nowik&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-160"><em>wartość</em>,<em>wartość</em> (przecinek)</span><span class="sxs-lookup"><span data-stu-id="198c5-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="198c5-161">Zgodne z wprowadzonymi wartościami, rozdzielonymi przecinkami</span><span class="sxs-lookup"><span data-stu-id="198c5-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="198c5-162">Wpisz wszystkie kryteria, rozdzielając je przecinkami.</span><span class="sxs-lookup"><span data-stu-id="198c5-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="198c5-163">Wyrażenie <strong>A, D, F, G</strong> pozwala wyszukać dokładnie &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, i &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="198c5-164">Wyrażenie <strong>10, 20, 30, 100</strong> pozwala wyszukać dokładnie &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="198c5-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-165">„” (dwa podwójne cudzysłowy)</span><span class="sxs-lookup"><span data-stu-id="198c5-165">"" (two double quotes)</span></span></td>
<td><span data-ttu-id="198c5-166">Dopasowywanie wartości pustej</span><span class="sxs-lookup"><span data-stu-id="198c5-166">Matching a blank value</span></span></td>
<td><span data-ttu-id="198c5-167">Wpisz dwa kolejne podwójne cudzysłowy, aby odfiltrować puste wartości w tym polu.</span><span class="sxs-lookup"><span data-stu-id="198c5-167">Type two consecutive double quotes to filter for blank values in that field.</span></span></td>
<td><span data-ttu-id="198c5-168">Dwa kolejne podwójne cudzysłowy (<strong>""</strong>) spowodują wyszukanie wierszy bez wartości dla bieżącej kolumny.</span><span class="sxs-lookup"><span data-stu-id="198c5-168">Two consecutive double quotes (<strong>""</strong>) finds rows with no value for the current column.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-169">(<span class="code">Finance and Operations kwerenda</span>) (Finance and Operations kwerenda między nawiasami)</span><span class="sxs-lookup"><span data-stu-id="198c5-169">(<span class="code">Finance and Operations query</span>) (Finance and Operations query between parentheses)</span></span></td>
<td><span data-ttu-id="198c5-170">Zgodne ze wskazaną kwerendą.</span><span class="sxs-lookup"><span data-stu-id="198c5-170">Matching a defined query</span></span></td>
<td><span data-ttu-id="198c5-171">Umożliwia wpisanie kwerendy w postaci instrukcji SQL między nawiasami za pomocą języka kwerendy rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="198c5-171">Type a query as an SQL statement between parentheses using the Finance and Operations query language.</span></span></td>
  <td><span data-ttu-id="198c5-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span><span class="sxs-lookup"><span data-stu-id="198c5-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span></span><br><br> 
       <span data-ttu-id="198c5-173">przykładem składni warunku filtru dla pola z głównego źródła danych, a także pola z innego źródła danych (na stronie wszyscy odbiorcy)</span><span class="sxs-lookup"><span data-stu-id="198c5-173">as an example of syntax for a filter condition on a field from the root datasource as well as a field from a different datasource (for the All customers page)</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-174">W</span><span class="sxs-lookup"><span data-stu-id="198c5-174">T</span></span></td>
<td><span data-ttu-id="198c5-175">Data dzisiejsza</span><span class="sxs-lookup"><span data-stu-id="198c5-175">Today's date</span></span></td>
<td><span data-ttu-id="198c5-176">Wpisz <strong>T</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-176">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="198c5-177"><strong>T</strong> pasuje do bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="198c5-177"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="198c5-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> metoda w nawiasach)</span><span class="sxs-lookup"><span data-stu-id="198c5-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="198c5-179">Dopasowanie wartości lub zakresu wartości określonych przez parametry metody <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="198c5-179">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="198c5-180">Wpisz metodę <strong>SysQueryRangeUtil</strong> z parametrami, które określają wartość lub zakres wartości.</span><span class="sxs-lookup"><span data-stu-id="198c5-180">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td>
<ol>
<li><span data-ttu-id="198c5-181">Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Otwarte faktury odbiorcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-181">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="198c5-182">Naciśnij kombinację klawiszy Ctrl + Shift + F3, aby otworzyć stronę <strong>Informacje</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-182">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="198c5-183">Na karcie <strong>Zakres</strong> kliknij przycisk <strong>Dodaj</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-183">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="198c5-184">W polu <strong>Tabela</strong> wybierz <strong>Otwarte transakcje odbiorcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-184">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="198c5-185">W polu <strong>Pole</strong> wybierz <strong>Termin</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-185">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="198c5-186">W polu <strong>Kryteria</strong> wpisz <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-186">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="198c5-187">Kliknij przycisk <strong>OK</strong></span><span class="sxs-lookup"><span data-stu-id="198c5-187">Click <strong>OK</strong>.</span></span> <span data-ttu-id="198c5-188">Strona listy jest aktualizowana i pojawiają się faktury pasujące do wpisanych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="198c5-188">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="198c5-189">W tym przykładzie faktury należne w ciągu ostatnich dwóch lat, są wymienione.</span><span class="sxs-lookup"><span data-stu-id="198c5-189">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="198c5-190">Zobacz tabelę w następnej sekcji, aby uzyskać szczegóły o metodzie wprowadzania daty <strong>SysQueryRangeUtil</strong> oraz kilka przykładów.</span><span class="sxs-lookup"><span data-stu-id="198c5-190">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="198c5-191">Zaawansowane kwerendy danych używające metod SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="198c5-191">Advanced date queries that use SysQueryRangeUtil methods</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="198c5-192">Metoda</span><span class="sxs-lookup"><span data-stu-id="198c5-192">Method</span></span></th>
<th><span data-ttu-id="198c5-193">Opis</span><span class="sxs-lookup"><span data-stu-id="198c5-193">Description</span></span></th>
<th><span data-ttu-id="198c5-194">Przykład</span><span class="sxs-lookup"><span data-stu-id="198c5-194">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="198c5-195">Day (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="198c5-195">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="198c5-196">Znajdowanie daty względem daty sesji.</span><span class="sxs-lookup"><span data-stu-id="198c5-196">Find a date relative to the session date.</span></span> <span data-ttu-id="198c5-197">Wartości dodatnie wskazują na przyszłe daty, a wartości ujemne na daty w przeszłości.</span><span class="sxs-lookup"><span data-stu-id="198c5-197">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="198c5-198"><strong>Jutro</strong> — wpisz <strong>(Day(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-198"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="198c5-199"><strong>Dziś</strong> — wpisz <strong>(Day(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-199"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="198c5-200"><strong>Wczoraj</strong> — wpisz <strong>(Day(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-200"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="198c5-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="198c5-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="198c5-202">Znajdowanie zakresu dat względem daty sesji.</span><span class="sxs-lookup"><span data-stu-id="198c5-202">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="198c5-203">Wartości dodatnie wskazują na przyszłe daty, a wartości ujemne na daty w przeszłości.</span><span class="sxs-lookup"><span data-stu-id="198c5-203">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="198c5-204"><strong>Ostatnie 30 dni</strong> — wpisz <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-204"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="198c5-205"><strong>Poprzednie 30 dni i następne 30 dni</strong> — wpisz <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-205"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="198c5-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="198c5-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="198c5-207">Znajdowanie wszystkich dat po określonej dacie względnej.</span><span class="sxs-lookup"><span data-stu-id="198c5-207">Find all dates after the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="198c5-208"><strong>Więcej niż 30 dni od teraz</strong> — wpisz <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-208"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="198c5-209">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="198c5-209">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="198c5-210">Znajdowanie wpisów daty/godziny po godzinie bieżącej.</span><span class="sxs-lookup"><span data-stu-id="198c5-210">Find all date/time entries after the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="198c5-211"><strong>Wszystkie przyszłe daty/godziny</strong> — wpisz <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-211"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="198c5-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="198c5-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="198c5-213">Znajdowanie wszystkich dat przed określoną datą względną.</span><span class="sxs-lookup"><span data-stu-id="198c5-213">Find all dates before the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="198c5-214"><strong>Mniej niż siedem dni od teraz</strong> — wpisz <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-214"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="198c5-215">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="198c5-215">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="198c5-216">Znajdowanie wpisów daty/godziny przed godziną bieżącą.</span><span class="sxs-lookup"><span data-stu-id="198c5-216">Find all date/time entries before the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="198c5-217"><strong>Wszystkie od daty/godziny</strong> — wpisz <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-217"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="198c5-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="198c5-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="198c5-219">Znajdowanie zakresu dat według miesięcy względem bieżącego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="198c5-219">Find a range of dates, based on months relative to the current month.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="198c5-220"><strong>Poprzednie dwa miesiące</strong> — wpisz <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-220"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="198c5-221"><strong>Następne trzy miesiące</strong> — wpisz <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-221"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="198c5-222">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="198c5-222">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="198c5-223">Znajdowanie zakresu dat według lat względem bieżącego roku.</span><span class="sxs-lookup"><span data-stu-id="198c5-223">Find a range of dates, based on years relative to the current year.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="198c5-224"><strong>Następny roku</strong> — wpisz <strong>(YearRange (0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-224"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="198c5-225"><strong>Poprzedni roku</strong> — wpisz <strong>(YearRange (-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="198c5-225"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]