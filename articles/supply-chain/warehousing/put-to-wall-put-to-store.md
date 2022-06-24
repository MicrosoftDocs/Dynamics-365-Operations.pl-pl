---
title: Umieść na ścianie - odłożenie do sklepu
description: Ten artykuł zawiera informacje o funkcji Umieść na ścianie - odłóż do sklepu. Ta funkcja umożliwia obsługę scenariuszy, w których trzeba skonsolidować produkt do obszaru tymczasowego na podstawie kryteriów konfigurowalnych. Umożliwia skrócenie czasu pobrania, ponieważ umożliwia pobranie go do jednego docelowego numeru identyfikacyjnego i może spowodować użycie większej liczby stanowisk niż pobranie w klastrze.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: e020bd3973b8b56dd1e6f3e5bdc8cba32600f7f8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909651"
---
# <a name="put-to-wall---put-to-store"></a>Umieść na ścianie - odłożenie do sklepu

[!include [banner](../includes/banner.md)]

Funkcja *Umieść na ścianie - odłożenie do sklepu* umożliwia obsługę scenariuszy, w których trzeba skonsolidować produkt do obszaru tymczasowego na podstawie kryteriów konfigurowalnych. Ponieważ ta funkcja umożliwia pobranie do jednego docelowego numeru identyfikacyjnego i może korzystać z większej liczby stanowisk niż pobieranie w klastrze, firmy, które mają być przeznaczone do przechowywania lub obsługi małych towarów, będą korzystać ze zmniejszonego czasu pobierania.

Przepływ pracy dla tej funkcji umożliwia kierowanie pobranego produktu do lokalizacji sortowania w różnych typach kontenerów. Na ogół każda lokalizacja sortowania zawiera wiele stanowisk sortowania. Każda pozycja sortowania jest przypisywana zgodnie z kryteriami określonymi przez proces biznesowy. Typowymi kryteriami są ostateczne miejsce docelowe, wysyłka lub obciążenie. Po dostarczeniu produktu jest on dystrybuowany do każdego stanowiska sortowania na podstawie ilości skojarzonej z zamówieniem, miejscem docelowym, wysyłką lub obciążeniem. Gdy kontener jest pełny lub kompletny, jest on przenoszony do lokalizacji przemieszczania lub do lokalizacji wysyłki w celu dalszej obsługi, w zależności od procesu biznesowego.

Ta funkcja magazynowania jest również nazywana innymi nazwami, takimi jak otwarcie funkcji odłożenie-lekkie i przerwanie.

## <a name="turn-on-the-outbound-sorting-feature"></a>Włącz funkcję sortowania wychodzącego

Zanim będzie możliwe użycie funkcji przekazanie *Umieść na ścianie - odłożenie do sklepu*, funkcja *Sortowanie towarów wychodzących* musi być włączona w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Sortowanie wychodzące*

Funkcja *Sortowanie towarów wychodzących* może być używana w połączeniu z funkcją *Kod kroku grupy czynności dotyczący całej organizacji:*, jeśli jest włączona. Należy również włączyć tę funkcję, jeśli będą używane wstępnie zdefiniowane kody skonfigurowane w kodach kroków grupy czynności. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Kod kroku grupy czynności dotyczący całej organizacji*

## <a name="setup"></a>Konfiguracja

W przypadku tego pokazu używane są standardowe dane firmy Contoso i magazyn *62*. Używane są również niektóre dodatki, które zostały przedstawione później.

### <a name="location-type"></a>Typ lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Typy lokalizacji**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ lokalizacji służący do sortowania.
1. Ustaw następujące wartości:

    - **Typ lokalizacji:** *SORTOWANIE*
    - **Opis:** *Sortowanie*

1. Wybierz opcję **Zapisz**.

### <a name="warehouse-management-parameters"></a>Parametry zarządzania magazynem

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na karcie **Ogólne**, na skróconej karcie **Typy lokalizacji** w polu **Typ lokalizacji sortowania** wpisz *Sortowanie*.
1. Wybierz opcję **Zapisz**.

### <a name="location-profile"></a>Profil lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć profil lokalizacji dla lokalizacji sortowania.
1. W nagłówku ustaw następujące wartości:

    - **Identyfikator profilu lokalizacji:** *Sortowanie*
    - **Nazwa:** *Sortowanie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Format lokalizacji:** *PACK*
    - **Typ lokalizacji:** *SORTOWANIE*
    - **Używaj śledzenia numeru identyfikacyjnego:** *Tak*
    - **Pozwól na mieszane pozycje:** *Yes*
    - **Zezwalaj na mieszane stany zapasów:** *Tak*

1. Wybierz opcję **Zapisz**.

### <a name="locations"></a>Lokalizacje

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.
1. Wyczyść pole wyboru **Generuj cyfry kontroli dla lokalizacji**.
1. Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:

    - **Magazyn:** *62*
    - **Lokalizacja:** *Sortowanie*
    - **Identyfikator profilu lokalizacji:** *Sortowanie*

1. Wybierz opcję **Zapisz**.

### <a name="packing-profiles"></a>Profile pakowania

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Profile pakowania**.
1. Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:

    - **Identyfikator profilu pakowania:** *Sortowanie*
    - **Opis:** *Sortowanie*
    - **Zasady pakowania kontenerów:** Pozostaw to pole puste.
    - **Tryb identyfikatora kontenera:** *Automatyczny*
    - **Typ kontenera:** *PALETA 48X48*
    - **Utwórz automatycznie kontener przy zamknięciu kontenera:** Pozostaw to pole puste.

1. Wybierz opcję **Zapisz**.

### <a name="wave-step-codes"></a>Kody kroku grupy czynności

Po włączeniu funkcji *Kod kroku grupy czynności dotyczący całej organizacji* należy skonfigurować poniższy kod.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Kody kroku grupy czynności**.
1. Wybierz opcję **Nowe** w okienku akcji, a następnie określ następujące wartości:

    - **Kod kroku grupy czynności:** *Sortowanie*
    - **Opis kroku grupy czynności:** *Sortowanie*
    - **Typ kroku grupy czynności:** *Szablon sortowania*

1. Wybierz opcję **Zapisz**.

### <a name="outbound-sorting-template"></a>Szablon sortowania towarów wychodzących

Szablon sortowania określa, czy są tworzone pozycje sortowania, używane kryteria oraz inne atrybuty procesu sortowania.

1. Przejdź do **Zarządzanie magazynem \> Ustawienia \> Pakowanie \> Szablon sortowania towarów wychodzących**.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć szablon sortowania.
1. W nagłówku nowego szablonu określ następujące wartości:

    - **Identyfikator szablonu sortowania towarów wychodzących:** *Sortowanie grupy czynności*
    - **Opis:** *Sortowanie grupy czynności*
    - **Typ szablonu sortowania:** *Popyt grupy czynności*

        To pole definiuje proces, dla którego jest używany szablon sortowania. Dostępne są następujące wartości:

        - **Popyt grupy czynności** — szablon sortowania jest używany w procesie *Odkładania do ściany*. Ten typ szablonu służy do ominięcia stacji pakowania i przetwarzania zapasów bezpośrednio poza falą. Można użyć tego typu, tylko jeśli metoda przetwarzania grupy czynności typu **sortowanie** jest uwzględniona w szablonie grupy czynności.
        - **Kontener** — szablon sortowania jest używany do procesu *kompilacji palet po pakowaniu*. Ten typ szablonu jest używany do przetwarzania kontenerów, które są zamknięte na stacji pakowania i muszą być sortowane na paletach.

    - **Magazyn:** *62*
    - **Lokalizacja:** *Sortowanie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Typ weryfikacji sortowania:** *Skan pozycji*

        To pole określa weryfikację wymaganą podczas sortowania. Dostępne są następujące wartości:

        - None
        - Skan numeru identyfikacyjnego
        - Skan stanowiska

    - **Utwórz pracę przy zamknięciu stanowiska:** *Tak*

        Jeśli opcja jest ustawiona na *Tak*, po zamknięciu stanowiska zostanie utworzona praca, aby przenieść zapasy do końcowej lokalizacji wysyłki. Jeśli opcja jest ustawiona na *Nie*, zapasy będą natychmiast pobierane dla zamówienia w momencie zamknięcia stanowiska.

    - **Przypisanie stanowiska:** *Manual*

        To pole określa typ przypisania stanowiska. Dostępne są następujące wartości:

        - **Ręczne** – Użytkownik musi zawsze wskazać, do którego stanowiska należy sortować zapasy.
        - **Automatycznie** – System w miarę możliwości automatycznie poprowadzi zapasy do stanowiska na podstawie podziałów w szablonie sortowania.

    - **Przypisz kryteria stanowiska sortowania:** *Używaj tylko pustego stanowiska*

        To pole kontroluje, czy zapasy, które są już obecne na stanowiskach sortowania, są brane pod uwagę podczas przypisywania stanowiska do zapotrzebowania. Dostępne są następujące wartości:

        - **Używaj tylko pustego stanowiska** — Uwzględnione zostaną stanowiska, które mają już skojarzone z nimi zapasy
        - **Przyjmij puste stanowisko** — Wszystkie zapasy znajdujące się już w danym stanowisku zostaną zignorowane podczas przypisywania. Zostaną użyte wszystkie dostępne stanowiska.

    - **Kod kroku grupy czynności:** *Sortowanie*

        Jeśli jest włączona funkcja *Kod kroku grupy czynności dotyczący całej organizacji*, kod etapu grupy czynności do *Sortowania* musi być również ustawiony w kodach kroków grupy czynności.

    - **Automatycznie zamknij stanowisko sortowania:** *Tak*

        Jeśli ta opcja jest ustawiona na *Tak*, stanowisko sortowania zostanie automatycznie zamknięte po zakończeniu całej pracy wchodzącej do jej stanowiska.

    - **Liczba stanowisk sortowania:** *3*

        W tym polu jest określana maksymalna liczba stanowisk sortowania tworzonych przez system.

    - **Prefiks stanowiska sortowania:** *SP-*

        To pole definiuje prefiks, który system przypisuje przed numerem stanowiska.

    - **Automatycznie pakuj stanowisko sortowania:** *Tak*

        Jeśli ta opcja jest ustawiona na *Tak*, zapasy w pozycji sortowania będą pakowane do kontenera po zamknięciu stanowiska.

    - **Identyfikator profilu pakowania:** *Sortowanie*

        To pole definiuje profil pakowania, który będzie używany, gdy stanowisko sortowania jest pakowane do kontenera.

1. W okienku akcji wybierz opcję **Edytuj kwerendę**, aby określić kryteria używane dla tego szablonu sortowania.
1. W oknie dialogowym kwerenda, na karcie **Sortowanie** wybierz opcję **Nowy**, aby dodać wiersz, a następnie określ następujące wartości:

    - **Tabela:** *Szczegóły ładunku*
    - **Tabela pochodna:** *Szczegóły ładunku*
    - **Pole:** *Identyfikator wysyłki*
    - **Kierunek wyszukiwania:** *Rosnąco*

1. Kliknij przycisk **OK**.
1. Może zostać wyświetlony następujący komunikat: „Grupowanie zostanie zresetowane, czy chcesz kontynuować?” Wybierz opcję **Tak**.

    W okienku akcji zostanie udostępniony przycisk **Podziały szablonu sortowania towarów wychodzących**.

1. W okienku akcji wybierz pozycję **Podziały szablonu sortowania towarów wychodzących**.
1. Wybierz **Grupuj według pola**, aby pogrupować wysyłki według identyfikatora wysyłki.

    To ustawienie spowoduje utworzenie jednego stanowiska sortowania na przesyłkę będącą kontenerem w grupie.

1. Kliknij przycisk **OK**.

### <a name="wave-process-methods"></a>Metody przetwarzania grupy czynności

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.
1. W okienku akcji wybierz pozycję **Ponownie utwórz metody**.

    Metoda **sortowania** jest dodawana do listy dostępnych metod, a dla niego wybrano typ szablonu grupy czynności *Wysyłki*.

### <a name="wave-templates"></a>Szablony grupy czynności

Edytuj szablon grupy czynności używany do popytu sortowania na grupy czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. W **Typ szablonu grupy czynności** wybierz *Wysyłka*.
1. Umożliwia wybór istniejącego szablonu **Domyślna wysyłka 62**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Ogólne** wprowadź następujące zmiany:

    - Ustaw opcję **Przetwarza grupę czynności w czasie uwalniania jej do magazynu** na wartość *Nie*.
    - Ustaw opcję **Przypisz do otwartych grup czynności** na *Tak*.

1. Na skróconej karcie **Metody** należy ustawić metodę **sortowania**:

    1. W siatce **Pozostałe metody** wybierz opcję **Sortowanie**.
    2. Korzystaj z przycisku Strzałka w prawo, aby przesunąć **sortowanie** na siatkę **Wybrane metody**.
    3. W siatce **Wybrane metody** wybierz opcję **Sortowanie**.
    4. W polu **Kod kroku grupy czynności** należy ustawić *Sortowanie*.

1. Wybierz opcję **Zapisz**.

### <a name="mobile-device-menu-items"></a>Elementy menu urządzenia przenośnego

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Nazwa elementu menu:** *Sortowanie*
    - **Tytuł:** *Sortowanie*
    - **Tryb:** *Pośrednie*
    - **Używanie istniejącej pracy:** *Nie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Kod działania:** *Sortowanie towarów wychodzących*
    - **Skorzystaj z przewodnika procesu:** *Tak* (wartość domyślna)
    - **Identyfikator szablonu sortowania towarów wychodzących:** *Sortowanie grupy czynności*

1. Wybierz opcję **Zapisz**.

### <a name="mobile-device-menu"></a>Menu urządzeń przenośnych

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. Z listy menu wybierz opcję **Wychodzące**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. W siatce **Dostępne menu i elementy menu** znajdź i wybierz element menu **Sortowanie**, który został właśnie utworzony.
1. Wybierz strzałkę w prawo, aby przenieść **Sortowanie** do siatki **Struktura menu**. W ten sposób dodasz nowy element menu do menu **Wychodzące**.
1. Wybierz opcję **Zapisz**.

### <a name="location-directives"></a>Dyrektywy lokalizacji

Należy utworzyć dyrektywy lokalizacji, które będą kierować pracą utworzoną po zakończeniu sortowania.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W polu **Typ zlecenia pracy** zaznacz opcję *Pobranie z posortowanych zapasów*.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Sekwencja:** *1*
    - **Nazwa:** *Odłóż do bramy dokowej*

1. Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości:

    - **Typ pracy:** *Odłożenie*
    - **Oddział:** *6*
    - **Magazyn:** *62*
    - Pole **Kod dyrektywy:** należy pozostawić puste.
    - **Wiele jednostek SKU:** *Nie*

1. Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.
1. Na skróconej karcie **Wiersze** wybierz opcję **Nowy**, a następnie określ następujące wartości. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Numer sekwencyjny:** *1*
    - **Od ilości:** *0*
    - **Do ilości:** *1000000*

1. Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.
1. Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz opcję **Nowy**, a następnie określ następujące wartości. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Numer sekwencyjny:** *1*
    - **Nazwa:** *Baydoor*

1. Wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę** na skróconej karcie **Dyrektywy akcji lokalizacji**.
1. Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.
1. W oknie dialogowym zapytań na karcie **Zakres** znajdź wiersz, w którym pole **Pole** ma wartość *Lokalizacja*. Umożliwia ustawienie pola **Kryterium** dla tego wiersza na *Baydoor*.
1. Wybierz przycisk **OK**, aby zatwierdzić zmiany.

### <a name="work-classes"></a>Klasy robocze

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Identyfikator klasy roboczej:** *Sortowane*
    - **Opis:** *Sortowane*
    - **Typ zlecenia pracy:** *Szablon pracy pobrania z posortowanych zapasów*

1. Wybierz opcję **Zapisz**.

### <a name="work-templates"></a>Szablony pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szablony pracy**.
1. W polu **Typ zlecenia pracy** wybierz opcję *Zamówienia sprzedaży*.
1. W siatce wybierz szablon pracy **62 Pobranie do pakowania**.
1. W okienku akcji wybierz **Podziały nagłówka pracy**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. W wierszu, w którym pole **Nazwa pola** ma wartość *Identyfikator wysyłki*, wyczyść pole wyboru **Grupuj według tego pola**.
1. Wybierz opcję **Zapisz**, a następnie zamknij okno dialogowe **Podziały nagłówka pracy**.
1. W polu **Typ zlecenia pracy** zaznacz opcję *Pobranie z posortowanych zapasów*.
1. Wybierz pozycję **Nowy**, aby utworzyć nowy pracy.
1. W sekcji **Omówienie** ustaw następujące wartości. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Szablon pracy:** *Pobranie z posortowanych*
    - **Opis szablonu pracy:** *Pobranie z posortowanych*

1. Wybierz opcję **Zapisz**, aby sekcja **Szczegóły szablonu pracy** stała się dostępna.
1. W sekcji **Szczegóły szablonu pracy** zostaną utworzone dwa wiersze. Wybierz opcję **Nowe**, a następnie określ następujące wartości dla wiersza 1:

    - **Typ pracy:** *Pobranie*
    - **Wymagane:** Wybrane (= *Tak*)
    - **Identyfikator klasy roboczej:** *Sortowane*

1. Wybierz znowu opcję **Nowe**, a następnie określ następujące wartości dla wiersza 2:

    - **Typ pracy:** *Odłożenie*
    - **Wymagane:** Wybrane (= *Tak*)
    - **Identyfikator klasy roboczej:** *Sortowane*

1. Wybierz opcję **Zapisz**.

## <a name="example-scenario"></a>Przykładowy scenariusz

W tym scenariuszu symulowane są sytuacje, w których magazyn przechowuje małe towary w lokalizacjach i pakuje je do pól przed ich wysłaniem, a funkcjonalność stacji pakowania jest w rzeczywistości odpowiednia. Pracownicy kompletują zamówienia dla wielu klientów i jednocześnie pod różnymi adresami, aby zwiększyć szybkość kompletacji. Po zakończeniu pobierania pracownicy docierają do lokalizacji sortowania, gdzie pobrane towary mogą być posortowane w odpowiednim polu na podstawie wymaganych kryteriów. W tym przykładzie identyfikator wysyłki zostanie użyty do ustalenia prawidłowego pola, ponieważ każda wysyłka ma inny adres. Po zapełnieniu wszystkich towarów z ładunku i posortowaniu ich według wysyłki pola zostaną przeniesione do obszaru tymczasowego, a ostatecznie załadowane na ciężarówkę.

Przed rozpoczęciem scenariusza należy upewnić się, że wszystkie funkcje magazynu standardowego są poprawnie skonfigurowane dla danego magazynu. W tym celu jest używany standardowy magazyn *62* firmy Contoso. Standardowe konfiguracje nie zostały zmienione, a nie zostały opisane w konfiguracji.

### <a name="create-demand"></a>Utwórz popyt

Aby można było wykazać tę funkcję, trzeba utworzyć pewne zapotrzebowanie. W tym scenariuszu zostaną utworzone trzy zamówienia sprzedaży dla trzech różnych odbiorców w celu symulacji różnych adresów dostawy. W ten sposób utworzysz trzy osobne wysyłki.

Przed utworzeniem zamówień sprzedaży i wysyłek upewnij się, że w lokalizacjach pobrania jest wystarczająca ilość zapasów dla wszystkich towarów w zamówieniach. Przejrzyj ustawienia dyrektywy lokalizacji, aby potwierdzić lokalizacje pobrania używane do pobierania zamówień sprzedaży. Jeśli konieczne jest skorygowanie zapasów, można ręcznie tworzyć zmiany, skorzystać z uzupełnienia lub skorzystać z dowolnego innego przepływu. Następnie zarezerwuj ekwipunek.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć zamówienie sprzedaży dla zamówienia 1.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Odbiorca:** *US-001*
    - **Magazyn:** *62*

1. Kliknij przycisk **OK**.
1. Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**. Ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *5*

1. Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:

    - **Numer pozycji:** *A0002*
    - **Ilość:** *10*

1. Poniższe kroki należy powtórzyć dla każdego wiersza sprzedaży w zamówieniu, aby zarezerwować dla niego zapasy:

    1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacja**.
    1. Na stronie **Rezerwacje** wybierz **Rezerwacja partii** i zamknij stronę.
    1. Wybierz opcję **Zapisz**.

1. Wybierz pozycję **Nowe**, aby utworzyć zamówienie sprzedaży dla zamówienia 2.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Odbiorca:** *US-004*
    - **Magazyn:** *62*

1. Kliknij przycisk **OK**.
1. Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**. Ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *7*

1. Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:

    - **Numer pozycji:** *A0002*
    - **Ilość:** *3*

1. Poniższe kroki należy powtórzyć dla każdego wiersza sprzedaży w zamówieniu, aby zarezerwować dla niego zapasy:

    1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacja**.
    1. Na stronie **Rezerwacje** wybierz **Rezerwacja partii** i zamknij stronę.
    1. Wybierz opcję **Zapisz**.

1. Wybierz pozycję **Nowe**, aby utworzyć zamówienie sprzedaży dla zamówienia 3.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Odbiorca:** *US-007*
    - **Magazyn:** *62*

1. Kliknij przycisk **OK**.
1. Nowy wiersz zostanie dodany skróconej karty **Wiersze zamówienia sprzedaży**. Ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *8*

1. Wykonaj następujące kroki, aby zarezerwować zapasy dla linii sprzedaży:

    1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacja**.
    1. Na stronie **Rezerwacje** wybierz **Rezerwacja partii** i zamknij stronę.
    1. Wybierz opcję **Zapisz**.

Aby zwolnić poszczególne zamówienia sprzedaży do magazynu, należy wykonać poniższą procedurę. Zostaną utworzone trzy różne wysyłki. Następnie należy dodać wszystkie trzy wysyłki do jednej nowej grupy czynności.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W siatce wybierz pierwsze utworzone zamówienie sprzedaży.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Użytkownik otrzymuje komunikat informacyjny, który zawiera utworzony identyfikator grupy czynności oraz identyfikator wysyłki.

1. Powtórz powyższe kroki, aby zwolnić zamówienia sprzedaży 2 i 3 do magazynu. Należy zauważyć, że otrzymany komunikat informacyjny wskazuje, że wysyłka została dodana do grupy czynności, która została utworzona podczas zwalniania zamówienia sprzedaży 1.
1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz grupę czynności, która została utworzona na podstawie zwolnienia zamówień sprzedaży, aby otworzyć stronę **Grupy czynności**. Na tej stronie są wyświetlane szczegóły dotyczące grupy czynności. Na skróconej karcie **Wiersze grupy czynności** są wyświetlane wywysyłki, które zostały utworzone.

    Teraz należy utworzyć pracę, aby przenieść pozycje z lokalizacji pobrania do lokalizacji sortowania.

1. W okienku akcji wybierz pozycję **Przetwarzanie**.

    Podczas przetwarzania grupy czynności metoda sortowania używa szablonu sortowania w celu przypisania zapasów do pozycji do sortowania. Po zakończeniu przetwarzania grupy czynności zostanie wyświetlony komunikat informacyjny z informacją, że grupa czynności została opublikowana i została utworzona praca.

1. W okienku akcji na karcie **Grupa czynności**, w grupie **Informacje pokrewne** wybierz opcję **Praca**, aby wyświetlić utworzoną pracę. Zanotuj identyfikator pracy.
1. Należy przejść do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Przypisania stanowisk sortowania towarów wychodzących**.
1. W lewej kolumnie można wyświetlić wychodzącą pozycję sortowania utworzoną dla każdej wysyłki.
1. Na skróconej karcie **Kryteria stanowiska sortowania** można wyświetlić identyfikator wysyłki dla danego stanowiska.

Utworzono jeden identyfikator pracy w celu przeniesienia zapasów z lokalizacji pobrania do lokalizacji sortowania. Do zakończenia pracy potrzebny jest identyfikator pracy utworzony podczas przetwarzania grupy czynności.

### <a name="sales-order-picking-to-the-sorting-location"></a>Pobieranie zamówienia sprzedaży do lokalizacji sortowania

1. Zaloguj się do aplikacji mobilnej jako pracownik w magazynie *62*.
1. W menu głównym wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz opcję **Pobranie sprzedaży**.
1. Zaznacz pole **Identyfikator**, a następnie wprowadź identyfikator pracy z przetwarzania grupy czynności.
1. Potwierdź wpis.

    Następnie wyświetlany jest monit o wprowadzenie docelowego numeru identyfikacyjnego. Zwróć uwagę, że wiersz 1 z zamówienia sprzedaży 1 musi zostać pobrany i dodany do docelowego numeru identyfikacyjnego. Wyświetlany jest kod towaru, ilość, opis towaru i lokalizacja pobrania.

1. W polu **Docelowy num. id.** wprowadź numer identyfikacyjny.

    Wszystkie wiersze utworzone z przetworzonej grupy czynności zostaną pobrane na ten sam docelowy numer identyfikacyjny.

1. Potwierdź wpis.

    Aplikacja mobilna przedstawia w serii stron **Pobrania**, które wskazują na lokalizację pobrania, oraz na towar i ilość, która musi zostać pobrana. Po dodaniu pobranego towaru do numeru identyfikacyjnego należy potwierdzić poprawność pobrania. Ostatnia strona to praca, która powoduje umieszczenie pobranych towarów w lokalizacji sortowania.

1. Potwierdź pierwszą pracę pobrania.
1. Zostanie wyświetlona Następna praca pobrania. Potwierdź pobranie.
1. Kontynuuj, aby potwierdzić pozostałą pracę pobrania.
1. Ostatnim krokiem jest zakończenie pracy odłożenia. Potwierdź odłożenie w lokalizacji sortowania.

    Zostanie wyświetlony komunikat „Praca zakończona”.

1. Zakończ **Pobranie sprzedaży** w aplikacji mobilnej.

### <a name="sortingput-to-wall"></a>Sortowanie/odłożenie na ścianę

Teraz, gdy wszystkie zapasy zostały wprowadzone do lokalizacji sortowania, należy je posortować na prawidłowej pozycji sortowania.

1. Logowanie do aplikacji mobilnej.
1. W menu głównym wybierz opcję **Wychodzące**.
1. W menu **Wychodzące** wybierz opcję **Sortowanie**, aby rozpocząć sortowanie towarów.
1. W polu **Numer identyfikacyjny/Con** wprowadź docelowy numer identyfikacyjny dla pobranej pracy zamówienia sprzedaży.
1. Potwierdź wpis.
1. Umożliwia wprowadzenie kodu towaru, który ma być posortowany jako pierwszy.
1. System określa pierwsze stanowisko sortowania, które powinno zostać pokazane. Potwierdź stanowisko sortowania.
1. Zostanie wyświetlony monit o przypisanie numeru identyfikacyjnego do stanowiska sortowania. Zaznacz pole **Numer identyfikacyjny**, wprowadź numer identyfikacyjny, a następnie potwierdź wpis.

    Ponieważ stanowisko sortowania jest powiązane z identyfikatorem wysyłki, towary te zostaną posortowane w numer identyfikacyjny, który jest właściwy dla wysyłki wychodzącej i zamówienia sprzedaży.

    Na następnej stronie jest wyświetlany identyfikator towaru, ilość, identyfikator stanowiska sortowania oraz numer identyfikacyjny „od” (pobranie) oraz „do” (sortowanie) identyfikatorów numerów identyfikacyjnych. Informacje na tej stronie instruują, aby posortować określoną pozycję i ilości z numeru rejestracyjnego pobrania do numeru identyfikacyjnego sortowania.

1. Potwierdź stanowisko sortowania.
1. Umożliwia posortowanie elementów na pierwszym stanowisku sortowania. Po zakończeniu system kieruje do następnego stanowiska sortowania.
1. Powtórz ten proces dla wszystkich pobranych wierszy w zleceniu pracy. Tego procesu należy również używać w przypadku wielu wierszy pobrania o tym samym numerze towaru.

    W przypadku powtórzenia tego procesu dla wszystkich towarów system ocenia kryteria z następnego zeskanowanego elementu (wiersz pracy) i określa stanowisko sortowania, do którego ma być wykonane przesunięcie. Automatycznie nastąpi przekierowanie w celu odłożenia towaru do właściwego stanowiska sortowania. W zależności od konfiguracji potwierdzeń użytkownik jest również kierowany do potwierdzenia tej akcji przez wprowadzenie numeru stanowiska lub numeru identyfikacyjnego.

    > [!NOTE]
    > Jeśli jest włączone sortowanie automatyczne, ręczna zmiana nie jest dostępna.

1. Po zakończeniu w Microsoft Dynamics 365 Supply Chain Management otwórz stronę **Przypisania stanowisk sortowania towarów wychodzących**, aby przejrzeć stan stanowisk.

    - Jeśli pozycje są zamykane automatycznie, wybierz opcję **Pokaż zamknięte**, aby wyświetlić zamknięte stanowiska.
    - Zauważ, że są wyświetlane transakcje dotyczące stanowisk sortowania. Wyświetlany jest towar i ilość przetworzona przez stanowisko.

    Podczas konfigurowania szablonu wychodzącego sortowania została ustawiona opcja **Automatycznie zamknij stanowisko sortowania** na wartość *Tak*. Z tego względu stanowisko jest automatycznie zamykane po umieszczeniu ostatniego oczekiwanego zapasu. Pozycje sortowania są w stanie **Zamkniętym** i utworzono pracę w celu przeniesienia posortowanych zapasów do lokalizacji *Bramy dokującej*.

1. Zakończ posortowaną pracę pobrania dla magazynu, aby przenieść zapasy do lokalizacji wysyłki. Gdy magazyn jest gotowy, należy go potwierdzić wysyłkę.

> [!NOTE]
> W przypadku posortowanej pracy pobierania zapasów, która ma zostać prawidłowo przetworzona, element menu urządzenia przenośnego z identyfikatorem klasy pracy, w którym pole **Typ zlecenia pracy** jest ustawione na *Pobranie z posortowanych zapasów* powinno być używane w procesie przesunięcia i załadunku.

### <a name="manually-close-a-position-optional"></a>Ręcznie zamknij stanowisko (opcjonalnie)

Jeśli stanowiska sortowania powinny być zamykane ręcznie, opcja **Automatycznie zamknij stanowisko sortowania** dla szablonu wychodzącego sortowania musi mieć wartość *Nie*, a zamknięcie musi być wykonane przed przeniesieniem zapasów do obszaru bramy dokującej. Stanowiska mogą być zamknięte na różne sposoby:

- Poprzez aplikację mobilną Warehouse Management:

    - Użytkownik może skanować jeden z towarów znajdujących się już na stanowisku, a następnie wybrać opcję **Zamknij**, aby zamknąć stanowisko.
    - Jeśli użytkownik zeskanuje kontener, który został już posortowany, wyświetlany jest komunikat o błędzie. Użytkownik może jednak nadal zamknąć stanowisko.

- Z Microsoft Dynamics 365 Supply Chain Management ze strony **Przypisania stanowisk sortowania towarów wychodzących**:

    - Użytkownik może wybrać rekord ze stanowiskiem wychodzącego sortowania, a następnie w okienku akcji wybrać **Zamknij stanowisko**.

## <a name="tips"></a>Porady

- Nie można przenosić towarów między pozycjami po ich przypisaniu do jednego. System ocenia, ile elementów powinno zostać przestawionych na określone stanowisko.
- Szablon sortowania można skonfigurować do automatycznego tworzenia kontenerów po zamknięciu stanowisk. Ta metoda spowoduje utworzenie standardowej struktury identyfikatorów kontenerów opartej na określonym profilu pakowania.

> [!IMPORTANT]
> Po utworzeniu pracy przesunięcia z lokalizacji sortowania nie można anulować pracy. W przeciwnym razie pozycja i kontenery w niej zostaną usunięte z systemu i nie będą dostępne do dalszego przetwarzania. Zapasy zostaną również usunięte.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]