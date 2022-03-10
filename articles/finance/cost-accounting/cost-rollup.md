---
title: Zasady akumulacji kosztów i obliczanie narzutu
description: W tym temacie omówiono sposób określania odpowiedniego poziomu podrzędnych składników kosztów i tworzenia reguł akumulacji kosztów, które pasują do schematów sprawozdawczości i monitorowania kosztów w organizacji.
author: AndersGirke
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostRollupRule, CAMDimensionHierarchy, CAMOverheadRatePolicy
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f86529359f548bf48fdef8817bd2e2260235561cce57cac28158739687ade2c1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779963"
---
# <a name="cost-rollup-policy-and-overhead-calculation"></a>Zasady akumulacji kosztów i obliczanie narzutu 

[!include [banner](../includes/banner.md)]

Moduł Rachunek kosztów pozwala zobaczyć, jak przepływ kosztów jest powiązany z produktami i usługami dostarczanymi wewnątrz organizacji. Aby czytelnie widzieć koszty, trzeba uzyskać alokację kosztów między obiektami kosztów w oparciu o odpowiednią podstawę alokacji. Domyślnie alokację kosztów uzyskuje się dla podstawowego składnika kosztów, co jest pożądane w niektórych sytuacjach, ale ma kilka konsekwencji, które trzeba wziąć pod uwagę.

-   Po obliczeniu kosztów ogólnych pomocnicze obiekty kosztów będą miały zerowe salda dla podstawowych składników kosztów.

-   Ilość wpisów kosztów wygenerowanych wskutek obliczania kosztów ogólnych może być bardzo duża.

-   Nie jest możliwe śledzenie przepływu kosztów między obiektami kosztów.

Aby uniknąć tych efektów, moduł Rachunek kosztów umożliwia skonfigurowanie alokacji kosztów spełniającej wymagania sprawozdawczości dla kierownictwa. W tym temacie omówiono sposób określania odpowiedniego poziomu podrzędnych składników kosztów i tworzenia reguł akumulacji kosztów, które pasują do schematów sprawozdawczości i monitorowania kosztów w organizacji.

> [!NOTE]
> W razie zmiany wymagań w zakresie sprawozdawczości można zmieniać konfiguracje.

## <a name="example-of-cost-rollup-policy-setup"></a>Przykład konfiguracji zasady akumulacji kosztów

Załóżmy, że organizacja ma następującą strukturę z 4 centrami kosztów.

![Przykład struktury organizacyjnej.](./media/dimension-hierarchy-org.png)

**Wymiar obiektu kosztów**

| MPK | opis          |
|--------------|-----------|
| CC001        | HR        |
| CC002        | Finanse   |
| CC003        | Zestaw  |
| CC004        | Opakowanie |

**Wymiar składnika kosztu**

| Składniki kosztów | opis | Typ    |
|---------------|-------------|---------|
| 1001          | Elektryczność | Główne |
| 1002          | Wynagrodzenia    | Główne |
| 1003          | Reklama | Główne |

Hierarchię wymiarów spełniającą wymagania sprawozdawcze organizacji można skonfigurować w następujący sposób.

**Szczegóły hierarchii wymiarów**

| Nazwa hierarchii wymiarów | Wymiar    | Nazwa typu hierarchii wymiarów      | Hierarchia list dostępu |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organizacja             | Centra kosztów | Hierarchia klasyfikacji wymiarów | Nie                    |

**Hierarchia wymiarów**

|    &nbsp;    | Zakresy elementów członkowskich wymiaru | &nbsp;              |
|--------------|-------------------------|---------------------|
| **Węzły**        | **Element członkowskiego wymiaru źródłowego**   | **Element członkowski wymiaru docelowego** |
| Organizacja |                         |                     |
| &nbsp;&nbsp;Administrator             |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanse              | CC001                   | CC001               |
| &nbsp;&nbsp;&nbsp;&nbsp;Zasoby ludzkie               | CC002                   | CC002               |
| &nbsp;&nbsp;Produkcja               |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Opakowanie              | CC003                   | CC003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Zestaw             | CC004                   | CC004               |

Hierarchię wymiarów spełniającą wymóg zasady można skonfigurować w następujący sposób.

**Szczegóły hierarchii wymiarów**

| Nazwa hierarchii wymiarów | Wymiar     | Nazwa typu hierarchii wymiarów      |
|--------------------------|---------------|------------------------------------|
| Rachunek zysków i strat  | Składniki kosztów | Hierarchia klasyfikacji wymiarów |

**Hierarchia wymiarów**

|      &nbsp;             | Zakresy elementów członkowskich wymiaru |      &nbsp;         |
|-------------------------|-------------------------|---------------------|
| Węzły                   | Element członkowskiego wymiaru źródłowego   | Element członkowski wymiaru docelowego |
| Rachunek zysków i strat |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Koszt podstawowy                    | 10001                   | 10003               |

Po przetworzeniu zapisów księgi głównej saldo wpisów kosztów z podziałem na obiekty kosztów wygląda następująco.

|      &nbsp;          | **Obiekt kosztów** | &nbsp;    |  &nbsp;   |  &nbsp;   | **Suma**     |
|----------------------|-----------------|-----------|-----------|-----------|---------------|
| **Składnik kosztu**     | **CC001**       | **CC002** | **CC003** | **CC004** |               |
| **1001 Energia elektryczna** | 100,00          | 200 000    | 6.000,00  | 2.000,00  | **8.300,00**  |
| **1002 Wynagrodzenia**    | 10.000,00       | 10.000,00 | 8.000,00  | 6.500,00  | **34.500,00** |
| **1003 Reklama** | 0,00            | 4.000,00  | 0,00      | 0,00      | **4.000,00**  |
|                      | 10.100,00       | 14.200,00 | 14.000,00 | 8.500,00  | **46.800,00** |

**Wymiar statystyczny**

| Elementy statystyczne |    opis   |
|----------------------|------------------|
| SE-1                 | Usługi kadrowe      |
| SE-2                 | Usługi finansowe |

Obiekt kosztów CC001 Zasoby ludzkie wnosi usługi kadrowe do kilku obiektów kosztów.

Usługi kadrowe są zużywane według następującego rozkładu wielkości.

| Obiekt kosztów | opis |   Usługi kadrowe |
|-------------|-------------|----|
| CC002       | Finanse     | 35 |
| CC003       | Zestaw    | 55 |
| CC004       | Opakowanie   | 10 |

Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.

Usługi finansowe są zużywane według następującego rozkładu wielkości.

| Obiekt kosztów |   opis    |  Usługi finansowe   |
|-------------|------------------|----|
| CC003       | Zestaw         | 65 |
| CC004       | Opakowanie        | 35 |

Zasady alokacji kosztów można skonfigurować w następujący sposób.

| Nazwa zasad | opis     | Hierarchia wymiarów obiektów kosztów | Wymiar statystyczny | Wymiar składnika kosztu |
|-------------|-----------------|---------------------------------|-----------------------|------------------------|
| 2017        | Alokacja kosztu | Organizacja                    | Elementy statystyczne  | Składniki kosztów          |

Reguły alokacji kosztów można skonfigurować w następujący sposób.

| Węzeł hierarchii wymiarów obiektów kosztów | Zachowanie kosztów | Podstawa alokacji        |
|--------------------------------------|---------------|------------------------|
| CC001                                | Razem         | **Usługi kadrowe**        |
| CC002                                | Razem         | **Usługi finansowe** |

## <a name="brhow-cost-flows-between-cost-centers"></a><br>Przepływ kosztów między centrami kosztów 

Jeśli chcesz się dowiedzieć, jak koszty przepływają między centrami kosztów w organizacji, można dla każdego centrum kosztów utworzyć składniki kosztów typu **Podrzędny**. Te składniki kosztów będą następnie używane do przenoszenia sald między centrami kosztów podczas obliczania kosztów ogólnych.

Elementy członkowskie wymiaru składnika kosztu można skonfigurować w następujący sposób.

| Składniki kosztów | Typ          |     &nbsp;    |
|---------------|---------------|---------------|
| 1001          | Elektryczność   | Główne       |
| 1002          | Wynagrodzenia      | Główne       |
| 1003          | Reklama   | Główne       |
| **SC-CC001**  | **Zasoby ludzkie**        | **Podrzędny** |
| **SC-CC002**  | **Finanse**   | **Podrzędny** |
| **SC-CC003**  | **Montaż**  | **Podrzędny** |
| **SC-CC004**  | **Pakowanie** | **Podrzędny** |

Hierarchia wymiarów **Rachunek zysków i strat** musi zostać zaktualizowana o nowe elementy członkowskie wymiaru, tak aby hierarchia wymiarów zawiera prawidłowe dane mogące służyć do definiowania sprawozdawczości i zasad.

**Szczegóły hierarchii wymiarów**

| Nazwa hierarchii wymiarów | Wymiar     | Nazwa typu hierarchii wymiarów      |
|--------------------------|---------------|------------------------------------|
| Rachunek zysków i strat  | Składniki kosztów | Hierarchia klasyfikacji wymiarów |

**Hierarchia wymiarów**

|      &nbsp;             | Zakresy elementów członkowskich wymiaru |  &nbsp;             |
|-------------------------|-------------------------|---------------------|
| Węzły                   | Element członkowskiego wymiaru źródłowego   | Element członkowski wymiaru docelowego |
| Rachunek zysków i strat |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Koszt podstawowy                        | 10001                   | 10003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Koszt w drugiej walucie                         | **SC-CC001**            | **SC-CC004**        |

Utwórz **zasadę akumulacji kosztów**, gdzie każde centrum kosztów jest zamapowane na odpowiedni składnik kosztów typu **Podrzędne**.

**Zasady akumulacji kosztów**

| Nazwa zasad | opis | Hierarchia wymiarów obiektów kosztów | Hierarchia wymiarów składników kosztów |
|-------------|-------------|---------------------------------|----------------------------------|
| 2017        | Przepływ kosztów   | Organizacja                    | Rachunek zysków i strat          |

**Reguły akumulacji kosztów**

| Węzeł hierarchii wymiarów obiektów kosztów | Węzeł hierarchii wymiarów składników kosztów | Podrzędny składnik kosztu |
|--------------------------------------|---------------------------------------|------------------------|
| CC001                                | Rachunek zysków i strat               | **SC-CC001**           |
| CC002                                | Rachunek zysków i strat               | **SC-CC002**           |
| CC003                                | Rachunek zysków i strat               | **SC-CC003**           |
| CC004                                | Rachunek zysków i strat               | **SC-CC004**           |

## <a name="perform-overhead-calculation"></a>Obliczanie kosztów ogólnych

**Arkusz**

| W arkuszu | Typ arkusza            | Kalendarzowy okres obrachunkowy | Rok | Okres | Wersja       |
|---------|-------------------------|------------------------|------|--------|---------------|
| 00002   | Arkusz alokacji kosztów | Fiskalny                 | 2017    | Okres 1 | Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1 |

Teraz system będzie stosował **zasadę akumulacji kosztów** podczas tworzenia **wpisów w arkuszu dotyczących salda obiektów kosztów**.

**Wpisy w arkuszu dotyczące salda obiektów kosztów**

| Data księgowania | Obiekt kosztów | opis  | Składnik kosztu | opis |  Ilość |
|-----------------|-------------|--------------|----------|-----------|-----------|
| 31-01-2017      | CC001       | Zasoby ludzkie           | SC-CC001 | Zasoby ludzkie        | 10.100,00 |
| 31-01-2017      | CC002       | Finanse      | SC-CC002 | Finanse   | 17.735,00 |
| 31-01-2017      | CC003       | Zestaw     | SC-CC003 | Zestaw  | 31.082,75 |
| 31-01-2017      | CC004       | Opakowanie    | SC-CC004 | Opakowanie | 15.717,25 |

> [!NOTE]
> Wpisy w arkuszu są tworzone na podstawie reguł określonych w **zasadzie akumulacji kosztów**, jeśli taka zasada istnieje. Wyświetlane saldo jest saldem obliczania kosztów ogólnych.

Strona **Szczegóły wpisu w arkuszu sald kosztów obiektów kosztów** otwierana z poziomu wpisów arkusza pokazuje sposób uzyskania salda.

**Przykład: Wpis w arkuszu dla obiektu kosztów CC002 Finanse**

**Szczegóły wpisu w arkuszu sald kosztów obiektów kosztów**

| Element członkowski wymiaru składnika kosztu | opis |  Ilość   |
|-------------------------------|-------------|-----------|
| 1001                          | Elektryczność | 200 000    |
| 1002                          | Wynagrodzenia    | 10.000,00 |
| 1003                          | Reklama | 4.000,00  |
| SC-CC001                      | Zasoby ludzkie          | 3.535,00  |

**Wpisy kosztów wygenerowane przez obliczanie kosztów ogólnych**

| Obiekt kosztów | opis  | Składnik kosztu   | opis  |        Ilość     |       Data księgowania     |
|-------------|--------------|----------|-----------------|-------------|------------|
| CC001       | Zasoby ludzkie           | SC-CC001 | Zasoby ludzkie              | 10.100,00\- | 31-01-2017 |
| CC002       | Finanse      | SC-CC001 | Zasoby ludzkie              | 3.535,00    | 31-01-2017 |
| CC003       | Zestaw     | SC-CC001 | Zasoby ludzkie              | 5.555,00    | 31-01-2017 |
| CC004       | Opakowanie    | SC-CC001 | Zasoby ludzkie              | 1.010,00    | 31-01-2017 |
| CC002       | Finanse      | SC-CC002 | Finanse         | 17.735,00\- | 31-01-2017 |
| CC003       | Zestaw     | SC-CC002 | Finanse         | 11.527,75   | 31-01-2017 |
| CC004       | Opakowanie    | SC-CC002 | Finanse         | 6.207,25    | 31-01-2017 |

Po zakończeniu **obliczania kosztów ogólnych** można zaraportować wyniki przy użyciu narzędzi takich jak Microsoft SharePoint Workspace, Excel lub Power BI.

## <a name="view-reporting-in-excel"></a>Wyświetlanie raportów w programie Excel 

Hierarchie wymiarów umożliwiają wyświetlanie danych na różnych poziomach agregacji.

Poniżej przedstawiono przykład raportu Power Pivot w programie Excel.

| **Rachunek zysków i strat** | **Obiekt kosztów** |      &nbsp;    |   &nbsp;      |     &nbsp;    |  **Suma**    |
|-----------------------------|-----------------|----------------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002**      | **CC003**     | **CC004**     |               |
| **Koszt podstawowy**            | **10.100,00**   | **14.200,00**  | **14.000,00** | **8.500,00**  | **46.800,00** |
| 1001&nbsp;&nbsp;&nbsp;&nbsp;                            | 100,00          | 200 000         | 6.000,00      | 2.000,00      | **8.300,00**  |
| 1002&nbsp;&nbsp;&nbsp;&nbsp;                            | 10.000,00       | 10.000,00      | 8.000,00      | 6.500,00      | **34.500,00** |
|1003&nbsp;&nbsp;&nbsp;&nbsp;                             | 0,00            | 4.000,00       | 0,00          | 0,00          | **4.000,00**  |
|**Koszt podrzędny**                            | **-10 100,00**  | **-14 200,00** | **17,082,75** | **7.217,25**  | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC001                            | 10.100,00\-     | 3.535,00       | 5.555,00      | 1.010,00      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC002                             | 0,00            | 17.735,00\-    | 11.527,75     | 6.207,25      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC003                            | 0,00            | 0,00           | 0,00          | 0,00          | 0,00          |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC004                             | 0,00            | 0,00           | 0,00          | 0,00          | 0,00          |
| **Suma**                   | **0,00**        | **0,00**       | **31.082,75** | **15.717,25** | **46.800,00** |

Za pomocą **zasady akumulacji kosztów** i **podrzędnych składników kosztów** można pozostawić koszt podstawowy obiektu kosztów dla sprawozdawczości wewnętrznej jako koszt podstawowy, która pozostaje po **obliczeniu kosztów ogólnych**.

Jeśli ten sam przykład zostałby wykonany bez tworzenia **zasady akumulacji kosztów**, wynik raportowania wyglądałby jak poniżej. Koszt przepływa poprawnie, ale traci się możliwość jego identyfikacji i wglądu w sposób przepływu między centrami kosztów.

| **Rachunek zysków i strat** | **Obiekt kosztów** |   &nbsp;  |    &nbsp;     |  &nbsp;       |          **Suma**  |
|-----------------------------|-----------------|-----------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002** | **CC003**     | **CC004**     |               |
| **Koszt podstawowy**            | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |
|1001&nbsp;&nbsp;&nbsp;&nbsp;                              | 0,00            | 0,00      | 6.207,75      | 2.092,25      | **8.300,00**  |
| 1002&nbsp;&nbsp;&nbsp;&nbsp;                             | 0,00            | 0,00      | 22.275,00     | 12.225,00     | **34.500,00** |
|1003&nbsp;&nbsp;&nbsp;&nbsp;                              | 0,00            | 0,00      | 2600,00       | 1.400,00      | **4.000,00**  |
|**Koszt podrzędny**                            | **0,00**        | **0,00**  | **0,00**      | **0,00**      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC001                             | 0,00            | 0,00      | 0,00          | 0,00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC002                             | 0,00            | 0,00      | 0,00          | 0,00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC003                             | 0,00            | 0,00      | 0,00          | 0,00          | 0,00          |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC004                             | 0,00            | 0,00      | 0,00          | 0,00          | 0,00          |
| **Suma**                   | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |

Zależnie od wymagań dotyczących sprawozdawczości i monitorowania w organizacji można określić odpowiedni poziom podrzędnych składników kosztów i tworzyć reguły akumulacji kosztów spełniających konkretne potrzeby.

Wyraźne rozgraniczenie między **alokacją kosztów** a **zasadami akumulacji kosztów** zapewnia elastyczność pozwalającą dokonywać ciągłych aktualizacji bez wzajemnego oddziaływania tych obiektów na siebie.



## <a name="additional-resources"></a>Dodatkowe zasoby
-  [Wymiary obiektów kosztów](cost-objects.md)
-  [Wymiary składników kosztów](cost-elements.md)
-  [Hierarchia wymiarów](dimension-hierarchy.md)
-  [Obliczenie narzutu](overhead-calculation.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]