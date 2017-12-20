---
title: "Zawartość usługi Power BI dla kierownika praktyk"
description: "W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI dla kierownika praktyk. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 836997f9f5b146ff48252c3f06153791ec1aabed
ms.contentlocale: pl-pl
ms.lasthandoff: 12/01/2017

---

# <a name="practice-manager-power-bi-content"></a>Zawartość usługi Power BI dla kierownika praktyk

[!include[banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Kierownik praktyk**. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Zawartości usługi Power BI **Kierownik praktyk** została utworzona dla kierowników praktyk i kierowników projektów. Zawiera podstawowe wskaźniki, które odnoszą się do projektów, nad którymi organizacja pracuje. Pulpit nawigacyjny zawiera przegląd projektów i powiązanych odbiorców. Filtr poziomu raportu może służyć do raportowania dla określonych firm. Ten pakiet zawartości usługi Power BI pobiera dane ze zagregowanych miar rozliczania projektu.

Pakiet zawartości Power BI **Kierownik praktyk** zawiera pięć stron raportu: jedną stronę omówienia i cztery strony zawierające szczegółowe informacje o kosztach projektu, przychodach, zarządzaniu wartością wypracowaną i metrykach godzinowych, które są podzielone według różnych wymiarów.

Wszystkie kwoty w zawartości są wyświetlane w walucie systemu. Można ustawiać walutę systemową na stronie **Parametry systemowe**.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Zawartość usługi Power BI **Kierownik praktyk** jest wyświetlana w obszarze roboczym **Zarządzanie projektem**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty umieszczone w pakiecie zawartości usługi Power BI

W poniższej tabeli przedstawiono szczegóły dotyczące mierników, które znajdują się na każdej stronie raportu w pakiecie zawartości dla usługi Power BI **Kierownik praktyk** .

| Strona raportu       | Metryki |
|-------------------|---------|
| Przegląd projektu | <ul><li>Utworzone projekty</li><li>Oszacowane projekty</li><li>Projekty w toku</li><li>Liczba projektów według etapów</li><li>Liczba projektów według miast</li><li>Rzeczywisty przychód według odbiorców</li><li>Budżetowa marża brutto według projektów</li><li>Omówienie zarządzania uzyskanymi wartościami</li></ul> |
| Koszt              | <ul><li>Koszt rzeczywisty a budżetowy według miesięcy</li><li>Koszt rzeczywisty a budżetowy według lat</li><li>Koszt rzeczywisty a budżetowy według kategorii</li><li>Rzeczywisty koszt według typów transakcji</li></ul> |
| Przychód           | <ul><li>Rzeczywisty przychód według miesięcy</li><li>Rzeczywisty przychód według kodów pocztowych</li><li>Przychód rzeczywisty a budżetowy według kategorii</li><li>Rzeczywisty przychód według branż odbiorców</li></ul> |
| EVM               | Wskaźnik bilansu kosztów i zgodności z harmonogramem według projektów |
| Godziny             | <ul><li>Rzeczywiste wykorzystanie do zafakturowania w godzinach w porównaniu z rzeczywistym obciążeniem do zafakturowania w godzinach w porównaniu z godzinami w budżecie</li><li>Rzeczywiste wykorzystanie do zafakturowania w godzinach w porównaniu z rzeczywistym obciążeniem do zafakturowania w godzinach według projektów</li><li>Rzeczywiste wykorzystanie do zafakturowania w godzinach w porównaniu z rzeczywistym obciążeniem do zafakturowania w godzinach według zasobów</li><li>Rzeczywisty współczynnik godzin do zafakturowania według projektów</li><li>Rzeczywisty współczynnik godzin do zafakturowania według zasobów</li></ul> |

Wykresy i kafelki we wszystkich tych raportach można filtrować i przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Można także użyć funkcji eksportu danych źródłowych do wyeksportowania danych podsumowanych w wizualizacji.

## <a name="extending-the-power-bi-content"></a>Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI
Za pomocą pakietów zawartości dostępnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) można dostarczać zaawansowane funkcje analityczne osobom, które się nie logują w programie Microsoft Dynamics 365. Te pakiety zawartości można modyfikować, tak aby zawierały inne raporty lub wizualizacje, a następnie publikować je w swojej dzierżawie usługi Power BI.com na potrzeby wykonywania analiz. 

Pakiet zawartości usługi Power BI **Kierownik praktyk** znajduje się w bibliotece zasobów wspólnych w usłudze LCS. Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md). Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

Uważaj, aby pobrać pakiet zawartości **Kierownik praktyk** mający zastosowanie do używanej wersji systemu Dynamics 365.

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

Następujące dane są używane do wypełniania stron raportów w pakiecie zawartości **Kierownik praktyk** dla usługi Power BI. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

Poniżej opisano zagregowane miary, które są używane w każdej jednostce.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Jednostka: ProjectAccountingCube_ActualHourUtilization
**Źródło danych**: ProjEmplTrans

| Najważniejsza zagregowana miara      | Pole                              | opis | 
|--------------------------------|------------------------------------|-------------|
| Rzeczywiste wykorzystanie do zafakturowania — godziny | Sum(ActualUtilizationBillableRate) | Rzeczywiste wykorzystanie do zafakturowania w godzinach łącznie. |
| Rzeczywiste obciążenie do zafakturowania — godziny   | Sum(ActualBurdenBillableRate)      | Wskaźnik rzeczywistego obciążenia łącznie. |

### <a name="entity-projectaccountingcubeactuals"></a>Jednostka: ProjectAccountingCube_Actuals
**Źródło danych**: ProjTransPosting

| Najważniejsza zagregowana miara | Pole              | opis | 
|---------------------------|--------------------|-------------|
| Rzeczywisty przychód            | Sum(ActualRevenue) | Przychód zaksięgowany dla wszystkich transakcji łącznie. |   
| Koszt rzeczywisty               | Sum(ActualCost)    | Koszt zaksięgowany dla wszystkich typów transakcji łącznie. |

### <a name="entity-projectaccountingcubecustomer"></a>Jednostka: ProjectAccountingCube_Customer
**Źródło danych**: CustTable

| Najważniejsza zagregowana miara | Pole                                            | opis | 
|---------------------------|--------------------------------------------------|-------------|
| Liczba projektów        | COUNTA(ProjectAccountingCube_Projects[PROJECTS]) | Liczba dostępnych projektów. |


### <a name="entity-projectaccountingcubeforecasts"></a>Jednostka: ProjectAccountingCube_Forecasts
**Źródło danych**: ProjTransBudget

| Najważniejsza zagregowana miara | Pole                  | opis | 
|---------------------------|------------------------|-------------|
| Koszt budżetowy               | Sum(BudgetCost)        | Koszt prognozowany dla wszystkich typów transakcji łącznie. |
| Przychód budżetowy            | Sum(BudgetRevenue)     | Prognozowany przychód naliczony/zafakturowany łącznie.  |
| Budżetowa marża brutto       | Sum(BudgetGrossMargin) | Różnica między sumą prognozowanego przychodu łącznie a sumą kosztów prognozowanych łącznie. |

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Jednostka: ProjectAccountingCube_ProjectPlanCostsView
**Źródło danych**: Projekt

| Najważniejsza zagregowana miara | Pole                    | opis | 
|---------------------------|--------------------------|-------------|
| Planowany koszt              | Sum(SumOfTotalCostPrice) | Całkowity koszt własny w oszacowaniach dla wszystkich typów transakcji projektu zawierających planowane zadania. |

### <a name="entity-projectaccountingcubeprojects"></a>Jednostka: ProjectAccountingCube_Projects
**Źródło danych**: Projekt

| Najważniejsza zagregowana miara    | Pole | opis | 
|------------------------------|-------|-------------|
| Wskaźnik bilansu kosztów       | ProjectAccountingCube_Projects[wartość uzyskana] / ProjectAccountingCube_Projects [Suma kosztów rzeczywistych wykonanych zadań] | Obliczenie łącznej wartości wypracowanej podzielonej przez łączny koszt rzeczywisty. |
| Wskaźnik zgodności z harmonogramem   | ProjectAccountingCube_Projects[wartość uzyskana] / ProjectAccountingCube_Projects [Suma kosztów planowanych wykonanych zadań] | Obliczenie łącznej wartości wypracowanej podzielonej przez łączny koszt planowany. |
| Procent ukończonej pracy | Procent wykonanej pracy = ProjectAccountingCube_Projects [suma kosztów rzeczywistych wykonanych zadań] / (ProjectAccountingCube_Projects [suma kosztów rzeczywistych wykonanych zadań] + ProjectAccountingCube_Projects [suma kosztów planowanych projektu] – ProjectAccountingCube_Projects [suma kosztów planowanych wykonanych zadań]) | Całkowity procent ukończenia pracy w zależności od sumy kosztów rzeczywistych wykonanych zadań oraz planowanego kosztu projektu. |
| Wskaźnik rzeczywistych godzin do zafakturowania  | ProjectAccountingCube_Projects [rzeczywiste wykorzystanie do zafakturowania w godzinach łącznie dla projektu] / (ProjectAccountingCube_Projects [rzeczywiste wykorzystanie do zafakturowania w godzinach łącznie dla projektu] +ProjectAccountingCube_Projects[rzeczywiste obciążenie do zafakturowania w godzinach łącznie dla projektu]) | Rzeczywista suma godzin do zafakturowania na podstawie godzin wykorzystanych (produktywnych) i obciążenia (nieproduktywnych). |
| Uzyskana wartość                 | ProjectAccountingCube_Projects[suma kosztów planowanych projektu] * ProjectAccountingCube_Projects [Procent wykonanej pracy] | Całkowity planowany koszt pomnożony przez procent wykonanej pracy. |

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Jednostka: ProjectAccountingCube_TotalEstimatedCosts 
**Źródło danych**: ProjTable

| Najważniejsza zagregowana miara       | Pole               | opis | 
|---------------------------------|---------------------|-------------|
| Planowany koszt ukończonego działania | Sum(TotalCostPrice) | Całkowity koszt własny w oszacowaniach dla wszystkich typów transakcji projektu zawierających ukończone zadania. |

