---
title: "Zarządzanie kosztami Power BI zawartości"
description: "W tym temacie opisano, co jest zawarte w zarządzanie kosztami zawartości Power BI. Wyjaśnia, jak uzyskać dostęp do raportów BI zasilania i zawiera informacje o modelu danych i podmiotów, które są używane do tworzenia treści."
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
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: e4de011e6eeac58643b828b65e24b874d981d5e7
ms.lasthandoff: 03/31/2017


---

# <a name="cost-management-power-bi-content"></a>Zarządzanie kosztami Power BI zawartości

W tym temacie opisano, co jest zawarte w zarządzanie kosztami zawartości Power BI. Wyjaśnia, jak uzyskać dostęp do raportów BI zasilania i zawiera informacje o modelu danych i podmiotów, które są używane do tworzenia treści.

# <a name="overview"></a>Przegląd

**Zarządzanie kosztami** Microsoft Power BI zawartość jest przeznaczona do księgowych zapasów lub osobom w organizacji, którzy są odpowiedzialni za zapasy. **Zarządzanie kosztami** Power BI zawartości zapewnia kierowniczego wgląd w spisu i pracy w toku (PWT) spisu i jak koszt przepływa przez nich według kategorii w czasie. Informacje można również jako uzupełnienie szczegółowe sprawozdania finansowego.

## <a name="key-measures"></a>Główne środki

+ Saldo początkowe
+ Saldo końcowe
+ Zmiana netto
+ Obroty netto w %
+ Wiekowanie

## <a name="key-performance-indicators"></a>Kluczowe wskaźniki wydajności
+ Obrót magazynowy
+ Dokładność zapasów

Główne źródło danych dla CostAggregatedCostStatementEntryEntity jest w tabeli CostStatementCache. Ta tabela jest zarządzany przez architekturę pamięci podręcznej zestawu danych. Domyślnie tabela jest aktualizowana co 24 godziny, ale można włączyć ręczne aktualizacje w konfiguracji pamięci podręcznej danych. Można następnie wykonaj ręczną aktualizację **Zarządzanie kosztami** lub **analiza kosztów** obszaru roboczego. Po uruchomieniu aktualizacji CostStatementCache, musisz zaktualizować połączenie OData na mocy BI.com, aby zobaczyć zaktualizowane dane na stronie. Środki wariancji (zakup, produkcja) w tej zawartości Power BI odnoszą się tylko do elementów, które są wyceniane przez metodę magazynu koszt standardowy. Odchylenie produkcji jest obliczana jako różnica między kosztami aktywne i zrealizowana. Odchylenie produkcji jest obliczana, gdy zlecenie produkcyjne ma stan **zakończone**. Aby uzyskać więcej informacji o typach odchylenia produkcji i sposobu obliczania każdego typu, zobacz [dotyczących analizy wariancji dla zlecenia produkcyjnego na zakończone](https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Dostęp do zawartości BI zasilania
**Zarządzanie kosztami** Power BI zawartość jest dostępna z PowerBI.com. Aby uzyskać więcej informacji na temat sposobu połączenia i załadować Twojego Microsoft Dynamics 365 dla danych operacji, zobacz [BI zasilania dostęp do zawartości z PowerBI.com](power-bi-home-page.md).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki, które są zawarte w treści BI zasilania
Zawartość zawiera zestaw stron raportu. Każda strona zawiera zestaw miar, które są przedstawiane jako wykresy, tabliczki i tabelami. Poniższa tabela zawiera omówienie wizualizacje w **Zarządzanie kosztami** Power BI zawartości.

| Strony raportu | Wykresy | Stanowiska |
|---|---|---|
|Zapasy ogólny (domyślnie dla bieżącego okresu) |Dokładność |Środki zapasów:<br>Zapasów, Saldo końcowe<br>Obroty magazynowe<br>% Obroty netto zapasów<br>|
| |Obrót magazynowy | |
| |Saldo końcowe przez grupę zasobów magazynowych | |
| |Obroty netto zapasów według kategorii nazwa poziomu 1 i poziomu nazwa kategorii 2| |
| |Odchylenia zakupu przez grupy zasobów i poziom nazwa kategorii 3 | |
|Zapasy przez witryny (ustawienie domyślne w bieżącym okresie) |Saldo końcowe według nazwy witryny i grupy zasobów magazynowych | |
| |Nazwa witryny i grupy zasobów obrotu magazynowego | |
| |Saldo końcowe według miasta i zasobów grupy zapasów | |
|Zapasy przez grupę zasobów (domyślnie dla bieżącego okresu) |Środki zapasów | |
| |Dokładność zapasów o kwotę przez grupę zasobów | |
| |Obrotu magazynowego o kwotę przez grupę zasobów | |
|Zapasy r/r (domyślny bieżącego roku w porównaniu z poprzedniego roku) |Środki zapasów | |
| |Kluczowe wskaźniki wydajności magazynu:<br>Obrót magazynowy<br>Dokładność zapasów | |
| |Saldo końcowe przez rok i zasobów grupy zapasów | |
| |Odchylenia zakupu według roku i kategoria Nazwa poziomu 3 | |
|Wiekowania zapasów (domyślnie przez bieżący rok) |Wiekowania zapasów według kwartałów i zasobów grupy | |
| |Wiekowania zapasów według nazw kwartałów i witryny | |
|PWT ogólny (domyślnie dla bieżącego okresu) |PWT netto zmienić poziom nazwa kategorii 1, a nazwa kategorii poziom 2 |Środki PWT pracy w toku:<br>Saldo końcowe PWT<br>Obroty netto PWT.<br>% Obroty netto PWT.<br> |
| |Odchylenia produkcji przez grupę zasobów i poziom nazwa kategorii 3 | |
| |Obroty netto PWT według grupy zasobów | |
|PWT według oddziałów (domyślnie dla bieżącego okresu) |Środki PWT pracy w toku | |
| |PWT netto zmienić nazwę witryny, a nazwa kategorii poziom 2 | |
| |Odchylenia produkcji według nazwy witryny i poziom nazwa kategorii 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dynamics 365 dla danych operacji jest używany do wypełniania stron raportów w **Zarządzanie kosztami** Power BI zawartości. Te dane jest reprezentowany jako zagregowanych wskaźników, które są umieszczane w magazynie podmiot, który jest bazy danych Microsoft SQL, który jest zoptymalizowany pod kątem analytics. Aby uzyskać więcej informacji, zobacz [omówienie Power BI Integracja z magazynu jednostki](power-bi-integration-entity-store.md). Następujące kluczowe pomiary agregacji są wykorzystywane jako podstawa zawartości.

| Jednostka            | Klucz zagregowanego wskaźnika | Źródło danych dla usługi Dynamics 365 dla operacji | Pole             | opis                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Zapisów wyciągu | Zmiana netto                | CostAggregatedCostStatementEntryEntity      | Suma (\[kwoty\])   | Kwota w walucie rozliczeniowej |
| Zapisów wyciągu | Ilość obroty netto       | CostAggregatedCostStatementEntryEntity      | Suma (\[ilość\]) |                                   |

W poniższej tabeli przedstawiono, jak klucza zagregowanych wskaźników są używane do tworzenia kilku miary obliczeniowe w zestawie danych zawartości.

| Pomiar                                 | Sposób obliczania środka                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo początkowe                       | \[Saldo końcowe\]-\[obroty netto\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Ilość (saldo) początku              | \[Końcowa ilość (saldo)\]-\[zmiana ilości netto\]                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Saldo końcowe                          | OBLICZ (Suma (\[kwota\]), filtr (ALLEXCEPT ("Kalendarze obrachunkowe", "Kalendarze obrachunkowe"\[LedgerRecId\], 'elementy'\[ID\], 'elementy'\[nazwa\], "Ksiąg"\[waluty\], "Ksiąg"\[opis\], "Ksiąg"\[nazwa\]), "Kalendarze obrachunkowe"\[data\]&lt;= MAX ("Kalendarze obrachunkowe"\[data\])))                                                                                                                                                                                           |
| Końcowa ilość (saldo)                 | OBLICZ (Suma (\[ilość\]), filtr (ALLEXCEPT ("Kalendarze obrachunkowe", "Kalendarze obrachunkowe"\[LedgerRecId\], 'elementy'\[ID\], 'elementy'\[nazwa\], "Ksiąg"\[waluty\], "Ksiąg"\[opis\], "Ksiąg"\[nazwa\]), "Kalendarze obrachunkowe"\[data\]&lt;= MAX ("Kalendarze obrachunkowe"\[data\])))                                                                                                                                                                                         |
| Zapasów, saldo początkowe             | OBLICZ (\[saldo początkowe\], "Zapisów wyciągu"\[typu instrukcji\] = "Zapasy")                                                                                                                                                                                                                                                                                                                                                                                      |
| Zapasów, Saldo końcowe                | OBLICZ (\[saldo końcowe\], "Zapisów wyciągu"\[typu instrukcji\] = "Zapasy")                                                                                                                                                                                                                                                                                                                                                                                         |
| Obroty magazynowe                    | OBLICZ (\[obroty netto\], "Zapisów wyciągu"\[typu instrukcji\] = "Zapasy")                                                                                                                                                                                                                                                                                                                                                                                             |
| Ilość zapasów obroty netto           | OBLICZ (\[zmiana ilości netto\], "Zapisów wyciągu"\[typu instrukcji\] = "Zapasy")                                                                                                                                                                                                                                                                                                                                                                                    |
| % Obroty netto zapasów                  | IF (\[zapasów saldo końcowe\] = 0, 0, \[zapasów obroty netto\] / \[zapasów saldo końcowe\])                                                                                                                                                                                                                                                                                                                                                                           |
| Wielkość obrotu magazynowego                | Jeżeli (lub (\[zapasów średnie saldo\]&lt;= 0, \[zapasów, sprzedaży lub wykorzystania problemów\]&gt;= 0), 0, ABS (\[zapasów, sprzedaży lub wykorzystania problemów\]) /\[zapasów średnie saldo\])                                                                                                                                                                                                                                                                                                  |
| Średnie saldo magazynowe               | (\[Zapasów saldo końcowe\] + \[zapasów saldo początkowe\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Zapasów, sprzedaży lub wykorzystania problemów       | \[Zapasy sprzedane\] + \[koszt materiałów zużytych zapasów\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Koszt materiałów zużytych zapasów        | OBLICZ (\[obroty netto zapasów\], "Zapisów wyciągu"\[nazwa kategorii - poziom 2\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Zapasy sprzedane                          | OBLICZ (\[obroty netto zapasów\], "Zapisów wyciągu"\[nazwa kategorii - poziom 2\_\] = "Sprzedane")                                                                                                                                                                                                                                                                                                                                                                             |
| Dokładność zapasów o kwotę            | IF (\[zapasów saldo końcowe\]&lt;= 0, jeżeli (lub (\[zapasów kwota zliczona\]&lt;&gt; 0, \[zapasów saldo końcowe\]&lt; 0), 0, 1), MAX (0, (\[zapasów saldo końcowe\] -ABS (\[zapasów kwota zliczona\])) /\[zapasów saldo końcowe\]))                                                                                                                                                                                                                              |
| Zliczona kwota zapasów                | OBLICZ (\[obroty netto zapasów\], "Zapisów wyciągu"\[nazwa kategorii — poziom 3\_\] = "Zliczanie")                                                                                                                                                                                                                                                                                                                                                                         |
| Wiekowanie zapasów                         | Jeśli (ISBLANK (max ("Kalendarze obrachunkowe"\[data\])), blank(), MAX (0, MIN (\[wiekowania zapasów potwierdzeń w ilości\], \[zapasów wiekowania końcową ilość (saldo)\] - \[wiekowania zapasów ilość przychodów w przyszłości\]))) \*\[koszt jednostkowy avg zapasów\]                                                                                                                                                                                                                                |
| Starzenie się ilość przyjęć magazynowych       | IF (\[minDate\] = \[minDateAllSelected\], OBLICZ (\[obroty netto ilość zapasów\], "Zapisów wyciągu"\[ilość\]&gt; 0, filtr (ALLEXCEPT ("Kalendarze obrachunkowe", "Kalendarze obrachunkowe"\[LedgerRecId\], 'elementy'\[ID\], 'elementy'\[nazwa\], "Ksiąg"\[waluty\], "Ksiąg"\[opis\], "Ksiąg"\[nazwa\]), "Kalendarze obrachunkowe"\[data\]&lt;= MAX ("Kalendarze obrachunkowe"\[data\]))), OBLICZ (\[obroty netto ilość zapasów\], "Zapisów wyciągu"\[ilość\]&gt; 0)) |
| Saldo Ilość końcowa wiekowania zapasów | \[Zapasów saldo Ilość końcowa\] + OBLICZ (\[obroty netto ilość zapasów\], filtr (ALLEXCEPT ("Kalendarze obrachunkowe", "Kalendarze obrachunkowe"\[LedgerRecId\], 'elementy'\[ID\], 'elementy'\[nazwa\], "Ksiąg"\[waluty\], "Ksiąg"\[opis\], "Ksiąg"\[nazwa\]), "Kalendarze obrachunkowe"\[data\]&gt; max ("Kalendarze obrachunkowe"\[data\])))                                                                                                                                 |
| W przyszłości przychodów wiekowania zapasów  | OBLICZ (\[zapasów obroty netto\], "Zapisów wyciągu"\[kwota\]&gt; 0, filtr (ALLEXCEPT ("Kalendarze obrachunkowe", "Kalendarze obrachunkowe"\[LedgerRecId\], 'elementy'\[ID\], 'elementy'\[nazwa\], "Ksiąg"\[waluty\], "Ksiąg"\[opis\], "Ksiąg"\[nazwa\]), "Kalendarze obrachunkowe"\[data\]&gt; MAX ("Kalendarze obrachunkowe"\[data\])))                                                                                                                                             |
| Koszt jednostkowy avg zapasów                 | OBLICZ (\[zapasów saldo końcowe\] / \[ilość bilans końcowy zapasów\], ALLEXCEPT ("Kalendarze obrachunkowe", "Kalendarze obrachunkowe"\[LedgerRecId\], 'elementy'\[ID\], 'elementy'\[nazwa\], "Ksiąg"\[waluty\], "Ksiąg"\[opis\], "Ksiąg"\[nazwa\]))                                                                                                                                                                                                                 |
| Odchylenia zakupu                      | OBLICZ (Suma (\[kwoty\]), "Zapisów wyciągu"\[nazwa kategorii - poziom 2\_\] = "Procured", "Zapisów wyciągu"\[typu instrukcji\] = "Odchylenie")                                                                                                                                                                                                                                                                                                                              |
| Saldo początkowe PWT                   | OBLICZ (\[saldo początkowe\], "Zapisów wyciągu"\[typu instrukcji\] = "PWT")                                                                                                                                                                                                                                                                                                                                                                                            |
| Saldo końcowe PWT                      | OBLICZ (\[saldo końcowe\], "Zapisów wyciągu"\[typu instrukcji\] = "PWT")                                                                                                                                                                                                                                                                                                                                                                                               |
| Obroty netto PWT.                          | OBLICZ (\[obroty netto\], "Zapisów wyciągu"\[typu instrukcji\] = "PWT")                                                                                                                                                                                                                                                                                                                                                                                                   |
| % Obroty netto PWT.                        | IF (\[PWT saldo końcowe\] = 0, 0, \[obroty netto PWT.\] / \[PWT saldo końcowe\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Odchylenia produkcji                    | OBLICZ (Suma (\[kwoty\]), "Zapisów wyciągu"\[nazwa kategorii - poziom 2\_\] = "ManufacturedCost", "Zapisów wyciągu"\[typu instrukcji\] = "Odchylenie")                                                                                                                                                                                                                                                                                                                      |
| Nazwa kategorii – poziom 1                 | Przełącz (\[nazwa kategorii — poziom 1\_\], "None", "Brak", "NetSourcing", "Net pozyskiwania", "NetUsage", "Net użytkowania", "NetConversionCost", "Net kosztu konwersji", "NetCostOfGoodsManufactured", "Net koszty wytworzonych towarów", "BeginningBalance", "Saldo początkowe")                                                                                                                                                                                                         |
| Nazwa kategorii — poziom 2                 | Przełącz (\[nazwa kategorii - poziom 2\_\], "None", "Brak", "Procured", "Procured", "Disposed", "Disposed", "Przetransferowane", "Przetransferowane", "Sprzedane", "Sprzedane", "ConsumedMaterialsCost", "Koszt materiałów zużytych", "ConsumedManufacturingCost", "Zużyte kosztów produkcji", "ConsumedOutsourcingCost", "Outsourcing koszt zużytego", "ConsumedIndirectCost", "Pośrednie zużyto w kosztów", "ManufacturedCost", "Wyprodukowany kosztów", "Odchyleń", "Odchyleń")                            |
| Nazwa kategorii — poziom 3                 | Przełącz (\[nazwa kategorii — poziom 3\_\], "None", "Brak", "Inwentaryzacji", "Brak", "ProductionPriceVariance", "Cena produkcyjna", "QuantityVariance", "Ilość", "SubstitutionVariance", "Zamiana", "ScrapVariance", "Złom", "LotSizeVariance", "Wielkości partii", "RevaluationVariance", "Przeszacowania", "PurchasePriceVariance", "Ceny zakupu", "CostChangeVariance", "Zmiana kosztu", "RoundingVariance", "Odchylenie zaokrąglania")                                                   |

Następujące wymiary kluczy są używane jako filtry do plasterka łącznej wartości, tak aby osiągnąć większą ziarnistość i zapewniają lepszy wgląd analityczne.

| Jednostka           | Przykłady atrybutów                       |
|------------------|----------------------------------------------|
| Jednostki         | Identyfikator, nazwa                                     |
| Kalendarze obrachunkowe | Kalendarz, miesiąc, okres, kwartał, rok       |
| Cele wskaźnika KPI        | Celem dokładności zapasów, celem obrotu magazynowego |
| Księgi          | Waluta, nazwa, opis                  |
| Oddziały            | ID, nazwa, kraj, Miasto                      |

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](..\data-entities\data-entities.md)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](configure-power-bi-integration.md)



