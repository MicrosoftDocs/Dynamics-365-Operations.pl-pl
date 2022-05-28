---
title: Kotwiczenie
description: W tym temacie wyjaśniono, jak włączyć i używać kotwiczenia.
author: GalynaFedorova
ms.date: 07/29/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-07-29
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 26a7bf60912ff1e8a23305e9331d520fe8d65727
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676503"
---
# <a name="anchoring"></a>Kotwiczenie

[!include [banner](../includes/banner.md)]

Ten temat zawiera szczegóły dotyczące procesu kotwiczenia. Opisuje on wymaganą konfigurację oraz logikę uruchamiania, gdy pracownik magazynu zmienia lokalizację pośrednią lub lokalizację załadunku.

Funkcja kotwiczenia umożliwia zastąpienie lokalizacji pośredniej lub załadunku. Wszystkie otwarte zostaną następnie skierowane do nowej lokalizacji pośredniej lub załadunku, która została określona przez użytkownika.

Ta funkcja pomaga pracownikom w efektywniejszej wysyłce towarów. Oto kilka przykładów:

- Pracownik ma odłożyć towary dla zamówienia 1 w lokalizacji pośredniej przy Doku 1, ale nie może, bo poprzedni ładunek nie opuścił jeszcze z lokalizacji. Zamiast czekać na to, aż lokalizacja pośrednia przy Doku 1 będzie dostępna, pracownik decyduje się użyć lokalizacji pośredniej przy Doku 2. W związku z tym pracownik zastępuje sugerowaną lokalizację pośrednią. Lokalizacja odłożenia dla wszystkich pozostałych towarów w pracy jest aktualizowana na lokalizację pośrednią przy Doku 2.
- Pracownik, który musi wykonać wiele pobrań dla tej samej dostawy, może mieć pewność, że wszystkie odłożone towary są zebrane w tym samym miejscu. W związku z tym jest wymagany krótszy czas do załadowania towarów do ciężarówki.

Aby skonfigurować kotwiczenie dla elementów menu urządzenia przenośnego, należy użyć opcji **Kotwica**. Jeśli ustawisz tę opcję na *Tak*, możesz użyć pola **Zakotwicz według** w celu określenia, czy chcesz zakotwiczyć według wysyłki lub ładunku. Jeśli w polu **Zakotwicz według** zostanie ustawiona wartość *Wysyłka*, kolejne otwarte odłożenia zostaną zmienione na nową lokalizację dla tej wysyłki. W przypadku wyboru ustawienia *Ładunek*, kolejne otwarte odłożenia zostaną zmienione na nową lokalizację dla tego ładunku.

> [!IMPORTANT]
> Lokalizacja kolejnych odłożeń otwartych zostanie zmieniona tylko w wierszach pracy generowanych z tego samego wiersza szablonu pracy. Innymi słowy, system zakotwiczy wiersze odłożenia, które pochodzą z tego samego wiersza szablonu pracy.

Ten temat zawiera scenariusz, który pokazuje, jak działa kotwiczenie. W tym scenariuszu utworzysz zestaw zamówień sprzedaży i zwolnisz je do magazynu. Następnie zastąpisz sugerowaną lokalizację pośrednią i sprawdzisz, czy cała pozostała praca odłożenia jest kierowana do nowej lokalizacji.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Warunek wstępny scenariusza: udostępnij dane pokazu

Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management. Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na *USMF*.

## <a name="scenario-setup"></a>Ustawienia scenariusza

Przed rozpoczęciem pracy nad przykładowym scenariuszem należy włączyć kotwiczenie dla odpowiedniego elementu menu urządzenia przenośnego.

### <a name="set-up-a-mobile-device-menu-item-to-enable-anchoring"></a>Konfigurowanie elementu menu urządzenia przenośnego do włączania kotwiczenia

Aby włączyć kotwiczenie dla elementu menu urządzenia przenośnego, należy wykonać następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku listy wybierz rekord o nazwie *Pobranie sprzedaży*. Jeśli żaden istniejący rekord nie ma tej nazwy, utwórz go. Potwierdź lub ustaw następujące wartości dla rekordu:

    - **Nazwa elementu menu:** *Pobranie sprzedaży*
    - **Tytuł:** *Pobranie sprzedaży*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Tak*
    - **Zarządzane przez:** *Sterowane przez użytkownika*
    - **Kotwiczenie:** *Tak*

        To ustawienie powoduje, że system zakotwicza wiele wierszy zlecenia pracy razem podczas pobierania sprzedaży.

    - **Zakotwicz według:** *Ładunek*

        To ustawienie powoduje, że system kotwiczy według ładunku.

    - **Zastąp docelowy numer identyfikacyjny:** *Tak*
    - **Zastąp numer identyfikacyjny podczas odłożenia:** *Tak*
    - **Zachowaj pracę zablokowaną przez użytkownika:** *Tak*
    - **Zezwalaj na pobranie nadmiarowe:** *Tak*

### <a name="set-up-a-work-template-to-enable-staging"></a>Konfigurowanie szablonu pracy w celu włączenia przemieszczania

Należy wykonać następujące kroki, aby skonfigurować szablon pracy w celu włączenia przemieszczania. Ta konfiguracja obsługuje scenariusz, w którym pracownik odkłada towary dla zamówienia w lokalizacji pośredniej.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. W polu **Typ zlecenia pracy** wybierz opcję *Zamówienia sprzedaży*.
1. W siatce wybierz szablon pracy **61 Zamówienie sprzedaży — etap**.
1. Upewnij się, że w sekcji **Szczegóły szablonu pracy** istnieją następujące wiersze i że zostały one skonfigurowane w następujący sposób:

    - Wiersz 1:

        - **Typ pracy:** *Pobranie*
        - **Wymagane:** Wybrane (= *Tak*)
        - **Identyfikator klasy roboczej:** *Pobranie zamówienia sprzedaży*

    - Wiersz 2:

        - **Typ pracy:** *Odłożenie*
        - **Wymagane:** Wybrane (= *Tak*)
        - **Kod dyrektywy:** *Etap*
        - **Identyfikator klasy roboczej:** *Pobranie zamówienia sprzedaży*

    - Wiersz 3:

        - **Typ pracy:** *Pobranie*
        - **Wymagane:** Wybrane (= *Tak*)
        - **Zatrzymaj pracę:** *Tak*
        - **Identyfikator klasy roboczej:** *Załadunek zamówienia sprzedaży*

    - Wiersz 4:

        - **Typ pracy:** *Odłożenie*
        - **Wymagane:** Wybrane (= *Tak*)
        - **Kod dyrektywy:** *Brama dokowa*
        - **Identyfikator klasy roboczej:** *Załadunek zamówienia sprzedaży*

1. W okienku akcji kliknij opcję **Edytuj zapytanie**, aby otworzyć edytor zapytania.
1. Na karcie **Zakres** upewnij się, że obecny jest następujący wiersz:

    - **Tabela:** *Tymczasowe transakcje pracy*
    - **Tabela pochodna:** *Tymczasowe transakcje pracy*
    - **Pole:** *Magazyn*
    - **Kryteria:** *61*

1. Na karcie **Sortowanie** upewnij się, że obecny jest następujący wiersz:

    - **Tabela:** *Tymczasowe transakcje pracy*
    - **Tabela pochodna:** *Tymczasowe transakcje pracy*
    - **Pole:** *Identyfikator wysyłki*
    - **Kierunek wyszukiwania:** *Rosnąco*

1. Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okno dialogowe kwerendy. Jeśli pojawi się okienko potwierdzenia, zaakceptuj zmiany.
1. W okienku akcji wybierz **Podziały nagłówka pracy**.
1. W wierszu, w którym pole **Nazwa pola** ma wartość *Identyfikator wysyłki*, upewnij się, że zaznaczone jest pole wyboru **Grupuj według tego pola**.

### <a name="set-up-license-plates-locations-and-inventory"></a>Ustawianie numerów identyfikacyjnych, lokalizacji i zapasów

Przed utworzeniem zamówień sprzedaży i wysyłek należy upewnić się, że istnieją wymagane lokalizacje, numer identyfikacyjne i zapasy.

1. Przejdź do opcji **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Numery identyfikacyjne** i utwórz dwa numery identyfikacyjne:

    - Mój numer identyfikacyjny 1
    - Mój numer identyfikacyjny 2

1. Przejdź do opcji **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje** i utwórz następujące lokalizacje, jeśli jeszcze nie istnieją.

    | Magazyn | Lokalizacja   | Identyfikator profilu lokalizacji | Identyfikator strefy   |
    |-----------|------------|---------------------|-----------|
    | 61        | 06A01R2S1B | POBIERZ-06             | FLOOR     |
    | 61        | 06A01R3S1B | POBIERZ-06             | FLOOR     |
    | 61        | ETAP01    | ETAP               | *(Puste)* |
    | 61        | ETAP02    | ETAP               | *(Puste)* |
    | 61        | ETAP03    | ETAP               | *(Puste)* |
    | 61        | ETAP04    | ETAP               | *(Puste)* |

1. Upewnij się, że następujące zapasy są dostępne. Jeśli konieczne jest skorygowanie zapasów, można ręcznie tworzyć zmiany, skorzystać z uzupełnienia lub skorzystać z dowolnego innego przepływu.

    | Numer towaru | Ilość | Magazyn | Lokalizacja   | Numer identyfikacyjny |
    |-------------|----------|-----------|------------|---------------|
    | A0001       | 100      | 61        | 06A01R2S1B | Mój numer identyfikacyjny 1         |
    | A0002       | 100      | 61        | 06A01R3S1B | Mój numer identyfikacyjny 2         |

### <a name="create-demand"></a>Utwórz popyt

Aby można było wypróbować funkcję kotwiczenia, trzeba utworzyć pewne zapotrzebowanie. W tym scenariuszu dla tego samego odbiorcy zostaną utworzone trzy zamówienia sprzedaży.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć pierwsze zamówienie sprzedaży.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *61*

1. Kliknij przycisk **OK**.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera ono pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**. Dla tego wiersza należy określić następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *1*

1. Na pasku narzędzi wybierz polecenie **Dodaj wiersz**, aby dodać drugi wiersz zamówienia sprzedaży i określ dla niego następujące wartości:

    - **Numer pozycji:** *A0002*
    - **Ilość:** *1*

1. Wykonaj poniższe kroki dla każdego wiersza sprzedaży w zamówieniu, aby zarezerwować dla niego zapasy:

    1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży.
    1. Na pasku narzędzi wybierz pozycję **Zapasy \> Rezerwacja**.
    1. Na stronie **Rezerwacje** wybierz **Rezerwacja partii** i zamknij stronę.
    1. Na okienku akcji wybierz opcję **Zapisz**.

1. Powtórz kroki od 2 do 6, aby utworzyć drugie zamówienie sprzedaży. Należy dla niego określić następujące wartości:

    - W oknie dialogowym **Utwórz zamówienie sprzedaży**:

        - **Konto odbiorcy:** *US-001*
        - **Magazyn:** *61*

    - W wierszu zamówienia sprzedaży 1:

        - **Numer pozycji:** *A0001*
        - **Ilość:** *2*

    - W wierszu zamówienia sprzedaży 2:

        - **Numer pozycji:** *A0002*
        - **Ilość:** *2*

1. Powtórz krok 7, aby zarezerwować każdy wiersz w zamówieniu sprzedaży 2.
1. Powtórz kroki od 2 do 6, aby utworzyć trzecie zamówienie sprzedaży. Należy dla niego określić następujące wartości:

    - W oknie dialogowym **Utwórz zamówienie sprzedaży**:

        - **Konto odbiorcy:** *US-001*
        - **Magazyn:** *61*

    - W wierszu zamówienia sprzedaży 1:

        - **Numer pozycji:** *A0001*
        - **Ilość:** *3*

    - W wierszu zamówienia sprzedaży 2:

        - **Numer pozycji:** *A0002*
        - **Ilość:** *3*

1. Powtórz krok 7, aby zarezerwować każdy wiersz w zamówieniu sprzedaży 3.

### <a name="use-the-load-planning-workbench-to-create-a-load-and-release-it-to-the-warehouse"></a>Tworzenie ładunku i zwalnianie go do magazynu przy użyciu pulpitu planowania wysyłki ładunku

Wykonaj następujące czynności aby utworzyć ładunek dla zamówień utworzonych w tym scenariuszu, a następnie zwolnić je do magazynu.

1. Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.
1. Na karcie **Wiersze sprzedaży** znajdź i zaznacz wszystkie wiersze zamówienia sprzedaży dla zamówienia sprzedaży 1 i zamówienia sprzedaży 2.
1. W okienku akcji na karcie **Popyt i podaż** w grupie **Dodaj** kliknij opcję **Do nowego transportu**.
1. W oknie dialogowym **Przypisanie szablonu ładunku** w polu **Identyfikator szablonu ładunku** wybierz szablon ładunku, na przykład *Standardowy szablon ładunku*.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. W sekcji **Ładunki** znajdź i wybierz utworzony ładunek.
1. Na pasku narzędzi wybierz **Zwolnij \> Zwolnij do magazynu**.
1. W oknie dialogowym **Zwolnij ładunek do magazynu** wybierz **OK**, aby zwolnić wybrany ładunek do magazynu.
1. Przejdź do obszaru **Zarządzanie magazynem \> Praca \> Cała praca**, aby wyświetlić utworzoną pracę. Należy znaleźć dwa nowe identyfikatory pracy, po jednym dla każdej wysyłki. Każdy identyfikator pracy ma wiersze pobrania i odłożenia, które przenoszą zapasy z lokalizacji pobrania do lokalizacji pośredniej i z lokalizacji pośredniej do bramy dokowej. Zanotuj wartość **Identyfikatora pracy** dla pierwszej wysyłki, ponieważ będziesz jej używać w następnej procedurze.

### <a name="sales-order-picking-to-the-staging-location-for-the-first-shipment"></a>Pobieranie zamówienia sprzedaży do lokalizacji pośredniej dla pierwszej wysyłki

1. Zaloguj się do aplikacji Warehouse Management jako pracownik w magazynie *61*. (W standardowych danych demonstracyjnych można zalogować się, używając _61_ jako identyfikatora użytkownika i _1_ jako hasła.)
1. W menu głównym wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz opcję **Pobranie sprzedaży**.
1. Zaznacz pole **Identyfikator**, a następnie wprowadź identyfikator pracy dla pierwszej wysyłki.
1. Potwierdź wpis.
1. W polu **Numer identyfikacyjny** wprowadź numer identyfikacyjny dla pierwszej pozycji (*Mój numer identyfikacyjny 1*).
1. Potwierdź wpis.
1. W polu **Docelowy numer identyfikacyjny** wprowadź dowolny numer (docelowy numer identyfikacyjny nie musi jeszcze istnieć).

    Wszystkie wiersze utworzone z przetworzonej grupy czynności zostaną pobrane na ten sam docelowy numer identyfikacyjny.

1. Potwierdź wpis.
1. W polu **Numer identyfikacyjny** wprowadź numer identyfikacyjny dla drugiej pozycji (*Mój numer identyfikacyjny 2*).
1. Potwierdź wpis.

    Załóżmy, że pracownik zebrał zamówienie, ale po dotarciu do lokalizacji pośredniej, która została określona w pracy, odkrywa, że miejsce jest już zajęte. Pracownik może jednak zobaczyć, że jest dostępna inna lokalizacja w pobliżu (*ETAP03*). W związku z tym zażądają zmiany lokalizacji pośredniej. Ponieważ funkcja kotwiczenia jest włączona, system automatycznie zaktualizuje lokalizację pośrednią dla tej i całej powiązanej pracy.

1. Wybierz opcję **Zastąp lokalizację**, aby zastąpić sugerowaną lokalizację pośrednią.
1. W polu **Wyjątki pracy** określ *Ścieżka pośrednia uległa zmianie*.
1. W polu **Lokalizacja** wprowadź nową lokalizację pośrednią (*ETAPE03*).
1. Potwierdź wpis. Zostanie wyświetlony komunikat „Praca zakończona”.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca\> Wszystkie prace**.
1. Otwórz identyfikator pracy dla pierwszej wysyłki. Sprawdź, czy lokalizacja pośrednia została zaktualizowana do nowej lokalizacji (*ETAP03*), która została zdefiniowana za pomocą urządzenia przenośnego.
1. Otwórz identyfikator pracy dla drugiej wysyłki. Sprawdź, czy lokalizacja pośrednia została zaktualizowana do nowej lokalizacji pośredniej (*ETAP03*) z powodu konfiguracji kotwiczenia.

> [!NOTE]
> Lokalizacja wszystkich pozostałych wierszy otwartej pracy odłożenia, które mają tę samą lokalizację pośrednią i które zostały wygenerowane z tego samego wiersza szablonu pracy, zostaną zaktualizowane do nowej lokalizacji.

### <a name="use-the-load-planning-workbench-to-add-the-new-sales-order-to-the-existing-load"></a>Używanie warsztatu planowania wysyłki ładunku do dodania nowego zamówienie sprzedaży do istniejącego ładunku

Aby dodać zamówienie do ładunku, a następnie zwolnić je do magazynu, należy wykonać następujące kroki.

1. Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.
1. Na karcie **Wiersze sprzedaży** znajdź i zaznacz wszystkie wiersze zamówienia sprzedaży dla zamówienia sprzedaży 3.
1. W okienku akcji na karcie **Popyt i podaż** wybierz grupę **Dodaj**, wybierz **Do istniejącego ładunku**, aby dodać wybrane wiersze zamówienia do istniejącego ładunku.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. W sekcji **Ładunki** znajdź i wybierz ładunek z poprzedniego kroku.
1. Wybierz **Zwolnienie \> Zwolnij do magazynu**.
1. W oknie dialogowym **Zwolnij ładunek do magazynu** wybierz **OK**, aby zwolnić wybrany ładunek do magazynu.
1. Przejdź do obszaru **Zarządzanie magazynem \> Praca \> Cała praca**, aby wyświetlić utworzoną pracę. Zanotuj wartość **Identyfikatora pracy**. Będziesz go używać w następnej procedurze.

### <a name="sales-order-picking-to-the-staging-location-for-the-third-shipment"></a>Pobieranie zamówienia sprzedaży do lokalizacji pośredniej dla trzeciej wysyłki

1. Zaloguj się do aplikacji mobilnej jako pracownik w magazynie *61*.
1. W menu głównym wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz opcję **Pobranie sprzedaży**.
1. Zaznacz pole **Identyfikator**, a następnie wprowadź identyfikator pracy dla trzeciej wysyłki.
1. Potwierdź wpis.
1. W polu **Numer identyfikacyjny** wprowadź numer identyfikacyjny dla pierwszej pozycji (*Mój numer identyfikacyjny 1*).
1. Potwierdź wpis.
1. W polu **Docelowy numer identyfikacyjny** wprowadź dowolny numer (docelowy numer identyfikacyjny nie musi jeszcze istnieć).
1. Potwierdź wpis.
1. W polu **Numer identyfikacyjny** wprowadź numer identyfikacyjny dla drugiej pozycji (*Mój numer identyfikacyjny 2*).
1. Potwierdź wpis.

    Jeśli chodzi o pierwszy ładunek, załóżmy, że pracownik stwierdzi, że określona lokalizacja pośrednia jest niedostępna. W związku z tym chce używać innej lokalizacji pośredniej (*ETAP04*).

1. Wybierz opcję **Zastąp lokalizację**, aby zastąpić sugerowaną lokalizację pośrednią.
1. W polu **Wyjątki pracy** określ *Ścieżka pośrednia uległa zmianie*.
1. W polu **Lokalizacja** wprowadź nową lokalizację pośrednią (*STAP04*).
1. Potwierdź wpis. Zostanie wyświetlony komunikat „Praca zakończona”.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca\> Wszystkie prace**.
1. Otwórz identyfikator pracy dla pierwszej wysyłki. Sprawdź, czy lokalizacja pośrednia nie została zaktualizowana do nowej lokalizacji pośredniej (*ETAP04*), ponieważ pozostały otwarty wiersz odłożenia nie jest zgodny z wierszem szablonu pracy ukończonego wiersza odłożenia.
1. Otwórz identyfikator pracy dla drugiej wysyłki. Sprawdź, czy lokalizacja pośrednia nie została zaktualizowana do nowej lokalizacji pośredniej (*ETAP04*), ponieważ lokalizacja pośrednia nie jest zgodna z lokalizacją pośrednią ukończonego wiersza odłożenia. Innymi słowy, ukończony wiersz pracy odłożenia i pozostały otwarty wiersz pracy mają różne lokalizacje pośrednie i w tym przypadku aktualizowane są tylko wiersze, które mają te same lokalizacje pośrednie.
1. Otwórz identyfikator pracy dla trzeciej wysyłki. Sprawdź, czy lokalizacja pośrednia została zaktualizowana do nowej lokalizacji pośredniej (*STAGE04*).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
