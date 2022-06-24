---
title: Rozwiązywanie problemów z wydajnością w konfiguracjach ER
description: W tym artykule opisano sposób wykrywania i usuwania problemów z wydajnością w konfiguracjach raportowania elektronicznego (ER).
author: NickSelin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 28ff68309bad7a6c1b6009ba03ef4b20aceb5194
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847348"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a>Rozwiązywanie problemów z wydajnością w konfiguracjach ER

W tym artykule opisano sposób wykrywania i usuwania problemów z wydajnością w [konfiguracjach](general-electronic-reporting.md#Configuration) [raportowania elektronicznego (ER)](general-electronic-reporting.md).

Zazwyczaj badanie wydajności składa się z kilku kroków.

1. [Zebranie](#collecting-data) danych.
2. Analizowanie zebranych danych.
3. Na podstawie wyników analizy użycie konfiguracji ER, aby [wprowadzić zmiany](#making-changes) lub zdecydować się na zebranie większej ilości danych.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="analyze-execution-time"></a>Analizowanie czasu wykonania

Czas wykonania może zależeć od nieprzewidywalnych czynników, takich jak inne zadania, które działają w tym samym środowisku oraz buforowanie, które wykorzystuje dane, gdy jest wywoływane po raz pierwszy. Dlatego należy kilkakrotnie powtórzyć wykonanie i pomiar.

Czasami problemy z wydajnością nie są spowodowane konfiguracją formatu ER, który jest używany do raportowania. Zamiast tego, są one powodowane przez kod X++, który jest używany do otwarcia konfiguracji formatu ER.

1. W [Centrum akcji](#infolog-time) lub [w dzienniku zdarzeń](#event-log-time) przyjrzyj się czasowi wykonania raportu.
2. Porównaj czas wykonania raportu z całkowitym czasem wykonania w scenariuszu.
3. Jeśli czas wykonania raportu jest znacznie mniejszy niż całkowity czas wykonania, należy rozważyć ilość danych przetwarzanych przez raport:

    - Jeśli raport przetwarza niewielką ilość danych, problem może dotyczyć czasu ładowania konfiguracji.
    - Jeśli raport przetwarza dużą ilość danych, problem może dotyczyć wstępnego przetwarzania X++. Użyj [Trace parsera](#analyze-trace-parser-trace) do analizy sprawy.

    W innych przypadkach zobacz następne sekcje.

4. Uruchom wiele testów, które zawierają różne ilości danych, aby określić, jak czas wykonania zależy od ilości danych.

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a>Śledzenie danych za pomocą programu Trace Parser

Przygotuj mały przykład, lub zbierz kilka śladów podczas losowo wybranych części generowania raportu.

Następnie w [Trace parserze](#trace-parser) wykonaj standardową analizę od dołu do góry i odpowiedz na następujące pytania:

- Jakie są najlepsze metody pod względem zużycia czasu?
- Jaką część całkowitego czasu wykorzystują te metody?

Odpowiedz na te same pytania dla zapytań.

Jeśli widzisz, że metody są poprzedzone „ER”, przejdź do następnej sekcji.

Jeśli widzisz, że metody lub kwerendy pochodzą z pakietu aplikacji, należy wziąć pod uwagę ogólne optymalizacje (na przykład utworzyć indeksy).

Analiza liczby połączeń. Jeśli liczba jest znacznie wyższa niż oczekiwano, należy rozważyć buforowanie odpowiednich węzłów konfiguracji.

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a>Analizowanie wywołań bazy danych

Przygotuj przykład, który ma niewielką ilość danych, dzięki czemu można zebrać [ślad ER](#electronic-reporting-traces).

Następnie otwórz śledzenie w projektancie mapowania modelu ER i spójrz na dół- strony. Odpowiedz na następujące pytania:

- Czy istnieje jakaś duplikacja kwerend? Jeśli tak, rozważ jedną z następujących poprawek:

    - [Użyj buforowania](#use-caching), jeśli uważasz, że istnieje kilka wywołań wewnątrz jednego rekordu nadrzędnego.
    - [Użyj buforowanego, sparametryzowanego pola obliczeniowego](#cached-parameterized), jeśli uważasz, że istnieją wywołania tego samego rekordu wewnątrz różnych rekordów.
    - [Użyj źródła danych **JOIN**](#use-join-datasource), jeśli trzeba odczytać do znacznej liczby różnych rekordów z bazy danych.

- Czy liczba zapytań i pobranych rekordów odpowiada ogólnej ilości danych? Na przykład jeśli dokument ma 10 wierszy, czy statystyki pokazują, że raport wyodrębnia 10 wierszy lub 1000 wierszy? Jeśli masz znaczną liczbę pobranych rekordów, należy wziąć pod uwagę jedną z następujących poprawek:

    - [Użyj funkcji **FILTER** zamiast funkcji **WHERE**](#filter) do przetwarzania danych po stronie programu Microsoft SQL Server.
    - Użyj buforowania, aby uniknąć pobierania tych samych danych.
    - [Użyj funkcji zebranych danych](#collected-data), aby uniknąć pobierania tych samych danych do podsumowania.

### <a name="analyze-perfview-traces"></a>Analizowanie śladów PerfView

[PerfView](#perfview) to narzędzie dla doświadczonych programistów. Aby uzyskać bardziej szczegółowe informacje na temat następujących kroków, zobacz [Zegar ścienny – podstawy badania czasu](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).

1. Zbieranie śledzenia przy użyciu czasu wątku.
2. Uwzględnij tylko stosy, które używają **runUnattended**, aby filtrować tylko wątek, który ma wykonanie konfiguracji. (Dodaj **runUnattended** do pola wejściowego **IncPats**.)
3. Złóż cały czas procesora, sieci i zablokowany czas.
4. Załaduj [ustawienia ER dla PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).
5. Wybierz **ER** \> **Inne ustawienia predefiniowane**.
6. Spójrz na nazwy:

    - Prawdopodobnie zobaczysz kod platformy, która zużywa najwięcej czasu.
    - Możesz dwukrotnie stuknąć (lub dwukrotnie kliknąć) i przejść w górę przez **wywoływane**.

        Jeśli znajdziesz klasy, które mają prefiks „ERExpression” i jeśli są to funkcje, które są związane z formułami, można odgadnąć nazwę funkcji na podstawie nazwy klasy i można spojrzeć na repozytorium ER, aby wyświetlić atrybuty.

### <a name="fixes"></a>Poprawki

- Jeśli widzisz, że większość czasu procesora jest zużywana przez kwerendy, spróbuj zmniejszyć liczbę zapytań:

    - [Przejrzyj śledzenie ER](#analyze-database-calls) dla zduplikowanych zapytań.
    - Zobacz, ile rekordów jest pobieranych i oceń, ile danych teoretycznie powinno być pobieranych.

- Jeśli widzisz, że większość czasu procesora jest zużywana przez funkcje, które są używane, spróbuj znaleźć miejsce w konfiguracji, które zużywa najwięcej zasobów.
- Jeśli widzisz, że większość czasu procesora jest zużywana przez funkcje zbierania danych, rozważ zastąpienie ich przez *Grupuj w/g SQL* po stronie mapowania modelu.

### <a name="collecting-data"></a><a name="collecting-data"></a>Gromadzenie danych

W zależności od środowiska istnieje kilka sposobów zbierania dostępnych danych:

- Uzyskanie całkowitego czasu pracy:

    - Z Centrum akcji
    - Z dziennika zdarzeń

- Wykonanie profilu:

    - Za pomocą narzędzi ER
    - Za pomocą analizatora śledzenia
    - Za pomocą PerfView

#### <a name="collecting-data-in-a-production-environment"></a>Gromadzenie danych w środowisku produkcyjnym

Czasami problemy mogą być powielane tylko w środowisku produkcyjnym. Istnieją następujące sposoby gromadzenia danych:

- Śledzenie danych za pomocą programu [Trace Parser](../perf-test/trace-trace-tutorial.md)
- Za pomocą śladów [wykonania ER](trace-execution-er-troubleshoot-perf.md)
- Korzystając z całkowitego czasu wykonania

#### <a name="collecting-data-in-a-development-environment"></a>Gromadzenie danych w środowisku projektowym

Oprócz narzędzi, które mogą być używane w środowisku produkcyjnym, istnieje kilka narzędzi, których można używać w środowisku programistycznym:

- Dziennik zdarzeń (Microsoft-Dynamics-ElectronicReporting). Ten dziennik może dać ci całkowity czas wykonywania.
- Typowe narzędzia .NET, takie jak PerfView.

Ponadto środowisko programistyczne zapewnia większą elastyczność eksperymentowania. Na przykład można wyłączyć części raportów, aby zobaczyć, jak wpływa to na czas wykonywania.

### <a name="tools"></a><a name="tools"></a>Narzędzia

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a>Czas wykonania w Centrum akcji

ER może pokazać czas wykonania konfiguracji w Centrum akcji. Ta opcja działa tylko dla określonego użytkownika i określonej firmy i tylko dla sesji interaktywnych. Aby udostępnić tę funkcję, wykonaj następujące kroki.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** ustaw opcję **Pokaż czas wygenerowania pliku** na **Tak**.

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a>Czas wykonania w dzienniku zdarzeń

1. Otwórz przeglądarkę zdarzeń systemu Windows.
2. W obszarze **Dzienniki aplikacji i usług** otwórz okno **Microsoft-Dynamics-ElectronicReporting/Operational**.
3. Poszukaj zdarzeń **FormatMapingRun**, gdzie **EventID=2**, ponieważ te zdarzenia zawierają informacje o upływie czasu.

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a>Śledzenie danych za pomocą programu Trace Parser 

Ponieważ ER jest zaimplementowany w X++, możesz użyć typowych narzędzi X++ do analizy wydajności. Aby uzyskać więcej informacji, zobacz temat [Śledzenie przy użyciu programu Trace Parser](../perf-test/trace-trace-tutorial.md).

To podejście ma kilka ograniczeń. Ponieważ część ER jest zaimplementowana w języku C#, nie wszystkie szczegóły będą dostępne. Można jednak wyświetlić szczegóły dotyczące użycia danych. Ponadto długie raporty mogą przekraczać limity śledzenia przechowywania.

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a>Śledzenie ER

Narzędzie ER może zbierać własne dane śledzenia oraz ma narzędzia wizualizacji i analizy tych danych. Aby uzyskać więcej informacji, zobacz [Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md).

#### <a name="perfview"></a><a name="perfview"></a>PerfView

Ponieważ zarówno X++ jak i ER są zaimplementowane na platformie .NET, można używać typowych narzędzi .NET. Można na przykład użyć bezpłatnego narzędzia [PerfView](https://github.com/Microsoft/perfview).

Można także zbierać dane z wiersza polecenia. Na przykład, poniższy skrypt Windows PowerShell zbiera czas wykonania do momentu zatrzymania wykonywania dowolnego formatu na maszynie.

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

To podejście ma kilka ograniczeń. Musisz mieć dostęp administracyjny do maszyny. Dodatkowo, musisz być doświadczonym programistą, ponieważ krzywa uczenia się jest bardzo stroma.

### <a name="making-changes"></a><a name="making-changes"></a>Dokonywanie zmian

#### <a name="use-caching"></a><a name="use-caching"></a>Użyj buforowania

Chociaż buforowanie zmniejsza ilość czasu, który jest wymagany do ponownego pobrania danych, kosztuje pamięć. Używaj buforowania w przypadkach, gdy ilość pobieranych danych nie jest zbyt duża. Więcej informacji oraz przykład pokazujący jak używać buforowania można znaleźć w [Ulepszanie odwzorowania modelu na podstawie informacji ze śladu wykonania](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).

#### <a name="reduce-volume-of-data-fetched"></a><a name="reduce-fetched-data"></a>Zmniejsz ilość pobieranych danych

Możesz zmniejszyć zużycie pamięci na buforowanie, ograniczając liczbę pól w rekordach tabeli aplikacji, które pobierasz w trybie uruchomieniowym. W tym przypadku pobierzesz tylko te wartości pól tabeli aplikacji, które są potrzebne w twoim odwzorowaniu modelu ER. Inne pola w tej tabeli nie będą pobierane. Dzięki temu zmniejsza się ilość pamięci potrzebnej do buforowania pobranych rekordów. Aby uzyskać więcej informacji, zobacz [Zwiększ wydajność rozwiązań ER poprzez zredukowanie liczby pól tabeli pobieranych w czasie działania](er-reduce-fetched-fields-number.md).

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a>Użyj buforowanych, parametryzowanych pól obliczeniowych

Czasami wartości muszą być szukane wielokrotnie. Przykłady: nazwy kont i numery kont. Aby zaoszczędzić czas, można utworzyć pole obliczeniowe z parametrami najwyższego poziomu, a następnie dodać je do pamięci podręcznej.

Zaleca się, aby tej metody użyć tylko wtedy, gdy rozmiar danych w pamięci podręcznej jest mały. Aby uzyskać więcej informacji, zobacz temat [Usprawnij działanie rozwiązań ER, dodając OBLICZANE POLA jako źródła danych](er-calculated-field-ds-performance.md).

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a>Używanie JOIN jako źródła danych

Źródło danych **JOIN** umożliwia pobranie kilku połączonych rekordów przez jedną kwerendę. Do pobrania każdego połączonego rekordu nie musi być używana osobna kwerenda. Na przykład, jeśli masz 1 000 wierszy i pobierasz dane pozycji dla każdego wiersza przez relację, będziesz miał 1 001 zapytań (= 1 000 + 1). W przypadku użycia źródła danych **JOIN** można pobierać te same dane tylko jedną kwerendą. Aby uzyskać więcej informacji, zob. [Użyj źródeł danych JOIN w odwzorowaniach modelu ER, aby uzyskać dane z wielu tabel aplikacji](er-join-data-sources.md).

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a>Użyj funkcji FILTER zamiast funkcji WHERE

Funkcja **[FILTER](er-functions-list-filter.md)** uruchamia warunki na serwerze SQL, podczas gdy funkcja **WHERE** pobiera wszystkie dane z listy, jeden rekord na raz i stosuje warunek do każdego rekordu. Na przykład chcesz wybrać jeden rekord z 1000 rekordów. W przypadku użycia **WHERE** zostanie pobranych wszystkie 1000 rekordów. Jednak w przypadku użycia **FILTER** zostanie pobrany dokładnie jeden rekord. **FILTER** może również używać indeksów po stronie bazy danych.

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a>Korzystanie ze zebranych funkcji danych lub skumulowanego źródła danych

Jeśli konfiguracja zawiera składnik *grupuj według*, który podsumowuje poprzednio pobrane dane według raportu, składnik ponownie pobierze wszystkie dane. Funkcja zbieranych danych umożliwia ER gromadzenie danych podczas pierwszego pobrania. Aby uzyskać więcej informacji, zobacz [Konfigurowanie formatu ER w celu zliczania i sumowania](tasks/er-format-counting-summing-2.md).

#### <a name="rewrite-parts-of-the-configuration-in-x"></a>Przepisanie części konfiguracji w X++

ER obsługuje wywoływanie metod tabel i klas, w tym rozszerzeń. Rozważ przepisanie części odwzorowania modelu w X++, aby poprawić wydajność.

ER może pobierać dane z następujących źródeł:

- Klasy (źródła danych **obiekt** i **klasa**)
- Tabele (źródła danych **tabela** i **rekordy tabeli**)

[Interfejs programowania aplikacji ER (API)](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) także oferuje sposób wysyłania wstępnie obliczonych danych z wywołującego kodu. Pakiet aplikacji zawiera wiele przykładów tego podejścia.
