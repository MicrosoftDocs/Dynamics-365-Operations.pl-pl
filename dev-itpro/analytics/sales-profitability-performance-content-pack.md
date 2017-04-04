---
title: "Sprzedaży i rentowności wydajności Power BI zawartości"
description: "W tym temacie opisano, co jest zawarte w 365 Dynamics dla operacji - sprzedaży i rentowności performance content pack dla Microsoft Power BI. To wyjaśnia, jak uzyskać dostęp do raportów w zestawie zawartości i zawiera informacje o modelu danych i podmiotów, które są używane do tworzenia zawartości pack."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 3e6b48768bb8e69d46f1555d9300f3b878b01ff1
ms.lasthandoff: 03/31/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Sprzedaży i rentowności wydajności Power BI zawartości

W tym temacie opisano, co jest zawarte w 365 Dynamics dla operacji - sprzedaży i rentowności performance content pack dla Microsoft Power BI. To wyjaśnia, jak uzyskać dostęp do raportów w zestawie zawartości i zawiera informacje o modelu danych i podmiotów, które są używane do tworzenia zawartości pack.

<a name="overview"></a>Przegląd
--------

Ten pakiet został utworzony dla menedżerów sprzedaży do monitorowania kluczowych wskaźników sprzedaży przychodów, zysku brutto i marży zysku. Używa danych transakcyjnych sprzedaży z Dynamics 365 dla operacji i zapewnia zarówno zagregowany widok wyników sprzedaży całej firmy i podział wyników sprzedaży dla klientów i produktów. Przez wyróżnianie zmian w wzrostu przychodów i zysków w czasie, raportów może służyć do ostrzegania menedżerów o pozytywnych i negatywnych tendencji dla klientów indywidualnych i produktów. Kategoria i regionalni kierownicy sprzedaży będzie znaleźć przydatne wykresów umożliwiających porównanie przychodów i rentowności różnych kategorii produktów i grup odbiorców do siebie wyodrębnić Technologie przestarzałe i liderów. Szczegółowe sprawozdanie działki dochodów poszczególnych nabywców i menedżerowie kont oferty marży zysku Fundacji kopii danych do dobrać wysiłków sprzedaży i marketingu do każdego odbiorcy w danym profilu. Sprzedaży i rentowności wydajność content pack umożliwia menedżerom sprzedaży analizować wyniki sprzedaży według:

-   Przychody, roku do daty (przez grupy odbiorców i klientów indywidualnych, kategorii sprzedaży oraz poszczególnych produktów i regionów geograficznych)
-   Zmiana przychodu, ponad rok (według kategorii regionów i sprzedaży odbiorcy)

Rentowność może zostać przeanalizowana przez:

-   Zysk brutto i marża zysku (według grup odbiorców i kategorii sprzedaży produktów)
-   Zmiany zysku brutto, ponad rok
-   Rentowność klienta (według przychodów i marży brutto)

## <a name="accessing-the-content-pack"></a>Uzyskiwanie dostępu do zawartości pack
Sprzedaż i zyskowności Power BI content pack jest publikowany jako składnika aktywów implementacji w cyklu życia usługi (LCS) i są dostępne z usługi Dynamics 365 dla operacji. Aby uzyskać więcej informacji dotyczących sposobu uzyskania dostępu i uruchamianie raportów Power BI, zobacz [Power BI zawartości w LCS firmy Microsoft i jej partnerzy](power-bi-content-microsoft-partners.md).

## <a name="metrics-included-in-the-content-pack"></a>Metryki w zestawie zawartości
Content pack zawiera raport, który zawiera zestaw miar przedstawiane jako wykresy, tabliczki i tabelami. Poniższa tabela zawiera omówienie wizualizacje w pakiecie zawartości.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Strony raportu**        | **Charts**                                 | **Płytki**                                               |
| Przychód według odbiorcy    | 10 najlepszych odbiorców według przychodów                | Całkowity przychód                                           |
|                        | Całkowity przychód przez grupy odbiorców            | Wzrost przychodów r/r                                      |
|                        | Przychód średnia klientów według grupy odbiorców | Marża brutto                                            |
|                        | Przychody i zysk brutto według grupy odbiorców   |                                                         |
| Przychód według produktu     | Przychody i zysk brutto według kategorii sprzedaży   | Całkowita \#produktów                                    |
|                        | 10 najlepszych produktów według przychodów                 | Całkowita liczba aktywnych produktów i procent całości |
|                        | Całkowity przychód według kategorii sprzedaży            | Liczba produktów rachunkowości dla przychodów 80%           |
| Przychód według okresu\*    | Przychód według miesiąca                           | Wzrost przychodów r/r                                      |
|                        | Odchylenie końcowe przychodów, r/r             | % Wzrostu przychodów r/r                                    |
|                        | Łączne odchylenie sprzedaży według regionów klienta    |                                                         |
| Przychód według lokalizacji    | Przychody ze sprzedaży według miast                      |                                                         |
|                        | % Wzrostu przychodów r/r                       |                                                         |
|                        | Przychody ze sprzedaży według regionów                    |                                                         |
| Rentowność klienta | Marża brutto zestawione z przychodami przez klienta   | Zysk brutto, marżę brutto, wzrost przychodów r/r          |
| Analiza rentowności | Przychody i zysk brutto według miesięcy          |                                                         |
|                        | Główni kontrahenci 15 według marży brutto           |                                                         |
|                        | Zysk brutto według miesięcy, r/r                 |                                                         |

\*Przychód ten i ostatni rok i wzrostu według kategorii sprzedaży.

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dynamics 365 dla danych operacji jest używany do wypełniania raportu w sprzedaży i rentowności wydajność content pack. To jest reprezentowany jako zagregowanych wskaźników, które są umieszczane w magazynie podmiot, który jest zoptymalizowany pod kątem analytics bazy danych programu Microsoft SQL. Dowiedz się więcej o blog [Power BI integracji z magazynem encji w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Wartość zagregowana pomiary w tym pakiecie zawartości są podzbiór agregacji miar, które były dostępne w module Sprzedaż w systemie Dynamics AX 2012 i AX 2012 R3. Do drugiego etapu modułu zagregowanych wskaźników w magazynie encji należy ich rozmieszczenia. Aby uzyskać więcej informacji, zobacz procedurę jak etap zagregowanych wskaźników do magazynu jednostki w blogu [Power BI integracji z magazynem encji w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Następujące pomiary agregacji klucza podmiotu wiersze faktury są wykorzystywane jako podstawa content Pack.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entity**    | **Klucz zagregowanych wskaźników**               | **Źródło danych dla usługi Dynamics 365 dla operacji** | **Field**                                    | **Description**                          |
| Wiersze faktury | Przychód                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Kwota w walucie rozliczeniowej            |
|               | Koszt sprzedanych towarów                           | InventTrans                                     | Suma (CostAmountPosted + CostAmountAdjustment) | Kwota kosztu + korekta                 |
|               | Kwota wiersza prowizji — waluta księgowania | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Kwota prowizji w walucie rozliczeniowej |

W poniższej tabeli przedstawiono klucza agregacji pomiary encji wierszy faktury, które są używane do tworzenia kilku miary obliczeniowe w zestawie danych content pack.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Measure**       | **Obliczona jako**                                                                                |
| Zysk brutto      | Suma (przychody – KWS – Komisja – podatek (uwzględniony w kwocie wiersza faktury odbiorcy))          |
| Marża brutto      | Suma (zysk brutto / (przychód — podatek (uwzględniony w kwocie wiersza faktury odbiorcy)))             |
| Przychód za ubiegły rok | Przychód ostatni rok = OBLICZ (Suma ('Wierszy faktur'\[dochodów\]), SAMEPERIODLASTYEAR (dat\[data\]) |

Następujące kluczowe wymiary w **moduł Sprzedaż** są używane jako filtry do plasterka zagregowanych wskaźników, aby osiągnąć większą ziarnistość i lepszy wgląd analitycznych.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entity**       | **Przykłady atrybutów**                           |
| Odbiorcy        | Regiony klienta, adres, przemysł, grupy odbiorców |
| Produkty         | Numer produktu, nazwa produktu, nazwa grupy towaru       |
| Kategorie sprzedaży | Nazwy kategorii sprzedaży                                 |
| Firmy   | Nazwy firmy                                   |
| Daty            | Daty                                                |

Domyślnie content pack wyświetla dane w bieżącym roku kalendarzowym, ale można otworzyć sekcji filtry raportu i zmienić filtr daty. Można również zmienić filtr firmy.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](..\data-entities\data-entities.md)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](configure-power-bi-integration.md)



