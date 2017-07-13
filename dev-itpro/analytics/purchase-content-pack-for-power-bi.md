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
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: daba17aed7e6cc475a16d6100c5c99ee747ca048
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Pakiet zawartości usługi Power BI Analiza wydatków zakupowych
<a id="purchase-spend-analysis-power-bi-content" class="xliff"></a>

[!include[banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Analiza wydatków zakupowych**. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## Przegląd
<a id="overview" class="xliff"></a>

Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** został zaprojektowany, aby pomóc kierownikom ds. zakupów i menedżerom odpowiedzialnym za budżety monitorować wydatki zakupowe. Menedżerowie mogą analizować wydatki zakupowe w następujące sposoby:

-   Zakupy od początku roku (według grupy dostawców i indywidualnych dostawców, kategorii zaopatrzenia, poszczególnych produktów i lokalizacji dostawców)
-   Zmiany wydatków zakupowych rok do roku (według grup dostawców i kategorii zaopatrzenia)

Pakiet zawartości wykorzystuje dane transakcyjne zakupów i przedstawia zarówno zagregowany widok danych zakupowych w całej firmie, jak i podział wydatków zakupowych na dostawców i produkty. Raporty eksponują zmiany wydatków zakupowych w horyzoncie czasowym. W związku z tym raporty mogą służyć do ostrzegania menedżerów o pozytywnych i negatywnych trendach wydatków dla poszczególnych dostawców i produktów. Dodatkowo wykresy pokazują wydatki zakupowe dla różnych kategorii zaopatrzenia i grup dostawców. W związku z tym menedżerowie kategorii i kierownicy regionalni mogą używać tych wykresów do identyfikowania zmian w zachowaniach wydatkowych.

## Przechodzenie do pakietu zawartości usługi Power BI
<a id="accessing-the-power-bi-content" class="xliff"></a>
Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r., pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** jest wyświetlany na stronie **Analiza wydatków i zakupów** (**Zaopatrzenie i sourcing** > **Zapytania i raporty** > **Analiza wydajności zakupów** > **Analiza wydatków i zakupów**). 

## Wskaźniki umieszczone w pakiecie zawartości usługi Power BI
<a id="metrics-that-are-included-in-the-power-bi-content" class="xliff"></a>
Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** obejmuje raport zawierający zestaw wskaźników. Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele. Następująca tabela zawiera przegląd dostępnych wizualizacji.

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

## Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI
<a id="extending-the-power-bi-content" class="xliff"></a>
Za pomocą pakietów zawartości dostępnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) można dostarczać zaawansowane funkcje analityczne osobom, które się nie logują w programie Microsoft Dynamics 365. Te pakiety zawartości można modyfikować, tak aby zawierały inne raporty lub wizualizacje, a następnie publikować je w swojej dzierżawie usługi Power BI.com na potrzeby wykonywania analiz. 

Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** znajduje się w bibliotece zasobów wspólnych w usłudze LCS. Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md). Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

Uważaj, aby pobrać pakiet zawartości **Analiza wydatków zakupowych** mający zastosowanie do używanej wersji systemu Dynamics 365.

> [!NOTE]
> Jeśli używasz programu Microsoft Dynamics 365 for Operations w wersji 1611, ten pakiet zawartości usługi Power BI wymaga poprawki KB 4011327. Po zalogowaniu się w usłudze LCS można uzyskać dostęp do tej poprawki KB tutaj: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## Model i jednostki danych
<a id="data-model-and-entities" class="xliff"></a>
Następujące dane są używane do wypełniania stron raportów w pakiecie zawartości **Analiza wydatków zakupowych** dla usługi Power BI. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

Zagregowane miary w tym pakiecie zawartości są podzbiorem zagregowanych miar, które były dostępne w module Zakupy w programach Microsoft Dynamics AX 2012 i Microsoft Dynamics AX 2012 R3. Aby zagregowane miary modułu można było umieścić w magazynie jednostek, trzeba ustawić te miary jako wdrażalne. Aby uzyskać więcej informacji, zobacz procedurę umieszczania zagregowanych miar w magazynie jednostek w temacie [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md). Następujące najważniejsze zagregowane miary są dostępne bezpośrednio w jednostce Wiersze faktury i używane jako podstawa w pakiecie zawartości:

| Jednostka        | Najważniejsze zagregowane miary | Źródło danych                                 | Pole              | opis                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Wiersze faktury | Zakup                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Kwota w walucie rozliczeniowej. |

W poniższej tabeli przedstawiono najważniejsze miary w pakiecie zawartości, które są obliczane na podstawie jednostki Wiersze faktury.

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

