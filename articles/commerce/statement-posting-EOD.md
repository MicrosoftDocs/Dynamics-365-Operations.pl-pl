---
title: Ulepszenia funkcji księgowania zestawień
description: W tym artykule opisano ulepszenia, które zostały wprowadzone w funkcji księgowania zestawień.
author: analpert
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2018-04-30
ms.openlocfilehash: a7f25a7cc1e214b5c08013055126728b2ad10f3f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886913"
---
# <a name="improvements-to-statement-posting-functionality"></a>Ulepszenia funkcji księgowania zestawień

[!include [banner](includes/banner.md)]

W tym artykule opisano pierwszy zestaw ulepszeń, które zostały wprowadzone w funkcji księgowania zestawień. Te ulepszenia są dostępne w programie Microsoft Dynamics 365 for Finance and Operations 7.3.2.

## <a name="activation"></a>Aktywacja

Domyślnie podczas instalowania programu Finanse i Działania 7.3.2 jest w nim konfigurowane używanie starszej funkcji księgowania zestawień. Aby włączyć ulepszoną funkcję księgowania zestawień, należy wyłączyć dla niej klucz konfiguracji.

- Wybierz kolejno opcje **Administrowanie systemem** \> **Ustawienia** \> **Konfiguracja licencji**, a następnie w węźle **Retail i Commerce** wyczyść pole wyboru **Zestawienia (starsze)**, po czym zaznacz pole wyboru **Zestawienia**.

Po włączeniu nowego klucza konfiguracji **Zestawienia** jest dostępny nowy element menu o nazwie **Zestawienia**. Ten element menu umożliwia ręczne tworzenie, obliczanie i księgowanie zestawień. Każde zestawienie, które powoduje błąd podczas używania procesu księgowania wsadowego, będzie również dostępne w tym elemencie menu. (Gdy jest włączony klucz konfiguracji **Zestawienia (starsze)**, ten element menu nosi nazwę **Otwórz zestawienia**.)

Commerce zawiera następujące mechanizmy sprawdzania poprawności, które dotyczą tych kluczy konfiguracji:

- Oba klucze konfiguracji nie mogą być włączone w tym samym czasie.
- Ten sam klucz konfiguracji musi być używany do wszystkich operacji wykonywanych na danym zestawieniu podczas jego całego cyklu (tworzenie, obliczanie, czyszczenie, księgowanie itd.). Na przykład nie można utworzyć i obliczyć zestawienia przy włączonym kluczu konfiguracji **Zestawienia (starsze)**, a następnie próbować zaksięgować to samo zestawienie przy włączonym kluczu konfiguracji **Zestawienia** .

> [!NOTE]
> Zalecamy, aby używać klucza konfiguracji **Zestawienia** zapewniającego dostęp do ulepszonej funkcji księgowania zestawień, chyba że istnieją istotne powody do używania klucza konfiguracji **Zestawienia (starsze)**. Microsoft będzie nadal inwestować w ulepszoną funkcję księgowania zestawień, dlatego ważne jest, aby użytkownicy jak najwcześniej zaczęli się z nią oswajać. Starsza funkcja księgowania zestawień będzie wycofywana, począwszy od wersji 8.0.

## <a name="setup"></a>Konfiguracja

W ramach ulepszania funkcji księgowania zestawień wprowadzono trzy nowe parametry na skróconej karcie **Zestawienie** dostępnej na karcie **Księgowanie** na stronie **Parametry rozwiązania Commerce**:

- **Wyłącz czyszczenie wierszy zestawienia** — Ta opcja ma zastosowanie tylko do starszej funkcji księgowania zestawień. Zalecamy ustawienie w niej wartości **Nie**, aby uniemożliwić użytkownikom czyszczenie zestawień będących w stanie częściowego zaksięgowania. Wyczyszczenie zestawień w stanie częściowego zaksięgowania powoduje uszkodzenie danych. Należy ustawić w tej opcji wartość **Tak** tylko w wyjątkowych okolicznościach.
- **Rezerwuj zapasy podczas obliczania** — zalecamy, aby do rezerwowania zapasów używać zadania wsadowego **Księgowanie zapasu**, a w tej opcji ustawić wartość **Nie**. Gdy w tej opcji zostanie ustawiona wartość **Nie**, ulepszona funkcja księgowania zestawień nie próbuje utworzyć wpisów rezerwacji zapasów podczas obliczania (jeśli wpisy nie zostały jeszcze utworzone za pomocą zadania wsadowego **Księgowanie zapasu**). Zamiast tego funkcja tworzy wpisy rezerwacji zapasów tylko podczas księgowania. Ta implementacja została wprowadzona specjalnie w związku z faktem, że okno czasowe między procesem obliczania a procesem księgowania jest zazwyczaj bardzo krótkie. Jednak jeśli chcesz rezerwować zapasy podczas obliczania, ustaw w tej opcji wartość **Tak**.

    Starsza funkcja księgowania zestawień zawsze rezerwuje zapasy w trakcie procesu obliczania zestawienia (jeżeli rezerwacja nie została jeszcze dokonana za pomocą zadania wsadowego **Księgowanie zapasu**), niezależnie od ustawienia tej opcji.

- **Wymagane wyłączenie zliczania** — Jeśli ta opcja jest ustawiona na **Tak**, proces księgowania zestawienia jest kontynuowany, nawet gdy różnica między kwotą obliczoną a kwotą transakcji wykracza poza próg zdefiniowany na skróconej karcie **Zestawienie** dla sklepów.

> [!NOTE]
> Od wersji 10.0.14 Commerce, gdy włączona jest opcja **Zestawienia detaliczne – zasilanie cykliczne**, zadanie wsadowe **Księgowanie zapasów** nie ma już zastosowania i nie może być uruchomione.

## <a name="processing"></a>Przetwarzanie

Zestawienia mogą być obliczane i księgowane wsadowo za pomocą elementów menu **Oblicz zestawienia w partii** i **Zaksięguj zestawienia w partii**. Alternatywnie zestawienia można ręcznie obliczać i księgować przy użyciu elementu menu **Zestawienia** dostępnego w ulepszonej funkcji księgowania zestawień.

Proces oraz etapy obliczania i księgowania zestawień wsadowo są takie same, jak w starszej funkcji księgowania zestawień. Jednak wprowadzono znaczne udoskonalenia w bazowym przetwarzaniu zestawień w systemach zaplecza. Te ulepszenia zwiększają odporność procesu na ewentualne problemy oraz oferują lepszy wgląd w stany i informacje o błędach. Dzięki temu użytkownicy mogą usuwać główne przyczyny błędów, a następnie kontynuować proces księgowania, nie powodując uszkodzenia danych i unikając konieczności stosowania poprawek danych.

W poniższych sekcjach opisano niektóre najważniejsze ulepszenia funkcji księgowania zestawień, które są wyświetlane interfejsie użytkownika dla zestawień i zaksięgowanych zestawień.

### <a name="status-details"></a>Szczegóły stanu

We wszystkich procesach obliczania i księgowania wprowadzono nowy model stanów w procedurze księgowania zestawień.

W poniższej tabeli opisano różne stany i ich kolejność w procesie obliczania.

| Nr kolejny stanu | Stanowy      | opis |
|-------------|------------|-------------|
| 1           | Rozpoczęte    | Zestawienie zostało utworzone i jest gotowe do obliczenia. |
| 2           | Zaznaczone     | Transakcje będące w zakresie zestawienia są identyfikowane na podstawie parametrów zestawienia i oznaczone identyfikatorem zestawienia. |
| 3           | Obliczony | Wiersze zestawienia są obliczane i wyświetlane. |

W poniższej tabeli opisano różne stany i ich kolejność w procesie księgowania.

| Nr kolejny stanu | Stanowy                   | opis |
|-------------|-------------------------|-------------|
| 1           | Sprawdzone                 | System dokonuje wielu kontroli poprawności dotyczących parametrów (na przykład opłaty za złożenie dyspozycji) oraz zestawienia i jego wierszy (na przykład różnicy między kwotą obliczoną a kwotą transakcji). |
| 2           | Zagregowane              | Transakcje sprzedaży dla odbiorców nazwanych i nienazwanych są agregowane na podstawie konfiguracji. Każda zagregowana transakcja jest ostatecznie konwertowana na zamówienie sprzedaży. |
| 3           | Utworzono zamówienie odbiorcy  | Na podstawie zagregowanej transakcji w systemie są tworzone zamówienia sprzedaży. |
| 4           | Zaksięgowano zamówienie odbiorcy | Zamówienia sprzedaży są księgowane. |
| 5           | Zaksięgowano rabaty        | Na podstawie konfiguracji są księgowane arkusze rababów okresowych. |
| 6           | Zaksięgowano dochody/wydatki   | Transakcje przychodów/wydatków są księgowane jako załączniki. |
| 7           | Połączono załączniki         | Są tworzone arkusze płatności i łączone z odpowiednią fakturą. |
| 8           | Zaksięgowano płatności         | Arkusze płatności są księgowane. |
| 9           | Zaksięgowano karty upominkowe       | Transakcje kartami upominkowymi są księgowane jako załączniki. |
| 10          | Opublikowano                  | Zestawienie jest oznaczane jako zaksięgowane. |

Każdy stan w tabelach powyżej ma charakter niezależny i między stanami jest budowana hierarchiczna zależność. Ta zależność przechodzi od góry do dołu. Jeśli system napotka jakiekolwiek błędy podczas przetwarzania stanu, stan zestawienia wraca do poprzedniego stanu. Wszystkie kolejne próby uruchomienia procesu są wznawiane od stanu, w którym wystąpił błąd. Ta metoda ma następujące zalety:

- Użytkownik ma pełen wgląd w stan, w którym wystąpił błąd.
- Unika się uszkodzenia danych. Na przykład w starszej funkcji księgowania zestawień były przypadki, gdy niektóre zamówienia sprzedaży były fakturowane, ale inne pozostawały otwarte. Były również przypadki, że niektóre arkusze płatności nie miały odpowiadającej im faktury na potrzeby rozliczenia, ponieważ podczas księgowania faktury występował błąd.
- Użytkownicy mogą zobaczyć bieżący stan zestawienia, naciskając przycisk **Szczegóły stanu** w grupie **Szczegóły wykonania** dla zestawienia. Strona Szczegóły stanu ma trzy części:

    - Pierwsza sekcja przedstawia bieżący stan zestawienia wraz z kodem błędu i szczegółowym komunikatem o błędzie, jeśli wystąpił błąd.
    - Druga sekcja przedstawia różne stany procesu obliczania. Podpowiedzi wizualne wskazują stany, które zostały pomyślnie osiągnięte, stany, których nie można osiągnąć z powodu błędów, oraz stany, których jeszcze nie próbowano osiągnąć.
    - Trzecia sekcja przedstawia różne stany procesu księgowania. Podpowiedzi wizualne wskazują stany, które zostały pomyślnie osiągnięte, stany, których nie można osiągnąć z powodu błędów, oraz stany, których jeszcze nie próbowano osiągnąć.

Ponadto nagłówek sekcji drugiej i trzeciej pokazuje całościowy stan odnośnego procesu.

### <a name="event-logs"></a>Dzienniki zdarzeń

Zestawienie przechodzi przez różne operacje (na przykład tworzenia, obliczania, czyszczenia i księgowania), a w trakcie cyklu życia zestawienia może być wywoływanych wiele wystąpień tej samej operacji. Na przykład po utworzeniu i obliczeniu zestawienia użytkownik może wyczyścić zestawienie i obliczyć je ponownie. Przycisk **Dzienniki zdarzeń** w grupie **Szczegóły wykonania** dla zestawienia wyświetla kompletny dziennik inspekcji wszystkich operacji, które zostały wywołane w sprawozdaniu, wraz z informacjami o tym, kiedy te operacje zostały wywołane.

### <a name="aggregated-transactions"></a>Zagregowane transakcje

W procesie księgowania transakcje kasowe i gotówkowe są agregowane według klienta i produktu. W związku z tym jest zmniejszana liczba utworzonych zamówień sprzedaży i wierszy. Zagregowane transakcje są przechowywane w systemie i używane do tworzenia zamówień sprzedaży. Każda zagregowana transakcja tworzy jedno odnośne zamówienie sprzedaży w systemie. 

Jeśli zestawienie nie zostało w pełni zaksięgowany, można wyświetlić agregowane transakcje w zestawieniu. W okienku akcji, na karcie **Zestawienie**, w grupie **Szczegóły wykonania** wybierz pozycję **Agregowane transakcje**.

![Przycisk agregowanych transakcji dla zestawienia, które nie zostało w pełni zaksięgowane.](media/aggregated-transactions.png)

W przypadku zaksięgowanych zestawień można wyświetlić agregowane transakcje na stronie **Zaksięgowane zestawienia**. W okienku akcji wybierz opcję **Zapytania**, a następnie wybierz opcję **Zagregowane transakcje**.

![Polecenie zagregowanych transakcji dla zaksięgowanych wyciągów.](media/aggregated-transactions-posted-statements.png)

Skrócona karta **Szczegóły zamówienia sprzedaży** w oknie zagregowanej transakcji pokazuje następujące informacje:

- **Identyfikator rekordu** — Identyfikator rekordu zagregowanej transakcji.
- **Numer zestawienia** — Zestawienie, do którego należy zagregowana transakcja.
- **Data** — Dzień, w którym utworzono zagregowaną transakcję.
- **Identyfikator sprzedaży** — Identyfikator zamówienia sprzedaży wstawiany po utworzeniu zamówienia sprzedaży na podstawie zagregowanej transakcji. Jeśli to pole jest puste, odnośne zamówienie sprzedaży nie zostało jeszcze utworzone.
- **Liczba zagregowanych wierszy** — Łączna liczba wierszy zagregowanej transakcji i zamówienia sprzedaży.
- **Stan** — Ostatni stan zagregowanej transakcji.
- **Identyfikator faktury** — Identyfikator faktury sprzedaży wstawiany po zafakturowaniu zamówienia sprzedaży powiązanego ze zagregowaną transakcją. Jeśli to pole jest puste, faktura za zamówienie sprzedaży nie została jeszcze zaksięgowana.
- **Kod błędu** — to pole jest ustawiane, jeśli agregacja znajduje się w stanie błędu.
- **Komunikat o błędzie** — to pole jest ustawiane, jeśli agregacja znajduje się w stanie błędu. Pokazuje szczegółowe informacje o tym, co spowodowało niepowodzenie procesu. Informacje zawarte w kodzie błędu mogą zostać podane w celu rozwiązania problemu. Następnie można ponownie ręcznie uruchomić proces. W zależności od typu rozwiązania może być konieczne usunięcie i przetworzenie zagregowanej sprzedaży w nowym zestawieniu.

![Pola na skróconej karcie szczegółów zamówienia sprzedaży zagregowanej transakcji.](media/aggregated-transactions-error-message-view.png)

Skrócona karta **Szczegóły transakcji** w oknie zagregowanej transakcji pokazuje wszystkie transakcje pobrane do zagregowanej transakcji. Zagregowane wiersze w zagregowanej transakcji pokazują wszystkie zagregowane rekordy z transakcji. W zagregowanych wierszach są również wyświetlane szczegóły takie jak towar, wariant, ilość, cena, kwota netto, jednostka i magazyn. Zasadniczo każdy zagregowany wiersz odpowiada jednemu wierszowi zamówienia sprzedaży.

![Skrócona karta szczegółów zagregowanej transakcji.](media/aggregated-transactions-sales-details.png)

W pewnych sytuacjach zagregowane transakcje mogą nie księgować skonsolidowanego zamówienia sprzedaży. W takich sytuacjach kod błędu jest skojarzony ze stanem zestawienia. Aby wyświetlić tylko zagregowane transakcje, które mają błędy, można włączyć filtr **Pokaż tylko błędy** w widoku zagregowanych transakcji, zaznaczając to pole wyboru. Włączenie tego filtru umożliwia ograniczenie wyników do zagregowanych transakcji, które mają błędy wymagające rozwiązania. Aby uzyskać informacje na temat usuwania tych błędów, zobacz temat [Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy](edit-order-trans.md).

![Pole wyboru filtru Pokaż tylko błędy w widoku zagregowanych transakcji.](media/aggregated-transactions-failure-view.png)

Na stronie **Zagregowane transakcje** można pobrać kod źródłowy XML konkretnej zagregowanej transakcji, wybierając pozycję **Eksportuj dane agregacji**. Plik XML można przeglądać w dowolnym formacie XML, aby wyświetlić szczegóły danych, które wymagają utworzenia i zaksięgowania zamówienia sprzedaży. Funkcja pobierania kodu XML zagregowanych transakcji nie jest dostępna dla zestawień, które zostały już zaksięgowane.

![Przycisk Eksportuj dane agregacji na stronie Zagregowane transakcje.](media/aggregated-transactions-export.png)

Jeśli nie można poprawić tego błędu, korygując dane zamówienia sprzedaży lub dane obsługujące zamówienie sprzedaży, można użyć dostępnego przycisku **Usuń zamówienie klienta**. Aby usunąć zamówienie, zaznacz zagregowaną transakcję z błędem, a następnie wybierz pozycję **Usuń zamówienie klienta**. Zagregowana transakcja i odpowiadające jej zamówienie sprzedaży zostaną usunięte. Transakcje można teraz przeglądać za pomocą funkcji edycji i inspekcji. Można je również przetworzyć ponownie w nowym zestawieniu. Po usunięciu błędów można wznowić księgowanie zestawienia, uruchamiając funkcję księgowania zestawienia dla odpowiedniego zestawienia.

![Przycisk Usuń zamówienie klienta w widoku zagregowanych transakcji.](media/aggregated-transactions-delete-cust-order.png)

Widok zagregowanych transakcji oferuje następujące zalety:

- Użytkownik ma wgląd w zagregowane transakcje, których wykonanie nie powiodło się podczas tworzenia zamówienia sprzedaży, oraz w zamówienia sprzedaży, których przetwarzanie nie powiodło się podczas fakturowania.
- Użytkownik ma wgląd w sposób agregowania transakcji.
- Użytkownik ma kompletny dziennik inspekcji — od powstania transakcji, przez zamówienia sprzedaży, aż po faktury sprzedaży. Ten dziennik inspekcji nie był dostępny w starszej funkcji księgowania zestawień.
- Zagregowany plik XML ułatwia identyfikowanie problemów podczas tworzenia i fakturowania zamówienia sprzedaży.

> [!NOTE]
> Kiedy transakcje są łączone, członek personelu przypisany do transakcji nie jest już dostępny dla **Raportu sprzedaży wg najlepszych pracowników**, co oznacza, że **Raportu sprzedaży wg najlepszych pracowników** nie będzie pokazywał wszystkich transakcji. Nie zaleca się używania **Raportu sprzedaży wg najlepszych pracowników** używając zagregowanych transakcji.

### <a name="journal-vouchers"></a>Załączniki arkusza

Przycisk **Załączniki arkusza** w grupie **Szczegóły wykonania** dla zestawienia powoduje wyświetlenie wszystkich transakcji załącznika utworzonych dla zestawienia, które są powiązane z rabatami, kontami przychodów/wydatków, kartami upominkowymi itd.

Obecnie w programie te dane są wyświetlane tylko dla zaksięgowanych zestawień.

### <a name="payment-journals"></a>Arkusze płatności

Przycisk **Arkusze płatności** w grupie **Szczegóły wykonania** dla zestawienia pokazuje wszystkie arkusze płatności utworzone dla zestawienia.

Obecnie w programie te dane są wyświetlane tylko dla zaksięgowanych zestawień.

## <a name="other-improvements"></a>Inne ulepszenia

W funkcji księgowania zestawień wprowadzono również różne ulepszenia w systemach zaplecza widoczne dla użytkowników. Oto kilka przykładów:

- Agregacja nie bierze pod uwagę jednostek personelu, terminala ani zmiany. Ze względu na mniejszą liczbę parametrów agregacji system ma mniej wierszy zamówień sprzedaży do przetwarzania.
- Występowanie zakleszczeń w tabelach transakcji zostało ograniczone poprzez wprowadzenie dodatkowych tabel rozszerzeń oraz poprzez wykonywanie operacji wstawiania zamiast operacji aktualizacji w tabelach transakcji.
- Liczba uruchamianych zadań przetwarzania wsadowego została sparametryzowana i ograniczona. W związku z tym tę liczbę można precyzyjnie dostosować do specyfiki środowiska klienta. W starszej funkcji księgowania zestawień była tworzona nieograniczona liczba zadań wsadowych w tym samym czasie. Efektem były ogromne obciążenia przetwarzaniem i powstawanie wąskich gardeł na serwerze przetwarzania wsadowego.
- Zestawienia są skutecznie umieszczane w kolejce do przetwarzania poprzez nadawanie priorytetu zestawieniom o największej liczbie transakcji.
- Procesy wsadowe, takie jak **Oblicz zestawienia w partii** i **Zaksięguj zestawienia w partii**, w wykonywane tylko w trybie wsadowym. W starszej funkcji księgowania zestawień użytkownicy mogli wybrać opcję uruchamiania tych procesów wsadowych w trybie interakcyjnym, czyli jednowątkowym, w przeciwieństwie do procesów wsadowych, które są wielowątkowe.
- W starszej funkcji księgowania zestawień każde niepowodzenie podzadania wsadowego powodowało stan błędu całego zadania wsadowego. W ulepszonej funkcji błędy podzadań wsadowych nie powodują ustawienia stanu błędu dla całego zadania wsadowego, jeśli inne podzadania wsadowe zostały wykonane pomyślnie. Stan księgowania sesji przetwarzania wsadowego należy ocenić za pomocą strony **Zestawienia**, gdzie widać wszystkie zestawienia, które nie zostały zaksięgowane z powodu błędów.
- W starszej funkcji księgowania zestawień pierwsze wystąpienie niepowodzenia przetwarzania zestawienia powoduje niepowodzenie dla całej partii. Pozostałe zestawienia nie są przetwarzane. W ulepszonej funkcji proces przetwarzania wsadowego kontynuuje przetwarzanie wszystkich zestawień, nawet jeśli przetwarzanie niektórych zestawień kończy się niepowodzeniem. Jedną z zalet takiego rozwiązania jest to, że użytkownicy widzą dokładną liczbę zestawień zawierających błędy. W rezultacie użytkownicy nie są już skazani na pętlę ustawicznego poprawiania błędów i ponownego uruchamiania procesu księgowania zestawień do czasu, aż wszystkie zestawienia zostaną pomyślnie zaksięgowane.

## <a name="general-guidance-about-the-statement-posting-process"></a>Ogólne wytyczne dotyczące procesu księgowania zestawień

- Zalecamy, aby proces księgowania zestawień wykonywać wsadowo, ponieważ sesje przetwarzania wsadowego wykorzystują mechanizm wielowątkowości. Wielowątkowość jest niezbędna do sprawnej obsługi dużych ilości transakcji występujących zwykle podczas księgowania zestawień.
- Zalecamy, aby w grupie modeli towarów włączyć funkcję ujemnych zapasów fizycznych, dzięki czemu księgowanie będzie przebiegało płynnie. W niektórych scenariuszach zestawienia z wartościami ujemnymi mogą być księgowane tylko pod warunkiem istnienia ujemnych zapasów fizycznych. Na przykład teoretycznie jeśli w zapasach istnieje tylko jedna jednostka towaru, a dla towaru wykonano transakcję sprzedaży i transakcję zwrotu, system powinien zaksięgować transakcję, nawet jeżeli nie włączono funkcji ujemnego poziomu zapasów. Jednak ponieważ proces księgowania zestawienia pobiera transakcję sprzedaży i transakcję zwrotu w jednym zamówieniu odbiorcy, nie ma gwarancji, że wiersz sprzedaży zostanie zaksięgowany najpierw, a po nim wiersz zwrotu. W związku z tym może wystąpić błąd. Jeśli w tym scenariuszu jest włączona funkcja ujemnych zapasów, nie będzie negatywnego wpływu na księgowanie transakcji i system poprawnie odzwierciedli zapasy.
- Zalecamy, aby podczas obliczania i księgowania zestawień używać agregacji. W związku z tym zalecamy następujące ustawienia niektórych parametrów agregacji:

    - Wybierz kolejno opcje **Retail i Commerce** \> **Ustawienia central** \> **Parametry** \> **Parametry rozwiązania Commerce**. Następnie na karcie **Księgowanie** na skróconej karcie **Aktualizacja zapasów** w polu **Poziom szczegółowości** zaznacz wartość **Podsumowanie**.
    - Wybierz kolejno opcje **Retail i Commerce** \> **Ustawienia central** \> **Parametry** \> **Parametry rozwiązania Commerce**. Następnie na karcie **Księgowanie** na skróconej karcie **Agregacja** w opcji **Transakcje na załączniku** ustaw wartość **Tak**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
