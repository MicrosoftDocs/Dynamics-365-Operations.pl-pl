---
title: Zarządzanie potrąceniami przy użyciu pulpitu potrącenia
description: W tym artykule opisano sposób korzystania z pulpitu potrącenia do przetwarzania płatności klientów, które zawierają potrącenia.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 607ad528b56d1f0c9a78e113f67c920cdae6e620
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873616"
---
# <a name="manage-deductions-using-the-deduction-workbench"></a>Zarządzanie potrąceniami przy użyciu pulpitu potrącenia

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób korzystania z pulpitu potrącenia do przetwarzania płatności klientów, które zawierają potrącenia.

Klient, któremu należny jest rabat, może zrezygnować z czekania na wypłatę rabatu. Zamiast tego klient może wysłać płatność, łącznie z potrąceniem kwoty rabatu. W celu obsługi tego typu transakcji pulpit potrąceń umożliwia dopasowanie potrąceń do otwartych transakcji kredytowych, potrąceń podzielonych, odmów potrąceń i odpisów potrąceń.

> [!NOTE]
> Pulpit nawigacyjny potrącenia jest częścią funkcji sprzedaży i marketingu w aplikacji Microsoft Dynamics 365 Supply Chain Management przez długi czas. Jednak teraz został on ulepszony tak, że działa również z nowszym modułem **zarządzania rabatami**. W tym artykule opisano sposób używania zarówno starszych funkcji, jak i funkcji zarządzania rabatami na pulpicie nawigacyjnym potrąceń. Jeśli jednak nie [włączysz modułu **zarządzania rabatami** dla swojego systemu](rebate-management-enable.md), niektóre funkcje opisane w tym miejscu nie będą dostępne.

## <a name="prerequisites"></a>Wymagania wstępne

### <a name="set-up-the-old-deduction-management-system"></a>Konfigurowanie starego systemu zarządzania potrąceniami

Można użyć pulpitu nawigacyjnego potrącenia wraz ze starymi możliwościami zarządzania potrąceniami z aplikacji Supply Chain Management, nawet jeśli nie używasz modułu **zarządzania rabatami**. Należy jednak najpierw przygotować system zgodnie z opisem w tej sekcji.

Przed użyciem pulpitu potrąceń należy wykonać zadania konfiguracyjne opisane w obszarze [Konfigurowanie zarządzania potrąceniami](/dynamicsax-2012/appuser-itpro/set-up-deduction-management). Należy również skonfigurować typ umowy rabatowej dla klienta: albo rabat dla klienta, zgodnie z opisem w części [Konfigurowanie i aktualizowanie rekordów rabatów dla odbiorców](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates), lub rabat dla odpisów handlowych.

Jeśli stosujesz potrącenie do rabatu klienta, musisz wykonać następujące zadania:

- [Konfigurowanie rabatów dla klientów](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates).
- Zatwierdzanie i przetwarzanie rabatu, tak aby można było użyć pulpitu potrąceń.

Jeśli stosujesz potrącenie do rabatu dla odpisu handlowego, musisz wykonać następujące zadania:

- Konfigurowanie rabatów fakturowania zwrotnego.
- Stosowanie rabatów fakturowania zwrotnego.

### <a name="configure-accounts-receivable-and-deductions"></a><a name="accounts-receivable-deductions"></a>Konfigurowanie modułu Rozrachunki z odbiorcami i potrąceń

System rejestruje wszystkie zdarzenia potrącenia w arkuszu roszczeń. W związku z tym system musi zawierać arkusz, który może służyć do tego celu. Jeśli nie masz jeszcze arkusza roszczeń, skonfiguruj go teraz. Ten arkusz jest wymagany do tworzenia potrąceń bezpośrednio na pulpicie potrąceń, rozliczeniu klienta lub na stronie klienta.

Aby skonfigurować nowy arkusz roszczeń dla potrąceń, wykonaj następujące kroki.

1. Przejdź do pozycji **Księga główna \> Konfiguracja arkusza \> Nazwy arkuszy**.
1. Wybierz pozycję **Nowy** i ustaw następujące pola dla nowej nazwy arkusza:

    - **Nazwa** — wprowadź unikatową nazwę arkusza roszczeń.
    - **Opis** — wprowadź opis nowego arkusza.
    - **Typ arkusza** — wybierz pozycję *Dzienny*.
    - **Seria załączników** — przypisz istniejący identyfikator sekwencji. Alternatywnie można utworzyć nową sekwencję identyfikatorów z zakresem firmy i przypisać ją do nowej nazwy arkusza.

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
1. Na karcie **Potrącenia** na skróconej karcie **Ogólne** ustaw pole **Nazwa arkusza roszczeń** na właśnie utworzoną nazwę arkusza.
1. Na skróconej karcie **Zwróć zamówienie** ustaw następujące pola:

    - **Utwórz zamówienie zwrotu** — ustaw tę opcję, aby określić, co system powinien zrobić po zatwierdzeniu roszczenia opartego na ilości:

        - *Tak* — utwórz zamówienie zwrotu.
        - *Nie* — utwórz zamówienie sprzedaży o wartości ujemnej.

    - **Tworzenie bez dołączonej faktury** — wybierz wartość, aby określić, co system powinien zrobić, gdy roszczenie oparte na ilości jest zatwierdzone, ale nie jest dołączona faktura:

        - *Zaakceptuj* — utwórz zamówienie zwrotu.
        - *Ostrzeżenie* — utwórz zamówienie zwrotu, ale wyświetl następujący komunikat ostrzegawczy: „Roszczenie nie jest dołączone do faktury”.
        - *Błąd* — nie twórz zamówienia zwrotu i wyświetl następujący komunikat o błędzie: „Roszczenie nie jest dołączone do faktury. Aktualizacja została anulowana".

    - **Utwórz zamówienie zwrotu przed zatwierdzeniem potrącenia** — ustaw tę opcję na *Tak*, jeśli zamówienia zwrotu mogą zostać utworzone przed zatwierdzeniem roszczenia. To ustawienie dotyczy tylko roszczeń opartych na ilości, w przypadku których opcja **Utwórz zamówienie zwrotu** jest ustawiona na *Tak*.

### <a name="configure-general-ledger-parameters"></a>Konfigurowanie parametrów księgi głównej

Gdy system tworzy arkusz roszczeń dla nowego potrącenia, tworzy również dwie nowe transakcje klienta: jedną, aby zrównoważyć kwotę roszczenia z oryginalną fakturą i drugą w celu zarejestrowania długu klienta do kwoty roszczenia (ponieważ roszczenie nie zostało jeszcze zatwierdzone). W związku z tym należy skonfigurować system, tak aby pojedynczy załącznik mógł mieć wiele wierszy klienta.

Aby włączyć opcję wielu wierszy klienta w jednym załączniku, wykonaj następujące kroki.

1. Przejdź do pozycji **Księga główna \> Ustawienia księgi \> Parametry księgi głównej**.
1. Na karcie **Księga**, na skróconej karcie **Ogólne** ustaw opcję **Zezwalaj na wiele transakcji w jednym załączniku** na *Tak*.
1. Jeśli zostanie wyświetlony komunikat ostrzegawczy, wybierz przycisk **Zamknij**, aby zaakceptować zmianę.

### <a name="create-deduction-reasons"></a><a name="deduction-reasons"></a>Tworzenie przyczyn potrąceń

System wymaga, aby użytkownicy określili przyczynę każdego potrącenia, które wprowadzają bezpośrednio na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta. Przyczyna określa sposób obsługi potrącenia po jego zatwierdzeniu.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Przyczyny potrąceń**.
1. Wybierz opcję **Nowy** w celu dodania wiersza do siatki, a następnie określ dla niego następujące pola:

    - **Przyczyna roszczenia** — wprowadź unikatową nazwę przyczyny.
    - **Opis** — umożliwia wprowadzenie opisu przyczyny w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.
    - **Podstawa roszczenia** — wybierz podstawę roszczenia dla przyczyny roszczenia:

        - *Oparte na cenie* — utwórz niezależną fakturę księgową po zatwierdzeniu.
        - *Oparte na ilości* — utwórz zamówienie sprzedaży o wartości ujemnej lub zamówienia zwrotu po zatwierdzeniu.

    - **Kod przyczyny zwrotu** — wybierz kod przyczyny zwrotu, aby zastosować jako wartość **kodu przyczyny zwrotu** dla zamówienia zwrotu.
    - **Typ** — umożliwia wybór typu potrącenia. Wartość **Kompensacja potrącenia** dla wybranego typu będzie używana do ustawiania pola **Kompensacja potrącenia** po utworzeniu potrącenia lub roszczenia. Typy potrąceń są definiowane na stronie **Typy potrąceń** (**Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Typy potrąceń**).
    - **Konto księgowania roszczeń** — to pole jest dostępne tylko wtedy, gdy pole **Podstawa roszczenia** jest ustawione na *Oparte na cenie*. Po zatwierdzeniu roszczenia opartego na cenie system przypisuje konto księgowe wybrane w tym miejscu jako wartość **Konto główne** dla niezależnej faktury korygującej w wersji roboczej.

### <a name="set-up-the-settle-approved-deductions-periodic-task"></a>Konfigurowanie zadania okresowego rozliczania zatwierdzonych potrąceń

W przypadku potrąceń, które są tworzone przy użyciu polecenie **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniach klienta lub na stronie klienta, można skonfigurować okresowe zadanie *rozliczania zatwierdzonych potrąceń*, aby automatycznie dopasowywać potrącenia i faktury korygujące, które mają pasujące wartości i kwoty **identyfikatora potrącenia**.

Aby zaplanować to zadanie, przejdź do pozycji **Sprzedaż i marketing \> Zadania okresowe \> Rozlicz zatwierdzone potrącenia** i skonfiguruj opcje, filtry i harmonogram, podobnie jak w przypadku innych typów zadań okresowych.

> [!NOTE]
> Jeśli opcja **Automatyczne rozliczenie** jest ustawiona na *Tak* na karcie **Rozliczenie** na stronie **Parametry rozrachunków z odbiorcami** (**Rozrachunki z odbiorcami \> Konfiguracja \> Parametry modułu rozrachunków z odbiorcami**) zadanie okresowe *Rozlicz zatwierdzone potrącenia* nic nie zrobi, ponieważ kredyt zostanie automatycznie rozliczony.

## <a name="create-a-deduction"></a>Tworzenie potrącenia

### <a name="create-a-deduction-journal-entry-by-using-the-customer-payment-journal"></a>Tworzenie wpisu w arkuszu potrąceń przy użyciu arkusza płatności klienta

Aby utworzyć wpis w arkuszu potrąceń, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Płatności \> Arkusz płatności klienta**.
1. Kliknij przycisk **Nowe**, aby dodać wiersz do siatki.
1. W polu **Nazwa** nowego wiersza wybierz nazwę arkusza.
1. W okienku akcji wybierz pozycję **Wiersze**.
1. Wprowadź datę, konto firmy i numer konta klienta.
1. W polu **Faktura** wybierz fakturę, z którą skojarzono potrącenie.
1. W polu **Kredyt** wprowadź kwotę wpłaconą przez klienta.
1. Wybierz **OK**, aby potwierdzić, że kwota jest niższa od całkowitej kwoty dla zaznaczonej transakcji.
1. Wybierz typ konta przeciwstawnego, a także konto przeciwstawne.
1. Na pasku narzędzi nad siatką wybierz pozycję **Potrącenia**.
1. Na stronie **Potrącenie**, w okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Pole **Identyfikator potrącenia** dla nowego wiersza jest ustawiane automatycznie.
1. W polu **Typ** wybierz typ potrącenia.
1. W polu **Kwota** wprowadź kwotę, która zostanie wyświetlona w polu **Saldo** nad listą potrąceń. Ta kwota reprezentuje kwotę, którą odbiorca potrącił z płatności.
1. Zamknij stronę **Potrącenie**. Nastąpi powrót na stronę **Płatności klienta**, na której zostanie wyświetlona nowy wiersz potrącenia.
1. W okienku akcji wybierz pozycję **Weryfikuj \> Weryfikuj**. Powinien zostać wyświetlony następujący komunikat: „Arkusz jest OK”.
1. W okienku akcji wybierz pozycję **Księguj**.

### <a name="create-a-deduction-by-using-the-deduction-workbench"></a>Tworzenie potrącenia przy użyciu pulpitu potrącenia

Aby utworzyć nowe potrącenie na pulpicie potrącenia, wykonaj następujące czynności.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. W okienku akcji wybierz pozycję **Obsługa \> Nowe potrącenie**.

    W oknie dialogowym **Nowe potrącenie** pole **Identyfikator potrącenia** jest ustawiane na podstawie sekwencji identyfikatorów **Identyfikator potrącenia** zdefiniowanej na stronie **Parametry zarządzania odpisami handlowymi** (**Sprzedaż i marketing \> Konfiguracja \> Odpisy handlowe \> Parametry zarządzania odpisami handlowymi**).

1. Ustaw wartości w następujących polach:

    - **Konto klienta** — wybierz konto klienta, którego dotyczy potrącenie.
    - **Zewnętrzny numer roszczenia** — wprowadź odwołanie do roszczenia klienta.
    - **Kwota roszczenia** — wprowadź kwotę roszczenia z podatkiem. Wartość musi być dodatnia.
    - **Waluta** — wybierz walutę dla potrącenia. Wartością domyślną jest waluta ustawiona dla wybranego konta klienta.
    - **Podstawa roszczenia** — wybierz podstawę roszczenia. Podstawa roszczenia określa typ transakcji kredytowej, która jest tworzona po zatwierdzeniu potrącenia lub roszczenia.

        - *Oparte o cenę* — zostanie utworzona wersja roboczej faktury niezależnej.
        - *Oparte o ilość* — zostanie utworzone zamówienie sprzedaży o wartości ujemnej lub zamówienie zwrotu.

    - **Data roszczenia** — wybierz datę roszczenia. Wartością domyślną jest data bieżąca.
    - **Przyczyna roszczenia** — wybierz kod przyczyny, który ma zastosowanie do bieżącego potrącenia. Wybrana podstawa roszczenia ma wpływ na zastosowane opcje. Aby uzyskać więcej informacji na temat tworzenia i konfigurowania przyczyn roszczeń, które są dostępne do wyboru w tym miejscu, zobacz sekcję [Tworzenie przyczyn potrąceń](#deduction-reasons) wcześniej w tym artykule.
    - **Uwagi** — dodaj wszystkie notatki, które mają zastosowanie. Po zatwierdzeniu roszczenia osoba zatwierdzająca będzie mogła edytować uwagi dotyczące roszczenia lub dodawać do nich informacje.
    - **Utwórz arkusz roszczen** — ustaw tę opcję, aby określić, czy arkusz roszczeń ma zostać utworzony podczas tworzenia roszczenia lub potrącenia:

        - *Tak* — system utworzy i zaksięguje arkusz główny przy użyciu arkusza roszczeń skonfigurowanego na stronie **Parametry modułu rozrachunków z odbiorcami**. (Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie modułu Rozrachunki z odbiorcami i potrąceń](#accounts-receivable-deductions) wcześniej w tym artykule). Gdy faktura jest dołączona do roszczenia, arkusz roszczenia jest używany do zmniejszenia salda odpowiedniej faktury. Jeśli roszczenie zostanie później odrzucone, arkusz roszczeń i rozliczenia (jeśli faktura została załączona) zostaną wycofane.
        - *Nie* — w tej chwili nie jest tworzony żaden arkusz roszczeń. Zostanie on utworzony po zatwierdzeniu roszczenia. Do nowego roszczenia nadal można dołączyć fakturę, nawet jeśli arkusz roszczenia nie został utworzony. Jednak rozliczenie nie może być wykonane bez arkusza roszczeń.

1. Kliknij przycisk **OK**.

    Zostanie utworzone nowe potrącenie. Jeśli opcja **Utwórz arkusz roszczeń** zostanie ustawiona na *Tak*, księgowane są następujące transakcje:

    - **Dwie nowe transakcje klienta** — jedna transakcja kompensuje kwotę roszczenia z oryginalną fakturą. Druga transakcja rejestruje dług klienta do kwoty roszczenia, ponieważ roszczenie nie zostało jeszcze zatwierdzone. Oryginalna transakcja faktury i przeciwstawna transakcja roszczenia zostaną automatycznie oznaczone do rozliczenia podczas dołączania faktury przez wybranie opcji **Obsługa \> Dołącz fakturę** w okienku akcji.
    - **Dwie transakcje kompensacyjne** — te transakcje są księgowane na koncie księgi **Kompensacja potrąceń**.
    - **Arkusz roszczeń** — aby wyświetlić arkusz roszczeń dla każdego potrącenia wyświetlanego na pulpicie potrąceń, wybierz kartę **Odwołania**. Arkusz roszczeń jest wyświetlany w polu **Numer partii arkusza**. Arkusz roszczeń można również wyświetlić na karcie **Zdarzenia potrącenia**. Tam będzie miał **Typ aktualizacji** ustawiony na *Dopasowanie*.

### <a name="create-a-deduction-from-a-customer-settlement"></a>Tworzenie potrącenia z rozliczenia klienta

Proces tworzenia potrącenia z rozliczenia klienta przypomina proces tworzenia potrącenia za pośrednictwem pulpitu potrąceń. Jednak waluta klienta i faktury są ustawiane automatycznie, a faktura jest dołączona. Podczas tworzenia roszczenia lub potrącenia za pośrednictwem strony rozliczenia klienta nie trzeba wybierać opcji **Obsługa \> Dołącz fakturę** w okienku akcji.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
1. Wybierz klienta, dla którego chcesz utworzyć potrącenie.
1. W okienku akcji na karcie **Windykacja** w grupie **Rozlicz** wybierz opcję **Rozlicz transakcje**.
1. W oknie dialogowym **Ustawianie transakcji** na karcie **Przegląd** wybierz fakturę, aby utworzyć powiązane potrącenie.
1. Na pasku narzędzi wybierz pozycję **Potrącenia \> Nowe potrącenie**.

    W oknie dialogowym **Nowe potrącenie** pole **Identyfikator potrącenia** jest ustawiane na podstawie sekwencji identyfikatorów **Identyfikator potrącenia** zdefiniowanej na stronie **Parametry zarządzania odpisami handlowymi** (**Sprzedaż i marketing \> Konfiguracja \> Odpisy handlowe \> Parametry zarządzania odpisami handlowymi**). Pole **Konto klienta** jest ustawiane na konto klienta, którego dotyczy potrącenie.

1. Ustaw wartości w następujących polach:

    - **Zewnętrzny numer roszczenia** — wprowadź odwołanie do roszczenia klienta.
    - **Kwota roszczenia** — wprowadź kwotę roszczenia z podatkiem. Wartość musi być dodatnia.
    - **Waluta** — wybierz walutę dla potrącenia. Wartością domyślną jest waluta ustawiona dla wybranego konta klienta.
    - **Podstawa roszczenia** — wybierz podstawę roszczenia. Podstawa roszczenia określa typ transakcji kredytowej, która jest tworzona po zatwierdzeniu potrącenia lub roszczenia.

        - *Oparte o cenę* — zostanie utworzona wersja roboczej faktury niezależnej.
        - *Oparte o ilość* — zostanie utworzone zamówienie sprzedaży o wartości ujemnej lub zamówienie zwrotu.

    - **Data roszczenia** — wybierz datę roszczenia. Wartością domyślną jest data bieżąca.
    - **Przyczyna roszczenia** — wybierz kod przyczyny, który ma zastosowanie do bieżącego potrącenia. Wybrana podstawa roszczenia ma wpływ na zastosowane opcje. Aby uzyskać więcej informacji na temat tworzenia i konfigurowania przyczyn roszczeń, które są dostępne do wyboru w tym miejscu, zobacz sekcję [Tworzenie przyczyn potrąceń](#deduction-reasons) wcześniej w tym artykule.
    - **Uwagi** — dodaj wszystkie notatki, które mają zastosowanie. Po zatwierdzeniu roszczenia osoba zatwierdzająca będzie mogła edytować uwagi dotyczące roszczenia lub dodawać do nich informacje.
    - **Utwórz arkusz roszczen** — ustaw tę opcję, aby określić, czy arkusz roszczeń ma zostać utworzony podczas tworzenia roszczenia lub potrącenia:

        - *Tak* — system utworzy i zaksięguje arkusz główny przy użyciu arkusza roszczeń skonfigurowanego na stronie **Parametry modułu rozrachunków z odbiorcami**. (Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie modułu Rozrachunki z odbiorcami i potrąceń](#accounts-receivable-deductions) wcześniej w tym artykule). Gdy faktura jest dołączona do roszczenia, arkusz roszczenia jest używany do zmniejszenia salda odpowiedniej faktury. Jeśli roszczenie zostanie później odrzucone, arkusz roszczeń i rozliczenia (jeśli faktura została załączona) zostaną wycofane.
        - *Nie* — w tej chwili nie jest tworzony żaden arkusz roszczeń. Zostanie on utworzony po zatwierdzeniu roszczenia. Do nowego roszczenia nadal można dołączyć fakturę, nawet jeśli arkusz roszczenia nie został utworzony. Jednak rozliczenie nie może być wykonane bez arkusza roszczeń.

1. Kliknij przycisk **OK**.

    Zostanie utworzone nowe potrącenie. Jeśli opcja **Utwórz arkusz roszczeń** zostanie ustawiona na *Tak*, księgowane są następujące transakcje:

    - **Dwie nowe transakcje klienta** — jedna transakcja kompensuje kwotę roszczenia z oryginalną fakturą. Druga transakcja rejestruje dług klienta do kwoty roszczenia, ponieważ roszczenie nie zostało jeszcze zatwierdzone. Oryginalna transakcja faktury i przeciwstawna transakcja roszczenia zostaną automatycznie oznaczone do rozliczenia podczas dołączania faktury przez wybranie opcji **Obsługa \> Dołącz fakturę** w okienku akcji.
    - **Dwie transakcje kompensacyjne** — te transakcje są księgowane na koncie księgi **Kompensacja potrąceń**.
    - **Arkusz roszczeń** — aby wyświetlić arkusz roszczeń dla każdego potrącenia wyświetlanego na pulpicie potrąceń, wybierz kartę **Odwołania**. Arkusz roszczeń jest wyświetlany w polu **Numer partii arkusza**. Arkusz roszczeń można również wyświetlić na karcie **Zdarzenia potrącenia**. Tam będzie miał **Typ aktualizacji** ustawiony na *Dopasowanie*.

    Nastąpi powrót do strony **Rozliczanie transakcji**, na której teraz zostanie wyświetlona wybrana faktura jako oznaczona. Przycisk **Księguj** jest dostępny tylko wtedy, gdy opcja **Utwórz arkusz roszczeń** jest ustawiona na *Tak*. Jeśli jest dostępna, wybierz pozycję **Księguj**, aby zmniejszyć saldo na fakturze o wartość **kwoty roszczenia**.

### <a name="create-a-deduction-from-a-customer-page"></a>Tworzenie potrącenia ze strony klienta

Proces tworzenia potrącenia ze strony klienta przypomina proces tworzenia potrącenia za pośrednictwem pulpitu potrąceń. Jednak klient jest ustawiany automatycznie.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
1. Wybierz klienta, dla którego chcesz utworzyć potrącenie.
1. W okienku akcji na karcie **Windykacja** w grupie **Potrącenia** wybierz opcję **Utwórz potrącenia**.

    W oknie dialogowym **Nowe potrącenie** pole **Identyfikator potrącenia** jest ustawiane na podstawie sekwencji identyfikatorów **Identyfikator potrącenia** zdefiniowanej na stronie **Parametry zarządzania odpisami handlowymi** (**Sprzedaż i marketing \> Konfiguracja \> Odpisy handlowe \> Parametry zarządzania odpisami handlowymi**). Pole **Konto klienta** jest ustawiane na konto klienta, którego dotyczy potrącenie.

1. Ustaw wartości w następujących polach:

    - **Zewnętrzny numer roszczenia** — wprowadź odwołanie do roszczenia klienta.
    - **Kwota roszczenia** — wprowadź kwotę roszczenia z podatkiem. Wartość musi być dodatnia.
    - **Waluta** — wybierz walutę dla potrącenia. Wartością domyślną jest waluta ustawiona dla wybranego konta klienta.
    - **Podstawa roszczenia** — wybierz podstawę roszczenia. Podstawa roszczenia określa typ transakcji kredytowej, która jest tworzona po zatwierdzeniu potrącenia lub roszczenia.

        - *Oparte o cenę* — zostanie utworzona wersja roboczej faktury niezależnej.
        - *Oparte o ilość* — zostanie utworzone zamówienie sprzedaży o wartości ujemnej lub zamówienie zwrotu.

    - **Data roszczenia** — wybierz datę roszczenia. Wartością domyślną jest data bieżąca.
    - **Przyczyna roszczenia** — wybierz kod przyczyny, który ma zastosowanie do bieżącego potrącenia. Wybrana podstawa roszczenia ma wpływ na zastosowane opcje. Aby uzyskać więcej informacji na temat tworzenia i konfigurowania przyczyn roszczeń, które są dostępne do wyboru w tym miejscu, zobacz sekcję [Tworzenie przyczyn potrąceń](#deduction-reasons) wcześniej w tym artykule.
    - **Uwagi** — dodaj wszystkie notatki, które mają zastosowanie. Po zatwierdzeniu roszczenia osoba zatwierdzająca będzie mogła edytować uwagi dotyczące roszczenia lub dodawać do nich informacje.
    - **Utwórz arkusz roszczen** — ustaw tę opcję, aby określić, czy arkusz roszczeń ma zostać utworzony podczas tworzenia roszczenia lub potrącenia:

        - *Tak* — system utworzy i zaksięguje arkusz główny przy użyciu arkusza roszczeń skonfigurowanego na stronie **Parametry modułu rozrachunków z odbiorcami**. (Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie modułu Rozrachunki z odbiorcami i potrąceń](#accounts-receivable-deductions) wcześniej w tym artykule). Gdy faktura jest dołączona do roszczenia, arkusz roszczenia jest używany do zmniejszenia salda odpowiedniej faktury. Jeśli roszczenie zostanie później odrzucone, arkusz roszczeń i rozliczenia (jeśli faktura została załączona) zostaną wycofane.
        - *Nie* — w tej chwili nie jest tworzony żaden arkusz roszczeń. Zostanie on utworzony po zatwierdzeniu roszczenia. Do nowego roszczenia nadal można dołączyć fakturę, nawet jeśli arkusz roszczenia nie został utworzony. Jednak rozliczenie nie może być wykonane bez arkusza roszczeń.

1. Kliknij przycisk **OK**.

    Zostanie utworzone nowe potrącenie. Jeśli opcja **Utwórz arkusz roszczeń** zostanie ustawiona na *Tak*, księgowane są następujące transakcje:

    - **Dwie nowe transakcje klienta** — jedna transakcja kompensuje kwotę roszczenia z oryginalną fakturą. Druga transakcja rejestruje dług klienta do kwoty roszczenia, ponieważ roszczenie nie zostało jeszcze zatwierdzone. Oryginalna transakcja faktury i przeciwstawna transakcja roszczenia zostaną automatycznie oznaczone do rozliczenia podczas dołączania faktury przez wybranie opcji **Obsługa \> Dołącz fakturę** w okienku akcji.
    - **Dwie transakcje kompensacyjne** — te transakcje są księgowane na koncie księgi **Kompensacja potrąceń**.
    - **Arkusz roszczeń** — aby wyświetlić arkusz roszczeń dla każdego potrącenia wyświetlanego na pulpicie potrąceń, wybierz kartę **Odwołania**. Arkusz roszczeń jest wyświetlany w polu **Numer partii arkusza**. Arkusz roszczeń można również wyświetlić na karcie **Zdarzenia potrącenia**. Tam będzie miał **Typ aktualizacji** ustawiony na *Dopasowanie*.

## <a name="create-a-credit-note-for-a-customer"></a>Tworzenie noty kredytowej dla klienta

Jeśli istnieje zatwierdzony rabat dla odbiorcy, możesz utworzyć fakturę korygującą na koncie odbiorcy, odpowiadającą rabatowi, zgodnie z potrzebami. Kwota pojawia się po stronie kredytowej na pulpicie potrącenia, gdzie może zostać dopasowana do potrącenia.

Aby utworzyć fakturę korygującą, należy wykonać poniższe kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odbiorcy \> Wszyscy odbiorcy**.
1. Zaznacz odbiorcę.
1. W okienku akcji na karcie **Windykacja** w grupie **Rozlicz** wybierz opcję **Rozlicz transakcje**.
1. W oknie dialogowym **Rozliczanie transakcji** wybierz transakcję, do której zastosowano rabat.
1. Na pasku narzędzi w menu **Funkcje** wybierz typ programu rabatowego, który ma zastosowanie.
1. Na stronie **Rabat** na karcie **Przegląd** zaznacz pole wyboru **Oznacz** obok odpowiedniego identyfikatora rabatu.
1. W okienku akcji wybierz pozycję **Funkcje \> Utwórz fakturę korygującą**.

## <a name="process-a-deduction-on-the-deduction-workbench"></a>Przetwarzanie potrącenia na pulpicie potrącenia

Pulpit potrącenia umożliwia dopasowanie potrąceń do otwartych transakcji kredytowych, potrąceń podzielonych, odmów potrąceń i odpisów potrąceń.

W zależności od żądanego sposobu przetwarzania potrącenia, wykonaj co najmniej jedną z procedur w poniższych podsekcjach. W razie potrzeby można połączyć procedury. Można na przykład podzielić potrącenie na dwie części, a następnie dopasować jedną część do wpisu po stronie kredytowej i zostawić pozostałą część na pulpicie w celu dopasowania do innego wpisu po stronie kredytowej później. Można również dopasować potrącenie do wpisu po stronie kredytowej, który jest mniejsza niż kwota potrącenia, a następnie odmówić lub odpisać pozostałe saldo potrącenia.

### <a name="match-a-deduction-to-a-credit"></a>Dopasowywanie potrącenia do wpisu po stronie kredytowej

Aby dopasować potrącenie do kredytu, wykonaj następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Zaznacz pole wyboru **Oznacz** obok potrącenia, aby rozpocząć przetwarzanie.
1. W sekcji **Otwarte transakcje** zaznacz pole wyboru **Oznacz**, aby kredyt był zgodny z potrąceniem. Jeśli na liście wyświetlono wiele wpisów po stronie kredytowej, można wybrać więcej niż jeden wpis w celu dopasowania do potrącenia. Jeśli chcesz, aby system automatycznie wybierał kredyty, które odpowiadają kwocie potrącenia, na pasku narzędzi wybierz odpowiednią opcję w menu **Wybierz kwotę potrącenia**.
1. W okienku akcji wybierz kolejno opcje **Obsługa \> Dopasuj**. System dopasowuje potrącenie do wpisu po stronie kredytowej. Jeśli saldo pozostaje w potrąceniu, jest ono wyświetlane w polu **Pozostała kwota** na karcie **Potrącenia**.

    > [!NOTE]
    > W przypadku potrąceń utworzonych przy użyciu polecenia **Nowe potrącenie** na pulpicie odliczeń, w rozliczenie klienta lub na stronie klienta polecenie **Obsługa \> Dopasuj** jest dostępne tylko wtedy, gdy pole **Stan roszczenia** jest ustawione na *Zaakceptowane*. To polecenie może służyć do ręcznego dopasowania transakcji opartej na cenie lub ilości do skojarzonego kredytu w sekcji **Otwarte transakcje**. Ten kredyt jest tworzony po zatwierdzeniu potrącenia (za pomocą polecenia **Obsługa \> Zatwierdź polecenie**) lub gdy jest on dołączony do istniejącego kredytu, zgodnie z opisem w sekcji [Kredyty tworzone poza procesem zatwierdzania potrąceń](#credits-outside-approval) w dalszej części tego artykułu. Zadanie okresowe *Rozliczanie zatwierdzonych potrąceń* (**Sprzedaż i marketing \> Zadania okresowe \> Rozlicz zatwierdzone potrącenia**) może być również używane do automatycznego dopasowywania potrąceń i kredytów, które mają pasujące wartości i kwoty **Identyfikator potrącenia**.

### <a name="split-a-deduction"></a>Dzielenie potrącenia

Aby podzielić potrącenie, wykonaj następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Zaznacz pole wyboru **Oznacz** obok potrącenia, aby rozpocząć przetwarzanie.
1. W okienku akcji wybierz kolejno opcje **Obsługa \> Podziel**.
1. W oknie dialogowym **Podział** w polu **Podziel kwotę** wprowadź kwotę do podziału z głównego potrącenia. Następnie wybierz opcję **OK**.
1. Na karcie **Potrącenia** pojawi się nowy rekord dotyczący kwoty podziału. Oryginalny rekord potrącenia zawiera pozostałe saldo potrącenia. Teraz można oddzielnie zarządzać obiema częściami oryginalnego rabatu.
1. Wybierz oryginalny rekord potrącenia, a następnie wybierz kartę **Odwołania**. Pole **Podziel kwotę** zawiera kwotę, która została oddzielona od pierwotnej kwoty.

### <a name="attach-an-invoice-to-a-deduction"></a>Dołączanie faktury do potrącenia

Fakturę można dołączyć do potrącenia, jeśli potrącenie zostało utworzone przy użyciu polecenia **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta, i nie ma aktualnie dołączonej faktury (oznacza to, że kolumna **Faktura** jest pusta).

Aby dołączyć fakturę do potrącenia, wykonaj następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Zaznacz pole wyboru **Oznacz** obok potrącenia, aby rozpocząć przetwarzanie.
1. W okienku akcji wybierz pozycję **Obsługa \> Dołącz fakturę**.
1. W oknie dialogowym **Dołączanie faktury** wybierz fakturę, a następnie wybierz przycisk **OK**.
1. W oknie dialogowym **Rozliczanie transakcji** wykonaj jedną z następujących czynności, w zależności od tego, czy arkusz roszczeń został zaksięgowany podczas tworzenia potrącenia:

    - Jeśli zaksięgowano arkusz roszczeń, wybrana faktura i transakcja kredytu klienta w arkuszu roszczeń mają znacznik wyboru w kolumnie **Oznacz**. Wybierz opcję **Zaksięguj**. Pozostałe saldo na załączonej fakturze jest zmniejszane o kwotę roszczenia.
    - Jeśli arkusz roszczeń nie został zaksięgowany, żadna transakcja nie jest oznaczana znacznikiem wyboru w kolumnie **Oznacz**. Ponieważ nie można skompensować arkusza roszczeń, dopóki nie zostanie zatwierdzone potrącenie, wybierz pozycję **Anuluj**.

### <a name="detach-an-invoice-from-a-deduction"></a>Odłączanie faktury od potrącenia

Fakturę można odłączyć od potrącenia, jeśli potrącenie zostało utworzone przy użyciu polecenia **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta, i ma aktualnie dołączoną fakturę (oznacza to, że kolumna **Faktura** zawiera numer faktury), a pole **Stan roszczenia** zostało ustawione na *Otwarte*. Zadanie to może zostać ukończone, ponieważ została dołączona nieprawidłowa faktura. Faktura jest usuwana z potrącenia, a pozostałe saldo jest aktualizowane, jeśli zostało zmniejszone, gdy faktura została dołączona.

Aby odłączyć fakturę, należy wykonać poniższe kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Zaznacz pole wyboru **Oznacz** obok potrącenia, aby rozpocząć przetwarzanie.
1. W okienku akcji wybierz pozycję **Obsługa \> Odłącz fakturę**.

### <a name="approve-a-deduction"></a>Zatwierdzanie potrącenia

Można zatwierdzać potrącenia utworzone przy użyciu polecenia **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta. Można jednak zatwierdzać tylko potrącenia, w których pole **Stan oświadczenia** jest ustawione na *Otwarte*.

Aby zatwierdzić potrącenie, wykonaj następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Zaznacz pole wyboru **Oznacz** obok potrącenia, aby rozpocząć przetwarzanie.
1. W okienku akcji wybierz pozycję **Obsługa \> Zatwierdź potrącenie**.
1. W oknie dialogowym **Zatwierdzanie potrącenia** edytuj lub dodaj informacje do wartości **Uwaga** zgodnie z wymaganiami.
1. Jeśli potrącenie jest oparte na cenie, a faktura nie została do niego dołączona, wybierz grupę podatków od pozycji. Zazwyczaj grupa pozycji dla podatku jest ustawiana na fakturze. W związku z tym kod pozycji dla podatku musi być określony, gdy nie jest dołączony do faktury.
1. Kliknij przycisk **OK**.

    W tym momencie nie można wprowadzać dalszych zmian potrącenia. Jeśli opcja **Utwórz arkusz roszczeń** została ustawiona na *Nie* podczas tworzenia potrącenia, arkusz roszczeń jest tworzony i księgowany po zatwierdzeniu potrącenia. Po zatwierdzeniu potrącenia kredyt jest automatycznie tworzony i otwierany. Typ zależy od wartości **podstawy roszczenia**:

    - *Oparte na cenie* — jeśli potrącenie jest oparte na cenie, faktura niezależna jest tworzona dla konta klienta. Możesz dodać opis i zaksięgować kredyt. Następujące pola są wypełniane przez potrącenie podczas tworzenia wersji roboczej:

        - **Identyfikator potrącenia** — to pole jest dodawane do nagłówka, aby umożliwić śledzenie z powrotem do potrącenia.
        - **Konto główne** — wartość jest określana przez wartość **Konto księgowania roszczenia**, która jest ustawiona dla przyczyny potrącenia przypisanej do potrącenia.
        - **Grupy podatków dla pozycji** — wartość jest określana przez dołączoną fakturę lub przez wartość wybraną podczas zatwierdzania potrącenia.
        - **Cena jednostkowa** — wartość jest kredytem kwoty roszczenia potrącenia.
        - **Tekst faktury** — domyślnie to pole jest ustawione na wartość pola **Uwagi**.

    - *Oparte na ilości* — jeśli potrącenie jest oparte na ilości, tworzone jest otwarte zamówienie sprzedaży lub zamówienie zwrotu. Ustawienie **Utwórz zamówienie zwrotu** na stronie **[Parametry modułu rozrachunków z odbiorcami](#accounts-receivable-deductions)** określa, czy zamówienie sprzedaży lub zamówienie zwrotu jest tworzone po zatwierdzeniu potrącenia. Zostanie wyświetlona strona **Kopiowanie zamówień** i będzie filtrowana w celu wyświetlenia wierszy, w których pole **Konto faktury** jest ustawione na konto klienta dla potrącenia. Wykonaj następujące kroków:

        1. Na skróconej karcie **Faktury** sekcja **Nagłówki** zawiera faktury sprzedaży, w których wartość **konta faktury** jest zgodna z kontem odbiorcy potrącenia. Wybierz odpowiednią fakturę sprzedaży.
        1. Sekcja **Wiersze** zawiera wiersze z wybranej faktury sprzedaży. Zaznacz pole wyboru **Wybierz** przy każdym wierszu, który chcesz skopiować. Alternatywnie w sekcji **Nagłówki** zaznacz pole wyboru **Zaznacz wszystkie** dla zamówienia sprzedaży, aby zaznaczyć wszystkie jego wiersze.
        1. W razie potrzeby dostosuj wartość **Ilość** dla jednego lub więcej wierszy.

            Wszystkie wiersze wybrane do tej pory są wyświetlane na skróconej karcie **Wybrane wiersze lub nagłówek do skopiowania**.

        1. Powtarzaj poprzednie dwa kroki zgodnie z wymaganiami, aż wszystkie wymagane wiersze zostaną wyświetlone na skróconej karcie **Wybrane wiersze lub nagłówek do skopiowania**.
        1. Kliknij przycisk **OK**.

            Zostanie otwarte nowe zamówienie zwrotu, a następujące pola są ustawiane automatycznie:

            - **Identyfikator potrącenia** — to pole jest dodawane do nagłówka, aby umożliwić śledzenie z powrotem do potrącenia.
            - **Kod przyczyny zwrotu** — domyślnie to pole jest ustawione na wartość **Kod przyczyny zwrotu**, która jest ustawiona dla przyczyny potrącenia przypisanej do potrącenia.

Kwota zafakturowanego kredytu pojawia się w sekcji **Otwarte transakcje** na pulpicie potrąceń względem odpowiedniej wartości **Identyfikator potrącenia**, a jego pole **Typ oświadczenia** jest ustawione na *Inne kredyty*. Kredyt będzie dostępny do momentu rozliczenia z potrąceniem w jeden z następujących sposobów:

- Rozlicz go ręcznie, wybierając pozycję **Obsługa \> Dopasuj** w okienku akcji.
- Jest on automatycznie rozliczany przez zadanie okresowe *Rozliczanie zatwierdzonych roszczeń* (**Sprzedaż i marketing \> Zadania okresowe \> Rozlicz zatwierdzone roszczenia**).
- Jest ona rozliczany automatycznie, ponieważ opcja **Automatyczne rozliczenie** na karcie **Rozliczenie** na stronie **Parametry modułu rozrachunków z odbiorcami** jest ustawiona na *Tak*.

Aby wyświetlić kredyt utworzony po zatwierdzeniu potrącenia, można również użyć przycisku **Otwórz kredyt** w sekcji **Otwarte transakcje** na pulpicie potrąceń.

### <a name="create-a-return-order"></a>Tworzenie zamówienia zwrotu

Można tworzyć zamówienie zwroty dla potrąceń utworzone przy użyciu polecenia **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta. Jednak muszą być spełnione wszystkie następujące warunki:

- Pole **Podstawa rozliczenia** jest ustawione na *Oparte na ilości*.
- Pole **Stan roszczenia** jest ustawione jako *Otwarte*.
- Opcja **Utwórz zamówienie zwrotu** na karcie **Potrącenia** na stronie **[Parametry modułu rozrachunków z odbiorcami](#accounts-receivable-deductions)** jest ustawiona na *Tak*.
- Opcja **Utwórz zamówienie zwrotu przed zatwierdzeniem potrącenia** na karcie **Potrącenia** na stronie **[Parametry modułu rozrachunków z odbiorcami](#accounts-receivable-deductions)** jest ustawiona na *Tak*.

Aby utworzyć zamówienie zwrotu, należy wykonać następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Zaznacz pole wyboru **Oznacz** obok potrącenia, aby rozpocząć przetwarzanie.
1. W okienku akcji **Obsługa \> Utwórz zamówienie zwrotu**.
1. W oknie dialogowym **Zatwierdzanie potrącenia** edytuj lub dodaj informacje do istniejącej wartości **Uwagi** zgodnie z wymaganiami, a następnie wybierz przycisk **OK**.
1. W oknie dialogowym **Kopiowanie zamówień**, na skróconej karcie **Faktury** sekcja **Nagłówki** zawiera faktury sprzedaży, w których wartość **konta faktury** jest zgodna z kontem odbiorcy potrącenia. Wybierz odpowiednią fakturę sprzedaży.
1. Sekcja **Wiersze** zawiera wiersze z wybranej faktury sprzedaży. Zaznacz pole wyboru **Wybierz** przy każdym wierszu, który chcesz skopiować. Alternatywnie w sekcji **Nagłówki** zaznacz pole wyboru **Zaznacz wszystkie** dla zamówienia sprzedaży, aby zaznaczyć wszystkie jego wiersze.
1. W razie potrzeby dostosuj wartość **Ilość** dla jednego lub więcej wierszy.

    Wszystkie wiersze wybrane do tej pory są wyświetlane na skróconej karcie **Wybrane wiersze lub nagłówek do skopiowania**.

1. Powtarzaj poprzednie dwa kroki zgodnie z wymaganiami, aż wszystkie wymagane wiersze zostaną wyświetlone na skróconej karcie **Wybrane wiersze lub nagłówek do skopiowania**.
1. Kliknij przycisk **OK**.

    Zostanie otwarte nowe zamówienie zwrotu, a następujące pola są ustawiane automatycznie:

    - **Identyfikator potrącenia** — to pole jest dodawane do nagłówka, aby umożliwić śledzenie z powrotem do potrącenia.
    - **Kod przyczyny zwrotu** — domyślnie to pole jest ustawione na wartość **Kod przyczyny zwrotu**, która jest ustawiona dla przyczyny potrącenia przypisanej do potrącenia.

### <a name="deny-a-deduction"></a>Odmowa potrącenia

Aby odmówić zastosowania potrącenia, wykonaj następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Zaznacz pole wyboru **Oznacz** obok potrącenia, aby rozpocząć przetwarzanie.
1. W okienku akcji wybierz kolejno opcje **Obsługa \> Odmów**.
1. W oknie dialogowym **Odmowa** wybierz kod przyczyny odmowy, a następnie wybierz przycisk **OK**.
1. W polu **Pokaż** pod okienkiem akcji wybierz opcję *Zamknięte*.

    Odrzucone potrącenie zostanie wyświetlone na karcie **Potrącenia**, a pole **Pozostała kwota** dla potrącenia będzie ustawione na *0,00*.

    Dla potrąceń utworzonych przy użyciu polecenia **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta wystąpią następujące zdarzenia:

    - Na karcie **Odwołania** aktualizowane są pola w sekcji **Odmowa**.
    - Jeśli wybrano utworzenie arkusza roszczeń podczas tworzenia potrącenia, a faktura została dołączona do potrącenia, które zmniejszyło saldo faktury, faktura jest odłączana, a pozostałe saldo wcześniej dołączonej faktury jest zwiększane o kwotę odrzuconego roszczenia.
    - Pole **Stan** potrącenia jest ustawione na *Zamknięte*.
    - Pole **Stan roszczenia** dla potrącenia jest ustawione na *Odrzucone*.

Aby wycofać odmowę, wykonaj następujące kroki.

1. Na karcie **Potrącenia** wybierz potrącenie z odmową.
1. W okienku akcji wybierz pozycję **Wycofaj odmowę**.

    Dla potrąceń utworzonych przy użyciu polecenia **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta wystąpią następujące zdarzenia:

    - Na karcie **Odwołania** aktualizowane są pola w sekcji **Odmowa**.
    - Pole **Stan** potrącenia jest ustawione na *Otwarte*.
    - Pole **Stan roszczenia** dla potrącenia jest ustawione na *Otwarte*.

### <a name="write-off-a-deduction"></a>Odpisywanie potrącenia

Aby odpisać potrącenie, wykonaj następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Zaznacz pole wyboru **Oznacz** obok potrącenia, aby rozpocząć przetwarzanie.
1. W okienku akcji wybierz kolejno opcje **Obsługa \> Odpisz**.
1. W oknie dialogowym **Odpis** wybierz kod przyczyny odpisu, a następnie wybierz przycisk **OK**.
1. W polu **Pokaż** wybierz opcję *Zamknięte*.

    Odpisane potrącenie zostanie wyświetlone na karcie **Potrącenia**, a pole **Pozostała kwota** dla potrącenia będzie ustawione na *0,00*.

    Dla potrąceń utworzonych przy użyciu polecenia **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta wystąpią następujące zdarzenia:

    - Na karcie **Odwołania** aktualizowane są pola w sekcji **Odpis**.
    - Jeśli arkusz roszczeń został utworzony podczas tworzenia potrącenia, arkusz ten jest księgowany z kodem przyczyny odpisu potrącenia. Ten wpis można wyświetlić na karcie **Zdarzenia potrącenia**, gdzie wartość **Typ aktualizacji** to *Odpis*.
    - Pole **Stan** potrącenia jest ustawione na *Zamknięte*
    - Pole **Stan roszczenia** dla potrącenia jest ustawione na *Odpis*.

Aby wycofać odpis, wykonaj następujące kroki.

1. Na karcie **Potrącenia** wybierz potrącenie z odmową.
1. W okienku akcji wybierz opcję **Wycofaj odpis**.

    Dla potrąceń utworzonych przy użyciu polecenia **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta wystąpią następujące zdarzenia:

    - Na karcie **Odwołania** aktualizowane są pola w sekcji **Odpis**.
    - Jeśli arkusz roszczeń został utworzony podczas tworzenia potrącenia, arkusz ten jest księgowany z kodem przyczyny odpisu potrącenia. Ten wpis można wyświetlić na karcie **Zdarzenia potrącenia**, gdzie wartość **Typ aktualizacji** to *Wycofaj odpis*.
    - Pole **Stan** potrącenia jest ustawione na *Otwarte*.
    - Pole **Stan roszczenia** dla potrącenia jest ustawione na *Otwarte*.

## <a name="credits-created-outside-the-approve-deduction-process"></a><a name="credits-outside-approval"></a>Kredyty utworzone poza procesem zatwierdzania potrącenia

Ta sekcja dotyczy tylko potrąceń utworzonych przy użyciu polecenia **Nowe potrącenie** na pulpicie potrąceń, w rozliczeniu klienta lub na stronie klienta.

Różni użytkownicy mogli już utworzyć fakturę niezależną, zamówienie zwrotu lub ujemne zamówienie sprzedaży dla roszczenia klienta poza procesem **zatwierdzania potrącenia**. Po zatwierdzeniu istniejącego potrącenia na pulpicie potrąceń system automatycznie tworzy inną fakturę niezależną, zamówienie zwrotu lub ujemne zamówienie sprzedaży. W tej sekcji opisano sposób dołączania istniejących kredytów do potrącenia przed zatwierdzeniem potrącenia, aby zapobiec duplikowaniu kredytów.

### <a name="attach-a-credit-to-deduction"></a>Dołączanie kredytu do potrącenia

W tej sekcji opisano, jak można dołączyć kredyt do potrącenia z kredytu.

Po dołączeniu kredytu do potrącenia można go wyświetlić przy użyciu przycisku **Otwórz kredyt** na pasku narzędzi w sekcji **Otwarte transakcje** na pulpicie potrąceń.

Kwota kredytu zafakturowanego po zatwierdzeniu potrącenia pojawia się w sekcji **Otwarte transakcje** na pulpicie potrąceń względem odpowiedniej wartości **Identyfikator potrącenia**, a jego pole **Typ oświadczenia** jest ustawione na *Inne kredyty*.

#### <a name="attach-a-free-text-invoice-to-a-deduction"></a>Dołączanie faktury niezależnej do potrącenia

Aby dołączyć fakturę niezależną do potrącenia, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Faktury \> Wszystkie faktury niezależne**.
1. Wybierz odpowiednią fakturę.
1. W okienku akcji na karcie **Faktura** wybierz opcję **Dołącz kredyt do potrącenia**. Ten przycisk jest dostępny tylko wtedy, gdy pole **Identyfikator potrącenia** dla faktury niezależnej jest puste. Puste pole wskazuje, że faktura niezależna nie jest jeszcze dołączona do potrącenia.
1. Na stronie **Dołączanie kredytu do potrącenia** można wybrać *jedno* potrącenie. Można wybrać wyłącznie otwarte potrącenia *oparte na cenie*.
1. Kliknij przycisk **OK**. Pole **Identyfikator potrącenia** jest ustawione na nagłówek faktury niezależnej.

#### <a name="attach-a-return-order-to-a-deduction"></a>Dołączanie zamówienia zwrotu do potrącenia

Aby dołączyć zamówienie zwrotu do potrącenia, wykonaj następujące kroki.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia zwrotu**.
1. Wybierz odpowiedni numer autoryzacji otrzymanego lub otwartego zwrotu towaru (RMA).
1. W okienku akcji na karcie **Zamówienie zwrotu** wybierz opcję **Dołącz kredyt do potrącenia**. Ten przycisk jest dostępny tylko wtedy, gdy pole **Identyfikator potrącenia** dla zamówienia zwrotu jest puste. Puste pole wskazuje, że zamówienie zwrotu nie jest jeszcze dołączone do potrącenia.
1. Na stronie **Dołączanie kredytu do potrącenia** można wybrać *jedno* potrącenie. Można wybrać wyłącznie otwarte potrącenia *oparte na ilości*.
1. Kliknij przycisk **OK**. Pole **Identyfikator potrącenia** jest ustawione na nagłówek zamówienia zwrotu.

#### <a name="attach-a-sales-order-to-a-deduction"></a>Dołączanie zamówienia sprzedaży do potrącenia

Aby dołączyć zamówienie sprzedaży do potrącenia, wykonaj następujące kroki.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży**.
1. Wybierz odpowiednie otwarte, dostarczone lub zafakturowane zamówienie sprzedaży.
1. W okienku akcji na karcie **Faktura** wybierz opcję **Dołącz kredyt do potrącenia**. Ten przycisk jest dostępny tylko wtedy, gdy pole **Identyfikator potrącenia** dla zamówienia sprzedaży jest puste. Puste pole wskazuje, że zamówienie sprzedaży nie jest jeszcze dołączone do potrącenia.
1. Na stronie **Dołączanie potrącenia** można wybrać *jedno* potrącenie. Można wybrać wyłącznie otwarte potrącenia *oparte na ilości*.
1. Kliknij przycisk **OK**. Pole **Identyfikator potrącenia** jest ustawione na nagłówek zamówienia sprzedaży.

#### <a name="detach-a-deduction-from-a-credit"></a>Odłączanie potrącenia od kredytu

Jeśli niepoprawne potrącenie zostało dołączone, można odłączyć je od kredytu. Jednak muszą być spełnione wszystkie następujące warunki:

- Do potrącenia jest dołączony kredyt.
- Pole **Stan roszczenia** jest ustawione jako *Otwarte*.

Aby odłączyć potrącenie od kredytu, wykonaj jedną z następujących czynności, w zależności od typu kredytu:

- **Faktury niezależne:** na stronie **Wszystkie faktury niezależne** wybierz fakturę. Następnie w okienku akcji na karcie **Faktura** wybierz opcję **Odłącz kredyt od potrącenia**.
- **Zamówienia zwrotu:** na stronie **Wszystkie zamówienia zwrotu**. Następnie w okienku akcji na karcie **Zamówienie zwrotu** wybierz opcję **Odłącz kredyt od potrącenia**.
- **Zamówienia sprzedaży:** na stronie **Wszystkie zamówienia sprzedaży**. Następnie w okienku akcji na karcie **Faktura** wybierz opcję **Odłącz kredyt od potrącenia**.

### <a name="attach-a-deduction-to-a-credit"></a>Dołączanie potrącenia do wpisu po stronie kredytowej

W tej sekcji opisano, jak można dołączyć potrącenie do kredytu z potrącenia.

#### <a name="attach-a-deduction-to-a-free-text-return-order-or-sales-order-credit"></a>Dołączanie potrącenia do faktury niezależnej, zamówienia zwrotu lub kredytu zamówienia sprzedaży

Aby dołączyć potrącenie do faktury niezależnej, zamówienia zwrotu lub kredytu zamówienia sprzedaży, wykonaj następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Wybierz odpowiednie otwarte potrącenie.
1. W okienku akcji wybierz pozycję **Obsługa \> Dołącz potrącenie do kredytu**. Ten przycisk jest dostępny tylko wtedy, gdy pole **Stan roszczenia** jest ustawione na *Otwarte*.
1. Na stronie **Dołączanie kredytu** można wybrać *jeden* kredyt. Typ kredytów, który jest wyświetlany, zależy od wartości **podstawa odliczenia**:

    - *Oparte na cenie* — strona zawiera faktury niezależne dla konta klienta, gdzie pole **Identyfikator potrącenia** jest puste. Zapotrzebowania klientów są również wyświetlane, ponieważ faktura niezależna może być niezaksięgowana. W związku z tym może nie mieć numeru, do którego można się odwoływać.
    - *Oparte na ilości* — typ kredytów, który jest wyświetlany zależy od ustawienia opcji **Utwórz zamówienie zwrotu** na stronie **[Parametry modułu rozrachunków z odbiorcami](#accounts-receivable-deductions)**:

        - *Tak* — strona zawiera zamówienia zwrotu dla konta klienta, gdzie pole **Identyfikator potrącenia** jest puste.
        - *Nie* — strona zawiera zamówienia sprzedaży dla konta klienta, gdzie pole **Identyfikator potrącenia** jest puste.

1. Kliknij przycisk **OK**. Pole **Identyfikator potrącenia** jest ustawione na nagłówek kredytu.

Po dołączeniu kredytu do potrącenia można go wyświetlić przy użyciu przycisku **Otwórz kredyt** na pasku narzędzi w sekcji **Otwarte transakcje** na pulpicie potrąceń.

Kwota kredytu zafakturowanego po zatwierdzeniu potrącenia pojawia się w sekcji **Otwarte transakcje** na pulpicie potrąceń względem odpowiedniej wartości **Identyfikator potrącenia**, a jego pole **Typ oświadczenia** jest ustawione na *Inne kredyty*.

#### <a name="detach-a-credit-from-the-deduction"></a>Odłączanie kredytu od potrącenia

Jeśli niepoprawny kredyt został dołączony, można odłączyć go od potrącenia. W okienku akcji w grupie **Obsługa** wybierz opcję **Odłącz potrącenie od kredytu**. Wartość **Identyfikator potrącenia** jest usuwana z kredytu.

Przycisk **Odłącz potrącenie od kredytu** jest dostępny tylko wtedy, gdy spełnione są następujące warunki:

- Do potrącenia jest dołączony kredyt.
- Pole **Stan roszczenia** jest ustawione jako *Otwarte*.

## <a name="create-a-one-time-promotion"></a>Tworzenie promocji jednorazowej

Czasami nie ma zatwierdzonego rabatu, który można dopasować do potrącenia. W takim przypadku można użyć funkcji *promocji jednorazowej*, aby uzgodnić potrącenie odpisu handlowego, który jest skojarzony z odbiorcą. Funkcja *promocji jednorazowej* tworzy nową umowę dotyczącą odpisu handlowego i zdarzenie promocyjne typu ryczałt. Następnie dopasowuje ryczałt do potrącenia i wykonuje wszystkie księgowania, które są wymagane do zamknięcia potrącenia.

Ta funkcja jest przydatna w przypadku korzystania z odpisów handlowych. Aby uzyskać więcej informacji na temat odpisów handlowych, zobacz [Zarządzanie odpisami handlowymi](../sales-marketing/trade-allowance.md).

Należy najpierw skonfigurować szablon, którego można użyć do tworzenia nowej umowy dotyczącej odpisu handlowego. Aby skonfigurować szablon, należy wykonać następujące czynności.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Szablony**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polach wprowadź informacje, które mają być wyświetlane w umowach tworzonych na podstawie szablonu.
1. Na skróconej karcie **Klienci** w polu **Hierarchia** wybierz poziom hierarchii.
1. Na liście hierarchii wybierz klienta, który ma niedopasowane potrącenie, a następnie wybierz przycisk strzałki w prawo (**\>**). Klient zostanie dodany do listy **klientów umów dotyczących odpisów handlowych**.
1. Ustaw pozostałe pola zgodnie z wymaganiami, a następnie zamknij stronę.
1. Przejdź do pozycji **Sprzedaż i marketing \> Konfiguracja \> Odpis handlowy \> Parametry zarządzania odpisami handlowymi**.
1. Na karcie **Przegląd** w polu **Szablon promocji jednorazowej** wybierz nazwę szablonu, który ma być używany do tworzenia promocji jednorazowych.

Następnie można utworzyć promocję jednorazową na pulpicie potrąceń. Aby utworzyć promocję jednorazową, wykonaj następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. Zaznacz pole wyboru **Oznacz** obok potrącenia, aby rozpocząć przetwarzanie.
1. W okienku akcji wybierz pozycję **Obsługa \> Rozlicz potrącenie jako promocję jednorazową**.
1. W oknie dialogowym **Promocja jednorazowa** wykonaj następujące czynności, aby skojarzyć potrącenie z co najmniej jednym funduszem:

    1. Wybierz pozycję **Nowy**, a następnie w polu **Identyfikator funduszu** wybierz odpowiedni identyfikator. Powtórz ten krok, aby dodać dowolną liczbę funduszy, o ile zachodzi taka potrzeba.
    1. W polu **Procent** obok każdego identyfikatora funduszu wprowadź wartość procentową potrącenia do przypisania dla funduszu. Kwoty, które zostały wprowadzone w polach **Procent** muszą mieć w sumie wartość 100 procent.

1. Kliknij przycisk **OK**. System tworzy nową umowę dotyczącą odpisu handlowego, posiadającą zdarzenie promocyjne typu ryczałt i uzgadnia ryczałt z potrąceniem.

## <a name="do-a-mass-update-of-deductions"></a>Wykonywanie grupowej aktualizacji potrąceń

Jeśli musisz wprowadzić tę samą zmianę dla wielu potrąceń, można zaznaczyć te potrącenia i wykonać grupową aktualizację ich pól.

Aby przeprowadzić grupową aktualizację, wykonaj następujące kroki.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrąceń**.
1. W polu **Pokaż** poniżej okienka akcji wybierz typ potrąceń do wyświetlenia.
1. Zaznacz pole wyboru obok każdego potrącenia do aktualizacji. Następnie w okienku akcji wybierz pozycję **Obsługa \> Aktualizacja grupowa**.
1. Okno dialogowe **Aktualizacja grupowa** zawiera wybrane potrącenia. Zaktualizuj pola zgodnie z wymaganiami, a następnie wybierz przycisk **OK**, aby zaakceptować zmiany.
