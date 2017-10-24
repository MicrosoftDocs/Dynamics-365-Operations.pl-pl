---
title: "Zawartość usługi Power BI dotycząca wyników sprzedaży i rentowności"
description: "W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Wyniki sprzedaży i rentowności. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: YuyuScheller
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 97c8f3d57ba1accb8d940c7edd3ddcac2146968b
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Zawartość usługi Power BI dotycząca wyników sprzedaży i rentowności

[!include[banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Wyniki sprzedaży i rentowności**. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości usługi Power BI **Wyniki sprzedaży i rentowności** umożliwia kierownikom sprzedaży monitorowanie głównych wskaźników sprzedaży: przychodów, zysku brutto i marż zysku. Wykorzystuje dane transakcyjne sprzedaży i przedstawia zarówno zagregowany widok wyników sprzedaży w całej firmie, jak i podział wyników sprzedaży na odbiorców i produkty.

Raporty eksponują zmiany wzrostu przychodów i zysków w czasie. W związku z tym mogą służyć do ostrzegania menedżerów o pozytywnych i negatywnych trendach dla poszczególnych odbiorców i produktów. Ponadto wykresy porównują przychody i rentowność różnych kategorii produktów i grup odbiorców. Dzięki temu menedżerowie kategorii i kierownicy regionalni mogą identyfikować maruderów i liderów. Na koniec kompleksowy raport przestawia przychody z poszczególnych odbiorców względem marży zysku. W ten sposób opiekunowie klientów otrzymują wiarygodną bazę, w oparciu o którą mogą dostosowywać działania sprzedażowe i marketingowe do profilu każdego odbiorcy. 

Pakiet zawartości **Wyniki sprzedaży i rentowności** umożliwia kierownikom sprzedaży analizowanie wyników sprzedaży pod następującymi względami:

-   Przychody od początku roku (według grup odbiorców i indywidualnych odbiorców, kategorii sprzedaży, poszczególnych produktów i regionów geograficznych)
-   Zmiana przychodu rok do roku (według regionów odbiorców i kategorii sprzedaży)

Rentowność można analizować w następujące sposoby:

-   Zysk brutto i marża zysku (według grup odbiorców i kategorii sprzedaży produktów)
-   Zmiana zysku brutto rok do roku
-   Rentowność odbiorców (przychody względem marży brutto)

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017 r.), pakiet zawartości usługi Power BI **Wyniki sprzedaży i rentowności** jest wyświetlany na stronie **Wyniki sprzedaży i rentowności** (**Sprzedaż i marketing** > **Zapytania i raporty** > **Analiza wydajności sprzedaży** > **Wyniki sprzedaży i rentowności**). 

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

## <a name="extending-the-power-bi-content"></a>Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI
Za pomocą pakietów zawartości dostępnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) można dostarczać zaawansowane funkcje analityczne osobom, które się nie logują w programie Microsoft Dynamics 365. Te pakiety zawartości można modyfikować, tak aby zawierały inne raporty lub wizualizacje, a następnie publikować je w swojej dzierżawie usługi Power BI.com na potrzeby wykonywania analiz.

Pakiet zawartości usługi Power BI **Wyniki sprzedaży i rentowności** znajduje się w bibliotece zasobów wspólnych w usłudze LCS. Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md). Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

Uważaj, aby pobrać pakiet zawartości **Wyniki sprzedaży i rentowności** mający zastosowanie do używanej wersji systemu Dynamics 365.

> [!NOTE]
> Jeśli używasz programu Microsoft Dynamics 365 for Operations w wersji 1611, ten pakiet zawartości usługi Power BI wymaga poprawki KB 4011327. Po zalogowaniu się w usłudze LCS można uzyskać dostęp do tej poprawki KB tutaj: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Następujące dane są używane do wypełniania raportów w pakiecie zawartości usługi Power BI **Wyniki sprzedaży i rentowności**. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md). 

Zagregowane miary w tym pakiecie zawartości są podzbiorem zagregowanych miar, które były dostępne w module Sprzedaż w programach Microsoft Dynamics AX 2012 i Microsoft Dynamics AX 2012 R3. Aby zagregowane miary modułu można było umieścić w magazynie jednostek, trzeba ustawić te miary jako wdrażalne. Aby uzyskać więcej informacji, zobacz procedurę umieszczania zagregowanych miar w magazynie jednostek we wpisie na blogu [Integracja usługi Power BI z magazynem jednostek w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). 

Następujące najważniejsze zagregowane miary jednostki Wiersze faktury są używane jako podstawa w pakiecie zawartości:

| Jednostka        | Najważniejsze zagregowane miary                   | Źródło danych programu Dynamics 365                    | Pole                                        | opis                                   |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|----------------------------------------------|
| Wiersze faktury | Przychód                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Kwota w walucie rozliczeniowej.            |
|               | Koszt sprzedanych towarów                           | InventTrans                                     | SUM(CostAmountPosted + CostAmountAdjustment) | Suma kwoty kosztu i korekty.    |
|               | Kwota wiersza prowizji — waluta rozliczeniowa | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Kwota prowizji w walucie rozliczeniowej. |

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

