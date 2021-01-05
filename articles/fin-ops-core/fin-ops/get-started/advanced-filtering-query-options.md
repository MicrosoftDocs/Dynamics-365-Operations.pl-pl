---
title: Filtrowanie zaawansowane i składnia zapytań
description: W tym temacie opisano opcje filtrowania i zapytań dostępne podczas używania okna dialogowego Zaawansowane filtrowanie/sortowanie lub operatora jest zgodne z w okienku Filtr lub filtrach nagłówków kolumn siatki.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: b867099b131594a64cad102e50ead7c355594f2b
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694550"
---
# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="eaf1b-103">Filtrowanie zaawansowane i składnia zapytań</span><span class="sxs-lookup"><span data-stu-id="eaf1b-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eaf1b-104">W tym temacie opisano opcje filtrowania i zapytań dostępne podczas używania okna dialogowego Zaawansowane filtrowanie/sortowanie lub operatora **jest zgodne** z w okienku Filtr lub filtrach nagłówków kolumn siatki.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-104">This topic describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span>

## <a name="advanced-query-syntax"></a><span data-ttu-id="eaf1b-105">Składnia zaawansowanych zapytań</span><span class="sxs-lookup"><span data-stu-id="eaf1b-105">Advanced query syntax</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="eaf1b-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="eaf1b-106">Syntax</span></span></th>
<th><span data-ttu-id="eaf1b-107">Opis charakterystyki</span><span class="sxs-lookup"><span data-stu-id="eaf1b-107">Character description</span></span></th>
<th><span data-ttu-id="eaf1b-108">opis</span><span class="sxs-lookup"><span data-stu-id="eaf1b-108">Description</span></span></th>
<th><span data-ttu-id="eaf1b-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="eaf1b-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="eaf1b-110"><em>wartość</em></span><span class="sxs-lookup"><span data-stu-id="eaf1b-110"><em>value</em></span></span></td>
<td><span data-ttu-id="eaf1b-111">Równa wartości, która została wprowadzona.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="eaf1b-112">Wpisz wartość, którą chcesz znaleźć.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="eaf1b-113">Wyrażenie <strong>Nowak</strong> pozwala wyszukać wartość &quot;Nowak&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-114">!<em>wartość</em> (wykrzyknik)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="eaf1b-115">Nie równa wartości, która została wprowadzona.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="eaf1b-116">Wpisz wykrzyknik i wartość którą chcesz wykluczyć.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="eaf1b-117">Wyrażenie <strong>!Nowak</strong> pozwala wyszukać wszystkie wartości z wyjątkiem &quot;Nowak&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-118"><em>Od</em>..<em>Do</em> (dwie kropki)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="eaf1b-119">Między wartościami rozdzielonymi dwoma kropkami</span><span class="sxs-lookup"><span data-stu-id="eaf1b-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="eaf1b-120">Wpisz wartość Od, a po niej dwie kropki i wartość Do.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="eaf1b-121">Wyrażenie <strong>1..10</strong> pozwala wyszukać wszystkie wartości od 1 do 10.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="eaf1b-122">Jednak w polu tekstowym wyrażenie <strong>A..C</strong> pozwala wyszukać wszystkie wartości rozpoczynające się od &quot;A&quot; i &quot;B&quot; oraz dokładnie równe &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="eaf1b-123">To zapytanie nie pozwala na przykład znaleźć wyrażenia &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="eaf1b-124">Aby wyszukać wszystkie wartości od &quot;A<em>&quot; do &quot;C</em>&quot; włącznie, wpisz <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-125">..<em>wartość</em> (dwie kropki)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="eaf1b-126">Mniejsze lub równe wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="eaf1b-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="eaf1b-127">Wpisz dwie kropki, a następnie wartość.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="eaf1b-128">Wyrażenie <strong>..1000</strong> pozwala wyszukać dowolną liczbę mniejszą lub równą 1000, na przykład &quot;100&quot;, &quot;999,95&quot; i &quot;1000&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-129"><em>wartość</em>..</span><span class="sxs-lookup"><span data-stu-id="eaf1b-129"><em>value</em>..</span></span> <span data-ttu-id="eaf1b-130">(dwie kropki)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-130">(double period)</span></span></td>
<td><span data-ttu-id="eaf1b-131">Większe lub równe wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="eaf1b-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="eaf1b-132">Wpisz wartość, a po niej dwie kropki.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="eaf1b-133">Wyrażenie <strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="eaf1b-133"><strong>1000..</strong></span></span> <span data-ttu-id="eaf1b-134">pozwala wyszukać dowolną liczbę większą lub równą 1000, na przykład &quot;1000&quot;, &quot;1000,01&quot; i &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-135">&gt;<em>wartość</em> (znak „większe niż”)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="eaf1b-136">Większe od wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="eaf1b-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="eaf1b-137">Wpisz znak „większe niż” (<strong>&gt;</strong>), a następnie wartość.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="eaf1b-138">Wyrażenie <strong>&gt;1000</strong> pozwala wyszukać dowolną liczbę większą niż 1000, np. &quot;1000,01&quot;, &quot;20 000&quot; i &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-139">&lt;<em>wartość</em> (znak „mniejsze niż”)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="eaf1b-140">Mniejsze od wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="eaf1b-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="eaf1b-141">Wpisz znak „mniejsze niż” (<strong>&lt;</strong>), a następnie wartość.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="eaf1b-142">Wyrażenie <strong>&lt;1000</strong> pozwala wyszukać dowolną liczbę mniejszą niż 1000, np. &quot;999,99&quot;, &quot;1&quot; i &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-143"><em>wartość</em>\* (gwiazdka)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="eaf1b-144">Począwszy od wprowadzonej wartości</span><span class="sxs-lookup"><span data-stu-id="eaf1b-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="eaf1b-145">Wpisz wartość początkową, a następnie gwiazdkę (<strong>\*</strong>).</span><span class="sxs-lookup"><span data-stu-id="eaf1b-145">Type the starting value and then an asterisk (<strong>\*</strong>).</span></span></td>
<td><span data-ttu-id="eaf1b-146">Wyrażenie <strong>S\*</strong> pozwala wyszukać wszystkie ciągi znaków rozpoczynające się literą &quot;S&quot;, takie jak &quot;Sztokholm&quot;, &quot;Sydney&quot; i &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-146"><strong>S\*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-147">\*<em>wartość</em> (gwiazdka)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-147">\*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="eaf1b-148">Kończące się wprowadzoną wartością</span><span class="sxs-lookup"><span data-stu-id="eaf1b-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="eaf1b-149">Wpisz gwiazdkę, a następnie wartość końcową.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="eaf1b-150">Wyrażenie <strong>\*chód</strong> pozwala wyszukać wszystkie ciągi znaków kończące się literami &quot;chód&quot;, takie jak &quot;Wschód&quot; i &quot;Zachód&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-150"><strong>\*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-151">*<em>wartość</em>* (gwiazdka)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="eaf1b-152">Zawiera wprowadzoną wartość</span><span class="sxs-lookup"><span data-stu-id="eaf1b-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="eaf1b-153">Wpisz gwiazdkę, a po niej wartość i kolejną gwiazdkę.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="eaf1b-154">Wyrażenie <strong>*ch*</strong> pozwala wyszukać wszystkie ciągi znaków zawierające litery &quot;ch&quot;, takie jak &quot;Wschód&quot; i &quot;Zachód&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-155">?</span><span class="sxs-lookup"><span data-stu-id="eaf1b-155">?</span></span> <span data-ttu-id="eaf1b-156">(pytajnik)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-156">(question mark)</span></span></td>
<td><span data-ttu-id="eaf1b-157">Posiadające co najmniej jeden nieznany znak.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="eaf1b-158">Wpisz pytajnik w miejscu nieznanego znaku w wartości.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="eaf1b-159">Wyrażenie <strong>Now?k</strong> pozwala wyszukać &quot;Nowak&quot; i &quot;Nowik&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-160"><em>wartość</em>,<em>wartość</em> (przecinek)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="eaf1b-161">Zgodne z wprowadzonymi wartościami, rozdzielonymi przecinkami</span><span class="sxs-lookup"><span data-stu-id="eaf1b-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="eaf1b-162">Wpisz wszystkie kryteria, rozdzielając je przecinkami.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="eaf1b-163">Wyrażenie <strong>A, D, F, G</strong> pozwala wyszukać dokładnie &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, i &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="eaf1b-164">Wyrażenie <strong>10, 20, 30, 100</strong> pozwala wyszukać dokładnie &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-165">„” (dwa podwójne cudzysłowy)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-165">"" (two double quotes)</span></span></td>
<td><span data-ttu-id="eaf1b-166">Dopasowywanie wartości pustej</span><span class="sxs-lookup"><span data-stu-id="eaf1b-166">Matching a blank value</span></span></td>
<td><span data-ttu-id="eaf1b-167">Wpisz dwa kolejne podwójne cudzysłowy, aby odfiltrować puste wartości w tym polu.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-167">Type two consecutive double quotes to filter for blank values in that field.</span></span></td>
<td><span data-ttu-id="eaf1b-168">Dwa kolejne podwójne cudzysłowy (<strong>""</strong>) spowodują wyszukanie wierszy bez wartości dla bieżącej kolumny.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-168">Two consecutive double quotes (<strong>""</strong>) finds rows with no value for the current column.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-169">(<span class="code">Finance and Operations kwerenda</span>) (Finance and Operations kwerenda między nawiasami)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-169">(<span class="code">Finance and Operations query</span>) (Finance and Operations query between parentheses)</span></span></td>
<td><span data-ttu-id="eaf1b-170">Zgodne ze wskazaną kwerendą.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-170">Matching a defined query</span></span></td>
<td><span data-ttu-id="eaf1b-171">Umożliwia wpisanie kwerendy w postaci instrukcji SQL między nawiasami za pomocą języka kwerendy rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-171">Type a query as an SQL statement between parentheses using the Finance and Operations query language.</span></span></td>
  <td><span data-ttu-id="eaf1b-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span><span class="sxs-lookup"><span data-stu-id="eaf1b-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span></span><br><br> 
       <span data-ttu-id="eaf1b-173">przykładem składni warunku filtru dla pola z głównego źródła danych, a także pola z innego źródła danych (na stronie wszyscy odbiorcy)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-173">as an example of syntax for a filter condition on a field from the root datasource as well as a field from a different datasource (for the All customers page)</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-174">W</span><span class="sxs-lookup"><span data-stu-id="eaf1b-174">T</span></span></td>
<td><span data-ttu-id="eaf1b-175">Data dzisiejsza</span><span class="sxs-lookup"><span data-stu-id="eaf1b-175">Today's date</span></span></td>
<td><span data-ttu-id="eaf1b-176">Wpisz <strong>T</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-176">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="eaf1b-177"><strong>T</strong> pasuje do bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-177"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> metoda w nawiasach)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="eaf1b-179">Dopasowanie wartości lub zakresu wartości określonych przez parametry metody <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="eaf1b-179">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="eaf1b-180">Wpisz metodę <strong>SysQueryRangeUtil</strong> z parametrami, które określają wartość lub zakres wartości.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-180">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td>
<ol>
<li><span data-ttu-id="eaf1b-181">Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Otwarte faktury odbiorcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-181">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-182">Naciśnij kombinację klawiszy Ctrl + Shift + F3, aby otworzyć stronę <strong>Informacje</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-182">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="eaf1b-183">Na karcie <strong>Zakres</strong> kliknij przycisk <strong>Dodaj</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-183">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-184">W polu <strong>Tabela</strong> wybierz <strong>Otwarte transakcje odbiorcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-184">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-185">W polu <strong>Pole</strong> wybierz <strong>Termin</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-185">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-186">W polu <strong>Kryteria</strong> wpisz <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-186">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-187">Kliknij przycisk <strong>OK</strong></span><span class="sxs-lookup"><span data-stu-id="eaf1b-187">Click <strong>OK</strong>.</span></span> <span data-ttu-id="eaf1b-188">Strona listy jest aktualizowana i pojawiają się faktury pasujące do wpisanych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-188">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="eaf1b-189">W tym przykładzie faktury należne w ciągu ostatnich dwóch lat, są wymienione.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-189">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="eaf1b-190">Zobacz tabelę w następnej sekcji, aby uzyskać szczegóły o metodzie wprowadzania daty <strong>SysQueryRangeUtil</strong> oraz kilka przykładów.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-190">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="eaf1b-191">Zaawansowane kwerendy danych używające metod SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="eaf1b-191">Advanced date queries that use SysQueryRangeUtil methods</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="eaf1b-192">Metoda</span><span class="sxs-lookup"><span data-stu-id="eaf1b-192">Method</span></span></th>
<th><span data-ttu-id="eaf1b-193">Opis</span><span class="sxs-lookup"><span data-stu-id="eaf1b-193">Description</span></span></th>
<th><span data-ttu-id="eaf1b-194">Przykład</span><span class="sxs-lookup"><span data-stu-id="eaf1b-194">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="eaf1b-195">Day (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-195">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="eaf1b-196">Znajdowanie daty względem daty sesji.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-196">Find a date relative to the session date.</span></span> <span data-ttu-id="eaf1b-197">Wartości dodatnie wskazują na przyszłe daty, a wartości ujemne na daty w przeszłości.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-197">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="eaf1b-198"><strong>Jutro</strong> — wpisz <strong>(Day(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-198"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-199"><strong>Dziś</strong> — wpisz <strong>(Day(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-199"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-200"><strong>Wczoraj</strong> — wpisz <strong>(Day(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-200"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="eaf1b-202">Znajdowanie zakresu dat względem daty sesji.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-202">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="eaf1b-203">Wartości dodatnie wskazują na przyszłe daty, a wartości ujemne na daty w przeszłości.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-203">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="eaf1b-204"><strong>Ostatnie 30 dni</strong> — wpisz <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-204"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-205"><strong>Poprzednie 30 dni i następne 30 dni</strong> — wpisz <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-205"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="eaf1b-207">Znajdowanie wszystkich dat po określonej dacie względnej.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-207">Find all dates after the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="eaf1b-208"><strong>Więcej niż 30 dni od teraz</strong> — wpisz <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-208"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-209">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="eaf1b-209">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="eaf1b-210">Znajdowanie wpisów daty/godziny po godzinie bieżącej.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-210">Find all date/time entries after the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="eaf1b-211"><strong>Wszystkie przyszłe daty/godziny</strong> — wpisz <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-211"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="eaf1b-213">Znajdowanie wszystkich dat przed określoną datą względną.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-213">Find all dates before the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="eaf1b-214"><strong>Mniej niż siedem dni od teraz</strong> — wpisz <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-214"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-215">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="eaf1b-215">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="eaf1b-216">Znajdowanie wpisów daty/godziny przed godziną bieżącą.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-216">Find all date/time entries before the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="eaf1b-217"><strong>Wszystkie od daty/godziny</strong> — wpisz <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-217"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="eaf1b-219">Znajdowanie zakresu dat według miesięcy względem bieżącego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-219">Find a range of dates, based on months relative to the current month.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="eaf1b-220"><strong>Poprzednie dwa miesiące</strong> — wpisz <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-220"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-221"><strong>Następne trzy miesiące</strong> — wpisz <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-221"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="eaf1b-222">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="eaf1b-222">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="eaf1b-223">Znajdowanie zakresu dat według lat względem bieżącego roku.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-223">Find a range of dates, based on years relative to the current year.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="eaf1b-224"><strong>Następny roku</strong> — wpisz <strong>(YearRange (0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-224"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="eaf1b-225"><strong>Poprzedni roku</strong> — wpisz <strong>(YearRange (-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf1b-225"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
