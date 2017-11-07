---
title: "Konfigurowanie etapu zatwierdzania w przepływie pracy"
description: "W tym temacie wyjaśniono sposób konfigurowania właściwości kroku zatwierdzania."
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b403a6f01a6c7ba95c2dd1cfd3bae8e58f0c6879
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="configure-an-approval-step-in-a-workflow"></a>Konfigurowanie etapu zatwierdzania w przepływie pracy

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono sposób konfigurowania właściwości kroku zatwierdzania.

Aby skonfigurować krok zatwierdzania, w edytorze przepływu pracy kliknij krok zatwierdzania prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**. Następnie za pomocą procedur zamieszczonych niżej skonfiguruj właściwości kroku zatwierdzania.

## <a name="name-the-step"></a>Nadawanie nazwy krokowi
Wykonaj następujące kroki, aby wprowadzić nazwę kroku zatwierdzania.

1.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2.  W polu **Nazwa** wprowadź unikatową nazwę kroku zatwierdzania.

## <a name="enter-a-subject-line-and-instructions"></a>Wprowadzanie wiersza tematu i instrukcji
Należy wprowadzić wiersz tematu i instrukcje dla użytkowników przypisanych do kroku zatwierdzania. Na przykład jeśli konfigurujesz krok zatwierdzania dla zapotrzebowań na zakup, użytkownik przypisany do kroku zobaczy wiersz tematu i instrukcje na stronie **Zapotrzebowania na zakup**. Wiersz tematu pojawia się na pasku komunikatów na stronie. Może wtedy kliknąć ikonę na pasku komunikatów i obejrzeć instrukcje. Aby wprowadzić wiersz tematu i instrukcje, należy wykonać poniższe kroki.

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

## <a name="assign-the-approval-step"></a>Przypisywanie kroku zatwierdzania
Wykonaj poniższe kroki, aby określić, komu ma zostać przypisany ten krok zatwierdzania.

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
    <th>Użytkownicy, którym jest przypisany krok zatwierdzania</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Uczestnik</td>
    <td>Użytkownicy, którzy są przypisani do określonej grupy lub roli</td>
    <td><ol>
    <li>Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której ma zostać przypisany krok.</li>
    <li>Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której ma zostać przypisany krok.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Hierarchia</td>
    <td>Użytkownicy w określonej hierarchii organizacyjnej</td>
    <td><ol>
    <li>Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać przypisany krok.</li>
    <li>System musi pobrać zakres nazwisk użytkowników z hierarchii. Te nazwy reprezentują użytkowników, którym można przypisać krok. Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system: <ol>
    <li>Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</li>
    <li>Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>. Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</li>
    </ol></li>
    <li>Na karcie <strong>Opcje hierarchii</strong> określ, którym użytkownikom w zakresie należy przypisać krok: <ul>
    <li><strong>Przypisz do wszystkich pobranych użytkowników</strong> — krok zostanie przypisany do wszystkich użytkowników w zakresie.</li>
    <li><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — krok zostanie przypisany tylko do ostatniego użytkownika w zakresie.</li>
    <li><strong>Nie uwzględniaj użytkowników spełniających następujący warunek</strong> — krok nie zostanie przypisany żadnym użytkownikom w zakresie, którzy spełniają określony warunek. Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</li>
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
    <li>Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations. Wybierz użytkowników, którym chcesz przypisać krok, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

3.  Na karcie **Limit czasu** w polu **Czas trwania** określ, ile czasu ma użytkownik, aby podjąć akcję lub zareagować na dokumenty, które dotrą do etapu zatwierdzania. Umożliwia wybranie jednej z następujących opcji:
    -   **Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi zareagować. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi zareagować. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi zareagować.
    -   **Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi zareagować. Na przykład można określić, że użytkownik ma odpowiedzieć do piątku w trzecim tygodniu miesiąca.
    -   **Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi zareagować. Na przykład można określić, że użytkownik ma odpowiedzieć do piątku w trzecim tygodniu grudnia.

    Jeśli użytkownik nie podejmie działania wobec dokumentu w wyznaczonym czasie, dokument staje się zaległy. Dokument zaległy można eskalować na podstawie opcji wybranych na stronie w obszarze **Eskalacja**.
4.  Jeśli krok zatwierdzania został przypisany do wielu użytkowników lub do grupy użytkowników, na karcie **Zasady ukończenia** wybierz jedną z następujących opcji:
    -   **Pojedyncza osoba zatwierdzająca** — Akcja stosowana do dokumentu jest określona przez pierwszą osobę, która odpowiada. Na przykład Tomasz przesłał raport z wydatków na 15 000 zł. Raport z wydatków jest obecnie przypisany do Magdy, Ewy i Bartka. Jeśli pierwszą osobą, która odpowie na dokument, jest Magda, wybrana przez nią akcja zostanie zastosowana do dokumentu. Jeśli Magda odrzuci dokument, zostanie on odrzucony i wysłany z powrotem do Tomasza. Po zatwierdzeniu przez Magdę dokument zostanie przesłany do Anny w celu zatwierdzenia. 
    
    ![Przepływ pracy z procesem zatwierdzania](./media/workflow_multipleusersinstep.gif)
    
    -   **Większość osób zatwierdzających** — Akcja stosowana do dokumentu jest określana po uzyskaniu odpowiedzi od większości osób zatwierdzających. Na przykład Tomasz przesłał raport z wydatków na 15 000 zł. Raport z wydatków jest obecnie przypisany do Magdy, Ewy i Bartka. Jeżeli dwoma pierwszym osobami zatwierdzającymi, które zareagowały, są Magda i Ewa, ich operacje są stosowane do dokumentu.
        -   Jeśli Magda zatwierdzi dokument, ale Ewa go odrzuci, dokument zostanie odrzucony i wysłany z powrotem do Tomasza.
        -   Jeśli Magda i Ewa zatwierdzą dokument, zostanie on wysłany do Anny do zatwierdzenia.
    -   **Odsetek obiektów zatwierdzających** — Akcja dotycząca dokumentu zostanie określona po uzyskaniu odpowiedzi określonego procentu osób zatwierdzających. Na przykład Tomasz przesłał raport z wydatków na 15 000 zł. Raport z wydatków jest obecnie przypisany do Magdy, Ewy i Bartka, a jako wartość procentową wprowadzono **50**. Jeśli Magda i Ewa są dwiema pierwszymi osobami zatwierdzającymi, które odpowiedziały, ich czynności są stosowane do dokumentu, ponieważ obie razem spełniają wymóg 50 procent osób zatwierdzających.
        -   Jeśli Magda zatwierdzi dokument, ale Ewa go odrzuci, dokument zostanie odrzucony i wysłany z powrotem do Tomasza.
        -   Jeśli Magda i Ewa zatwierdzą dokument, zostanie on wysłany do Anny do zatwierdzenia.
    -   **Wszystkie osoby zatwierdzające** — Wszystkie osoby zatwierdzające muszą zatwierdzić dokument. W przeciwnym razie nie można kontynuować przepływu pracy. Na przykład Tomasz przesłał raport z wydatków na 15 000 zł. Raport z wydatków jest obecnie przypisany do Magdy, Ewy i Bartka. Jeśli Magda i Ewa zatwierdzą dokument, ale Bartek go odrzuci, dokument zostanie odrzucony i wysłany z powrotem do Tomasza. Jeśli Magda, Ewa i Bartek zatwierdzą dokument, zostanie wysłany do Anny do zatwierdzenia.

## <a name="specify-when-the-approval-step-is-required"></a>Określanie, kiedy krok zatwierdzania jest wymagany
Można określić, kiedy krok zatwierdzania jest wymagany. Krok zatwierdzenia może być wymagany zawsze lub tylko wtedy, gdy są spełnione określone warunki.

### <a name="the-approval-step-is-always-required"></a>Krok zatwierdzania jest zawsze wymagany

Jeśli krok zatwierdzania jest zawsze wymagany, wykonaj następujące czynności.

1.  W lewym okienku kliknij opcję **Warunek**.
2.  Wybierz opcję **Zawsze wykonuj ten krok**.

### <a name="the-approval-step-is-required-in-specific-conditions"></a>Krok zatwierdzania jest wymagany w określonych warunkach

Konfigurowany krok zatwierdzania może być wymagany tylko w określonych warunkach. Na przykład jeśli konfigurujesz krok zatwierdzania przepływu pracy zapotrzebowania na zakup, można określić, aby krok następował tylko wtedy, gdy kwota zapotrzebowania na zakup jest większa niż 10 000 zł. Wykonaj następujące czynności, aby określić, kiedy krok zatwierdzania jest wymagany.

1.  W lewym okienku kliknij opcję **Warunek**.
2.  Wybierz opcję **Wykonaj ten krok, tylko jeśli zostanie spełniony następujący warunek**.
3.  Służy do wprowadzania warunku.
4.  Wprowadź wszelkie wymagane dodatkowe warunki.
5.  Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:
    1.  Kliknij przycisk **Test**.
    2.  Na stronie **Warunek testowy przepływu pracy** w obszarze **Sprawdź poprawność warunku** wybierz rekord.
    3.  Kliknij przycisk **Test**. System oszacuje rekord i określi, czy rekord spełnia określone warunki.
    4.  Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do strony **Właściwości**.

## <a name="specify-what-happens-when-the-document-is-overdue"></a>Określanie, co się dzieje z dokumentem zaległym
Jeśli użytkownik nie podejmie działania wobec dokumentu w wyznaczonym czasie, dokument staje się zaległy. Dokument zaległy może być eskalowany lub automatycznie przypisywany do innego użytkownika w celu zatwierdzenia. Wykonaj następujące kroki, aby eskalować zaległy dokument.

1.  W lewym okienku kliknij opcję **Eskalacja**.
2.  Zaznacz pole wyboru **Użyj ścieżki eskalacji**, aby utworzyć ścieżkę eskalacji. System automatycznie przypisze dokument do użytkowników wymienionych w ścieżce eskalacji. Na przykład poniższa tabela przedstawia ścieżkę eskalacji.

    | Kolejność | Ścieżka eskalacji      |
    |----------|----------------------|
    | 1 przypada na wpłatę z zysku na rzecz budżetu państwa        | Przypisać do: Danuta     |
    | 2        | Przypisać do: Ireny      |
    | 3        | Działanie końcowe: Odrzucenie |

    W tym przykładzie system przypisuje zaległy dokument do Danuty. Jeśli Danuta nie odpowie w przydzielonym czasie, system przypisze dokument do Ireny. Jeśli Irena nie odpowie w przydzielonym czasie, system odrzuci dokument.
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
    <th>Użytkownicy, do których dokument jest eskalowany</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Hierarchia</td>
    <td>Użytkownicy w określonej hierarchii organizacyjnej</td>
    <td><ol>
    <li>Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać eskalowany dokument.</li>
    <li>System musi pobrać zakres nazwisk użytkowników z hierarchii. Te nazwy reprezentują użytkowników, do których można eskalować dokument. Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system: <ol>
    <li>Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</li>
    <li>Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>. Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</li>
    </ol></li>
    <li>Na karcie <strong>Opcje hierarchii</strong> określ, do których użytkowników w zakresie należy eskalować dokument: <ul>
    <li><strong>Przypisz do wszystkich pobranych użytkowników</strong> — dokument zostanie eskalowany do wszystkich użytkowników w zakresie.</li>
    <li><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — dokument zostanie eskalowany tylko do ostatniego użytkownika w zakresie.</li>
    <li><strong>Nie uwzględniaj użytkowników spełniających następujący warunek</strong> — dokument nie będzie eskalowany do żadnych użytkowników w zakresie, którzy spełniają określony warunek. Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</li>
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
    <li>Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations. Wybierz użytkowników, do których chcesz eskalować dokument, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  Na karcie **Limit czasu** w polu **Czas trwania** określ, ile czasu ma użytkownik, aby podjąć akcję lub zareagować na dokumenty. Umożliwia wybranie jednej z następujących opcji:
    -   **Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi zareagować. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi zareagować. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    -   **Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi zareagować.
    -   **Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi zareagować. Na przykład można określić, że użytkownik ma odpowiedzieć do piątku w trzecim tygodniu miesiąca.
    -   **Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi zareagować. Na przykład można określić, że użytkownik ma odpowiedzieć do piątku w trzecim tygodniu grudnia.

5.  Powtórz kroki od 3 do 4 dla każdego użytkownika, który powinien zostać dodany do ścieżki eskalacji. Można zmienić kolejność użytkowników.
6.  Jeśli użytkownicy wymienieni w ścieżce eskalacji nie odpowiedzą w wyznaczonym czasie, system automatycznie wykona operację na dokumencie. Aby określić akcję podejmowaną przez system, wybierz wiersz **Akcja**, a następnie na karcie **Zakończ działanie** wybierz akcję.





