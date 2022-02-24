---
title: Pakiet zawartości usługi Power BI Analiza wydatków zakupowych
description: W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Analiza wydatków zakupowych. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3f556cf2e506c57e465c2a86485d2cdd4cf8b65e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680621"
---
# <a name="purchase-spend-analysis-power-bi-content"></a>Pakiet zawartości usługi Power BI Analiza wydatków zakupowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Analiza wydatków zakupowych**. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** został zaprojektowany, aby pomóc kierownikom ds. zakupów i menedżerom odpowiedzialnym za budżety monitorować wydatki zakupowe. Menedżerowie mogą analizować wydatki zakupowe w następujące sposoby:

- Zakupy od początku roku (według grupy dostawców i indywidualnych dostawców, kategorii zaopatrzenia, poszczególnych produktów i lokalizacji dostawców)
- Zmiany wydatków zakupowych rok do roku (według grup dostawców i kategorii zaopatrzenia)

Pakiet zawartości wykorzystuje dane transakcyjne zakupów i przedstawia zarówno zagregowany widok danych zakupowych w całej firmie, jak i podział wydatków zakupowych na dostawców i produkty. Raporty eksponują zmiany wydatków zakupowych w horyzoncie czasowym. W związku z tym raporty mogą służyć do ostrzegania menedżerów o pozytywnych i negatywnych trendach wydatków dla poszczególnych dostawców i produktów. Dodatkowo wykresy pokazują wydatki zakupowe dla różnych kategorii zaopatrzenia i grup dostawców. W związku z tym menedżerowie kategorii i kierownicy regionalni mogą używać tych wykresów do identyfikowania zmian w zachowaniach wydatkowych.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Pakiet zawartości usługi Power BI **Analiza wydatków związanych z zakupami** jest wyświetlany na stronie **Analiza wydatków i zakupów** (**Zaopatrzenie i sourcing** \> **Zapytania i raporty** \> **Analiza wydajności zakupów** \> **Analiza wydatków i zakupów**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki umieszczone w pakiecie zawartości usługi Power BI
Pakiet zawartości usługi Power BI **Analiza wydatków zakupowych** obejmuje raport zawierający zestaw wskaźników. Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele. 

Następująca sekcja zawiera przegląd dostępnych wizualizacji.

### <a name="purchase-by-vendor-report-page"></a>Strona raportu o zakupach wg dostawcy
**Wykresy**
- 10 najważniejszych dostawców wg wartości zakupów (wykres skumulowany słupkowy)
- Łączne zakupy wg grupy dostawców/kraju/nazwy (wykres kołowy)
- Zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)
- Średnie zakupy wg grupy dostawców/kraju/nazwy (wykres kolumnowy)

**Kafelki**
- Suma zakupów
- Wzrost zakupów r/r
- Łączna liczba dostawców
- Łączna liczba aktywnych dostawców

**Przykład**
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a>Strona raportu o produktach wg dostawcy

**Wykresy**
- Zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kolumnowy)
- Łączne zakupy wg kategorii zaopatrzenia/nazwy produktu (wykres kołowy)
- 10 najważniejszych produktów wg wartości zakupów (wykres skumulowany słupkowy)

**Kafelki**
- Łączna liczba produktów</li>
- Procent aktywnych produktów w łącznej liczbie produktów
- Liczba produktów odpowiedzialnych za 80% zakupów

**Przykład**


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a>Strona raportu o okresie wg dostawcy
Ta strona pokazuje zakupy w tym i ubiegłym roku oraz wzrost według kategorii zaopatrzenia.

**Wykresy** 
- Zakupy wg miesiąca/dnia (wykres kolumnowy)
- Odchylenie łącznych zakupów r/r (wykres kaskadowy)
- Wzrost łącznych zakupów r/r (wykres kolumnowy)
- Zestawienie zaopatrzenia (macierz)

**Kafelki**
- Wzrost zakupów r/r
- % wzrostu zakupów r/r

**Przykład**
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a>Strona raportu o zakupach wg lokalizacji dostawcy

**Wykresy**
- Zakupy wg miejscowości
- % wzrostu zakupów r/r
- Zakupy wg krajów

**Przykład**
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a>Analiza wydatków zakupowych wg strony raportu

**Wykresy** 
- Zakupy w bieżącym roku wg miesiąca/dnia (wykres liniowy)
- Zakupy w bieżącym i ubiegłym roku (wykres liniowy i kolumnowy)

**Przykład**
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a>Analiza wydatków zakupowych wg strony raportu dot. dostawcy

**Wykresy** 
- % udziału 10 najważniejszych dostawców w zakupach (wykres lejkowy)
- 10 dostawców z największym wzrostem wydatków r/r
- 10 dostawców z największym spadkiem wydatków r/r

**Przykład** 
<img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a>Model i jednostki danych
Następujące dane są używane do wypełniania stron raportów w pakiecie zawartości **Analiza wydatków zakupowych** dla usługi Power BI. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

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
