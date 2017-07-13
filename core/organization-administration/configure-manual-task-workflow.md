---
title: "Konfigurowanie zadania ręcznego w przepływie pracy"
description: "W tym temacie wyjaśniono sposób konfigurowania właściwości zadania ręcznego."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 242abaae1aa17578ba8eab4b2664794ff2c2caec
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Konfigurowanie zadania ręcznego w przepływie pracy
<a id="configure-a-manual-task-in-a-workflow" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono sposób konfigurowania właściwości zadania ręcznego.

Aby skonfigurować zadanie ręczne, w edytorze przepływu pracy kliknij zadanie prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**. Następnie za pomocą procedur zamieszczonych niżej skonfiguruj właściwości zadania ręcznego.

## Nadawanie nazwy zadaniu
<a id="name-the-task" class="xliff"></a>
Wykonaj następujące kroki, aby wprowadzić nazwę zadania ręcznego.

1.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2.  W polu **Nazwa** wprowadź unikatową nazwę zadania.

## Wprowadzanie wiersza tematu i instrukcji
<a id="enter-a-subject-line-and-instructions" class="xliff"></a>
Należy wprowadzić wiersz tematu i instrukcje dla użytkowników przypisanych do zadania. Na przykład jeśli konfigurujesz zadanie dla zapotrzebowań na zakup, użytkownik przypisany do zadania zobaczy wiersz tematu i instrukcje na stronie **Zapotrzebowania na zakup**. Wiersz tematu pojawia się na pasku komunikatów na stronie. Może wtedy kliknąć ikonę na pasku komunikatów i przeczytać instrukcje. Aby wprowadzić wiersz tematu i instrukcje, należy wykonać poniższe kroki.

1.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2.  W polu **Temat elementu pracy** wprowadź wiersz tematu.
3.  Aby spersonalizować wiersz tematu, można wstawić symbole zastępcze. Podczas wyświetlania wiersza tematu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi. Wykonaj następujące czynności, aby wstawić symbol zastępczy:
    1.  W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.
    2.  Kliknij opcję **Wstaw symbol zastępczy**.
    3.  Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4.  Kliknij przycisk **Wstaw**.

4.  Aby dodać tłumaczenia wiersza tematu, wykonaj następujące kroki:
    1.  Kliknij opcję **Tłumaczenia**.
    2.  Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3.  Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.
    4.  W polu **Przetłumaczony tekst** wprowadź tekst.
    5.  Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 3.
    6.  Kliknij przycisk **Zamknij**.

5.  W polu **Instrukcje dotyczące elementu produkcyjnego** wprowadź instrukcje.
6.  Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze. Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi. Wykonaj następujące czynności, aby wstawić symbol zastępczy:
    1.  W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.
    2.  Kliknij opcję **Wstaw symbol zastępczy**.
    3.  Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4.  Kliknij przycisk **Wstaw**.

7.  Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:
    1.  Kliknij opcję **Tłumaczenia**.
    2.  Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3.  Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.
    4.  W polu **Przetłumaczony tekst** wprowadź tekst.
    5.  Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 6.
    6.  Kliknij przycisk **Zamknij**.

## Przypisywanie zadania
<a id="assign-the-task" class="xliff"></a>
Wykonaj poniższe kroki, aby określić, komu ma zostać przypisane to zadanie ręczne.

1.  W lewym okienku kliknij opcję **Przypisanie**.
2.  Na karcie **Typ przypisania** wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 3.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opcja</th>
    <th>Użytkownicy, którym jest przypisane zadanie</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Uczestnik</td>
    <td>Użytkownicy, którzy są przypisani do określonej grupy lub roli</td>
    <td><ol>
    <li>Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której ma zostać przypisane zadanie.</li>
    <li>Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której ma zostać przypisane zadanie.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Hierarchia</td>
    <td>Użytkownicy w określonej hierarchii organizacyjnej</td>
    <td><ol>
    <li>Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać przypisane zadanie.</li>
    <li>System musi pobrać zakres nazwisk użytkowników z hierarchii. Te nazwy reprezentują użytkowników, którym można przypisać zadanie. Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system: <ol>
    <li>Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</li>
    <li>Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>. Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</li>
    </ol></li>
    <li>Na karcie <strong>Opcje hierarchii</strong> określ, którym użytkownikom w zakresie należy przypisać zadanie: <ul>
    <li><strong>Przypisz do wszystkich pobranych użytkowników</strong> — zadanie zostanie przypisane do wszystkich użytkowników w zakresie.</li>
    <li><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — zadanie zostanie przypisane tylko do ostatniego użytkownika w zakresie.</li>
    <li><strong>Nie uwzględniaj użytkowników spełniających następujący warunek</strong> — zadanie nie zostanie przypisane użytkownikom w zakresie, którzy spełniają określony warunek. Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Użytkownik przepływu pracy</td>
    <td>Użytkownicy w bieżącym przepływie pracy</td>
    <td><ul>
    <li>Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</li>
    </ul></td>
    </tr>
    <tr class="even">
    <td>Użytkownik</td>
    <td>Konkretny użytkownik programu Microsoft Dynamics 365 for Finance and Operations</td>
    <td><ol>
    <li>Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</li>
    <li>Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations. Wybierz użytkowników, którym chcesz przypisać zadanie, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Kolejka</td>
    <td>Kolejka elementów roboczych</td>
    <td><ol>
    <li>Po wybraniu wartości w polu <strong>Kolejka</strong> kliknij kartę <strong>Na podstawie kolejki</strong>.</li>
    <li>Aby przypisać zadanie do określonej kolejki, wykonaj następujące czynności: <ol>
    <li>Na liście <strong>Typ kolejki</strong> zaznacz pozycję <strong>Kolejki elementów roboczych</strong>.</li>
    <li>Na liście <strong>Nazwa kolejki</strong> zaznacz kolejkę.</li>
    </ol></li>
    <li>Jeśli określony warunek ma decydować o kolejce, do której zostanie przypisane zadanie, wykonaj następujące czynności: <ol>
    <li>Na liście <strong>Typ kolejki</strong> zaznacz pozycję <strong>Warunkowe kolejki elementów roboczych</strong>.</li>
    <li>Na liście <strong>Nazwa kolejki</strong> zaznacz pozycję <strong>Kolejka warunkowa</strong>.</li>
    </ol></li>
    </ol>
    <strong>Uwaga:</strong> Ta opcja jest używana tylko do niektórych przepływów pracy, takich jak Zarządzanie sprawami.</td>
    </tr>
    </tbody>
    </table>

3.  Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na wykonanie zadania. Umożliwia wybranie jednej z następujących opcji:
    -   **Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi wykonać zadanie. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi wykonać zadanie. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi wykonać zadanie.
    -   **Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi wykonać zadanie. Może to być na przykład piątek trzeciego tygodnia w miesiącu.
    -   **Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi wykonać zadanie. Może to być na przykład piątek trzeciego tygodnia grudnia.

    Jeśli użytkownik nie wykona zadania w wyznaczonym czasie, staje się ono zaległe. Zadanie zaległe można eskalować na podstawie opcji wybranych na stronie w obszarze **Eskalacja**.

## Określanie, co się dzieje z zadaniem zaległym
<a id="specify-what-happens-when-the-task-is-overdue" class="xliff"></a>
Jeśli użytkownik nie wykona zadania ręcznego w wyznaczonym czasie, staje się ono zaległe. Zadanie zaległe może być eskalowane lub automatycznie przypisywane do innego użytkownika. Wykonaj następujące kroki, eskalować zaległe zadanie.

1.  W lewym okienku kliknij opcję **Eskalacja**.
2.  Zaznacz pole wyboru **Użyj ścieżki eskalacji**, aby utworzyć ścieżkę eskalacji. System automatycznie przypisze zadanie do użytkowników wymienionych w ścieżce eskalacji. Na przykład poniższa tabela przedstawia ścieżkę eskalacji.
    | Kolejność | Ścieżka eskalacji      |
    |----------|----------------------|
    | 1 przypada na wpłatę z zysku na rzecz budżetu państwa        | Przypisać do: Danuta     |
    | 2        | Przypisać do: Ireny      |
    | 3        | Działanie końcowe: Odrzucenie |

    W tym przykładzie system przypisuje zaległe zadanie do Danuty. Jeśli Danuta nie wykona zadania w przydzielonym czasie, system przypisze zadanie do Ireny. Jeśli Irena nie wykona zadania w przydzielonym jej czasie, system odrzuci dokument przesłany do przetworzenia.
3.  Aby dodać użytkownika do ścieżki eskalacji, kliknij opcję **Dodaj eskalację**. Na karcie **Typ przypisania** wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 4.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opcja</th>
    <th>Użytkownicy, do których zadanie jest eskalowane</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Hierarchia</td>
    <td>Użytkownicy w określonej hierarchii organizacyjnej</td>
    <td><ol>
    <li>Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać eskalowane zadanie.</li>
    <li>System musi pobrać zakres nazwisk użytkowników z hierarchii. Te nazwy reprezentują użytkowników, do których można eskalować zadanie. Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system: <ol>
    <li>Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</li>
    <li>Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>. Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</li>
    </ol></li>
    <li>Na karcie <strong>Opcje hierarchii</strong> określ, do których użytkowników w zakresie należy eskalować zadanie: <ul>
    <li><strong>Przypisz do wszystkich pobranych użytkowników</strong> — zadanie zostanie eskalowane do wszystkich użytkowników w zakresie.</li>
    <li><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — zadanie zostanie eskalowane tylko do ostatniego użytkownika w zakresie.</li>
    <li><strong>Nie uwzględniaj użytkowników spełniających następujący warunek</strong> — to zadanie nie będzie eskalowane do użytkowników w zakresie, którzy spełniają określony warunek. Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Użytkownik przepływu pracy</td>
    <td>Użytkownicy w bieżącym przepływie pracy</td>
    <td><ul>
    <li>Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Użytkownik</td>
    <td>Konkretny użytkownik programu Finance and Operations</td>
    <td><ol>
    <li>Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</li>
    <li>Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations. Wybierz użytkowników, do których chcesz eskalować zadanie, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na wykonanie zadania. Umożliwia wybranie jednej z następujących opcji:
    -   **Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi wykonać zadanie. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi wykonać zadanie. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi wykonać zadanie.
    -   **Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi wykonać zadanie. Może to być na przykład piątek trzeciego tygodnia w miesiącu.
    -   **Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi wykonać zadanie. Może to być na przykład piątek trzeciego tygodnia grudnia.

5.  Powtórz kroki od 3 do 4 dla każdego użytkownika, który powinien zostać dodany do ścieżki eskalacji. Można zmienić kolejność użytkowników.
6.  Jeśli użytkownicy wymienieni w ścieżce eskalacji nie wykonają zadania w wyznaczonym czasie, system wykona na nim operację. Aby określić akcję podejmowaną przez system, wybierz wiersz **Akcja**, a następnie na karcie **Zakończ działanie** wybierz akcję.

## Określanie, kiedy system automatycznie wykonuje operację na zadaniu
<a id="specify-when-the-system-automatically-acts-on-the-task" class="xliff"></a>
Można skonfigurować system, aby podejmował akcję wobec zadania ręcznego, jeśli są spełnione określone warunki. Na przykład zadanie wymaga, aby członek działu raportów z wydatków przeglądał paragony dostarczane razem z raportem z wydatków. Zgodnie z zasadami firmy to zadanie trzeba wykonać, jeśli łączna kwota raportu z wydatków jest większa niż 100 USD. W tym scenariuszu można tak skonfigurować system, aby automatycznie oznaczał zadanie jako **Ukończone**, gdy łączna kwota jest mniejsza niż 100. Wykonaj następujące kroki, aby określić, kiedy system podejmuje akcję wobec zadania ręcznego.

1.  W lewym okienku kliknij opcję **Akcje automatyczne**.
2.  Zaznacz pole wyboru **Włącz akcje automatyczne**.
3.  Kliknij opcję **Dodaj warunek**.
4.  Służy do wprowadzania warunku.
5.  Wprowadź wszelkie wymagane dodatkowe warunki.
6.  Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:
    1.  Kliknij przycisk **Test**.
    2.  Na stronie **Warunek testowy przepływu pracy** w obszarze **Sprawdź poprawność warunku** wybierz rekord.
    3.  Kliknij przycisk **Test**. System oszacuje rekord i określi, czy rekord spełnia określone warunki.
    4.  Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do strony **Właściwości**.

7.  Z listy **Akcja automatycznego ukończenia** wybierz akcję, jaką ma podjąć system wobec zadania.

## Określanie, kiedy są wysyłane powiadomienia
<a id="specify-when-notifications-are-sent" class="xliff"></a>
Możliwe jest wysyłanie do odpowiednich osób powiadomień w przypadku delegowania, eskalowania, ukończenia lub odrzucenia zadania ręcznego albo żądania jego modyfikacji. Wykonaj następujące kroki, aby określić, kiedy i do kogo są wysyłane powiadomienia.

1.  W lewym okienku kliknij opcję **Powiadomienia**.
2.  Zaznacz pola wyboru obok zdarzeń, o których mają być wysyłane powiadomienia:
    -   **Deleguj** — zadanie zostało przypisane innemu użytkownikowi.
    -   **Eskaluj** — przypisany użytkownik nie wykonał zadania w wyznaczonym czasie.
    -   **Ukończono** — przypisany użytkownik wykonał zadanie.
    -   **Odrzuć** — przypisany użytkownik odrzucił dokument, który został mu przesłany.
    -   **Żądanie zmiany** — przypisany użytkownik zażądał zmiany w przesłanym mu dokumencie.

3.  Zaznacz wiersz zdarzenia wybranego w kroku 2.
4.  Na karcie **Tekst powiadomienia** w polu tekstowym wprowadź tekst powiadomienia.
5.  Aby spersonalizować powiadomienie, możesz wstawić symbole zastępcze. Podczas wyświetlania powiadomień użytkownikom symbole zastępcze są zastępowane odpowiednimi informacjami. Wykonaj następujące czynności, aby wstawić symbol zastępczy:
    1.  W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.
    2.  Kliknij opcję **Wstaw symbol zastępczy**.
    3.  Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4.  Kliknij przycisk **Wstaw**.

6.  Aby dodać tłumaczenia powiadomienia, wykonaj następujące kroki:
    1.  Kliknij opcję **Tłumaczenia**.
    2.  Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3.  Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.
    4.  W polu **Przetłumaczony tekst** wprowadź tekst.
    5.  Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 5.
    6.  Kliknij przycisk **Zamknij**.

7.  Na karcie **Odbiorcy** określ, komu będą wysyłane powiadomienia. Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 8.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opcja</th>
    <th>Adresaci powiadomień</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Uczestnik</td>
    <td>Użytkownicy, którzy są przypisani do określonej grupy lub roli</td>
    <td><ol>
    <li>Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</li>
    <li>Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Użytkownik przepływu pracy</td>
    <td>Użytkownicy w bieżącym przepływie pracy</td>
    <td><ul>
    <li>Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Użytkownik</td>
    <td>Konkretny użytkownik programu Finance and Operations</td>
    <td><ol>
    <li>Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</li>
    <li>Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations. Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.

## Ustawianie limitu czasu
<a id="set-a-time-limit" class="xliff"></a>
Jeśli zadanie ręczne musi zostać ukończone w określonym czasie, wykonaj następujące kroki. **Uwaga:** Opcje wybranej w tej procedurze zastępują opcje wybrane na stronie w obszarach **Przypisanie** i **Eskalacja**.

1.  W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.
2.  Zaznacz pole wyboru **Ustaw limit czasu dla elementu przepływu pracy**.
3.  W polu **Czas trwania** określ, do kiedy zadanie ma zostać ukończone. Umożliwia wybranie jednej z następujących opcji:
    -   **Godziny** — Wprowadź liczbę godzin, w ciągu których należy wykonać zadanie. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Dni** — Wprowadź liczbę dni, w ciągu których należy wykonać zadanie. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Tygodnie** — Wprowadź liczbę tygodni, w ciągu których należy wykonać zadanie.
    -   **Miesiące** — Wybierz dzień i tydzień, do kiedy należy wykonać zadanie. Może to być na przykład piątek trzeciego tygodnia w miesiącu.
    -   **Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy należy wykonać zadanie. Może to być na przykład piątek trzeciego tygodnia grudnia.

4.  W przypadku przekroczenia tego limitu czasu system wykona operację na zadaniu. Na liście **Akcja** zaznacz akcję, jaką ma podjąć system.

## Określanie akcji dostępnych użytkownikowi
<a id="specify-which-actions-are-available-to-the-user" class="xliff"></a>
Gdy zadanie ręczne zostanie przypisane użytkownikowi, musi on podjąć wobec niego działanie. Wykonaj następujące kroki, aby określić, które akcje użytkownik może wykonywać na zadaniu. **Uwaga:** Dostępne akcje będą się różnić w zależności od projektu zadania.

1.  W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.
2.  Zaznacz pole wyboru **Ukończono**, jeśli użytkownik ma mieć możliwość oznaczenia zadania statusem **Ukończono**.
3.  Zaznacz pole wyboru **Odrzuć**, jeśli użytkownik ma mieć możliwość odrzucenia przesłanego mu dokumentu.
4.  Zaznacz pole wyboru **Żądanie zmiany**, jeśli użytkownik ma mieć możliwość zażądania zmian w przesłanym dokumencie.
5.  Zaznacz pole wyboru **Deleguj**, jeśli użytkownik ma mieć możliwość przypisania zadania do innego użytkownika.
6.  Zaznacz pole wyboru **Przypisz ponownie**, jeśli użytkownik ma mieć możliwość przypisania zadania innemu użytkownikowi w kolejce elementów roboczych.
7.  Zaznacz pole wyboru **Zwolnienie**, jeśli użytkownik ma mieć możliwość przypisania zadania do kolejki elementów roboczych. Następnie inny użytkownik może wykonać to zadanie.





