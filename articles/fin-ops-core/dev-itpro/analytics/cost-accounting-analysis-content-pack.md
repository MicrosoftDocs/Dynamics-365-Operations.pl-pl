---
title: Pakiet zawartości Analiza rachunku kosztów dostępny w usłudze Power BI
description: W tym temacie opisano, co się znajduje w pakiecie zawartości Analiza rachunku kosztów usługi Power BI.
author: AndersGirke
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1c9a4741c1b09b8e68a9fe95d6f4effa328615d5
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093393"
---
# <a name="cost-accounting-analysis-power-bi-content"></a>Analiza rachunku kosztów dostępny w usłudze Power BI

[!include [banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości **Analiza rachunku kosztów** usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości **Analiza rachunku kosztów** usługi Power BI jest przeznaczony dla kontrolerów kosztów i innych osób odpowiedzialnych za kontrolowanie kosztów w organizacji. Obejmuje kluczowe wskaźniki, takie jak koszt, wartość oraz stawka kosztu rzeczywistego, budżetowego lub budżetu elastycznego. Wykorzystuje dane transakcji z modułu **Rachunek kosztów** i zapewnia zagregowany widok kosztów dla całej organizacji w jednej walucie raportowania. Menedżerowie mogą filtrować dane według obiektów kosztów w celu kontrolowania kosztów w podległych jednostkach organizacyjnych, nawet jeśli organizacja jest podzielona na kilka firm.

Ponieważ pakiet zawartości usługi **Analiza rachunku kosztów** eksponuje odchylenia między kosztami rzeczywistymi a budżetowymi, menedżerowie mogą być powiadamiani o pozytywnych i negatywnych tendencjach w swoich jednostkach operacyjnych. Menedżerowie mogą przechodzić do hierarchii składników kosztów lub poszczególnych składników kosztów. W ten sposób mogą uzyskać szczegółowe informacje dotyczące sposobu zaistnienia odchyleń kosztów, a następnie podejmować skuteczne działania.

Pakiet zawartości usługi **Analiza rachunku kosztów** pozwala księgowym analizować przepływy kosztów przez obiekty kosztów w całej organizacji.

Aby dowiedzieć się więcej o module Rachunek kosztów, zobacz [Rachunek kosztów — strona główna](../../../finance/cost-accounting/cost-accounting-home-page.md).

Poprzez zdefiniowanie zabezpieczeń na poziomie dostępu w module Rachunek kosztów i połączenie ich z zabezpieczeniami na poziomie wierszy w usłudze Power BI można wszystkim właścicielom obiektów kosztów udzielić dostępu do pakietu zawartości **Analiza rachunku kosztów** usługi Power BI. Wszystkie dane w wizualizacjach będą następnie filtrowane według poziomu dostępu kontrolowanego w module Rachunek kosztów. Aby dowiedzieć się więcej na temat zabezpieczeń na poziomie dostępu i zabezpieczeń na poziomie wierszy, zobacz [Konfigurowanie zabezpieczeń pakietu zawartości usług Power BI Analiza rachunku kosztów](setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Pakiet zawartości **Analiza rachunku kosztów** usługi Power BI znajduje się w bibliotece zasobów wspólnych w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).

Uważaj, aby pobrać pakiet zawartości **Analiza rachunku kosztów** mający zastosowanie do używanej wersji systemu Microsoft Dynamics 365.

> [!NOTE]
> Poprawka KB 4011327 jest wstępnie wymaganym składnikiem tego pakietu zawartości usługi Power BI. Po zalogowaniu się do usługi LCS ta poprawka KB będzie dostępna pod łączem <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki umieszczone w pakiecie zawartości usługi Power BI
Pakiet zawartości zawiera zestaw stron raportów. Każda strona zawiera zestaw wskaźników, które są wizualizowane jako wykresy, kafelki i tabele. Poniższa tabela zawiera omówienie wizualizacji dostępnych w pakiecie zawartości **Analiza rachunku kosztów** usługi Power BI.

| Strona raportu                      | Wykres                                                                                                                         | Kafelek                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Kontrola kosztów wg okresu obrachunkowego    | Koszty rzeczywisty i budżetowy wg poziomu hierarchii składników kosztów                                                                   | Koszty rzeczywisty a budżetowy                    |
|                                  | Odchylenia kosztów wg poziomu hierarchii składników kosztów                                                                               | Stawka kosztu rzeczywistego a stawka kosztu budżetowego          |
|                                  | 10 największych odchyleń budżetu w procentach wg składników kosztów                                                                          | Wartość rzeczywista a budżetowa          |
| Kontrola kosztów od początku roku     | Koszty rzeczywisty i budżetowy wg okresu roku kalendarzowego                                                                           | Koszty rzeczywisty a budżetowy                    |
|                                  | Odchylenie budżetu wg okresu roku kalendarzowego                                                                                       | Stawka kosztu rzeczywistego a stawka kosztu budżetowego          |
|                                  | 10 największych odchyleń budżetu w procentach wg składników kosztów                                                                          | Wartość rzeczywista a budżetowa          |
| Stawka kosztu wg roku obrachunkowego         | Stawka kosztu rzeczywistego wg zachowań kosztów                                                                                             | Stawka kosztu rzeczywistego a stawka kosztu budżetowego          |
|                                  | Stawka kosztu rzeczywistego, odchylenie stawki kosztu budżetowego, procent stawki kosztu budżetowego i stawka kosztu budżetowego wg poziomu hierarchii składników kosztów | Wartość rzeczywista a budżetowa          |
|                                  | Odchylenia kosztów wg poziomu hierarchii składników kosztów                                                                               |                                               |
|                                  | 10 największych odchyleń budżetu w procentach wg składników kosztów                                                                          |                                               |
| Budżet elastyczny wg okresu obrachunkowego | Koszty rzeczywisty, budżetowy i budżetu elastycznego wg poziomu hierarchii składników kosztów                                             | Wartość rzeczywista a budżetowa          |
|                                  | Odchylenia budżetu i budżetu elastycznego wg poziomu hierarchii składników kosztów                                                  | Koszty rzeczywisty a budżetu elastycznego           |
|                                  | Koszty rzeczywisty, budżetowy i zmienny wg zachowania kosztów i poziomu hierarchii składników kosztów                                  | Stawka kosztu rzeczywistego a stawka kosztu budżetu elastycznego |
| Zestawienie kosztów wg okresu obrachunkowego  | Koszt rzeczywisty wg poziomu hierarchii składników kosztów i nazwy elementu członkowskiego wymiaru obiektu kosztów                                             |                                               |
|                                  | Koszt rzeczywisty wg nazwy elementu członkowskiego wymiaru obiektu kosztów i nazwy elementu członkowskiego wymiaru składnika kosztu                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Następujące dane są używane do wypełniania stron raportów w pakiecie zawartości **Analiza rachunku kosztów** dla usługi Power BI. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

Następujące najważniejsze zagregowane miary są używane jako podstawa w pakiecie zawartości:

| Jednostka                  | Najważniejsza zagregowana miara | Źródło danych programu Dynamics 365      | Pole     | opis                                        |
|-------------------------|---------------------------|-----------------------------------|-----------|----------------------------------------------------|
| Wpisy rachunku kosztów | SUM(Kwota)               | CAMDATAAggregatedCostEntry        | Ilość    | Kwota w walucie księgi rachunku kosztów. |
| Wpisy statystyczne     | SUM(Wartość)            | CAMDATAAggregatedStatisctialEntry | Wartość |                                                    |

W poniższej tabeli przedstawiono, jak najważniejsze zagregowane miary są używane do tworzenia kilku miar obliczanych w zestawie danych pakietu zawartości.

| Pomiar                                       | Sposób obliczania miary                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Koszt rzeczywisty                                   | CALCULATE('Wpisy rachunku kosztów'\[Miara\], 'Wersje transakcji'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)            |
| Koszt budżetowy                                   | CALCULATE('Wpisy rachunku kosztów'\[Miara\], 'Wersje transakcji'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)            |
| Odchylenie kosztu budżetowego                          | \[Koszt budżetowy\] - \[Koszt rzeczywisty\]                                                                                      |
| Procent odchylenia budżetu                    | IF(\[Koszt budżetowy\] = 0, blank(), \[Odchylenie budżetu\] / \[Koszt budżetowy\])                                                |
| Wartość rzeczywista                              | CALCULATE('Wpisy statystyczne'\[FullMagnitude\], 'Wersje transakcji'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)          |
| Wartość budżetowa                              | CALCULATE(\[FullMagnitude\], 'Wersje transakcji'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)                               |
| Odchylenie statystyczne budżetu                   | \[Wartość budżetowa\] - \[Wartość rzeczywista\]                                                                            |
| Procent odchylenia statystycznego budżetu        | IF(\[Wartość budżetowa\] = 0, blank(), \[Odchylenie statystyczne budżetu\] / \[Wartość budżetowa\])                          |
| Stawka kosztu rzeczywistego                              | IF(\[Wartość rzeczywista\] = 0, BLANK(), \[Koszt rzeczywisty\] / \[Wartość rzeczywista\])                                          |
| Stawka kosztu budżetowego                              | IF(\[Wartość budżetowa\] = 0, BLANK(), \[Koszt budżetowy\] / \[Wartość budżetowa\])                                          |
| Odchylenie stawki kosztu budżetowego                     | \[Stawka kosztu budżetowego\] - \[Stawka kosztu rzeczywistego\]                                                                            |
| Procent odchylenia stawki kosztu budżetowego          | IF(\[Koszt budżetowy\] = 0, blank(), \[Odchylenie stawki kosztu budżetowego\] / \[Stawka kosztu budżetowego\])                                 |
| Stały koszt budżetowy                             | CALCULATE(\[Koszt budżetowy\], 'Wpisy rachunku kosztów'\[COSTBEHAVIOR\] = 1)                                              |
| Zmienny koszt budżetowy                          | CALCULATE(\[Koszt budżetowy\], 'Wpisy rachunku kosztów'\[COSTBEHAVIOR\] = 2)                                              |
| Stały koszt budżetu elastycznego                    | \[Stały koszt budżetowy\]                                                                                                  |
| Zmienny koszt budżetu elastycznego                 | IF(\[Wartość budżetowa\] = 0, BLANK(), (\[Zmienny koszt budżetowy\] / \[Wartość budżetowa\]) \* \[Wartość rzeczywista\])       |
| Koszt budżetu elastycznego                          | \[Stały koszt budżetu elastycznego\] + \[Zmienny koszt budżetu elastycznego\]                                                     |
| Odchylenie budżetu elastycznego                      | \[Koszt budżetu elastycznego\] - \[Koszt rzeczywisty\]                                                                             |
| Procent odchylenia budżetu elastycznego           | IF(\[Koszt budżetu elastycznego\] = 0, BLANK(), \[Odchylenie budżetu elastycznego\] / \[Koszt budżetu elastycznego\])                     |
| Stawka kosztu budżetu elastycznego                     | IF(\[Wartość rzeczywista\] = 0, BLANK(), \[Koszt budżetu elastycznego\] / \[Wartość rzeczywista\])                                 |
| Odchylenia stawki kosztu budżetu elastycznego            | \[Stawka kosztu budżetu elastycznego\] - \[Stawka kosztu rzeczywistego\]                                                                   |
| Procent odchylenia stawki kosztu budżetu elastycznego | IF(\[Stawka kosztu budżetu elastycznego\] = 0, BLANK(), \[Odchylenia stawki kosztu budżetu elastycznego\] / \[Stawka kosztu budżetu elastycznego\]) |

Następujące najważniejsze wymiary są używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i zapewnienia lepszego wglądu analitycznego.

| Jednostka                             | Przykłady atrybutów                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Księgi rachunku kosztów            | Księga rachunku kosztów                                                                                               |
| Jednostki kontroli kosztów                 | Nazwa jednostki kontroli kosztów                                                                                               |
| Wymiary składników kosztów            | Nazwa wymiaru składnika kosztu, Nazwa elementu członkowskiego wymiaru składnika kosztu, Opis elementu członkowskiego wymiaru składnika kosztu          |
| Wymiary obiektów kosztów             | Nazwa wymiaru obiektu kosztów, Nazwa elementu członkowskiego wymiaru obiektu kosztów, Opis elementu członkowskiego wymiaru obiektu kosztów              |
| Wymiary statystyczne             | Nazwa wymiaru statystycznego, Nazwa elementu członkowskiego wymiaru statystycznego, Opis elementu członkowskiego wymiaru statystycznego              |
| Hierarchie wymiarów obiektów kosztów  | Nazwa hierarchii wymiarów obiektów kosztów, Poziom hierarchii wymiarów obiektów kosztów, Drzewo hierarchii wymiarów obiektów kosztów    |
| Hierarchie wymiarów składników kosztów | Nazwa hierarchii wymiarów składników kosztów, Poziom hierarchii wymiarów składników kosztów, Drzewo hierarchii wymiarów składników kosztów |
| Hierarchie wymiarów statystycznych  | Nazwa hierarchii wymiarów statystycznych, Poziom hierarchii wymiarów statystycznych, Drzewo hierarchii wymiarów statystycznych    |
| Wersje transakcji               | Nazwa wersji                                                                                                         |
| Kalendarze obrachunkowe                   | Kalendarz, Opis kalendarza                                                                                       |
| Lata obrachunkowe                       | Rok kalendarzowy                                                                                                        |
| Okresy obrachunkowe                     | Okres roku kalendarzowego                                                                                                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]