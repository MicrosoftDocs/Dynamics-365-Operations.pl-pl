---
title: Szablony podziału przychodów w rozliczeniach subskrypcyjnych
description: Ten temat wyjaśnia, jak skonfigurować szablony podziału przychodu dla artykułów sprzedawanych jako pakiety.
author: JodiChristiansen
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 73dbc2242639a54d687506e7c325fec4b9a95d12
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770162"
---
# <a name="revenue-split-templates-in-subscription-billing"></a>Szablony podziału przychodów w rozliczeniach subskrypcyjnych

Użyj strony **Szablon podziału przychodu**, aby skonfigurować szablony dla podziału przychodu. Podział dochodu składa się z elementu nadrzędnego, który posiada elementy potomne. Tego typu przedmioty są często sprzedawane klientom jako pojedyncze sztuki lub w pakietach.

Na przykład element komputerowy może być utworzony w następujący sposób:

- **Przedmiot nadrzędny:** Subskrypcja Silver
- **Pozycje wiersza (podrzędne):**

    - Pomoc techniczna
    - Konserwacja
    - Licencja

Kiedy tworzysz element nadrzędny, pamiętaj o następujących ograniczeniach:

- Element może być określony jako element nadrzędny tylko jeden raz.
- Element nadrzędny może być wybrany jako element dziecięcy w tym samym szablonie.
- Prawidłowy szablon wymaga co najmniej jednego elementu podrzędnego.
- Element może być określony jako element podrzędny dla więcej niż jednego elementu wiązki.
- Każda relacja nadrzędny-podrzędny musi być unikalna.

## <a name="create-a-parent-item-that-has-child-items"></a>Utwórz element nadrzędny, który ma elementy podrzędne

Wykonaj poniższe kroki, aby utworzyć element nadrzędny, który będzie miał elementy podrzędne.

1. Na stronie **Szablon podziału przychodu** wybierz **Nowy**.
1. W polu **Element nadrzędny** wybierz element nadrzędny. Pole **Numer wariantu** jest aktualizowane automatycznie. Można jednak zmienić jego wartość.
1. W polu **Metoda alokacji** wybierz metodę alokacji.
1. Na liście **Elementy komponentu** wybierz **Dodaj**, aby dodać elementy dziecięce.
1. Jeśli w polu **Metoda alokacji** wybrałeś **procent**, w polu **Procent** podaj wartość procentową.

    - Jeśli w polu **Metoda alokacji** wybrałeś **Równa kwota**, pole **Procent** zostanie automatycznie zaktualizowane, tak aby każdy element miał równy procent.
    - Jeśli w polu **Metoda alokacji** wybrałeś **kwotę zmienną**, **zero kwoty głównej** lub **zero kwoty**, wartość pola **Procent** pozostaje **0** (zero) i nie może zostać zmieniona.

1. Wybierz opcję **Zapisz**.

## <a name="fields"></a>Pola

Strona **Szablon podziału przychodów** zawiera następujące pola.

| Pole | Opis |
|-------|-------------|
| Pozycja nadrzędna | Wybierz numer pozycji. Ten element staje się elementem nadrzędnym dla elementu pakietu, który tworzysz. |
| Nazwa produktu | Nazwa produktu. |
| Metoda alokacji | <p>Wybierz sposób przydziału:</p><ul><li>**Równa kwota** — wartości procentowe alokacji są obliczane automatycznie i w równej wysokości dzielone między wszystkie towary w szablonie.</li><li>**Procent** – Możesz określić procentową wartość przydziału. Suma wszystkich wartości procentowych musi być równa 100.</li><li>**Kwota zmienna** – dodane elementy podrzędne mają wartość netto równą 0 (zero). Cena pozycji podrzędnych musi być określona na poziomie transakcji.</li><li>**Kwota zero** – pozycja nadrzędna zachowuje swoją cenę jednostkową i kwotę netto. Wszystkie pozycje dziecka mają wartość netto równą 0 (zero).</li><li>**Zerowa kwota nadrzędna** – pozycja nadrzędna ma stałą wartość netto równą 0 (zero). Wszystkie elementy dziecięce są traktowane jak elementy standardowe. Nie jest przeprowadzana walidacja, aby sprawdzić, czy suma kwot pozycji podrzędnych jest równa kwocie pozycji nadrzędnej.</li></ul> |
| **Pozycje składnika** | |
| Pozycja składnika | Wybierz numer pozycji. Ten element jest podrzędny. |
| Numer wariantu | Wybierz numer wariantu dla elementu. |
| Nazwa produktu | Nazwa produktu. |
| Wartość procentowa | <p>Procent alokacji dla miejsca etapu:</p><ul><li>Jeśli w polu **Metoda alokacji** jest ustawiona wartość **Procent**, możesz określić wartość procentową dla wiersza.</li><li>Jeśli w polu **Metoda alokacji** jest ustawiona wartość **Równa ilość**, procent jest obliczany automatycznie, tak aby każdy element w szablonie miał taki sam procent.</li><li>Jeśli pole **Metoda alokacji** jest ustawione na **kwotę zmienną**, **zero kwoty nadrzędnej** lub **zero kwoty**, wartość procentowa wynosi 0 (zero) i nie może być edytowana.</li></ul><p>Wartość tego pola może być dowolną liczbą dodatnią z przedziału od 0 (zero) do 100. Suma wszystkich wartości procentowych musi być równa 100.</p> |
| Łączny procent | <p>Suma wartości w kolumnie **Procent**.</p><ul><li>Jeśli pole **Metoda alokacji** jest ustawione na **Wartość** lub **Procent**, suma wszystkich procentów musi być równa 100.</li><li>Jeśli pole **Metoda alokacji** jest ustawione na **kwotę zmienną**, **zero kwoty nadrzędnej** lub **zero kwoty**, całkowita wartość procentowa wynosi 0 (zero) i nie może być edytowana.</li></ul> |

## <a name="revenue-split-on-a-sales-order"></a>Podział przychodu na zlecenie sprzedaży

Aby utworzyć zlecenie sprzedaży z pozycją, która jest ustawiona na podział przychodu, wykonaj poniższe kroki.

1. Na stronie **Zamówienie sprzedaży** utwórz zlecenie sprzedaży.
2. W wierszu każdej pozycji, w której ustawiony jest podział przychodów, zaznacz pole wyboru **Podział przychodów**. Ten element staje się elementem nadrzędnym. Jeśli szablon jest już skonfigurowany, elementy podrzędne automatycznie pojawiają się na liście.
3. Aby dodać więcej pozycji podrzędnych, wybierz **Dodaj dziecko podziału przychodu** i wybierz pozycję podrzędną, którą chcesz dodać.
4. Zapisz zamówienie.

## <a name="revenue-split-with-billing-schedules"></a>Podział przychodów według harmonogramu rozliczeń

Aby utworzyć harmonogram rozliczeń z pozycją, która jest ustawiona na podział przychodu, wykonaj poniższe kroki.

1. Na stronie **Wszystkie/Aktywne harmonogramy fakturowania** utwórz harmonogram rozliczeniowy.
2. W wierszu każdej pozycji, w której ustawiony jest podział przychodów, zaznacz pole wyboru **Podział przychodów**. Ten element staje się elementem nadrzędnym. Jeśli szablon jest już skonfigurowany, elementy podrzędne automatycznie pojawiają się na liście.
3. Aby dodać więcej pozycji podrzędnych, wybierz **Dodaj dziecko podziału przychodu** i wybierz pozycję podrzędną, którą chcesz dodać.
4. Kontynuuj pracę z harmonogramem rozliczeń.

> [!NOTE]
> Jeśli opcja **Automatycznie utwórz podział przychodu** jest ustawiona na **Tak** na stronie **Parametry rozliczania kontraktu cyklicznego**, wystąpią następujące działania:
>
> - Jeśli pozycja linii jest ustawiona jako pozycja nadrzędna w szablonie podziału przychodu, pole wyboru **Podział przychodu** jest automatycznie zaznaczone.
> - Pozycje podrzędne są automatycznie wprowadzane do wiersza zlecenia sprzedaży lub harmonogramu rozliczeń.
>
> Jeśli opcja **Automatycznie utwórz podział przychodu** jest ustawiona na **Nie**, zachowanie jest takie, jak opisano wcześniej.

## <a name="additional-revenue-split-information"></a>Dodatkowe informacje o podziale przychodów

Kiedy dodajesz pozycję, która jest częścią podziału przychodu, zwróć uwagę na następujące informacje: 

- Kwota macierzysta nie może być odroczona.
- Data rozpoczęcia, data zakończenia, ilość, jednostka, miejsce i wartości magazynowe pozycji podrzędnych są oparte na pozycji nadrzędnej. Wartości te nie mogą być zmienione dla elementów podrzędnych. Wszystkie zmiany muszą być dokonywane w elemencie nadrzędnym. 
- Metoda ustalania cen jest **płaska** i nie można jej zmienić.
- Elementy podrzędne mogą być dodawane i usuwane.
- Elementy nadrzędne i podrzędne muszą używać tej samej grupy elementów. 
- Elementy podrzędne mogą mieć jedną z następujących konfiguracji:

    - Pola **Częstotliwość rozliczeń** i **Częstotliwość rozliczeń** są ustawione na taką samą wartość jak w przypadku elementu nadrzędnego. 
    - Pole **Częstotliwość rozliczania** jest ustawione na **Jeden raz**. W tym przypadku pole **Odstępy rozliczeniowe** jest automatycznie ustawione na **1**. 

- Suma kwot netto pozycji podrzędnych jest równa kwocie nadrzędnej. Jeśli metodą alokacji jest **kwoty zerowe**, zarówno suma kwot pozycji podrzędnych, jak i kwota nadrzędna wynoszą 0 (zero). 

    > [!NOTE]
    > Jeśli metodą alokacji jest **Zero kwoty nadrzędnej**, to (niezerowa) suma pozycji podrzędnych nie jest równa kwocie nadrzędnej, czyli wynosi 0 (zero). Ta metoda alokacji jest używana do celów wewnętrznych, aby pracownicy mogli zobaczyć pozycje podrzędne. Klienci mogą jednak zobaczyć tylko element nadrzędny.

- Jeśli typ układu wieloelementowego (MEA) dla zamówienia sprzedaży to **Jeden**, odpowiednia linia transakcyjna przypisania przychodu wieloelementowego jest tworzona po dodaniu pozycji nadrzędnej i podrzędnej. 
- Jeśli metodą podziału dochodu jest **Równe kwoty**, a kwota nadrzędna zostanie zmieniona, kwoty zostaną przeliczone dla wszystkich linii podrzędnych. 
- W przypadku podziału przychodu, gdzie metodą alokacji jest **Kwota zmienna**, mają miejsce następujące działania:

    - Kwota netto pozycji nadrzędnej pojawia się w kolumnie **Kwota nadrzędna**. Tej wartości można edytować. Jednak cena jednostkowa, kwota netto i rabat wynoszą 0 (zero) i nie mogą być edytowane.
    - Cena jednostkowa elementów podrzędnych wynosi 0 (zero). Możesz edytować cenę jednostkową lub kwotę netto. Kiedy edytujesz jedną wartość, druga wartość jest automatycznie aktualizowana.

- W przypadku podziału przychodu, gdzie metodą alokacji jest **Procent**, mają miejsce następujące działania:

    - Kwota netto pozycji nadrzędnej pojawia się w kolumnie **Kwota nadrzędna**. Tej wartości można edytować. Jednak cena jednostkowa, kwota netto i rabat wynoszą 0 (zero) i nie mogą być edytowane. 
    - Kwota netto elementów podrzędnych jest obliczana jako *procent* &times; *kwota nadrzędna*.

- W przypadku podziału przychodu, gdzie metodą alokacji jest **Równa ilość**, mają miejsce następujące działania:

    - Kwota netto pozycji nadrzędnej pojawia się w kolumnie **Kwota nadrzędna**. Tej wartości można edytować. Jednak cena jednostkowa, kwota netto i rabat wynoszą 0 (zero) i nie mogą być edytowane. 
    - Kwota netto pozycji podrzędnych jest obliczana przez podzielenie kwoty głównej równo pomiędzy wszystkie pozycje podrzędne. 
    - Jeśli pozycje podrzędne są usuwane lub dodawane, kwota netto i ceny jednostkowe są przeliczane tak, aby wszystkie linie podrzędne miały równe kwoty. 
    - Jeśli kwoty głównej nie da się podzielić równo, kwota netto i cena jednostkowa ostatniego elementu podrzędnego może być nieco wyższa lub niższa niż kwota netto i cena jednostkowa pozostałych elementów podrzędnych. 

- W przypadku podziału przychodu, gdzie metodą alokacji jest **Kwota zerowa**, mają miejsce następujące działania:

    - Można edytować cenę jednostkową, kwotę netto i rabat. Kwota nadrzędna wynosi 0 (zero) i nie może być edytowana. 
    - Ilość, jednostka, miejsce i wartości magazynowe pozycji podrzędnych są oparte na pozycji nadrzędnej. Wartości te nie mogą być zmienione dla elementów podrzędnych. Wszystkie zmiany muszą być dokonywane w elemencie nadrzędnym. 
    - Cena jednostkowa i cena netto pozycji podrzędnych wynosi 0 (zero) i nie może być edytowana. 

- W przypadku podziału przychodu, gdzie metodą alokacji jest **Zerowa kwota macierzysta**, mają miejsce następujące działania:

    - Cena jednostkowa, kwota nadrzędna i kwota netto pozycji nadrzędnej wynoszą 0 (zero).
    - W harmonogramie rozliczeń linie podrzędne pojawiają się tak, jakby zostały dodane ręcznie, a wszystkie wartości są aktualizowane na podstawie wybranej grupy harmonogramu rozliczeń. Wartości te mogą być edytowane. W przypadku pozycji podrzędnych możesz uzyskać dostęp do opcji **Eskalacja i rabat** oraz **Zaawansowana wycena**, korzystając z pól **Wprowadzona ilość**, **Cena jednostkowa**, **Zniżka** oraz **Kwota netto** w **Wyświetl szczegóły rozliczenia**. 
    - W zamówieniu sprzedaży wiersze podrzędne mają rabat i wartość procentową rabatu 0 (zero). 
    - Częstotliwość fakturowania pozycji nadrzędnych i podrzędnych może być zmieniana, a każda linia może mieć inną częstotliwość. Jednak element nadrzędny jest automatycznie aktualizowany tak, by wykorzystywał najkrótszą częstotliwość spośród swoich linii podrzędnych. Na przykład podział przychodów ma dwie pozycje podrzędne, z których jedna korzysta z **miesięcznej** częstotliwości rozliczeń, a druga z **rocznej** częstotliwości rozliczeń. W tym przypadku częstotliwość rozliczeń elementu nadrzędnego jest aktualizowana do **Miesięcznie**.
