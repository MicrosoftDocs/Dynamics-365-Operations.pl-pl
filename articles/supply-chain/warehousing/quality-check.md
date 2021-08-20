---
title: Kontrola jakości
description: Ten temat zawiera informacje dotyczące funkcji Kontrola jakości. Ta funkcja pozwala pracownikom magazynowym na szybkie sprawdzenie jakości podczas przyjmowania towarów do obszaru doków przychodzących.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: fb61597dd7e1100efe4fbdeb7982858838caff26ea4a6d3d92547201a04cc977
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780925"
---
# <a name="quality-check"></a>Kontrola jakości

[!include [banner](../includes/banner.md)]

Funkcja *Kontroli jakości* pozwala pracownikom magazynowym na szybkie sprawdzenie jakości podczas przyjmowania towarów do obszaru doków przychodzących. Te kontrole na miejscu są korzystne w przypadku, gdy pracownicy badają pakowanie lub inne łatwo rozpoznawalne części towaru. Ta funkcja prowadzi pracowników do szybkiego spojrzenia, aby sprawdzić, czy coś jest ewidentnie wadliwe lub uszkodzone, zanim zapiszą zapasy w miejscu składowania.

Ta funkcja jest alternatywą dla standardowego procesu kontroli jakości. Zapewnia większą elastyczność i szybsze przetwarzanie.

Podczas korzystania z tej funkcji przybycie i kontrola jakości odbywają się w następujący sposób:

1. Kiedy nadejdzie przesyłka, magazynier rejestruje przybycie. Pracownik również skanuje numer identyfikacyjny w celu zarejestrowania lokalizacji.
1. Pracownik przeprowadza szybką kontrolę jakości i zapisuje wynik (pozytywny lub negatywny) dla danego numeru identyfikacyjnego.
1. Następuje jedna z następujących czynności:

    - Jeśli kontrola jakości jest przekazywana, numer identyfikacyjny jest akceptowany i kierowany do lokalizacji odbiorczej w zwykły sposób.
    - Jeśli kontrola jakości nie powiodło się, oznacza to, że numer identyfikacyjny jest odrzucony, a istniejące prace odkładane dla niej są przekierowywane do innej lokalizacji w celu dalszej kontroli. Zostanie utworzone nowe zlecenie kontroli jakości. Aby wyświetlić zlecenie kontroli jakości utworzone na podstawie niepowodzenia kontroli jakości, należy przejść do **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.

Ten proces można również skonfigurować w taki sposób, aby wszystkie zeskanowane numey identyfikacyjne zostały natychmiast skierowane do lokalizacji kontroli jakości.

## <a name="turn-on-the-quality-check-feature"></a>Włącz funkcję kontroli jakości

Aby móc używać funkcji *Kontroli jakości*, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Kontrola jakości*

## <a name="set-up-the-feature-for-the-example-scenario"></a>Skonfiguruj funkcję dla tego scenariusza przykładowego

Ta sekcja zawiera wskazówki oraz przykład, w jaki sposób należy skonfigurować funkcję *Kontrola jakości* i przygotować przykładowe dane do scenariusza przykładowego, który opisano w dalszej części tego tematu.

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tymi [przykładowymi scenariuszami](#example-scenario) przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

### <a name="quality-check-template"></a><a name="quality-template"></a>Szablon kontroli jakości

Szablon kontroli jakości określa reguły przeprowadzania szybkich kontroli jakości w momencie przyjmowania.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablon kontroli jakości**.
1. Kliknij przycisk **Nowe**, aby dodać szablon do siatki.
1. Ustaw następujące wartości, aby zdefiniować nowy szablon:

    - **Nazwa szablonu kontrolu jakości:** *Kontrola doku*

        Umożliwia wprowadzenie nazwy identyfikującej zasady stosowane do tego szablonu.

    - **Zasady akceptacji:** *Monituj użytkownika*

        Umożliwia określenie, czy użytkownicy powinni być monitowani o zaakceptowanie lub odrzucenie jakości zapasów podczas przetwarzania pracy lub określać, czy jakość ma być automatycznie odrzucona. Dostępne opcje to *Automatyczne odrzucanie* i *Monituj użytkownika*.

    - **Zasady przetwarzania jakości:** *Tworzenie zlecenia kontroli jakości*

        Wybierz zasadę, która ma być stosowana w przypadku odrzucenia jakości zasobów reklamowych. Dostępne są następujące opcje:

        - *Utwórz tylko pracę* — Utwórz tylko pracę, aby ułatwić przenoszenie zapasów.
        - *Tworzenie zlecenia kontroli jakości* — umożliwia tworzenie zlecenia kontroli jakości w celu ułatwienia testowania jakości.

    - **Grupa testowa:** *Odgrodzona*

        Umożliwia określenie grupy testowej, która powinna być używana w tworzonym zleceniu kontroli jakości. Grupy testowe są konfigurowane w module **Zarządzania zapasami**.

        Pozostaw opcję **Testy destrukcyjne** wyłączoną dla grupy testowej Ta opcja określa, czy próbka zostanie zniszczona w ramach testów w grupie testowej. Jeśli używany jest test niszczący, system generuje transakcję magazynową po utworzeniu zlecenia kontroli jakości dla towaru. Nowa transakcja magazynowa przewiduje zmniejszenie zapasu dla ilości testowej. Zmniejszenie zapasów następuje, gdy zlecenie kontroli jakości jest zakończone w kroku walidacji. Transakcja magazynowa jest identyfikowana jako zlecenie kontroli jakości.

### <a name="work-class--quality-check"></a><a name="work-class"></a>Klasa robocza – Kontrola jakości

Klas pracy są używane do kierowania i/lub ograniczania typów wierszy zlecenia, które pracownicy magazynu może przetwarzać na urządzeniu przenośnym.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.
1. Wybierz pozycję **Nowy**, aby utworzyć nową klasę pracy.
1. W nagłówku ustaw następujące wartości:

    - **Identyfikator klasy roboczej:** *Sprawdzanie jakości kontroli*

        Umożliwia wprowadzenie nazwy identyfikującej klasę pracy.

    - **Opis:** *Sprawdzanie jakości kontroli*

        Służy do wprowadzania krótkiego opisu, który wskazuje klasę pracy, której jest używana.

    - **Typ zlecenia pracy:** *Jakość w kontroli jakości*

        Wybierz typ zlecenia pracy utworzonego przez klasę pracy. Podczas ustawiania działania kontroli jakości należy zawsze wybierać opcje *Jakość w kontroli jakości*.

1. Na skróconej karcie **Prawidłowe typy lokalizacji odłożenia** pozostaw pole **Typ lokalizacji** puste.

    W przypadku wybrania typu lokalizacji można ograniczyć lokalizacje, w których towary mogą być umieszczane po pobraniu. To pole jest używane, gdy dyrektywa lokalizacji próbuje rozpoznać lokalizację lub gdy pracownik magazynu ręcznie określa lokalizację w elemencie menu urządzenia przenośnego.

Aby uzyskać więcej informacji o klasach pracy i sposobach ich tworzenia, należy zapoznać się z tematem [Tworzenie klasy pracy](tasks/create-work-class.md).

### <a name="work-template"></a>Szablon pracy

Szablony pracy pozwalają zdefiniować operacje pracy, które muszą być wykonane w magazynie. Zwykle operacje pracy w magazynie składają się z dwóch działań: pracownik magazynu odbiera dostępny towar w lokalizacji, a następnie odkłada odebrany towar w innej lokalizacji. Szablon pracy kontroli jakości określa operacje wykonywane przy wykonywaniu kontroli jakości.

#### <a name="purchase-orders"></a>Zamówienia zakupu

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. W nagłówku w polu **Typ zlecenia pracy** zaznacz opcję *Zamówienia zakupu*.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Wybierz szablon pracy, który powinien zawierać krok kontroli jakości. W sekcji **Przegląd** w polu **Szablon pracy** wybierz pozycję *Paragon zamówienia zakupu 51*.
1. W sekcji **Szczegóły szablonu pracy** zwróć uwagę, że siatka ma dwa istniejące wiersze: jeden dla *Pobrania*, a drugi do *Odłożenia*.
1. W sekcji **Szczegóły szablonu pracy** wybierz opcję **Nowy**, aby dodać wiersz kontroli jakości do siatki. Zwróć uwagę, że pole **Numer wiersza** dla nowego wiersza jest ustawione na wartość *3*.
1. W nowym wierszu ustaw następujące wartości. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Typ pracy:** *Kontrola jakości*
    - **Identyfikator klasy roboczej:** *Zakup*
    - **Nazwa szablonu kontrolu jakości:** *Kontrola doku*

        Wybierz unikatowy identyfikator dla klasy roboczej. Ta wartość służy do konfigurowania elementów menu na urządzeniu przenośnym i typów pracy, które te elementy mają przetwarzać.

1. W okienku akcji wybierz opcję **Zapisz**, aby zapisać dotychczasową pracę.

    Otrzymujesz komunikat informacyjny o treści „Nieprawidłowe - kontrola jakości musi nastąpić bezpośrednio po pobraniu”. Dlatego należy zmienić wartość **Numeru wiersza** dla dodanego właśnie wiersza.

1. Aby zmienić wartość **Numeru wiersza** dla nowego wiersza, należy wykonać następujące kroki:

    1. W sekcji **Szczegóły szablonu pracy** wybierz wiersz, w którym pole **Typ pracy** ma wartość *Kontrola jakości*.
    2. Wybierz przycisk **Przenieś w górę** lub **Przenieś w dół**, aby przenieść wiersz *Kontroli jakości*, tak aby był po wierszu *Pobranie*.

1. Na okienku akcji wybierz opcję **Zapisz**.

#### <a name="quality-in-quality-check"></a>Kontrolowane aspekty jakości

Następnie uUtwórz szablon pracy dla kontroli jakości.

1. W nagłówku strony **Szablony pracy** zmień wartość pola **Typ zlecenia pracy** na *Jakość w kontroli jakości*.
1. W okienku akcji wybierz opcję **Nowy** w okienku akcji, aby dodać nowy wiersz do siatki w sekcji **Przegląd**.
1. W nowym wierszu ustaw następujące wartości:

    - **Szablon pracy:** *51 Kontrola jakości*

        Wprowadź nazwę szablonu.

    - **Opis szablonu pracy:** *51 Kontrola jakości*

1. W okienku akcji wybierz opcję **Zapisz**, aby sekcja **Szczegóły szablonu pracy** stała się dostępna.
1. Gdy nowy szablon jest wciąż wybrany w sekcji **Przegląd**, wybierz opcję **Nowy** w sekcji **Szczegóły szablonu pracy**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Typ pracy:** *Pobranie*
    - **Identyfikator klasy roboczej:** *Sprawdzanie jakości kontroli*

        Wybierz nazwę [klasy pracy](#work-class), która została utworzona wcześniej dla pracy kontroli jakości.

1. W sekcji **Szczegóły szablonu pracy** wybierz ponownie opcję **Nowy**, aby dodać kolejny wiersz.
1. W nowym wierszu ustaw następujące wartości:

    - **Typ pracy:** *Odłożenie*
    - **Identyfikator klasy roboczej:** *Sprawdzanie jakości kontroli*

        Wybierz nazwę [klasy pracy](#work-class), która została utworzona wcześniej dla pracy kontroli jakości.

1. Na okienku akcji wybierz opcję **Zapisz**.

Aby uzyskać więcej informacji dotyczących szablonów pracy, zobacz [Kontrolowanie pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji](control-warehouse-location-directives.md)

### <a name="location-directive--quality-failures"></a>Dyrektywa lokalizacji — błędy jakości

Dyrektywy lokalizacji to zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego. Na przykład w ramach transakcji zamówienia sprzedaży, dyrektywa lokalizacji określa, gdzie towary zostaną pobrane i gdzie zostaną umieszczone pobrane zapasy. Należy skonfigurować regułę dyrektywy lokalizacji, aby określić, jak będą obsługiwane niepowodzenia kontroli jakości.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W lewym okienku skonfiguruj pole **Typ zlecenia produkcyjnego**, aby *Zamówienia zakupu* działały z dyrektywami lokalizacji tego typu.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć dyrektywę lokalizacji do kontroli jakości.
1. W nagłówku ustaw następujące wartości:

    - **Numer sekwencyjny:** Zaakceptuj wartość domyślną.
    - **Nazwa:** *51 do jakości*

1. Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Typ pracy:** *Odłożenie*
    - **Oddział:** *5*
    - **Magazyn:** *51*

1. W okienku akcji wybierz opcję **Zapisz**, aby zapisać dyrektywę i udostępnić skróconą kartę **Wiersze**.
1. Na skróconej karcie **Wiersze** wybierz **Nowe**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Od ilości:** *1*
    - **Do ilości:** *1000000*

1. W okienku akcji wybierz opcję **Zapisz**, aby zapisać nowy wiersz i udostępnić na skróconą kartę **Akcje dyrektywy lokalizacji**.
1. Gdy nowy wiersz jest wciąż wybrany na skróconej karcie **Wiersze**, wybierz opcję **Nowy** na skróconej karcie **Akcje dyrektywy lokalizacji**, aby dodać wiersz do siatki, tak aby można było skonfigurować akcję dla wiersza.
1. W nowym wierszu należy określić wartość w polu **Nazwa** na *Jakość*. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.
1. W okienku akcji wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę** na skróconej karcie **Dyrektywy akcji lokalizacji**.
1. Mimo że dodany wiersz jest wciąż zaznaczony na skróconej karcie **Akcje dyrektywy lokalizacji**, wybierz opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe, w którym można edytować kwerendę dotyczącą danej akcji.
1. Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do kwerendy.
1. W nowym wierszu ustaw następujące wartości:

    - **Tabela:** *Lokalizacje*
    - **Tabela pochodna:** *Lokalizacje*
    - **Pole:** *Lokalizacja*
    - **Kryteria QMS:** *QMS*

    Lokalizacja *QMS* jest lokalizacją magazynu dla jakości.

1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. Musisz teraz zmienić kolejność dyrektyw lokalizacji zamówienia zakupu dla magazynu *51*. Zapisz nową dyrektywę lokalizacji *51 do jakości*, odśwież stronę i wybierz dyrektywę lokalizacji z listy. Następnie użyj przycisków **Przenieś w górę** i **Przenieś w dół** w okienku akcji, aby umieścić dyrektywę lokalizacji dla magazynu *51* w następującej kolejności: (Przed wybraniem opcji **Przenieś w górę** lub **Przenieś w dół**, na liście należy wybrać lokalizację dyrektywy.)

    1. 51 do jakości
    2. 51 bezpośrednie zamówienie zakupu
    3. 51 QMS

### <a name="mobile-device-menu-items"></a>Elementy menu urządzenia przenośnego

Skonfiguruj element menu, aby urządzenia przenośne mogły wykonywać funkcję **Kontroli jakości**.

#### <a name="purchase-putaway"></a>Odłożenie zakupu

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Na liście wybierz element menu **Odłożenie zakupu**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. W sekcji **Klasy robocze** wybierz **Nowe**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Identyfikator klasy roboczej:** *Sprawdzanie jakości kontroli*

        Wpisz nazwę [klasy pracy](#work-class), która została utworzona wcześniej dla pracy kontroli jakości.

    - **Typ zlecenia pracy:** *Jakość w kontroli jakości*

1. Na okienku akcji wybierz opcję **Zapisz**.

#### <a name="purchase-order-line-receiving"></a>Przyjęcie wiersza zamówienia zakupu

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku ustaw następujące wartości:

    - **Nazwa elementu menu:** *Wiersz zamówienia zakupu – przyjęcie*
    - **Nazwa:** *Wiersz zamówienia zakupu – przyjęcie*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Nie*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości. Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.

    - **Proces tworzenia pracy:** *Przyjęcie i umieszczenie wierszy zamówienia zakupu*
    - **Generuj numer identyfikacyjny:** *Tak*
    - **Szablon pracy:** *51 przyjęcie zamówienia zakupu*

1. Na okienku akcji wybierz opcję **Zapisz**.

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Dodawanie element menu do menu urządzenia przenośnego

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. W lewym okienku wybierz menu **Przychodzące**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. W kolumnie **Dostępne menu i elementy menu** wybierz nowy element menu **Wiersz zamówienia zakupu – przyjęcie**.
1. Wybierz strzałkę w prawo, aby przenieść **Wiersz zamówienia zakupu – przyjęcie** do kolumny **Struktura menu**.
1. W kolumnie **Struktura menu** wybierz opcję **Wiersz zamówienia zakupu – przyjęcie**, a następnie wybierz przycisk strzałka w górę lub strzałka w dół, aby przenieść element menu do żądanej pozycji w menu urządzenie przenośne.
1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="example-scenario"></a><a name="example-scenario"></a>Przykładowy scenariusz

Po wykonaniu wszystkich poprzednio opisanych przykładowych danych i ich skonfigurowania można korzystać z tego scenariusza, aby wypróbować funkcję *Kontroli jakości*. Wartości przedstawione w tym scenariuszu zakładają, że pracujesz ze standardowymi danymi demonstracyjnymi, które zostały wybrane firmę **USMF**, oraz że zostały przygotowane przykładowe rekordy opisane wcześniej w tym temacie. Ten scenariusz służy także jako przykład, który pokazuje, w jaki sposób funkcja może być używana w ustawieniu produkcji.

### <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:

    - **Konto dostawcy:** *104*
    - **Magazyn:** *51*

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i otworzyć nowe zamówienie zakupu.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** siatka zawiera nowy, pusty wiersz. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *M9203*
    - **Ilość:** *3*
    - **Jednostka:** *PL*

1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="process-quality-check-receiving"></a>Odbiór kontroli jakości procesu

Po utworzeniu zamówienia zakupu można go odebrać za pomocą elementu menu **Wiersz zamówienia zakupu – przyjęcie** oraz funkcji *Kontroli jakości*.

#### <a name="receive-pallet-1"></a>Odbiór palety 1

1. Zaloguj się do aplikacji Warehouse Management jako użytkownik dla magazynu *51*. (Wprowadź *51* jako identyfikator użytkownika i *1* jako hasło.)
1. Przejdź do **Przychodzące \> Wiersz zamówienia zakupu – przyjęcie**.
1. W polu **PONUM** wprowadź numer zamówienia zakupu.
1. Potwierdź numer zamówienia zakupu.
1. W polu **LINENUM** wprowadź numer otrzymywanego wiersza zamówienia zakupu. Ponieważ zamówienie ma tylko jedną linię w tym scenariuszu, wpisz *1* w polu **LINENUM** dla każdego kroku odbioru.
1. Potwierdź numer wiersza.
1. W polu **Ilość** wprowadź ilość do odbioru. Ponieważ zamówienie zakupu jest przeznaczone dla trzech palet (*PL*) w tym scenariuszu, a istnieją trzy czynności, należy wprowadzić wartość *1* w polu **Ilość** dla każdego kroku przyjęcia.
1. Potwierdź ilość.

    Strona **Kontrola jakości**, która zostanie wyświetlona, nie zawiera pól wpisów. Ma tylko przycisk potwierdzenia (znacznik wyboru) u dołu i przycisk Menu (**≡**) u góry. (Przycisk Menu jest czasami nazywany przyciskiem hamburgera lub hamburgerem). Aby przyspieszyć proces kontroli jakości, gdy paleta przejdzie kontrolę jakości, użytkownik po prostu potwierdza stronę **Kontrolę jakości**.

    ![Strona kontroli jakości.](media/quality-check.png "Strona kontroli jakości")

1. Wybierz przycisk potwierdzenia, aby przejść kontrolę jakości dla palety 1 z wiersza 1.

    Wyświetlona strona **Zamówienia zakupu: Odłóż** zawiera szczegóły dotyczące pracy odłożenia:

    - **Lokalizacja:** system ustalił lokalizację

        Ta lokalizacja jest wyznaczonym miejscem odłożenia na potrzeby przyjęcia zamówienia zakupu.

    - **Numer identyfikacyjny:** wygenerowany przez system identyfikator numeru identyfikacyjnego
    - **Pozycja:** *M9203*
    - **Ilość:** *1 PL: 100 każdy*

    Pokazany jest również opis pozycji.

1. Potwierdź pracę odłożenia.

    Na stronie **Zadania** dla przyjęcia wiersza zamówienia zakupu zostanie wyświetlony komunikat „praca wykonana”. Pole **LINENUM** jest dostępne w taki sposób, aby można było rozpocząć otrzymywanie następnej palety.

#### <a name="receive-pallet-2"></a>Odbiór palety 2

W tym scenariuszu paleta 2 zostanie odrzucona.

1. W polu **LINENUM** wprowadź wartość *1* i potwierdź numer wiersza.
1. Pole **Ilość** jest teraz dostępne. Wprowadź wartość *1* i potwierdź ilość.

    Zostanie wyświetlona strona **Kontrola jakości**. W przypadku tego przyjęcia paleta zostanie odrzucona w celu uzyskania jakości i zostanie umieszczona w lokalizacji jakości *QMS*.

1. Wybierz przycisk menu (**≡**) u góry strony, a następnie w menu wybierz opcję **Odrzuć**.
1. Na wyświetlonej stronie **Zadanie** wprowadź **QMS** jako lokalizację *Odłożenia*, aby wysłać paletę do dalszej inspekcji.

    Wyświetlona strona **Jakość w kontroli jakości: Odłóż** zawiera szczegóły dotyczące pracy odłożenia:

    - **Lokalizacja:** *QMS*

        Ta lokalizacja jest wyznaczonym miejscem odłożenia na potrzeby przyjęcia odrzuconej jakości.

    - **Numer identyfikacyjny:** wygenerowany przez system identyfikator numeru identyfikacyjnego
    - **Pozycja:** *M9203*
    - **Ilość:** *1 PL: 100 każdy*

    Pokazany jest również opis pozycji.

1. Potwierdź pracę odłożenia.

    Na stronie **Zadania** dla przyjęcia wiersza zamówienia zakupu zostanie wyświetlony komunikat „praca wykonana”. Pole **LINENUM** jest dostępne w taki sposób, aby można było rozpocząć otrzymywanie następnej palety.

Teraz ukończono sprawdzanie jakości i utworzono zlecenie kontroli jakości dla odrzuconej palety. Aby wyświetlić zlecenie kontroli jakości utworzone, należy przejść do **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.

Testy zlecenia kontroli jakości można teraz przetworzyć. Testowanie jakości nie jest opisane w tym temacie.

Aby uzyskać więcej informacji o zarządzaniu jakością funkcji, zapoznaj się z [Zarządzanie jakością — omówienie](../inventory/enable-quality-management.md)

#### <a name="receive-pallet-3"></a>Odbiór palety 3

W tym scenariuszu paleta 3 zostanie zaakceptowana.

1. W polu **LINENUM** wprowadź wartość *1* i potwierdź numer wiersza.
1. Pole **Ilość** jest teraz dostępne. Wprowadź wartość *1* i potwierdź ilość.

    Zostanie wyświetlona strona **Kontrola jakości**. W przypadku tego przyjęcia paleta zostanie zaakceptowana w celu uzyskania jakości i zostanie umieszczona w lokalizacji odłożenia partii.

1. Wybierz przycisk potwierdzenia, aby przejść kontrolę jakości.

    Wyświetlona strona **Zamówienia zakupu: Odłóż** zawiera szczegóły dotyczące pracy odłożenia:

    - **Lokalizacja:** system ustalił lokalizację

        Ta lokalizacja jest wyznaczonym miejscem odłożenia na potrzeby przyjęcia zamówienia zakupu.

    - **Numer identyfikacyjny:** wygenerowany przez system identyfikator numeru identyfikacyjnego
    - **Pozycja:** *M9203*
    - **Ilość:** *1 PL: 100 każdy*

    Pokazany jest również opis pozycji.

1. Potwierdź pracę odłożenia.

    Na stronie **Zadania** dla przyjęcia wiersza zamówienia zakupu zostanie wyświetlony komunikat „praca wykonana”. Pole **LINENUM** jest dostępne w taki sposób, aby można było rozpocząć otrzymywanie następnej palety.

1. Wybierz przycisk menu (**≡**) u góry strony, a następnie w menu wybierz opcję **Anuluj**, aby wrócić do menu.

Teraz możesz zamknąć aplikację mobilną.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]