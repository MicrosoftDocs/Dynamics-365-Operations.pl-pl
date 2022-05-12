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
ms.openlocfilehash: 5c2eb6c8e18770eb149c445f662ab7a90aad81a7
ms.sourcegitcommit: 367e323bfcfe41976e5d8aa5f5e24a279909d8ac
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/29/2022
ms.locfileid: "8660459"
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
