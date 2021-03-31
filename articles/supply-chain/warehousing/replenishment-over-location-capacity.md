---
title: Uzupełnianie zapasów ponad pojemność lokalizacji
description: Ten temat zawiera informacje dotyczące funkcji uzupełniania zapasów pojemności lokalizacji. Ta funkcja umożliwia utworzenie wszystkich prac związanych z uzupełnianiem zapasów, które będą wymagane w danym dniu, i zarządza dostępnością tych prac, aby zapewnić, że w lokalizacji pobrania nie zabraknie zapasów ani nie przekroczą pojemności.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 1e4acfea3484acaafd982d0f22c2303f921f909f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228400"
---
# <a name="replenishment-over-location-capacity"></a>Uzupełnianie zapasów ponad pojemność lokalizacji

[!include [banner](../includes/banner.md)]

Niektóre magazyny o dużym poziomie wolumenu lub przestrzeni muszą wysyłać większą ilość towaru w ciągu dnia, który nie mieści się w lokalizacji pobrania. Funkcja *Uzupełnianie zapasów ponad pojemność lokalizacji* umożliwia utworzenie wszystkich prac związanych z uzupełnianiem zapasów, które będą wymagane w danym dniu, i zarządza dostępnością tych prac, aby zapewnić, że w lokalizacji pobrania nie zabraknie zapasów ani nie przekroczą pojemności.

Funkcja umożliwia tworzenie większej ilości pracy uzupełniania, która nie mieści się w lokalizacji i blokuje pracę uzupełniania zapasów w przypadku zapełnienia lokalizacji. Jeśli zapasy w lokalizacji pobrania są porzucane poniżej progu konfigurowalnego, dostępna jest większa ilość pracy uzupełniania zapasów.

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a>Włączanie funkcji Uzupełnianie zapasów ponad pojemność lokalizacji

Aby ta funkcja była dostępna, włącz następujące funkcje w module [zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (w tej kolejności):

1. Blokowanie pracy na poziomie organizacji
1. Uzupełnianie zapasów ponad pojemność lokalizacji

## <a name="set-up-the-feature-for-the-example-scenario"></a>Skonfiguruj funkcję dla tego scenariusza przykładowego

Ta sekcja zawiera wskazówki oraz przykład, w jaki sposób należy skonfigurować funkcję i przygotować przykładowe dane do scenariusza przykładowego, który opisano w dalszej części tego tematu.

### <a name="enable-sample-data"></a>Włącz dane przykładowe

Aby pracować z tymi [przykładowymi scenariuszami](#example-scenario) przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

### <a name="location-profile"></a>Profil lokalizacji

Włącz funkcję uzupełniania nadmiaru pojemności w profilu lokalizacji.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
1. W lewym okienku wybierz **PICK-06**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Uzupełnianie zapasów** ustaw następujące wartości:

    - **Przekraczanie pojemności lokalizacji:** *Tak*

        Po włączeniu tej opcji maksymalna pojemność lokalizacji będzie mogła być przekraczana przez pracę uzupełniania zapasów. Umożliwia także korzystanie z innych pól na skróconej karcie **Uzupełnienie zapasów**.

    - **Typ progu dostępności pracy:** *Ilość*

        To pole określa metodę używaną do określenia, kiedy ma być zwalniana większa praca. Możesz zwolnić według ilości lub procentu:

        - *Procent* — tę opcję należy wybrać, aby zastosować procentową zdolność produkcyjną opartą na limitach składowania lub miarach. Zaznaczenie tej opcji włącza pole **Procent przepełnienia** i wyłącza dwie powiązane pola ilości, **Ilość przepełnienia** i **Jednostkę przepełnienia**.

            Opcji tej można skorzystać, jeśli lokalizacje pobrania używają miar.

            Jeśli ta opcja jest zaznaczona, pole **Procent przepełnienia** jest ustawiane na wartość procentową, przy której będzie udostępniana większa ilość pracy uzupełniania zapasów.

        - *Ilość* — tę opcję należy wybrać, aby zastosować określoną wartość ilości. Zaznaczenie tej opcji wyłącza pole **Procent przepełnienia** i włącza dwie powiązane pola **Ilość przepełnienia** i **Jednostkę przepełnienia**.

            Tej opcji należy użyć w przypadku, gdy nie są używane objętości w odniesieniu do lokalizacji, które są uzupełniane, lub gdy istnieją spójne ilości, na których ma zostać przeprowadzona większa ilość zapasów w lokalizacji.

           Jeśli ta opcja jest zaznaczona, wartości pól **Ilość przepełnienia** i **Jednostka przepełnienia** należy określić w odniesieniu do ilości i jednostki, w których będzie dostępna większa ilość pracy uzupełniania zapasów.

    - **Ilość przepełnienia:** *0,65*

        To pole służy do definiowania ilości przepełnienia lokalizacji.

        Praca będzie dostępna zawsze, gdy suma ilości dostępnej w lokalizacji i ilości pracy spadnie poniżej tej wartości. Dowolna ilość pracy uzupełniania zapasów powyżej tej wartości zostanie zablokowana i musi być odblokowana ręcznie.

        Limity składowania są brane pod uwagę podczas obliczania ilości pracy.

    - **Jednostka przepełnienia:** *PL*

        To pole określa jednostkę, która jest skojarzona z ilością przepełnienia.

        W takim przypadku więcej pracy uzupełniania zapasów zostanie udostępniona, gdy lokalizacja odniesie się do 0,65 palety (PL).

    - **Procent przepełnienia**

        To pole służy do definiowania procentu przepełnienia lokalizacji.

        Praca będzie dostępna zawsze, gdy suma ilości dostępnej w lokalizacji i ilości pracy spadnie poniżej tego procentu. Dowolna wartość procentowa ilości pracy uzupełniania zapasów powyżej tej wartości zostanie zablokowana i musi być odblokowana ręcznie.

        Limity składowania są brane pod uwagę podczas obliczania procentu ilości pracy. Jeśli nie zdefiniowano żadnych limitów magazynowych, procent ilości pracy jest obliczany na podstawie objętości, jeśli w profilu lokalizacji są zdefiniowane ograniczenia dotyczące wolumenu.

> [!IMPORTANT]
> Jeśli użytkownik korzysta z danych demonstracyjnych dla firmy **USMF** i uprzednio włączył funkcję *Pozycjonowania numeru identyfikacyjnego danej lokalizacji*, musi wyłączyć ustawienie **Włącz pozycjonowanie numeru identyfikacyjnego** dla profilu lokalizacji **BULK-06**, aby zakończyć etapy mobilne w scenariuszu przykładowym.

### <a name="wave-step-code"></a>Kod kroku grupy czynności

> [!NOTE]
> Aby można było skonfigurować kod kroku grupy czynności w sposób opisany w tym miejscu, należy najpierw skorzystać z [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby włączyć funkcję o nazwie *Kod kroku grupy czynności dotyczący całej organizacji:*.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Kody kroku grupy czynności**.
1. Wybierz opcję **Nowe** i określ następujące wartości:

    - **Kod kroku grupy czynności:** *Uzupełnienie*
    - **Opis kroku grupy czynności:** *Uzupełnienie*
    - **Typ kroku grupy czynności:** *Uzupełnienie*

1. Wybierz opcję **Zapisz**.

### <a name="replenishment-template"></a>Szablon uzupełniania zapasów

Szablony uzupełniania zapasów są zestawem reguł, które sterują tym, kiedy i jak zapasy są uzupełniane w lokalizacji.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. W sekcji **Przegląd** wybierz wiersz, w którym w polu **Szablon uzupełnienia** zaznaczono wartość *Uzupełnienie zapotrzebowania*.
1. Ustaw następujące wartości:

    - **Kod kroku grupy czynności:** *Uzupełnienie*
    - **Zezwalaj, aby żądania w ramach grupy czynności korzystały z niezarezerwowanych ilości:** *Tak*

1. Wybierz opcję **Zapisz**.

### <a name="wave-template"></a>Szablon grupy czynności

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. W lewym okienku w polu **Typ szablonu grupy czynności** ustaw wartość na *Wysyłka*.
1. Wybierz szablon **61 Wysyłka** na liście.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. W karcie **Ogólne** ustaw **Automatyczne zwalnianie pracy uzupełniania zapasów** jako *Tak*.

    Ustaw opcję na *Tak*, aby tworzyć pracę uzupełnienia opartą na żądaniu, i zwalniać ją automatycznie. Należy dodać do szablonu grupy czynności metodę grupy czynności uzupełnienia i utworzyć szablon uzupełnienia typu **Popyt grupy czynności**. Konfigurowanie szablonu uzupełniania zapasów znajdujących się na stronie **Szablony uzupełniania zapasów**. Aby skonfigurować szablon uzupełniania zapasów, należy dodać metodę uzupełnienia do szablonu grupy czynności.

1. Na skróconej karcie **Metody** w kolumnie **Wybrane metody** znajdź następujący wiersz:

    - **Nazwa metody:** *replenish*
    - **Nazwa:** *Uzupełnienie*

1. Umożliwia ustawienie pola **Koda kroku grupy czynności** dla tego wiersza na *Replen*.
1. Wybierz opcję **Zapisz**.

## <a name="example-scenario"></a>Przykładowy scenariusz

Po wykonaniu wszystkich poprzednio opisanych przykładowych danych i ich skonfigurowania można korzystać z tego scenariusza, aby wypróbować funkcję *Uzupełnianie zapasów ponad pojemność lokalizacji*. Wartości przedstawione w tym scenariuszu zakładają, że pracujesz ze standardowymi danymi demonstracyjnymi, które zostały wybrane firmę **USMF**, oraz że zostały przygotowane przykładowe rekordy opisane wcześniej w tym temacie. Ten scenariusz służy także jako przykład, który pokazuje, w jaki sposób funkcja może być używana w ustawieniu produkcji.

### <a name="create-replenishment-work"></a>Utwórz pracę uzupełniania zapasów

#### <a name="create-sales-order-1"></a>Utwórz zamówienie sprzedaży 1

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz opcję **Nowe** w okienku akcji, aby otworzyć okno dialogowe do tworzenia nowego zamówienia sprzedaży.
1. W oknie dialogowym ustaw następujące wartości:

    - **Konto odbiorcy:** *US-007*
    - **Magazyn:** *61*

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera nowy, pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *T0100*
    - **Ilość:** *40*

1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.
1. Na stronie **Rezerwacje** wybierz **Rezerwacja partii**.
1. Zamknij stronę.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Otrzymujesz komunikaty informacyjne, które zawierają utworzone identyfikatory grupy czynności i przesyłki. Tworzona jest również grupa czynności uzupełnień.

    Otrzymujesz również komunikat ostrzegawczy z informacją, że „Identyfikator pracy XXXX nie może zostać odblokowany, ponieważ zawiera niedokończone prace uzupełniające”.

#### <a name="create-sales-order-2"></a>Utwórz zamówienie sprzedaży 2

1. Na stronie **Wszystkie zamówienia sprzedaży** wybierz opcję **Nowe** w okienku akcji, aby otworzyć okno dialogowe do tworzenia nowego zamówienia sprzedaży.
1. W oknie dialogowym ustaw następującą wartość:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *61*

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera nowy, pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *T0100*
    - **Ilość:** *60*

1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.
1. Na stronie **Rezerwacje** wybierz **Rezerwacja partii**.
1. Zamknij stronę.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Otrzymujesz komunikaty informacyjne, które zawierają utworzone identyfikatory grupy czynności i przesyłki. Tworzona jest również grupa czynności uzupełnień.

    Otrzymujesz również komunikat ostrzegawczy z informacją, że „Identyfikator pracy XXXX nie może zostać odblokowany, ponieważ zawiera niedokończone prace uzupełniające”.

#### <a name="create-sales-order-3"></a>Utwórz zamówienie sprzedaży 3

1. Na stronie **Wszystkie zamówienia sprzedaży** wybierz opcję **Nowe** w okienku akcji, aby otworzyć okno dialogowe do tworzenia nowego zamówienia sprzedaży.
1. W oknie dialogowym ustaw następujące wartości:

    - **Konto odbiorcy:** *US-004*
    - **Magazyn:** *61*

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera nowy, pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *T0100*
    - **Ilość:** *30*

1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.
1. Na stronie **Rezerwacje** wybierz **Rezerwacja partii**.
1. Zamknij stronę.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Otrzymujesz komunikaty informacyjne, które zawierają utworzone identyfikatory grupy czynności i przesyłki. Tworzona jest również grupa czynności uzupełnień.

    Otrzymujesz również komunikat ostrzegawczy z informacją, że „Identyfikator pracy XXXX nie może zostać odblokowany, ponieważ zawiera niedokończone prace uzupełniające”.

#### <a name="view-work-details"></a>Wyświetlanie szczegółów pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. W sekcji **Przegląd** odfiltruj kolumnę **Magazyn** dla magazynu *61*.
1. Należy sprawdzić, czy dla trzech zamówień sprzedaży na żądanie zostały utworzone siedem identyfikatorów pracy.

    - Trzy z siedmiu identyfikatorów pracy mają w **Typu zlecenia pracy** wartość *Uzupełnienie*, a cztery mają w **Typ zlecenia pracy** wartość *Zamówienie sprzedaży*.
    - Wszystkie trzy identyfikatory pracy, dla których wartość **Typu zlecenia pracy** to *Uzupełnienie*, mają te same lokalizacje *Pobrania* i *Odłożenia* w sekcji **Wiersze**:

        - **Odbierz:** *02A01R5S1B*
        - **Odłóz:** *06A01R2S1B*

    - Utworzono dwa identyfikatory pracy dla zamówienia sprzedaży 1.

1. Zapisz identyfikatory pracy dla zamówienń sprzedaży.

W zależności od ilości dostępnych ilości pracy mogą być nieco niezmienne. Jednak ogólnie utworzone nagłówki pracy powinny pasować do tego przykładu scenariusza.

#### <a name="on-hand-inventory-license-plate-id"></a>Identyfikator numeru identyfikacyjnego dostępnych zapasów

W dalszej części tego scenariusza będzie używana aplikacja magazynu (lub emulator), gdzie należy zidentyfikować numer identyfikacyjny w celu ukończenia scenariuszy pobierania i uzupełniania zapasów.

Aby znaleźć identyfikatory numerów identyfikacyjnych, które będą potrzebne później, należy wykonać poniższe kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zapytania i raporty \> Dostępne zapasy**.
1. Wybierz przycisk **Pokaż filtry**, aby otworzyć okienko filtru.
1. Wprowadź poniższe kryteria filtrowania, aby uzyskać tablice rejestracyjne dla scenariusza. Należy skorzystać z filtru *zaczyna się od*.

    - **Numer pozycji:** *T0100*
    - **Magazyn:** *61*

1. Wybierz opcję **Zastosuj**.
1. W Okienku akcji kliknij pozycję **Wymiary**.
1. W oknie dialogowym **Wyświetlanie wymiarów** w sekcji **Wymiary magazynowe** wybierz wszystkie wartości.
1. W sekcji **Transakcje** wybierz **Numer pozycji** i **Ilość \<\> 0**.
1. Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. Na siatce **Dostępne** są wyświetlane numery numerów identyfikacyjnych dla pozycji *T0100* w każdej lokalizacji. Zanotuj numer identyfikacyjny znajdujący się w każdej lokalizacji, ponieważ informacje te będą potrzebne później.
1. Zamknij stronę.

### <a name="process-steps"></a>Kroki procesu

Uzupełnianie lokalizacji w magazynie jest wykonywane dla pierwszych dwóch identyfikatorów pracy. Praca nad trzecią pracą uzupełniania zapasów zostanie zablokowana do momentu, gdy poziom zapasów w lokalizacji pobrania spadnie poniżej progu.

#### <a name="replenishment"></a>Uzupełnianie zapasów

1. Zaloguj się do aplikacji magazynowania jako użytkownik w magazynie *61*. (Wprowadź *61* jako identyfikator użytkownika i *1* jako hasło.)
1. Przejdź do **Zapasy \> Uzupełnienie**.

    Zostanie wyświetlony monit o wykonanie pierwszej pracy uzupełniania zapasów. Wyświetlany jest numer pozycji, ilość i lokalizacja do pobrania.

1. W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.
1. Wybierz przycisk **OK** (symbol znacznika wyboru).

    System generuje numer identyfikacyjny docelowy dla nowego numeru identyfikacyjnego pobranego towaru.

1. Wybierz przycisk **OK**, aby zatwierdzić wartość.

    Wyświetlana jest pokazana praca, która nakazuje użytkownikowi umieszczenie docelowego numeru identyfikacyjnego w lokalizacji uzupełnienia zapasów. Lokalizacja *Odłożenia* powinna być **06A01R2S1B**.

1. Potwierdź szczegóły umieszczania i kliknij przycisk **OK**.

    Otrzymasz komunikat „Praca zakończona” i zostaną wyświetlone szczegóły następnego zadania pobrania uzupełnienia: numer pozycji, ilość i lokalizacja do pobrania. Lokalizacja pobrania będzie taka sama jak pierwsza lokalizacja uzupełnienia zapasów. W związku z tym numer identyfikacyjny ma ten sam identyfikator, który był używany dla pierwszego zadania pracy uzupełniania zapasów.

1. Powtórz powyższe kroki, aby ukończyć pracę uzupełniania zapasów dla drugiego zadania pracy. Ilość i docelowy numer identyfikacyjny różnią się od ilości i docelowego numeru identyfikacyjnego dla pierwszego zadania pracy.

Po zakończeniu drugiej pracy uzupełniania zapasów wyświetlany jest komunikat „praca wykonana”. Urządzenie przenośne informuje również o tym, że nie ma dostępnej pracy, nawet jeśli pozostała część pracy uzupełniającej. Takie zachowanie występuje, ponieważ praca uzupełniania zapasów ma stan dostępności *Wstrzymany* i dlatego oznaczono jako **Zablokowana**.

Stan *Wstrzymany* został wyzwolony, ponieważ profil lokalizacji dla lokalizacji pobrania, do której jest przypisana praca, ma wartość **Ilości przepełnienia** równą *0,65 PL*. Dwa poprzednie zadania związane z uzupełnianiem zapasów wypełnione lokalizacją prawie do limitu przepełnienia dla pozycji *T0100*. (Przeliczenie jednostek towaru wynosi *1 PL = 100 każdy*.) W związku z tym pozostała praca uzupełniania zapasów spowodowałaby przekroczenie limitu przepełnienia w lokalizacji.

Dopóki w lokalizacji nie zostanie pobrana wystarczająca ilość zapasów w celu przeniesienia jej poniżej progu zwolnienia pracy w menu urządzenia przenośnego, ta praca uzupełniania pozostanie zablokowana.

#### <a name="sales-order-pick"></a>Odbiór zamówienia sprzedaży

Aby można było ukończyć pozostałe zadanie uzupełniania zapasów, lokalizacja pobrania musi zostać wyczerpana z zapasów do poziomu, w którym może zostać odblokowana pozostała praca uzupełniająca. Innymi słowy, suma ilości dostępnych zapasów w lokalizacji i ilości uzupełniania nie może przekroczyć wartości **Ilości przepełnienia**. Gdy ta suma jest mniejsza niż ilość przepełnienia, zostanie odblokowana pozostała praca uzupełniająca.

1. Zaloguj się do aplikacji magazynowania jako użytkownik w magazynie *61*. (Wprowadź *61* jako identyfikator użytkownika i *1* jako hasło.)
1. Przejdź do **Wychodzące \> Pobieranie sprzedaży**.
1. Wprowadź pierwszy identyfikator pracy dla zamówienia sprzedaży 1.

    Zapoznaj się z identyfikatorami roboczymi dla zamówień sprzedaży, które zostały wykonane wcześniej, na stronie **Szczegóły pracy**. Wprowadzony tutaj identyfikator pracy będzie generował pracę pobrania dla ilości 10 każdy z dwóch odrębnych lokalizacji.

1. Kliknij przycisk **OK**.

    Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, które można pobrać z pierwszej lokalizacji.

1. W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.
1. Wybierz przycisk **OK** (symbol znacznika wyboru).

    Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, które można pobrać z następnej lokalizacji.

1. W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.
1. Wybierz przycisk **OK** (symbol znacznika wyboru).

    Strona **Zamówień sprzedaży: Pobranie** zawiera instrukcje, aby odłożyć obie kompletacje do lokalizacji wyjściowej.

1. Kliknij przycisk **OK**.

    Zostanie wyświetlony komunikat „Praca zakończona”.

1. Wprowadź drugi identyfikator pracy dla zamówienia sprzedaży 1.

    Istnieje tylko jedno zadanie pobrania dla tego identyfikatora pracy.

1. Kliknij przycisk **OK**.

    Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, z której można pobrać.

1. W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.

    Określony numer identyfikacyjny będzie jednym z wygenerowanych przez system numerów identyfikacyjnych na podstawie zadań związanych z pracą uzupełniania zapasów. Aby mieć pewność, że jest przechwytywany poprawny identyfikator numeru identyfikacyjnego, należy sprawdzić, czy na stronie **Lista dostępnych** znajduje się pozycja zapasy, lokalizacja i ilość.

1. Wybierz przycisk **OK** (symbol znacznika wyboru).
1. Potwierdź instrukcje dotyczące zadania wysyłania do wychodzącej lokalizacji przemieszczania.
1. Kliknij przycisk **OK**.

    Zostanie wyświetlony komunikat „Praca zakończona”.

Zamówienie sprzedaży 2 jest zablokowane przed pobraniem, ponieważ zadanie uzupełniania zapasów, z którym jest połączony, nie zostało zakończone. Obecnie w lokalizacji pobrania występuje wciąż liczba 30 każdy, a ilość uzupełnienia zapasów dla zamówienia sprzedaży 2 wynosi 60 każdy. Suma dostępnych zapasów i zapasów uzupełniających (90 każdy) przekracza ilość przepełnienia 0,65 PL (lub 65 każdy). Aby można było ukończyć pracę uzupełniania zapasów, należy pobrać zamówienie sprzedaży 3.

1. Wprowadź identyfikator pracy dla zamówienia sprzedaży 3.

    Istnieje tylko jedno zadanie pobrania dla tego identyfikatora pracy.

1. Kliknij przycisk **OK**.

    Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, z której można pobrać.

1. W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.

    Określony numer identyfikacyjny będzie jednym z wygenerowanych przez system numerów identyfikacyjnych na podstawie zadań związanych z pracą uzupełniania zapasów. Aby mieć pewność, że jest przechwytywany poprawny identyfikator numeru identyfikacyjnego, należy sprawdzić, czy na stronie **Lista dostępnych** znajduje się pozycja zapasy, lokalizacja i ilość.

1. Wybierz przycisk **OK** (symbol znacznika wyboru).
1. Potwierdź instrukcje dotyczące zadania wysyłania do wychodzącej lokalizacji przemieszczania.
1. Kliknij przycisk **OK**.

    Zostanie wyświetlony komunikat „Praca zakończona”.

Gdy tylko suma ilości na stanie w miejscu pobrania i ilości do uzupełnienia spadnie poniżej progu, będzie można przetworzyć pozostałą pracę uzupełniania.

Wróć do strony **Szczegóły pracy** i zwróć uwagę, że dostępność prac uzupełniających dla ostatniej części uzupełnienia (dla zamówienia sprzedaży 2) to *Otwarte*, ponieważ w tej lokalizacji jest teraz wystarczająco dużo miejsca, aby przyjąć uzupełnienie.

Teraz można przetwarzać tę pracę uzupełniania zapasów za pośrednictwem urządzenia przenośnego.

1. Przejdź do **Zapasy \> Uzupełnienie**.

    Zostanie wyświetlony monit o wykonanie resztę pracy uzupełniania zapasów. Wyświetlany jest numer pozycji, ilość i lokalizacja do pobrania.

1. W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.
1. Wybierz przycisk **OK** (symbol znacznika wyboru).

    System generuje numer identyfikacyjny docelowy dla nowego numeru identyfikacyjnego pobranego towaru.

1. Wybierz przycisk **OK**, aby zatwierdzić wartość.

    Wyświetlana jest pokazana praca, która nakazuje użytkownikowi umieszczenie docelowego numeru identyfikacyjnego w lokalizacji uzupełnienia zapasów. Lokalizacja *Odłożenia* powinna być **06A01R2S1B**.

1. Potwierdź szczegóły umieszczania i kliknij przycisk **OK**.

    Otrzymujesz komunikaty „Praca zakończona” i „Brak dostępnej pracy”.

Teraz może być pobrane zamówienie sprzedaży 2. Po zakończeniu pracy uzupełniania zapasów połączonej z zamówieniem sprzedaży jego praca została odblokowana.

1. Wprowadź identyfikator pracy dla zamówienia sprzedaży 2.

    Istnieje tylko jedno zadanie pobrania dla tego identyfikatora pracy.

1. Kliknij przycisk **OK**.

    Na stronie zadania **Zamówień sprzedaży: Pobranie** wyświetlany jest kod towaru, ilość i lokalizacja, z której można pobrać.

1. W polu **LP** wprowadź numer identyfikacyjny dla towaru w pokazanej lokalizacji.

    Określony numer identyfikacyjny będzie wygenerowanych przez system numerem identyfikacyjnym na podstawie zadania związanego z pracą uzupełniania zapasów. Aby mieć pewność, że jest przechwytywany poprawny identyfikator numeru identyfikacyjnego, należy sprawdzić, czy na stronie **Lista dostępnych** znajduje się pozycja zapasy, lokalizacja i ilość.

1. Wybierz przycisk **OK** (symbol znacznika wyboru).
1. Potwierdź instrukcje dotyczące zadania wysyłania do wychodzącej lokalizacji przemieszczania.
1. Kliknij przycisk **OK**.

    Zostanie wyświetlony komunikat „Praca zakończona”.

## <a name="notes-and-tips"></a>Notatki i porady

- Ta funkcja działa ze wszystkimi typami uzupełniania: zapotrzebowaniem na falę, min./maks., zapotrzebowaniem na obciążenie i szczelinami.
- Można ręcznie zastępować dostępność pracy uzupełniania zapasów dla każdego nagłówka pracy na stronie **Szczegóły pracy**.
- Jeśli system ustawi dostępność pracy uzupełniania zapasów, będzie ona uwzględniać zapasy znajdujące się już w lokalizacji przed ukończeniem pracy
- Każda część pracy z zamówieniem sprzedaży jest połączona z określoną pracą uzupełniania zapasów. Nie ma odpowiedniej funkcji dostępności pracy w sprzedaży.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]