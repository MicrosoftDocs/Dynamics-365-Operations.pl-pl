---
title: Sortowanie towarów wychodzących
description: Ten temat zawiera informacje o sortowaniu towarów wychodzących. Ta funkcjonalność ułatwia obsługę małych pojemników i pomaga pracownikom magazynu lepiej planować i organizować pojemność palet w ciężarówce.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 84c4ec83ed16762e6c3c1a22425cf60e5b3ae8da
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435643"
---
# <a name="outbound-sorting"></a>Sortowanie towarów wychodzących

[!include [banner](../includes/banner.md)]

Ta funkcjonalność ułatwia obsługę małych pojemników i pomaga pracownikom magazynu lepiej planować i organizować pojemność palet w ciężarówce. W przypadku korzystania z sortowania wychodzącego można posortować spakowane kontenery na właściwej palecie, która znajduje się w stacji pakowania. Można również zbudować hierarchię pakowania.

Ta funkcja umożliwia tworzenie palet z kontenerów, które zostały zapakowane w ramach funkcji pakowania. Kontener nie jest wysyłany do końcowej lokalizacji wysyłki, ponieważ znajduje się w oryginalnym przepływie pakowania. Pracownicy mogą natomiast zamknąć kontener i przenieść go do lokalizacji typu sortowania. Następnie mogą sortować kontenery według pozycji, z których każda ma numer identyfikacyjny. Po posortowaniu kontenerów można pracować w celu wysłania całego numeru identyfikacyjnego do ostatecznej lokalizacji doku wysyłkowego lub na scenę, w ulotce o dyrektywy lokalizacyjne lub własne wymagania. Ponadto akcja zamknięcia pozycji sortowania może natychmiast przenieść zapasy do ostatecznej lokalizacji wysyłki i odebrać je do zamówienia.

## <a name="turn-on-the-outbound-sorting-feature"></a>Włącz funkcję sortowania wychodzącego

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Sortowanie wychodzące*

## <a name="setup"></a>Konfiguracja

W tym scenariuszu należy stosować standardowe dane demonstracyjne **USMF** oraz magazyn *62*. Należy również ukończyć konfigurację opisaną w poniższych podsekcjach.

### <a name="set-up-a-wave-template"></a>Konfigurowanie szablonu grupy czynności

Ta konfiguracja automatycznie przetwarza grupę czynności i tworzy pracę po zwolnieniu wiersza do magazynu.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. Na liście szablonów wybierz **Magazyn 62**.
1. Na skróconej karcie **Ogólne** należy upewnić się, że opcja **Przetwarzanie grupy czynności w czasie uwalniania jej do magazynu** jest ustawiona na wartość *Tak*.

### <a name="set-up-a-worker"></a>Konfigurowanie pracownika

Stacja pakowania jest traktowana jako lokalizacja. Pracownicy magazynowi, którzy logują się w stacji pakowania, widzą i pracują tylko w wysyłkach i kontenerach planowanych w danej lokalizacji pakowania. Użytkownik, który zarejestruje się w Microsoft Dynamics 365, musi być skonfigurowany jako pracownik w zarządzaniu magazynem. Jeśli na liście użytkowników pracy nie ma nazwy użytkownika, należy ją dodać, wykonując następującą procedurę:

> [!NOTE]
> W tych krokach przyjęto, że użytkownik już istnieje w systemie i jest skojarzony jako pracownik lub pracownik w module **Human Resources**.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**.
1. Wybierz pozycję **Nowy**.
1. W polu **Pracownik** wybierz użytkownika docelowego z listy pracowników.
1. Wybierz pozycję **Wybierz**.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Na skróconej karcie **Użytkownicy** wybierz opcję **Nowy**, aby utworzyć konto urządzenia przenośnego, i określ dla niego następujące wartości:

    - **Identyfikator użytkownika:** wprowadź unikatowy identyfikator.
    - **Nazwa użytkownika:** wprowadź nazwę identyfikatora.
    - **Magazyn domyślny:** *62*
    - **Nazwa menu:** *Główne*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Pojawi się okno dialogowe **Ustaw hasło**, w którym można utworzyć proste hasło, za pomocą którego użytkownik może zalogować w aplikacji mobilnej. Ustaw następujące wartości:

    - **Hasło:** wprowadź proste hasło.
    - **Potwierdź hasło:** Wprowadź ponownie to samo hasło.

1. Wybierz opcję **Ustaw hasło**.

    Powiadomienie w centrum akcji informuje o ustawieniu hasła dla utworzonego przez niego użytkownika.

### <a name="create-a-location-type"></a>Tworzenie typu lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Typy lokalizacji**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ lokalizacji, i określ dla niej następujące wartości:

    - **Typ lokalizacji:** *SORTOWANIE*
    - **Opis:** *Sortowanie*

1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-warehouse-management-parameters"></a>Konfigurowanie parametrów zarządzania magazynem

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na karcie **Ogólne**, na skróconej karcie **Typy lokalizacji** ustaw pole **Typ lokalizacji sortowania** na *Sortowanie*.
1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-a-location-profile"></a>Ustaw profil lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Identyfikator profilu lokalizacji:** *Sortowanie*
    - **Nazwa:** *Sortowanie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Format lokalizacji:** *ASRB* (korytarz— regał—półka—pojemnik)
    - **Typ lokalizacji:** *SORTOWANIE*
    - **Używaj śledzenia numeru identyfikacyjnego:** *Tak*
    - **Zezwalaj na towary mieszane:** *Tak* (Po ustawieniu tej opcji na wartość *Tak* opcja **Zezwalaj na mieszane partie zapasów** jest automatycznie ustawiana na wartość *Tak* i nie może być zmieniana niezależnie.)

1. Wybierz opcję **Zapisz**.

### <a name="set-up-a-location"></a>Ustaw lokalizację

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.
1. W nagłówku wyczyść pole wyboru **Generuj cyfry kontroli dla lokalizacji**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć lokalizację, i określ dla niej następujące wartości:

    - **Magazyn:** *62*
    - **Lokalizacja:** *SORT*
    - **Identyfikator profilu lokalizacji:** *SORTOWANIE*

1. Wybierz opcję **Zapisz**.

### <a name="set-up-an-outbound-sorting-template"></a>Ustaw szablon sortowania towarów wychodzących

Szablon sortowania towarów wychodzących określa, czy praca jest tworzona poza lokalizacją sortowania oraz czy sortowanie jest wykonywane ręcznie czy automatycznie.

W tym scenariuszu zostanie utworzony szablon sortowania towarów wychodzących w celu zbudowania palet po stacji pakowania.

1. Przejdź do **Zarządzanie magazynem \> Ustawienia \> Pakowanie \> Szablon sortowania towarów wychodzących**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku nowego szablonu określ następujące wartości:

    - **Identyfikator szablonu sortowania towarów wychodzących:** *Autopraca*
    - **Opis:** *Automatyczne tworzenie pracy*
    - **Typ szablonu sortowania towarów wychodzących:** *Kontener*
    - **Magazyn:** *62*
    - **Lokalizacja:** *SORT*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Typ weryfikacji sortowania:** *Skan pozycji*
    - **Utwórz pracę przy zamknięciu stanowiska:** *Tak*

        Jeśli opcja jest ustawiona na *Tak*, po zamknięciu stanowiska zostanie utworzona praca, aby przenieść zapasy do końcowej lokalizacji wysyłki. Jeśli opcja jest ustawiona na *Nie*, zapasy będą natychmiast pobierane dla zamówienia w momencie zamknięcia stanowiska.

    - **Przypisanie stanowiska:** *Automatyczne*

        W przypadku ustawienia tego pola na *Ręcznie* użytkownik musi zawsze wskazać, do którego stanowiska należy sortować zapasy. W przypadku ustawienia pola na *Automatycznie* system w miarę możliwości automatycznie poprowadzi zapasy do stanowiska na podstawie podziałów w szablonie sortowania.

1. Wybierz **Zapisz**, aby udostępnić opcję **Edytuj kwerendę** w okienku akcji.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W edytorze zapytań na karcie **Sortowanie** dodaj wiersz o następujących wartościach:

    - **Tabela:** *Wysyłki*
    - **Tabela pochodna:** *Wysyłki*
    - **Pole:** *Usługa przewozowa*

        Po wybraniu tej wartości może zostać wyświetlony następujący komunikat: „Usługa przewoźnika nie jest polem indeksu. Czy na pewno chcesz dodać sortowanie według tego kryterium?” Wybierz opcję **Tak**.

    - **Kierunek wyszukiwania:** *Rosnąco*

1. Kliknij przycisk **OK**.
1. Może zostać wyświetlony następujący komunikat: „Grupowanie zostanie zresetowane, czy chcesz kontynuować?” Wybierz opcję **Tak**.

    W okienku akcji zostanie udostępniony przycisk **Podziały szablonu sortowania towarów wychodzących**.

1. W okienku akcji wybierz pozycję **Podziały szablonu sortowania towarów wychodzących**.
1. W wyświetlonym oknie dialogowym **Kryteria sortowania towarów wychodzących** można ustawić następujące wartości:

    - **Nazwa tabeli odwołania:** *Wysyłki*
    - **Nazwa pola odwołania:** *Usługa przewoźnika*
    - **Grupuj według pola:** Należy zaznaczyć to pole wyboru, aby pogrupować wysyłki według usługi przewozowej.

1. Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okienko dialogowe.

### <a name="set-up-container-packing-policies"></a>Ustawianie zasad pakowania kontenerów

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Zasady pakowania kontenera**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku nowej zasady określ następujące wartości:

    - **Zasady pakowania kontenerów:** *Sortowanie*
    - **Opis:** *Sortowanie*

1. Na skróconej karcie **Omówienie** ustaw następujące wartości:

    - **Magazyn:** *62*
    - **Domyślna lokalizacja do sortowania:** *SORTOWANIE*
    - **Jednostka wagi:** *kg*
    - **Zasada zamykania kontenera:** *Automatyczne zwalnianie*
    - **Zasady zwalniania kontenerów:** *Przypisz kontener do pozycji sortowania towarów wyjściowych*

1. Wybierz opcję **Zapisz**.

### <a name="set-up-packing-profiles"></a>Konfigurowanie profili pakowania

Utwórz nowy profil pakowania, który będzie używany razem z funkcją sortowania.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Profile pakowania**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć linię, i określ dla niej następujące wartości:

    - **Identyfikator profilu pakowania:** *Sortowanie*
    - **Opis:** *Sortowanie*
    - **Zasady pakowania kontenerów:** *Sortowanie*
    - **Tryb identyfikatora kontenera:** *Automatyczny*
    - **Typ kontenera:** *Pudełko-duże*
    - **Automatycznie utwórz kontener przy zamknięciu kontenera:** Wyczyszczone (= *Nie*)

1. Wybierz opcję **Zapisz**.

### <a name="set-up-work-classes"></a>Ustaw klasy pracy

Umożliwia skonfigurowanie klasy pracy, która będzie używana razem z sortowaniem.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć klasę pracy dla sortowania, i określ dla niej następujące wartości:

    - **Identyfikator klasy roboczej:** *Sortowanie*
    - **Opis:** *Sortowanie*
    - **Typ zlecenia pracy:** *Szablon pracy pobrania z posortowanych zapasów*

1. Wybierz opcję **Zapisz**.

### <a name="set-up-mobile-device-menu-items"></a>Konfigurowanie elementów menu urządzenia przenośnego

#### <a name="set-up-a-new-pallet-menu-item"></a>Konfigurowanie elementu menu nowej palety

Umożliwia utworzenie elementu menu urządzenia przenośnego w celu zbudowania palet podczas sortowania.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Nazwa elementu menu:** *kompilacja palety*
    - **Tytuł:** *kompilacja palety*
    - **Tryb:** *Pośrednie*
    - **Używanie istniejącej pracy:** *Nie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Kod działania:** *Sortowanie towarów wychodzących*

        Jeśli to pole jest ustawione na wartość *Sortowanie towarów wychodzących*, wyświetlane jest pole **Identyfikator szablonu sortowania towarów wychodzących**.

    - **Użyj przewodnika procesu:** *Tak*

        Jeśli w polu **Kod działania** wybrano opcję *Sortowanie towarów wychodzących*, ta opcja jest automatycznie ustawiana na wartość *Tak*.

    - **Identyfikator szablonu sortowania towarów wychodzących:** *Autopraca*

1. Wybierz opcję **Zapisz**.

#### <a name="set-up-a-new-loading-menu-item"></a>Konfigurowanie elementu menu nowego ładowania

Następnie Utwórz element menu, który pozwoli użytkownikom przenieść posortowane towary magazynowe do lokalizacji wysyłki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Nazwa elementu menu:** *ładowanie z sortowania*
    - **Tytuł:** *ładowanie z sortowania*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Tak*

1. Na skróconej karcie **Ogólne**, pole **Sterowane przez** powinno być ustawione na wartość *Sterowane przez użytkownika*.
1. Na skróconej karcie **Klasy pracy** wybierz opcję **Nowy**, a następnie określ następujące wartości:

    - I **dentyfikator klasy pracy:** *SORTOWANIE*
    - **Typ zlecenia pracy:** *Szablon pracy pobrania z posortowanych zapasów*

1. Wybierz opcję **Zapisz**.

### <a name="set-up-the-mobile-device-menu"></a>Konfigurowanie menu urządzenia przenośnego

Teraz musisz dodać nowe elementy menu do menu urządzenia przenośnego.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. Wybierz menu **Wychodzące**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. W kolumnie **Dostępne menu i elementy menu** znajdź i zaznacz opcję **Kompilacja palety**.
1. Wybierz strzałkę w prawo, aby przenieść **Kompilacja palety** do kolumny **Struktura menu**.
1. Za pomocą przycisków Strzałka w górę i Strzałka w dół można umieścić element menu **Kompiluj paletę** w wybranym miejscu w menu urządzenia przenośnego.
1. Wybierz opcję **Zapisz**.
1. Powtórz tę procedurę, aby dodać element menu **Ładowanie z sortowania** do menu **Towary wychodzące**.

### <a name="set-up-location-directives"></a>Ustaw dyrektywy lokalizacji

*Dyrektywy lokalizacji* to zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego. Teraz musisz utworzyć regułę, aby zarządzać pracą sortowania.

#### <a name="set-up-a-single-sku-directive"></a>Konfigurowanie pojedyńczej dyrektywy SKU

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W lewym okienku zmień wartość pola **Typ zlecenia pracy** na *Pobranie z posortowanych zapasów*.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Sekwencja:** *1*
    - **Nazwa:** *Baydoor*

1. Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości:

    - **Typ pracy:** *Odłożenie*
    - **Oddział:** *6*
    - **Magazyn:** *62*
    - **Wiele jednostek SKU:** *Nie*

1. Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Wiersze** stał się dostępny.
1. Na skróconej karcie **Wiersze** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu: Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Sekwencja:** *1*
    - **Od:** *0*
    - **Do:** *1 000 000*

1. Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Dyrektywy akcji lokalizacji** stał się dostępny.
1. Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu: Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Sekwencja:** *1*
    - **Nazwa:** *Baydoor*

1. Wybierz opcję **Zapisz**.
1. Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.
1. W edytorze zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** ma wartość *Lokalizacja*. Umożliwia ustawienie pola **Kryterium** dla tego wiersza na *Baydoor*.
1. Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okno dialogowe kwerendy.

#### <a name="set-up-a-multiple-sku-directive"></a>Konfigurowanie wielu dyrektyw SKU

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W lewym okienku zmień wartość pola **Typ zlecenia pracy** na *Pobranie z posortowanych zapasów*.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Sekwencja:** *2*
    - **Nazwa:** *Baydoor Multi*

1. Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości:

    - **Typ pracy:** *Odłożenie*
    - **Oddział:** *6*
    - **Magazyn:** *62*
    - **Wiele SKU:** *Tak*

1. Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Wiersze** stał się dostępny.
1. Na skróconej karcie **Wiersze** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu: Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Sekwencja:** *1*
    - **Od:** *0*
    - **Do:** *1 000 000*

1. Wybierz opcję **Zapisz**, aby pasek narzędzi na skróconej karcie **Dyrektywy akcji lokalizacji** stał się dostępny.
1. Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz opcję **Nowy**, a następnie określ następujące wartości w nowym wierszu: Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Sekwencja:** *1*
    - **Nazwa:** *Baydoor Multi*

1. Wybierz opcję **Zapisz**.
1. Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.
1. W edytorze zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** ma wartość *Lokalizacja*. Umożliwia ustawienie pola **Kryterium** dla tego wiersza na *Baydoor*.
1. Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okno dialogowe kwerendy.

### <a name="set-up-work-templates"></a>Ustaw szablony pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. Zmień wartość pola **Typ zlecenia pracy** na *Pobranie z posortowanych zapasów*.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć szablon.
1. Na karcie **Omówienie** ustaw następujące wartości:

    - **Sekwencja:** *1*
    - **Szablon pracy:** *Sortowanie*
    - **Opis szablonu pracy:** *Sortowanie*

1. Wybierz opcję **Zapisz**, aby skrócona karta **Szczegóły szablonu pracy** stała się dostępna.
1. Na skróconej karcie **Szczegóły szablonu pracy** wybierz opcję **Nowy**, aby dodać wiersz, a następnie określ dla niego następujące wartości:

    - **Typ pracy:** *Pobranie*
    - I **dentyfikator klasy pracy:** *SORTOWANIE*

1. Wybierz znowu **Nowe** i określ następujące wartości:

    - **Typ pracy:** *Odłożenie*
    - I **dentyfikator klasy pracy:** *SORTOWANIE*

1. Wybierz opcję **Zapisz**.

## <a name="scenario"></a>Scenariusz

Ten scenariusz symuluje sytuację, w której spakowane kontenery powinny być automatycznie sortowane według różnych stanowisk (palet) po stanowisku pakowania, w zależności od usługi firmy przewozowej. Po zapełnieniu wszystkich towarów z ładunku i posortowaniu ich według adresu paleta zostanie przeniesiona do bramy dokowej.

### <a name="create-sales-orders-and-picking-work"></a>Tworzenie zlecenia pracy i pobierania zamówienia sprzedaży

#### <a name="create-sales-order-1"></a>Utwórz zamówienie sprzedaży 1

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-005*
    - **Magazyn:** *62*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

    Nowe zamówienie zakupu (PO) zostało otwarte.

1. Przełącz do widoku **nagłówka**.
1. Na skróconej karcie **Dostawa** w sekcji **Transport** należy określić następujące wartości:

    - **Przewoźnik:** *Transport lotniczy*
    - **Usługa przewozowa:** *Lotnicza*

1. Przełącz się do widoku **Wiersz**.
1. Jeśli nowy wiersz nie został dodany automatycznie do siatki na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać.
1. Dla nowego wiersza zamówienia należy określić następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *2*

1. Gdy nowy wiersz zamówienia jest wciąż wybrany na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.
1. Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia. Zanotuj identyfikator grupy czynności i numery identyfikacyjne przesyłki.

#### <a name="sales-order-2"></a>Zamówienie sprzedaży 2

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-006*
    - **Magazyn:** *62*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Powinno zawierać pusty wiersz w siatce na skróconej karcie **Wiersze zamówienia sprzedaży**. Ustaw następujące wartości w tym wierszu zamówienia:

    - **Pozycja:** *A0001*
    - **Ilość:** *1*

1. Na skróconej karcie **Szczegółów wiersza** na karcie **Dostawa** należy określić wartość w polu **Metoda dostawy** na *Flowe-STD*.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, a następnie określ następujące wartości w drugim wierszu:

    - **Pozycja:** *A0002*
    - **Ilość:** *1*

1. Na skróconej karcie **Szczegółów wiersza** na karcie **Dostawa** należy zmienić wartość w polu **Metoda dostawy** na *Air C-Air*.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz pierwszy wiersz zamówienia. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz drugi wiersz zamówienia. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.
1. Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia. Zwróć uwagę, że utworzono dwa numery identyfikacyjne grupy czynności i dwa numery identyfikacyjne przesyłki, po jednym dla każdego trybu dostawy dla wierszy zamówienia sprzedaży.

#### <a name="get-the-work-ids-from-the-work-details"></a>Pobierz identyfikatory pracy z szczegółów pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. Na stronie są wyświetlane identyfikatory pracy, które zostały utworzone na podstawie zamówień sprzedaży. Identyfikatory grupy czynności i identyfikatory wysyłki można stosować w utworzonych zamówieniach sprzedaży w celu znalezienia identyfikatora pracy dla każdej grupy czynności i wysyłki. Zapisz identyfikatory pracy, ponieważ są one potrzebne w następnych krokach. Zwróć uwagę, że utworzono dwa identyfikatory pracy dla drugiego zamówienia sprzedaży. Jeśli różne towary są pobierane z różnych lokalizacji, generowane są oddzielne identyfikatory słowne.

### <a name="pick-items-for-the-sales-orders"></a>Wybierz towary dla zamówień sprzedaży

Zakończ utworzoną pracę, korzystając z urządzenia przenośnego, aby przenieść elementy do stacji pakowania.

1. Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).
1. W menu głównym wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz opcję **Pobranie sprzedaży**.
1. W polu **Identyfikator** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży 1.
1. Kliknij przycisk **OK**.
1. Na stronie **Zamówień sprzedaży - Pobranie** wprowadź docelowy numer identyfikacyjny, który został utworzony dla zamówienia sprzedaży 1. Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*masowo-001*), pozycja (*A0001*) oraz ilość (*2 sztuki*).
1. Kliknij przycisk **OK**.
1. Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**. Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *Pakunek*.
1. Kliknij przycisk **OK**.

    Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”, który wskazuje, że identyfikator pracy z zamówienia sprzedaży 1 został zakończony.

    Teraz zostanie pobrane zamówienie sprzedaży 2.

1. W polu **Identyfikator** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży 2, gdzie wiersz 1 ma element *A0001*.
1. Kliknij przycisk **OK**.
1. Na stronie **Zamówień sprzedaży - Pobranie** wprowadź docelowy numer identyfikacyjny. Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*masowo-001*), pozycja (*A0001*) oraz ilość (*1 sztuki*).
1. Kliknij przycisk **OK**.
1. Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**. Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *Pakunek*.
1. Kliknij przycisk **OK**.

    Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”. Ten komunikat wskazuje, że wykonano identyfikator pracy z wiersza 1 zamówienia sprzedaży 2.

1. W polu **Identyfikator** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży 2, gdzie wiersz 2 ma element *A0002*.
1. Kliknij przycisk **OK**.
1. Na stronie **Zamówień sprzedaży - Pobranie** wprowadź docelowy numer identyfikacyjny. Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*masowo-002*), pozycja (*A0001*) oraz ilość (*1 sztuki*).
1. Kliknij przycisk **OK**.
1. Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**. Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *Pakunek*.
1. Kliknij przycisk **OK**.

    Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”. Ten komunikat wskazuje, że wykonano identyfikator pracy z wiersza 2 zamówienia sprzedaży 2.

### <a name="pack-sales-orders-into-containers"></a>Pakowanie zamówień sprzedaży do kontenerów

#### <a name="pack-sales-order-1-into-containers"></a>Pakowanie zamówienia 1 sprzedaży do kontenerów

1. Przejdź do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Pakunek**.

    Wyświetli się okno dialogowe **Wybierz stację pakowania**. Domyślnie pole **Pracownik** powinno mieć ustawioną nazwę pracownika skonfigurowanego wcześniej.

1. Poniższe wartości umożliwiają wyświetlanie i pracę z wysyłkami i kontenerami planowanymi w określonej lokalizacji pakowania:

    - **Oddział:** *6*
    - **Magazyn:** *62*
    - **Lokalizacja:** *Pakiet*
    - **Identyfikator profilu pakowania:** *Sortowanie*

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. Na stronie **Pakiet**, w polu **Numer identyfikacyjny lub wysyłka**, wprowadź docelowy numer identyfikacyjny dla zamówienia sprzedaży 1. Następnie należy wybrać **Kartę** lub klawisz **Enter** na klawiaturze w celu wychodzenia z pola.
1. W okienku akcji wybierz opcję **Nowy kontener**.
1. Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**. Zanotuj identyfikator kontenera.
1. Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:

    - **Ilość:** *1*
    - **Identyfikator:** pozycja *A0001*

1. W okienku akcji wybierz opcję **Zamknij kontener**.
1. W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.
1. Kliknij przycisk **OK**. Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.
1. Utwórz drugi kontener, aby dodać drugi towar z numeru identyfikacyjnego dla zamówienia sprzedaży 1 do nowego kontenera.
1. W okienku akcji wybierz opcję **Nowy kontener**.
1. Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**. Zanotuj identyfikator kontenera.
1. Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:

    - **Ilość:** *1*
    - **Identyfikator:** pozycja *A0001*

1. W okienku akcji wybierz opcję **Zamknij kontener**.
1. W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.
1. Kliknij przycisk **OK**. Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.

#### <a name="pack-sales-order-2-into-containers"></a>Pakowanie zamówienia 2 sprzedaży do kontenerów

1. Na stronie **Pakiet**, w polu **Numer identyfikacyjny lub wysyłka**, wprowadź docelowy numer identyfikacyjny dla wiersza 1 zamówienia sprzedaży 2. Następnie należy wybrać **Kartę** lub klawisz **Enter** na klawiaturze w celu wychodzenia z pola.
1. W okienku akcji wybierz opcję **Nowy kontener**.
1. Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**. Zanotuj identyfikator kontenera.
1. Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:

    - **Ilość:** *1*
    - **Identyfikator:** pozycja *A0001*

1. W okienku akcji wybierz opcję **Zamknij kontener**.
1. W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.
1. Kliknij przycisk **OK**. Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.
1. Wpolu **Numer identyfikacyjny lub wysyłka**, wprowadź docelowy numer identyfikacyjny dla wiersza 2 zamówienia sprzedaży 2. Następnie należy wybrać **Kartę** lub klawisz **Enter** na klawiaturze w celu wychodzenia z pola.
1. W okienku akcji wybierz opcję **Nowy kontener**.
1. Zaakceptuj wszystkie ustawienia domyślne i kliknij przycisk **OK**. Zanotuj identyfikator kontenera.
1. Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:

    - **Ilość:** *1*
    - **Pole identyfikatora:** pozycja *A0002*

1. W okienku akcji wybierz opcję **Zamknij kontener**.
1. W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby zaktualizować pole **Waga brutto**.
1. Kliknij przycisk **OK**. Kontener zostanie przeniesiony do lokalizacji *SORTOWANIA* i będzie gotowy do sortowania.

Aby wyświetlić szczegóły kontenera, należy przejść do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Kontenery** oraz wyszukać identyfikatory kontenerów, które zostały utworzone podczas pakowania.

### <a name="sort-the-containers"></a>Sortowanie kontenerów

> [!IMPORTANT]
> Po dostępie do elementu menu **Kompilacja palety** w aplikacji mobilnej do sortowania wychodzącego wyświetlany jest przycisk z etykietą **Pełna**. *Nie używaj przycisku **Pełne** do sortowania lub zamykania stanowiska.*
>
> Przycisk **Pełny** jest domyślnie dostępny i nie można go wyłączyć ani usunąć ze strony. Nie jest używany dla funkcji *Sortowanie towarów wychodzących*.

#### <a name="sort-the-first-container"></a>Sortuj pierwszy kontener

1. Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).
1. W menu głównym wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz opcję **Kompilacja palety**.
1. W polu **LP/Con** wprowadź pierwszy identyfikator kontenera skojarzony z zamówieniem sprzedaży 1.
1. Kliknij przycisk **OK**.
1. Ponieważ nie istnieją obecnie pozycje sortowania, należy je określić. W polu **Identyfikator stanowiska sortowania** wprowadź *SP01*.
1. Ponieważ żaden numer identyfikacyjny nie jest aktualnie skojarzony z pozycją sortowania *SP01*, należy określić jeden z nich. W polu **Numer identyfikacyjny** wprowadź *PLP01*.
1. Kliknij przycisk **OK**.
1. Ponieważ sprawdzanie poprawności pozycji sortowania jest włączone, należy ponownie wprowadzić identyfikator pozycji sortowania. W polu **Identyfikator stanowiska sortowania** wprowadź *SP01*.
1. Kliknij przycisk **OK**.

    Zostanie wyświetlony komunikat „Praca zakończona”.

> [!TIP]
> Aby wyświetlić pozycję sortowania i numer identyfikacyjny w tym celu należy przejść do pola pakowanie w **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Przypisania stanowisk sortowania towarów wychodzących**.
>
> Na stronie **Przypisania stanowisk sortowania towarów wychodzących** wyświetlane są wszystkie stanowiska, które są obecnie aktywne. W polu **Transakcja na stanowisku sortowania** wyświetlany jest numer numer identyfikacyjny skojarzony z poszczególnymi pozycjami sortowania oraz kontenery znajdujące się na położeniu sortowania. Zauważ, że jedna pozycja sortowania już istnieje, a skrócona karta **Kryteria stanowiska sortowania** przedstawia kryterium **Wysyłka - usługa przewoźnika - powietrze**.

#### <a name="sort-the-remaining-containers"></a>Posortuj pozostałe pojemniki

1. Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).
1. W menu głównym wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz opcję **Kompilacja palety**.
1. W polu **LP/Con** wprowadź drugi identyfikator kontenera skojarzony z zamówieniem sprzedaży 1.
1. Kliknij przycisk **OK**. Ponieważ szablon sortowania jest skonfigurowany do automatycznego sortowania, a pozycja sortowania, która ma kryteria dopasowywania, już istnieje, jest automatycznie kierowana do właściwej pozycji sortowania.
1. Kliknij przycisk **OK**.
1. Potwierdź identyfikator stanowiska sortowania, aby wskazać, że ilość zapasów znajduje się w odpowiednim miejscu. W polu **Identyfikator stanowiska sortowania** wprowadź *SP01*.
1. Kliknij przycisk **OK**.

    Praca została zakończona dla drugiego kontenera z zamówienia sprzedaży 1. Teraz zostaną posortowane pozostałe kontenery z zamówienia sprzedaży 2.

1. W polu **LP/Con** wprowadź identyfikator kontenera z zamówienia sprzedaży 2, który zawiera pozycję *A0001*. Ponieważ usługa przewoźnika jest inna, system wyświetli monit o wprowadzenie nowej pozycji sortowania i przypisanie do tego stanowiska obiektu numer identyfikacyjny. Należy skorzystać z pozycji sortowania *SP02* i numer identyfikacyjny *PLP02*.
1. Kliknij przycisk **OK**.
1. Potwierdź pozycję sortowania, wprowadzając *SP02* w polu **Identyfikator pozycji sortowania**.
1. Kliknij przycisk **OK**.

    Praca w kontenerze została zakończona.

1. W polu **LP/Con** wprowadź identyfikator ostatniego kontenera z zamówienia sprzedaży 2, który zawiera pozycję *A0002*. Ponieważ usługa przewoźnika jest taka sama jak usługa przewoźnika dla zamówienia sprzedaży 1, system pokazuje istniejącą pozycję sortowania, która ma kryteria dopasowywania.
1. Kliknij przycisk **OK**.
1. Potwierdź pozycję sortowania, wprowadzając *SP01* w polu **Identyfikator pozycji sortowania**.
1. Kliknij przycisk **OK**.

    Praca w kontenerze została zakończona.

### <a name="close-the-outbound-sorting-positions"></a>Zamknij wychodzące pozycje sortowania

Po posortowaniu wszystkich zapasów należy zamknąć to stanowisko, aby można było utworzyć pracę. Zostaną utworzone posortowane prace związane z pobieraniem zapasów, aby przenieść je do bramy dokowej.

#### <a name="close-a-position-from-the-mobile-device"></a>Zamykanie stanowiska z urządzenia przenośnego

1. Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).
1. W menu głównym wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz opcję **Kompilacja palety**.
1. W polu **LP/Con** wprowadź identyfikator kontenera, który został posortowany w celu posortowania pozycji *SP01*.
1. Kliknij przycisk **OK**.
1. Pojawi się następujący komunikat: „Kontener jest już posortowany do stanowiska SP01. Zamknąć to stanowisko?” Kliknij przycisk **Zamknij**.

    Praca została zakończona.

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a>Zamykanie stanowiska z przypisań pozycji sortowania wychodzącego

1. Należy przejść do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Przypisania stanowisk sortowania towarów wychodzących**.
1. W lewej kolumnie wybierz **SP02**. Ten wiersz określający pozycję sortowania dla zapasów wychodzących jest tym, który zostanie zamknięty.
1. W okienku akcji wybierz opcję **Zamknij stanowisko**. Rekord stanowiska sortowania jest zamknięty i nie jest już wyświetlany.

    > [!TIP]
    > Aby wyświetlić wszystkie rekordy zamkniętych stanowisk, zaznacz pole wyboru **Wyświetl zamknięte**.

### <a name="sorted-inventory-picking"></a>Pobranie z posortowanych zapasów

Należy wykonać posortowaną pracę pobrania z magazynu. Po zakończeniu Inwentaryzacja zostanie pobrana do zamówienia sprzedaży. W tym momencie obowiązują wszystkie inne procesy magazynowe.

1. Na urządzeniu przenośnym zaloguj się do magazynu *62*, używając identyfikatora użytkownika utworzonego dla tego scenariusza (lub identyfikatora użytkownika dla istniejącego użytkownika danych demonstracyjnych).
1. W menu głównym wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz opcję **Ładowanie z sortowania**.
1. Wprowadź identyfikator docelowego z pierwszej pozycji sortowania, *SP01*. Ustaw wartość w polu **Identyfikator** na *PLP01*.
1. Kliknij przycisk **OK**.
1. Strona **Odbieranie sortowanych zapasów: Odbiór** zawiera listę prac pobrań, które muszą zostać wykonane. Pobranie z lokalizacji *SORTOWANIE* i docelowego numeru identyfikacyjnego *PLP01*, który ma wiele towarów i ilość *3*.
1. Kliknij przycisk **OK**.
1. Strona **Odbieranie sortowanych zapasów: Odłożenie** zawiera listę prac odkładania, które muszą zostać wykonane. Odkładanie z lokalizacji *Baydoor* i docelowego numeru identyfikacyjnego *PLP01*, który ma wiele towarów i ilość *3*.
1. Kliknij przycisk **OK**.

    Praca została zakończona.

1. Wprowadź docelowy numer identyfikacyjny z drugie pozycji sortowania, *SP02*. Ustaw wartość w polu **Identyfikator** na *PLP02*.
1. Kliknij przycisk **OK**.
1. Strona **Odbieranie sortowanych zapasów: Odbiór** zawiera listę prac pobrań, które muszą zostać wykonane. Pobranie z lokalizacji *SORTOWANIE* i docelowego numeru identyfikacyjnego *PLP02*, który ma wiele towarów i ilość *1*.
1. Kliknij przycisk **OK**.
1. Strona **Odbieranie sortowanych zapasów: Odłożenie** zawiera listę prac odkładania, które muszą zostać wykonane. Odkładanie z lokalizacji *Baydoor* i docelowego numeru identyfikacyjnego *PLP02*, który ma wiele towarów i ilość *1*.
1. Kliknij przycisk **OK**.

    Praca została zakończona.

Od tego momentu obowiązują wszystkie inne procesy magazynowe.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]