---
title: Korzystanie z samouczka narzędzia Regression Suite Automation Tool
description: W tym temacie przedstawiono sposób użycia narzędzia Regression suite automation tool (RSAT). Opisuje on różne funkcje i zawiera przykłady korzystania z funkcji zaawansowanego tworzenia skryptów.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 026d1d743b5150f152ef70aa642dcf6841a4e398
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025811"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a>Korzystanie z samouczka narzędzia Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Tę stronę można pobrać i zapisać w formacie PDF przy użyciu narzędzi dostępnych w przeglądarce internetowej. 

Ten samouczek dotyczy niektórych zaawansowanych funkcji narzędzia Regression suite automation tool (RSAT), który zawiera przypisanie demonstracyjne oraz opisuje strategię i najważniejsze punkty szkoleniowe.

## <a name="features-of-rsattask-recorder"></a>Funkcje RSAT/rejestratora zadań

### <a name="validate-a-field-value"></a>Sprawdź wartość pola

Aby uzyskać informacje o tej funkcji, zapoznaj się z [funkcją tworzenia nowego nagrania zadania zawierającego funkcję sprawdzania poprawności](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).

### <a name="saved-variable"></a>Zapisane zmienne

Aby uzyskać informacje o tej funkcji, zapoznaj się z tematem [modyfikowanie istniejącego nagrania zadania w celu utworzenia zapisanej zmiennej](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).

### <a name="derived-test-case"></a>Pochodny przypadek testowy

1. Otwórz narzędzie Regression suite automation tool (RSAT) i wybierz oba przypadki testowe utworzone w [Konfigurowanie i instalowanie samouczka narzędzia Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).
2. Wybierz **Nowy \> Utwórz pochodny przypadek testowy**

    ![Utwórz pochodne polecenie przypadku testowego w menu Nowy](./media/use_rsa_tool_01.png)

3. Zostanie wyświetlony komunikat informujący o tym, że pochodny przypadek testowy zostanie utworzony dla każdego wybranego przypadku testowego w bieżącym zestawie testów oraz że każdy pochodny przypadek testowy będzie miał własną kopię pliku parametrów programu Excel. Kliknij przycisk **OK**.

    > [!NOTE]
    > Po uruchomieniu pochodnego przypadku testowego używane jest rejestrowanie zadania nadrzędnego przypadku testowego i jego kopia w pliku parametrów programu Excel. W ten sposób można uruchomić ten sam test z różnymi parametrami bez konieczności obsługiwania więcej niż jednego rejestrowania zadań. Pochodny przypadek testowy nie musi być częścią tego samego pakietu testowego, co jego nadrzędny przypadek testowy.

    ![Okno komunikatu](./media/use_rsa_tool_02.png)

    Utworzono dwa dodatkowe pochodne przypadki testowe i pole wyboru **Pochodny?** jest dla nich zaznaczone.

    ![Utworzone przypadki testowe pochodne](./media/use_rsa_tool_03.png)

    Pochodny przypadek testowy jest automatycznie tworzony w programie Azure DevOps. Jest to element podrzędny dla **tworzenia nowego przypadku testowego produktu** i jest oznakowany specjalnym słowem kluczowym **: RSAT:DerivedTestSteps**. Te przypadki testowe są również automatycznie dodawane do planu testu w systemie Azure DevOps.

    ![Słowo kluczowe RSAT: DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > Jeśli z jakiegokolwiek powodu utworzone przypadki testowe nie znajdują się w odpowiednim porządku, przejdź do Azure DevOps i zmień kolejność przypadków testowych w zestawie testów, tak aby pakiet RSAT mógł je uruchomić w odpowiedniej kolejności.

4. Wybierz tylko pochodny przypadek testowy, a następnie kliknij przycisk **Edytuj**, aby otworzyć odpowiedni plik parametrów programu Excel.
5. Pliki parametrów programu Excel można edytować w taki sam sposób, jak pliki nadrzędne. Innymi słowy, należy się upewnić, że identyfikator produktu jest skonfigurowany do automatycznego generowania. Upewnij się również, że zapisana zmienna jest kopiowana do odpowiednich pól.
6. Na karcie **ogólne** obu plików parametrów programu Excel zaktualizuj wartość pola **Firma** w celu **Ussi**, tak aby pochodne przypadki testowe zostały uruchomione dla innej firmy niż w przypadku testu nadrzędnego. Aby uruchomić przypadki testowe w odniesieniu do określonego użytkownika (lub roli skojarzonej z określonym użytkownikiem), można zaktualizować wartość pola **użytkownik testowy**.
7. Wybierz opcję **Uruchom**, a następnie sprawdź, czy produkt został utworzony w firmie USMF i firmie Ussi.

### <a name="validate-notifications"></a>Weryfikuj powiadomienia

Za pomocą tej funkcji można sprawdzić, czy akcja wystąpiła. Na przykład podczas tworzenia zlecenia produkcyjnego, szacowanego, a następnie rozpoczętego, aplikacja wyświetla komunikat „produkcja – rozpoczęcie” informujący o rozpoczęciu zlecenia produkcyjnego.

![Produkcja — Powiadomienie o rozpoczęciu](./media/use_rsa_tool_05.png)

Można sprawdzić poprawność tej wiadomości za pośrednictwem narzędzia RSAT, wprowadzając tekst **Weryfikacja komunikatu** na karcie pliku parametrów programu Excel w celu odpowiedniego nagrania.

![Karta weryfikacji komunikatu](./media/use_rsa_tool_06.png)

Po uruchomieniu przypadku testowego komunikat w pliku parametrów programu Excel jest porównywany z komunikatem wyświetlanym. Jeśli wiadomości nie pasują do siebie, przypadek testowy nie powiedzie się.

> [!NOTE]
> Można wprowadzić więcej niż jedną wiadomość na karcie **Weryfikacja komunikatu** w pliku parametrów programu Excel. Komunikatami mogą być także komunikaty o błędach lub ostrzeżenia, a nie komunikaty informacyjne.

### <a name="validate-values-by-using-operators"></a>Sprawdzanie poprawności wartości przy użyciu operatorów

W poprzednich wersjach pakietu RSAT można było sprawdzać poprawność wartości tylko wtedy, gdy wartość kontrolna jest równa oczekiwanej wartości. Nowa funkcja umożliwia sprawdzenie, czy zmienna nie jest równa, jest mniejsza niż lub równa określonej wartości.

- Aby skorzystać z tej funkcji, należy otworzyć plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.

    ```xml
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    W pliku parametrów programu Excel pojawi się pole nowego **operatora**.

    > [!NOTE]
    > W przypadku korzystania ze starszej wersji pakietu RSAT należy wygenerować nowe pliki parametrów programu Excel.

    ![Pole Operator](./media/use_rsa_tool_07.png)

W poniższym przykładzie pokazano, jak można skorzystać z tej funkcji w celu sprawdzenia, czy dostępne zapasy przekraczają 0 (zero).

1. W danych demonstracyjnych firmy **USMF** utwórz nagranie zadań, które mają następujące kroki:

    1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
    2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład filtruj według pola z wartością **1000** dla **Numeru elementu**.
    3. Wybierz **Dostępne zapasy**.
    4. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola **Oddział** z wartością **1**.
    5. Na liście oznacz wybrany wiersz.
    6. Sprawdź, czy wartość pola **W sumie dostępne** to **411.0000000000000000**.

2. Zapisz nagranie zadania w BPM i LCS i zsynchronizuj z Azure DevOps.
3. Dodaj przypadek testowy do planu testu i załaduj przypadek testowy do pakietu RSAT.
4. Otwórz plik parametrów programu Excel. Na karcie **InventOnhandItem** zostanie wyświetlona sekcja **sprawdzanie poprawności InventOnhandItem** zawierającej pole **operatora.**

    ![Pole Operator](./media/use_rsa_tool_08.png)

5. Aby sprawdzić, czy dostępne zapasy będą zawsze większe niż 0, Zmień wartość w polu **wartość** z **411** na **0** i wartość pola **operator** w znaku równości (**=**) na znak większości (**\>**).

    ![Wartości pól wartości i operatora zostały zmienione](./media/use_rsa_tool_09.png)

6. Zapisz i zamknij plik parametrów w programie Excel.
7. Kliknij przycisk **Przekaż**, aby zapisać dokonane zmiany w pliku parametrów programu Excel w Azure DevOps.

Jeśli wartość w polu **Łączna ilość dostępna** dla określonego towaru w magazynie jest większa od 0 (zero), testy zostaną przekazane niezależnie od wartości rzeczywistej dostępnych zapasów.

### <a name="generator-logs"></a>Generator dzienników

Ta funkcja tworzy folder zawierający dzienniki uruchomionych spraw testowych.

- Aby skorzystać z tej funkcji, należy otworzyć plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.

    ```xml
    <add key="LogGeneration" value="false" />
    ```

Po uruchomieniu przypadków testowych można znaleźć pliki dziennika w folderze **C:\\użytkownicy\\\<nazwa użytkownika\>\\AppData\\mobilne\\regressionTool\\generatorLogs**.

![Folder GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> Jeśli istnieją przypadki testowe przed zmianą wartości w pliku. config, dzienniki nie zostaną wygenerowane dla tych przypadków testowych, dopóki nie zostaną utworzone nowe pliki wykonywania testów.
> 
> ![Polecenie Generuj tylko pliki wykonania testu w menu Nowy](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a>Migawka

Ta funkcja wykonuje zrzuty ekranu czynności, które zostały wykonane podczas rejestrowania zadań.

- Aby skorzystać z tej funkcji, należy otworzyć plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

W obszarze **C:\\użytkownicy\\\<nazwa użytkownika\>\\AppData\\mobilny\\regressionTool\\playback** jest tworzony oddzielny folder dla każdego uruchomionego przypadku testowego.

![Folder migawek dla przypadku testowego](./media/use_rsa_tool_12.png)

W każdym z tych folderów można znaleźć migawki kroków, które zostały wykonane w trakcie wykonywania przypadków testowych.

![Pliki migawek](./media/use_rsa_tool_13.png)

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

Na poniższej ilustracji przedstawiono proces biznesowy dla tego scenariusza w RSAT.

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

### <a name="command-line"></a>Wiersz polecenia

RSAT można wywołać z poziomu okna **wiersza polecenia**.

> [!NOTE]
> Sprawdź, czy zmienna środowiskowa **TestRoot** jest ustawiona jako ścieżka instalacji pakietu RSAT. (W systemie Microsoft Windows otwórz **panel sterowania**, wybierz **System i zabezpieczenia  \> System \> Zaawansowane ustawienia systemu**, a następnie wybierz **zmienne środowiskowe**).

1. Otwórz okno **Wiersz poleceń** jako administrator.
2. Uruchom narzędzie z katalogu instalacyjnego.

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
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a>Przykłady środowiska Windows PowerShell

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
$excelFilename = "full path to excel file parameter file"
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
