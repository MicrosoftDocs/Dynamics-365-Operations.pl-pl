---
title: Pakiet zawartości zarządzania kosztami w usłudze Power BI
description: W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Zarządzanie kosztami.
author: ShylaThompson
ms.date: 03/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, CostObjectWithLowestAccuracy, CostVarianceChart, CostObjectWithLowestTurn
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9fbdc6addc820aadc1f5469cb059a62724cfe905
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752647"
---
# <a name="cost-management-power-bi-content"></a>Pakiet zawartości zarządzania kosztami w usłudze Power BI

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Omówienie

Pakiet zawartości **Zarządzanie kosztami** dostępny w usłudze Microsoft Power BI jest przeznaczony dla pracowników księgujących zapasy lub osób w organizacji, które są zainteresowane lub odpowiedzialne za zapasy lub produkcję w toku (PWT) albo zainteresowane lub odpowiedzialne za analizowanie odchyleń kosztu standardowego.

Ten pakiet zawartości usługi Power BI oferuje skategoryzowany format, który pomaga monitorować sytuację w zapasach oraz wizualizować przepływy kosztów przez zapasy. Można uzyskać różne informacje przydatne kierownictwu, takie jak wskaźnik obrotu, liczba dni dostępności zapasów na stanie, dokładność oraz „klasyfikacja ABC” na preferowanym zagregowanym poziomie (firmy, towaru, grupy towarów lub oddziału). Dostępne informacje mogą być również wykorzystywane jako szczegółowe uzupełnienie sprawozdania finansowego.

Ten pakiet zawartości usługi Power BI opiera się na zagregowanej miarze **CostObjectStatementCacheMonthly**, którego podstawowym źródłem jest tabela **CostObjectStatementCache**. Ta tabela jest zarządzana przez strukturę pamięci podręcznej zestawów danych. Domyślnie tabela jest aktualizowana co 24 godziny, ale można zmienić częstotliwość aktualizacji lub włączyć ręczne aktualizacje w konfiguracji pamięci podręcznej danych. Ręczne aktualizacje mogą być wykonywane w obszarze roboczym **Administrowanie kosztami** lub **Analiza kosztów**.

Po każdej aktualizacji tabeli **CostObjectStatementCache** należy zaktualizować zagregowaną miarę **CostObjectStatementCacheMonthly**. Dopiero wtedy będą aktualizowane dane w wizualizacjach usługi Power BI.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI

Pakiet zawartości usługi Power BI **Zarządzanie kosztami** jest wyświetlany w obszarach roboczych **Administrowanie kosztami** i **Analiza kosztów**.

Obszar roboczy **Administrowanie kosztami** zawiera następujące karty:

- **Przegląd** — na tej karcie są wyświetlane dane aplikacji.
- **Stan księgowania zapasów** — ta karta pokazuje informacje z pakietu zawartości usługi Power BI.
- **Stan księgowania produkcji** — ta karta pokazuje informacje z pakietu zawartości usługi Power BI.

Obszar roboczy **Analiza kosztów** zawiera następujące karty:

- **Przegląd** — na tej karcie są wyświetlane dane aplikacji.
- **Analiza księgowania zapasów** — ta karta pokazuje informacje z pakietu zawartości usługi Power BI.
- **Analiza księgowania produkcji** — ta karta pokazuje informacje z pakietu zawartości usługi Power BI.
- **Analiza odchyleń kosztu standardowego** — ta karta pokazuje informacje z pakietu zawartości usługi Power BI.

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>Strony raportów umieszczone w pakiecie zawartości usługi Power BI

Pakiet zawartości usługi Power BI **Zarządzanie kosztami** obejmuje zestaw stron raportów zawierających zbiór mierników. Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele. 

Poniższe tabele zawierają omówienie wizualizacji dostępnych w pakiecie zawartości usługi Power BI **Zarządzanie kosztami**.

### <a name="inventory-accounting-status"></a>Stan księgowania zapasów

| Strona raportu                               | Wizualizacja                                   |
|-------------------------------------------|-------------------------------------------------|
| Omówienie zapasów                        | Saldo początkowe                               |
|                                           | Zmiana netto                                      |
|                                           | % zmiany netto                                    |
|                                           | Saldo końcowe                                  |
|                                           | Dokładność zapasów                              |
|                                           | Wskaźnik obrotu magazynowego                        |
|                                           | Dostępne zapasy dzienne                          |
|                                           | Aktywny produkt w okresie                        |
|                                           | Aktywne obiekty kosztów w okresie                   |
|                                           | Saldo wg grupy towarów                           |
|                                           | Saldo wg oddziału                                 |
|                                           | Zestawienie wg kategorii                           |
|                                           | Zmiana netto wg kwartału                           |
| Przegląd zapasów wg oddziału i grupy towarów | Dokładność zapasów wg oddziału                      |
|                                           | Wskaźnik obrotu zapasami wg oddziału                |
|                                           | Saldo końcowe zapasów wg oddziału                |
|                                           | Dokładność zapasów wg grupy towarów                |
|                                           | Wskaźnik obrotu zapasami wg grupy towarów          |
|                                           | Saldo końcowe zapasów wg oddziału i grupy towarów |
| Zestawienie magazynowe                       | Zestawienie magazynowe                             |
| Zestawienie zapasów wg oddziału               | Zestawienie zapasów wg oddziału                     |
| Zestawienie zapasów wg hierarchii produktów  | Zestawienie magazynowe                             |
| Zestawienie zapasów wg hierarchii produktów  | Zestawienie zapasów wg oddziału                     |

### <a name="manufacturing-accounting-status"></a>Stan księgowania produkcji

| Strona raportu                | Wizualizacja                       |
|----------------------------|-------------------------------------|
| Przegląd PWT od początku roku           | Saldo początkowe                   |
|                            | Zmiana netto                          |
|                            | % zmiany netto                        |
|                            | Saldo końcowe                      |
|                            | Wskaźnik obrotu PWT                  |
|                            | Dostępna PWT dzienna                    |
|                            | Aktywny obiekt kosztów w okresie        |
|                            | Zmiana netto wg grupy zasobów        |
|                            | Saldo wg oddziału                     |
|                            | Zestawienie wg kategorii               |
|                            | Zmiana netto wg kwartału               |
| zestawienie PWT              | Saldo początkowe                   |
|                            | Saldo końcowe                      |
|                            | Zestawienie PWT wg kategorii           |
| Zestawienie PWT wg oddziału      | Saldo początkowe                   |
|                            | Saldo końcowe                      |
|                            | Zestawienie PWT wg kategorii i oddziału  |
| Zestawienie PWT wg hierarchii | Saldo początkowe                   |
|                            | Saldo końcowe                      |
|                            | Zestawienie PWT wg hierarchii kategorii |

### <a name="inventory-accounting-analysis"></a>Analiza księgowania zapasów

| Strona raportu        | Wizualizacja                                                                |
|--------------------|------------------------------------------------------------------------------|
| Szczegóły zapasów  | 10 najważniejszych zasobów wg salda końcowego                                           |
|                    | 10 najważniejszych zasobów wg zmiany wzrostowej netto                                      |
|                    | 10 najważniejszych zasobów wg zmiany spadkowej netto                                      |
|                    | 10 najważniejszych zasobów wg wskaźnika obrotu zapasami                                 |
|                    | Zasoby wg niskiego wskaźnika obrotu zapasami i salda końcowego powyżej progu |
|                    | 10 najważniejszych zasobów wg niskiej dokładności                                             |
| Klasyfikacja ABC | Saldo końcowe zapasów                                                     |
|                    | Zużyty materiał                                                            |
|                    | Sprzedane (KWS)                                                                  |
| Trendy zapasów   | Saldo końcowe zapasów                                                     |
|                    | Zmiana netto zapasów                                                         |
|                    | Wskaźnik obrotu magazynowego                                                     |
|                    | Dokładność zapasów                                                           |

### <a name="manufacturing-accounting-analysis"></a>Analiza księgowania produkcji

| Strona raportu | Wizualizacja      |
|-------------|--------------------|
| Trendy PWT  | Saldo końcowe PWT |
|             | Zmiana netto PWT     |
|             | Wskaźnik obrotu PWT |

### <a name="std-cost-variance-analysis"></a>Analiza odchyleń kosztu standardowego

| Strona raportu                             | Wizualizacja                                        |
|-----------------------------------------|------------------------------------------------------|
| Odchylenie ceny zakupu (koszt standardowy) od początku roku | Saldo zaopatrzenia                                     |
|                                         | Rozbieżność cen zakupu                              |
|                                         | Wskaźnik odchylenia ceny zakupu                        |
|                                         | Odchylenie wg grupy towarów                               |
|                                         | Odchylenie wg oddziału                                     |
|                                         | Cena zakupu wg kwartału                            |
|                                         | Cena zakupu wg kwartału i grupy towarów             |
|                                         | 10 najważniejszych zasobów wg niekorzystnego wskaźnika ceny zakupu |
|                                         | 10 najważniejszych zasobów wg korzystnego wskaźnika ceny zakupu   |
| Odchylenie produkcji (koszt standardowy) od początku roku     | Koszt wyprodukowanych                                    |
|                                         | Odchylenia produkcji                                  |
|                                         | Wskaźnik odchylenia produkcji                            |
|                                         | Odchylenie wg grupy towarów                               |
|                                         | Odchylenie wg oddziału                                     |
|                                         | Odchylenie produkcji wg kwartału                       |
|                                         | Odchylenie produkcji wg kwartału i typu odchylenia     |
|                                         | 10 najważniejszych zasobów wg niekorzystnego odchylenia produkcji  |
|                                         | 10 najważniejszych zasobów wg korzystnego odchylenia produkcji    |

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

Dane z aplikacji są używane do wypełniania stron raportów w pakiecie zawartości usługi **Zarządzanie kosztami** Power BI. Te dane są przedstawiane jako zagregowane miary umieszczane w magazynie jednostek, który jest bazą danych programu Microsoft SQL Server zoptymalizowaną pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

Najważniejsze zagregowane miary poniższych obiektów są używane jako podstawa w pakiecie zawartości usługi Power BI.

| Obiekt                          | Najważniejsze zagregowane miary | Źródło danych w Finance and Operations | Pole               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | Liczba dni                     | CostObjectStatementCache               | Ilość              |
| CostObjectStatementCacheMonthly | Ilość                   | CostObjectStatementCache               | Ilość                 |
| CostInventoryAccountingKPIGoal  | AnnualInventoryTurn        | CostInventoryAccountingKPIGoal         | AnnualInventoryTurn |
| CostInventoryAccountingKPIGoal  | InventoryAccuracy          | CostInventoryAccountingKPIGoal         | InventoryAccuracy   |

W poniższej tabeli przedstawiono najważniejsze obliczane miary w pakiecie zawartości usługi Power BI.

| Pomiar                            | Obliczenie |
|------------------------------------|-------------|
| Saldo początkowe                  | Saldo początkowe = \[Saldo końcowe\]-\[Zmiana netto\] |
| Ilość salda początkowego             | Ilość salda początkowego = \[Ilość salda końcowego\]-\[Ilość zmiany netto\] |
| Saldo końcowe                     | Saldo końcowe = (CALCULATE(SUM(\[Kwota\]), FILTER(ALL(FiscalCalendar) ,FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| Ilość salda końcowego                | Ilość salda końcowego = CALCULATE(SUM(\[QTY\]), FILTER(ALL(FiscalCalendar),FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\]))) |
| Zmiana netto                         | Zmiana netto = SUM(\[AMOUNT\]) |
| Ilość zmiany netto                    | Ilość zmiany netto = SUM(\[QTY\]) |
| Wskaźnik obrotu zapasami wg ilości | Wskaźnik obrotu zapasami wg ilości = if(OR(\[Średnie saldo zapasów\] \<= 0, \[Inventory sold or consumed issues\] \>[Wydania zapasów sprzedanych lub zużytych]= 0), 0, ABS(\[Wydania zapasów sprzedanych lub zużytych\])/\[Średnie saldo zapasów\]) |
| Średnie saldo zapasów          | Średnie saldo zapasów = ((\[Saldo końcowe\] + \[Saldo początkowe\]) / 2) |
| Dostępne zapasy dzienne             | Dostępne zapasy dzienne = 365 / CostObjectStatementEntries\[Wskaźnik obrotu zapasami wg ilości\] |
| Dokładność zapasów                 | Dokładność zapasów według kwoty = if(\[Saldo końcowe\] \<= 0, IF(OR(\[Inventory counted amount\] \<\> 0[Ilość zliczonych zapasów], \[Saldo końcowe\] \< 0), 0, 1), MAX(0, (\[Saldo końcowe\] -ABS(\[Kwota zliczona przez magazyn\]))/\[Saldo końcowe\])) |

Następujące najważniejsze wymiary są używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i lepszego wglądu analitycznego.


| Jednostka                                                  | Przykłady atrybutów                          |
|---------------------------------------------------------|-------------------------------------------------|
| Produkty                                                | Numer produktu, Nazwa produktu, Jednostka, Grupy pozycji |
| Hierarchie kategorii (przypisane do roli Zarządzanie kosztami) | Hierarchia kategorii, Poziom kategorii              |
| Firmy                                          | Nazwy firm                              |
| Kalendarze obrachunkowe                                        | Kalendarz obrachunkowy, Rok, Kwartał, Okres, Miesiąc   |
| Witryna                                                    | Identyfikator, Nazwa, Adres, Województwo, Kraj               |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
