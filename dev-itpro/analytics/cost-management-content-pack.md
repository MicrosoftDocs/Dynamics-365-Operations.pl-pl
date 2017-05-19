---
title: "Pakiet zawartości usługi Power BI Zarządzanie kosztami"
description: "W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Zarządzanie kosztami. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 50889ffbbbc44d966081d60e5d631bd17476b6df
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="cost-management-power-bi-content"></a>Pakiet zawartości usługi Power BI Zarządzanie kosztami

[!include[banner](../includes/banner.md)]


W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Zarządzanie kosztami. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

# <a name="overview"></a>Przegląd

Pakiet zawartości **Zarządzanie kosztami** dostępny w usłudze Microsoft Power BI jest przeznaczony dla pracowników księgujących zapasy lub osób w organizacji, które są odpowiedzialne za zapasy. Pakiet zawartości **Zarządzanie kosztami** w usłudze Power BI zapewnia zaawansowany wgląd w zapasy i zapasy pracy w toku (PWT) oraz przepływy kosztów między tymi zapasami z podziałem na kategorie w ujęciu czasowym. Informacje mogą być również wykorzystywane jako szczegółowe uzupełnienie sprawozdania finansowego.

## <a name="key-measures"></a>Najważniejsze miary

+ Saldo początkowe
+ Saldo końcowe
+ Zmiana netto
+ Zmiana netto w %
+ Wiekowanie

## <a name="key-performance-indicators"></a>Kluczowe wskaźniki wydajności
+ Obrót magazynowy
+ Dokładność zapasów

Głównym źródłem danych jednostki CostAggregatedCostStatementEntryEntity jest tabela CostStatementCache. Ta tabela jest zarządzana przez strukturę pamięci podręcznej zestawów danych. Domyślnie tabela jest aktualizowana co 24 godziny, ale można włączyć ręczne aktualizacje w konfiguracji pamięci podręcznej danych. Następnie można wykonywać ręczną aktualizację w obszarze roboczym **Zarządzanie kosztami** lub **Analiza kosztów**. Po zaktualizowaniu pamięci podręcznej zarządzania kosztami trzeba zaktualizować połączenie OData na stronie BI.com, aby zobaczyć zaktualizowane dane w witrynie. Miary odchyleń (zakup, produkcja) w tym pakiecie zawartości usługi Power BI odnoszą się tylko do elementów, które są wyceniane metodą inwentaryzacji Koszt standardowy. Odchylenie produkcji jest obliczane jako różnica między kosztami aktywnym i zrealizowanym. Odchylenie produkcji jest obliczane w momencie, gdy zlecenie produkcyjne uzyskuje stan **Zakończone**. Aby uzyskać więcej informacji o typach odchyleń produkcji i sposobach ich obliczania, zobacz [Analiza odchyleń dla zrealizowanego zlecenia produkcyjnego](https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Pakiet zawartości usługi Power BI **Zarządzanie kosztami** jest dostępny w witrynie PowerBI.com. Aby uzyskać więcej informacji o tworzeniu połączenia z danymi programu Microsoft Dynamics 365 for Operations i ich ładowaniu, zobacz [Dostęp do pakietu zawartości usługi Power BI z witryny Microsoft Dynamics 365 for Operations](power-bi-home-page.md).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki umieszczone w pakiecie zawartości usługi Power BI
Pakiet zawartości zawiera zestaw stron raportów. Każda strona zawiera zestaw wskaźników, które są wizualizowane jako wykresy, kafelki i tabele. Poniższa tabela zawiera omówienie wizualizacji dostępnych w pakiecie zawartości usługi Power BI **Zarządzanie kosztami**.

| Strona raportu | Wykresy | Stanowiska |
|---|---|---|
|Zapasy ogółem (domyślnie wg bieżącego okresu) |Dokładność |Miary zapasów:<br>Saldo końcowe zapasów<br>Zmiana netto zapasów<br>% zmiany netto zapasów<br>|
| |Obrót magazynowy | |
| |Saldo końcowe zapasów wg grupy zasobów | |
| |Zmiana netto zapasów wg nazwy kategorii poziomu 1 i nazwy kategorii poziomu 2| |
| |Odchylenia zakupów wg grupy zasobów i nazwy kategorii poziomu 3 | |
|Zapasy wg oddziału (domyślnie wg bieżącego okresu) |Saldo końcowe zapasów wg nazwy oddziału i grupy zasobów | |
| |Obrót magazynowy wg nazwy oddziału i grupy zasobów | |
| |Saldo końcowe zapasów wg miejscowości i grupy zasobów | |
|Zapasy wg grupy zasobów (domyślnie wg bieżącego okresu) |Miary zapasów | |
| |Dokładność zapasów wg kwoty i grupy zasobów | |
| |Obrót magazynowy wg kwoty i grupy zasobów | |
|Zapasy r/r (domyślnie bieżący rok w porównaniu z poprzednim rokiem) |Miary zapasów | |
| |Wskaźniki KPI zapasów:<br>Obrót magazynowy<br>Dokładność zapasów | |
| |Saldo końcowe zapasów wg roku i grupy zasobów | |
| |Odchylenia zakupów wg roku i nazwy kategorii poziomu 3 | |
|Wiekowanie zapasów (domyślnie wg bieżącego roku) |Wiekowanie zapasów wg kwartału i grupy zasobów | |
| |Wiekowanie zapasów wg kwartału i nazwy oddziału | |
|PWT ogółem (domyślnie wg bieżącego okresu) |Zmiana netto PWT wg nazwy kategorii poziomu 1 i nazwy kategorii poziomu 2 |Miary pracy w toku (PWT):<br>Saldo końcowe PWT<br>Zmiana netto PWT<br>% zmiany netto PWT<br> |
| |Odchylenia produkcji wg grupy zasobów i nazwy kategorii poziomu 3 | |
| |Zmiana netto PWT wg grupy zasobów | |
|PWT wg oddziału (domyślnie wg bieżącego okresu) |Miary pracy w toku (PWT) | |
| |Zmiana netto PWT wg nazwy oddziału i nazwy kategorii poziomu 2 | |
| |Odchylenia produkcji wg nazwy oddziału i nazwy kategorii poziomu 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dane programu Dynamics 365 for Operations są używane do wypełniania stron raportów w pakiecie zawartości usługi Power BI **Zarządzanie kosztami**. Te dane są przedstawiane jako zagregowane miary umieszczane w magazynie jednostek, który jest bazą danych programu Microsoft SQL zoptymalizowaną pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md). Następujące najważniejsze zagregowane miary są używane jako podstawa w pakiecie zawartości:

| Jednostka            | Najważniejsza zagregowana miara | Źródło danych programu Dynamics 365 for Operations | Pole             | opis                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Wpisy zestawienia | Zmiana netto                | CostAggregatedCostStatementEntryEntity      | sum(\[Kwota\])   | Kwota w walucie rozliczeniowej |
| Wpisy zestawienia | Ilość zmiany netto       | CostAggregatedCostStatementEntryEntity      | sum(\[Ilość\]) |                                   |

W poniższej tabeli przedstawiono, jak najważniejsze zagregowane miary są używane do tworzenia kilku miar obliczanych w zestawie danych pakietu zawartości.

| Pomiar                                 | Sposób obliczania miary                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo początkowe                       | \[Saldo końcowe\]-\[Zmiana netto\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Ilość salda początkowego              | \[Ilość salda końcowego\]-\[Ilość zmiany netto\]                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Saldo końcowe                          | CALCULATE(SUM(\[Kwota\]), FILTER(ALLEXCEPT('Kalendarze obrachunkowe', 'Kalendarze obrachunkowe'\[LedgerRecId\], 'jednostki'\[Identyfikator\], 'jednostki'\[Nazwa\], 'Księgi'\[Waluta\], 'Księgi'\[Opis\], 'Księgi'\[Nazwa\]), 'Kalendarze obrachunkowe'\[Data\] &lt;= MAX('Kalendarze obrachunkowe'\[Data\])))                                                                                                                                                                                           |
| Ilość salda końcowego                 | CALCULATE(SUM(\[Ilość\]), FILTER(ALLEXCEPT('Kalendarze obrachunkowe', 'Kalendarze obrachunkowe'\[LedgerRecId\], 'jednostki'\[Identyfikator\], 'jednostki'\[Nazwa\], 'Księgi'\[Waluta\], 'Księgi'\[Opis\], 'Księgi'\[Nazwa\]), 'Kalendarze obrachunkowe'\[Data\] &lt;= MAX('Kalendarze obrachunkowe'\[Data\])))                                                                                                                                                                                         |
| Saldo początkowe zapasów             | CALCULATE(\[Saldo początkowe\], 'Wpisy zestawienia'\[Typ zestawienia\] = "Zapasy")                                                                                                                                                                                                                                                                                                                                                                                      |
| Saldo końcowe zapasów                | CALCULATE(\[Saldo końcowe\], 'Wpisy zestawienia'\[Typ zestawienia\] = "Zapasy")                                                                                                                                                                                                                                                                                                                                                                                         |
| Zmiana netto zapasów                    | CALCULATE(\[Zmiana netto\], 'Wpisy zestawienia'\[Typ zestawienia\] = "Zapasy")                                                                                                                                                                                                                                                                                                                                                                                             |
| Ilość zmiany netto zapasów           | CALCULATE(\[Ilość zmiany netto\], 'Wpisy zestawienia'\[Typ zestawienia\] = "Zapasy")                                                                                                                                                                                                                                                                                                                                                                                    |
| % zmiany netto zapasów                  | IF(\[Saldo końcowe zapasów\] = 0, 0, \[Zmiana netto zapasów\] / \[Saldo końcowe zapasów\])                                                                                                                                                                                                                                                                                                                                                                           |
| Obrót magazynowy wg kwoty                | if(OR(\[Średnie saldo zapasów\] &lt;= 0, \[Wydania zapasów sprzedanych lub zużytych\] &gt;= 0), 0, ABS(\[Wydania zapasów sprzedanych lub zużytych\])/\[Średnie saldo zapasów\])                                                                                                                                                                                                                                                                                                  |
| Średnie saldo zapasów               | (\[Saldo końcowe zapasów\] + \[Saldo początkowe zapasów\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Wydania zapasów sprzedanych lub zużytych       | \[Zapasy sprzedane\] + \[Koszt materiałów zużytych zapasów\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Koszt materiałów zużytych zapasów        | CALCULATE(\[Zmiana netto zapasów\], 'Wpisy zestawienia'\[Nazwa kategorii - poziom 2\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Zapasy sprzedane                          | CALCULATE(\[Zmiana netto zapasów\], 'Wpisy zestawienia'\[Nazwa kategorii - poziom 2\_\] = "Sprzedane")                                                                                                                                                                                                                                                                                                                                                                             |
| Dokładność zapasów wg kwoty            | IF(\[Saldo końcowe zapasów\] &lt;= 0, IF(OR(\[Kwota inwentaryzacji zapasów\] &lt;&gt; 0, \[Saldo końcowe zapasów\] &lt; 0), 0, 1), MAX(0, (\[Saldo końcowe zapasów\] - ABS(\[Kwota inwentaryzacji zapasów\]))/\[Saldo końcowe zapasów\]))                                                                                                                                                                                                                              |
| Kwota inwentaryzacji zapasów                | CALCULATE(\[Zmiana netto zapasów\], 'Wpisy zestawienia'\[Nazwa kategorii - poziom 3\_\] = "Inwentaryzacja")                                                                                                                                                                                                                                                                                                                                                                         |
| Wiekowanie zapasów                         | if(ISBLANK(max('Kalendarze obrachunkowe'\[Data\])), blank(), MAX(0, MIN(\[Ilość z przyjęć w wiekowaniu zapasów\], \[Ilość salda końcowego w wiekowaniu zapasów\] - \[Ilość z przyjęć w wiekowaniu zapasów w przyszłości\]))) \* \[Średni koszt jednostkowy zapasów\]                                                                                                                                                                                                                                |
| Ilość z przyjęć w wiekowaniu zapasów       | IF(\[minDate\] = \[minDateAllSelected\], CALCULATE(\[Ilość zmiany netto zapasów\], 'Wpisy zestawienia'\[Ilość\] &gt; 0, FILTER(ALLEXCEPT('Kalendarze obrachunkowe', 'Kalendarze obrachunkowe'\[LedgerRecId\], 'jednostki'\[Identyfikator\], 'jednostki'\[Nazwa\], 'Księgi'\[Waluta\], 'Księgi'\[Opis\], 'Księgi'\[Nazwa\]), 'Kalendarze obrachunkowe'\[Data\] &lt;= MAX('Kalendarze obrachunkowe'\[Dat\]))), CALCULATE(\[Ilość zmiany netto zapasów\], 'Wpisy zestawienia'\[Ilość\] &gt; 0)) |
| Ilość salda końcowego w wiekowaniu zapasów | \[Ilość salda końcowego zapasów\] + CALCULATE(\[Ilość zmiany netto zapasów\], FILTER(ALLEXCEPT('Kalendarze obrachunkowe', 'Kalendarze obrachunkowe'\[LedgerRecId\], 'jednostki'\[Identyfikator\], 'jednostki'\[Nazwa\], 'Księgi'\[Waluta\], 'Księgi'\[Opis\], 'Księgi'\[Nazwa\]), 'Kalendarze obrachunkowe'\[Data\] &gt; max('Kalendarze obrachunkowe'\[Data\]) ))                                                                                                                                 |
| Przyjęcia w wiekowaniu zapasów w przyszłości  | CALCULATE(\[Zmiana netto zapasów\], 'Wpisy zestawienia'\[Kwota\] &gt; 0, FILTER(ALLEXCEPT('Kalendarze obrachunkowe', 'Kalendarze obrachunkowe'\[LedgerRecId\], 'jednostki'\[Identyfikator\], 'jednostki'\[Nazwa\], 'Księgi'\[Waluta\], 'Księgi'\[Opis\], 'Księgi'\[Nazwa\]), 'Kalendarze obrachunkowe'\[Data\] &gt; MAX('Kalendarze obrachunkowe'\[Data\])))                                                                                                                                             |
| Średni koszt jednostkowy zapasów                 | CALCULATE(\[Saldo końcowe zapasów\] / \[Ilość salda końcowego zapasów\],ALLEXCEPT('Kalendarze obrachunkowe', 'Kalendarze obrachunkowe'\[LedgerRecId\], 'jednostki'\[Identyfikator\], 'jednostki'\[Nazwa\], 'Księgi'\[Waluta\], 'Księgi'\[Opis\], 'Księgi'\[Nazwa\]))                                                                                                                                                                                                                 |
| Odchylenia zakupów                      | CALCULATE(SUM(\[Kwota\]), 'Wpisy zestawienia'\[Nazwa kategorii - poziom 2\_\] = "Zaopatrzono", 'Wpisy zestawienia'\[Typ zestawienia\] = "Odchylenie")                                                                                                                                                                                                                                                                                                                              |
| Saldo początkowe PWT                   | CALCULATE(\[Saldo początkowe\], 'Wpisy zestawienia'\[Typ zestawienia\] = "PWT")                                                                                                                                                                                                                                                                                                                                                                                            |
| Saldo końcowe PWT                      | CALCULATE(\[Saldo końcowe\], 'Wpisy zestawienia'\[Typ zestawienia\] = "PWT")                                                                                                                                                                                                                                                                                                                                                                                               |
| Zmiana netto PWT                          | CALCULATE(\[Zmiana netto\], 'Wpisy zestawienia'\[Typ zestawienia\] = "PWT")                                                                                                                                                                                                                                                                                                                                                                                                   |
| % zmiany netto PWT                        | IF(\[Saldo końcowe PWT\] = 0, 0, \[Zmiana netto PWT\] / \[Saldo końcowe PWT\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Odchylenia produkcji                    | CALCULATE(SUM(\[Kwota\]), 'Wpisy zestawienia'\[Nazwa kategorii - poziom 2\_\] = "ManufacturedCost", 'Wpisy zestawienia'\[Typ zestawienia\] = "Odchylenie")                                                                                                                                                                                                                                                                                                                      |
| Nazwa kategorii - poziom 1                 | switch(\[Nazwa kategorii - poziom 1\_\], "Brak", "Brak", "NetSourcing", "Pozyskiwanie netto", "NetUsage", "Użycie netto", "NetConversionCost", "Koszt konwersji netto", "NetCostOfGoodsManufactured", "Koszt wytworzonych towarów netto", "BeginningBalance", "Saldo początkowe")                                                                                                                                                                                                         |
| Nazwa kategorii - poziom 2                 | switch(\[Nazwa kategorii - poziom 2\_\], "Brak", "Brak", "Zaopatrzono", "Zaopatrzono", "Zlikwidowano", "Zlikwidowano", "Przeniesione", "Przeniesione", "Sprzedane", "Sprzedane", "ConsumedMaterialsCost", "Koszt materiałów zużytych", "ConsumedManufacturingCost", "Wykorzystany koszt produkcji", "ConsumedOutsourcingCost", "Wykorzystany koszt outsourcingu", "ConsumedIndirectCost", "Wykorzystany koszt pośredni", "ManufacturedCost", "Koszt wyprodukowanych", "Odchylenia", "Odchylenia")                            |
| Nazwa kategorii - poziom 3                 | switch(\[Nazwa kategorii - poziom 3\_\], "Brak", "Brak", "Inwentaryzacja", "Brak", "ProductionPriceVariance", "Cena produkcji", "QuantityVariance", "Ilość", "SubstitutionVariance", "Podstawianie", "ScrapVariance", "Odpadki", "LotSizeVariance", "Rozmiar partii", "RevaluationVariance", "Przeszacowanie", "PurchasePriceVariance", "Cena zakupu", "CostChangeVariance", "Zmiana kosztu", "RoundingVariance", "Odchylenie zaokrąglania")                                                   |

Następujące najważniejsze wymiary są używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i zapewnienia lepszego wglądu analitycznego.

| Jednostka           | Przykłady atrybutów                       |
|------------------|----------------------------------------------|
| Jednostki         | Identyfikator, Nazwa                                     |
| Kalendarze obrachunkowe | Kalendarz, Miesiąc, Okres, Kwartał, Rok       |
| Cele wskaźnika KPI        | Cel dokładności zapasów, Cel obrotu magazynowego |
| Księgi          | Waluta, Nazwa, Opis                  |
| Oddziały            | Identyfikator, Nazwa, Kraj, Miejscowość                      |

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](..\data-entities\data-entities.md)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](configure-power-bi-integration.md)





