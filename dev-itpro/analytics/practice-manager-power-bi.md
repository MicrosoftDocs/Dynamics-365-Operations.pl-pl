---
title: "Zawartość usługi Power BI dla kierownika praktyk"
description: "W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI dla kierownika praktyk. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach używanych do zbudowania pakietu."
author: knelson
manager: AnnBe
ms.date: 04/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer/IT Pro
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.dyn365.intro: 2017/04/27
ms.dyn365.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0f2a1a9df8e5036c60b74b8a710e606b0b1e312a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="practice-manager-power-bi-content"></a>Zawartość usługi Power BI dla kierownika praktyk

[!include[banner](../includes/banner.md)]


W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Kierownik praktyk**. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Zawartości usługi Power BI **Kierownik praktyk** została utworzona dla kierowników praktyk i kierowników projektów. Zawiera podstawowe wskaźniki, które odnoszą się do projektów, nad którymi organizacja pracuje. Pulpit nawigacyjny zawiera przegląd projektów i powiązanych odbiorców. Filtr poziomu raportu może służyć do raportowania dla określonych firm. Ta zawartość Power BI pobiera dane z zagregowanych miar księgowania projektu dla Microsoft Dynamics 365 for Operations.

Zawartość Power BI **Kierownik praktyk** zawiera pięć stron raportu: jedna strona omówienia i cztery strony zawierające szczegółowe informacje o kosztach projektu, przychodach, zarządzaniu uzyskanymi wartościami i metrykach godzin, które są podzielone i wymieszane wg różnych wymiarów.

Wszystkie kwoty w zawartości są wyświetlane w walucie systemu. Można ustawiać walutę systemową na stronie **Parametry systemowe**.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI

Pakiet zawartości usługi Power BI **Kierownik praktyk** znajduje się w bibliotece zasobów wspólnych w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i łączeniu go z danymi usługi Dynamics 365 for Operations, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md).

Aby obejrzeć demonstrację przedstawiającą sposób implementacji zawartości Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty umieszczone w pakiecie zawartości usługi Power BI

W poniższej tabeli przedstawiono szczegóły dotyczące mierników, które znajdują się na każdej stronie raportu w pakiecie zawartości dla usługi Power BI **Kierownik praktyk** .

| Strona raportu                                          | Metryki               |
|------------------------------------------------------|-----------------------------------------------|
| Pulpit nawigacyjny  | Utworzone projekty<br>Oszacowane projekty<br>Projekty w toku<br>Liczba projektów według etapów<br>Liczba projektów według miast<br>Rzeczywisty przychód według odbiorców<br>Budżetowa marża brutto według projektów<br>Omówienie zarządzania uzyskanymi wartościami |
| Koszt                                                 | Koszt rzeczywisty a budżetowy według miesięcy<br>Koszt rzeczywisty a budżetowy według lat<br>Koszt rzeczywisty a budżetowy według kategorii<br>Rzeczywisty koszt według typów transakcji       |
| Przychód                                              | Rzeczywisty przychód według miesięcy<br>Rzeczywisty przychód według kodów pocztowych<br>Przychód rzeczywisty a budżetowy według kategorii<br>Rzeczywisty przychód według branż odbiorców        |
| EVM                                                  | Wskaźnik bilansu kosztów i zgodności z harmonogramem według projektów                 |
| Godziny                                                | Rzeczywiste wykorzystanie do zafakturowania w godzinach w porównaniu z rzeczywistym obciążeniem do zafakturowania w godzinach w porównaniu z godzinami w budżecie<br>Rzeczywiste wykorzystanie do zafakturowania w godzinach w porównaniu z rzeczywistym obciążeniem do zafakturowania w godzinach według projektów<br>Rzeczywiste wykorzystanie do zafakturowania w godzinach w porównaniu z rzeczywistym obciążeniem do zafakturowania w godzinach według zasobów<br>Rzeczywisty współczynnik godzin do zafakturowania według projektów<br>Rzeczywisty współczynnik godzin do zafakturowania według zasobów |

Wykresy i kafelki we wszystkich tych raportach można filtrować i przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Można także użyć funkcji eksportu danych źródłowych do wyeksportowania danych podsumowanych w wizualizacji.

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

Dane programu Dynamics 365 for Operations są używane do wypełniania stron raportów w pakiecie zawartości usługi Power BI **Kierownik praktyk**. Te dane są przedstawiane jako zagregowane miary umieszczane w magazynie jednostek, który jest bazą danych programu Microsoft SQL zoptymalizowaną pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Omówienie integracji usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

Poniżej opisano zagregowane wskaźniki, które są używane w każdej jednostce.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Jednostka: ProjectAccountingCube_ActualHourUtilization
**Źródło danych**: ProjEmplTrans

| Najważniejsza zagregowana miara                | Pole                                | opis                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualBillableUtilizedHours              | Sum(ActualUtilizationBillableRate)   | Rzeczywiste wykorzystanie do zafakturowania w godzinach łącznie |
| ActualBillableBurdenHours                | Sum(ActualBurdenBillableRate)        | Wskaźnik rzeczywistego obciążenia łącznie             |

### <a name="entity-projectaccountingcubeactuals"></a>Jednostka: ProjectAccountingCube_Actuals
**Źródło danych**: ProjTransPosting

| Najważniejsza zagregowana miara                | Pole                                | opis                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualRevenue                            |     Sum(ActualRevenue)               |  Przychód zaksięgowany dla wszystkich transakcji łącznie |   
| ActualCost   |                             Sum(ActualCost)           |    Koszt zaksięgowany dla wszystkich typów transakcji łącznie    |

### <a name="entity-projectaccountingcubecustomer"></a>Jednostka: ProjectAccountingCube_Customer
**Źródło danych**: CustTable

| Najważniejsza zagregowana miara                | Pole                                | opis                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    Liczba projektów        |   COUNTA(ProjectAccountingCube_Projects[PROJECTS])       |         Liczba dostępnych projektów    |


### <a name="entity-projectaccountingcubeforecasts"></a>Jednostka: ProjectAccountingCube_Forecasts
**Źródło danych**: ProjTransBudget

| Najważniejsza zagregowana miara                | Pole                                | opis                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    BudgetCost    |       Sum(BudgetCost)  |       Koszt prognozowany dla wszystkich typów transakcji łącznie     |
|     BudgetRevenue    |         Sum(BudgetRevenue)    |    Prognozowany przychód naliczony/zafakturowany łącznie         |
|BudgetGrossMargin | Sum(BudgetGrossMargin) |Różnica między sumą prognozowanego przychodu łącznie i sumą kosztów prognozowanych łącznie

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Jednostka: ProjectAccountingCube_ProjectPlanCostsView
**Źródło danych**: projekt

| Najważniejsza zagregowana miara                | Pole                                | opis                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|      PlannedCost      |        Sum(SumOfTotalCostPrice)   | Całkowity koszt własny w oszacowaniach dla wszystkich typów transakcji projektu z planowanymi zadaniami |

### <a name="entity-projectaccountingcubeprojects"></a>Jednostka: ProjectAccountingCube_Projects
**Źródło danych**: projekt

| Najważniejsza zagregowana miara                | Pole                                | opis                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|   Wskaźnik bilansu kosztów  |ProjectAccountingCube_Projects[wartość uzyskana] / ProjectAccountingCube_Projects [Suma kosztów rzeczywistych wykonanych zadań] |     Obliczenie łącznej wartości uzyskanej podzielonej przez łączny koszt rzeczywisty|
|  Wskaźnik zgodności z harmonogramem |ProjectAccountingCube_Projects[wartość uzyskana] / ProjectAccountingCube_Projects [Suma kosztów planowanych wykonanych zadań]|Obliczenie łącznej wartości uzyskanej podzielonej przez łączny koszt planowany |
|Procent ukończonej pracy |Procent wykonanej pracy = ProjectAccountingCube_Projects [suma kosztów rzeczywistych wykonanych zadań] / (ProjectAccountingCube_Projects [suma kosztów rzeczywistych wykonanych zadań] + ProjectAccountingCube_Projects [suma kosztów planowanych projektu] – ProjectAccountingCube_Projects [suma kosztów planowanych wykonanych zadań])|Całkowity procent ukończenia pracy w zależności od sumy kosztów rzeczywistych wykonanego zadania oraz planowanych kosztów projektu|
|Rzeczywisty współczynnik godzin do zafakturowania dla projektu|ProjectAccountingCube_Projects [rzeczywiste wykorzystanie do zafakturowania w godzinach łącznie dla projektu] / (ProjectAccountingCube_Projects [rzeczywiste wykorzystanie do zafakturowania w godzinach łącznie dla projektu] +ProjectAccountingCube_Projects[rzeczywiste obciążenie do zafakturowania w godzinach łącznie dla projektu])|Suma rzeczywistych godzin do zafakturowania na podstawie wykorzystania + obciążenia|
|Uzyskana wartość|ProjectAccountingCube_Projects[suma kosztów planowanych projektu] * ProjectAccountingCube_Projects [Procent wykonanej pracy]|Całkowity planowany koszt należy pomnożyć przez procent wykonanej pracy|

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Jednostka: ProjectAccountingCube_TotalEstimatedCosts 
**Źródło danych**: ProjTable

| Najważniejsza zagregowana miara                | Pole                                | opis                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| CompletedActivityPlannedCost  |  Sum(TotalCostPrice)  |   Całkowity koszt własny w oszacowaniach dla wszystkich typów transakcji projektu z wykonanymi zadaniami|

## <a name="additional-resources"></a>Dodatkowe zasoby

Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

- [Jednostki danych](/dynamics365/operations/dev-itpro/data-entities/data-entities)
- [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Konfigurowanie integracji usługi Power BI dla obszarów roboczych](configure-power-bi-integration.md)

