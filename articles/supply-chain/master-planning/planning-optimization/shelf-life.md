---
title: Planowanie główne dla produktów o ograniczonym okresie trwałości
description: W tym artykule opisano sposób skonfigurowania i używania funkcji planowania, które bierze pod uwagę okres trwałości psujących się produktów.
author: t-benebo
ms.date: 08/10/2022
ms.topic: article
ms.search.form: ReqPlanSched, CustTable, EcoResProductDetailsExtended, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 95c905cbcc3c057dbccf2b7d6e894b1e99ddfba5
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337162"
---
# <a name="master-planning-for-products-with-limited-shelf-life"></a>Planowanie główne dla produktów o ograniczonym okresie trwałości

[!include [banner](../../includes/banner.md)]

Okres trwałości to czas przechowywania produktu do momentu, aż nie będzie można go już używać ani sprzedać. W przypadku produktów o ograniczonym okresie trwałości prawdopodobnie będzie można użyć strategii magazynu „pierwsze przeterminowane, pierwsze usunięte” (FEFO), która określa priorytety zużycia i sprzedaży towarów na podstawie pozostałego okresu przydatności. Ta strategia magazynu jest charakterystyczna dla żywności, leków i innych towarów, które charakteryzuje się krótkim czasem magazynowania. Według FEFO towary w magazynie są przechowywane jak towary na półce supermarketu: produkty o długim okresie trwałości są umieszczone w głębi półek, dzięki czemu najpierw są wysyłane produkty o krótszym okresie trwałości.

## <a name="using-shelf-life-in-master-planning"></a>Używanie okresu trwałości w planowaniu głównym

W tej sekcji opisano sposób, w jaki planowanie główne sugeruje podaż towarów w przypadku pozycji z okresem trwałości.

Podczas uruchamiania planu głównego generowane są sugerowane zamówienia planowane (podaż), które będą realizować popyt, a także minimalizować opóźnienia. Jeśli plan obejmuje towary o ograniczonym okresie trwałości, obliczenia planowania stają się bardziej złożone, ponieważ plan musi nie tylko minimalizować opóźnienia, ale również korzystać z istniejącej podaży przed upływem okresu ważności. Plan musi użyć podaży najbliższej dacie ważności przed datą ważności dostaw, która wygaśnie później. Dlatego planowanie główne chce osiągnąć następujące cele w następującej kolejności:

1. Zminimalizować sumę opóźnień.
1. Zmaksymalizować sumę dostaw FEFO.
1. Zminimalizować uzupełnianie zapasów.

W niektórych przypadkach może wystąpić konflikt między pierwszymi dwoma celami i musi zostać dokonany wybór: czy chcesz opóźnić wysyłkę, czy chcesz użyć dostaw, których termin ważności wygaśnie później, zamiast dostawy, która wygaśnie wcześniej? Aby rozwiązać ten konflikt podczas planowania głównego, system określa priorytety zminimalizowanych opóźnień przy użyciu dostaw, których termin trwałości wkrótce upłynie. Na ogół ten typ konfliktu występuje, gdy mogą wystąpić opóźnienia i zapotrzebowanie w okresie. Dlatego zaleca się użycie okresu zapotrzebowania, który jest krótszy niż okres trwałości towaru. Inne typy zapotrzebowania (takie jak wymagania) mogą napotkać ten typ konfliktu.

## <a name="set-up-shelf-life"></a>Konfigurowanie okresu trwałości

### <a name="configure-each-master-plan-to-consider-shelf-life"></a>Skonfiguruj każdy plan główny, aby uwzględnić okres trwałości

Domyślnie w planach głównych nie są uwzględniany okres trwałości. Aby włączyć obliczanie okresu trwałości dla każdego wymaganego planu głównego, należy skorzystać z następującej procedury.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz albo istniejący plan główny w okienku listy, albo utwórz nowy.
1. Na skróconej karcie **Ogólne** ustaw opcję **Użyj dat okresu trwałości** na *Tak*.

### <a name="configure-tracking-dimension-groups-to-track-the-batch-dimension"></a>Konfigurowanie grup wymiarów śledzenia w celu śledzenia wymiarów partii

Okres trwałości towaru może być śledzony tylko wtedy, gdy jest on śledzony w wymiarze partii. Innymi słowy, odwołanie do partii oraz wymagane daty muszą być rejestrowane w momencie przyjęcia lub wyprodukowania oraz w każdej transakcji magazynowej dotyczącej towaru. Aby zarządzać tą opcją, należy skonfigurować jedną lub więcej grup wymiarów śledzenia, aby wykonać wymagane śledzenie, a następnie w razie potrzeby przypisać odpowiednie towary do tych grup.

Aby skonfigurować grupę wymiarów śledzenia do śledzenia wymiaru partii, należy skorzystać z następującej procedury.

1. Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Grupy wymiarów i wariantów \> Śledzenie grupy wymiarów**.
1. Wykonaj jeden z następujących kroków:

    - W okienku akcji wybierz opcję **Nowa**, aby utworzyć nową grupę wymiarów śledzenia. Wprowadź nazwę i opis, a następnie wybierz **Zapisz** w okienku akcji.
    - W okienku listy zaznacz istniejącą grupę wymiarów śledzenia, którą chcesz skonfigurować w celu śledzenia wymiaru partii.

1. Na skróconej karcie **Wymiaru śledzenia** w wierszu **Numer partii** zaznacz pola wyboru w kolumnach **Aktywne** i **Fizyczne zapasy**.

### <a name="set-up-shelf-life-for-a-product"></a>Konfigurowanie okresu trwałości produktu

Aby skonfigurować okres trwałości produktu, należy skorzystać z następującej procedury.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Utwórz lub otwórz produkt, który chcesz skonfigurować.
1. Aby użyć ustawień okresu trwałości, na skróconej karcie **Ogólne** ustaw w polu **Grupa wymiarów śledzenia** grupę wymiarów śledzenia, która jest ustawiona do śledzenia wymiaru partii. To pole można ustawić tylko podczas tworzenia produktu po raz pierwszy. Nie można zmienić wartości istniejących produktów.
1. Na skróconej karcie **Zarządzaj zapasami** ustaw następujące pola:

    - **Okres trwałości do spożycia w dniach** — umożliwia określenie okresu (w dniach), w którym ma być sprawdzana partia danego produktu w celu zapewnienia, że jest on odpowiedni do zużycia lub odsprzedaży. Wartość z pola jest dodawana do *daty produkcji partii* w celu określenia jej *daty trwałości partii*. System można skonfigurować w taki sposób, aby generował zlecenia kontroli jakości, gdy partia zbliża się do daty trwałości partii.
    - **Okres trwałości w dniach** — należy określić liczbę dni przed wygaśnięciem partii tego produktu. Ta wartość jest dodawana do *daty produkcji* w celu określenia *daty ważności*. Po tej dacie partia jest traktowana jako nienadatna do użytku.
    - **Okres ważności w dniach** — umożliwia określenie okresu (w dniach), po którym partia danego produktu jest uważana za wciąż do sprzedaży, ale nie może już zachować niektórych swoich pierwotnych właściwości. Ta wartość jest dodawana do *daty produkcji* w celu określenia *daty przydatności*. Raporty można uruchamiać w celu określenia zapasów, których data przydatności minęła. 

### <a name="set-a-sellable-days-rule-for-each-customer"></a>Ustaw regułę dni sprzedaży dla każdego odbiorcy

Funkcja *Dni sprzedaży* zapewnia, że produkty z partii, która wkrótce wygaśnie, nie będą wysyłane do odbiorców. Ponadto zapewnia, że po wysłaniu produktów do odbiorcy pozostanie odpowiednia liczba dni możliwej sprzedaży.

Aby korzystać z funkcji dni sprzedaży, należy określić liczbę dni sprzedaży, która dotyczy każdego produktu (lub grupy produktów) dla każdego odbiorcy. Ten proces należy wykonać ręcznie, ponieważ nie istnieje dla niego jednostka danych.

Aby skonfigurować dni sprzedaży dla każdego produktu dla każdego odbiorcy, należy skorzystać z następującej procedury.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odbiorcy \> Wszyscy odbiorcy**.
1. Znajdź i wybierz odbiorcę, którego chcesz skonfigurować.
1. W okienku akcji na karcie **Sprzedaj** w grupie **Konfiguracja** wybierz pozycję **Sprzedaj \> Dni sprzedaży**.
1. Na stronie **Dni sprzedaży dla odbiorców** w siatce są dostępne istniejące reguły dotyczące dni sprzedaży dla każdego produktu lub grupy produktów. W razie potrzeby za pomocą przycisków okienka akcji dodaj lub edytuj wiersze w siatce. Podano **Filtr**, który pomoże w odnalezieniu istniejących wierszy.
1. Dla każdego wiersza ustaw następujące pola:

    - **Kod pozycji** — wybierz jedną z następujących wartości, aby określić zakres pozycji, które będą miały wpływ:

        - *Tabela* — wiersz dotyczy określonego towaru.
        - *Grupa* – wiersz dotyczy tylko określonej grupy pozycji.
        - *Wszyscy* — wiersz dotyczy wszystkich pozycji.

    - **Relacja produktu** — wybierz konkretny element, jeśli w polu **Kod towaru** ustawisz wartość *Tabela*. Jeśli w polu **Kod towaru** wybrano opcję *Grupa*, należy wybrać grupę towarów. Jeśli ustawisz pole **Kod pozycji** na *Wszystko*, to pole jest niedostępne.
    - **Dni sprzedaży** — wprowadź minimalną liczbę dni, po upływie których klient musi sprzedać pasujące produkty, zanim upłynie termin ważności partii. Wartość dni możliwej sprzedaży jest oparta na żądanej dacie przyjęcia (lub potwierdzonej dacie przyjęcia, jeśli jest zdefiniowana) dla pasujących produktów na zamówieniu sprzedaży.
    - *(Inne wymiary produktu)* — aby dodatkowo ograniczyć zakres wiersza, należy określić w razie potrzeby inne wartości wymiarów (takie jak **Rozmiar** i **Kolor**). Aby kontrolować, które wymiary, które będą wyświetlane w siatce, wybierz **Wyświetl wymiary** na pasku akcji.

### <a name="set-up-all-relevant-products-so-that-they-are-fefo-date-controlled"></a>Skonfiguruj wszystkie odpowiednie produkty, aby były one kontrolowane przez datę FEFO

W przypadku dni sprzedaży do pracy każdy odpowiedni towar musi należeć do grupy modeli pozycji, w której jest zaznaczone pole wyboru **Kontrolowane przez datę FEFO**.

Aby skonfigurować grupę modeli pozycji, tak aby obsługiwała ona funkcje dni możliwej sprzedaży, należy skorzystać z następującej procedury.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zapasy \> Grupy modeli pozycji**.
1. Wybierz istniejącą grupę w okienku listy lub utwórz nową, wybierając opcję **Nowa** w okienku akcji.
1. Na skróconej karcie **Zasady zapasów** zaznacz pole wyboru **Zarządzanie przez datę FEFO**.
1. Ustaw pozostałe pola grupy zgodnie z wymaganiami.

Aby wyświetlić lub ustawić grupę modeli towaru, do której należy produkt, należy użyć następującej procedury.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Otwórz produkt, który chcesz sprawdzić lub edytować.
1. Na skróconej karcie **Ogólne** ustaw w polu **Grupa modeli pozycji** grupę, w której jest zaznaczone pole wyboru **Kontrolowane przez datę FEFO**.

## <a name="example-1-simple-fefo-10-day-period-zero-days-of-lead-time"></a>Przykład 1: proste FEFO, 10-dniowy okres, zero dni czasu realizacji

W tym przykładzie pokazano podstawowy przykład okresu trwałości, w którym oznaczanie zamówień podaży i popytu odbywa się w celu realizacji następujących celów systemu:

- Zminimalizować sumę opóźnień.
- Zmaksymalizować sumę dostaw FEFO.
- Zminimalizować uzupełnianie zapasów.

System ma następujące ustawienia pozycji i planu głównego:

- **Kod zapotrzebowania (strategia uzupełniania zapasów):** okres 
- **Okres zapotrzebowania:** 10 dni (równy okresowi trwałości)
- **Okres trwałości:** 10 dni
- **Dni możliwej sprzedaży:** 0 dni
- **Czas realizacji:** 0 dni
- **Ilość dni z ujemnym stanem magazynu:** 0 dni
- **Typ zamówienia planowanego (domyślne ustawienia zamówienia towaru):** zamówienie zakupu

W systemie istnieją następujące zamówienia sprzedaży towaru:

- **SO1:** ilość (il.) = 2, żądana data dostawy = dzisiaj + 1 dzień
- **SO2:** ilość = 1, żądana data dostawy = dzisiaj + 4 dni
- **SO3:** ilość = 1, żądana data dostawy = dzisiaj + 5 dni

Wszystkie te zamówienia sprzedaży tworzą popyt na pozycję.

Dla pozycji istnieje następująca dostawa:

- **Stan dostępnych zapasów:** ilość = 1, data ważności = dzisiaj + 5 dni
- **Zamówienie zakupu 1 (PO1):** data przyjęcia = dzisiaj + 2 dni, ilość = 1, data ważności = dzisiaj + 4 dni

System tworzy listę podaży, która może pokryć ten popyt, i sortuje listę według daty ważności (przy użyciu FEFO).

Planowanie główne tworzy wymagane oznaczanie popytu i podaży. Tworzy również każdy wymagany popyt na podstawie listy dostaw (przy użyciu FEFO) i z uwzględnieniem daty dostępności.

- Towar SO1 może być zrealizowany na podstawie ilości dostępnych zapasów, ale nie może zostać zrealizowany przez wiersz zamówienia zakupu 1, ponieważ data dostępności dla PO1 jest o jeden dzień późniejsza niż wymaga tego SO1. Z tego względu SO1 generuje popyt na jedną jednostkę towarów.
- SO2 może zostać pokryte PO1, ponieważ PO1 zostanie dostarczone do określonego czasu i data ważności będzie nadal ważna. Dlatego też wymaganie SO2 jest w pełni pokryte przez PO1.
- SO3 nie jest pokryte, ponieważ zasoby nie są dostępne. Z tego względu SO3 generuje popyt na jedną jednostkę towarów.

Aby pokryć wszystkie pozostałe wymagania, system musi utworzyć następujące planowane zamówienie zakupu:

- **PPO1:** data przyjęcia = dzisiaj, ilość = 2, data ważności = dzisiaj + 10 dni

W poniższej tabeli podsumowano wynik.

| Popyt | Oznaczanie transakcji |
|---|---|
| **SO1:** data dostawy = dzisiaj + 1 dzień, ilość = 2 | <p>**Dostępne zapasy:** ilość = 1, data ważności = dzisiaj + 5 dni</p><p>**PPO1:** data przyjęcia = dzisiaj, ilość = 1, data ważności = dzisiaj + 10 dni</p> |
| **SO2:** data dostawy = dzisiaj + 4 dni, ilość = 1 | **PO1:** data przyjęcia = dzisiaj + 2 dni, ilość 1, data ważności = dzisiaj + 4 dni |
| **SO3:** data dostawy = dzisiaj + 5 dni, ilość = 1 | **PPO1:** data przyjęcia = dzisiaj, ilość = 2, data ważności = dzisiaj + 10 dni |

Poniższa ilustracja przedstawia oś czasu w tym przykładzie.

![Przykład 1: proste FEFO, 10-dniowy okres, zero dni czasu realizacji.](media/fefo-example-1.png "Przykład 1: proste FEFO, 10-dniowy okres, zero dni czasu realizacji")

## <a name="example-2-simple-fefo-requirement-three-days-of-lead-time"></a>Przykład 2: proste FEFO, wymaganie, trzy dni czasu realizacji

W tym przykładzie pokazano, w jaki sposób próba zminimalizowania opóźnień w systemie może czasami spowodować nadmierne zamówienie.

System ma następujące ustawienia pozycji i planu głównego:

- **Kod zapotrzebowania (strategia uzupełniania zapasów):** wymaganie
- **Okres trwałości:** 10 dni
- **Dni możliwej sprzedaży:** 0 dni
- **Czas realizacji:** ustalony na podstawie następujących umów handlowych z dostawcą:

    - **Umowa handlowa 1:** jeśli ilość = 1, czas realizacji = 4
    - **Umowa handlowa 2:** jeśli ilość = 2, czas realizacji = 3

- **Ilość dni z ujemnym stanem magazynu:** 0 dni
- **Typ zamówienia planowanego (domyślne ustawienia zamówienia towaru):** zamówienie zakupu

Poniższe zamówienie sprzedaży istnieje w systemie:

- **SO1:** ilość = 2, żądana data dostawy = dzisiaj + 3 dni

Ten popyt jest pokrywany przez istniejącą podaż i potwierdzone zamówienie zakupu:

- **Stan dostępnych zapasów:** dostępne = dzisiaj, ilość = 1, data ważności = dzisiaj + 2 dni
- **PO1:** data przyjęcia = dzisiaj + 3 dni, ilość = 1, data ważności = dzisiaj + 4 dni

Nie można wypełnić stanu zapasów SO1, ponieważ data ważności zapasów jest wcześniejsza niż data wysyłki. PO1 może pokryć zapotrzebowanie z SO1 i ilość tylko 1. Z tego względu SO1 generuje popyt na jedną jednostkę towarów. Aby pokryć to zapotrzebowanie, system tworzy planowane zamówienie zakupu (PPO1).

System ma dwie umowy handlowe (jedna dla ilości = 1, czas realizacji = 4 dni, a jedna dla ilości = 2, czas realizacji = 3 dni). W związku z tym system próbuje zminimalizować opóźnienia, tworząc planowane zamówienie zakupu (PPO1) spełniającego drugą umowę handlową. W wyniku tego generuje się nadmiar dostawy (ilość = 2, data ważności = dzisiaj + 10 dni).

W poniższej tabeli podsumowano wynik.

| Popyt | Oznaczanie transakcji |
|---|---|
| **SO1:** data dostawy = dzisiaj + 3 dni, ilość = 2 | <p>**PO1:** data przyjęcia = dzisiaj + 3 dni, ilość = 1, data ważności = dzisiaj + 4 dni</p><p>**PPO1:** data przyjęcia = dzisiaj + 3 dni, ilość = 1, data ważności = dzisiaj + 10 dni</p> |

Poniższa ilustracja przedstawia oś czasu w tym przykładzie.

![Przykład 2: proste FEFO, wymaganie, trzy dni czasu realizacji.](media/fefo-example-2.png "Przykład 2: proste FEFO, wymaganie, trzy dni czasu realizacji")

## <a name="example-3-simple-fefo-requirement-three-days-of-lead-time-five-sellable-days"></a>Przykład 3: proste FEFO, wymaganie, trzy dni czasu realizacji, pięć dni przydatności do sprzedaży

W tym przykładzie pokazano, jak działa okres trwałości, gdy dla towaru są dodawane dni przydatności do sprzedaży.

System ma następujące ustawienia pozycji i planu głównego:

- **Kod zapotrzebowania (strategia uzupełniania zapasów):** wymaganie
- **Okres trwałości:** 10 dni
- **Dni możliwej sprzedaży:** 5 dni
- **Czas realizacji:** 5 dni
- **Ilość dni z ujemnym stanem magazynu:** 0 dni
- **Typ zamówienia planowanego (domyślne ustawienia zamówienia towaru):** zamówienie zakupu

Poniższe zamówienia sprzedaży istnieją w systemie:

- **SO1:** ilość = 2, żądana data dostawy = dzisiaj + 2 dni
- **SO2:** ilość = 1, żądana data dostawy = dzisiaj + 3 dni
- **SO3:** ilość = 1, żądana data dostawy = dzisiaj + 5 dni

Ten popyt może być pokrywane przez istniejącą podaż i potwierdzone zamówienie zakupu:

- **Stan dostępnych zapasów:** dostępne = dzisiaj, ilość = 1, data ważności = dzisiaj + 6 dni
- **PO1:** data przyjęcia = dzisiaj + 2 dni, ilość = 3, data ważności = dzisiaj + 10 dni

Na podstawie listy dostaw (FEFO) i dat dostępności system utworzy listę oznaczania kandydatów oznaczania transakcji. Z tego względu SO1 nie może być zrealizowane przez dostępne zapasy, ponieważ zapasy wygasają przed upływem dni do sprzedaży wymaganych przez klienta (żądana data przyjęcia + 5 dni). PO1 może pokryć zapotrzebowanie SO1 z dwiema jednostkami, a zapotrzebowanie SO2 z jedną jednostką. Dlatego tylko w przypadku SO3 wciąż pozostaje bez pokrycia popyt na jedną jednostkę towarów. Aby pokryć to zapotrzebowanie, system tworzy następujące planowane zamówienie zakupu:

- **PP01:** data przyjęcia = dzisiaj + 5 dni, ilość = 1, data ważności = dzisiaj + 10 dni

W poniższej tabeli podsumowano wynik.

| Popyt | Oznaczanie transakcji |
|---|---|
| **SO1:** data dostawy = dzisiaj + 2 dni, ilość = 2 | **PO1:** data przyjęcia = dzisiaj + 2 dni, ilość = 2, data ważności = dzisiaj + 10 dni |
| **SO2:** data dostawy = dzisiaj + 3 dni, ilość = 1 | **PO1:** data przyjęcia = dzisiaj + 2 dni, ilość = 1, data ważności = dzisiaj + 10 dni |
| **SO3:** data dostawy = dzisiaj + 5 dni, ilość = 1 | **PPO1:** data przyjęcia = dzisiaj + 5 dni, ilość = 1, data ważności = dzisiaj + 10 dni |

Poniższa ilustracja przedstawia oś czasu w tym przykładzie.

![Przykład 3: proste FEFO, wymaganie, trzy dni czasu realizacji, pięć dni przydatności do sprzedaży.](media/fefo-example-3.png "Przykład 3: proste FEFO, wymaganie, trzy dni czasu realizacji, pięć dni przydatności do sprzedaży")

## <a name="example-4-simple-fefo-period-lead-time-depends-on-the-quantity"></a>Przykład 4: proste FEFO, okres, czas realizacji zależy od ilości

W tym przykładzie pokazano, w jaki sposób próba zminimalizowania opóźnień w systemie może czasami spowodować nadmierne zamówienie.

System ma następujące ustawienia pozycji i planu głównego:

- **Kod zapotrzebowania (strategia uzupełniania zapasów):** okres
- **Okres zapotrzebowania:** 10 dni (równy okresowi trwałości)
- **Okres trwałości:** 10 dni
- **Dni możliwej sprzedaży:** 0 dni
- **Czas realizacji:** ustalony na podstawie następujących umów handlowych z dostawcą:

    - **Umowa handlowa 1:** jeśli ilość = 1, czas realizacji = 5
    - **Umowa handlowa 2:** jeśli ilość = 2, czas realizacji = 0

- **Ilość dni z ujemnym stanem magazynu:** 0 dni
- **Typ zamówienia planowanego (domyślne ustawienia zamówienia towaru):** zamówienie zakupu

Poniższe zamówienia sprzedaży istnieją w systemie:

- **SO1:** ilość = 1, żądana data dostawy = dzisiaj
- **SO2:** ilość = 1, żądana data dostawy = dzisiaj + 6 dni

Ten popyt może być częściowo pokrywany przez istniejącą podaż z następujących potwierdzonych zamówień zakupu:

- **PO1:** data przyjęcia = dzisiaj + 1 dni, ilość = 1, data ważności = dzisiaj + 2 dni
- **PO2:** data przyjęcia = dzisiaj + 3 dni, ilość = 1, data ważności = dzisiaj + 7 dni

System ma dwie umowy handlowe (jedna dla ilości = 1, czas realizacji = 5 dni, a jedna dla ilości = 2, czas realizacji = 0 dni). W związku z tym system próbuje zminimalizować opóźnienie, tworząc następujące planowane zamówienie zakupu spełniającego drugą umowę handlową:

- **PP01:** data przyjęcia = dzisiaj, ilość = 2, data ważności = dzisiaj + 10 dni

O1 zostanie pokryte przez jedną jednostkę z PPO1. SO2 zostanie objęte PO2, ponieważ PO2 wygasa szybciej niż PPO1.

W poniższej tabeli podsumowano wynik.

| Popyt | Oznaczanie transakcji |
|---|---|
| **SO1:** data dostawy = dzisiaj, ilość = 1 | **PPO1:** data przyjęcia = dzisiaj, ilość = 1, data ważności = dzisiaj + 10 dni |
| **SO2:** data dostawy = dzisiaj + 6 dni, ilość = 1 | **PO2:** data przyjęcia = dzisiaj + 3 dni, ilość = 1, data ważności = dzisiaj + 7 dni |

> [!NOTE]
> Nie jest używane PO1, ponieważ przybędzie za późno dla S01 i wygaśnie przed dostawą S02. PPO1 zostało zamówione za pośrednictwem jednej jednostki, co umożliwia ustawienie czasu realizacji na poziomie 0 (zero) na umowę handlową 2.

Poniższa ilustracja przedstawia oś czasu w tym przykładzie.

![Przykład 4: proste FEFO, okres, czas realizacji zależy od ilości.](media/fefo-example-4.png "Przykład 4: proste FEFO, okres, czas realizacji zależy od ilości")

## <a name="example-5-simple-fefo-requirement-10-negative-days"></a>Przykład 5: proste FEFO, zapotrzebowanie, 10 ujemnych dni

<!-- KFM: This is more of a negative days example than a shelf life example. We should point out more explicitly how shelf life affects this situation (or maybe otherwise remove this example). -->

W tym przykładzie pokazano, jak działa okres trwałości, gdy dla towaru jest dodawana dużą liczna dni ujemnych. Liczba w dniach ujemnych reprezentuje liczbę dni, po upływie których użytkownik chce zamówić nowe uzupełnienie zapasów w przypadku ujemnego stanu zapasów tego towaru. System nie utworzy dostaw, dopóki nie zostanie przekroczona liczba dni z ujemnym poziomem zapasów.

System ma następujące ustawienia pozycji i planu głównego:

- **Kod zapotrzebowania (strategia uzupełniania zapasów):** wymaganie
- **Czas realizacji:** 0 dni
- **Ilość dni z ujemnym stanem magazynu:** 10 dni
- **Typ zamówienia planowanego (domyślne ustawienia zamówienia towaru):** zamówienie zakupu

Poniższe zamówienie sprzedaży istnieje w systemie:

- **SO1:** ilość = 1, żądana data dostawy = dzisiaj

Ten popyt może być częściowo pokrywany przez istniejącą podaż z następującego potwierdzonego zamówienia zakupu:

- **PO1:** data przyjęcia = dzisiaj + 3 dni, ilość = 1, data ważności = dzisiaj + 5 dni

Ponieważ system jest skonfigurowany do zezwalania na 10 dni z ujemnym stanem magazynu, pokrywa popyt SP1 przy użyciu pola PO1, nawet jeśli wynik będzie opóźniony o trzy dni, ponieważ SO1 tworzy ujemne zapasy, dopóki nie pojawi się PO1. Żadne planowane zamówienie zakupu nie jest tworzone, nawet jeśli czas realizacji wynosi 0 (zero) i utworzenie nowego planowanego zamówienia zakupu zmniejszy opóźnienia.

W poniższej tabeli podsumowano wynik.

| Popyt | Oznaczanie transakcji |
|---|---|
| **SO1:** data dostawy = dzisiaj, ilość = 1 | **PO1:** data przyjęcia = dzisiaj + 3 dni, ilość = 1, data ważności = dzisiaj + 5 dni |

Poniższa ilustracja przedstawia oś czasu w tym przykładzie.

![Przykład 5: proste FEFO, zapotrzebowanie, 10 ujemnych dni.](media/fefo-example-5.png "Przykład 5: proste FEFO, zapotrzebowanie, 10 ujemnych dni")

## <a name="example-6-simple-fefo-requirement-five-negative-days"></a>Przykład 6: proste FEFO, zapotrzebowanie, pięć ujemnych dni

W tym przykładzie pokazano, jak działa okres trwałości, gdy liczba dni ujemnych dla pozycji jest mniejsza niż okres trwałości.

System ma następujące ustawienia pozycji i planu głównego:

- **Kod zapotrzebowania (strategia uzupełniania zapasów):** wymaganie
- **Dni możliwej sprzedaży:** 0 dni
- **Czas realizacji:** 0 dni
- **Ilość dni z ujemnym stanem magazynu:** 5 dni
- **Typ zamówienia planowanego (domyślne ustawienia zamówienia towaru):** zamówienie zakupu

Poniższe zamówienie sprzedaży istnieje w systemie:

- **SO1:** ilość = 2, żądana data dostawy = dzisiaj

Ten popyt może być częściowo pokrywany przez istniejącą podaż z następujących potwierdzonych zamówień zakupu:

- **PO1:** data przyjęcia = dzisiaj, ilość = 1, data ważności = dzisiaj + 1 dzień
- **PO2:** data przyjęcia = dzisiaj + 2 dni, ilość = 1, data ważności = dzisiaj + 3 dni

Jednak system musi przestrzegać ograniczeń, że wysłane towary nie mogą utracić ważności w momencie wysyłki. Z tego względu nie można używać jednocześnie PO2 i PO1 w związku z SO1, ponieważ PO1 wygasa przed upływem terminu w PO2. Aby zakończyć pokrycie zapotrzebowania dla SO1, system tworzy następujące planowane zamówienie zakupu:

- **PPO1:** data przyjęcia = dzisiaj, ilość = 1, data ważności = dzisiaj + 10 dni

System może korzystać z pięciu ujemnych dni i używać PO2 i PPO1 do pokrycia SO1. Jednak ta metoda spowoduje opóźnienie dostawy, dopóki nie nadejdzie realizacja zamówienia PO2, a w międzyczasie wygaśnie PO1. Dlatego system pokrywa SO1 przy użyciu PPO1 i PO1.

W poniższej tabeli podsumowano wynik.

| Popyt | Oznaczanie transakcji |
|---|---|
| **SO1:** data dostawy = dzisiaj, ilość = 2 | <p>**PO1:** data przyjęcia = dzisiaj, ilość = 1, data ważności = dzisiaj + 1 dzień</p><p>**PPO1:** data przyjęcia = dzisiaj, ilość = 1, data ważności = dzisiaj + 10 dni</p> |

Poniższa ilustracja przedstawia oś czasu w tym przykładzie.

![Przykład 6: proste FEFO, zapotrzebowanie, pięć ujemnych dni.](media/fefo-example-6.png "Przykład 6: proste FEFO, zapotrzebowanie, pięć ujemnych dni")
