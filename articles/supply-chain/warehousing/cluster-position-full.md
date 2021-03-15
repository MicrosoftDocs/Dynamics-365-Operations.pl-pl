---
title: Stanowisko w grupie pełne
description: Ten temat zawiera informacje dotyczące funkcji Stanowisko w grupie pełne. Ta funkcja oferuje alternatywę dla sztywnego egzekwowania reguł przerwy w pracy, gdy jest używana funkcja pobierania dla grupy. Zezwala ona na większy margines błędu w ramach ograniczeń dotyczących objętości kontenerów lub pojemników.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9c90380cb5d109e331a2552ba779525b66d10fa6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001106"
---
# <a name="cluster-position-full"></a>Stanowisko w grupie pełne

[!include [banner](../includes/banner.md)]

Funkcja *Stanowisko w grupie pełne* oferuje alternatywę dla sztywnego egzekwowania reguł przerwy w pracy, gdy jest używana funkcja pobierania dla grupy. Zezwala ona na większy margines błędu w ramach ograniczeń dotyczących objętości kontenerów lub pojemników. W typowym przebiegu pracy nie wszystkie towary w zleceniu pracy mieszczą się w wybranym kontenerze. Pracownicy magazynowi, którzy pobierają z grupy, mają w takiej sytuacji tylko kilka opcji: muszą zmienić rozmiar kontenera na większy lub porozmawiać z przełożonym w i znaleźć jakieś inne rozwiązanie.

Ta funkcja wprowadza możliwość skorzystania z przycisku **Pełne** przy jednej z jednostek pracy w grupie. W starszych wersjach ta opcja była dostępna tylko w przypadku pobierania zamówienia zwykłego, a nie w przypadku pobierania z grupy. Jednak ta funkcja różni się od standardowego przycisku **Pełne**, gdyż anuluje pozostałą pracę. Nie sugeruje to użytkownikowi dodaia kolejnego pojemnika do tego samego klastra i nie powoduje automatycznego utworzenia nowej pracy.

## <a name="turn-on-the-cluster-position-full-feature"></a>Włącz funkcję „Stanowisko w grupie pełne”

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Stanowisko w grupie pełne*

## <a name="setup"></a>Konfiguracja

W tej sekcji znajdują się wskazówki i sposób konfigurowania i używania funkcji *Stanowisko w grupie pełne*.

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tymi [przykładowymi scenariuszami](#example-scenario) przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

Tego scenariusza przykładowego można również używać jako wskazówek podczas używania danej funkcji w produkcji. Jednak w takim przypadku należy podstawić własne wartości dla ustawień opisanych w tym polu.

### <a name="cluster-profiles"></a>Profile grup

Należy określić, czy identyfikatory grupy są generowane automatycznie, jaka jest liczba stanowisk, kiedy grupy są przerywane oraz jak wygląda sekwencja i weryfikacja pracy pobierania.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Profile grup**.
1. W okienku listy wybierz opcję rekord **Utwórz grupę**.
1. Na skróconej karcie **Ogólne** zweryfikuj następujące wartości:

    - **Generuj identyfikator grupy:** — wybierz opcję *Tak*
    - **Aktywuj stanowiska:** *Tak*
    - **Liczba stanowisk:** *2*
    - **Nazwa stanowiska:** *Numeryczne*
    - **Podziel grupę w:** — wybierz pozycję *Odłożenie*.
    - **Typ weryfikacji sortowania:** *Skan pozycji*

1. Na skróconej karcie **Sortowanie grupy**. Siatka powinna być pusta (czyli nie powinna zawierać żadnych wierszy).

### <a name="work-templates"></a>Szablony pracy

Należy określić sposób tworzenia pracy pobierania dla pobierania dla grup.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. U góry strony, w polu **Typ zlecenia produkcyjnego** ustaw wartość *Zamówienia sprzedaży*.
1. Upewnij się, że spośród danych demonstracyjnych są wymienione następujące szablony pracy. Jeśli nie są one dostępne, nie można ukończyć tego scenariusza.

    - 61 Zamówienie sprzedaży — etap
    - 61 Zamówienie sprzedaży — pobranie z grupy

### <a name="location-directives"></a>Dyrektywy lokalizacji

Należy określić, skąd towary są pobierane i gdzie są umieszczane.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W nagłówku listy w polu **Typ zlecenia pracy** zaznacz opcję *Zamówienia sprzedaży*.
1. Upewnij się, że spośród danych demonstracyjnych są wymienione następujące dyrektywy zamówień sprzedaży. Jeśli nie są one dostępne, nie można ukończyć tego scenariusza.

    - 61 pobranie z grupy
    - 61 Zamówienie sprzedaży — pobranie zamówienia

### <a name="mobile-device-menu-items"></a>Elementy menu urządzenia przenośnego

Należy skonfigurować menu urządzenia przenośnego do wykorzystania istniejącej pracy, która jest sterowana przez pobieranie dla grup. W elemencie menu urządzenia przenośnego do pobierania grupy musi być włączona opcja **Zezwalaj na dzielenie pracy** oraz musi być dodana klasa pracy *Zamówienia sprzedaży*.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku listy wybierz rekord **Utwórz pobieranie dla grupy**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Zarządzane przez:** *Pobieranie dla grupy*
    - **Generuj numer identyfikacyjny:** *Tak*
    - **Zezwalaj na dzielenie pracy:** *Tak*
    - **Identyfikator profilu grupy:** *Utwórz grupę*

    Zaakceptuj wartość domyślną we wszystkich pozostałych polach.

1. W przypadku skróconej karty **Klasa pracy**, w razie potrzeby dodaj następujące dwa wiersze:

    - Wiersz 1 (zwykle obecny w danych demonstracyjnych):

        - **Identyfikator klasy roboczej:** *Sprzedaż* 
        - **Typ zamówienia pracy:** *zamówienia sprzedaży*

    - Wiersz 2 (zwykle nieobecny w danych demonstracyjnych):

        - **Identyfikator klasy roboczej:** *Pobranie zamówienia sprzedaży*
        - **Typ zamówienia pracy:** *zamówienia sprzedaży*

1. Przejdź do **Ustawień potwierdzenia pracy** w okienku akcji.
1. Wybierz opcję **Edycja**.
1. Wprowadź jedną z następujących wartości w wierszu na siatce.
    - **Typ pracy** - *Pobranie*
    - **Potwierdzenie produktu** - *Zaznacz pole wyboru*

1. Wybierz **Zapisz** w okienku akcji i zamknij stronę.

## <a name="create-picking-work"></a>Tworzenie pracy pobrania

Aby można było uruchomić pobieranie z grupy, należy utworzyć kilka prac wychodzących. Utworzony wcześniej profil grupy określa dwie pozycje grupy. Dla pobrania zamówienia sprzedaży trzeba utworzyć co najmniej dwa identyfikatory robocze. W tym scenariuszu transakcje będą mieć miejsce w magazynie *61* i będą korzystały z towarów *L0101* i *T0100*. Dane demonstracyjne powinny zawierać wystarczająco dużo dostępnych zapasów tych towarów. Upewnij się, że masz wystarczające zapasy do ukończenia transakcji.

### <a name="create-sales-order-1"></a>Utwórz zamówienie sprzedaży 1

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży 1.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-010*
    - **Magazyn:** *61*

1. Kliknij przycisk **OK**.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj wiersz o następujących ustawieniach:

    - **Numer pozycji:** *T0100*
    - **Ilość:** *5*

1. W polu **Potwierdzona data dostawy** na karcie **Ustawienia** na skróconej karcie **Szczegóły wiersza** należy ustawić dzisiejszą datę.
1. Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj drugi wiersz o następujących ustawieniach:

    - **Numer pozycji:** *L0101*
    - **Ilość:** *20*

1. W polu **Potwierdzona data dostawy** na karcie **Ustawienia** na skróconej karcie **Szczegóły wiersza** należy ustawić dzisiejszą datę.
1. Dla każdego właśnie dodanego wiersza należy wykonać następujące kroki, aby zarezerwować zapasy:

    1. Wybierz wiersz do zarezerwowania.
    2. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.
    3. Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.
    4. Zamknij stronę **Rezerwacja**.

1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Po wykonaniu zwolnienia, użytkownik otrzymuje komunikaty informacyjne, które zawierają identyfikator grupy czynności oraz identyfikator wysyłki.

### <a name="create-sales-order-2"></a>Utwórz zamówienie sprzedaży 2

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży 2.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-011*
    - **Magazyn:** *61*

1. Kliknij przycisk **OK**.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj wiersz o następujących ustawieniach:

    - **Numer pozycji:** *L0101*
    - **Ilość:** *20*

1. W polu **Potwierdzona data dostawy** na karcie **Ustawienia** na skróconej karcie **Szczegóły wiersza** należy ustawić dzisiejszą datę.
1. Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj drugi wiersz o następujących ustawieniach:

    - **Numer pozycji:** *T0100*
    - **Ilość:** *2*

1. W polu **Potwierdzona data dostawy** na karcie **Ustawienia** na skróconej karcie **Szczegóły wiersza** należy ustawić dzisiejszą datę.
1. Dla każdego właśnie dodanego wiersza należy wykonać następujące kroki, aby zarezerwować zapasy:

    1. Wybierz wiersz do zarezerwowania.
    2. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.
    3. Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.
    4. Zamknij stronę **Rezerwacja**.

1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Po wykonaniu zwolnienia, użytkownik otrzymuje komunikaty informacyjne, które zawierają identyfikator grupy czynności oraz identyfikator wysyłki.

### <a name="get-work-ids-and-license-plate-numbers"></a>Pobierz identyfikatory pracy i numery identyfikacyjne

Powinny zostać utworzone dwa identyfikatory pracy, z których każdy ma dwa wiersze pobrania. Aby znaleźć identyfikatory pracy i przypisania numerów identyfikacyjnych, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. W siatce **Przeglądu** wyszukaj w kolumnie **Numery zamówień** dwóch nowo utworzonych zamówień sprzedaży. Zapisz identyfikatory pracy dla każdego zamówienia sprzedaży.
1. Wybierz wiersz dla każdego zamówienia sprzedaży, aby wyświetlić informacje powiązane z siatką **Wiersze**. Umożliwia zanotowanie lokalizacji, z której będzie pobierany każdy towar.
1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zapytania i raporty \> Dostępne zapasy**.
1. Wybierz opcję **Wymiary** w okienku akcji, aby otworzyć okno dialogowe **Wyświetlane wymiary**.
1. Upewnij się, że pola wyboru **Numer identyfikacyjy**, **Magazyn** i **Kod towaru** są zaznaczone, a następnie kliknij przycisk **OK**.
1. W okienku **Filtr** należy skonfigurować następujące filtry:

    - **Kod pozycji** — **jeden z** — *L0101* i *T100*
    - **Magazyn** — **zaczyna się od** – *61*

1. Zanotuj wyświetlony **numer identyfikacyjny**.

## <a name="example-scenario"></a><a name="example-scenario"></a>Przykładowy scenariusz

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a>Wykonywanie przepływu urządzeń przenośnych — konfiguracja potwierdzenia pracy dla produktu

1. Zaloguj się do aplikacji magazynowania jako użytkownik w magazynie *61*.
1. Przejdź do **Wychodzące \> Tworzenie pobrania w grupie**.

    Zostanie wyświetlona strona **ZADANIE: Przypisz pracę do grupy**.

1. Wprowadź identyfikator pracy dla zamówienia sprzedaży 1 w celu przypisania go do pozycji w grupie 1.
1. Wybierz **OK** (symbol znacznika wyboru).
1. Wprowadź identyfikator pracy dla zamówienia sprzedaży 2 w celu przypisania go do pozycji w grupie 2.
1. Wybierz **OK** (symbol znacznika wyboru).

    Pojawi się strona **ZADANIE: Utwórz pobieranie dla grupy: pobierz**, które wyświetli *Pozycja L0101 2 PL*.

Ponieważ profil grupy ustawia liczbę stanowisk na 2, system automatycznie kieruje do pierwszego pobrania: dwie palety (PL) pozycji *L0101*.

W dowolnym momencie podczas wykonywania poniższych kroków można wybrać kartę **Szczegóły**, aby wyświetlić dodatkowe informacje o zadaniu, takie jak lokalizacja pobierania.

1. Ustaw wartość w polu **POZYCJA** na *L0101*. Powoduje to potwierdzenie kodu towaru wymaganego dla tego elementu menu (wcześniej skonfigurowano przez wybranie **Ustawienia potwierdzenie pracy** z poziomu strony **Element menu urządzenia przenośnego** po utworzeniu tego elementu menu).
1. Umożliwia wprowadzenie numeru identyfikacyjnego, który jest skojarzony z towarem w lokalizacji pobierania. Zostaną pobrane dwie palety.
1. W polu **LP** ustaw wartość *LP\_PICK\_01*.
1. Wybierz **OK** (symbol znacznika wyboru).

    Zostanie wyświetlona strona **ZADANIE:Sortuj: Tworzenie pobierania dla grupy**. W tym miejscu zostaną posortowane dwie pobrane palety w wybrane pozycje pobrania. To stanowisko może być pojemnikiem lub kontenerem używanym do oddzielenia pobranego przedmiotu według zamówienia sprzedaży.

1. Wyświetl szczegóły dotyczące towaru (*L0101*) i ilości (*20* ea), które zostaną posortowane w ramach stanowiska 1 (dla zamówienia sprzedaży 1).
1. W polu **NAZWA STAN** wybierz *1*.
1. Wybierz **OK** (symbol znacznika wyboru).
1. Wyświetl szczegóły dotyczące towaru (*L0101*) i ilości (*20* ea), które zostaną posortowane w ramach stanowiska 2 (dla zamówienia sprzedaży 2).
1. W polu **NAZWA STAN** wybierz *2*.
1. Wybierz **OK** (symbol znacznika wyboru).

    Pojawi się strona **ZADANIE: Utwórz pobieranie dla grupy: pobierz**, które wyświetli *Pozycja T0100 7 ea*.

W tym scenariuszu pozycja 1 nie akceptuje pełnej ilości towarów, które muszą zostać pobrane, aby zrealizować zamówienie sprzedaży 1. Pozycja musi być oznaczona jako pełna. W tym scenariuszu zostanie wydane częściowe pobranie drugiego towaru. Drugi towar zostanie częściowo pobrany dla stanowiska 1, a w celu wybrania pozostałej ilości do zrealizowania zamówienia zostanie utworzona nowa praca.

1. Wybierz przycisk menu (czasami nazywany przyciskiem hamburger lub hamburgerem), a następnie wybierz opcję **Stanowisko pełne**.
1. Określ zapełnione stanowisko i wybierz opcję *1*.
1. Wybierz **OK** (symbol znacznika wyboru).
1. Wprowadź ilość pobrania, która może zostać jeszcze pobrana do pozycji 1. System może ustalić, który numer pozycji jest pobierany.
1. Wprowadź *2*.
1. Wybierz **OK** (symbol znacznika wyboru).
1. Potwierdź numer pozycji, aby zakończyć pobieranie pozostałego towaru w stanowisku 2.
1. Ustaw wartość w polu **POZYCJA** na *T0100*.
1. Wybierz **OK** (symbol znacznika wyboru).
1. Wprowadź numer identyfikacyjny towaru, z którego ma zostać pobrany towar, ustawiając **pole LP** na wartość *LPREPL04*.
1. Wybierz **OK** (symbol znacznika wyboru).
1. Wyświetl szczegóły dotyczące towaru (*T0100*) i ilości (*2* ea), które zostaną posortowane w ramach stanowiska 2 (dla zamówienia sprzedaży 2).
1. W polu **NAZWA STAN** wybierz *2*.
1. Wybierz **OK** (symbol znacznika wyboru).
1. Wyświetl szczegóły dotyczące towaru (*T0100*) i ilości (*2* ea), które zostaną posortowane w ramach stanowiska 1 (dla zamówienia sprzedaży 1).
1. W polu **NAZWA STAN** wybierz *1*.
1. Wybierz **OK** (symbol znacznika wyboru).

    Zostanie wyświetlona strona **ZADANIE: Tworzenie pobierania dla grupy: Odłóż**.

W tym scenariuszu pobranie klastra zostało zakończone i użytkownik jest proszony o odłożenie pobranych pozycji z pozycji 1 i 2 i umieszczenie ich w lokalizacji *STAGE01*.

1. Przejrzyj informacje znajdujące się na stronie. Wskazują one, że całkowita ilość *44* zostanie wprowadzona do lokalizacji pośredniej.
1. Wybierz **OK** (symbol znacznika wyboru).

    Zostanie wyświetlony komunikat „Pobieranie dla grupy zakończone”.

Za pomocą elementu menu **Pobranie sprzedaży** można teraz pobrać pozostałą ilość. Następnie można skorzystać z elementu menu **Ładowanie sprzedaży**, aby przenieść elementy z lokalizacji pośredniej do doku załadunku.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]