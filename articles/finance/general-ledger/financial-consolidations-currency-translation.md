---
title: Omówienie konsolidacji finansowych i przeliczania walut
description: W tym artykule opisano funkcje konsolidacji finansowych i przeliczania walut dostępne w księdze głównej.
author: jinniew
ms.date: 10/07/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 1b2f5f56e757e89339c12fd41c59848b4c987a2f
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831841"
---
# <a name="financial-consolidations-and-currency-translation-overview"></a>Omówienie konsolidacji finansowych i przeliczania walut

[!include [banner](../includes/banner.md)]

W tym artykule omówiono podejście stosowane w Microsoft Dynamics 365 Finance i raportowaniu finansowym na potrzeby konsolidacji. Opisano scenariusze raportowania międzyfirmowego, agregacji, eliminacji i udziałów mniejszościowych. Wyjaśniono też sposób postępowania w sytuacjach specjalnych, takich jak scenariusze, gdzie firmy mają różne okresy obrachunkowe lub plany kont.

Ten artykuł został napisany dla użytkowników i konsultantów funkcjonalnych. Założono w nim, że czytelnicy mają ogólną wiedzę o usługach Finance i Raportowanie finansowe. Nie omówiono podstawowego konfigurowania.

> [!NOTE]
> Określenie *firma* jest używane w rozwiązaniu Finance, natomiast określenie *firma* w programie Raportowanie finansowe. Występuje również w tym artykule. Jego znaczenie na potrzeby tego artykułu jest identyczne w obu aplikacjach.

## <a name="audience"></a>Odbiorcy
Ten artykuł jest przeznaczony dla użytkowników z działów finansów i księgowości oraz konsultantów ds. aplikacji, którzy chcą używać oprogramowania finansowego i operacyjnego oraz Raportowanie finansowe do konsolidowania danych o wielu firmach i wielu walutach.

## <a name="approach"></a>Metoda
Aplikacja Finance wykorzystuje odrębną firmę do przetwarzania konsolidacji. Umożliwia to konsolidację wewnątrz jednego wystąpienia, ale oferuje opcję wprowadzania danych z innych źródeł. Proces konsolidacji musi być uruchamiany za każdym razem, gdy zostaną wprowadzone zmiany w firmach źródłowych.

Aplikacja Raportowanie finansowe może konsolidować wiele firm podczas generowania raportu. Mimo że dane są przechowywane w składnicy danych, otrzymują numery wersji i mogą być eksportowane, każda firma źródłowa jest właścicielem i kontenerem danych. Raport można uruchomić w dowolnym momencie, nawet co minutę (na przykład). Oferuje wiele dodatkowych korzyści, takich jak możliwość przechodzenia do szczegółów wszystkich firm i wymiarów.

Użytkownicy mogą używać narzędzia Konsolidacja online, Raportowanie finansowe lub ich kombinacji. Wybór zależy od potrzeb firmy i od preferencji audytorów.

## <a name="consolidations"></a>Konsolidacje
Moduł **Konsolidacja** zawiera opcje umożliwiające konsolidowanie wielu firm w trakcie procesu konsolidacji oraz importowanie lub eksportowania salda firmy. Można także skonfigurować eliminacje i księgować arkusze eliminacji.

## <a name="benefits-of-using-consolidate-online"></a>Korzyści wynikające z używania narzędzia Konsolidacja online
Klienci korzystający z modułu **Konsolidacje** mogą liczyć na szereg korzyści:

- **Dogłębność danych** — można tworzyć skonsolidowane raporty, które grupują dane rzeczywiste i budżetowe na poziomach konta i wymiaru.
- **Dynamiczne konsolidacje** — konsolidacje mogą być przetwarzane wiele razy.
- **Funkcje inspekcji** — wymiary i konta są zarządzane pod kątem możliwości analizowania i kontrolowania, a salda są tworzone według dat.
- **Przeliczanie walut** — istnieje możliwość skonfigurowania zakresów kont i kursów w celu przeliczania z waluty rozliczeniowej firmy źródłowej na walutę rozliczeniową firmy konsolidowanej.
- **Przetwarzanie eliminacji w firmie skonsolidowanej lub zawierającej wpisy eliminacji** — podczas konsolidacji eliminacje można przetwarzać i księgować jako pojedynczy proces. Alternatywnie można wygenerować propozycję oddzielnie.

## <a name="supported-consolidation-scenarios"></a>Obsługiwane scenariusze konsolidacji
Oto kilka scenariuszy konsolidacji obsługiwanych przez narzędzie Konsolidacja online:

- Konsolidacje jednopoziomowe w różnych firmach
- Konsolidacje obejmujące eliminacje
- Udział mniejszościowy (w tym scenariuszu należy używać ręcznego obliczania i wprowadzania do firmy)
- Wiele planów kont w różnych firmach
- Różne kalendarze obrachunkowe w różnych firmach
- Konsolidacje obejmujące różne waluty raportowania

## <a name="legal-entity-setup"></a>Konfiguracja firmy
Przed rozpoczęciem przetwarzania konsolidacji należy skonfigurować firmę. Konsolidację można uruchamiać dowolną potrzebną liczbę razy, a wszystkie dane zostaną przeliczone z waluty rozliczeniowej lub sprawozdawczej firmy źródłowej na walutę zdefiniowaną dla konsolidowanej firmy. Dlatego dla poniższej struktury organizacyjnej należy przeliczyć wszystkie spółki w Ameryce Północnej najpierw na dolary amerykańskie (USD), a następnie na euro (EUR), czyli walutę firmy nadrzędnej, muszą istnieć co najmniej dwie konsolidowane firmy.

![Struktura organizacyjna.](./media/organizational-structure.png "Struktura organizacyjna")

W powyższej strukturze organizacyjnej musi istnieć firma w celu skonsolidowania Ameryki Północnej, ponieważ konsolidacje zawsze odbywają się z waluty rozliczeniowej firmy źródłowej do waluty konsolidowanej firmy. W tym przykładzie jeżeli wszystkie firmy zostaną ujęte w jednym konsolidacji, filia meksykańska zostanie przeliczona z meksykańskich peso (MXN) na EUR, a nie z MXN na USD, a następnie na EUR.

Podczas tworzenia firmy można określić, czy będzie ona używana w procesach konsolidacji i eliminacji, czy tylko w jednym z nich. Na poniższej ilustracji firma jest używana w obu procesach. Należy zauważyć, że nie można księgować arkuszy dziennych w konsolidowanej firmie, ale można je zaksięgować w firmie z wpisami eliminacji. W związku z tym warto utworzyć oddzielną firmę z wpisami eliminacji.

![Firma, która jest używana zarówno do konsolidacji, jak i eliminacji.](./media/sep-elimination-company.png "Firma, która jest używana zarówno do konsolidacji, jak i eliminacji")

## <a name="main-accounts-and-consolidation-account-groups"></a>Konta główne i grupy kont konsolidacyjnych
Jednym z wyborów, jakich należy dokonać, jest sposób konsolidowania planu kont. W trakcie procesu konsolidacji możliwe są trzy opcje konsolidowania kont głównych.

Pierwszą opcją jest używanie kont głównych z firm źródłowych. W takim przypadku zostaną skonsolidowane wszystkie konta ze wszystkich firm. Na przykład jeśli kontem środków pieniężnych jest konto 100000 w firmie USMF, a konto 1100 w firmie DEMF, konsolidowana firma będzie zawierać oba konta. Każde konto będzie miało swoje odpowiednie saldo.

Druga opcja to określenie domyślnego konta konsolidacyjnego na stronie **Konta główne**. Następnie konto zostanie zamapowane na konto konsolidacyjne. Ta opcja może być przydatna, jeśli masz różne plany kont lub musisz zamapować na plan zdefiniowany przez centralę.

![Domyślne konto konsolidacji określone na stronie konta główne.](./media/main-accounts.png "Domyślne konto konsolidacji określone na stronie konta główne")

Trzecią opcją jest użycie grup kont konsolidacyjnych. Można zdefiniować dowolną potrzebną liczbę grup kont konsolidacyjnych. Następnie na stronie **Dodatkowe konta konsolidacji** można po prostu zamapować konto główne z planu kont do konta wymaganego dla tej grupy.

![Mapowanie na stronie dodatkowe konta konsolidacji.](./media/additional-consolidation-accounts.png "Mapowanie na stronie dodatkowe konta konsolidacji")

## <a name="consolidating-online"></a>Konsolidowanie online
Aby się dowiedzieć, jak wprowadzać szczegółowe informacje o konsolidacji w trybie online, zobacz [Konsolidacja finansowa online](./consolidate-online.md).

## <a name="managing-consolidation-transactions"></a>Zarządzanie transakcjami konsolidacji
Aby wyświetlić wyniki konsolidacji, możesz skorzystać z różnych opcji:

- Wygenerowanie raportu finansowego dla konsolidowanej firmy.
- Przejrzenie strony listy **Bilans próbny** w konsolidowanej firmie.
- Na stronie **Konsolidacje** na liście transakcji konsolidacji wyświetlenie utworzonych sald z podziałem na daty dla każdej firmy źródłowej i każdego okresu.

    ![Konsolidowanie transakcji na stronie konsolidacji.](./media/managing-consolidation-transactions.png "Konsolidowanie transakcji na stronie konsolidacji")

Aby ponownie uruchomić konsolidację, wystarczy wykonać przetwarzanie konsolidacji. Alternatywnie można najpierw wybrać opcję **Usuń transakcje** na stronie **Konsolidacje**.
Salda na skonsolidowanym koncie nie są dokładne, salda te można skorygować przy użyciu strony **Korekty okresu zamknięcia**.

## <a name="consolidate-with-import"></a>Konsoliduj z importem
Funkcjonalność Konsolidacja z importem działa podobnie, jak funkcjonalność Konsolidacja online. Podczas wybierania firm przejdziesz do pliku źródłowego, który zawiera dane.

## <a name="export-company-balances"></a>Eksportuj salda firmy
Funkcjonalność Eksportowanie sald firmy również działa podobnie, jak funkcjonalność Konsolidacja online. Podczas wybierania firm będziesz ustawiać ścieżkę pliku danych wyjściowych.

## <a name="elimination-rules"></a>Reguły eliminacji
W celu wyeliminowania transakcji międzyfirmowych można utworzyć regułę eliminacji. Alternatywnie można wprowadzić ręczny wpis eliminacji w firmie wyznaczonej jako firma z wpisami eliminacji. Tworząc regułę eliminacji, masz dwie możliwości określenia metody eliminacji: **Zmiana netto** i **Stałe**.

### <a name="set-up-elimination-rules"></a>Konfigurowanie reguł eliminacji
Podczas konfigurowania reguł eliminacji w usłudze Finance można utworzyć wymiar finansowy, który będzie używany specjalnie do eliminacji. Większość klientów nazywa ten wymiar finansowy **Partner handlowy** lub podobnie. Jeśli postanowisz nie używać wymiaru finansowego, to upewnij się, że masz konta główne używane tylko do transakcji międzyfirmowych.

Konfiguracja eliminacji znajduje się w obszarze **Ustawienia** w module **Konsolidacje**. Po wprowadzeniu opisu reguły trzeba wybrać firmę, w której arkusz eliminacji zostanie zaksięgowany. Powinna to być firma, która ma wybraną opcję **Użyj na potrzeby procesu eliminacji finansowej** w ustawieniach firmy.

Można ustawić daty, od kiedy i do kiedy reguła eliminacji ma obowiązywać. Jeśli reguła eliminacji ma być dostępna w procesie proponowania eliminacji, należy ustawić opcję **Aktywne** na **Tak**. Wybierz arkusz, który ma typ **Eliminacja**.

![Podstawowe właściwości reguły eliminacji.](./media/ledger-elimination-rule-journal.png "Podstawowe właściwości reguły eliminacji")

Po określeniu podstawowych właściwości kliknij przycisk **Wiersze** i zdefiniuj faktyczne reguły przetwarzania. Możliwe są dwie opcje eliminacji: eliminowanie kwoty zmiany netto lub zdefiniowanie stałej kwoty.

Wybierz konta źródłowe. Można użyć gwiazdki (\*) jako symbolu wieloznacznego. Na przykład wartość **1\**_ spowoduje używanie jako źródła danych alokacji wszystkich kont rozpoczynających się od _* 1**.

Po wybraniu kont źródłowych należy w polu **Specyfikacja konta** określić używane konto z firmy docelowej. Wybierz opcję **Źródło**, aby używać tego samego konta głównego, jak zdefiniowane w polu konta źródłowego. Jeśli wybierzesz opcję **Zdefiniowany przez użytkownika**, należy określić konto docelowe.

![Strona wiersza reguły eliminacji księgi.](./media/ledger-elimination-rule-line.png "Strona wiersza reguły eliminacji księgi")

Pole **Specyfikacja wymiaru** działa podobnie, jak pole **Specyfikacja konta**. Wybierz opcję **Źródło**, jeśli chcesz używać tych samych wymiarów w firmach docelowej i źródłowej. Jeśli wybierzesz opcję **Zdefiniowany przez użytkownika**, będzie trzeba określić wymiary w firmie docelowej, klikając opcję **Docelowe wymiary**. Następnie wybierz wymiary źródłowe i wymiary finansowe oraz wartości, które będą używane jako źródło eliminacji.

### <a name="process-elimination-transactions"></a>Przetwarzanie transakcje eliminacji
Istnieją dwa sposoby przetwarzania transakcji eliminacji: w procesie konsolidacji online lub poprzez utworzenie arkusza eliminacji i uruchomienie procesu propozycji eliminacji. W tej części koncentrujemy się na drugiej opcji.

W firmie zdefiniowanej jako firma z wpisami eliminacji wybierz opcję **Arkusz eliminacji** w module **Konsolidacje**. Po wybraniu arkusza kliknij przycisk **Wiersze**. Aby uruchomić propozycję, wybierz kolejno opcje **Propozycje** \> **Propozycje eliminacji**.

Wybierz firmę będącą źródłem skonsolidowanych danych, a następnie wybierz regułę do przetwarzania. Wprowadź daty rozpoczęcia i zakończenia, aby określić zakres dat, w którym będą wyszukiwane kwoty eliminacji. Pole **Data księgowania w księdze głównej** określa datę użytą do zaksięgowania arkusza w księdze głównej. Po kliknięciu przycisku **OK** można przejrzeć kwoty i zaksięgować arkusz.

> [!NOTE]
> W arkuszu eliminacji są wyświetlane kwoty będące wartościami kont w walucie transakcji źródłowych, a nie w walucie rozliczeniowej. Przeglądając kwoty w arkuszu eliminacji, można się z tego powodu pogubić.

Aby uzyskać więcej informacji i przykładów, zobacz [Reguły eliminacji](./elimination-rules.md).

## <a name="currency-revaluation-in-a-consolidation-company"></a>Przeszacowanie waluty w konsolidowanej firmie
Podczas konsolidowania danych z jednej waluty rozliczeniowej do innej należy wykonać przeszacowanie waluty, jeśli nastąpiła zmiana kursów wymiany, tak aby salda kont zostały poprawnie przeszacowane. Podczas pierwszej konsolidacji danych użyj karty **Przeliczanie walut**, aby wybrać początkowe kursy wymiany, które mają być używane do przeszacowania podczas procesu konsolidacji. Po wprowadzeniu nowego kursu wymiany (na przykład w kolejnym miesiącu) można przeszacować salda konta. Niezrealizowane dodatnie lub ujemne różnice kursowe zostaną wtedy zaktualizowane na podstawie nowego kursu wymiany i daty.

Aby uzyskać więcej informacji na temat przeszacowania waluty w konsolidowanej firmie zobacz [Przeszacowanie waluty w konsolidowanej firmie](currency-revaluation-consolidation-company.md).

Aby uzyskać więcej informacji na temat działania funkcji przeszacowania waluty w module **Księga główna**, zobacz [Przeszacowanie w walucie obcej dla księgi głównej](./foreign-currency-revaluation-general-ledger.md).

### <a name="additional-information"></a>Informacje dodatkowe
- Podczas przetwarzania konsolidacji są konsolidowane wszystkie warstwy księgowania.
- Arkusze eliminacji mogą być księgowane tylko do bieżącej warstwy.
- Konsolidowane są tylko salda operacyjne. W związku z tym w celu wyświetlenia sald otwarcia nadal należy wykonać proces zamknięcia na koniec roku w konsolidowanej firmie.
- Arkusz dzienny można zaksięgować w firmie z wpisami eliminacji, ale nie w konsolidowanej firmie.
- Korekty sald w konsolidowanej firmie można przeprowadzić tylko przy użyciu strony **Korekty okresu zamknięcia**. 

## <a name="benefits-of-using-financial-reporting-for-financial-consolidations-and-currency-translation-or-to-complement-consolidate-online-for-consolidated-reporting"></a>Zalety używania aplikacji Raportowanie finansowe dla konsolidacji finansowych i przeliczania walut lub w celu uzupełnienia aplikacji Konsolidacja online w sprawozdawczości skonsolidowanej
Klienci, którzy używają aplikacji Raportowanie finansowe dla konsolidacji finansowych i przeliczania walut lub w celu uzupełnienia aplikacji Konsolidacja online w sprawozdawczości skonsolidowanej, mogą liczyć na szereg korzyści:

- **Dogłębność danych** — można tworzyć skonsolidowane raporty, które grupują dane rzeczywiste i budżetowe na poziomach konta i wymiaru. W usłudze Finance te dane obejmują informacje z narzędzi kontroli budżetu i planowania budżetu.
- **Dynamiczne konsolidacje** — konsolidacje można wykonywać w dowolnej chwili i na dowolnym poziomie hierarchii organizacyjnej.
- **Kompletne funkcje inspekcji** — wszystkie wymiary, konta i szczegóły transakcji są zarządzane pod kątem możliwości analizowania i kontrolowania. Ponadto moduł Raportowanie finansowe umożliwia pełne cofanie od szczegółów do oryginalnej transakcji w każdej konsolidowanej firmie.
- **Usprawnione przeliczanie walut** — po wykonaniu jedynie minimalnych czynności konfiguracyjnych w aplikacji Finance można przeliczać każdą walutę z raportu programu Raportowanie finansowe na dowolną skonfigurowaną walutę raportowania. Ponadto można skonfigurować nieograniczoną liczbę walut raportowania.
- **Księgowanie eliminacji u źródła** — można utworzyć i wydrukować raport eliminacji w celu zweryfikowania transakcji eliminacji. Następnie wszelkie nowe eliminacje można zaksięgować jako standardowe transakcje międzyfirmowe. Można również użyć firmy z wpisami eliminacji dla każdej transakcji, której nie chcesz w swoich firmach.

## <a name="supported-consolidation-scenarios-for-financial-reporting"></a>Obsługiwane scenariusze konsolidacji dla raportowania finansowego

Oto kilka scenariuszy konsolidacji obsługiwanych przez narzędzie Raportowanie finansowe:

- Konsolidacje jednopoziomowe i wielopoziomowe w różnych firmach
- Konsolidacje wykorzystujące struktury organizacyjne tworzone na podstawie firm
- Konsolidacje obejmujące eliminacje
- Udział mniejszościowy
- Wiele planów kont w różnych firmach
- Różne kalendarze obrachunkowe w różnych firmach
- Konsolidacje obejmujące różne waluty raportowania
- Konsolidacje jednostek biznesowych

## <a name="generating-consolidated-financial-statements"></a>Generowanie skonsolidowanych sprawozdań finansowych
Aby uzyskać informacje o scenariuszach, w których mogą być tworzone skonsolidowane sprawozdania finansowe, zobacz [Generowanie skonsolidowanych sprawozdań finansowych](./generating-consolidated-financial-statements.md).

## <a name="performance-enhancement-for-large-consolidations"></a>Poprawa wydajności dla dużych konsolidacji

Środowiska, w których istnieje wiele transakcji księgi głównej, mogą być uruchamiane wolniej niż jest to optymalne. Aby rozwiązać ten problem, można skonfigurować równoległe przetwarzanie partii, w których jest używana zdefiniowana przez użytkownika liczba dat. Aby zapewnić, że rozwiązanie działa zgodnie z zamierzeniami, dodaj do konsolidacji punkt rozszerzenia, aby zwrócić kontener zakresów dat. Podstawowa implementacja powinna zawierać jeden zakres dat dla stanu rozpoczęcia i zakończenia konsolidacji. Zakresy dat w implementacji podstawowej zostaną zweryfikowane, aby upewnić się, że nie zawierają przerw lub się nie nakładają. Zakresy dat zostaną użyte do utworzenia równoległych pakietów partii dla każdej firmy.

Można dostosować liczbę zakresów dat do wymagań organizacji. Dostosowanie liczby zakresów dat pomaga uprościć testowanie i zminimalizować wpływ na istniejący kod, ponieważ nie istnieje logika alokacji. Jedyne nowe testy wymagane do sprawdzenia poprawności tworzenia pakietów partii, sprawdzania poprawności zakresów dat i testowania podzestawu zakresów dat w celu sprawdzenia, czy partie mogą zostać połączone w celu wykonania końcowego zadania przetwarzania wsadowego. 

Ta funkcja usprawnia proces konsolidacji w księdze głównej po uruchomieniu tego procesu w trybie wsadowym. Rozszerzenie usprawnia wydajność procesu konsolidacji księgi głównej, dzieląc konsolidację na wiele zadań, które mogą być przetwarzane równolegle. W domyślnej metodzie uruchamiania konsolidacji każde zadanie przetwarza warte osiem dni działania księgi głównej. Dodano jednak punkt rozszerzenia, który umożliwia dostosowanie liczbę utworzonych zadań.

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego **Zarządzanie funkcjami**, aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** księga główna
- **Nazwa funkcji:** zwiększenie wydajności dla dużych konsolidacji

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
