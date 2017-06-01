---
title: "Pakiet zawartości usługi Power BI Analiza wydatków zakupowych"
description: "W tym temacie opisano, co się znajduje w pakiecie zawartości Analiza wydatków zakupowych dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach używanych do zbudowania pakietu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ad0ee95113d05710cccc1a5e9d215b38244c2047
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Pakiet zawartości usługi Power BI Analiza wydatków zakupowych

[!include[banner](../includes/banner.md)]


W tym temacie opisano, co się znajduje w pakiecie zawartości Analiza wydatków zakupowych dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach używanych do zbudowania pakietu.

<a name="overview"></a>Przegląd
--------

Pakiet zawartości Analiza wydatków zakupowych dla usługi Microsoft Power BI został utworzony dla menedżerów ds. zakupów i menedżerów odpowiedzialnych za budżety. Ma im pomóc na bieżąco pilnować wydatków zakupowych. Wykorzystuje dane transakcyjne zakupów z programu Microsoft Dynamics 365 for Operations i przedstawia zarówno zagregowany widok danych zakupowych w całej firmie, jak i podział wydatków zakupowych na dostawców i produkty. Raporty eksponują zmiany wydatków zakupowych w horyzoncie czasowym. W związku z tym mogą służyć do ostrzegania menedżerów o pozytywnych i negatywnych trendach wydatków dla poszczególnych dostawców i produktów. Wykresy pokazują wydatki zakupowe dla różnych kategorii zaopatrzenia i grup dostawców. Menedżerowie kategorii i kierownicy regionalni docenią przydatność tych wykresów w identyfikowaniu zmian w zachowaniach wydatkowych. Pakiet zawartości umożliwia menedżerom ds. zakupów i menedżerom odpowiedzialnym za budżety analizowanie wydatków zakupowych na szereg sposobów:

-   Zakupy od początku roku (według grupy dostawców i indywidualnych dostawców, kategorii zaopatrzenia, poszczególnych produktów i lokalizacji dostawców)
-   Zmiany wydatków zakupowych rok do roku (według grup dostawców i kategorii zaopatrzenia)

## <a name="accessing-the-content-pack"></a>Przechodzenie do pakietu zawartości
Pakiet zawartości Analiza wydatków zakupowych jest publikowany jako składnik implementacyjny w usłudze Microsoft Dynamics Lifecycle Services (LCS) i można go uruchomić z programu Microsoft Dynamics 365 for Operations. Aby uzyskać więcej informacji dotyczących sposobu uzyskiwania dostępu i otwierania raportów usługi Power BI, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md).
Uwaga: Poprawka KB 4011327 jest wstępnie wymaganym składnikiem tego pakietu zawartości usługi Power BI. Po zalogowaniu się w usłudze Lifecycle Services można uzyskać dostęp do tej poprawki KB tutaj: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="metrics-that-are-included-in-the-content-pack"></a>Wskaźniki dostępne w pakiecie zawartości
Pakiet zawartości Analiza wydatków zakupowych obejmuje raport zawierający zestaw wskaźników. Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele. Następująca tabela zawiera przegląd wizualizacji dostępnych w pakiecie zawartości.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Strona raportu</th>
<th>Wykresy</th>
<th>Kafelki</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zakupy wg dostawców</td>
<td><ul>
<li>10 najważniejszych dostawców wg wartości zakupów (wykres skumulowany słupkowy)</li>
<li>Łączne zakupy wg grupy dostawców/kraju/nazwy (wykres kołowy)</li>
<li>Zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)</li>
<li>Średnie zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)</li>
</ul></td>
<td><ul>
<li>Suma zakupów</li>
<li>Wzrost zakupów r/r</li>
<li>Łączna liczba dostawców</li>
<li>Łączna liczba aktywnych dostawców</li>
</ul></td>
</tr>
<tr class="even">
<td>Zakupy wg produktów</td>
<td><ul>
<li>Zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kolumnowy)</li>
<li>Łączne zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kołowy)</li>
<li>10 najważniejszych produktów wg wartości zakupów (wykres skumulowany słupkowy)</li>
</ul></td>
<td><ul>
<li>Łączna liczba produktów</li>
<li>Procent aktywnych produktów w łącznej liczbie produktów</li>
<li>Liczba produktów odpowiedzialnych za 80% zakupów</li>
</ul></td>
</tr>
<tr class="odd">
<td>Zakupy wg okresu*</td>
<td><ul>
<li>Zakupy wg miesiąca/dnia (wykres kolumnowy)</li>
<li>Odchylenie łącznych zakupów r/r (wykres kaskadowy)</li>
<li>Wzrost łącznych zakupów r/r (wykres kolumnowy)</li>
<li>Zestawienie zaopatrzenia (macierz)</li>
</ul></td>
<td><ul>
<li>Wzrost zakupów r/r</li>
<li>% wzrostu zakupów r/r</li>
</ul></td>
</tr>
<tr class="even">
<td>Zakupy wg lokalizacji dostawców</td>
<td><ul>
<li>Zakupy wg miejscowości</li>
<li>% wzrostu zakupów r/r</li>
<li>Zakupy wg krajów</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Analiza wydatków zakupowych wg okresów</td>
<td><ul>
<li>Zakupy w bieżącym roku wg miesiąca/dnia (wykres liniowy)</li>
<li>Zakupy w bieżącym i ubiegłym roku (wykres liniowy i kolumnowy)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Analiza wydatków zakupowych wg dostawców</td>
<td><ul>
<li>% udziału 10 najważniejszych dostawców w zakupach (wykres lejkowy)</li>
<li>10 dostawców z największym wzrostem wydatków r/r</li>
<li>10 dostawców z największym spadkiem wydatków r/r</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\* Zakupy w tym i ubiegłym roku oraz wzrost według kategorii zaopatrzenia.

## <a name="data-model-and-entities"></a>Model i jednostki danych
W raportach w pakiecie zawartości Analiza wydatków zakupowych są wykorzystywane dane programu Dynamics 365 for Operations. Te dane są przedstawiane jako zagregowane miary umieszczane w magazynie jednostek, który jest bazą danych programu Microsoft SQL zoptymalizowaną pod kątem analiz. Aby uzyskać więcej informacji o magazynie jednostek, zobacz wpis na blogu [Integracja usługi Power BI z magazynem jednostek w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Zagregowane miary w tym pakiecie zawartości są podzbiorem zagregowanych miar, które były dostępne w module Zakupy w programach Microsoft Dynamics AX 2012 i Microsoft Dynamics AX 2012 R3. Aby zagregowane miary modułu można było umieścić w magazynie jednostek, trzeba ustawić te miary jako wdrażalne. Aby uzyskać więcej informacji, zobacz procedurę umieszczania zagregowanych miar w magazynie jednostek we wpisie na blogu [Integracja usługi Power BI z magazynem jednostek w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Następujące najważniejsze zagregowane miary są dostępne bezpośrednio w jednostce Wiersze faktury i używane jako podstawa w pakiecie zawartości:

| Jednostka        | Najważniejsze zagregowane miary | Źródło danych programu Dynamics 365 for Operations | Pole              | opis                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Wiersze faktury | Zakup                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Kwota w walucie rozliczeniowej |

W poniższej tabeli przedstawiono najważniejsze miary, które są obliczane w pakiecie zawartości na podstawie jednostki Wiersze faktury.

| Pomiar               | Obliczenie                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Zakupy w bieżącym roku | Zakupy w bieżącym roku = SUM('Wiersze faktury'\[Zakupy\])                                            |
| Zakupy w ubiegłym roku    | Zakupy w ubiegłym roku = CALCULATE(SUM('Wiersze faktury'\[Zakupy\]), SAMEPERIODLASTYEAR(Daty\[Data\])) |
| Wzrost zakupów r/r   | Wzrost zakupów r/r = \[Zakupy w bieżącym roku\] – \[Zakupy w ubiegłym roku\]                            |

Następujące najważniejsze wymiary w pakiecie zawartości są używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i lepszego wglądu analitycznego.

| Jednostka                 | Przykłady atrybutów                                |
|------------------------|-------------------------------------------------------|
| Dostawcy                | Grupa dostawców, Kraj/region dostawcy, Nazwa dostawcy |
| Produkty               | Numer produktu, Nazwa produktu, Nazwa grupy pozycji        |
| Kategorie zaopatrzenia | Kategoria zaopatrzenia, Nazwa kategorii zaopatrzenia      |
| Firmy         | Nazwa firmy                                     |
| Daty                  | Daty, Przesunięcie roku                                    |

Domyślnie pakiet zawartości przestawia dane bieżącego roku kalendarzowego. Można jednak zmienić wartość filtra dat w sekcji filtrów raportu. Można również zmienić wartość filtra firm.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](..\data-entities\data-entities.md)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](configure-power-bi-integration.md)





