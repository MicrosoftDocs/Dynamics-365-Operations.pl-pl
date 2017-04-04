---
title: "Analiza zawartości Power BI wydatków zakupu"
description: "W tym temacie opisano, co jest zawarte w nabyciu spędzić pakiet analizy dla Microsoft Power BI. Wyjaśnia, jak uzyskać dostęp do raportów, które są zawarte w pakiecie zawartości i zawiera informacje o modelu danych i podmiotów, które są używane do tworzenia zawartości pack."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-12-30 09 - 40 - 51
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 8cb928cbf1316e63a8c7de833587168cd36a455c
ms.lasthandoff: 03/29/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Analiza zawartości Power BI wydatków zakupu

W tym temacie opisano, co jest zawarte w nabyciu spędzić pakiet analizy dla Microsoft Power BI. Wyjaśnia, jak uzyskać dostęp do raportów, które są zawarte w pakiecie zawartości i zawiera informacje o modelu danych i podmiotów, które są używane do tworzenia zawartości pack.

<a name="overview"></a>Przegląd
--------

Analiza zawartości, że pack dla Microsoft Power BI został utworzony za zakup menedżerów i menedżerowie, którzy są odpowiedzialni za budżety wydatków zakupu. Został zaprojektowany tak, aby pomóc im Zwracaj uwagę na wydatki zakupu. Używa danych transakcyjnych zakupu z Microsoft Dynamics 365 dla operacji i zapewnia zarówno zagregowany widok danych liczbowych zakupu całej firmy i podział wydatków według dostawców i produktów zakupu. Raporty Wyróżniaj zmiany w zakupach wydatków w czasie. W związku z tym ich może służyć do ostrzegania menedżerów o pozytywnych i negatywnych tendencji wydatków dla poszczególnych dostawców i produktów. Wykresy pokazują wydatków dla grup dostawców i kategorie różnych zamówień zakupu. Kategoria i regionalni kierownicy sprzedaży może być przydatna do identyfikowania zmian w wydatkach na zachowanie za pomocą tych wykresów. Content pack menedżerów zakupów i menedżerów, którzy są odpowiedzialni za budżetów Przeanalizujmy zakupu wydatków w następujący sposób:

-   Zakupów od początku roku (przez grupy dostawców poszczególnych dostawców, kategorii zaopatrzenia i poszczególne produkty i lokalizacja dostawcy)
-   Zmiany zakupu z roku na rok (według kategorii grupy i zamówień dostawcy)

## <a name="accessing-the-content-pack"></a>Uzyskiwanie dostępu do zawartości pack
Analiza zawartości pack jest publikowany jako składnik aktywów implementacji w Microsoft Dynamics cyklu życia usługi (LCS) i są dostępne z usługi Microsoft Dynamics 365 dla operacji wydatków zakupu. Aby uzyskać więcej informacji dotyczących sposobu dostępu i otwartych raportów BI zasilania, zobacz [Power BI zawartości w LCS firmy Microsoft i jej partnerzy](power-bi-content-microsoft-partners.md).

## <a name="metrics-that-are-included-in-the-content-pack"></a>Wskaźniki, które są zawarte w pakiecie zawartości
Analiza, że content pack zawiera raport, który zawiera zestaw wskaźników wydatków zakupu. Te wskaźniki są przedstawiane jako wykresy, tabliczki i tabelami. Poniższa tabela zawiera omówienie wizualizacji w pakiecie zawartości.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Strony raportu</th>
<th>Wykresy</th>
<th>Płytki</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zakupu według dostawcy</td>
<td><ul>
<li>10 najlepszych dostawców według zakupów (skumulowany wykres słupkowy)</li>
<li>Całkowite zakupy według dostawców grupy / kraj / nazwa (wykres kołowy)</li>
<li>Zakupy według dostawców grupy / kraj / nazwa (wykres słupkowy)</li>
<li>Średnia zakupu według dostawcy grupy / kraj / nazwa (wykres słupkowy)</li>
</ul></td>
<td><ul>
<li>Suma zakupów</li>
<li>Wzrost zakupu r/r</li>
<li>Łączna liczba dostawców</li>
<li>Całkowita liczba aktywnych dostawców</li>
</ul></td>
</tr>
<tr class="even">
<td>Zakup według produktu</td>
<td><ul>
<li>Zakupy według kategorii zaopatrzenia / nazwa produktu (wykres słupkowy)</li>
<li>Całkowity zakup według kategorii zaopatrzenia / nazwa produktu (wykres kołowy)</li>
<li>10 najlepszych produktów według zakupów (skumulowany wykres słupkowy)</li>
</ul></td>
<td><ul>
<li>Łączna liczba produktów</li>
<li>Łączna liczba produktów active procent całkowita liczba produktów</li>
<li>Liczba produktów rachunkowości w 80% sprzedaży</li>
</ul></td>
</tr>
<tr class="odd">
<td>Zakupu przez okres *</td>
<td><ul>
<li>Zakupu przez miesiąc / dzień (wykres słupkowy)</li>
<li>Rozbieżność r/r zbiorczej zakupu (wykres wodospadu)</li>
<li>Łączny zakup wzrost r/r (wykres słupkowy)</li>
<li>Instrukcja zaopatrzenia (macierz)</li>
</ul></td>
<td><ul>
<li>Wzrost zakupu r/r</li>
<li>% Wzrostu zakupu r/r</li>
</ul></td>
</tr>
<tr class="even">
<td>Zakupu według dostawcy lokalizacji</td>
<td><ul>
<li>Zakup według miast</li>
<li>% Wzrostu r/r zakupu</li>
<li>Zakupu przez kraj</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Analiza wydatków zakupu według czasu</td>
<td><ul>
<li>Zakup bieżącego roku przez miesiąc / dzień (wykres liniowy)</li>
<li>Zakup z bieżącego i poprzedniego roku (wykres wierszy i kolumn)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Analiza przez dostawcę wydatków zakupu</td>
<td><ul>
<li>Pierwsze 10% zakupu dostawcy zakupu (ścieżki)</li>
<li>10 najlepszych dostawców z zwiększenia wydatków r/r</li>
<li>10 najlepszych dostawców z zmniejszenie wydatków r/r</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\*Zakup tego roku i ubiegłego roku i wzrostu według kategorii zaopatrzenia

## <a name="data-model-and-entities"></a>Model danych i podmiotów
Dynamics 365 dla operacji danych jest używany w raporcie zamówienia zakupu spędzić zawartości pakiet do analiz. Te dane jest reprezentowany jako zagregowanych wskaźników, które są umieszczane w magazynie podmiot, który jest bazy danych Microsoft SQL, który jest zoptymalizowany pod kątem analytics. Aby uzyskać więcej informacji o magazynie encji, zobacz [Power BI integracji z magazynem encji w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/) wpis w blogu. Wartość zagregowana pomiary w tym pakiecie zawartości są podzbiór agregacji miar, które były dostępne w module zakupu w systemie Microsoft Dynamics AX 2012 i Microsoft Dynamics 365 dla operacji 2012 R3. Aby przemieścić modułu zagregowanych wskaźników w magazynie encji, należy to zrobić rozmieszczenia. Aby uzyskać więcej informacji, zobacz procedurę dla agregacji miar w magazynie encji w tymczasowej [Power BI integracji z magazynem encji w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/) wpis w blogu. Następujące kluczowe pomiary agregacji są dostępne bezpośrednio z jednostką wierszy faktury i są wykorzystywane jako podstawa content Pack.

| Jednostka        | Klucz zagregowanych wskaźników | Źródło danych dla usługi Dynamics 365 dla operacji | Pole              | opis                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Wiersze faktury | Zakup                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Kwota w walucie rozliczeniowej |

W poniższej tabeli przedstawiono pomiary kluczy, które są obliczane w pakiecie zawartości z tej jednostki wierszy faktury.

| Pomiar               | Obliczenie                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Bieżący rok zakupu | Zakup bieżącego roku = Suma ('Wierszy faktur'\[zakupu\])                                            |
| Ostatni rok zakupu    | Zakupu ostatniego roku = OBLICZ (Suma ('Wierszy faktur'\[zakupu\]), SAMEPERIODLASTYEAR (dat\[data\])) |
| Wzrost zakupu r/r   | Wzrost zakupu r/r = \[zakupu bieżącego roku\] — \[zakupu ostatniego roku\]                            |

Następujące wymiary klucza w pakiecie zawartości są używane jako filtry na fragmenty zagregowanych wskaźników, tak, że można osiągnąć większą szczegółowość i lepszy wgląd analitycznych.

| Jednostka                 | Przykłady atrybutów                                |
|------------------------|-------------------------------------------------------|
| Dostawcy                | Grup dostawców, kraju dostawcy lub regionów, nazwy dostawcy |
| Produkty               | Numer produktu, nazwa produktu, nazwa grupy towaru        |
| Kategorie zaopatrzenia | Kategoria zaopatrzenia, nazwy kategorii zaopatrzenia      |
| Firmy         | Nazwa firmy                                     |
| Daty                  | Dat, przesunięcie roku                                    |

Domyślnie content pack zawiera dane dla bieżącego roku kalendarzowego. Można jednak zmienić filtr daty w sekcji filtry raportu. Można również zmienić filtr firmy.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](..\data-entities\data-entities.md)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](configure-power-bi-integration.md)



