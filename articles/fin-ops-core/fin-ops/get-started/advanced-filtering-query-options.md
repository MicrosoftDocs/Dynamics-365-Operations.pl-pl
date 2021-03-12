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
ms.openlocfilehash: 650f1c209b1797973634c788645a4659bff28f13
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798678"
---
# <a name="advanced-filtering-and-query-syntax"></a>Filtrowanie zaawansowane i składnia zapytań

[!include [banner](../includes/banner.md)]

W tym temacie opisano opcje filtrowania i zapytań dostępne podczas używania okna dialogowego Zaawansowane filtrowanie/sortowanie lub operatora **jest zgodne** z w okienku Filtr lub filtrach nagłówków kolumn siatki.

## <a name="advanced-query-syntax"></a>Składnia zaawansowanych zapytań

<table>
<thead>
<tr>
<th>Składnia</th>
<th>Opis charakterystyki</th>
<th>opis</th>
<th>Przykład</th>
</tr>
</thead>
<tbody>
<tr>
<td><em>wartość</em></td>
<td>Równa wartości, która została wprowadzona.</td>
<td>Wpisz wartość, którą chcesz znaleźć.</td>
<td>Wyrażenie <strong>Nowak</strong> pozwala wyszukać wartość &quot;Nowak&quot;.</td>
</tr>
<tr>
<td>!<em>wartość</em> (wykrzyknik)</td>
<td>Nie równa wartości, która została wprowadzona.</td>
<td>Wpisz wykrzyknik i wartość którą chcesz wykluczyć.</td>
<td>Wyrażenie <strong>!Nowak</strong> pozwala wyszukać wszystkie wartości z wyjątkiem &quot;Nowak&quot;.</td>
</tr>
<tr>
<td><em>Od</em>..<em>Do</em> (dwie kropki)</td>
<td>Między wartościami rozdzielonymi dwoma kropkami</td>
<td>Wpisz wartość Od, a po niej dwie kropki i wartość Do.</td>
<td>Wyrażenie <strong>1..10</strong> pozwala wyszukać wszystkie wartości od 1 do 10. Jednak w polu tekstowym wyrażenie <strong>A..C</strong> pozwala wyszukać wszystkie wartości rozpoczynające się od &quot;A&quot; i &quot;B&quot; oraz dokładnie równe &quot;C&quot;. To zapytanie nie pozwala na przykład znaleźć wyrażenia &quot;Ca&quot;. Aby wyszukać wszystkie wartości od &quot;A<em>&quot; do &quot;C</em>&quot; włącznie, wpisz <strong>A..D</strong>.</td>
</tr>
<tr>
<td>..<em>wartość</em> (dwie kropki)</td>
<td>Mniejsze lub równe wprowadzonej wartości</td>
<td>Wpisz dwie kropki, a następnie wartość.</td>
<td>Wyrażenie <strong>..1000</strong> pozwala wyszukać dowolną liczbę mniejszą lub równą 1000, na przykład &quot;100&quot;, &quot;999,95&quot; i &quot;1000&quot;.</td>
</tr>
<tr>
<td><em>wartość</em>.. (dwie kropki)</td>
<td>Większe lub równe wprowadzonej wartości</td>
<td>Wpisz wartość, a po niej dwie kropki.</td>
<td>Wyrażenie <strong>1000..</strong> pozwala wyszukać dowolną liczbę większą lub równą 1000, na przykład &quot;1000&quot;, &quot;1000,01&quot; i &quot;1 000 000&quot;.</td>
</tr>
<tr>
<td>&gt;<em>wartość</em> (znak „większe niż”)</td>
<td>Większe od wprowadzonej wartości</td>
<td>Wpisz znak „większe niż” (<strong>&gt;</strong>), a następnie wartość.</td>
<td>Wyrażenie <strong>&gt;1000</strong> pozwala wyszukać dowolną liczbę większą niż 1000, np. &quot;1000,01&quot;, &quot;20 000&quot; i &quot;1 000 000&quot;.</td>
</tr>
<tr>
<td>&lt;<em>wartość</em> (znak „mniejsze niż”)</td>
<td>Mniejsze od wprowadzonej wartości</td>
<td>Wpisz znak „mniejsze niż” (<strong>&lt;</strong>), a następnie wartość.</td>
<td>Wyrażenie <strong>&lt;1000</strong> pozwala wyszukać dowolną liczbę mniejszą niż 1000, np. &quot;999,99&quot;, &quot;1&quot; i &quot;-200&quot;.</td>
</tr>
<tr>
<td><em>wartość</em>* (gwiazdka)</td>
<td>Począwszy od wprowadzonej wartości</td>
<td>Wpisz wartość początkową, a następnie gwiazdkę (<strong>*</strong>).</td>
<td>Wyrażenie <strong>S*</strong> pozwala wyszukać wszystkie ciągi znaków rozpoczynające się literą &quot;S&quot;, takie jak &quot;Sztokholm&quot;, &quot;Sydney&quot; i &quot;San Francisco&quot;.</td>
</tr>
<tr>
<td>*<em>wartość</em> (gwiazdka)</td>
<td>Kończące się wprowadzoną wartością</td>
<td>Wpisz gwiazdkę, a następnie wartość końcową.</td>
<td>Wyrażenie <strong>*chód</strong> pozwala wyszukać wszystkie ciągi znaków kończące się literami &quot;chód&quot;, takie jak &quot;Wschód&quot; i &quot;Zachód&quot;.</td>
</tr>
<tr>
<td>*<em>wartość</em>* (gwiazdka)</td>
<td>Zawiera wprowadzoną wartość</td>
<td>Wpisz gwiazdkę, a po niej wartość i kolejną gwiazdkę.</td>
<td>Wyrażenie <strong>*ch*</strong> pozwala wyszukać wszystkie ciągi znaków zawierające litery &quot;ch&quot;, takie jak &quot;Wschód&quot; i &quot;Zachód&quot;.</td>
</tr>
<tr>
<td>? (pytajnik)</td>
<td>Posiadające co najmniej jeden nieznany znak.</td>
<td>Wpisz pytajnik w miejscu nieznanego znaku w wartości.</td>
<td>Wyrażenie <strong>Now?k</strong> pozwala wyszukać &quot;Nowak&quot; i &quot;Nowik&quot;.</td>
</tr>
<tr>
<td><em>wartość</em>,<em>wartość</em> (przecinek)</td>
<td>Zgodne z wprowadzonymi wartościami, rozdzielonymi przecinkami</td>
<td>Wpisz wszystkie kryteria, rozdzielając je przecinkami.</td>
<td>Wyrażenie <strong>A, D, F, G</strong> pozwala wyszukać dokładnie &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, i &quot;G&quot;. Wyrażenie <strong>10, 20, 30, 100</strong> pozwala wyszukać dokładnie &quot;10, 20, 30, 100&quot;.</td>
</tr>
<tr>
<td>„” (dwa podwójne cudzysłowy)</td>
<td>Dopasowywanie wartości pustej</td>
<td>Wpisz dwa kolejne podwójne cudzysłowy, aby odfiltrować puste wartości w tym polu.</td>
<td>Dwa kolejne podwójne cudzysłowy (<strong>""</strong>) spowodują wyszukanie wierszy bez wartości dla bieżącej kolumny.</td>
</tr>
<tr>
<td>(<span class="code">Finance and Operations kwerenda</span>) (Finance and Operations kwerenda między nawiasami)</td>
<td>Zgodne ze wskazaną kwerendą.</td>
<td>Umożliwia wpisanie kwerendy w postaci instrukcji SQL między nawiasami za pomocą języka kwerendy rozwiązania Finance and Operations.</td>
  <td><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong><br><br> 
       przykładem składni warunku filtru dla pola z głównego źródła danych, a także pola z innego źródła danych (na stronie wszyscy odbiorcy)</td>
</tr>
<tr>
<td>W</td>
<td>Data dzisiejsza</td>
<td>Wpisz <strong>T</strong>.</td>
<td><strong>T</strong> pasuje do bieżącej daty.</td>
</tr>
<tr>
<td>(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> metoda w nawiasach)</td>
<td>Dopasowanie wartości lub zakresu wartości określonych przez parametry metody <strong>SysQueryRangeUtil</strong></td>
<td>Wpisz metodę <strong>SysQueryRangeUtil</strong> z parametrami, które określają wartość lub zakres wartości.</td>
<td>
<ol>
<li>Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Otwarte faktury odbiorcy</strong>.</li>
<li>Naciśnij kombinację klawiszy Ctrl + Shift + F3, aby otworzyć stronę <strong>Informacje</strong>.</li>
<li>Na karcie <strong>Zakres</strong> kliknij przycisk <strong>Dodaj</strong>.</li>
<li>W polu <strong>Tabela</strong> wybierz <strong>Otwarte transakcje odbiorcy</strong>.</li>
<li>W polu <strong>Pole</strong> wybierz <strong>Termin</strong>.</li>
<li>W polu <strong>Kryteria</strong> wpisz <strong>(yearRange(-2,0))</strong>.</li>
<li>Kliknij przycisk <strong>OK</strong> Strona listy jest aktualizowana i pojawiają się faktury pasujące do wpisanych kryteriów. W tym przykładzie faktury należne w ciągu ostatnich dwóch lat, są wymienione.</li>
</ol>
Zobacz tabelę w następnej sekcji, aby uzyskać szczegóły o metodzie wprowadzania daty <strong>SysQueryRangeUtil</strong> oraz kilka przykładów.</td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a>Zaawansowane kwerendy danych używające metod SysQueryRangeUtil

<table>
<thead>
<tr>
<th>Metoda</th>
<th>Opis</th>
<th>Przykład</th>
</tr>
</thead>
<tbody>
<tr>
<td>Day (_relativeDays=0)</td>
<td>Znajdowanie daty względem daty sesji. Wartości dodatnie wskazują na przyszłe daty, a wartości ujemne na daty w przeszłości.</td>
<td>
<ul>
<li><strong>Jutro</strong> — wpisz <strong>(Day(1))</strong>.</li>
<li><strong>Dziś</strong> — wpisz <strong>(Day(0))</strong>.</li>
<li><strong>Wczoraj</strong> — wpisz <strong>(Day(-1))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Znajdowanie zakresu dat względem daty sesji. Wartości dodatnie wskazują na przyszłe daty, a wartości ujemne na daty w przeszłości.</td>
<td>
<ul>
<li><strong>Ostatnie 30 dni</strong> — wpisz <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>Poprzednie 30 dni i następne 30 dni</strong> — wpisz <strong>(DayRange(-30,30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>Znajdowanie wszystkich dat po określonej dacie względnej.</td>
<td>
<ul>
<li><strong>Więcej niż 30 dni od teraz</strong> — wpisz <strong>(GreaterThanDate(30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanUtcNow ()</td>
<td>Znajdowanie wpisów daty/godziny po godzinie bieżącej.</td>
<td>
<ul>
<li><strong>Wszystkie przyszłe daty/godziny</strong> — wpisz <strong>(GreaterThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>Znajdowanie wszystkich dat przed określoną datą względną.</td>
<td>
<ul>
<li><strong>Mniej niż siedem dni od teraz</strong> — wpisz <strong>(LessThanDate(7))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanUtcNow ()</td>
<td>Znajdowanie wpisów daty/godziny przed godziną bieżącą.</td>
<td>
<ul>
<li><strong>Wszystkie od daty/godziny</strong> — wpisz <strong>(LessThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Znajdowanie zakresu dat według miesięcy względem bieżącego miesiąca.</td>
<td>
<ul>
<li><strong>Poprzednie dwa miesiące</strong> — wpisz <strong>(MonthRange(-2,0))</strong>.</li>
<li><strong>Następne trzy miesiące</strong> — wpisz <strong>(MonthRange(0,3))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Znajdowanie zakresu dat według lat względem bieżącego roku.</td>
<td>
<ul>
<li><strong>Następny roku</strong> — wpisz <strong>(YearRange (0, 1))</strong>.</li>
<li><strong>Poprzedni roku</strong> — wpisz <strong>(YearRange (-1,0))</strong>.</li>
</ul>
</td>
</tr>
</tbody>
</table>
