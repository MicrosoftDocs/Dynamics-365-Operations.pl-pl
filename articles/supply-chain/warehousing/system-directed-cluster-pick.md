---
title: Pobieranie dla grupy sterowane przez system
description: Ten temat zawiera omówienie pobierania dla grupy sterowanego przez system w aplikacji Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkCluster, WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0838405bcb5ee0d8e582093fbbd69553228cb2b6
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435614"
---
# <a name="system-directed-cluster-picking"></a>Pobieranie dla grupy sterowane przez system

[!include [banner](../includes/banner.md)]

Pobieranie dla grupy jest procesem pobierania elementów, który umożliwia wybieranie elementów dla wielu zamówień w tym samym czasie przez pobieranie ich do wybranej grupy. Następnie musisz odwiedzić lokalizację pobrania tylko jeden raz. Zazwyczaj ta funkcja jest używana do pobierania małych zamówień lub ilości, które są mniejsze niż wielkości dla przypadku.

Po skonfigurowaniu pobierania dla grupy sterowanego przez system można wybrać nagłówki robocze pobierania dla grupy na grupie wygenerowanej przez system. System pobiera zamówienia dla grupy do liczby stanowisk określonej w profilu grupy. W związku z tym można wybrać wiele zamówień w tym samym czasie bez konieczności ręcznego tworzenia grupy.

Pobieranie dla grupy sterowane przez system oferuje alternatywę dla ręcznego budowania grupy, gdzie profil grupy jest używany do tworzenia grupy. Przed użyciem grupy należy w jej profilu skonfigurować kilka wierszy związanych z konfiguracją:

- **Liczba stanowisk** odpowiada liczbie zleceń, które zostaną umieszczone w grupie. W związku z tym odpowiada liczbie pojemników.
- Wartość **Podziel grupę** określa, kiedy należy podzielić grupę.
- Wartość **Generuj identyfikator grupy** kontroluje, czy identyfikator grupy zostanie wygenerowany przez system lub wprowadzony przez użytkownika.
- **Typ weryfikacji sortowania** określa, czy wymagana jest weryfikacja pozycji.

Nowy element menu urządzenia przenośnego służy do pobierania dla grupy sterowanego przez system. **Identyfikator profilu grupy** należy określić dla wybranej opcji **Sterowane przez**. Dodatkowo, kierowane przez system zapytania dotyczące sekwencji pracy mogą grupować zamówienia na podstawie kryteriów specyficznych dla firmy. W związku z tym można dodatkowo zoptymalizować przypisania zleceń pracy, określając dostosowane kryteria sortowania używając zapytań sekwencji pracy sterowanej przez system.

Po włączeniu pobierania dla grupy sterowanego przez systemu pracownicy magazynu uzyskują dostęp do grupy, w którym zamówienia pobrania zostały wstępnie przypisane do stanowisk grupy. W związku z tym pracownicy mogą zacząć wybierać element dla wielu zleceń pracy, odwiedzając lokalizację pobrania tylko jeden raz. Proces pobierania dla grupy sterowany przez system jest taki sam jak proces pobierania dla grupy sterowany przez użytkownika.

## <a name="enable-the-system-directed-cluster-picking-feature"></a>Włączanie funkcji pobierania grupy kierowanej przez system

Aby móc używać tej funkcji, musi zosyać włączona w systemie. Administratorzy mogą skorzystać ze strony [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją w razie potrzeby. W tym miejscu funkcja jest wyświetlana jako:

- **Moduł** - Zarządzanie magazynem
- **Nazwa funkcji** - Pobieranie grupy kierowane przez system

Ta funkcja wymaga również włączenia funkcji zależnej. Funkcja zależna:

- **Moduł** - Zarządzanie magazynem
- **Nazwa funkcji** — sekwencjonowanie pracy skierowanej na system całej organizacji

## <a name="set-up-system-directed-cluster-picking"></a>Konfigurowanie pobierania dla grupy sterowanego przez system

### <a name="create-cluster-profiles"></a>Tworzenie profilów grup

Profile grup kontrolują sposób, w jaki system tworzy każdą grupę. Jeśli wymagane są różne grupy, dla każdego elementu menu urządzenia przenośnego należy utworzyć inny profil grupy.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Profile grup**.
2. Wybierz pozycję **Nowy**.
3. W polu **Identyfikator profilu grupy** wprowadź **Pozycja 2**.
4. W polu **Nazwa** wprowadź **Pozycja 2**.
5. Na skróconej karcie **Ogólne** wprowadź następujące informacje:

    - **Generuj identyfikator grupy** — Wybierz opcję **Tak**. Ta opcja określa, czy identyfikator grupy jest automatycznie tworzony przez system, czy też użytkownik utworzy go na początku pobierania. 
    - **Aktywuj stanowiska** — Wybierz opcję **tak**. Ta opcja określa, czy nazwy stanowisk są generowane automatycznie na podstawie konfiguracji nazw stanowisk. Jeśli ta opcja zostanie ustawiona na **Nie**, będzie używany numer identyfikacyjny dla stanowiska.
    - **Liczba stanowisk:** - Wybierz **2**. To pole określa maksymalną liczbę stanowisk, które może zawierać grupa (czyli maksymalną liczbę opakowań, pojemników itd.).
    - **Nazwa stanowiska:** - Wybierz pozycję **Numeryczna**, tak aby stanowiska były nazywane przy użyciu liczb ciągłych. Jeśli wybierzesz pozycję **Alfabetyczna**, stanowiska będą nazywane w kolejności alfabetycznej.
    - **Podziel grupę w** - Wybierz pozycję **Odłożenie**. To pole określa, kiedy grupa jest dzielona. 
    - **Typ weryfikacji sortowania** - Wybierz pozycję **Skan pozycji**. To pole określa, czy jest weryfikowany krok odłożenia do pozycji.
        
6. Na skróconej karcie **Sortowanie grupy** można zdefiniować kryteria sortowania, tworząc nowy wiersz i wprowadzając następujące informacje:

    - **Numer sekwencyjny** - Wybierz **1**. To pole określa kolejność sortowania przez system. Wartość jest wprowadzana automatycznie, ale w razie potrzeby można ją zmienić.
    - **Nazwa pola** - Wprowadź **WMSLocationId**. To pole określa pole używane przez wiersz dla kryteriów sortowania.
    - **Sortowanie** - Wybierz pozycję **Rosnąco**. To pole określa, czy sortowanie odbywa się w porządku rosnącym czy malejącym.

### <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego

Aby utworzyć nowy element menu urządzenia przenośnego dla pobierania dla grupy sterowanego przez system i połączyć identyfikator profilu grupy z elementem menu urządzenia przenośnego, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego**.
1. Wybierz pozycję **Nowy**.
1. W sekcji nagłówek wprowadź następujące informacje:
    - **Nazwa elementu menu** - Grupa SD
    - **Tytuł** - Grupa SD
    - **Tryb** - Praca
    - **Używanie istniejącej pracy** - Tak

1. Na skróconej karcie **Ogólne** wprowadź następujące informacje:
    - **Sterowane przez** - Pobieranie dla grupy sterowane przez system
    - **Generuj numer identyfikacyjny** - Tak
    - **Identyfikator profilu grupy** - Pozycja 2

1. Na skróconej karcie **Klasy robocze** skonfiguruj prawidłową klasę roboczą dla tego elementu menu urządzenia przenośnego, ustawiając następujące pola:
    - **Identyfikator klasy roboczej** - Sprzedaż
    - **Typ zamówienia pracy** - zamówienia sprzedaży

1. W okienku akcji **Elementy menu urządzenia przenośnego** wybierz opcję **Systemowe zapytania dotyczące sekwencji pracy** i wykonaj następujące kroki w celu określenia nowej, skierowanej do systemu kwerendy sekwencji pracy:
    - W okienku akcji wybierz opcję **Nowy**.
    - **Numer sekwencyjny** - 1
    - **Opis** — priorytet pracy — identyfikator pracy

1. W okienku akcji wybierz pozycję **Edytuj zapytanie**
1. Wybierz kartę **Sortowanie**
1. Wybierz przycisk **Dodaj**, aby dodać nowy wiersz, a następnie wprowadź następujące opcje:
    - **Tabela** — Praca
    - **Tabela pochodna** - Praca
    - **Pole** - Priorytet pracy
    - **Kierunek wyszukiwania** - Rosnąco
1. Wybierz przycisk **Dodaj**, aby dodać drugi wiersz, a następnie wprowadź następujące opcje:
    - **Tabela** — Praca
    - **Tabela pochodna** - Praca
    - **Pole** - Identyfikator pracy
    - **Kierunek wyszukiwania** - Rosnąco

1. System będzie teraz sortować identyfikatory pracy w grupie, najpierw według priorytetu pracy, a następnie według identyfikatora pracy.

### <a name="set-up-a-mobile-device-menu"></a>Konfigurowanie menu urządzenia przenośnego

1. Wybierz kolejno opcje **Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Menu urządzeń przenośnych**.
1. Dodaj element menu **Grupa SD** utworzony wcześniej do menu urządzenia przenośnego.
1. Wybierz menu **Wychodzące**.
1. Wybierz pozycję **Edytuj** w okienku akcji.
1. Przewijaj do momentu znalezienia **Grupa SD**.
1. Wybierz **grupa SD**, a strzałka wskazująca na listę **Struktury menu** zostanie włączona.
1. Wybierz przycisk **strzałki**, aby przenieść element menu **Grupy SD** do struktury menu **Wychodzącego**.
1. Wybierz opcję **Grupa SD** z listy **Struktura menu**, a następnie wybierz strzałkę **W GÓRĘ** lub **W DÓŁ**, aby przenieść element menu do żądanej pozycji w menu urządzenia przenośnego.

## <a name="scenario"></a>Scenariusz

### <a name="create-picking-work"></a>Tworzenie pracy pobrania

Aby można było skonfigurować pobieranie dla grupy sterowane przez system, należy utworzyć kwalifikującą się pracę wychodzącą. Utworzony wcześniej profil grupy określa dwie pozycje grupy. W związku z tym musisz utworzyć co najmniej dwa identyfikatory pracy. W tym scenariuszu utworzysz dwa zamówienia sprzedaży, zarezerwujesz zapasy, zwolnisz zamówienia sprzedaży do magazynu, a następnie ręcznie przetworzysz falę.

1. Wybierz kolejno opcje **Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży**.
1. Wybierz **Nowe** w okienku akcji, aby utworzyć nowe zamówienie sprzedaży.
    - Zostanie otwarte menu **Utwórz zamówienie sprzedaży**, w którym należy wprowadzić następujące informacje:
        - Na skróconej karcie **Klient** wprowadź **Konto klienta** - **US-004**.
        - Na skróconej karcie **Ogólne** wprowadź **Magazyn** - **62**.
        - Naciśnij przycisk **OK**, aby zamknąć menu i utworzyc zamówienie sprzedaży.
    - Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, jeśli nowy wiersz nie został dodany automatycznie i wprowadź następujące opcje:
        - **Numer pozycji** - A0001
        - **Ilość** - 1
        - Wybierz pozycję **Dodaj wiersz**, aby dodać drugi wiersz.
        - **Numer pozycji** - A0002
        - **Ilość** - 3
    - Rezerwuj zapasy w nowo utworzonych wierszach.
        - Zaznacz **Wiersz 1**.
        - W **Wiersze zamówienia sprzedaży** w okienku akcji wybierz **Zapasy**, a następnie wybierz **Rezerwacja** z listy.
        - W formularzu **Rezerwacja** wybierz **Rezerwacja partii** w celu zarezerwowania zapasów.
        - Po zakończeniu rezerwacji zamknij formularz **Rezerwacja**.
        - Powtórz te kroki, aby zarezerwować zapasy dla **Wiersza 2**.
1. Wybierz **Nowe** w okienku akcji, aby utworzyć drugie zamówienie sprzedaży
    - Zostanie otwarte menu **Utwórz zamówienie sprzedaży**, w którym należy wprowadzić następujące informacje:
        - Na skróconej karcie **Klient** wprowadź **Konto klienta** - **US-005**.
        - Na skróconej karcie **Ogólne** wprowadź **Magazyn** - **62**.
        - Naciśnij przycisk **OK**, aby zamknąć menu i utworzyc zamówienie sprzedaży
    - Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, jeśli nowy wiersz nie został dodany automatycznie i wprowadź następujące informacje:
        - **Numer pozycji** - A0001
        - **Ilość** - 4
        - Wybierz pozycję **Dodaj wiersz**, aby dodać drugi wiersz.
        - **Numer pozycji** - A0002
        - **Ilość** - 2
    - Rezerwuj zapasy w obu utworzonych wierszach.
        - Zaznacz **Wiersz 1**.
        - W **Wiersze zamówienia sprzedaży** w okienku akcji wybierz **Zapasy**, a następnie wybierz **Rezerwacja** z listy.
        - W formularzu **Rezerwacja** wybierz **Rezerwacja partii** w celu zarezerwowania zapasów.
        - Po zakończeniu rezerwacji zamknij formularz **Rezerwacja**.
        - Powtórz te kroki, aby zarezerwować zapasy dla **Wiersza 2**.
    - Zamknij zamówienie sprzedaży i wróć do strony listy **Wszystkie zamówienia sprzedaży**.
1. Znajdź utworzone dwa zamówienia sprzedaży (konieczne może być odświeżenie strony). W tabeli zaznacz oba zamówienia sprzedaży, używając znacznika wyboru sekcji.
    - W okienku akcji **Wszystkie zamówienia sprzedaży** wybierz kartę **Magazyn**.
    - W grupie **Akcje** wybierz opcję **zwolnienie do magazynu**, aby zwolnić oba zamówienia sprzedaży do magazynu.
1. Po zakończeniu procesu zwalniania do magazynu zostanie wyświetlony komunikat informacyjny.
    - Dla każdego zamówienia sprzedaży zostaną utworzone wysyłki.
    - Zostanie utworzona grupa czynności, a obie wysyłki zostaną przypisane do grupy czynności. Zanotuj **Identyfikator pracy**.
1. Przejdź do **Zarządzanie magazynem > Wychodzące grupy czynności > Grupy czynności wysyłki > Wszystkie grupy czynności**.
    - Na liście **Wszystkie grupy czynności** znajdź i zaznacz **Identyfikator grupy czynności** utworzony w poprzednim kroku.
    - W okienku akcji wybierz kartę **Grupa czynności**.
    - W grupie **Grupa czynności** wybierz opcję **Proces**, aby przetworzyć grupę czynności i utworzyć **Pracę**.
    - Komunikaty informacyjne będą generowane po zakończeniu przetwarzania, co oznacza, że utworzono pracę i że dana grupa czynności została zaksięgowana.
1. **Opcjonalnie**: Przejdź do **Zarządzanie magazynem > Praca > Szczegóły pracy**, aby wyświetlić utworzoną pracę. Tworzone są dwa różne identyfikatory pracy. Każdy identyfikator pracy ma dwa wiersze pobrania.

### <a name="run-the-mobile-device-flow"></a>Uruchamianie przepływu na urządzeniu przenośnym

1. Zaloguj się do urządzenia przenośnego dla użytkownika w magazynie **62**.
1. W **Menu głównym** wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz **Grupa SD**, aby zainicjować pobieranie.
    - Zostanie utworzona grupa i dwa identyfikatory pracy, które utworzono wcześniej, są dołączane. Jeśli utworzono więcej niż dwa identyfikatory pracy, tylko dwa pierwsze są dodawane do grupy. Zauważ, że identyfikatory pracy są dodawane do grupy w kolejności rosnącej, jak określono w konfiguracji zapytania.

    > [!NOTE]
    > Nowa grupa jest tworzona automatycznie tylko wtedy, gdy wcześniej utworzono wystarczająco dużo dodatkowych identyfikatorów pracy. W przeciwnym razie wyświetlany jest następujący komunikat: „Dla grupy nie można znaleźć wystarczającej ilości pracy”.

    - Po wybraniu menu zostanie wyświetlony pierwszy ekran wyboru. System agreguje wszystkie pasujące wiersze pobrania z dwóch identyfikatorów pracy i kieruje Cię do odwiedzenia lokalizacji pobrania jeden raz, dzięki czemu można zrealizować oba zamówienia za pomocą jednego pobrania. Ten proces odbywa się w taki sam sposób jak proces pobierania dla grupy sterowany przez użytkownika.

1. Potwierdź pierwszą lokalizację pobrania i towar, klikając **OK**.
    - Ilość pobrania będzie sumą towarów wyświetlanych w zamówieniach sprzedaży w grupie.
1. Umożliwia wprowadzenie nazwy stanowiska (numeryczne lub alfabetyczne) w celu potwierdzenia, że ilość towaru pobrana dla danego stanowiska została umieszczona we właściwym miejscu.
1. Powtórz ten proces, aż wszystkie ilości towaru zostaną pobrane i umieszczone w prawidłowej pozycji.
1. Ostatnim krokiem na urządzeniu przenośnym jest **Umieszczenie** grupy w ostatecznej lokalizacji. Kliknij przycisk **OK**
    - Po potwierdzeniu operacji odłożenia grupa jest zamykana i dzielona na podstawie wartości ustawionej w polu **Podziel grupę w** w profilu grupy. Identyfikatory pracy są również zamknięte.
1. Na urządzeniu przenośnym jest wyświetlany komunikat „Grupa kompletna”.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]