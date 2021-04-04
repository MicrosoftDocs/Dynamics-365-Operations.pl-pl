---
title: Pakiet zawartości usługi Power BI Wyniki sprzedaży i rentowności
description: W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Wyniki sprzedaży i rentowności.
author: ShylaThompson
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesProfitabilityPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6eb5a78c6ac4ad13ad1d263c557359ad2f789cc0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569919"
---
# <a name="sales-and-profitability-performance-power-bi-content"></a>Pakiet zawartości usługi Power BI Wyniki sprzedaży i rentowności

[!include [banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości **Wyniki sprzedaży i rentowności** usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości usługi Power BI **Wyniki sprzedaży i rentowności** umożliwia kierownikom sprzedaży monitorowanie głównych wskaźników sprzedaży: przychodów, zysku brutto i marż zysku. Wykorzystuje dane transakcyjne sprzedaży i przedstawia zarówno zagregowany widok wyników sprzedaży w całej firmie, jak i podział wyników sprzedaży na odbiorców i produkty.

Raporty eksponują zmiany wzrostu przychodów i zysków w czasie. W związku z tym mogą służyć do ostrzegania menedżerów o pozytywnych i negatywnych trendach dla poszczególnych odbiorców i produktów. Ponadto wykresy porównują przychody i rentowność różnych kategorii produktów i grup odbiorców. Dzięki temu menedżerowie kategorii i kierownicy regionalni mogą identyfikować maruderów i liderów. Na koniec kompleksowy raport przestawia przychody z poszczególnych odbiorców względem marży zysku. W ten sposób opiekunowie klientów otrzymują wiarygodną bazę, w oparciu o którą mogą dostosowywać działania sprzedażowe i marketingowe do profilu każdego odbiorcy.

Pakiet zawartości **Wyniki sprzedaży i rentowności** umożliwia kierownikom sprzedaży analizowanie wyników sprzedaży pod następującymi względami:

- Przychody od początku roku (według grup odbiorców i indywidualnych odbiorców, kategorii sprzedaży, poszczególnych produktów i regionów geograficznych)
- Zmiana przychodu rok do roku (według regionów odbiorców i kategorii sprzedaży)

Rentowność można analizować w następujące sposoby:

- Zysk brutto i marża zysku (według grup odbiorców i kategorii sprzedaży produktów)
- Zmiana zysku brutto rok do roku
- Rentowność odbiorców (przychody względem marży brutto)

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Pakiet zawartości Power BI **Wyniki w zakresie sprzedaży i rentowności** jest wyświetlany na stronie **Wyniki w zakresie sprzedaży i rentowności** (**Sprzedaż i marketing** \> **Zapytania i raporty** \> **Analiza wydajności sprzedaży** \> **Wyniki w zakresie sprzedaży i rentowności**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki umieszczone w pakiecie zawartości usługi Power BI
Pakiet zawartości usługi Power BI **Wyniki sprzedaży i rentowności** zawiera raport obejmujący zbiór miar. Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele. Następująca tabela zawiera przegląd wizualizacji dostępnych w pakiecie zawartości.

| Strona raportu            | Wykresy                                     | Kafelki                                                   |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| Przychody wg odbiorców    | 10 najważniejszych odbiorców wg przychodów                | Całkowity przychód                                           |
|                        | Całkowity przychód wg grupy odbiorców            | Wzrost przychodu r/r                                      |
|                        | Średni przychód z odbiorcy wg grupy odbiorców | Marża brutto                                            |
|                        | Przychód i zysk brutto wg grupy odbiorców   |                                                         |
| Przychód wg produktu     | Przychód i zysk brutto wg kategorii sprzedaży   | Łączna liczba produktów: \#                                    |
|                        | 10 najważniejszych produktów wg przychodów                 | Całkowita liczba aktywnych produktów i procent całości |
|                        | Całkowity przychód wg kategorii sprzedaży            | Liczba produktów odpowiedzialnych za 80% przychodu           |
| Przychód wg okresu\*    | Przychód wg miesiąca                           | Wzrost przychodu r/r                                      |
|                        | Odchylenie przychodów za ostatni okres r/r             | % wzrostu przychodu r/r                                    |
|                        | Odchylenie całkowitej sprzedaży wg regionu odbiorców    |                                                         |
| Przychód wg lokalizacji    | Przychód ze sprzedaży wg miejscowości                      |                                                         |
|                        | % wzrostu przychodu r/r                       |                                                         |
|                        | Przychód ze sprzedaży wg regionu                    |                                                         |
| Rentowność odbiorcy | Marża brutto względem przychodu wg odbiorcy   | Zysk brutto, marża brutto, wzrost przychodu r/r          |
| Analiza rentowności | Przychód i zysk brutto wg miesiąca          |                                                         |
|                        | 15 najważniejszych odbiorców wg marży brutto           |                                                         |
|                        | Zysk brutto wg miesiąca r/r                 |                                                         |

\* Przychód w tym i ubiegłym roku oraz wzrost według kategorii sprzedaży.

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Następujące dane są używane do wypełniania raportów w pakiecie zawartości usługi Power BI **Wyniki sprzedaży i rentowności**. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

Zagregowane miary w tym pakiecie zawartości są podzbiorem zagregowanych miar, które były dostępne w module Sprzedaż w programach Microsoft Dynamics AX 2012 i Microsoft Dynamics AX 2012 R3. Aby zagregowane miary modułu można było umieścić w magazynie jednostek, trzeba ustawić te miary jako wdrażalne. Aby uzyskać więcej informacji, zobacz procedurę umieszczania zagregowanych miar w magazynie jednostek we wpisie na blogu [Integracja usługi Power BI z magazynem jednostek w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/).

Następujące najważniejsze zagregowane miary jednostki Wiersze faktury są używane jako podstawa w pakiecie zawartości:

| Jednostka        | Najważniejsze zagregowane miary                   | Źródło danych programu Dynamics 365 | Pole                                        | opis                                       |
|---------------|----------------------------------------------|------------------------------|----------------------------------------------|---------------------------------------------------|
| Wiersze faktury | Przychód                                      | CustInvoiceTrans             | SUM(LineAmountMST)                           | Kwota w walucie rozliczeniowej.            |
|               | Koszt sprzedanych towarów                           | InventTrans                  | SUM(CostAmountPosted + CostAmountAdjustment) | Suma kwoty kosztu i korekty.    |
|               | Kwota wiersza prowizji — waluta rozliczeniowa | CustInvoiceTrans             | SUM(CommissAmountMST)                        | Kwota prowizji w walucie rozliczeniowej. |

W poniższej tabeli przedstawiono najważniejsze zagregowane miary jednostki Wiersze faktury używane do tworzenia kilku miar obliczanych w zestawie danych pakietu zawartości.

| Pomiar           | Obliczenie                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| Zysk brutto      | SUM(Przychód – KWS – Prowizja – Podatek (uwzględniony w kwocie wiersza faktury dla odbiorcy))          |
| Marża brutto      | SUM(Zysk brutto / (Przychód – Podatek (uwzględniony w kwocie wiersza faktury dla odbiorcy)))             |
| Przychód w ubiegłym roku | Przychód w ubiegłym roku = CALCULATE(SUM('Wiersze faktury'\[Przychód\]), SAMEPERIODLASTYEAR(Daty\[Data\]) |

Następująca najważniejsze wymiary w module Sprzedaż są używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i lepszego wglądu analitycznego.

| Jednostka           | Przykłady atrybutów                               |
|------------------|------------------------------------------------------|
| Odbiorcy        | Grupy odbiorców, Regiony odbiorców, Adres, Branża |
| Produkty         | Numer produktu, Nazwa produktu, Nazwa grupy pozycji       |
| Kategorie sprzedaży | Nazwy kategorii sprzedaży                                 |
| Firmy   | Nazwy firm                                   |
| Daty            | Daty                                                |

Domyślnie pakiet zawartości przestawia dane bieżącego roku kalendarzowego. Można jednak zmienić wartość filtra dat w sekcji filtrów raportu. Można również zmienić wartość filtra firm.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]