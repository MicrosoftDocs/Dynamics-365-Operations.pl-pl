---
title: Pakiet zawartości usługi Power BI Wydajność produkcji
description: W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Wydajność produkcji. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.
author: AndersGirke
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ProductionPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 661617ea7e51ac5cacdd5a08ee52f6a6e43b44be
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686693"
---
# <a name="production-performance-power-bi-content"></a>Pakiet zawartości usługi Power BI Wydajność produkcji

[!include [banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Wydajność produkcji** Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości **Wydajność produkcji** dla usługi Power BI jest przeznaczony dla menedżerów produkcji lub osób w organizacji, które są odpowiedzialne za kontrolę produkcji.

Raporty dostępne w pakiecie pozwalają używać usługi Power BI do monitorowanie wydajności operacji produkcji pod względem terminowości wykonania, jakości i kosztów. Raporty wykorzystują dane transakcyjne ze zleceń produkcyjnych i szarż produkcyjnych. Przedstawiają zarówno zagregowany widok metryk produkcji dla całej firmy, jak i podział metryk według produktów i zasobów.

Pakiet zawartości usługi Power BI pokazuje zdolność firmy do wykonywania produkcji na czas i w całości. Wydajność w przyszłości jest przewidywana na podstawie planów produkcji. Kompleksowe raporty zawierają szczegółowe informacje o wadach produktów spowodowanych na produkcji, jak również o wskaźnikach wadliwości zasobów i operacji.

Ten pakiet zawartości usługi Power BI umożliwia także analizowanie odchyleń produkcji. Odchylenia produkcji są obliczane jako różnica między kosztami szacowanym a zrealizowanym. Odchylenia produkcji są obliczane w momencie, gdy zlecenia produkcyjne lub szarże produkcyjne osiągają stan **Zakończone**.

Pakiet zawartości usługi Power BI **Wydajność produkcji** zawiera dane, które pochodzą ze zleceń produkcyjnych i szarż produkcyjnych. Raporty nie obejmują danych związanych z produkcją Kanban.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Pakiet zawartości usługi Power BI **Wydajność produkcji** jest wyświetlany na stronie **Wydajność produkcji** (**Kontrola produkcji** \> **Zapytania i raporty** \> **Analiza wydajności produkcji** \> **Wydajność produkcji**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki umieszczone w pakiecie zawartości usługi Power BI

Pakiet zawartości usługi Power BI **Wydajność produkcji** zawiera zestaw stron raportu. Każda strona zawiera zestaw wskaźników, które są wizualizowane jako wykresy, kafelki i tabele.

W poniższej tabeli znajduje się omówienie dostępnych wizualizacji.

| Strona raportu                                | Wykresy | Kafelki |
|--------------------------------------------|--------|-------|
| Wydajność produkcji                     | <ul><li>Wyprodukowana ilość wg daty</li><li>Wyprodukowana ilość wg produktu i grupy towarów</li><li>Ilość planowana do wyprodukowania wg daty</li><li>10 najgorszych produktów wg terminowości i kompletności</li></ul> | <ul><li>Razem zamówienia</li><li>% na czas i w całości</li><li>% niezakończonych</li><li>% wczesnych</li><li>% opóźnionych</li></ul> |
| Wady wg produktów                         | <ul><li>Wskaźnik wadliwości (części na milion) wg daty</li><li>Wskaźnik wadliwości (części na milion) wg produktu i grupy towarów</li><li>Wyprodukowana ilość wg daty</li><li>10 najlepszych produktów wg wskaźnika efektywności</li></ul> | <ul><li>Wskaźnik wadliwości (części na milion)</li><li>Ilość wadliwych</li><li>Ilość całkowita</li></ul> |
| Trend wad wg produktów                   | Wskaźnik wadliwości (części na milion) wg wyprodukowanej ilości | Wskaźnik wadliwości (części na milion) |
| Wady wg zasobów                        | <ul><li>Wskaźnik wadliwości (części na milion) wg daty</li><li>Wskaźnik wadliwości (części na milion) wg zasobu i oddziału</li><li>Wskaźnik wadliwości (części na milion) wg operacji</li><li>10 najlepszych zasobów wg wskaźnika wadliwości</li></ul> | Ilość wadliwych |
| Trend wad wg zasobów                  | Wskaźnik wadliwości (części na milion) wg przetworzonej ilości | |
| Odchylenia produkcji w kalkulacji doliczeniowej zleceniowej | <ul><li>Odchylenie produkcji wg daty i typu grupy kosztów</li><li>Odchylenie produkcji wg oddziału i typu grupy kosztów</li><li>10 najlepszych produktów z niekorzystnymi odchyleniami produkcji</li><li>10 najbardziej niekorzystnych odchyleń produkcji wg zasobów</li></ul> | <ul><li>Zrealizowany koszt</li><li>Odchylenia produkcji</li><li>% odchylenia produkcji</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

Następujące dane są używane dla stron raportów w pakiecie zawartości **Wydajność produkcji** dla usługi Power BI. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji o magazynie jednostek, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

Następująca tabela pokazuje najważniejsze zagregowane miary używane jako podstawa w pakiecie zawartości usługi Power BI.

| Jednostka                   | Najważniejsze zagregowane miary  | Źródło danych dla aplikacji rozwiązania Finance and Operations | Pole              |
|--------------------------|-----------------------------|----------------------------------------|--------------------|
| CostCalculation          | CostAmount                  | ProdCalcTransExpanded                  | CostAmount         |
| CostCalculation          | CostMarkup                  | ProdCalcTransExpanded                  | CostMarkup         |
| CostCalculation          | ActualCostAmount            | ProdCalcTransExpanded                  | RealCostAmount     |
| CostCalculation          | RealCostAdjustment          | ProdCalcTransExpanded                  | RealCostAdjustment |
| RouteTransactions        | ErrorQuantity               | ProdRouteTransExpanded                 | QtyError           |
| RouteTransactions        | GoodQuantity                | ProdRouteTransExpanded                 | QtyGood            |
| ProductionOrder          | DaysDelayed                 | ProdTableExpanded                      | DaysDelayed        |
| ProductionOrder          | LeadTime                    | ProdTableExpanded                      | LeadTime           |
| ProductionOrder          | PlannedLeadTime             | ProdTableExpanded                      | PlannedLeadTime    |
| ProductionOrder          | ProductionOrderCount        | ProdTableExpanded                      |                    |
| CoproductCostCalculation | CoproductCostAmount         | PmfCoByProdCalcTransExpanded           | CostAmount         |
| CoproductCostCalculation | CoproductCostMarkup         | PmfCoByProdCalcTransExpanded           | CostMarkup         |
| CoproductCostCalculation | CoproductRealCostAdjustment | PmfCoByProdCalcTransExpanded           | RealCostAdjustment |
| CoproductCostCalculation | CoproductActualCostAmount   | PmfCoByProdCalcTransExpanded           | RealCostAmount     |

W poniższej tabeli przedstawiono, jak najważniejsze zagregowane miary są używane do tworzenia kilku miar obliczanych w zestawie danych pakietu zawartości.

| Pomiar                  | Sposób obliczania miary |
|--------------------------|-------------------------------|
| % odchylenia produkcji   | SUM('Odchylenie produkcji'\[Odchylenie produkcji\]) / SUM('Odchylenie produkcji'\[Koszty szacowane\]) |
| Wszystkie planowane zamówienia       | COUNTROWS('Planowane zlecenie produkcyjne') |
| Wcześnie                    | COUNTROWS(FILTER('Planowane zlecenie produkcyjne', 'Planowane zlecenie produkcyjne'\[Planowana data zakończenia\] \< 'Planowane zlecenie produkcyjne'\[Data zapotrzebowania\])) |
| Opóźnione                     | COUNTROWS(FILTER('Planowane zlecenie produkcyjne', 'Planowane zlecenie produkcyjne'\[Planowana data zakończenia\] \> 'Planowane zlecenie produkcyjne'\[Data zapotrzebowania\])) |
| Na czas                  | COUNTROWS(FILTER('Planowane zlecenie produkcyjne', 'Planowane zlecenie produkcyjne'\[Planowana data zakończenia\] = 'Planowane zlecenie produkcyjne'\[Data zapotrzebowania\])) |
| % na czas                | IF ( 'Planowane zlecenie produkcyjne'\[Na czas\] \<\> 0, 'Planowane zlecenie produkcyjne'\[Na czas\], IF ('Planowane zlecenie produkcyjne'\[Wszystkie planowane zamówienia\] \<\> 0, 0, BLANK()) ) / 'Planowane zlecenie produkcyjne'\[Wszystkie planowane zamówienia\] |
| Ukończono                | COUNTROWS(FILTER('Zlecenie produkcyjne', 'Zlecenie produkcyjne'\[Zgłoszone jako gotowe\] = TRUE)) |
| Wskaźnik wadliwości (części na milion)     | IF( 'Zlecenie produkcyjne'\[Ilość całkowita\] = 0, BLANK(), (SUM('Zlecenie produkcyjne'\[Ilość wadliwych\]) / 'Zlecenie produkcyjne'\[Ilość całkowita\]) \* 1000000) |
| Wskaźnik opóźnionej produkcji  | 'Zlecenie produkcyjne'\[opóźnionych \#\] / 'Zlecenie produkcyjne'\[Zakończone\] |
| Wcześnie i w całości          | COUNTROWS(FILTER('Zlecenie produkcyjne', 'Zlecenie produkcyjne'\[W całości\] = TRUE && 'Zlecenie produkcyjne'\[Wcześnie\] = TRUE)) |
| \# wczesnych                 | COUNTROWS(FILTER('Zlecenie produkcyjne', 'Zlecenie produkcyjne'\[Wcześnie\] = TRUE)) |
| % wczesnych                  | IFERROR( IF('Zlecenie produkcyjne'\[wczesnych \#\] \<\> 0, 'Zlecenie produkcyjne'\[wczesnych \#\], IF('Zlecenie produkcyjne'\[Razem zamówienia\] = 0, BLANK(), 0)) / 'Zlecenie produkcyjne'\[Razem zamówienia\], BLANK()) |
| Nie zakończono               | COUNTROWS(FILTER('Zlecenie produkcyjne', 'Zlecenie produkcyjne'\[W całości\] = FALSE && 'Zlecenie produkcyjne'\[Zgłoszone jako gotowe\] = TRUE)) |
| % niezakończonych             | IFERROR( IF('Zlecenie produkcyjne'\[Nie zakończono\] \<\> 0, 'Zlecenie produkcyjne'\[Nie zakończono\], IF('Zlecenie produkcyjne'\[Razem zamówienia\] = 0, BLANK(), 0)) / 'Zlecenie produkcyjne'\[Razem zamówienia\], BLANK()) |
| Opóźnione               | 'Zlecenie produkcyjne'\[Zgłoszone jako gotowe\] = TRUE && 'Zlecenie produkcyjne'\[Wartość opóźnienia\] = 1 |
| Wcześnie                 | 'Zlecenie produkcyjne'\[Zgłoszone jako gotowe\] = TRUE && 'Zlecenie produkcyjne'\[Dni opóźnienia\] \< 0 |
| W całości               | 'Zlecenie produkcyjne'\[Ilość dobrych\] \>= 'Zlecenie produkcyjne'\[Zaplanowana ilość\] |
| Zgłoszone jako gotowe                | 'Zlecenie produkcyjne'\[Wartość stanu produkcji\] = 5 \|\| 'Zlecenie produkcyjne'\[Wartość stanu produkcji\] = 7 |
| Opóźnione i w całości           | COUNTROWS(FILTER('Zlecenie produkcyjne', 'Zlecenie produkcyjne'\[W całości\] = TRUE && 'Zlecenie produkcyjne'\[Opóźnione\] = TRUE)) |
| \# opóźnionych                  | COUNTROWS(FILTER('Zlecenie produkcyjne', 'Zlecenie produkcyjne'\[Opóźnione\] = TRUE)) |
| % opóźnionych                   | IFERROR( IF('Zlecenie produkcyjne'\[opóźnionych \#\] \<\> 0, 'Zlecenie produkcyjne'\[opóźnionych \#\], IF('Zlecenie produkcyjne'\[Razem zamówienia\] = 0, BLANK(), 0)) / 'Zlecenie produkcyjne'\[Razem zamówienia\], BLANK()) |
| Na czas i w całości        | COUNTROWS(FILTER('Zlecenie produkcyjne', 'Zlecenie produkcyjne'\[W całości\] = TRUE && 'Zlecenie produkcyjne'\[Opóźnione\] = FALSE && 'Zlecenie produkcyjne'\[Wcześnie\] = FALSE)) |
| % na czas i w całości      | IFERROR( IF('Zlecenie produkcyjne'\[Na czas i w całości\] \<\> 0, 'Zlecenie produkcyjne'\[Na czas i w całości\], IF('Zlecenie produkcyjne'\[Zakończone\] = 0, BLANK(), 0)) / 'Zlecenie produkcyjne'\[Zakończone\], BLANK()) |
| Razem zamówienia             | COUNTROWS('Zlecenie produkcyjne') |
| Ilość całkowita           | SUM('Zlecenie produkcyjne'\[Ilość dobrych\]) + SUM('Zlecenie produkcyjne'\[Ilość wadliwych\]) |
| Wskaźnik wadliwości (części na milion)        | IF( 'Transakcje marszruty'\[Ilość przetworzona\] = 0, BLANK(), (SUM('Transakcje marszruty'\[Ilość wadliwych\]) / 'Transakcje marszruty'\[Ilość przetworzona\]) \* 1000000) |
| Mieszany wskaźnik wadliwości (części na milion) | IF( 'Transakcje marszruty'\[Ilość mieszana razem\] = 0, BLANK(), (SUM('Transakcje marszruty'\[Ilość wadliwych\]) / 'Transakcje marszruty''\[Ilość mieszana razem\]) \* 1000000) |
| Ilość przetworzona       | SUM('Transakcje marszruty'\[Ilość dobrych\]) + SUM('Transakcje marszruty'\[Ilość wadliwych\]) |
| Ilość mieszana razem     | SUM('Zlecenie produkcyjne'\[Ilość dobrych\]) + SUM('Transakcje marszruty'\[Ilość wadliwych\]) |

Następująca tabela przedstawia najważniejsze wymiary używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i lepszego wglądu analitycznego.

| Jednostka                    | Przykłady atrybutów                                        |
|---------------------------|---------------------------------------------------------------|
| Data zgłoszenia jako gotowej | Data ukończenia (zgłoszenia wyrobów gotowych), miesiąc i przesunięcie roku                 |
| Data zakończenia                | Przesunięcie zakończonego miesiąca i Miesiąc                                  |
| Data zapotrzebowania          | Przesunięcie miesiąca daty zapotrzebowania i Data zapotrzebowania            |
| Data transakcji marszruty    | Przesunięcie miesiąca transakcji marszruty i Data                       |
| Oddziały                     | Identyfikator oddziału, Nazwa oddziału, Stan i Miejscowość                          |
| Jednostki                  | Identyfikator i Nazwa                                                   |
| Zasoby                 | Identyfikator zasobu, Nazwa zasobu, Typ zasobu i Grupa zasobów |
| Produkty                  | Numer produktu, Nazwa produktu, Identyfikator towaru i Grupa towarów         |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]