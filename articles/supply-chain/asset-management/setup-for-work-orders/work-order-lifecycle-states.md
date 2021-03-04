---
title: Stany cyklu życia zlecenia pracy
description: W tym temacie opisano cykle stanu zlecenia pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderLifecycleState, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b6e96f2f6b324ffe44e8684d9bd2a42fb52d0aed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435278"
---
# <a name="work-order-lifecycle-states"></a>Stany cyklu życia zlecenia pracy


[!include [banner](../../includes/banner.md)]

 

Stany cyklu życia zlecenia pracy określają Stany, przez które może przechodzić zlecenie pracy. Przykłady to **utworzone**, **zaplanowane**, **w toku** i **zakończone**. Stany cyklu życia zlecenia pracy można aktualizować ręcznie w zleceniu pracy albo automatycznie je aktualizować (na przykład podczas planowania zlecenia pracy).

Stany cyklu realizacji zlecenia pracy wymagane dla zleceń pracy muszą być dołączone do zgodnych etapów projektu na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie** (**Zarządzanie projektami i ich księgowanie** \> **Parametry modułu Zarządzanie projektami i ich księgowanie**). Najpierw skonfigurowano etapy projektu w module Zarządzanie projektami i ich księgowanie. Następnie należy skonfigurować Stany cyklu życia zlecenia pracy oraz modele cyklu życia zlecenia pracy w module Zarządzanie składnikami majątku.

Poniższa tabela opisuje opcje w sekcjach **Zlecenie pracy** i **Harmonogram** na karcie skróconej **Ogólne** na stronie **Stan cyklu życia zlecenia pracy** (**Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Stany cyklu życia**).

![Strona stanów cyklu życia zlecenia pracy](media/09-setup-for-work-orders.png)

| Nazwa opcji                   | Opis |
|-------------------------------|-------------|
| Aktywna                        | Ustawienie tej opcji na **Tak** powoduje, że zlecenie pracy powinno być aktywne, gdy jest ono w stanie cyklu życia. |
| Dodaj wiersz                      | Tę opcję należy ustawiać **Tak**, jeśli zadanie zlecenia pracy można dodać do zlecenia pracy w tym stanie cyklu życia. |
| Usuwanie                        | Ustawienie tej opcji na **Tak** jeśli zlecenie pracy może być usunięte, gdy jest ono w stanie cyklu życia. |
| Usuń wiersz                   | Tę opcję należy ustawiać **Tak**, jeśli zadanie zlecenia pracy można usunąć ze zlecenia pracy w tym stanie cyklu życia. |
| Zezwalaj na planowanie              | Ustawienie tej opcji na **Tak** jeśli zlecenie pracy może być zaplanowane, gdy jest ono w stanie cyklu życia. |
| Ustaw rzeczywisty początek              | Tę opcję należy skonfigurować **tak**, aby użytkownik był proszony o wybranie rzeczywistej daty i godziny rozpoczęcia zlecenia pracy, które jest aktualizowane w tym stanie cyklu życia. |
| Ustaw rzeczywisty koniec                | Tę opcję należy skonfigurować **tak**, aby użytkownik był proszony o wybranie rzeczywistej daty i godziny zakończenia zlecenia pracy, które jest aktualizowane w tym stanie cyklu życia. |
| Zaksięguj arkusze                 | Tę opcję należy ustawiać **Tak**, jeśli arkusz zlecenia pracy można automatycznie zaksięgować kiedy zlecenie pracy jest aktualizowane w tym stanie cyklu życia. Jeśli wystąpi błąd podczas księgowania w arkuszu, wyświetlany jest komunikat, a Aktualizacja stanu cyklu życia zlecenia pracy jest anulowana. Aby wyświetlić wiersze arkusza dla zlecenia pracy, należy wybrać **Zarządzanie składnikami majątku** \> **Wspólne** \> **Zlecenia pracy** \> **Wszystkie zlecenia pracy**, **Aktywne zlecenia pracy** lub **Moje aktywne zlecenia pracy**, następnie wybierz zlecenie produkcyjne z listy, a następnie wybierz **Arkusze**. Ta konfiguracja automatycznego księgowania arkusza zleceń pracy w określonym stanie cyklu eksploatacji jest taka sama, jak po wybraniu **Księgowanie arkuszy** na stronie **Arkusze zleceń pracy**.<p>**Uwaga:** Jeśli ta opcja zostanie ustawiona na **Tak**, arkusze będą księgowane automatycznie, jeśli nie skonfigurowano przepływu pracy zatwierdzania. Jeśli firma używa konfiguracji zatwierdzania arkusza skonfigurowanej na stronie **Zatwierdzanie arkusza** (**Zarządzanie projektami i ich księgowanie** \> **Konfiguracja** \> **Arkusze** \> **Zatwierdzenie arkusza**), kierownik lub pracownik muszą sprawdzić poprawność i zaksięgować rejestracje zużycia.</p> |
| Przetwarzaj listę kontrolną konserwowanego składnika majątku | Tę opcję należy ustawiać **Tak**, jeśli wszystkie załączone listy konserwacji powinny być przetworzone kiedy zlecenie pracy jest aktualizowane w tym stanie cyklu życia. W ramach tego przetwarzania są księgowane wszystkie rejestracje liczników, które zostały utworzone na liście konserwacji, oraz są oceniane wyniki całej listy konserwacji. Zostaną ocenione wiersze listy kontrolne konserwacji, w której są wyniki **Sukces** i **Niepowodzenie**, a co najmniej jeden wiersz nie powiedzie się, cała lista kontrolna konserwacji zostanie oznaczona jako **Niepowodzenie** w zarządzaniu składnikami majątku. |
| Gotowy                         | Tę opcję należy wybrać na wartość **tak**, jeśli stan harmonogramu zadań zlecenia pracy dla wszystkich zadań zlecenia pracy utworzonych w zleceniu pracy powinien być automatycznie aktualizowany jako **Gotowe**, gdy zlecenie pracy zostanie zaktualizowane do stanu cyklu życia. |
| Uruchom                         | Tę opcję należy wybrać na wartość **tak**, jeśli stan harmonogramu zadań zlecenia pracy dla wszystkich zadań zlecenia pracy utworzonych w zleceniu pracy powinien być automatycznie aktualizowany jako **Rozpoczęto**, gdy zlecenie pracy zostanie zaktualizowane do stanu cyklu życia. |
| Zamknięcie zlecenia produkcyjnego                           | Tę opcję należy wybrać na wartość **tak**, jeśli stan harmonogramu zadań zlecenia pracy dla wszystkich zadań zlecenia pracy utworzonych w zleceniu pracy powinien być automatycznie aktualizowany jako **Zakończone**, gdy zlecenie pracy zostanie zaktualizowane do stanu cyklu życia. |
| Usuń wiersze harmonogramu         | W tej opcji należy wybrać wartość **Tak**, jeśli harmonogram wszystkich zadań zlecenia pracy utworzonych w zleceniu pracy, które już zostało zaplanowane powinien zostać usunięty, gdy zlecenie pracy zostanie zaktualizowane do stanu cyklu życia. Innymi słowy, rezerwacje zdolności produkcyjnych składnika majątku, powiązanego konserwatora i powiązanych z nim narzędzi zostaną usunięte. Na przykład ustawienie tej opcji na wartość **tak** na stanie cyklu życia zlecenia pracy, które jest nazwane jako **Oszacowany**. Następnie, gdy zlecenie pracy zostanie wycofane do tego stanu cyklu życia, ponieważ jest wymagane ponowne planowanie, można je usunąć w tym zleceniu pracy. |

## <a name="set-up-project-stages-and-work-order-lifecycle-states"></a>Konfigurowanie etapów projektu i stanów cyklu życia zlecenia pracy.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Parametry modułu Zarządzanie projektami i ich księgowanie**.
2. Na karcie **etap projektu** dla każdego etapu, którego chcesz użyć, zaznacz pole wyboru dla każdego typu projektu, który jest wymagany dla danego zlecenia pracy. Typy projektów definiują reguły dotyczące dozwolonych zadań finansowych. Przykładowe zadania finansowe to tworzenie prognozy, tworzenie oszacowań i tworzenie sald początkowych.

    > [!IMPORTANT]
    > Jeśli etap projektu nie jest wybrany dla typu projektu, ale etap projektu jest używany dla stanu cyklu życia zlecenia, projekty zlecenia nie będą aktualizowane w odpowiedni sposób.

3. Zamknij stronę **Parametry modułu Zarządzanie projektami i ich księgowanie**.
4. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zlecenia pracy** \> **Stany cyklu życia**.
5. Wybierz pozycję **Nowy**, aby utworzyć nowy stan cyklu życia zlecenia pracy.
6. W polu **Stan cyklu życia** wprowadź identyfikator stanu cyklu życia.
7. W polu **Nazwa** wprowadź nazwę.

    Na skróconej karcie **Szczegóły** pole **Modele cyklu życia** pokazuje liczbę modeli cyklu życia zleceń pracy, które używają tego stanu cyklu życia.

8. Na skróconej karcie **Ogólne** w sekcji **Zlecenie pracy** wybierz funkcje, które powinny być dostępne dla tego stanu cyklu życia, ustawiając odpowiednie opcje na **tak**. Opis opcji znajduje się w tabeli w poprzedniej części tego tematu.
9. W sekcji **Projekt** w polu **etap** wybierz etap projektu, który powinien być związany z tym stanem cyklu życia.
10. W sekcji **projekt** określ opcję **Zamknij działania** na wartość **tak**, jeśli działania związane z każdym zadaniem zlecenia pracy powinny zostać automatycznie zamknięte, jeśli zlecenie pracy jest w tym stanie cyklu życia.

    > [!NOTE]
    > Aby znaleźć numer działania projektu, które jest powiązane z zadaniem zlecenia pracy, należy wybrać polecenie **Zarządzanie składnikami majątku** \> **Wspólne** \> **Zlecenia pracy** \> **Wszystkie zlecenia pracy**, **Aktywne zlecenia pracy** lub **Moje aktywne zlecenia pracy**. Otwórz zlecenie pracy, a następnie wybierz zadanie zlecenia pracy. Numer działania jest wyświetlany w polu **Numer działania** w sekcji **projekt** na karcie **ogólne** w formularzu skróconej karty **szczegóły wiersza**.

11. W sekcji **Prognoza** Określ opcję **Kopiuj prognozę godzinową**, **Kopiuj wartość prognozy** i/lub **Kopiuj prognozę wydatków** do wartości **tak**, jeśli prognozy projektu zleceń pracy mają automatycznie kopiowane do arkuszy zleceń pracy, jeśli zlecenie pracy jest w danym stanie cyklu życia.
12. W sekcji **harmonogram** Określ jedną z opcji równą **tak**, jeśli stan harmonogramu zadań zlecenia pracy ma zostać zaktualizowany, gdy stanem cyklu eksploatacji jest zlecenie pracy. Aby uzyskać opis opcji **gotowy**, **początkowy**, **końcowy** i **Usuń wiersze harmonogramu**, zajrzyj do tabeli wcześniej w tym temacie.

    > [!NOTE]
    > Aby znaleźć linie harmonogramu powiązane z zadaniem zlecenia pracy, należy wybrać polecenie **Zarządzanie składnikami majątku** \> **Wspólne** \> **Zlecenia pracy** \> **Wszystkie zlecenia pracy**, **Aktywne zlecenia pracy** lub **Moje aktywne zlecenia pracy**. Otwórz zlecenie pracy, zaznacz **zadanie zlecenia pracy** w skróconej karcie zadania zlecenia i informacje związane z widokiem w skróconej karcie **Szczegóły wiersza**. W polu **stan** na karcie **harmonogram** jest wyświetlany stan zadania dotyczącego zlecenia pracy. W **polu** stan można określić następujące wartości: **zaplanowane**, **gotowe**, **rozpoczęte**, **zatrzymane** i **zakończone.**

13. W sekcji **żądania konserwacji** w polu **stan cyklu życia** wybierz stan cyklu życia żądania konserwacji, do którego mają być aktualizowane powiązane żądania konserwacji. Ta aktualizacja jest wykonywana automatycznie. Można ją wykonać tylko wtedy, gdy w modelu czasu trwania żądania konserwacji jest wybrany stan cyklu konserwacji, który jest używany dla żądania konserwacji.
14. W sekcji **Składnik majątku** ustawienie opcji **Aktualizuj BOM** na wartość **tak**, jeśli wszystkie towary używane w zleceniu pracy powinny być automatycznie aktualizowane na **składniku majatku BOM** po zaktualizowaniu zlecenia pracy do tego stanu cyklu życia. To ustawienie może być przydatne, jeśli na przykład stan cyklu czasowego zlecenia pracy definiuje zlecenie jako wykonane lub zakończone.
15. W sekcji **Pula zleceń pracy**, dla opcji **Usuń odwołanie do puli** określ wartość **tak**, jeśli zlecenia pracy w tym stanie cyklu życia powinny być automatycznie usuwane z pul zleceń pracy.
16. Na skróconej karcie **Sprawdź poprawność**, wybierz typy sprawdzania poprawności, które powinny zostać aktywowane w tym stanie cyklu życia systemu, ustawiająco dpowiednie opcje na **tak**. Następnie w polu **typ** dla każdego wybranego typu sprawdzania poprawności wybierz typ komunikatu, który ma być wyświetlany, jeśli nie sprawdzono poprawności pól obowiązkowych powiązanych z typem sprawdzania poprawności. Jeśli zostanie wybrana opcja **błąd**, aktualizacja stanu cyklu życia zlecenia pracy zostanie anulowana do czasu zaktualizowania odpowiednich pól wymaganych w zleceniu pracy.

    - Opcje **Przerwa konserwacyjna**, **Lista kontrolna konserwowanego składnika majątku**, **Objaw usterki**, **Przyczyna usterki** i **Środki zaradcze dla usterki** są powiązane z opcjami w sekcji **Wymagany** na stronie **Typy zleceń pracy** (**Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zlecenia pracy** \> **Typy zleceń pracy**). Aby aktywować te sprawdzanie poprawności, w typie zlecenia produkcyjnego, który jest używany dla zlecenia, dla opcji powiązanych należy również użyć wartości **tak**.
    - Jeśli opcja **Lista kontrolna konserwowanego składnika majątku** jest ustawiona na wartość **tak** dla stanu cyklu konserwacji, na którym jest aktualizowane zlecenie pracy, sprawdzanie poprawności jest wykonywane w celu sprawdzenia, czy wiersze Lista kontrolna konserwowanego składnika majątku są oznaczone jako **wymagane** zostały zarejestrowane jako **sprawdzone** lub **nie dotyczy**. Jeśli żadna z tych rejestracji nie została dokonana w obowiązujących wierszach, komunikat informacyjny, błąd lub ostrzeżenie jest wyświetlany, gdy zlecenie pracy zostanie zaktualizowane do tego stanu cyklu życia.
    - Jeśli dla opcji **kosztu ustalonego** ustawiono wartość **tak** w przypadku stanu cyklu eksploatacji, do którego jest aktualizowane zlecenie pracy, łączna kwota kosztów ustalonych (czyli całkowita kwota wydatków, na które osoba prawna zobowiązała się zapłacić) jest obliczana dla każdego zadania zlecenia pracy. Komunikat jest wyświetlany, jeśli ustalona kwota kosztu przekracza 0 (zero). Należy wybrać typy zobowiązań dotyczących kosztów, które są uwzględnione na skróconej karcie **Zobowiązania kosztowe** na karcie **Kontrola kosztów** na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie** (**Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Parametry modułu Zarządzanie projektami i ich księgowanie**).
    - Jeśli dla opcji **Przerwa konserwacyjna** jest ustawiona wartość **tak** w przypadku stanu cyklu życia, na którym jest aktualizowane zlecenie pracy, proces sprawdzania przez czas konserwacji jest wykonywany na składniku majątku, który jest powiązany ze zleceniem pracy. Jeśli dokonano rejestracji przestojów związanych z obsługą, ale nie **zakończono** rejestracji, komunikat jest wyświetlany, gdy zlecenie pracy zostanie zaktualizowane do tego stanu cyklu życia.
    - Jeśli standardowe ustawienia projektu nie zawierają wszystkich etapów wymaganych dla konfiguracji Zarządzanie składnikami majątku, można skonfigurować zdefiniowane przez użytkownika etapy projektu na karcie **etap projektu** na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie**. Na poniższej ilustracji przedstawiono kartę **etap projektu** na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie**.

    ![Strona Ustaw etapy projektu dla różnych typów projektów](media/10-setup-for-work-orders.png)

> [!NOTE]
> Jeśli stan cyklu życia, w którym zlecenie pracy zostanie zaktualizowany, nie jest aktywny, Arkusze powiązane ze zleceniem produkcyjnym, które nie zostały jeszcze zaksięgowane, są usuwane automatycznie. To zachowanie pomaga zagwarantować automatyczne oczyszczanie nieużywanych danych. (Stan cyklu życia jest nieaktywny, jeśli **aktywna** opcja dla tej opcji jest ustawiona na wartość **nie** na skróconej karcie **ogólne** strony stan **cyklu życia zlecenia pracy**.)
>
> Jeśli ręcznie ustawiono zlecenie pracy tak, że nie jest aktywne, arkusze powiązane ze zleceniem pracy, które nie zostały jeszcze zaksięgowane, **nie** są usuwane automatycznie. (Aby ręcznie dezaktywować zlecenie pracy **Zarządzanie składnikami majątku** \> **Wspólny** \> **Zlecenia pracy** \> **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**. Otwórz zlecenie produkcyjne i przełącz się na widok **nagłówka**. Na skróconej karcie **ogólne** wybierz opcję **Edycja**, a następnie ustawienie **aktywnej** opcji na wartość **nie**.)

## <a name="relations-among-work-order-lifecycle-models-work-order-types-and-work-order-lifecycle-states"></a>Relacje między stanami cyklu życia zlecenia pracy, modelami cyklu życia zlecenia pracy i typami zleceń pracy

Modele cyklu życia odwołują się do przepływów pracy, a stany cyklu są wybierane w ramach modelu cyklu życia w kolejności sekwencyjnej. Modele cyklu życia są ustawiane dla typów zleceń pracy. Typy zleceń pracy decydują o rozmiarze lub zakresie przepływów pracy i procesów roboczych. Na przykład **konserwacja**, która jest standardowym typem zlecenia pracy, może być związana z modelem cyklu życia zlecenia pracy, który ma wiele stanów cyklu życia. W przeciwieństwie do tego można utworzyć zlecenie pracy **korygujące**, które jest używane dla zleceń, które nie zostały zaplanowane lub dla zleceń roboczych, w których zadanie zostało ukończone przed wykonaniem zlecenia pracy z powodu pilnej sytuacji. Ten typ zlecenia może być powiązany z modelem cyklu życia zlecenia pracy, który ma tylko kilka stanów cyklu życia.

Powodem użycia typów jest to, że w przypadku zdefiniowania typu na przykład zlecenia pracy lub składnika majątku automatycznie są definiowane powiązane procesy pracy (Stany cyklu). Aby uzyskać więcej informacji na temat konfigurowania typów zleceń pracy, zobacz temat [Typy zleceń pracy](../setup-for-work-orders/work-order-types.md).

> [!NOTE]
> Stany cyklu, modele cyklu życia i typy są stosowane do lokalizacji czynności konserwacyjnych, zasobów i obsługi, a także do zleceń pracy.

Na poniższej ilustracji przedstawiono relację między typami zleceń pracy, modelami cyklu życia i stanami cyklu życia.

![Strona typ zlecenia pracy porównywanego z modelami cyklu życia zlecenia pracy](media/11-setup-for-work-orders.png)

## <a name="work-order-lifecycle-models"></a>Modele cyklu życia zlecenia pracy

Po utworzeniu stanów cyklu życia zlecenia pracy, które są wymagane dla zleceń pracy, można je podzielić na grupy stanu cyklu życia zlecenia pracy. Należy utworzyć co najmniej jeden standardowy model cyklu życia.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zlecenia pracy** \> **Modele cyklu życia**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowy model cyklu życia zlecenia pracy.
3. W polu **Model cyklu życia** wprowadź identyfikator modelu cyklu życia.
4. W polu **Nazwa** wprowadź nazwę.

    Na skróconej karcie **Szczegóły** pole **Stany cyklu życia** pokazuje liczbę stanów cyklu życia, które są wybrane w modelu cyklu życia. Pole **Typy zlecenia pracy** pokazuje liczbę typów zlecenia pracy, które używają tego modelu cyklu życia.

5. Na skróconej karcie **Stany cyklu życia** wybierz stany cyklu życia, które powinny być uwzględnione w modelu cyklu życia:

    - Aby uwzględnić stanu cyklu życia w modelu cyku życia, zaznacz go w sekcji **Pozostałe stany cyklu życia**, a następnie wybierz przycisk strzałki w prawo ![Strzałka w prawo](media/12-setup-for-work-orders.png), aby przenieść go do sekcji **Wybrane stany cyklu życia**.
    - Aby uwzględnić wszystkie dostępne stany cyklu życia w modelu cyklu życia, wybierz przycisk **Wybierz wszystkie dostępne stany** ![Wybierz wszystkie dostępne stany](media/13-setup-for-work-orders.png). Wszystkie stany cyklu życia są przenoszone do sekcji **Wybrane cykle życia**.
    - Aby usunąć stan cyklu życia z modelu cyklu życia, wybierz go w sekcji **Wybrane stany cyklu życia**, a następnie wybierz przycisk strzałki lewo ![Strzałka w lewo](media/14-setup-for-work-orders.png), aby przenieść go do sekcji **Pozostałe stany cyklu życia**.

6. Wybierz pozycję **Aktualizacje stanu cyklu życia**, aby określić stany cyklu życia, które mogą być wybranym stanem cyklu życia.
7. W skróconej karcie **aktualizacji** w polu **stan zaplanowana** wybierz stan cyklu życia, który zawsze powinien być wybierany dla zlecenia, dla którego wykonano planowanie zlecenia pracy, niezależnie od poprzedniego stanu cyklu życia zlecenia pracy.
8. W polu **niezaplanowany stan cyklu życia** wybierz stan cyklu życia, który zawsze powinien być wybierany dla zlecenia pracy, jeśli zostanie usunięte Planowanie zleceń pracy.
9. Zapisz model cyklu życia zlecenia pracy.

![Strona Modele cyklu życia zlecenia pracy](media/15-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]