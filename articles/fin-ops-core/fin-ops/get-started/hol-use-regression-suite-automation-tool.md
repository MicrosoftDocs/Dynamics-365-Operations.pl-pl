---
title: Korzystanie z samouczka narzędzia Regression Suite Automation Tool
description: W tym temacie przedstawiono sposób użycia narzędzia Regression suite automation tool (RSAT). Opisuje on różne funkcje i zawiera przykłady korzystania z funkcji zaawansowanego tworzenia skryptów.
author: robinarh
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 2d3dde69b102ce161e5c1f1dd393ffceca608bcb
ms.sourcegitcommit: 4fdee254649a751d46632fb4d0d48698e112fa72
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2020
ms.locfileid: "3248743"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a>Korzystanie z samouczka narzędzia Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Tę stronę można pobrać i zapisać w formacie PDF przy użyciu narzędzi dostępnych w przeglądarce internetowej. 

Ten samouczek dotyczy niektórych zaawansowanych funkcji narzędzia Regression suite automation tool (RSAT), który zawiera przypisanie demonstracyjne oraz opisuje strategię i najważniejsze punkty szkoleniowe. 

## <a name="notable-features-of-rsat-and-task-recorder"></a>Funkcje narzędzi RSAT i Rejestratora zadań

### <a name="validate-a-field-value"></a>Sprawdź wartość pola

Narzędzia RSAT umożliwiają uwzględnianie etapów sprawdzania poprawności w ramach testowania w celu weryfikacji oczekiwanych wartości. Aby uzyskać informacje dotyczące tej funkcji, należy zapoznać się z artykułem [Sprawdzanie oczekiwanych wartości](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).

W poniższym przykładzie pokazano, jak można skorzystać z tej funkcji w celu sprawdzenia, czy dostępne zapasy przekraczają 0 (zero).

1. W danych demonstracyjnych firmy **USMF** utwórz nagranie zadań, które mają następujące kroki:

    1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
    2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład filtruj według pola z wartością **1000** dla **Numeru elementu**.
    3. Wybierz **Dostępne zapasy**.
    4. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola **Oddział** z wartością **1**.
    5. Na liście oznacz wybrany wiersz.
    6. Sprawdź, czy wartość pola **W sumie dostępne** to **411.0000000000000000**.

2. Zapisz rejestrowanie zadań i dołącz je do przypadku testowego w usłudze Azure DevOps.
3. Dodaj przypadek testowy do planu testu i załaduj przypadek testowy do pakietu RSAT.
4. Otwórz plik parametrów programu Excel. Na karcie **InventOnhandItem** zostanie wyświetlona sekcja **sprawdzanie poprawności InventOnhandItem** zawierającej pole **operatora.**

    ![Pole Operator](./media/use_rsa_tool_08.png)

5. Aby sprawdzić, czy dostępne zapasy będą zawsze większe niż 0, Zmień wartość w polu **wartość** z **411** na **0** i wartość pola **operator** w znaku równości (**=**) na znak większości (**\>**).

    ![Wartości pól wartości i operatora zostały zmienione](./media/use_rsa_tool_09.png)

6. Zapisz i zamknij plik parametrów w programie Excel.
7. Kliknij przycisk **Przekaż**, aby zapisać dokonane zmiany w pliku parametrów programu Excel w Azure DevOps.

Jeśli wartość w polu **Łączna ilość dostępna** dla określonego towaru w magazynie jest większa od 0 (zero), testy zostaną przekazane niezależnie od wartości rzeczywistej dostępnych zapasów.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Zapisane zmienne i łańcuchy przypadków testowych

Jedną z najważniejszych funkcji narzędzia RSAT jest łączenie przypadków testowych w łańcuchy (to znaczy zdolność testu do przekazywania zmiennych do innych testów). Aby uzyskać więcej informacji, zajrzyj do artykułu [Skopiuj zmienne do łańcuchowych przypadków testowych](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).

### <a name="derived-test-case"></a>Pochodny przypadek testowy

Narzędzia RSAT umożliwiają korzystanie z tego samego zapisu zadań w wielu przypadkach testowych, umożliwiając uruchamianie zadań z różnymi konfiguracjami danych. Aby uzyskać więcej informacji, zajrzyj do artykułu [Przypadki testu pochodnego](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md).

### <a name="validate-notifications-and-messages"></a>Sprawdzanie poprawności powiadomień i komunikatów

Za pomocą tej funkcji można sprawdzić, czy akcja wystąpiła. Na przykład podczas tworzenia zlecenia produkcyjnego, szacowanego, a następnie rozpoczętego, aplikacja wyświetla komunikat „produkcja – rozpoczęcie” informujący o rozpoczęciu zlecenia produkcyjnego.

![Produkcja — Powiadomienie o rozpoczęciu](./media/use_rsa_tool_05.png)

Można sprawdzić poprawność tej wiadomości za pośrednictwem narzędzia RSAT, wprowadzając tekst **Weryfikacja komunikatu** na karcie pliku parametrów programu Excel w celu odpowiedniego nagrania.

![Karta weryfikacji komunikatu](./media/use_rsa_tool_06.png)

Po uruchomieniu przypadku testowego komunikat w pliku parametrów programu Excel jest porównywany z komunikatem wyświetlanym. Jeśli wiadomości nie pasują do siebie, przypadek testowy nie powiedzie się.

> [!NOTE]
> Można wprowadzić więcej niż jedną wiadomość na karcie **Weryfikacja komunikatu** w pliku parametrów programu Excel. Komunikatami mogą być także komunikaty o błędach lub ostrzeżenia, a nie komunikaty informacyjne.

### <a name="snapshot"></a>Migawka

Ta funkcja wykonuje zrzuty ekranu czynności, które zostały wykonane podczas rejestrowania zadań. Jest on przydatny do celów inspekcji lub debugowania.

- Aby skorzystać z tej funkcji, należy otworzyć plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Po uruchomieniu przypadku testowego narzędzia RSAT generują migawki (obrazy) kroków w folderze odtwarzania przypadków testowych w katalogu roboczym. Jeśli używana jest starsza wersja narzędzia RSAT, obrazy są zapisywane w folderze **C:\\użytkownicy\\\<Nazwa użytkownika\>\\AppData\\Roaming\\regressionTool\\odtwarzanie**, utowrzony jest osobny folder dla każdego uruchomionego przypadku testowego.

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

![Proces dla scenariusza pokazu](./media/use_rsa_tool_14.png)

Na poniższej ilustracji przedstawiono hierarchię procesów biznesowych dla tego scenariusza w narzędziu do modelowania procesów biznesowych usługi LCS.

![Procesy biznesowe dla scenariusza pokazu](./media/use_rsa_tool_15.png)

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
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>? 
Pokazuje pomoc dotyczącą wszystkich dostępnych poleceń i ich parametrów.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a>Parametry opcjonalne

**``command``**


Gdzie ``[command]`` jest jednym z poleceń określonych poniżej.


#### <a name="about"></a>informacje
Wyświetla obecną wersję.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls
Czyści ekran.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a>pobierz
Pobiera załączniki dla określonego przypadku testowego do katalogu wyjściowego. Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe. Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Wymagane parametry
**``test_case_id``** Przedstawia identyfikator przypadku testowego.  
**``output_dir``** Reprezentuje katalog wyjściowy. Katalog musi istnieć.

##### <a name="examples"></a>Przykłady

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a>edycja
Umożliwia otwieranie pliku parametrów w programie Excel i edytowanie go.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a>Wymagane parametry
**``excel_file``** Musi zawierać pełną ścieżkę do istniejącego pliku programu Excel.

##### <a name="examples"></a>Przykłady
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a>generate
Generuje pliki wykonania testu i parametry dla określonego przypadku testowego w katalogu wyjściowym.
Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe. Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Wymagane parametry
**``test_case_id``** Przedstawia identyfikator przypadku testowego.  
**``output_dir``** Reprezentuje katalog wyjściowy. Katalog musi istnieć.

##### <a name="examples"></a>Przykłady
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a>generatederived
Generuje nowy przypadek testowy pochodzący z dostarczonego przypadku testowego. Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe. Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a>Wymagane parametry
**``parent_test_case_id``** Przedstawia identyfikator nadrzędnego przypadku testowego.  
**``test_plan_id``** Przedstawia identyfikator planu testowego.  
**``test_suite_id``** Przedstawia identyfikator zestawu testowego.

##### <a name="examples"></a>Przykłady
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a>generatetestonly
Generuje tylko plik wykonania testu dla określonego przypadku testowego w katalogu wyjściowym. Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe. Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Wymagane parametry
**``test_case_id``** Przedstawia identyfikator przypadku testowego.  
**``output_dir``** Reprezentuje katalog wyjściowy. Katalog musi istnieć.

##### <a name="examples"></a>Przykłady
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a>generatetestsuite
Generuje wszystkie przypadki testowe dla określonego zestawu w katalogu wyjściowym.
Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe. Jako parametru **test_suiye_id** należy zastosować dowolną wartość z kolumny.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a>Wymagane parametry
**``test_suite_name``** Przedstawia nazwę zestawu testowego.  
**``output_dir``** Reprezentuje katalog wyjściowy. Katalog musi istnieć.

##### <a name="examples"></a>Przykłady
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a>help
Identyczny z [?](#section) command


#### <a name="list"></a>liście
Umożliwia wyświetlenie listy wszystkich dostępnych przypadków testowych.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a>listtestplans
Umożliwia wyświetlenie listy wszystkich dostępnych planów testowych.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a>listtestsuite
Wyświetla przypadki testowe dla określonego zestawu testowego. Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe. Jako parametru **suite_name** należy zastosować dowolną wartość z pierwszej kolumny.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a>Wymagane parametry
**``suite_name``** Nazwa żądanego zestawu.

##### <a name="examples"></a>Przykłady
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a>listtestsuitenames
Umożliwia wyświetlenie listy wszystkich dostępnych zestawów testowych.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a>playback
Umożliwia ponowne odtworzenie przypadku testowego w pliku programu Excel.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a>Wymagane parametry
**``excel_file``** Pełna ścieżka do pliku Excel. Plik musi istnieć. 

##### <a name="examples"></a>Przykłady
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a>playbackbyid
Umożliwia jednoczesne odtworzenie wielu przypadków testowych.
Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe. Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a>Wymagane parametry
**``test_case_id1``** Identyfikator dla istniejących przypadków testowych.  
**``test_case_id2``** Identyfikator dla istniejących przypadków testowych.  
**``test_case_idN``** Identyfikator dla istniejących przypadków testowych.  

##### <a name="examples"></a>Przykłady
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a>playbackmany
Umożliwia jednoczesne odtwarzanie wielu przypadków testowych przy użyciu plików programu Excel.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a>Wymagane parametry
**``excel_file1``** Pełna ścieżka do pliku Excel. Plik musi istnieć.  
**``excel_file2``** Pełna ścieżka do pliku Excel. Plik musi istnieć.  
**``excel_fileN``** Pełna ścieżka do pliku Excel. Plik musi istnieć.  

##### <a name="examples"></a>Przykłady
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a>playbacksuite
Odtwarza wszystkie przypadki testowe z określonego zestawu testowego. Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe. Jako parametru **suite_name** należy zastosować dowolną wartość z pierwszej kolumny.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a>Wymagane parametry
**``suite_name``** Nazwa żądanego zestawu.

##### <a name="examples"></a>Przykłady
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a>quit
Zamyka aplikację.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a>upload
Umożliwia przekazanie wszystkich plików należących do określonego zestawu testów lub przypadków testowych.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a>Wymagane parametry
**``suite_name``** Wszystkie pliki należące do określonego zestawu testów zostaną przesłane.
**``testcase_id``** Wszystkie pliki należące do określonego przypadku testowego (przypadków testowych) zostaną przesłane.

##### <a name="examples"></a>Przykłady
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a>uploadrecording
Umożliwia przekazanie tylko pliku nagrania należącego do określonych przypadków testowych.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a>Wymagane parametry
**``testcase_id``** Plik nagrania należący do określonych przypadków testowych zostanie przesłany.

##### <a name="examples"></a>Przykłady
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a>usage
Pokazuje dwa sposoby wywoływania tej aplikacji: jeden przy użyciu pliku ustawień domyślnych oraz drugi, który udostępnia plik ustawień.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a>Przykłady środowiska Windows PowerShell

[!IMPORTANT] Przykładowe skrypty przedstawione poniżej są przeznaczone do celów ilustracyjnych i nie są obsługiwane przez firmę Microsoft.

#### <a name="run-a-test-case-in-a-loop"></a>Uruchamianie przypadku testowego w pętli

Masz skrypt testowy, który tworzy nowego klienta. Za pomocą skryptów ten przypadek testowy można uruchomić w pętli, tworząc losowo następujące dane przed uruchomieniem każdej iteracji:

- Identyfikator odbiorcy
- Nazwa odbiorcy
- Adres odbiorcy

Identyfikator odbiorcy będzie w formacie *ATCUS\<liczba\>*, gdzie \<liczba\> jest wartością z zakresu od **000000001** do **999999999**.

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

```xpp
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
