---
title: Wyświetlanie sald urlopów w interfejsie wykonania hal produkcyjnych
description: Ten artykuł zawiera przykładowy scenariusz, który pokazuje, jak skonfigurować Microsoft Dynamics 365 Supply Chain Management tak, aby używał statystyk płacowych do zapewnienia pracownikom wglądu w stan ich urlopów w bieżącym roku.
author: johanhoffmann
ms.date: 04/22/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-04-22
ms.dyn365.ops.version: 10.0.XX
ms.openlocfilehash: 2a6b6f52bfa7539b7c9bb5841536b0d564d0274c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852281"
---
# <a name="show-vacation-balances-in-the-production-floor-execution-interface"></a>Wyświetlanie sald urlopów w interfejsie wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera przykładowy scenariusz, który pokazuje, jak skonfigurować Microsoft Dynamics 365 Supply Chain Management tak, aby na podstawie statystyk płacowych udostępniał każdemu pracownikowi informacje o stanie jego urlopu w bieżącym roku. Pracownicy będą mogli zobaczyć stan swojego urlopu w oknie dialogowym **Mój dzień** w interfejsie wykonawczym hali produkcyjnej.

Ten scenariusz wykorzystuje duńskie prawo urlopowe, w którym rok urlopowy trwa od 1 września do 31 sierpnia. W tym scenariuszu Twoja firma zatrudniła nowego pracownika i przyzna mu 10 dni urlopu do końca bieżącego roku urlopowego.

## <a name="turn-on-the-required-features"></a>Włącz wymagane funkcje

Aby uruchomić ten scenariusz, musisz włączyć widok *Mój dzień dla interfejsu wykonawczego hali produkcyjnej* w [Zarządzaniu cechami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Aby dowiedzieć się, jak włączyć tę i inne funkcje interfejsu wykonawczego hali produkcyjnej, zobacz [Konfiguracja interfejsu wykonawczego hali produkcyjnej](production-floor-execution-configure.md).

## <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

## <a name="create-a-new-pay-type"></a>Utwórz nowy typ wypłaty

Zacznij od stworzenia nowego *typu wypłaty*, który będzie śledził zarobione przez pracowników dni urlopu (określane też jako ich *bilans urlopowy*). Zazwyczaj do obliczania wynagrodzenia pracowników używa się typów płac. Jednak typ wypłaty, który tutaj utworzysz, będzie używany do obliczania salda.

1. Przejdź do **Czas pracy \> Konfiguracja \> Lista płac \> Typy wypłat**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Typ wynagrodzenia:** *5151-1*
    - **Opis:** *Licznik dni urlopu pracownika*
    - **Uwzględnij w eksporcie:** *Nie*

## <a name="update-the-pay-agreement"></a>Aktualizacja porozumienia płacowego

W tej części edytujesz istniejącą *porozumienie płacowe*, dodając do niej nowy typ wynagrodzenia oraz ustawiając zasady, które określają, w jaki sposób saldo urlopu każdego pracownika jest korygowane po zarejestrowaniu dni urlopu.

1. Przejdź do **Czas pracy \> Konfiguracja \> Lista płac \> Porozumienia płacowe**.
1. Wybierz porozumienie płacowe, w którym chcesz ustawić politykę urlopową. (Jeśli pracujesz ze standardowymi danymi przykładowymi USMF, jest tylko jedno porozumienie płacowe, *Man*.)
1. Upewnij się, że wybrane porozumienie płacowe jest ważne na bieżącą datę. Jeśli pracujesz ze standardowymi przykładowymi danymi USMF, pole **Do dnia dzisiejszego** w umowie płacowej *Man* może być ustawione na datę, która należy do przeszłości. W zależności od potrzeb zmień wartość tak, aby była o rok lub dwa w przyszłości.
1. W okienku akcji kliknij pozycję **Wiersze porozumienia**.
1. Na stronie **Wiersze porozumienia płacowego**, na skróconej karcie **Przegląd**, ustaw następujące wartości na pasku narzędzi:

    - Na pierwszej liście rozwijanej wybierz **Poniedziałek**.
    - Na drugiej liście rozwijanej wybierz **Absencja**.

1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. W nowym wierszu ustaw pole **Typ płacy** na typ płacy, który utworzyłeś dla tego scenariusza (*5151-1*). Pozostaw wszystkie pozostałe pola ustawione na wartości domyślne.
1. Podczas gdy nowy wiersz jest wciąż zaznaczony, na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Grupy kodów nieobecności:** *Wakacje*
    - **Użyj stałej ilości:** *Tak*
    - **Stała:** *-1*

1. W okienku akcji wybierz opcję **Dzień kopiowania**.
1. W oknie dialogowym **Dzień kopiowania** ustaw następujące wartości:

    - **Wtorek**, **Środa**, **Czwartek** i **Piątek:** *Tak*
    - **Czy zastąpić?:** *Tak*
    - **Nieobecność:** *Tak*

1. Kliknij przycisk **OK**.

## <a name="create-a-payroll-statistic-group"></a>Utwórz grupę statystyk list płac

*Grupy statystyk płacowych* służą do ustawiania statystyk rejestracji pracowników w danym okresie. W tym scenariuszu użyjesz grupy statystyk płacowych do obliczenia liczby dni urlopowych, które pracownicy otrzymali w okresie urlopowym. W Danii okres wakacyjny trwa od 1 września do 31 sierpnia.

1. Przejdź do **Czas pracy \> Konfiguracja \> Lista płac \> Grupy statystyk płacowych**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Grupa statystyk listy płac:** *VAC*
    - **Opis:** *Saldo urlopu*
    - **Przeniesienie:** *Nie*

1. Gdy nowy wiersz jest nadal zaznaczony, wybierz opcję **Konfiguracja** w okienku akcji.
1. Na stronie **Konfiguracja**, w okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. W nowym wierszu należy określić wartość w polu **Rodzaj wynagrodzenia** na *5151-1*.
1. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) pole **Kod okresu**, a następnie wybierz **Wyświetl szczegóły**. Możesz teraz ustawić kod okresu, który później przypiszesz do tego pola.
1. Na stronie **Typy okresów**, na panelu akcji wybierz **Nowy**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Typy okresu:** *RokWakacji*
    - **Opis:** *Rok urlopu*
    - **Częstotliwość:** *Lata*

1. Gdy nowy wiersz jest nadal zaznaczony, wybierz opcję **Generowanie okresów** w okienku akcji.
1. W wyświetlonym oknie dialogowym **Generowanie okresów** można ustawić następujące wartości:

    - **Określ datę rozpoczęcia okresu:** *1 września, 2021 r.*
    - **Długość okresu:** *5*

1. Kliknij przycisk **OK**.
1. Zamknij stronę **Typy okresów**, aby powrócić do strony **Grupy statystyk płacowych**.
1. Ustaw pole **Kod okresu** na typ okresu, który właśnie utworzyłeś (*RokWakacji*).

## <a name="create-a-statistical-balance-setup"></a>Utwórz statystyczną konfigurację równowagi

W tej części utworzysz *ustawienie bilansu statystycznego*, który będzie powiązany z grupą statystyczną listy płac, którą utworzyłeś w poprzedniej części. Później połączysz tę konfigurację bilansu statystycznego z widokiem **Mój dzień** w interfejsie wykonawczym hali produkcyjnej. W widoku **Mój dzień** będzie można wtedy zobaczyć salda urlopów dla typu płacy, który jest przypisany do danej grupy statystyk listy płac.

1. Przejdź do **Czas pracy \> Konfiguracja \> Lista płac \> Ustawienie wagi statystycznej**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. W nowym wierszu ustaw następujące wartości:

    - **Grupa statystyk listy płac:** *VAC*
    - **Nazwa zewnętrzna:** *Saldo urlopu*
    - **Elastyczny czas pracy:** *Nie*

## <a name="create-a-manual-premium"></a>Utwórz ręczną premię

*Premie ręczne* są zazwyczaj wykorzystywane do przyznawania pracownikom dodatkowego wynagrodzenia za dodatkową pracę. W tym scenariuszu utworzysz ręczną premię, której będziesz mógł użyć do ustalenia początkowego salda urlopów dla każdego pracownika.

1. Przejdź do **Czas pracy \> Konfiguracja \> Lista płac \> Ręczne składki**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać rekord.
1. W nowym rekordzie ustaw następujące wartości:

    - **Dodatki:** *VAC*
    - **Opis:** *Korekty salda urlopów pracowników*
    - **Typ wynagrodzenia:** *5151-1*

## <a name="set-a-workers-initial-vacation-balance-and-adjust-it-by-one-day"></a>Ustaw początkowe saldo urlopu pracownika i dostosuj je o jeden dzień

Administratorzy płac używają strony **Zatwierdź**, aby przeglądać i zatwierdzać codzienne rejestracje pracowników. W tym scenariuszu wcielisz się w rolę administratora, który będzie mógł ustawić początkowe saldo urlopu dla pracownika i rejestrować dni urlopu, które pracownik wykorzysta.

1. Wybierz opcję **Czas i frekwencja \> Przejrzyj i zatwierdź \> Zatwierdź lub oblicz**.
1. W oknie dialogowym **Zatwierdź** ustaw następujące pola:

    - **Grupa zatwierdzania** — Wybierz grupę zatwierdzającą, do której należysz. (Jeśli pracujesz ze standardowymi danymi próbnymi USMF, istnieje tylko jedna grupa zatwierdzająca, *AdmMan*).
    - **Widok całej grupy, 1 dzień** – wybierz opcję, a następnie ustaw pole na aktualną datę.

1. Kliknij przycisk **OK**.
1. Na stronie **Zatwierdź** znajduje się lista rekordów, które spełniają twoje kryteria. Wybierz pracownika, którego chcesz zatwierdzić. Jeśli pracujesz ze standardowymi danymi próbek USMF, wybierz pracownika *000496* (*Christina Portra*).
1. Przyznaj wybranemu pracownikowi 10 dni urlopu:

    1. Gdy nowy pracownik jest nadal zaznaczony, wybierz opcję **Wiersze premium** w okienku akcji.
    1. Na stronie **Wiersze premium** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki.
    1. W nowym wierszu ustaw następujące wartości:

        - **Dodatki:** *VAC*
        - **Ilość:** *10*

    1. Zamknij stronę **Wiersze premium**.

1. Na stronie **Zatwierdź** zarejestruj fakt, że pracownik wykorzystał jeden ze swoich dni urlopu w bieżącym dniu:

    1. Kiedy pracownik jest jeszcze zaznaczony, w dolnej części strony, w zakładce **Przegląd**, wybierz **Nowy** na pasku narzędzi, aby dodać wiersz do siatki.
    1. W nowym wierszu ustaw następujące wartości:

        - **Typ rejestracji dziennika:** *Absencja*
        - **Referencja:** *Vacation*

    1. W górnej części strony wybierz **Transfer** na pasku narzędzi, aby zastosować saldo urlopu i obliczyć potrącenie.

## <a name="configure-the-production-floor-execution-interface-so-that-it-includes-the-my-day-dialog-box"></a>Skonfiguruj interfejs wykonawczy hali produkcyjnej tak, aby zawierał okno dialogowe Mój dzień

W tej części dodasz przycisk **Mój dzień** do interfejsu wykonawczego hali produkcyjnej. Pracownicy mogą wtedy użyć tego przycisku, by otworzyć okno dialogowe **Mój dzień**.

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Wykonywanie produkcji \> Konfigurowanie interfejsu wykonania hal produkcyjnych**.
1. Wybierz konfigurację, na przykład *Domyślna*.
1. Następnie w okienku akcji wybierz opcję **Karty projektu**.
1. Na stronie **Zakładki projektu** w okienku listy wybierz *Wszystkie prace*, aby zobaczyć ustawienia dla tej zakładki. W polu **Widok główny** powinna być teraz widoczna wartość *Wszystkie zadania*.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Pasku narzędzi dodatkowych**, w kolumnie **Dostępne działania** wybierz **Mój dzień**. Następnie wybierz przycisk strzałki w prawo, aby przenieść ją do kolumny **Zaznaczone działania**.

## <a name="check-your-balance-in-the-production-floor-execution-interface"></a>Sprawdź swoje saldo w interfejsie wykonawczym hali produkcyjnej

W tej części zalogujesz się do interfejsu wykonawczego hali produkcyjnej jako pracownik, którego urlop ustawiłeś wcześniej. Zostanie otwarte okno dialogowe **Mój dzień**, aby wyświetlić saldo urlopu.

1. Wybierz kolejno opcje **Kontrola produkcji \> Konfiguracja \> Wykonywanie produkcji \> Tworzenie hal produkcyjnych**.
1. Jeśli zostaniesz poproszony o wybranie konfiguracji, wybierz konfigurację, którą ustawiłeś wcześniej w tym scenariuszu (*Domyślna*).
1. Zaloguj się jako użytkownik, którego skonfigurowałeś wcześniej w tym scenariuszu. Jeśli pracujesz ze standardowymi danymi próbnymi USMF, powinieneś móc się zalogować, wpisując *123* w polu **Identyfikator odznaki**. Ten identyfikator odpowiada Christinie Portra.
1. Wybierz **Mój dzień** na lewym pasku narzędzi.
1. Sprawdź sekcję **Bilanse** w oknie dialogowym. W tej sekcji powinno być teraz widoczne, że masz dziewięć dni urlopu.
