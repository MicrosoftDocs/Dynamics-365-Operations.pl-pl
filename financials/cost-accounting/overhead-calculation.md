---
title: Obliczenie narzutu
description: "W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: c040a50d9962d7a900fbef285ea1f1baea124033
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017

---

# <a name="overhead-calculation"></a>Obliczenie narzutu

[!include[banner](../includes/banner.md)]


W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.

<a name="term-definition"></a>Definicja terminu
---------------

Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi. Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk. Oto kilka przykładów kosztów ogólnych:

-   Dzierżawa
-   Elektryczność
-   Wynagrodzenia administracyjne

## <a name="overhead-calculation-overview"></a>Omówienie obliczania kosztów ogólnych
W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności. Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy. Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach. Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania. Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu. Unikatowy identyfikator wersji składa się z następujących elementów:

-   Typ wersji
-   Data i godzina
-   Księga rachunku kosztów
-   Rok obrachunkowy
-   Okres obrachunkowy

Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji. W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą. Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji. Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu. Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń. Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów. Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów. 
[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a>Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej
W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt. W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów. Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne. Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie. W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.

<table>
<thead>
<tr>
<th>Data księgowania</th>
<th colspan="2">Centrum kosztu</th>
<th colspan="2">Konto główne</th>
<th>Kwota w walucie rozliczeniowej</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 stycznia 2017</td>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a>Krok 1: Przetwarzanie obliczania zachowania kosztów

Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów. Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.

#### <a name="define-the-cost-behavior-rule"></a>Definiowanie reguły zachowania kosztów

W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu. Rachunki za energię elektryczną często pasują do tej definicji. Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh). Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:

-   Kwota stała 1000,00
    -   0 &lt;= 1000,00 = Stały
    -   1000,01 &lt; N = Zmienny

##### <a name="journal"></a>W arkuszu

<table>
<thead>
<tr>
<th>W arkuszu</th>
<th>Typ arkusza</th>
<th colspan="3">Kalendarzowy okres obrachunkowy</th>
<th>Wersja</th>
</tr>
</thead>
<tbody>
<tr>
<td>00001</td>
<td>Arkusz obliczania zachowania kosztów</td>
<td>Fiskalny</td>
<td>2017</td>
<td>Okres 1</td>
<td>Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)

<table>
<thead>
<tr>
<th>Data księgowania</th>
<th colspan="2">Obiekt kosztów</th>
<th colspan="2">Składnik kosztu</th>
<th>Zachowanie kosztów</th>
<th>Ilość</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 stycznia 2017</td>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Niesklasyfikowane</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Wpisy kosztów

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th colspan="2">Składnik kosztu</th>
<th>Zachowanie kosztów</th>
<th>Ilość</th>
<th>Data księgowania</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Niesklasyfikowane</td>
<td>10,000.00</td>
<td>3 stycznia 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Niesklasyfikowane</td>
<td>-10 000,00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>1000,00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>9,000.00</td>
<td>31 stycznia 2017</td>
</tr>
</tbody>
</table>

Aby uzyskać szczegółowe informacje o zachowaniu kosztów, zobacz temat Zasada zachowania kosztów. (należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).

### <a name="step-2-process-the-cost-distribution-calculation"></a>Krok 2: Przetwarzanie obliczania dystrybucji kosztów

Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji. Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.

#### <a name="define-the-cost-distribution-rule"></a>Definiowanie reguły dystrybucji kosztów

W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt. W rachunku kosztów to podejście nie jest wystarczająco szczegółowe. Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy. Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh). Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej. Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>kWh</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>1 000</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>6,000</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>0</td>
</tr>
</tbody>
</table>

W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Wartość</th>
<th>Współczynnik alokacji</th>
<th>Ilość</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>1 000</td>
<td>(1000 ÷ 7000) × 9000,00</td>
<td>1,285.71</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>6,000</td>
<td>(6000 ÷ 7000) × 9000,00</td>
<td>7,714.29</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>0</td>
<td>(0 ÷ 7000) × 9000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd. Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Wzór</th>
<th>Wartość</th>
<th>Współczynnik alokacji</th>
<th>Ilość</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>(1000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1000,00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>(6000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1000,00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>(0 &gt; 0,00)</td>
<td>0</td>
<td>(0 ÷ 2) × 1000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>W arkuszu

<table>
<thead>
<tr>
<th>W arkuszu</th>
<th>Typ arkusza</th>
<th colspan="3">Kalendarzowy okres obrachunkowy</th>
<th>Wersja</th>
</tr>
</thead>
<tbody>
<tr>
<td>00002</td>
<td>Arkusz obliczania dystrybucji kosztów</td>
<td>Fiskalny</td>
<td>2017</td>
<td>Okres 1</td>
<td>Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)

<table>
<thead>
<tr>
<th>Data księgowania</th>
<th colspan="2">Obiekt kosztów</th>
<th colspan="2">Składnik kosztu</th>
<th>Zachowanie kosztów</th>
<th>Ilość</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 stycznia 2017</td>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>1000,00</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>9,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Wpisy kosztów

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th colspan="2">Składnik kosztu</th>
<th>Zachowanie kosztów</th>
<th>Ilość</th>
<th>Data księgowania</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>-1000,00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>500.00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>500.00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Domyślne centrum kosztu</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>-9000,00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>1,285.71</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>7,714.29</td>
<td>31 stycznia 2017</td>
</tr>
</tbody>
</table>

Aby uzyskać szczegółowe informacje na temat dystrybucji kosztów i podstaw alokacji, zobacz tematy Zasada dystrybucji kosztów i Podstawa alokacji. (należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).

### <a name="step-3-process-the-overhead-rate-calculation"></a>Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego

Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów. Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji. 

#### <a name="define-the-overhead-rate"></a>Definiowanie stawki kosztu ogólnego

Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych. Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Godziny</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>Projekt 1</td>
<td>3</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Projekt 2</td>
<td>1</td>
</tr>
</tbody>
</table>

Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Składnik kosztu</th>
<th>Zachowanie kosztów</th>
<th>Jednostki</th>
<th>Kurs</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>10001</td>
<td>Koszt zmienny</td>
<td>1</td>
<td>10</td>
</tr>
</tbody>
</table>

W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Wartość</th>
<th>Składnik kosztu</th>
<th>Współczynnik alokacji</th>
<th>Ilość</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>Projekt 1</td>
<td>3</td>
<td>10001</td>
<td>(3 ÷ 1) × 10,00</td>
<td>30.00</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Projekt 2</td>
<td>1</td>
<td>10001</td>
<td>(1 ÷ 1) × 10,00</td>
<td>10,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>W arkuszu

<table>
<thead>
<tr>
<th>W arkuszu</th>
<th>Typ arkusza</th>
<th colspan="3">Kalendarzowy okres obrachunkowy</th>
<th>Wersja</th>
</tr>
</thead>
<tbody>
<tr>
<td>00003</td>
<td>Arkusz obliczania stawek narzutów</td>
<td>Fiskalny</td>
<td>2017</td>
<td>Okres 1</td>
<td>Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a>Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)

<table>
<thead>
<tr>
<th>Data księgowania</th>
<th colspan="2">Obiekt kosztów</th>
<th>Wartość</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 stycznia 2017</td>
<td>Proj 1</td>
<td>Proj wewnętrzny 1</td>
<td>3,00</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>Proj 2</td>
<td>Proj wewnętrzny 2</td>
<td>1.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Wpisy kosztów

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th colspan="2">Składnik kosztu</th>
<th>Zachowanie kosztów</th>
<th>Ilość</th>
<th>Data księgowania</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC0001</td>
<td>Zasoby ludzkie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>-30,00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Proj 1</td>
<td>Proj wewnętrzny 1</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>30.00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>-10,00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Proj wewnętrzny 2</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>10,00</td>
<td>31 stycznia 2017</td>
</tr>
</tbody>
</table>

Aby uzyskać szczegółowe informacje o zasadach stawek kosztów ogólnych, zobacz tematy Zasada stawki kosztu ogólnego i Podstawy alokacji. (należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).

### <a name="step-4-process-the-cost-allocation-calculation"></a>Krok 4: Przetwarzanie obliczania alokacji kosztów

Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji. Program Finance and Operations obsługuje metody wzajemnej alokacji. W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów. System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja. Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji. Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi. Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów. [![Metoda wzajemna](./media/reciprocal-method.png)]

#### <a name="define-the-cost-allocation"></a>Definiowanie alokacji kosztów

Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów. Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów. Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Usługi kadrowe</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>35</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>55</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>10</td>
</tr>
</tbody>
</table>

Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów. Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Usługi finansowe</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>65</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>35</td>
</tr>
</tbody>
</table>

Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów. Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Usługi montażowe (w godzinach)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>60</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>20</td>
</tr>
</tbody>
</table>

Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów. Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Usługi pakowania (w godzinach)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>80</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>15</td>
</tr>
</tbody>
</table>

**Uwaga:** W programie Finance and Operations miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych. Aby uzyskać bardziej szczegółowe informacje o dostawcach miar statystycznych, zobacz temat Szablon dostawcy miar statystycznych (należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy). W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Wartość</th>
<th>Współczynnik alokacji</th>
<th>Ilość</th>
<th>Zachowanie kosztów</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>35</td>
<td>(35 ÷ 100) × 500,00</td>
<td>175.00</td>
<td>Koszt stały</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>55</td>
<td>(55 ÷ 100) × 500,00</td>
<td>275.00</td>
<td>Koszt stały</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>10</td>
<td>(10 ÷ 100) × 500,00</td>
<td>50,00</td>
<td>Koszt stały</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>35</td>
<td>(35 ÷ 100) × 1245,71</td>
<td>436.00</td>
<td>Koszt zmienny</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>55</td>
<td>(55 ÷ 100) × 1245,71</td>
<td>685.14</td>
<td>Koszt zmienny</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>10</td>
<td>(10 ÷ 100) × 1245,71</td>
<td>124.57</td>
<td>Koszt zmienny</td>
</tr>
</tbody>
</table>

W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Wartość</th>
<th>Współczynnik alokacji</th>
<th>Ilość</th>
<th>Zachowanie kosztów</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>65</td>
<td>(65 ÷ 100) × (500,00 + 175,00)</td>
<td>438.75</td>
<td>Koszt stały</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>35</td>
<td>(35 ÷ 100) × (500,00 + 175,00)</td>
<td>236.25</td>
<td>Koszt stały</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>65</td>
<td>(65 ÷ 100) × (7714,29 + 436,00)</td>
<td>5,297.69</td>
<td>Koszt zmienny</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>35</td>
<td>(35 ÷ 100) × (7714,29 + 436,00)</td>
<td>2,852.60</td>
<td>Koszt zmienny</td>
</tr>
</tbody>
</table>

W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Wartość</th>
<th>Współczynnik alokacji</th>
<th>Ilość</th>
<th>Zachowanie kosztów</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>60</td>
<td>(60 ÷ 80) × (275,00 + 438,75)</td>
<td>535.31</td>
<td>Koszt stały</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>20</td>
<td>(20 ÷ 80) × (275,00 + 438,75)</td>
<td>178.44</td>
<td>Koszt stały</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>60</td>
<td>(60 ÷ 80) × (5297,69 + 685,14)</td>
<td>4,487.12</td>
<td>Koszt zmienny</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>20</td>
<td>(20 ÷ 80) × (5297,69 + 685,14)</td>
<td>1,495.71</td>
<td>Koszt zmienny</td>
</tr>
</tbody>
</table>

W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th>Wartość</th>
<th>Współczynnik alokacji</th>
<th>Ilość</th>
<th>Zachowanie kosztów</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>80</td>
<td>(80 ÷ 95) × (50,00 + 236,25)</td>
<td>241.05</td>
<td>Koszt stały</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>15</td>
<td>(15 ÷ 95) × (50,00 + 236,25)</td>
<td>45.20</td>
<td>Koszt stały</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>80</td>
<td>(80 ÷ 95) × (2852,60 + 124,57)</td>
<td>2,507.09</td>
<td>Koszt zmienny</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>15</td>
<td>(15 ÷ 95) × (2852,60 + 124,57)</td>
<td>470.08</td>
<td>Koszt zmienny</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)

<table>
<thead>
<tr>
<th>W arkuszu</th>
<th>Typ arkusza</th>
<th colspan="3">Kalendarzowy okres obrachunkowy</th>
<th>Wersja</th>
</tr>
</thead>
<tbody>
<tr>
<td>00004</td>
<td>Arkusz alokacji kosztów</td>
<td>Fiskalny</td>
<td>2017</td>
<td>Okres 1</td>
<td>Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a>Wiersze arkusza

<table>
<thead>
<tr>
<th>Data księgowania</th>
<th colspan="2">Obiekt kosztów</th>
<th colspan="2">Składnik kosztu</th>
<th>Zachowanie kosztów</th>
<th>Ilość</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 stycznia 2017</td>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>500.00</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>1,245.71</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>CC002</td>
<td>Finanse</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>675.00</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>CC002</td>
<td>Finanse</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>8,150.29</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>713.75</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>5,982.83</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>CC003</td>
<td>Opakowanie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>286.25</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>CC003</td>
<td>Opakowanie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>2,977.17</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>776.36</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>6,994.21</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>Prod 2</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>223.64</td>
</tr>
<tr>
<td>31 stycznia 2017</td>
<td>Prod 2</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>1,965.79</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Wpisy kosztów

<table>
<thead>
<tr>
<th colspan="2">Obiekt kosztów</th>
<th colspan="2">Składnik kosztu</th>
<th>Zachowanie kosztów</th>
<th>Ilość</th>
<th>Data księgowania</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>-500,00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>175.00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>275.00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>50,00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Zasoby ludzkie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>-1245,71</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>436.00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>685.14</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>124.57</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>-675,00</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>438.75</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>236.25</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanse</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>-8150,29</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>5,297.69</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Opakowanie</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>2,852.60</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>-713,75</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>535.31</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>178.44</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>-5982,83</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>4,487.12</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>1,495.71</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>-286,25</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>241.05</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt stały</td>
<td>45.20</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Zestaw</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>-2977,17</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>2,507.09</td>
<td>31 stycznia 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>10001</td>
<td>Elektryczność</td>
<td>Koszt zmienny</td>
<td>470.08</td>
<td>31 stycznia 2017</td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a>Wniosek
W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze. W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony. W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane. Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.

<table>
<thead>
<tr>
<th colspan="2" rowspan="2">Składnik kosztu</th>
<th colspan="9">Obiekt kosztów</th>
<th rowspan="2">Razem</th>
</tr>
<tr>
<th>CC099</th>
<th>CC001</th>
<th>CC002</th>
<th>CC003</th>
<th>CC004</th>
<th>Proj 1</th>
<th>Proj 2</th>
<th>Prod 1</th>
<th>Prod 2</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">10001 Energia elektryczna</td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><strong>30,00</strong></td>
<td style="text-align: right;"><strong>10,00</strong></td>
<td style="text-align: right;"><strong>7.770,57</strong></td>
<td style="text-align: right;"><strong>2.189,43</strong></td>
<td style="text-align: right;"><strong>10.000,00</strong></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;">Niesklasyfikowane</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Koszt stały</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;">776.36</td>
<td style="text-align: right;">223.64</td>
<td style="text-align: right;"><strong>1.000,00</strong></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Koszt zmienny</td>
<td style="text-align: right;">000</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">30.00</td>
<td style="text-align: right;">10,00</td>
<td style="text-align: right;">6,994.21</td>
<td style="text-align: right;">1,965.79</td>
<td style="text-align: right;"><strong>9.000,00</strong></td>
</tr>
</tbody>
</table>

> [!NOTE]
> W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów. W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji. Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie. Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów. Aby uzyskać szczegółowe informacje, zobacz temat Zasada akumulacji kosztów. (należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).




