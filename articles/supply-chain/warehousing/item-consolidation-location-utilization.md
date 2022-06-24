---
title: Konsolidacja pozycji — wykorzystanie lokalizacji
description: Ten artykuł zawiera informacje o funkcjach ułatwiających menedżerom magazynów wyświetlanie i filtrowanie objętościowe wykorzystania lokalizacji w magazynie. Menedżerowie mogą wybierać lokalizacje i tworzyć pracę przesunięcia zapasów bezpośrednio na stronie konsolidacji towaru w celu konsolidowania towarów, a w ten sposób lepiej korzystać z przestrzeni magazynowej.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 63fd8b209cb73843aae7324c805c5d0eb83b4ca4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849192"
---
# <a name="item-consolidation---location-utilization"></a>Konsolidacja pozycji — wykorzystanie lokalizacji

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o funkcjach ułatwiających menedżerom magazynów wyświetlanie i filtrowanie objętościowe wykorzystania lokalizacji w magazynie. Menedżerowie mogą wybierać lokalizacje i tworzyć pracę przesunięcia zapasów bezpośrednio na stronie **Konsolidacji towaru** w celu konsolidowania towarów, a w ten sposób lepiej korzystać z przestrzeni magazynowej.

## <a name="turn-on-the-features"></a>Włączanie funkcji

Aby można było skorzystać z funkcji opisanych w tym artykule, należy je włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć je, jeśli istnieje taka potrzeba. Włącz obie następujące funkcje w kolejności, w jakiej są wymienione w systemie. (Obie funkcje dotyczą modułu **Zarządzania magazynem**.)

1. Stan lokalizacji w magazynie
2. Wykorzystanie lokalizacji konsolidacji pozycji

## <a name="warehouse-location-status"></a>Stan lokalizacji w magazynie

Funkcja *Stan lokalizacji w magazynie* dodaje cztery nowe pola do strony **Lokalizacje** w celu śledzenia dodatkowych informacji o bieżącym stanie lokalizacji:

- **Kod towaru** – pozycja aktualnie w lokalizacji. Jeśli lokalizacja zawiera wiele towarów, pole będzie puste.
- **Data i godzina ostatniego działania** – sygnatura czasowa ostatniej transakcji magazynowej, która została wykonana w odniesieniu do tej lokalizacji.
- **Data wieku** – Data, kiedy zapasy w lokalizacji zostały wprowadzone do magazynu. Ta data jest obliczana na podstawie daty wiekowania numeru identyfikacyjnego. Ta data dokładna w przypadku lokalizacji, w których numer identyfikacyjny jest śledzony, ale może być niedokładna w przypadku lokalizacji, dla których nie jest śledzony numer identyfikacyjny.
- **Stan lokalizacji** – stan lokalizacji. Cztery dostępne wartości:

    - **Nieokreślony** – Profil lokalizacji nie śledzi stanu. W związku z tym bieżący stan jest nieznany.
    - **Puste** – W tej lokalizacji nie ma obecnie żadnych zapasów.
    - **Pobieranie** – transakcje wychodzące zostały wykonane w odniesieniu do lokalizacji po jej opróżnieniu.
    - **Magazyn** – Tylko transakcje przychodzące zostały wykonane od kiedy lokalizacja była pusta.

Te pola umożliwiają kierownikom magazynu lepszy przegląd stanu lokalizacji w magazynie. Umożliwiają także bardziej zaawansowane raportowanie i filtrowanie.

## <a name="set-up-item-consolidation-and-location-utilization"></a>Ustawianie konsolidacja pozycji i wykorzystanie lokalizacji

W tej sekcji opisano sposób przygotowania systemu do użycia konsolidacji pozycji i wykorzystania lokalizacji. W procedurach są używane przykładowe wartości z standardowych danych demonstracyjnych. Jeśli planujesz pracę z przykładowym scenariuszem przedstawionym w dalszej części tego artykułu, wybierz firmę **USMF** (zawierającą standardowe dane demonstracyjne) i utwórz każdy rekord opisany w tej sekcji. Jeśli nie planujesz pracy za pomocą scenariusza przykładowego, podane tu wartości można traktować jako przykłady typów konfiguracji, które należy wykonać w celu użycia tych funkcji.

### <a name="released-product"></a>Zwolniony produkt

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. W polu **Identyfikator pozycji** wybierz opcję *M9201*, a następnie otwórz stronę szczegółów.
1. W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Magazyn** wybierz **Wymiary fizyczne**.
1. Na stronie **Wymiary fizyczne** w okienku akcji wybierz **Nowa**.

    Nowy wiersz zostanie dodany do siatki. Pole **Identyfikator pozycji** jest wstępnie ustawione.

1. W polu **Jednostka** zaznacz opcję *każdy*. Pozostałe pola w wierszu są ustawiane automatycznie.
1. Wybierz przycisk **Zapisz** i zamknij stronę.

### <a name="location-profile"></a>Profil lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
1. Z listy profilów lokalizacji wybierz opcję **PIĘTRO-05**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Ogólne** upewnij się, że obie następujące opcje są ustawione na wartość *Tak*:

    - Włącz obsługę towaru w lokalizacji
    - Włącz obsługę stanu lokalizacji

1. Wybierz opcję **Zapisz**.

    > [!IMPORTANT]
    > Jeśli dla opcji **Włącz przedmiot w lokalizacji** i **Włącz stan lokalizacji** została już ustawiona wartość *Tak*, przejdź na instrukcje dotyczące konfigurowania karty skróconej **Wymiary** w kroku 10. Jeśli opcje nie zostały jeszcze ustawione na wartość *Tak*, należy uruchomić sprawdzanie spójności modułu **Zarządzania magazynem** po ich ręcznym ustawieniu. W takim przypadku przejdź do następnego kroku.

1. Aby uruchomić sprawdzanie spójności, należy przejść do okna **Administracja systemu \> Okresowe zadania \> Baza danych \> Sprawdzania spójności**.
1. W wyświetlonym oknie dialogowym **Sprawdzanie spójności** można ustawić następujące wartości:

    - **Moduł:** *Zarządzanie magazynem*
    - **Sprawdź/napraw:** *Sprawdź*
    - **Od daty:** Zostaw to pole puste.
    - **Sprawdzanie spójności stanu lokalizacji w magazynie:** Zaznacz to pole wyboru.

1. Kliknij przycisk **OK**.

    > [!TIP]
    > Po zakończeniu sprawdzania spójności otrzymasz powiadomienie. Otwórz [Centrum akcji](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) w celu wyświetlenia wiadomości. Kliknij przycisk **Szczegóły komunikatu**, aby wyświetlić szczegóły.
    >
    > Jeśli komunikat dotyczący kontroli spójności brzmi: „Znaleziono nieprawidłowe informacje o statusie lokalizacji dla lokalizacji XXXX w magazynie XX”, należy ponownie przeprowadzić kontrolę spójności. W tym momencie należy zaznaczyć pole **Sprawdź/napraw**, aby *Naprawić błąd*. Wyświetl komunikaty, aby upewnić się, że nie znaleziono błędów.

1. Należy teraz zakończyć konfigurowanie profilu lokalizacji. Wróć do **Zarządzanie magazynem \> Konfiguracja \> Magazyn \> Profile lokalizacji**, wybierz profil lokalizacji **PIĘTRO-05**, a następnie w okienku akcji wybierz opcję **Edytuj**.
1. Na skróconej karcie **Wymiary** ustaw następujące wartości:

    - **Procent wykorzystania objętości:** *100*
    - **Metoda pomiarowa używana w lokalizacji zapasów:** *Użyj woluminu lokalizacji*
    - **Rzeczywista wysokość lokalizacji:** *10*
    - **Rzeczywista szerokość lokalizacji:** *10*
    - **Rzeczywista głębokość lokalizacji:** *10*
    - **Maksymalna waga:** *100*

1. Wybierz opcję **Zapisz**.

### <a name="mobile-device-menu-items"></a>Elementy menu urządzenia przenośnego

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć element menu do sortowania.
1. W nagłówku ustaw następujące wartości:

    - **Nazwa elementu menu:** *Dostosuj w*
    - **Tytuł:** *Dostosuj w*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Nie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Proces tworzenia pracy:** *Korekta w*
    - **Typy korekt zapasów:** *Korekta w*

1. Wybierz opcję **Zapisz**.

### <a name="mobile-device-menu"></a>Menu urządzeń przenośnych

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. Z listy menu wybierz opcję **Zapasy**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na liście **Dostępne menu i elementy menu** znajdź i zaznacz element menu **Dostosuj w**.
1. Wybierz strzałkę w prawo, aby przenieść **Dostosuj w** do listy **Struktura menu**. W ten sposób dodasz nowy element menu do wybranego menu.
1. Wybierz opcję **Zapisz**.

### <a name="movement-types"></a>Typy przeniesienia

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Typy przesunięcia**.
1. Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:

    - **Kod typu przesunięcia:** *KONSOLIDOWANIE*
    - **Opis:** *Konsoliduj lokalizacje*
    - **Identyfikator klasy roboczej:** *InvMov*

1. Wybierz opcję **Zapisz**.

## <a name="example-scenario"></a>Przykładowy scenariusz

W poniższym scenariuszu używana jest aplikacja Warehouse Management do tworzenia *korekt w* zapasów w dwóch lokalizacjach w magazynie.

### <a name="add-inventory-to-locations"></a>Dodaj zapasy do lokalizacji

1. Zaloguj się do urządzenia mobilnego jako użytkownik skonfigurowany dla magazynu *51*.
1. Przejdź do **Zapasy \> Dostosuj w**.

    Teraz będzie można wprowadzić pierwszą korektę lokalizacji.

1. W zadaniu **Korekta w** wybierz lokalizację, dla której ma zostać dokonana korekta zapasów. W polu **LOC** wybierz wartość *LP-001*.
1. Potwierdź lokalizację.
1. Utwórz identyfikator numeru identyfikacyjnego dla pozycji, która zostanie dodana do lokalizacji. W polu **Numer identyfikacyjny** wprowadź *LP00101*.
1. Potwierdź numer identyfikacyjny.
1. Wprowadź towar, który zostanie dodany do numeru identyfikacyjnego. W polu **ITEM** wprowadź *M9201*.
1. Potwierdź pozycję.
1. Wprowadź ilość pozycji, która zostanie dodana. W polu **ILOŚĆ** wprowadź *10*.
1. Potwierdź ilość.

    Zostanie wyświetlony komunikat „Praca zakończona”. Teraz będzie można wprowadzić drugą korektę lokalizacji.

1. W zadaniu **Korekta w** wybierz lokalizację, dla której ma zostać dokonana korekta zapasów. W polu **LOC** wybierz wartość *LP-002*.
1. Potwierdź lokalizację.
1. Utwórz identyfikator numeru identyfikacyjnego dla pozycji, która zostanie dodana do lokalizacji. W polu **Numer identyfikacyjny** wprowadź *LP00201*.
1. Potwierdź numer identyfikacyjny.
1. Wprowadź towar, który zostanie dodany do numeru identyfikacyjnego. W polu **ITEM** wprowadź *M9201*.
1. Potwierdź pozycję.
1. Wprowadź ilość pozycji, która zostanie dodana. W polu **ILOŚĆ** wprowadź *15*.
1. Potwierdź ilość.

    Zostanie wyświetlony komunikat „Praca zakończona”.

1. Wybierz przycisk menu (czasami nazywany przyciskiem Hamburger lub Hamburger), a następnie wybierz opcję **Anuluj**, aby zamknąć zadanie **Korekta w**.

### <a name="consolidate-locations"></a>Konsolidowanie lokalizacji

1. Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Konsolidacja pozycji**.
1. W nagłówku wybierz magazyn, dla którego ma być wykonana konsolidacja. W polu **Magazyn** wprowadź *51*.

    Rekord jest wyświetlany dla każdej lokalizacji, w której skorygowano pozycję *M9201*. Kolumna **Procent wykorzystania** wskazuje objętościowe wykorzystanie poszczególnych lokalizacji.

1. Aby skonsolidować zapasy, zaznacz wszystkie lokalizacje, które muszą zostać skonsolidowane, a następnie w okienku akcji wybierz opcję **Konsoliduj zapasy**.
1. W oknie dialogowym **Konsolidowanie zapasów** określ lokalizację i typ ruchu, który ma być używany do tworzenia pracy na potrzeby przesunięcia zapasów. Ustaw następujące wartości:

    - **Lokalizacja:** *LP-001*
    - **Kod typu przesunięcia:** *KONSOLIDOWANIE*

1. Kliknij przycisk **OK**.
1. Użytkownik otrzymuje komunikat informacyjny, który pokazuje utworzoną pracę przeniesienia. Zanotuj identyfikator pracy przeniesienia.

### <a name="view-movement-work"></a>Wyświetlanie pracy przeniesienia

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. Umożliwia wyświetlenie utworzonej pracy. Identyfikator pracy przepływu należy wykorzystać z konsolidacji zapasów w celu filtrowania lub wyszukiwania siatki pracy.

    W tym scenariuszu istniejąca lokalizacja, w której były zapasy, została użyta jako lokalizacja konsolidacji zapasów. W związku z tym utworzono tylko jeden identyfikator pracy.

    > [!NOTE]
   > System tworzy jeden identyfikator pracy dla każdego przeniesienia, które musi zostać ukończone. Jeśli zostanie określona lokalizacja, która już zawiera zapasy, zostanie utworzony tylko jeden identyfikator pracy. W przypadku określenia nowej lokalizacji tworzone są dwa identyfikatory pracy.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]