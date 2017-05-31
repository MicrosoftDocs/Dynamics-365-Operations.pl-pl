---
title: "Pakiet zawartości usługi Power BI Wyniki sprzedaży i rentowności"
description: "W tym temacie opisano, co się znajduje w pakiecie zawartości Dynamics 365 for Operations — Wyniki sprzedaży i rentowności dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 357f7071d801b13518c83170f8d0e7946dd9dede
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Pakiet zawartości usługi Power BI Wyniki sprzedaży i rentowności

[!include[banner](../includes/banner.md)]


W tym temacie opisano, co się znajduje w pakiecie zawartości Dynamics 365 for Operations — Wyniki sprzedaży i rentowności dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

<a name="overview"></a>Przegląd
--------

Ten pakiet zawartości został utworzony dla menedżerów sprzedaży w celu umożliwienia monitorowania kluczowych wskaźników, jakimi są przychód, zysk brutto i marża zysku. Wykorzystuje dane transakcyjne sprzedaży z programu Dynamics 365 for Operations i przedstawia zarówno zagregowany widok wyników sprzedaży w całej firmie, jak i podział wyników sprzedaży na odbiorców i produkty. Wyróżniając zmiany we wzroście przychodów i zysków w czasie, raporty mogą służyć do ostrzegania menedżerów o pozytywnych i negatywnych trendach dotyczących poszczególnych odbiorców i produktów. Menedżerowie kategorii i kierownicy regionalni docenią wykresy porównujące przychody i rentowności różnych kategorii produktów i grup odbiorców, co pozwala identyfikować maruderów i liderów. Kompleksowy raport, który na wykresie zestawia przychody z poszczególnych odbiorców względem marży zysku, jest dla opiekunów klientów wiarygodną bazą, w oparciu o którą można dostosowywać działania sprzedażowe i marketingowe do profili konkretnych odbiorców. Pakiet zawartości Wyniki sprzedaży i rentowności umożliwia menedżerom sprzedaży analizowanie wyników sprzedaży według następujących kryteriów:

-   Przychody od początku roku (według grup odbiorców i indywidualnych odbiorców, kategorii sprzedaży, poszczególnych produktów i regionów geograficznych)
-   Zmiana przychodu rok do roku (według regionów odbiorców i kategorii sprzedaży)

Rentowność może być analizowana według następujących kryteriów:

-   Zysk brutto i marża zysku (według grup odbiorców i kategorii sprzedaży produktów)
-   Zmiana zysku brutto rok do roku
-   Rentowność odbiorców (przychody względem marży brutto)

## <a name="accessing-the-content-pack"></a>Przechodzenie do pakietu zawartości
Pakiet zawartości usługi Power BI Wyniki sprzedaży i rentowności jest publikowany jako składnik implementacyjny w usłudze Lifecycle Services (LCS) i można go uruchomić z programu Dynamics 365 for Operations. Aby uzyskać więcej informacji dotyczących sposobu uzyskiwania dostępu i uruchamianie raportów usługi Power BI, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md).
**Uwaga:** Poprawka KB 4011327 jest wstępnie wymaganym składnikiem tego pakietu zawartości usługi Power BI. Po zalogowaniu się w usłudze Lifecycle Services można uzyskać dostęp do tej poprawki KB tutaj: <a href="https://fix.lcs.dynamics.com/issue/results/?q=kb4011327">https://fix.lcs.dynamics.com/issue/results/?q=kb4011327</a>.

## <a name="metrics-included-in-the-content-pack"></a>Wskaźniki dostępne w pakiecie zawartości
Pakiet zawartości obejmuje raport zawierający zestaw wskaźników wizualizowanych jako wykresy, kafelki i tabele. Następująca tabela zawiera przegląd wizualizacji dostępnych w pakiecie zawartości.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Strona raportu**        | **Wykresy**                                 | **Kafelki**                                               |
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
Dane programu Dynamics 365 for Operations są używane do wypełniania raportu w pakiecie zawartości Wyniki sprzedaży i rentowności. Jest to przedstawiane jako zagregowane miary umieszczane w magazynie jednostek, który jest bazą danych programu Microsoft SQL zoptymalizowaną pod kątem analiz. Więcej na ten temat przeczytasz we wpisie na blogu [Integracja usługi Power BI z magazynem jednostek w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Zagregowane miary w tym pakiecie zawartości są podzbiorem zagregowanych miar, które były dostępne w module Sprzedaż w systemach Dynamics AX 2012 i AX 2012 R3. Aby zagregowane miary modułu można było umieścić w magazynie jednostek, trzeba ustawić te miary jako wdrażalne. Aby uzyskać więcej informacji, zobacz procedurę umieszczania zagregowanych miar w magazynie jednostek we wpisie na blogu [Integracja usługi Power BI z magazynem jednostek w systemie Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Następujące najważniejsze zagregowane miary jednostki Wiersze faktury są używane jako podstawa w pakiecie zawartości:

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Jednostka**    | **Najważniejsze zagregowane miary**               | **Źródło danych programu Dynamics 365 for Operations** | **Pole**                                    | **Opis**                          |
| Wiersze faktury | Przychód                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Kwota w walucie rozliczeniowej            |
|               | Koszt sprzedanych towarów                           | InventTrans                                     | SUM(CostAmountPosted + CostAmountAdjustment) | Kwota kosztu + korekta                 |
|               | Kwota wiersza prowizji — waluta rozliczeniowa | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Kwota wiersza prowizji w walucie rozliczeniowej |

W poniższej tabeli przedstawiono najważniejsze zagregowane miary jednostki Wiersze faktury używane do tworzenia kilku miar obliczanych w zestawie danych pakietu zawartości.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Miara**       | **Sposób obliczenia**                                                                                |
| Zysk brutto      | SUM(Przychód – KWS – Prowizja – Podatek (uwzględniony w kwocie wiersza faktury dla odbiorcy))          |
| Marża brutto      | SUM(Zysk brutto / (Przychód – Podatek (uwzględniony w kwocie wiersza faktury dla odbiorcy)))             |
| Przychód w ubiegłym roku | Przychód w ubiegłym roku = CALCULATE(SUM('Wiersze faktury'\[Przychód\]), SAMEPERIODLASTYEAR(Daty\[Data\]) |

Następujące najważniejsze wymiary w module **Sprzedaż** są używane jako filtry do dzielenia zagregowanych miar w celu uzyskania większej szczegółowości i lepszego wglądu analitycznego.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Jednostka**       | **Przykłady atrybutów**                           |
| Odbiorcy        | Grupy odbiorców, Regiony odbiorców, Adres, Branża |
| Produkty         | Numer produktu, Nazwa produktu, Nazwa grupy pozycji       |
| Kategorie sprzedaży | Nazwy kategorii sprzedaży                                 |
| Firmy   | Nazwy firm                                   |
| Daty            | Daty                                                |

Domyślnie pakiet zawartości wyświetla dane bieżącego roku kalendarzowego, ale można otworzyć sekcję filtrów raportu i zmienić wartość filtra dat. Można również zmienić wartość filtra firm.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](..\data-entities\data-entities.md)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](configure-power-bi-integration.md)





