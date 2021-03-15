---
title: Pakiet zawartości Kierownik praktyk w usłudze Power BI
description: W tym temacie opisano, co się znajduje w pakiecie zawartości Kierownik praktyk dla usługi Power BI.
author: KimANelson
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ProjManagementWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.assetid: ''
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: f01109b360b23adf84673e84e6240f8f4431340d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092464"
---
# <a name="practice-manager-power-bi-content"></a>Pakiet zawartości Kierownik praktyk w usłudze Power BI

[!include [banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości **Kierownik praktyk** dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Zawartości **Kierownik praktyk** usługi Power BI została utworzona dla kierowników praktyk i kierowników projektów. Zawiera podstawowe wskaźniki, które odnoszą się do projektów, nad którymi organizacja pracuje. Pulpit nawigacyjny zawiera przegląd projektów i powiązanych odbiorców. Filtr poziomu raportu może służyć do raportowania dla określonych firm. Ten pakiet zawartości usługi Power BI pobiera dane ze zagregowanych miar rozliczania projektu.

Pakiet zawartości **Kierownik praktyk** usługi Power BI zawiera pięć stron raportu: jedną stronę omówienia i cztery strony zawierające szczegółowe informacje o kosztach projektu, przychodach, zarządzaniu wartością wypracowaną i metrykach godzinowych, które są podzielone według różnych wymiarów.

Wszystkie kwoty w zawartości są wyświetlane w walucie systemu. Można ustawiać walutę systemową na stronie **Parametry systemowe**.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI

Pakiet zawartości **Kierownik praktyk** usługi Power BI jest wyświetlana w obszarze roboczym **Zarządzanie projektem**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty dostępne w pakiecie zawartości dla usługi Power BI

W poniższej tabeli przedstawiono szczegóły dotyczące mierników, które znajdują się na każdej stronie raportu w pakiecie zawartości **Kierownik praktyk** usługi Power BI.

| Strona raportu       | Metryki |
|-------------------|---------|
| Przegląd projektu | <ul><li>Utworzone projekty</li><li>Oszacowane projekty</li><li>Projekty w toku</li><li>Rzeczywisty przychód według odbiorców</li><li>Budżetowa marża brutto według projektów</li><li>Omówienie zarządzania uzyskanymi wartościami</li></ul> |
| Koszt              | <ul><li>Koszt rzeczywisty a budżetowy według miesięcy</li><li>Koszt rzeczywisty a budżetowy według lat</li><li>Koszt rzeczywisty a budżetowy według kategorii</li><li>Rzeczywisty koszt według typów transakcji</li></ul> |
| Przychód           | <ul><li>Rzeczywisty przychód według miesięcy</li><li>Rzeczywisty przychód według kodów pocztowych</li><li>Przychód rzeczywisty a budżetowy według kategorii</li><li>Rzeczywisty przychód według branż odbiorców</li></ul> |
| EVM               | Wskaźnik bilansu kosztów i zgodności z harmonogramem według projektów |
| Godziny             | <ul><li>Rzeczywiste wykorzystanie do zafakturowania w godzinach w porównaniu z rzeczywistym obciążeniem do zafakturowania w godzinach w porównaniu z godzinami w budżecie</li><li>Rzeczywiste wykorzystanie do zafakturowania w godzinach w porównaniu z rzeczywistym obciążeniem do zafakturowania w godzinach według projektów</li><li>Rzeczywiste wykorzystanie do zafakturowania w godzinach w porównaniu z rzeczywistym obciążeniem do zafakturowania w godzinach według zasobów</li><li>Rzeczywisty współczynnik godzin do zafakturowania według projektów</li><li>Rzeczywisty współczynnik godzin do zafakturowania według zasobów</li></ul> |

Wykresy i kafelki we wszystkich tych raportach można filtrować i przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w usłudze Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Można także użyć funkcji eksportu danych źródłowych do wyeksportowania danych podsumowanych w wizualizacji.

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

Następujące dane są używane do wypełniania stron raportów w pakiecie zawartości **Kierownik praktyk** usługi Power BI. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

Poniżej opisano zagregowane miary, które są używane w każdej jednostce.

### <a name="entity-projectaccountingcube_actualhourutilization"></a>Jednostka: ProjectAccountingCube\_ActualHourUtilization
**Źródło danych**: ProjEmplTrans

| Najważniejsza zagregowana miara      | Pole                              | opis |
|--------------------------------|------------------------------------|-------------|
| Rzeczywiste wykorzystanie do zafakturowania — godziny | Sum(ActualUtilizationBillableRate) | Rzeczywiste wykorzystanie do zafakturowania w godzinach łącznie. |
| Rzeczywiste obciążenie do zafakturowania — godziny   | Sum(ActualBurdenBillableRate)      | Wskaźnik rzeczywistego obciążenia łącznie. |

### <a name="entity-projectaccountingcube_actuals"></a>Jednostka: ProjectAccountingCube\_Actuals
**Źródło danych**: ProjTransPosting

| Najważniejsza zagregowana miara | Pole              | opis |
|---------------------------|--------------------|-------------|
| Rzeczywisty przychód            | Sum(ActualRevenue) | Przychód zaksięgowany dla wszystkich transakcji łącznie. |
| Koszt rzeczywisty               | Sum(ActualCost)    | Koszt zaksięgowany dla wszystkich typów transakcji łącznie. |

### <a name="entity-projectaccountingcube_customer"></a>Jednostka: ProjectAccountingCube\_Customer
**Źródło danych**: CustTable

| Najważniejsza zagregowana miara | Pole                                             | opis |
|---------------------------|---------------------------------------------------|-------------|
| Liczba projektów        | COUNTA(ProjectAccountingCube\_Projects\[PROJECTS\]) | Liczba dostępnych projektów. |

### <a name="entity-projectaccountingcube_forecasts"></a>Jednostka: ProjectAccountingCube\_Forecasts
**Źródło danych**: ProjTransBudget

| Najważniejsza zagregowana miara | Pole                  | opis |
|---------------------------|------------------------|-------------|
| Koszt budżetowy               | Sum(BudgetCost)        | Koszt prognozowany dla wszystkich typów transakcji łącznie. |
| Przychód budżetowy            | Sum(BudgetRevenue)     | Prognozowany przychód naliczony/zafakturowany łącznie. |
| Budżetowa marża brutto       | Sum(BudgetGrossMargin) | Różnica między sumą prognozowanego przychodu łącznie a sumą kosztów prognozowanych łącznie. |

### <a name="entity-projectaccountingcube_projectplancostsview"></a>Jednostka: ProjectAccountingCube\_ProjectPlanCostsView
**Źródło danych**: Projekt

| Najważniejsza zagregowana miara | Pole                    | opis |
|---------------------------|--------------------------|-------------|
| Planowany koszt              | Sum(SumOfTotalCostPrice) | Całkowity koszt własny w oszacowaniach dla wszystkich typów transakcji projektu zawierających planowane zadania. |

### <a name="entity-projectaccountingcube_projects"></a>Jednostka: ProjectAccountingCube\_Projects
**Źródło danych**: Projekt

| Najważniejsza zagregowana miara    | Pole | opis |
|------------------------------|-------|-------------|
| Wskaźnik bilansu kosztów       | ProjectAccountingCube\_Projects\[wartość uzyskana\] ÷ ProjectAccountingCube\_Projects\[suma kosztów rzeczywistych wykonanych zadań\] | Obliczenie łącznej wartości wypracowanej podzielonej przez łączny koszt rzeczywisty. |
| Wskaźnik zgodności z harmonogramem   | ProjectAccountingCube\_Projects\[wartość uzyskana\] ÷ ProjectAccountingCube\_Projects\[suma kosztów planowanych wykonanych zadań\] | Obliczenie łącznej wartości wypracowanej podzielonej przez łączny koszt planowany. |
| Procent ukończonej pracy | Procent wykonanej pracy = ProjectAccountingCube\_Projects\[suma kosztów rzeczywistych wykonanych zadań\] ÷ (ProjectAccountingCube\_Projects\[suma kosztów rzeczywistych wykonanych zadań\] + ProjectAccountingCube\_Projects\[suma kosztów planowanych wykonanych zadań\] – ProjectAccountingCube\_Projects\[suma kosztów planowanych wykonanych zadań\]) | Całkowity procent ukończenia pracy w zależności od sumy kosztów rzeczywistych wykonanych zadań oraz planowanego kosztu projektu. |
| Wskaźnik rzeczywistych godzin do zafakturowania  | ProjectAccountingCube\_Projects\[rzeczywiste wykorzystanie do zafakturowania w godzinach łącznie dla projektu\] ÷ (ProjectAccountingCube\_Projects\[rzeczywiste wykorzystanie do zafakturowania w godzinach łącznie dla projektu\] + ProjectAccountingCube\_Projects\[rzeczywiste obciążenie do zafakturowania w godzinach łącznie dla projektu\]) | Rzeczywista suma godzin do zafakturowania na podstawie godzin wykorzystanych (produktywnych) i obciążenia (nieproduktywnych). |
| Uzyskana wartość                 | ProjectAccountingCube\_Projects\[suma kosztów planowanych projektu\] × ProjectAccountingCube\_Projects\[procent wykonanej pracy\] | Całkowity planowany koszt pomnożony przez procent wykonanej pracy. |

### <a name="entity-projectaccountingcube_totalestimatedcosts"></a>Jednostka: ProjectAccountingCube\_TotalEstimatedCosts 
**Źródło danych**: ProjTable

| Najważniejsza zagregowana miara       | Pole               | opis |
|---------------------------------|---------------------|-------------|
| Planowany koszt ukończonego działania | Sum(TotalCostPrice) | Całkowity koszt własny w oszacowaniach dla wszystkich typów transakcji projektu zawierających ukończone zadania. |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]