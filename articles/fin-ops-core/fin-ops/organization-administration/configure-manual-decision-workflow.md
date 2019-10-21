---
title: Konfigurowanie decyzji ręcznych w przepływie pracy
description: W tym temacie wyjaśniono sposób konfigurowania właściwości decyzji ręcznej.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f46b875f52d3d3e7c755ee92dcd5faddf0d94356
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179498"
---
# <a name="configure-manual-decisions-in-a-workflow"></a>Konfigurowanie decyzji ręcznych w przepływie pracy

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania właściwości decyzji ręcznej.

Aby skonfigurować decyzję ręczną, w edytorze przepływu pracy kliknij decyzję ręczną prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**. Następnie za pomocą procedur zamieszczonych niżej skonfiguruj właściwości decyzji ręcznej.

## <a name="name-the-decision"></a>Nazywanie decyzji

Wykonaj następujące kroki, aby wprowadzić nazwę decyzji ręcznej.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. W polu **Nazwa** wprowadź unikatową nazwę decyzji ręcznej.

## <a name="enter-a-subject-line-and-instructions"></a>Wprowadzanie wiersza tematu i instrukcji

Należy wprowadzić wiersz tematu i instrukcje dla użytkowników przypisanych do decyzji ręcznej. Na przykład jeśli konfigurujesz decyzję dla zapotrzebowań na zakup, użytkownik przypisany do decyzji zobaczy wiersz tematu i instrukcje na stronie **Zapotrzebowania na zakup**. Wiersz tematu pojawia się na pasku komunikatów na stronie. Może wtedy kliknąć ikonę na pasku komunikatów i przeczytać instrukcje. Aby wprowadzić wiersz tematu i instrukcje, należy wykonać poniższe kroki.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. Na karcie **Instrukcje** w polu **Temat elementu pracy** wprowadź wiersz tematu.
3. Aby spersonalizować wiersz tematu, można wstawić symbole zastępcze. Podczas wyświetlania wiersza tematu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi. Wykonaj następujące czynności, aby wstawić symbol zastępczy:

    1. W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.
    2. Kliknij opcję **Wstaw symbol zastępczy**.
    3. Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4. Kliknij przycisk **Wstaw**.

4. Aby dodać tłumaczenia wiersza tematu, wykonaj następujące kroki:

    1. Kliknij opcję **Tłumaczenia**.
    2. Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3. Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.
    4. W polu **Przetłumaczony tekst** wprowadź tekst.
    5. Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 3.
    6. Kliknij przycisk **Zamknij**.

5. W polu **Instrukcje dotyczące elementu produkcyjnego** wprowadź instrukcje.
6. Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze. Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi. Wykonaj następujące czynności, aby wstawić symbol zastępczy:

    1. W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.
    2. Kliknij opcję **Wstaw symbol zastępczy**.
    3. Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4. Kliknij przycisk **Wstaw**.

7. Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:

    1. Kliknij opcję **Tłumaczenia**.
    2. Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3. Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.
    4. W polu **Przetłumaczony tekst** wprowadź tekst.
    5. Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 6.
    6. Kliknij przycisk **Zamknij**.

## <a name="specify-the-possible-outcomes-of-a-decision"></a>Określanie możliwych wyników decyzji

Zazwyczaj gdy dokument jest przypisany do osoby podejmującej decyzje, osobie tej jest zadawane pytanie. Odpowiedź na to pytanie brzmi zazwyczaj **Tak** lub **Nie** albo **Prawda** lub **Fałsz**. Wykonaj następujące kroki, aby określić możliwe wyniki decyzji ręcznej.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. Na karcie **Wyniki** w polu **Wynik 1** wprowadź nazwę wyniku lub opcji.
3. Aby dodać tłumaczenia wyniku, wykonaj następujące kroki:

    1. Kliknij opcję **Tłumaczenia**.
    2. Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3. Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.
    4. W polu **Przetłumaczony tekst** wprowadź tekst.
    5. Kliknij przycisk **Zamknij**.

4. W polu **Wynik 2** wprowadź nazwę wyniku lub opcji.
5. Aby dodać tłumaczenia wyniku, wykonaj następujące kroki:

    1. Kliknij opcję **Tłumaczenia**.
    2. Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3. Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.
    4. W polu **Przetłumaczony tekst** wprowadź tekst.
    5. Kliknij przycisk **Zamknij**.

## <a name="specify-when-notifications-are-sent"></a>Określanie, kiedy są wysyłane powiadomienia

Można wysyłać powiadomienia do osób w momencie wprowadzenia decyzji, jej delegowania lub eskalowania. Wykonaj następujące kroki, aby określić, kiedy i do kogo są wysyłane powiadomienia.

1. W lewym okienku kliknij opcję **Powiadomienia**.
2. Zaznacz pola wyboru obok zdarzeń, o których mają być wysyłane powiadomienia:

    - **\[Wybór 1\]** — przypisany użytkownik wybrał opcję **\[Wybór 1\]**.
    - **\[Wybór 2\]** — przypisany użytkownik wybrał opcję **\[Wybór 2\]**.
    - **Delegowanie** — przypisany użytkownik przypisał decyzję innemu użytkownikowi.
    - **Eskaluj** — przypisany użytkownik nie podjął decyzji w wyznaczonym czasie.

3. Zaznacz wiersz zdarzenia wybranego w kroku 2.
4. Na karcie **Tekst powiadomienia** w polu tekstowym wprowadź tekst powiadomienia.
5. Aby spersonalizować powiadomienie, możesz wstawić symbole zastępcze. Podczas wyświetlania powiadomienia użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi. Wykonaj następujące czynności, aby wstawić symbol zastępczy:

    1. W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.
    2. Kliknij opcję **Wstaw symbol zastępczy**.
    3. Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4. Kliknij przycisk **Wstaw**.

6. Aby dodać tłumaczenia powiadomienia, wykonaj następujące kroki:

    1. Kliknij opcję **Tłumaczenia**.
    2. Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3. Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.
    4. W polu **Przetłumaczony tekst** wprowadź tekst.
    5. Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 5.
    6. Kliknij przycisk **Zamknij**.

7. Na karcie **Odbiorcy** określ, komu będą wysyłane powiadomienia. Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 8.

    <table>
    <thead>
    <tr>
    <th>Opcja</th>
    <th>Adresaci powiadomień</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Uczestnik</td>
    <td>Użytkownicy, którzy są przypisani do określonej grupy lub roli</td>
    <td>
    <ol>
    <li>Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</li>
    <li>Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Użytkownik przepływu pracy</td>
    <td>Użytkownicy w bieżącym przepływie pracy</td>
    <td>
    <ul>
    <li>Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Użytkownik</td>
    <td>Określeni użytkownicy</td>
    <td>
    <ol>
    <li>Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</li>
    <li>Lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników. Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.

## <a name="assign-a-decision"></a>Przypisywanie decyzji

Wykonaj poniższe kroki, aby określić, komu ma zostać przypisana decyzja ręczna.

1. W lewym okienku kliknij opcję **Przypisanie**.
2. Na karcie **Typ przypisania** wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 3.

    <table>
    <thead>
    <tr>
    <th>Opcja</th>
    <th>Użytkownicy, którym jest przypisana decyzja</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Uczestnik</td>
    <td>Użytkownicy, którzy są przypisani do określonej grupy lub roli</td>
    <td>
    <ol>
    <li>Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której ma zostać przypisana decyzja.</li>
    <li>Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której ma zostać przypisana decyzja.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hierarchia</td>
    <td>Użytkownicy w określonej hierarchii organizacyjnej</td>
    <td>
    <ol>
    <li>Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać przypisana decyzja.</li>
    <li>System musi pobrać zakres nazwisk użytkowników z hierarchii. Te nazwy reprezentują użytkowników, którym można przypisać decyzję. Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system: <ol>
    <li>Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</li>
    <li>Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>. Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</li>
    </ol>
    </li>
    <li>Na karcie <strong>Opcje hierarchii</strong> określ, którym użytkownikom w zakresie należy przypisać decyzję: <ul>
    <li><strong>Przypisz do wszystkich pobranych użytkowników</strong> — decyzja zostanie przypisana do wszystkich użytkowników w zakresie.</li>
    <li><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — decyzja zostanie przypisana tylko do ostatniego użytkownika w zakresie.</li>
    <li><strong>Nie uwzględniaj użytkowników spełniających następujący warunek</strong> — decyzja nie zostanie przypisana żadnym użytkownikom w zakresie, którzy spełniają określony warunek. Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Użytkownik przepływu pracy</td>
    <td>Użytkownicy w bieżącym przepływie pracy</td>
    <td>
    <ul>
    <li>Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Użytkownik</td>
    <td>Określeni użytkownicy</td>
    <td>
    <ol>
    <li>Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</li>
    <li>Lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników. Wybierz użytkowników, którym chcesz przypisać decyzję, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Kolejka</td>
    <td>Kolejka elementów roboczych</td>
    <td>
    <ol>
    <li>Po wybraniu wartości w polu <strong>Kolejka</strong> kliknij kartę <strong>Na podstawie kolejki</strong>.</li>
    <li>Aby przypisać decyzję do określonej kolejki, wykonaj następujące czynności: <ol>
    <li>Na liście <strong>Typ kolejki</strong> zaznacz pozycję <strong>Kolejki elementów roboczych</strong>.</li>
    <li>Na liście <strong>Nazwa kolejki</strong> zaznacz kolejkę.</li>
    </ol>
    </li>
    <li>Jeśli określony warunek ma decydować o kolejce, do której zostanie przypisana decyzja, wykonaj następujące czynności: <ol>
    <li>Na liście <strong>Typ kolejki</strong> zaznacz pozycję <strong>Warunkowe kolejki elementów roboczych</strong>.</li>
    <li>Na liście <strong>Nazwa kolejki</strong> zaznacz pozycję <strong>Kolejka warunkowa</strong>.</li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] Ta opcja jest używana tylko do niektórych przepływów pracy, takich jak Zarządzanie sprawami.</blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na podjęcie decyzji. Umożliwia wybranie jednej z następujących opcji:

    - **Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi podjąć decyzję. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    - **Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi podjąć decyzję. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    - **Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi podjąć decyzję.
    - **Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi podjąć decyzję. Może to być na przykład piątek trzeciego tygodnia w miesiącu.
    - **Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi podjąć decyzję. Może to być na przykład piątek trzeciego tygodnia grudnia.

    Jeśli użytkownik nie podejmie decyzji w wyznaczonym czasie, staje się ona zaległa. Decyzję zaległą można eskalować na podstawie opcji wybranych na stronie w obszarze **Eskalacja**.

## <a name="specify-what-happens-when-a-decision-is-overdue"></a>Określanie, co się dzieje z decyzją zaległą

Jeśli użytkownik nie podejmie decyzji w wyznaczonym czasie, staje się ona zaległa. Decyzja zaległa może być eskalowana lub automatycznie przypisywana do innego użytkownika. Wykonaj następujące kroki, aby eskalować zaległą decyzję.

1. W lewym okienku kliknij opcję **Eskalacja**.
2. Zaznacz pole wyboru **Użyj ścieżki eskalacji**, aby utworzyć ścieżkę eskalacji. System automatycznie przypisze decyzję do użytkowników wymienionych w ścieżce eskalacji. Na przykład poniższa tabela przedstawia ścieżkę eskalacji.

    | Kolejność | Ścieżka eskalacji            |
    |----------|----------------------------|
    | 1        | Przypisać do: Danuta           |
    | 2        | Przypisać do: Ireny            |
    | 3        | Działanie końcowe: \[Wybór 1\] |

    W tym przykładzie system przypisuje zaległą decyzję do Danuty. Jeśli Danuta nie podejmie decyzji w przydzielonym czasie, system przypisze decyzję do Ireny. Jeśli Irena nie podejmie decyzji w przydzielonym czasie, system wybierze opcję **\[Wybór 1\]** jako decyzję.

3. Aby dodać użytkownika do ścieżki eskalacji, kliknij opcję **Dodaj eskalację**. Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 4.

    <table>
    <thead>
    <tr>
    <th>Opcja</th>
    <th>Użytkownicy, do których decyzja jest eskalowana</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hierarchia</td>
    <td>Użytkownicy w określonej hierarchii organizacyjnej</td>
    <td>
    <ol>
    <li>Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać eskalowana decyzja.</li>
    <li>System musi pobrać zakres nazwisk użytkowników z hierarchii. Te nazwy reprezentują użytkowników, do których można eskalować decyzję. Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system: <ol>
    <li>Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</li>
    <li>Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>. Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</li>
    </ol>
    </li>
    <li>Na karcie <strong>Opcje hierarchii</strong> określ, do których użytkowników w zakresie należy eskalować decyzję: <ul>
    <li><strong>Przypisz do wszystkich pobranych użytkowników</strong> — decyzja zostanie eskalowana do wszystkich użytkowników w zakresie.</li>
    <li><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — decyzja zostanie eskalowana tylko do ostatniego użytkownika w zakresie.</li>
    <li><strong>Nie uwzględniaj użytkowników spełniających następujący warunek:</strong> — decyzja nie będzie eskalowana do żadnych użytkowników w zakresie, którzy spełniają określony warunek. Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Użytkownik przepływu pracy</td>
    <td>Użytkownicy w bieżącym przepływie pracy</td>
    <td>
    <ul>
    <li>Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Użytkownik</td>
    <td>Określeni użytkownicy</td>
    <td>
    <ol>
    <li>Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</li>
    <li>Lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników. Wybierz użytkowników, do których chcesz eskalować decyzję, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na podjęcie decyzji. Umożliwia wybranie jednej z następujących opcji:

    - **Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi podjąć decyzję. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    - **Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi podjąć decyzję. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    - **Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi podjąć decyzję.
    - **Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi podjąć decyzję. Może to być na przykład piątek trzeciego tygodnia w miesiącu.
    - **Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi podjąć decyzję. Może to być na przykład piątek trzeciego tygodnia grudnia.

5. Powtórz kroki od 3 do 4 dla każdego użytkownika, który powinien zostać dodany do ścieżki eskalacji. Można zmienić kolejność użytkowników.
6. Jeśli użytkownicy wymienieni w ścieżce eskalacji nie podejmą decyzji w wyznaczonym czasie, system sam podejmie decyzję. Aby określić opcję wybieraną przez system, wybierz wiersz **Akcja**, a następnie na karcie **Zakończ działanie** wybierz opcję.

## <a name="set-a-time-limit"></a>Ustawianie limitu czasu

Jeśli decyzja musi zostać podjęta w określonym czasie, wykonaj następujące kroki.

> [!NOTE]
> Opcje wybranej w tej procedurze zastępują opcje wybrane na stronie w obszarach **Przypisanie** i **Eskalacja**.

1. W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.
2. Zaznacz pole wyboru **Ustaw limit czasu dla elementu przepływu pracy**.
3. W polu **Czas trwania** określ, do kiedy decyzja musi zostać podjęta. Umożliwia wybranie jednej z następujących opcji:

    - **Godziny** — Wprowadź liczbę godzin. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    - **Dni** — Wprowadź liczbę dni. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    - **Tygodnie** — Wprowadź liczbę tygodni.
    - **Miesiące** — Wybierz dzień i tydzień, do kiedy należy podjąć decyzję. Może to być na przykład piątek trzeciego tygodnia w miesiącu.
    - **Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy należy podjąć decyzję. Może to być na przykład piątek trzeciego tygodnia grudnia.

4. W przypadku przekroczenia tego limitu czasu system sam podejmie decyzję. Na liście **Akcja** zaznacz opcję, którą system powinien wybrać.
