---
title: Harmonogram prac sterowany przez system
description: Ten temat zawiera informacje dotyczące harmonogramu prac sterowanego przez system. Ta funkcja umożliwia sortowanie i filtrowanie zleceń roboczych przedstawianych przez system użytkownikom w celu wykonania. Jest to przydatne w sytuacjach, w których dodatkowe kryteria są wymagane do kierowania procesu pobierania z magazynu.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 3811486a31d079cac7f7c27ea6323f16de4478d5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970213"
---
# <a name="system-directed-work-sequencing"></a>Harmonogram prac sterowany przez system

[!include [banner](../includes/banner.md)]

Funkcja harmonogramu prac sterowanego przez system umożliwia sortowanie i filtrowanie zleceń roboczych przedstawianych przez system użytkownikom w celu wykonania. Jest to przydatne w sytuacjach, w których dodatkowe kryteria (takie jak czas wysyłki, strefa pobrania, profil lokalizacji lub kombinacja różnych kryteriów) są wymagane do kierowania procesem pobierania magazynowego.

Ta funkcja rozszerza bieżącą funkcję pobierania sterowanego przez system o nową opcję, Sterowane przez system porządkowanie według, dzięki której użytkownik może skonfigurować sekwencję oraz zapytanie lub wiele zapytań, które będą oceniać wszystkie utworzone zlecenia pracy. Zostaną przechwycone i przedstawione tylko te zlecenia pracy, które spełniają kryteria określone w konfiguracji elementu menu urządzenia przenośnego.

Ta funkcja pozwala na dalszą optymalizację procesów pobierania magazynowego, ponieważ identyfikuje zlecenia pracy spełniające określone kryteria, przypisuje je do poprawnego elementu menu urządzenia przenośnego, a następnie przedstawia je pracownikowi na podstawie określonego zestawu umiejętności, sprzętu pobrania lub innego zapotrzebowania.

> [!NOTE]
> Jeśli są potrzebne jest zastosowanie innych kryteriów, należy użyć wielu elementów menu urządzeń przenośnych.

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a>Należy włączyć funkcję harmonogramu prac sterowanego przez system obowiązującego dla całej organizacji

Aby można było korzystać z funkcji harmonogramu pracy kierowanej przez system, funkcja ta musi być włączona w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Harmonogram prac sterowany przez system obowiązujący dla całej organizacji*

## <a name="setup"></a>Konfiguracja

### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

Aby przejść przez ten scenariusz przy użyciu określonych przykładowych rekordów i wartości zaprezentowanych w tym temacie, należy korzystać z systemu, w którym są zainstalowane standardowe dane demonstracyjne. Ponadto należy wybrać firmę **USMF**. Scenariusz korzysta z magazynu *51* znajdującego się w danych demonstracyjnych.

> [!IMPORTANT]
> Przed zwolnieniem zleceń do magazynu należy upewnić się, że lokalizacje pobrania mają wystarczającą ilość zapasów dla wszystkich pozycji na wszystkich zamówieniach.
>
> W tym scenariuszu powinny być obsługiwane dane domyślne USMF. Jeśli nie korzystasz z danych demonstracyjnych, przejrzyj ustawienie **Dyrektywa lokalizacji**, aby dowiedzieć się, które lokalizacje pobrania są używane do pobrania zamówienia sprzedaży. Jeśli konieczne jest skorygowanie zapasów, można ręcznie tworzyć zmiany, skorzystać z uzupełnienia lub skorzystać z dowolnego innego przepływu.

### <a name="set-up-a-mobile-device-menu-item"></a>Konfigurowanie elementu menu urządzenia przenośnego

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Na liście elementów menu w urządzeniu przenośnym wybierz opcję **Pobieranie sprzedaży – system**. Wymagany element menu już istnieje. 
1. Potwierdź następujące ustawienia:

    - Na skróconej karcie **Ogólne**, pole **Sterowane przez** powinno być ustawione na wartość *Sterowane przez system*.
    - Skrócona karta **Klasy robocze** powinny zawierać następujące ustawienia.

        | Identyfikator klasy roboczej | Typ zlecenia |
        |---|---|
        | Sprzedaż | Zamówienia sprzedaży |
        | Pobranie zamówienia sprzedaży | Zamówienia sprzedaży |

1. W okienku akcji wybierz opcję **Systemowe zapytania dotyczące sekwencji pracy**.
1. Wybierz opcję **Edycja**.
1. Usuń istniejący wiersz, a następnie potwierdź akcję, wybierając **Tak**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć wiersz.
1. W nowym wierszu ustaw następujące wartości:

    - **Numer sekwencyjny:** *1*
    - **Pole opis:** *Ilość pracy mniejsza niż 20 i spada*

1. Wybierz opcję **Zapisz**.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. Na karcie **Sprzężenia** rozwiń hierarchię sprzężeń, aby wyświetlić tabelę **Wiersze pracy**.
1. Wybierz sprzężenie tabeli **Wiersze pracy**.
1. Wybierz pozycję **Dodaj sprzężenie tabeli**.
1. Z wyświetlonej listy znajdź i zaznacz wiersz, który ma następujące ustawienia:

    - **Tryb sprzężenia:** *n:1*
    - **Relacja:** *Lokalizacje (lokalizacja)*

1. Wybierz pozycję **Wybierz**.

    Do tabeli sprzężenia dodawane są lokalizacje.

1. Na karcie **Sortowanie** wybierz opcję **Dodaj**, aby dodać wiersz.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Ilość pracy* (w wyświetlonym oknie komunikatu wybierz opcję **Tak**, aby dodać funkcję sortowania do tego pola).
    - **Kierunek sortowania:** *Malejąco*

1. Kliknij kartę **Zakres**.

    Jeśli w sekwencjonowaniu powinny być uwzględnione tylko określone kryteria pracy, można je określić korzystając z karty **Zakres**. W tym przykładzie należy skorzystać z zadań, w których ilość jest mniejsza niż 20 ea (najniższa jednostka miary).

    Zauważ, że niektóre wiersze są już uwzględnione. Tych wierszy nie należy usuwać.

1. Wybierz pozycję **Dodaj**, aby dodać drugi wiersz.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Ilość pracy w magazynie*
    - **Kryteria:** *\<20* (mniej niż 20)

1. Wybierz pozycję **Dodaj**, aby dodać kolejny wiersz.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Wiersze pracy*
    - **Tabela pochodna:** *Wiersze pracy*
    - **Pole:** *Typ pracy*
    - **Kryteria:** *Pobranie*

1. Wybierz pozycję **Dodaj**, aby dodać kolejny wiersz.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Lokalizacje*
    - **Tabela pochodna:** *Lokalizacje*
    - **Pole:** *Identyfikator profilu lokalizacji*
    - **Kryteria:** *!STAGE*

        > [!IMPORTANT]
        > Pamiętaj, aby umieścić wykrzyknik (*!*) przed *ETAP*.

1. Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć je.
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę, aby powrócić do strony **Elementy menu urządzenia przenośnego**.

> [!NOTE]
> Ta konfiguracja definiuje kryteria, które będą używane w celu podawania kwalifikujących się elementów pracy do elementu menu urządzenia przenośnego. Jeśli do zapytania zostanie dodanych kilka wierszy kryteriów, system najpierw użyje tego wiersza zapytania, który ma najniższy numer sekwencyjny. Innymi słowy, wszystkie zakwalifikowane elementy z harmonogramu nr 1 zostaną przedstawione użytkownikowi jako pierwsze, a następnie procedura zostanie powtórzona dla harmonogramu o numerze 2. Jeśli muszą zostać zastosowane razem określony zakres i sortowani, należy je określić w tym samym zapytaniu harmonogramu prac sterowanym przez system.
>
> Ta konfiguracja spowoduje przechwycenie elementu pracy, który ma co najmniej jeden wiersz o ilości mniejszej niż 20 ea. Dlatego jeśli w elemencie pracy znajduje się wiersz, w którym ilość wynosi dokładnie 20 lub więcej niż 20 ea, będzie uznany za prawidłowy, pod warunkiem, że ma co najmniej jeden wiersz, w którym ilość jest mniejsza niż 20 ea.

### <a name="location-directives"></a>Dyrektywy lokalizacji

Jeśli są używane domyślne dane firmy Contoso, w zapytaniu dot. dyrektywy lokalizacji nie są wymagane żadne zmiany. Aby jednak upewnić się, że w dyrektywach lokalizacji są przechwytywane towary znajdujące się w zamówieniach sprzedaży, po zastosowaniu tej funkcji w środowisku firmy innej niż Contoso, należy utworzyć nową dyrektywę lokalizacji. Aby sprawdzić ustawienia w środowisku demonstracyjnym, wykonaj następujące kroki.

1. Przejdź kolejno do pozycji **Zarządzanie magazynem** \> **Ustawienia** \> **Dyrektywy lokalizacji**.
1. W polu **Typ zlecenia pracy** wybierz opcję *Zamówienia sprzedaży*.
1. Wybierz dyrektywę lokalizacji o nazwie *Pobranie 51*.
1. Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz wiersz dla akcji **Pobrania**.
1. Wybierz opcję **Edytuj zapytanie** znajdującą się powyżej siatki.
1. Przejrzyj zapytanie **Zakres**.

    1. Znajdź wiersz, w którym pole o nazwie **Pole** ma wartość *Lokalizacja*.
    2. Upewnij się, że pole **Kryteria** jest puste (to znaczy, że nie ma wybranych żadnych ograniczeń).

## <a name="scenario"></a>Scenariusz

### <a name="create-sales-order-picking-work"></a>Tworzenie zlecenia pracy dot. pobierania zamówienia sprzedaży

Przed uruchomieniem pobierania kierowanego przez system powinny zostać utworzone niektóre prace wychodzące. W tym scenariuszu zostaną utworzone cztery zamówienia sprzedaży oparte na określonych zapytaniach systemowych dot. sekwencji pracy.

Ilości zapasów dla każdego zamówienia sprzedaży zostaną rezerwowane. Oznacza to, że zarezerwowane zapasy nie mogą być wycofywane z magazynu dla innych zamówień, chyba że rezerwacja lub część rezerwacji zostanie anulowana.

Następnie należy zwolnić poszczególne zamówienia sprzedaży do magazynu w celu utworzenia pracy wychodzącej.

#### <a name="sales-order-1"></a>Zamówienie sprzedaży 1

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć zamówienie sprzedaży 1.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - W sekcji **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-004*.
    - W sekcji **Ogólne** w polu **Magazyn** wybierz wartość *51*.

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe. Zanotuj numer zamówienia sprzedaży.
1. Dodaj wiersz do nowego zamówienia sprzedaży i określ następujące wartości:

    - **Numer pozycji:** *M9200*
    - **Ilość:** *20*

1. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja** wybierz **Rezerwacja partii** w celu zarezerwowania zapasów.
1. Zamknij stronę **Rezerwacja**.
1. W okienku akcji na karcie **Magazyn** wybierz pozycję Akcje **Zwolnij do magazynu**, aby utworzyć zlecenie pracy dla magazynu.

    Użytkownik otrzymuje komunikaty informacyjne, które zawierają identyfikator grupy czynności oraz identyfikatory wysyłki utworzone dla zamówienia sprzedaży.

#### <a name="sales-order-2"></a>Zamówienie sprzedaży 2

1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć zamówienie sprzedaży 2.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-007*
    - **Magazyn:** *51*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe. Zanotuj numer zamówienia sprzedaży.
1. Dodaj wiersz do nowego zamówienia sprzedaży i określ następujące wartości:

    - **Numer pozycji:** *M9200*
    - **Ilość:** *5*

1. Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:

    - **Numer pozycji:** *M9201*
    - **Ilość:** *1*

1. Zarezerwuj zapasy dla obu wierszy.
1. Zwolnij zamówienie do magazynu.

#### <a name="sales-order-3"></a>Zamówienie sprzedaży 3

1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć zamówienie sprzedaży 3.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-009*
    - **Magazyn:** *51*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe. Zanotuj numer zamówienia sprzedaży.
1. Dodaj wiersz do nowego zamówienia sprzedaży i określ następujące wartości:

    - **Numer pozycji:** *M9200*
    - **Ilość:** *7*

1. Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:

    - **Numer pozycji:** *M9202*
    - **Ilość:** *8*

1. Zarezerwuj zapasy dla obu wierszy.
1. Zwolnij zamówienie do magazynu.

#### <a name="sales-order-4"></a>Zamówienie sprzedaży 4

1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć zamówienie sprzedaży 4.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-010*
    - **Magazyn:** *51*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe. Zanotuj numer zamówienia sprzedaży.
1. Dodaj wiersz do nowego zamówienia sprzedaży i określ następujące wartości:

    - **Numer pozycji:** *M9200*
    - **Ilość:** *25*

1. Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:

    - **Numer pozycji:** *M9202*
    - **Ilość:** *10*

1. Zarezerwuj zapasy dla obu wierszy.
1. Zwolnij zamówienie do magazynu.

### <a name="get-work-ids-for-the-work-that-was-created"></a>Pobierz identyfikatory pracy dla utworzonej pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. Odfiltruj dane w polu **Magazyn**, aby wyświetlić tylko pracę dla magazynu *51*.
1. Powinny być wyświetlone cztery identyfikatory pracy. Zapisz identyfikatory pracy dla każdego zamówienia sprzedaży.

    | Identyfikator zamówienia sprzedaży | Identyfikator pracy | Ilość pracy |
    |---|---|---|
    | Zamówienie sprzedaży 1 | Identyfikator pracy 1 | 20 każdy |
    | Zamówienie sprzedaży 2 | Identyfikator pracy 2 | 6 każdy (suma obu wierszy) |
    | Zamówienie sprzedaży 3 | Identyfikator pracy 3 | 15 każdy (suma obu wierszy) |
    | Zamówienie sprzedaży 4 | Identyfikator pracy 4 | 35 każdy (suma obu wierszy) |

Przed uruchomieniem przepływu na urządzeniu przenośnym należy upewnić się, że tylko utworzone zadanie ma stan *Otwarte* dla magazynu *51*, oraz że ma nadany typ pracy *Zamówienie sprzedaży*. W przeciwnym razie wyniki testu mogą się różnić, ponieważ Pobieranie bezpośrednie przez system będzie obejmowało całą kwalifikującą się pracę.

1. Przejdź do **Zarządzanie magazynem \> Praca \> Wychodzące \> Otwarte zlecenia pracy sprzedażowej**.
1. W siatce **Otwarte zlecenia pracy sprzedażowej** odfiltruj wartości w polu **Magazyn**, aby widoczna była tylko praca dla magazynu *51*.
1. Upewnij się, że zostały wyświetlone tylko cztery identyfikatory pracy, które zostały wcześniej utworzone.
1. Zamknij stronę **Praca**.

### <a name="mobile-device-flow-execution"></a>Wykonanie przepływu na urządzeniu przenośnym

Na podstawie ustawień system będzie przesyłać użytkownikowi informacje o pracy, która jest posortowana od najwyższej ilości w wierszu pracy do najniższej. Ilość w każdym wierszu będzie mniejsza niż 20 ea.

Należy pamiętać, że ta konfiguracja spowoduje przechwycenie elementu pracy, który ma co najmniej jeden wiersz o ilości mniejszej niż 20 ea. Jeśli więc praca ma inny wiersz, w którym ilość wynosi dokładnie 20 ea lub więcej, będzie ona również uznana za prawidłową.

#### <a name="mobile-app"></a>Aplikacja mobilna

1. Zaloguj się do aplikacji magazynowania jako użytkownik w magazynie *51*.
1. Przejdź do **Wychodzące \> Pobieranie sprzedaży – system**.

    Przedstawiony jest krok pobrania dla identyfikatora pracy o numerze *4*. Ten identyfikator pracy jest przedstawiany jako pierwszy z powodu korzystania z konfiguracji zapytań sterowanych przez system, w której określono, że praca powinna być sekwencjonowana na podstawie ilości w wierszu pracy – malejąco.

1. Zakończ wymagane pobranie i zamknij dany identyfikator pracy.

    Następnie prezentowany jest identyfikator pracy *3*. Jeden ze znajdujących się w nim wierszy jest wybrany jako następny w sekwencji na podstawie ilości w wierszu pracy.

1. Zakończ pobranie i zamknij dany identyfikator pracy.

    Następnie prezentowany jest identyfikator pracy *2*. Wiersz pobrania tego działania jest następny w sekwencji.

1. Zakończ pobranie i zamknij dany identyfikator pracy.

    Żadne więcej zlecenia pracy nie powinny być wyświetlane użytkownikowi. Identyfikator pracy *1* nie kwalifikuje się do tego elementu menu urządzenia przenośnego, ponieważ zapytanie określa, że nagłówki pracy są uwzględniane tylko wtedy, gdy ilość w wierszach pracy ma wartość mniejszą niż 20 ea.

## <a name="tips"></a>Porady

Zapytanie dotyczące sekwencji pracy sterowanej przez system ma wartość *zawierająca*. Ważne jest, aby pamiętać o tym fakcie w przypadku niektórych konfiguracji. Można na przykład określić, że określony element menu ma przetwarzać tylko pracę, w której jednostka pracy ma wartość *ea* – ograniczenie to jest określane na karcie **Zakres** w zapytaniu. W tym przypadku wszystkie elementy pracy, w której co najmniej jeden wiersz pracy ma ustawioną jednostkę roboczą na wartość *ea* zostanie przekazana pracownikowi. Dlatego to zadanie może również obejmować pracę, w której wiersze pracy mają jednostkę roboczą inną niż *ea* (np *pudełko* lub *paleta*). Zapytanie wykluczy tylko te elementy, w których żaden wiersz pracy nie ma jednostki roboczej ustawionej na wartość *ea*.

Dlatego w przykładzie z tego scenariusza identyfikator pracy *4* również został wyświetlony w ramach zapytania. Po jego utworzeniu dodano dwa wiersze: jeden dla 25 ea, a drugi dla 10 ea. Praca została przekazana użytkownikowi, ponieważ co najmniej jeden wiersz pracy miał ilość mniejszą niż 20 ea.

W zależności od scenariusza można uniknąć takiego zachowania, korzystając z podziału pracy.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]