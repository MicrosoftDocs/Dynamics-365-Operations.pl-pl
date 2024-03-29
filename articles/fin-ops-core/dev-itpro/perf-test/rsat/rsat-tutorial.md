---
title: Samouczek narzędzia Regression Suite Automation Tool
description: W tym artykule przedstawiono sposób użycia narzędzia Regression suite automation tool (RSAT). Opisuje on różne funkcje i zawiera przykłady korzystania z funkcji zaawansowanego tworzenia skryptów.
author: FrankDahl
ms.date: 09/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: a270398ddebef0f47a2c31b0ffb022e3df6489c7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277413"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Samouczek narzędzia Regression Suite Automation Tool

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Tę stronę można pobrać i zapisać w formacie PDF przy użyciu narzędzi dostępnych w przeglądarce internetowej.

Ten samouczek dotyczy niektórych zaawansowanych funkcji narzędzia Regression suite automation tool (RSAT), który zawiera przypisanie demonstracyjne oraz opisuje strategię i najważniejsze punkty szkoleniowe.

## <a name="notable-features-of-rsat-and-task-recorder"></a>Funkcje narzędzi RSAT i Rejestratora zadań

### <a name="validate-a-field-value"></a>Sprawdź wartość pola

Narzędzia RSAT umożliwiają uwzględnianie etapów sprawdzania poprawności w ramach testowania w celu weryfikacji oczekiwanych wartości. Aby uzyskać informacje dotyczące tej funkcji, należy zapoznać się z artykułem [Sprawdzanie oczekiwanych wartości](rsat-validate-expected.md).

W poniższym przykładzie pokazano, jak można skorzystać z tej funkcji w celu sprawdzenia, czy dostępne zapasy przekraczają 0 (zero).

1. W danych demonstracyjnych firmy **USMF** utwórz nagranie zadań, które mają następujące kroki:

    1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
    2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład filtruj według pola z wartością **1000** dla **Numeru elementu**.
    3. Wybierz **Dostępne zapasy**.
    4. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola **Oddział** z wartością **1**.
    5. Na liście oznacz wybrany wiersz.
    6. Sprawdź, czy wartość pola **W sumie dostępne** to **411.0000000000000000**.

2. Zapisz nagranie zadania jako **nagranie dewelopera** i dołącz je do przypadku testowego w usłudze Azure DevOps.
3. Dodaj przypadek testowy do planu testu i załaduj przypadek testowy do pakietu RSAT.
4. Otwórz plik parametrów programu Excel i przejdź na kartę **TestCaseSteps**.
5. Aby sprawdzić, czy dostępne zapasy będą zawsze mieć wartość większą niż **0**, przejdź do kroku **sprawdzania sumy dostępnych** i zmień wartość z **411** na **0**. Zmień wartość pola **Operator** ze znaku równości (**=**) na znak większości (**\>**).
6. Zapisz i zamknij plik parametrów w programie Excel.
7. Kliknij przycisk **Przekaż**, aby zapisać dokonane zmiany w pliku parametrów programu Excel w Azure DevOps.

Jeśli wartość w polu **Łączna ilość dostępna** dla określonego towaru w magazynie jest większa od 0 (zero), testy zostaną przekazane niezależnie od wartości rzeczywistej dostępnych zapasów.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Zapisane zmienne i łańcuchy przypadków testowych

Jedną z najważniejszych funkcji narzędzia RSAT jest łączenie przypadków testowych w łańcuchy (to znaczy zdolność testu do przekazywania zmiennych do innych testów). Aby uzyskać więcej informacji, zajrzyj do artykułu [Skopiuj zmienne do łańcuchowych przypadków testowych](rsat-chain-test-cases.md).

### <a name="derived-test-case"></a>Pochodny przypadek testowy

Narzędzia RSAT umożliwiają korzystanie z tego samego zapisu zadań w wielu przypadkach testowych, umożliwiając uruchamianie zadań z różnymi konfiguracjami danych. Aby uzyskać więcej informacji, zajrzyj do artykułu [Przypadki testu pochodnego](rsat-derived-test-cases.md).

### <a name="validate-notifications-and-messages"></a>Sprawdzanie poprawności powiadomień i komunikatów

Za pomocą tej funkcji można sprawdzić, czy akcja wystąpiła. Na przykład podczas tworzenia zlecenia produkcyjnego, szacowanego, a następnie rozpoczętego, aplikacja wyświetla komunikat „produkcja – rozpoczęcie” informujący o rozpoczęciu zlecenia produkcyjnego.

![Produkcja — Powiadomienie o rozpoczęciu.](./media/use_rsa_tool_05.png)

Można sprawdzić poprawność tej wiadomości za pośrednictwem narzędzia RSAT, wprowadzając tekst **Weryfikacja komunikatu** na karcie pliku parametrów programu Excel w celu odpowiedniego nagrania.

![Karta weryfikacji komunikatu.](./media/use_rsa_tool_06.png)

Po uruchomieniu przypadku testowego komunikat w pliku parametrów programu Excel jest porównywany z komunikatem wyświetlanym. Jeśli wiadomości nie pasują do siebie, przypadek testowy nie powiedzie się.

> [!NOTE]
> Można wprowadzić więcej niż jedną wiadomość na karcie **Weryfikacja komunikatu** w pliku parametrów programu Excel. Komunikatami mogą być także komunikaty o błędach lub ostrzeżenia, a nie komunikaty informacyjne.

### <a name="snapshot"></a>Migawka

Ta funkcja wykonuje zrzuty ekranu czynności, które zostały wykonane podczas rejestrowania zadań. Jest on przydatny do celów inspekcji lub debugowania.

- Aby skorzystać z tej funkcji, podczas uruchamiania RSAT z interfejsem użytkownika, otwórz plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

- Aby użyć tej funkcji podczas uruchamiania narzędzia RSAT przez interfejs wiersza polecenia (na przykład Azure DevOps), otwórz plik **Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C:\\Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Po uruchomieniu przypadków testowych program RSAT generuje migawki (obrazy) kroków i zapisuje je w folderze odtwarzania przypadków testowych w katalogu roboczym. W folderze odtwarzania zostanie utworzony oddzielny podfolder o nazwie **StepSnapshots**. Ten folder zawiera migawki dla uruchomionych przypadków testowych.

## <a name="assignment"></a>Przypisanie

### <a name="scenario"></a>Scenariusz

1. Konstruktor produktów tworzy nowy wydany produkt.
2. Menedżer produkcji inicjuje zlecenie produkcyjne w celu przeniesienia poziomu zapasów do dwóch sztuk.
3. Produkcja rozpoczyna się i kończy zlecenie produkcyjne oraz sprawdza, czy ilość dostępnych zapasów wynosi dwie sztuki.
4. Zespół sprzedaży otrzymuje zamówienie na cztery części nowego produktu. Z tego względu zespół sprzedaży aktualizuje zapotrzebowanie netto za pośrednictwem planu dynamicznego. Ponieważ żadne dodatkowe zdolności produkcyjne nie są dostępne, domyślną zasadą zamówienia jest „Kup zamiast robić”. W związku z tym zostanie utworzone zamówienie zakupu.
5. Kupujący dodaje dostawcę, wiąże planowane zamówienie zakupu, a następnie potwierdza zamówienie zakupu.
6. Gdy towary, które zostały nabyte, dotarły do sklepu, operator sklepu przeszukuje powiązane zamówienie zakupu i odbiera towary. Zamówienie jest teraz ukończone, towary można pobrać i zapakować w związku z zamówieniem sprzedaży.
7. Pole finanse księguje fakturę zakupu i fakturę sprzedaży.

Na poniższej ilustracji przedstawiono proces dla tego scenariusza.

![Proces dla scenariusza pokazu.](./media/use_rsa_tool_14.png)

Na poniższej ilustracji przedstawiono hierarchię procesów biznesowych dla tego scenariusza w narzędziu do modelowania procesów biznesowych usługi LCS.

![Procesy biznesowe dla scenariusza pokazu.](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Strategia — nauka najważniejszych

### <a name="data"></a>Dane

- Upewnij się, że istnieją reprezentatywne woluminy danych (kopie danych konfiguracji produkcji/złota plus dane zmigrowane).
- Podczas generowania nowych danych za pomocą rejestratora zadań należy utworzyć nazwy testowe, które nie powodują konfliktu z istniejącymi nazwami (na przykład, należy zastosować prefiks jak **RSATxxx**).
- Za pomocą funkcji przywracania punktów na platformie Azure uruchom ponownie testy w środowiskach spoza warstwy 1.
- Chociaż można skorzystać z funkcji Excel **LOSOWO** i **TERAZ**, to aby wygenerować unikatową kombinację, nakład pracy jest znacznie wysoki. Oto przykład.

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>Rejestrator zadań

- Przed rozpoczęciem rejestrowania zdefiniuj scenariusze. Dobrze zarządzany projekt ma wstępnie zdefiniowane scenariusze testowania. Aby zbudować przypadek testowy, należy rozważyć przewidywany wynik tych scenariuszy testowych.
- Podziel nagrania, jeśli są wykonywane przez różne role lub jeśli istnieje czas oczekiwania lub zdarzenie zewnętrzne przed wykonaniem następnego kroku.
- Należy unikać wybierania wartości na listach. Zamiast tego należy użyć formatów tekstu, takich jak **FIFO**, **AudioRM** i **SiteWH**. Po wybraniu opcji na liście zostanie zarejestrowana pozycja wartości na liście, a nie sama wartość. Jeśli do tej listy zostaną dodane pozycje, może zmienić się pozycja wartości. Z tego względu nagranie będzie używało innego parametru i może mieć wpływ na pozostałą część scenariusza.
- Należy zastanowić się nad zachowaniem wielu użytkowników. Na przykład nie zakłada się, że nowo utworzone zamówienie sprzedaży zawsze będzie wybierane automatycznie. Zamiast tego należy zawsze używać filtru, aby odnaleźć właściwe zamówienie.
- W celu zapisania nazwy nowo utworzonego produktu należy użyć funkcji Kopiuj w rejestratorze zadań, aby można było jej użyć w łańcuchach przypadków testowych.
- Funkcja sprawdzania poprawności w rejestratorze zadań umożliwia ustawienie punktów kontrolnych, które weryfikują poprawność działania kroków.

### <a name="rsat"></a>RSAT

- Aby uruchomić test w innej firmie, można zmienić firmę na karcie **ogólne** w pliku parametrów programu Excel. Upewnij się, że ustawienia i dane są dostępne w nowo wybranej firmie.
- Użytkownik testowy można zmienić na karcie **ogólne** w pliku parametrów programu Excel. Określ identyfikator e-mail użytkownika, który uruchomi przypadek testowy. W ten sposób można uruchomić przypadek testowy przy użyciu uprawnień zabezpieczeń określonego użytkownika.
- Aby poczekać przed rozpoczęciem testu, można zdefiniować pauzę na karcie **ogólne** pliku parametrów programu Excel. To wstrzymanie może być używane w zadaniu wsadowym (na przykład, jeśli proces przepływu pracy musi zostać wykonany, aby można było wykonać następny krok)

## <a name="advanced-scripting"></a>Zaawansowane skrypty

### <a name="cli"></a>Wiersz poleceń

RSAT można wywołać z poziomu okna **Wiersz poleceń** lub **PowerShell**.

> [!NOTE]
> Sprawdź, czy zmienna środowiskowa **TestRoot** jest ustawiona jako ścieżka instalacji pakietu RSAT. (W systemie Microsoft Windows otwórz **panel sterowania**, wybierz **System i zabezpieczenia  \> System \> Zaawansowane ustawienia systemu**, a następnie wybierz **zmienne środowiskowe**).

1. Otwórz okno **Wiersz poleceń** lub **PowerShell** jako administrator.
2. Przejdź do katalogu instalacyjnego narzędzia RSAT.

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Lista wszystkich poleceń.

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        downloadsuite
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitebyid
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        playbacksuitebyid
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>?

Wyświetla listę wszystkich poleceń lub pokazuje pomoc dla określonego polecenia wraz z dostępnymi parametrami.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a>?: Parametry opcjonalne

`command`: Miejsce ``[command]``, w którym znajduje się jedno z poleceń z poprzedniej listy.

#### <a name="about"></a>informacje

Wyświetla wersję zainstalowanego narzędzia RSAT.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls

Czyści ekran.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a>pobierz

Pobiera załączniki (pliki nagrywania, wykonywania i parametrów) dla określonego przypadku testowego z usługi Azure DevOps do katalogu wyjściowego. Możesz użyć polecenia ``list``, aby pobrać wszystkie dostępne przypadki testowe, i użyć dowolnej wartości z pierwszej kolumny jako parametru **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="download-optional-switches"></a>pobierz: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowe przypadków są zablokowane przez inne wystąpienia programu RSAT, proces pobierania będzie czekać określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.

##### <a name="download-required-parameters"></a>download: wymagane parametry

+ `test_case_id`: przedstawia identyfikator przypadku testowego.

##### <a name="download-optional-parameters"></a>pobierz: parametry opcjonalne

+ `output_dir`: Reprezentuje wyjściowy katalog roboczy. Katalog musi istnieć. Katalog roboczy z ustawień będzie używany, jeśli ten parametr nie jest określony.

##### <a name="download-examples"></a>download: przykłady

`download 123 c:\temp\rsat`

`download /retry=240 765`

#### <a name="downloadsuite"></a>downloadsuite

Pobiera załączniki (pliki nagrywania, wykonywania i parametrów) dla wszystkich przypadków testowych w określonym zestawie testów z usługi Azure DevOps do katalogu wyjściowego. Możesz użyć polecenia ``listtestsuitenames``, aby pobrać wszystkie dostępne przypadki testowe, i użyć dowolnej wartości jako parametru **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``downloadsuite``**``[/retry[=<seconds>]] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="downloadsuite-optional-switches"></a>downloadsuite: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowe przypadków są zablokowane przez inne wystąpienia programu RSAT, proces pobierania będzie czekać określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.
+ `/byid`: Ten przełącznik wskazuje, że żądany pakiet testów jest identyfikowany za pomocą Azure DevOps jego identyfikatora, a nie nazwy pakietu testów.

##### <a name="downloadsuite-required-parameters"></a>downloadsuite: wymagane parametry

+ `test_suite_name`: przedstawia nazwę zestawu testowego. Ten parametr jest wymagany, jeśli **nie** określono przełącznika /byid. Ta nazwa jest nazwą pakietu testów Azure DevOps.
+ `test_suite_id`: przedstawia identyfikator zestawu testowego. Ten parametr jest wymagany, jeśli **jest** określony przełącznik /byid. Ten identyfikator jest identyfikatorem pakietu testów Azure DevOps.

##### <a name="downloadsuite-optional-parameters"></a>downloadsuite: parametry opcjonalne

+ `output_dir`: Reprezentuje wyjściowy katalog roboczy. Katalog musi istnieć. Katalog roboczy z ustawień będzie używany, jeśli ten parametr nie jest określony.

##### <a name="downloadsuite-examples"></a>downloadsuite: przykłady

`downloadsuite NameOfTheSuite c:\temp\rsat`

`downloadsuite /byid 123 c:\temp\rsat`

`downloadsuite /retry=240 /byid 765`

`downloadsuite /retry=240 /byid 765 c:\temp\rsat`

#### <a name="edit"></a>edycja

Umożliwia otwieranie pliku parametrów w programie Excel i edytowanie go.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a>edit: wymagane parametry

+ `excel_file`: musi zawierać pełną ścieżkę do istniejącego pliku programu Excel.

##### <a name="edit-examples"></a>edit: przykłady

`edit c:\RSAT\123\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a>generate

Generuje pliki wykonania testu i parametry dla określonego przypadku testowego w katalogu wyjściowym. Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe. Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] [test_case_id] [output_dir]``

##### <a name="generate-optional-switches"></a>generowanie: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowania przypadków są blokowane przez inne instancje RSAT, proces generowania odczeka określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.
+ `/dllonly`: Generuj tylko pliki wykonania testowego. Nie generuj ponownie pliku parametrów programu Excel.
+ `/keepcustomexcel`: uaktualnij istniejący plik parametrów. Wygeneruj ponownie pliki wykonania.

##### <a name="generate-required-parameters"></a>generate: wymagane parametry

+ `test_case_id`: przedstawia identyfikator przypadku testowego.

##### <a name="generate-optional-parameters"></a>generate: opcjonalne parametry

+ `output_dir`: Reprezentuje wyjściowy katalog roboczy. Katalog musi istnieć. Katalog roboczy z ustawień będzie używany, jeśli ten parametr nie jest określony.

##### <a name="generate-examples"></a>generate: przykłady

`generate 123 c:\temp\rsat`

`generate /retry=240 765 c:\rsat\last`

`generate /retry=240 /dllonly 765`

`generate /retry=240 /keepcustomexcel 765`

#### <a name="generatederived"></a>generatederived

Generuje nowy pochodny przypadek testowy (podrzędny przypadek testowy) podanego przypadku testowego. Nowy przypadek testowy jest również dodawany do określonego zestawu testów. Możesz użyć polecenia ``list``, aby pobrać wszystkie dostępne przypadki testowe, i użyć dowolnej wartości z pierwszej kolumny jako parametru **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[/retry[=<seconds>]] [parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-optional-switches"></a>generatederived: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowania przypadków są blokowane przez inne instancje RSAT, proces generowania odczeka określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.

##### <a name="generatederived-required-parameters"></a>generatederived: wymagane parametry

+ `parent_test_case_id`: przedstawia identyfikator nadrzędnego przypadku testowego.
+ `test_plan_id`: przedstawia identyfikator planu testowego.
+ `test_suite_id`: przedstawia identyfikator zestawu testowego.

##### <a name="generatederived-examples"></a>generatederived: przykłady

`generatederived 123 8901 678`

`generatederived /retry 123 8901 678`

#### <a name="generatetestonly"></a>generatetestonly

Generuje tylko plik wykonania testu dla określonego przypadku testowego. Nie generuje ponownie pliku parametrów programu Excel. Pliki są generowane w określonym katalogu wyjściowym. Możesz użyć polecenia ``list``, aby pobrać wszystkie dostępne przypadki testowe, i użyć dowolnej wartości z pierwszej kolumny jako parametru **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="generatetestonly-optional-switches"></a>generatetestonly: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowania przypadków są blokowane przez inne instancje RSAT, proces generowania odczeka określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.

##### <a name="generatetestonly-required-parameters"></a>generatetestonly: wymagane parametry

+ `test_case_id`: przedstawia identyfikator przypadku testowego.

##### <a name="generatetestonly-optional-parameters"></a>generatetestonly: opcjonalne parametry

+ `output_dir`: Reprezentuje wyjściowy katalog roboczy. Katalog musi istnieć. Katalog roboczy z ustawień będzie używany, jeśli ten parametr nie jest określony.

##### <a name="generatetestonly-examples"></a>generatetestonly: przykłady

`generatetestonly 123 c:\temp\rsat`

`generatetestonly /retry=240 765`

#### <a name="generatetestsuite"></a>generatetestsuite

Generuje pliki automatyzacji testów dla wszystkich przypadków testowych w określonym zestawie testów. Możesz użyć polecenia ``listtestsuitenames``, aby pobrać wszystkie dostępne przypadki testowe, i użyć dowolnej wartości jako parametru **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="generatetestsuite-optional-switches"></a>generatetestsuite: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowania przypadków są blokowane przez inne instancje RSAT, proces generowania odczeka określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.
+ `/dllonly`: Generuj tylko pliki wykonania testowego. Nie generuj ponownie pliku parametrów programu Excel.
+ `/keepcustomexcel`: uaktualnij istniejący plik parametrów. Wygeneruj ponownie pliki wykonania.
+ `/byid`: Ten przełącznik wskazuje, że żądany pakiet testów jest identyfikowany za pomocą Azure DevOps jego identyfikatora, a nie nazwy pakietu testów.

##### <a name="generatetestsuite-required-parameters"></a>generatetestsuite: wymagane parametry

+ `test_suite_name`: przedstawia nazwę zestawu testowego. Ten parametr jest wymagany, jeśli **nie** określono przełącznika /byid. Ta nazwa jest nazwą pakietu testów Azure DevOps.
+ `test_suite_id`: przedstawia identyfikator zestawu testowego. Ten parametr jest wymagany, jeśli **jest** określony przełącznik /byid. Ten identyfikator jest identyfikatorem pakietu testów Azure DevOps.

##### <a name="generatetestsuite-optional-parameters"></a>generatetestsuite: opcjonalne parametry

+ `output_dir`: Reprezentuje wyjściowy katalog roboczy. Katalog musi istnieć. Katalog roboczy z ustawień będzie używany, jeśli ten parametr nie jest określony.

##### <a name="generatetestsuite-examples"></a>generatetestsuite: przykłady

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite /retry Purchase c:\rsat\last`

`generatetestsuite /dllonly /byid 121`

`generatetestsuite /keepcustomexcel /byid 121`

#### <a name="help"></a>help

Identyczny z [?](#section) polecenie.

#### <a name="list"></a>lista

Zawiera listę wszystkich dostępnych przypadków testowych w bieżącym planie testu.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a>listtestplans

Umożliwia wyświetlenie listy wszystkich dostępnych planów testowych.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a>listtestsuite

Wyświetla przypadki testowe dla określonego zestawu testowego. Możesz użyć polecenia ``listtestsuitenames``, aby pobrać wszystkie dostępne przypadki testowe, i użyć dowolnej wartości jako parametru **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[test_suite_name]``

##### <a name="listtestsuite-required-parameters"></a>listtestsuite: wymagane parametry

+ `test_suite_name`: nazwa żądanego zestawu.

##### <a name="listtestsuite-examples"></a>listtestsuite: przykłady

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitebyid"></a>listtestsuitebyid

Wyświetla przypadki testowe dla określonego zestawu testowego.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitebyid``**``[test_suite_id]``

##### <a name="listtestsuitebyid-required-parameters"></a>listtestsuitebyid: wymagane parametry

+ `test_suite_id`: identyfikator żądanego zestawu.

##### <a name="listtestsuitebyid-examples"></a>listtestsuitebyid: przykłady

`listtestsuitebyid 12345`

#### <a name="listtestsuitenames"></a>listtestsuitenames

Zawiera listę wszystkich dostępnych zestawów testowych w bieżącym planie testu.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a>playback

Odtwarza przypadek testowy skojarzony z określonym plikiem parametrów programu Excel. To polecenie używa istniejących lokalnych plików automatyzacji i nie pobiera plików z Azure DevOps. To polecenie nie jest obsługiwane w przypadku przypadków testowych commerce w programie POS.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file]``

##### <a name="playback-optional-switches"></a>Odtwarzanie: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowania przypadków są blokowane przez inne instancje RSAT, proces odtwarzania odczeka określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.
+ `/comments[="comment"]`: Podaj niestandardowy ciąg informacji, który będzie uwzględniony w polu **Komentarze** na stronach podsumowania i wyników testu dla przebiegów Azure DevOps sprawy testowej.

##### <a name="playback-required-parameters"></a>playback: wymagane parametry

+ `excel_parameter_file`: pełna ścieżka pliku parametrów programu Excel. Plik musi istnieć.

##### <a name="playback-examples"></a>playback: przykłady

`playback c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playback /retry e:\temp\test.xlsx`

`playback /retry=300 e:\temp\test.xlsx`

`playback /comments="Payroll solution 10.0.0" e:\temp\test.xlsx`

#### <a name="playbackbyid"></a>playbackbyid

Umożliwia jednoczesne odtworzenie wielu przypadków testowych. Przypadki testowe są identyfikowane za pomocą ich identyfikatora. To polecenie pobierze pliki z Azure DevOps. Możesz użyć polecenia ``list``, aby pobrać wszystkie dostępne przypadki testowe, i użyć dowolnej wartości z pierwszej kolumny jako parametru **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[/retry[=<seconds>]] [/comments[="comment"]] [test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-optional-switches"></a>playbackbyid: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowania przypadków są blokowane przez inne instancje RSAT, proces odtwarzania odczeka określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.
+ `/comments[="comment"]`: Podaj niestandardowy ciąg informacji, który będzie uwzględniony w polu **Komentarze** na stronach podsumowania i wyników testu dla przebiegów Azure DevOps sprawy testowej.

##### <a name="playbackbyid-required-parameters"></a>playbackbyid: wymagane parametry

+ `test_case_id1`: identyfikator dla istniejących przypadków testowych.
+ `test_case_id2`: identyfikator dla istniejących przypadków testowych.
+ `test_case_idN`: identyfikator dla istniejących przypadków testowych.

##### <a name="playbackbyid-examples"></a>playbackbyid: przykłady

`playbackbyid 878`

`playbackbyid 2345 667 135`

`playbackbyid /comments="Payroll solution 10.0.0" 2345 667 135`

`playbackbyid /retry /comments="Payroll solution 10.0.0" 2345 667 135`

#### <a name="playbackmany"></a>playbackmany

Umożliwia jednoczesne odtworzenie wielu przypadków testowych. Przypadki testowe są identyfikowane przez pliki parametrów programu Excel. To polecenie używa istniejących lokalnych plików automatyzacji i nie pobiera plików z Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file1] [excel_parameter_file2] ... [excel_parameter_fileN]``

##### <a name="playbackmany-optional-switches"></a>playbackmany: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowania przypadków są blokowane przez inne instancje RSAT, proces odtwarzania odczeka określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.
+ `/comments[="comment"]`: Podaj niestandardowy ciąg informacji, który będzie uwzględniony w polu **Komentarze** na stronach podsumowania i wyników testu dla przebiegów Azure DevOps sprawy testowej.

##### <a name="playbackmany-required-parameters"></a>playbackmany: wymagane parametry

+ `excel_parameter_file1`: pełna ścieżka pliku parametrów programu Excel. Plik musi istnieć.
+ `excel_parameter_file2`: pełna ścieżka pliku parametrów programu Excel. Plik musi istnieć.
+ `excel_parameter_fileN`: pełna ścieżka pliku parametrów programu Excel. Plik musi istnieć.

##### <a name="playbackmany-examples"></a>playbackmany: przykłady

`playbackmany c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playbackmany e:\temp\test.xlsx f:\RSAT\sample1.xlsx c:\RSAT\sample2.xlsx`

`playbackmany /retry=180 /comments="Payroll solution 10.0.0" e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a>playbacksuite

Odtwarza wszystkie przypadki testowe z co najmniej jednego określonego zestawu testów. Jeśli określono przełącznik /lokalny, do odtwarzania będą używane załączniki lokalne. W przeciwnym razie załączniki zostaną pobrane z Azure DevOps. Możesz użyć polecenia ``listtestsuitenames``, aby pobrać wszystkie dostępne przypadki testowe, i użyć dowolnej wartości z pierwszej kolumny jako parametru **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] ([test_suite_name1] .. [test_suite_nameN] | [/byid] [test_suite_id1] .. [test_suite_idN])``

##### <a name="playbacksuite-optional-switches"></a>playbacksuite: opcjonalne przełączniki

+ `/updatedriver`: Jeśli ten przełącznik jest określony, przed uruchomieniem procesu odtwarzania zostanie zaktualizowana aplikacja sieci Web przeglądarki internetowej.
+ `/local`: Ten przełącznik wskazuje, że do odtwarzania należy używać lokalnych załączników, a nie pobierania plików z Azure DevOps.
+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowania przypadków są blokowane przez inne instancje RSAT, proces odtwarzania odczeka określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.
+ `/comments[="comment"]`: Podaj niestandardowy ciąg informacji, który będzie uwzględniony w polu **Komentarze** na stronach podsumowania i wyników testu dla przebiegów Azure DevOps sprawy testowej.
+ `/byid`: Ten przełącznik wskazuje, że żądany pakiet testów jest identyfikowany za pomocą Azure DevOps jego identyfikatora, a nie nazwy pakietu testów.

##### <a name="playbacksuite-required-parameters"></a>playbacksuite: wymagane parametry

+ `test_suite_name1`: przedstawia nazwę zestawu testowego. Ten parametr jest wymagany, jeśli **nie** określono przełącznika /byid. Ta nazwa jest nazwą pakietu testów Azure DevOps.
+ `test_suite_nameN`: przedstawia nazwę zestawu testowego. Ten parametr jest wymagany, jeśli **nie** określono przełącznika /byid. Ta nazwa jest nazwą pakietu testów Azure DevOps.
+ `test_suite_id1`: przedstawia identyfikator zestawu testowego. Ten parametr jest wymagany, jeśli **jest** określony przełącznik /byid. Ten identyfikator jest identyfikatorem pakietu testów Azure DevOps.
+ `test_suite_idN`: przedstawia identyfikator zestawu testowego. Ten parametr jest wymagany, jeśli **jest** określony przełącznik /byid. Ten identyfikator jest identyfikatorem pakietu testów Azure DevOps.

##### <a name="playbacksuite-examples"></a>playbacksuite: przykłady

`playbacksuite suiteName`

`playbacksuite suiteName suiteNameToo`

`playbacksuite /updatedriver /local /retry=180 /byid 151 156`

`playbacksuite /updatedriver /local /comments="Payroll solution 10.0.0" /byid 150`

#### <a name="playbacksuitebyid"></a>playbacksuitebyid

Odtwarza wszystkie przypadki testowe z określonego zestawu testowego Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuitebyid``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] [test_suite_id]``

##### <a name="playbacksuitebyid-optional-switches"></a>playbacksuitebyid: opcjonalne przełączniki

+ `/retry[=seconds]`: Jeśli ten przełącznik jest określony, a przypadki testowania przypadków są blokowane przez inne instancje RSAT, proces odtwarzania odczeka określoną liczbę sekund, a następnie spróbuje jeszcze raz. Wartość domyślna dla \[sekundy\] to 120 sekund. Bez tego przełącznika proces zostanie natychmiast anulowany, jeśli przypadki testowe zostaną zablokowane.
+ `/comments[="comment"]`: Podaj niestandardowy ciąg informacji, który będzie uwzględniony w polu **Komentarze** na stronach podsumowania i wyników testu dla przebiegów Azure DevOps sprawy testowej.
+ `/byid`: Ten przełącznik wskazuje, że żądany pakiet testów jest identyfikowany za pomocą Azure DevOps jego identyfikatora, a nie nazwy pakietu testów.

##### <a name="playbacksuitebyid-required-parameters"></a>playbacksuitebyid: wymagane parametry

+ `test_suite_id`: Reprezentuje identyfikator pakietu testów, ponieważ istnieje w Azure DevOps.

##### <a name="playbacksuitebyid-examples"></a>playbacksuitebyid: przykłady

`playbacksuitebyid 2900`

`playbacksuitebyid /retry 2099`

`playbacksuitebyid /retry=200 2099`

`playbacksuitebyid /retry=200 /comments="some comment" 2099`

#### <a name="quit"></a>quit

Zamyka aplikację. To polecenie jest przydatne tylko wtedy, gdy aplikacje działają w trybie interaktywnym.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

##### <a name="quit-examples"></a>quit: przykłady

`quit`

#### <a name="upload"></a>upload

Umożliwia przekazywanie plików załączników (plików nagrania, wykonania i parametrów) należących do określonego pakietu testowego lub przypadków testowych Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``([test_suite_name] | [test_case_id1] .. [test_case_idN])``

##### <a name="upload-required-parameters"></a>upload: wymagane parametry

+ `test_suite_name`: wszystkie pliki należące do określonego zestawu testów zostaną przesłane.
+ `test_case_id1`: Reprezentuje identyfikator pierwszego przypadku testowego, który powinien zostać przekazany. Tego parametru należy używać tylko wtedy, gdy nie podano nazwy pakietu testów.
+ `test_case_idN`: Reprezentuje identyfikator ostatniego przypadku testowego, który powinien zostać przekazany. Tego parametru należy używać tylko wtedy, gdy nie podano nazwy pakietu testów.

##### <a name="upload-examples"></a>upload: przykłady

`upload sample_suite`

`upload 2900`

`upload 123 456`

#### <a name="uploadrecording"></a>uploadrecording

Przekazuje tylko plik nagrywania, który należy do co najmniej jednego określonego przypadku testowego do usługi Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[test_case_id1] .. [test_case_idN]``

##### <a name="uploadrecording-required-parameters"></a>uploadrecording: wymagane parametry

+ `test_case_id1`: reprezentuje pierwszy identyfikator przypadku testowego dla nagrania, które należy przekazać do Azure DevOps.
+ `test_case_idN`: reprezentuje ostatni identyfikator przypadku testowego dla nagrania, które należy przekazać do Azure DevOps.

##### <a name="uploadrecording-examples"></a>uploadrecording: przykłady

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a>usage

Wyświetla trzy tryby korzystania z tej aplikacji.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

Interaktywne uruchamianie aplikacji:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``

Aby uruchamiać aplikację, należy określić polecenie:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp ``**``[command]``**

Uruchamianie aplikacji przez dostarczenie pliku ustawień:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``/settings [drive:\Path to\file.settings] [command]``**

### <a name="windows-powershell-examples"></a>Przykłady środowiska Windows PowerShell

#### <a name="run-a-test-case-in-a-loop"></a>Uruchamianie przypadku testowego w pętli

Masz skrypt testowy, który tworzy nowego klienta. Za pomocą skryptów ten przypadek testowy można uruchomić w pętli, tworząc losowo następujące dane przed uruchomieniem każdej iteracji:

- Identyfikator odbiorcy
- Nazwa odbiorcy
- Adres odbiorcy

Identyfikator odbiorcy będzie w formacie *ATCUS\<number\>*, gdzie \<number\> jest wartością z zakresu od **000000001** do **999999999**.

W poniższym przykładzie użyto jednego parametru, **Start**, aby zdefiniować pierwszy użyty numer. Do zdefiniowania liczby odbiorców używany jest drugi paramentr **nr**, który musi być utworzony. W przypadku każdej iteracji parametry w pliku parametrów programu Excel są zmieniane za pomocą funkcji UpdateCustomer. Następnie wiersz polecenia RSAT jest wywoływany w funkcji RunTestCase

Otwórz środowisko Microsoft Windows PowerShell Integrated Scripting Environment (ISE) w trybie administratora i wklej następujący kod do okna o nazwie **Untitled1.ps1**.

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Uruchom skrypt zależny od danych w Microsoft Dynamics 365

W poniższym przykładzie użyto wywołania protokołu OData (Open Data Protocol) w celu znalezienia stanu zamówienia zakupu. Jeśli stan nie jest **fakturowany**, można na przykład wywołać przypadek testowy narzędzia RSAT, które zaksięguje fakturę.

```powershell
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
