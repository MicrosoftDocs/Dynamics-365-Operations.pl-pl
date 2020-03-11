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
ms.openlocfilehash: 6cdaa89fb6d50ebaaaefe7f92d7224a1567d17d1
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070827"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="ef5a7-104">Korzystanie z samouczka narzędzia Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="ef5a7-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ef5a7-105">Tę stronę można pobrać i zapisać w formacie PDF przy użyciu narzędzi dostępnych w przeglądarce internetowej.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="ef5a7-106">Ten samouczek dotyczy niektórych zaawansowanych funkcji narzędzia Regression suite automation tool (RSAT), który zawiera przypisanie demonstracyjne oraz opisuje strategię i najważniejsze punkty szkoleniowe.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="features-of-rsattask-recorder"></a><span data-ttu-id="ef5a7-107">Funkcje RSAT/rejestratora zadań</span><span class="sxs-lookup"><span data-stu-id="ef5a7-107">Features of RSAT/Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="ef5a7-108">Sprawdź wartość pola</span><span class="sxs-lookup"><span data-stu-id="ef5a7-108">Validate a field value</span></span>

<span data-ttu-id="ef5a7-109">Aby uzyskać informacje o tej funkcji, zapoznaj się z [funkcją tworzenia nowego nagrania zadania zawierającego funkcję sprawdzania poprawności](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span><span class="sxs-lookup"><span data-stu-id="ef5a7-109">For information about this feature, see the [Create a new task recording that has a Validate function](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span></span>

### <a name="saved-variable"></a><span data-ttu-id="ef5a7-110">Zapisane zmienne</span><span class="sxs-lookup"><span data-stu-id="ef5a7-110">Saved variable</span></span>

<span data-ttu-id="ef5a7-111">Aby uzyskać informacje o tej funkcji, zapoznaj się z tematem [modyfikowanie istniejącego nagrania zadania w celu utworzenia zapisanej zmiennej](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span><span class="sxs-lookup"><span data-stu-id="ef5a7-111">For information about this feature, see the [Modify an existing task recording to create a saved variable](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="ef5a7-112">Pochodny przypadek testowy</span><span class="sxs-lookup"><span data-stu-id="ef5a7-112">Derived test case</span></span>

1. <span data-ttu-id="ef5a7-113">Otwórz narzędzie Regression suite automation tool (RSAT) i wybierz oba przypadki testowe utworzone w [Konfigurowanie i instalowanie samouczka narzędzia Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="ef5a7-113">Open Regression suite automation tool (RSAT), and select both the test cases that you created in [Set up and install Regression suite automation tool tutorial](./hol-set-up-regression-suite-automation-tool.md).</span></span>
2. <span data-ttu-id="ef5a7-114">Wybierz **Nowy \> Utwórz pochodny przypadek testowy**</span><span class="sxs-lookup"><span data-stu-id="ef5a7-114">Select **New \> Create derived test case**.</span></span>

    ![Utwórz pochodne polecenie przypadku testowego w menu Nowy](./media/use_rsa_tool_01.png)

3. <span data-ttu-id="ef5a7-116">Zostanie wyświetlony komunikat informujący o tym, że pochodny przypadek testowy zostanie utworzony dla każdego wybranego przypadku testowego w bieżącym zestawie testów oraz że każdy pochodny przypadek testowy będzie miał własną kopię pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-116">You receive a message that states that a derived test case will be created for each selected test case in the current test suite, and that each derived test case will have its own copy of the Excel parameter file.</span></span> <span data-ttu-id="ef5a7-117">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-117">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef5a7-118">Po uruchomieniu pochodnego przypadku testowego używane jest rejestrowanie zadania nadrzędnego przypadku testowego i jego kopia w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-118">When you run a derived test case, it uses the task recording of its parent test case and its own copy of the Excel parameter file.</span></span> <span data-ttu-id="ef5a7-119">W ten sposób można uruchomić ten sam test z różnymi parametrami bez konieczności obsługiwania więcej niż jednego rejestrowania zadań.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-119">In this way, you can run the same test with different parameters, without having to maintain more than one task recording.</span></span> <span data-ttu-id="ef5a7-120">Pochodny przypadek testowy nie musi być częścią tego samego pakietu testowego, co jego nadrzędny przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-120">A derived test case doesn't have to be part of the same test suite as its parent test case.</span></span>

    ![Okno komunikatu](./media/use_rsa_tool_02.png)

    <span data-ttu-id="ef5a7-122">Utworzono dwa dodatkowe pochodne przypadki testowe i pole wyboru **Pochodny?** jest dla nich zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-122">Two additional derived test cases are created, and the **Derived?** check box is selected for them.</span></span>

    ![Utworzone przypadki testowe pochodne](./media/use_rsa_tool_03.png)

    <span data-ttu-id="ef5a7-124">Pochodny przypadek testowy jest automatycznie tworzony w programie Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-124">A derived test case is automatically created in Azure DevOps.</span></span> <span data-ttu-id="ef5a7-125">Jest to element podrzędny dla **tworzenia nowego przypadku testowego produktu** i jest oznakowany specjalnym słowem kluczowym **: RSAT:DerivedTestSteps**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-125">It's a child item of the **Create a new product** test case and is tagged with a special keyword: **RSAT:DerivedTestSteps**.</span></span> <span data-ttu-id="ef5a7-126">Te przypadki testowe są również automatycznie dodawane do planu testu w systemie Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-126">These test cases are also automatically added to the test plan in Azure DevOps.</span></span>

    ![Słowo kluczowe RSAT: DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > <span data-ttu-id="ef5a7-128">Jeśli z jakiegokolwiek powodu utworzone przypadki testowe nie znajdują się w odpowiednim porządku, przejdź do Azure DevOps i zmień kolejność przypadków testowych w zestawie testów, tak aby pakiet RSAT mógł je uruchomić w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-128">If, for any reason, the derived test cases that are created aren't in the correct order, go to Azure DevOps, and reorder the test cases in the test suite, so that RSAT can run them in the correct order.</span></span>

4. <span data-ttu-id="ef5a7-129">Wybierz tylko pochodny przypadek testowy, a następnie kliknij przycisk **Edytuj**, aby otworzyć odpowiedni plik parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-129">Select the derived test cases, and then select **Edit** to open the corresponding Excel parameter files.</span></span>
5. <span data-ttu-id="ef5a7-130">Pliki parametrów programu Excel można edytować w taki sam sposób, jak pliki nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-130">Edit these Excel parameter files in the same way that you edited the parent files.</span></span> <span data-ttu-id="ef5a7-131">Innymi słowy, należy się upewnić, że identyfikator produktu jest skonfigurowany do automatycznego generowania.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-131">In other words, make sure that the product ID is set so that it's automatically generated.</span></span> <span data-ttu-id="ef5a7-132">Upewnij się również, że zapisana zmienna jest kopiowana do odpowiednich pól.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-132">Also make sure that the saved variable is copied to the relevant fields.</span></span>
6. <span data-ttu-id="ef5a7-133">Na karcie **ogólne** obu plików parametrów programu Excel zaktualizuj wartość pola **Firma** w celu **Ussi**, tak aby pochodne przypadki testowe zostały uruchomione dla innej firmy niż w przypadku testu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-133">On the **General** tab of both Excel parameter files, update the value of the **Company** field to **USSI**, so that the derived test cases will be run against a different legal entity than the parent test case.</span></span> <span data-ttu-id="ef5a7-134">Aby uruchomić przypadki testowe w odniesieniu do określonego użytkownika (lub roli skojarzonej z określonym użytkownikiem), można zaktualizować wartość pola **użytkownik testowy**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-134">To run the test cases against a specific user (or the role that is associated with a specific user), you can update the value of the **Test User** field.</span></span>
7. <span data-ttu-id="ef5a7-135">Wybierz opcję **Uruchom**, a następnie sprawdź, czy produkt został utworzony w firmie USMF i firmie Ussi.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-135">Select **Run**, and validate that the product is created in both the USMF legal entity and the USSI legal entity.</span></span>

### <a name="validate-notifications"></a><span data-ttu-id="ef5a7-136">Weryfikuj powiadomienia</span><span class="sxs-lookup"><span data-stu-id="ef5a7-136">Validate notifications</span></span>

<span data-ttu-id="ef5a7-137">Za pomocą tej funkcji można sprawdzić, czy akcja wystąpiła.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-137">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="ef5a7-138">Na przykład podczas tworzenia zlecenia produkcyjnego, szacowanego, a następnie rozpoczętego, aplikacja wyświetla komunikat „produkcja – rozpoczęcie” informujący o rozpoczęciu zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-138">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Produkcja — Powiadomienie o rozpoczęciu](./media/use_rsa_tool_05.png)

<span data-ttu-id="ef5a7-140">Można sprawdzić poprawność tej wiadomości za pośrednictwem narzędzia RSAT, wprowadzając tekst **Weryfikacja komunikatu** na karcie pliku parametrów programu Excel w celu odpowiedniego nagrania.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-140">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Karta weryfikacji komunikatu](./media/use_rsa_tool_06.png)

<span data-ttu-id="ef5a7-142">Po uruchomieniu przypadku testowego komunikat w pliku parametrów programu Excel jest porównywany z komunikatem wyświetlanym.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-142">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="ef5a7-143">Jeśli wiadomości nie pasują do siebie, przypadek testowy nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-143">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="ef5a7-144">Można wprowadzić więcej niż jedną wiadomość na karcie **Weryfikacja komunikatu** w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-144">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="ef5a7-145">Komunikatami mogą być także komunikaty o błędach lub ostrzeżenia, a nie komunikaty informacyjne.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-145">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="validate-values-by-using-operators"></a><span data-ttu-id="ef5a7-146">Sprawdzanie poprawności wartości przy użyciu operatorów</span><span class="sxs-lookup"><span data-stu-id="ef5a7-146">Validate values by using operators</span></span>

<span data-ttu-id="ef5a7-147">W poprzednich wersjach pakietu RSAT można było sprawdzać poprawność wartości tylko wtedy, gdy wartość kontrolna jest równa oczekiwanej wartości.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-147">In previous versions of RSAT, you could validate values only if a control value equaled an expected value.</span></span> <span data-ttu-id="ef5a7-148">Nowa funkcja umożliwia sprawdzenie, czy zmienna nie jest równa, jest mniejsza niż lub równa określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-148">The new feature lets you validate that a variable isn't equal to, is less than, or is more than a specified value.</span></span>

- <span data-ttu-id="ef5a7-149">Aby skorzystać z tej funkcji, należy otworzyć plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-149">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    <span data-ttu-id="ef5a7-150">W pliku parametrów programu Excel pojawi się pole nowego **operatora**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-150">In the Excel parameter file, a new **Operator** field appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef5a7-151">W przypadku korzystania ze starszej wersji pakietu RSAT należy wygenerować nowe pliki parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-151">If you've been using an older version of RSAT, you must generate new Excel parameter files.</span></span>

    ![Pole Operator](./media/use_rsa_tool_07.png)

<span data-ttu-id="ef5a7-153">W poniższym przykładzie pokazano, jak można skorzystać z tej funkcji w celu sprawdzenia, czy dostępne zapasy przekraczają 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="ef5a7-153">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="ef5a7-154">W danych demonstracyjnych firmy **USMF** utwórz nagranie zadań, które mają następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="ef5a7-154">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="ef5a7-155">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-155">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="ef5a7-156">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-156">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ef5a7-157">Na przykład filtruj według pola z wartością **1000** dla **Numeru elementu**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-157">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="ef5a7-158">Wybierz **Dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-158">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="ef5a7-159">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-159">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ef5a7-160">Na przykład wyfiltruj według pola **Oddział** z wartością **1**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-160">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="ef5a7-161">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-161">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="ef5a7-162">Sprawdź, czy wartość pola **W sumie dostępne** to **411.0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-162">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="ef5a7-163">Zapisz nagranie zadania w BPM i LCS i zsynchronizuj z Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-163">Save the task recording to the BPM library in LCS, and sync it to Azure DevOps.</span></span>
3. <span data-ttu-id="ef5a7-164">Dodaj przypadek testowy do planu testu i załaduj przypadek testowy do pakietu RSAT.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-164">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="ef5a7-165">Otwórz plik parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-165">Open the Excel parameter file.</span></span> <span data-ttu-id="ef5a7-166">Na karcie **InventOnhandItem** zostanie wyświetlona sekcja **sprawdzanie poprawności InventOnhandItem** zawierającej pole **operatora.**</span><span class="sxs-lookup"><span data-stu-id="ef5a7-166">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Pole Operator](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="ef5a7-168">Aby sprawdzić, czy dostępne zapasy będą zawsze większe niż 0, Zmień wartość w polu **wartość** z **411** na **0** i wartość pola **operator** w znaku równości (**=**) na znak większości (**\>**).</span><span class="sxs-lookup"><span data-stu-id="ef5a7-168">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Wartości pól wartości i operatora zostały zmienione](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="ef5a7-170">Zapisz i zamknij plik parametrów w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-170">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="ef5a7-171">Kliknij przycisk **Przekaż**, aby zapisać dokonane zmiany w pliku parametrów programu Excel w Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-171">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="ef5a7-172">Jeśli wartość w polu **Łączna ilość dostępna** dla określonego towaru w magazynie jest większa od 0 (zero), testy zostaną przekazane niezależnie od wartości rzeczywistej dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-172">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="generator-logs"></a><span data-ttu-id="ef5a7-173">Generator dzienników</span><span class="sxs-lookup"><span data-stu-id="ef5a7-173">Generator logs</span></span>

<span data-ttu-id="ef5a7-174">Ta funkcja tworzy folder zawierający dzienniki uruchomionych spraw testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-174">This feature creates a folder that contains the logs of the test cases that have been run.</span></span>

- <span data-ttu-id="ef5a7-175">Aby skorzystać z tej funkcji, należy otworzyć plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-175">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="LogGeneration" value="false" />
    ```

<span data-ttu-id="ef5a7-176">Po uruchomieniu przypadków testowych można znaleźć pliki dziennika w folderze **C:\\użytkownicy\\\<nazwa użytkownika\>\\AppData\\mobilne\\regressionTool\\generatorLogs**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-176">After the test cases are run, you can find the log files under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span></span>

![Folder GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> <span data-ttu-id="ef5a7-178">Jeśli istnieją przypadki testowe przed zmianą wartości w pliku. config, dzienniki nie zostaną wygenerowane dla tych przypadków testowych, dopóki nie zostaną utworzone nowe pliki wykonywania testów.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-178">If there were existing test cases before you changed the value in the .config file, logs won't be generated for those test cases until you generate new test execution files.</span></span>
> 
> ![Polecenie Generuj tylko pliki wykonania testu w menu Nowy](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a><span data-ttu-id="ef5a7-180">Migawka</span><span class="sxs-lookup"><span data-stu-id="ef5a7-180">Snapshot</span></span>

<span data-ttu-id="ef5a7-181">Ta funkcja wykonuje zrzuty ekranu czynności, które zostały wykonane podczas rejestrowania zadań.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-181">This feature takes screenshots of the steps that were performed during task recording.</span></span>

- <span data-ttu-id="ef5a7-182">Aby skorzystać z tej funkcji, należy otworzyć plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-182">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="ef5a7-183">W obszarze **C:\\użytkownicy\\\<nazwa użytkownika\>\\AppData\\mobilny\\regressionTool\\playback** jest tworzony oddzielny folder dla każdego uruchomionego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-183">Under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

![Folder migawek dla przypadku testowego](./media/use_rsa_tool_12.png)

<span data-ttu-id="ef5a7-185">W każdym z tych folderów można znaleźć migawki kroków, które zostały wykonane w trakcie wykonywania przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-185">In each of these folders, you can find snapshots of the steps that were performed while the test cases were run.</span></span>

![Pliki migawek](./media/use_rsa_tool_13.png)

## <a name="assignment"></a><span data-ttu-id="ef5a7-187">Przypisanie</span><span class="sxs-lookup"><span data-stu-id="ef5a7-187">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="ef5a7-188">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="ef5a7-188">Scenario</span></span>

1. <span data-ttu-id="ef5a7-189">Konstruktor produktów tworzy nowy wydany produkt.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-189">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="ef5a7-190">Menedżer produkcji inicjuje zlecenie produkcyjne w celu przeniesienia poziomu zapasów do dwóch sztuk.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-190">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="ef5a7-191">Produkcja rozpoczyna się i kończy zlecenie produkcyjne oraz sprawdza, czy ilość dostępnych zapasów wynosi dwie sztuki.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-191">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="ef5a7-192">Zespół sprzedaży otrzymuje zamówienie na cztery części nowego produktu.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-192">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="ef5a7-193">Z tego względu zespół sprzedaży aktualizuje zapotrzebowanie netto za pośrednictwem planu dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-193">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="ef5a7-194">Ponieważ żadne dodatkowe zdolności produkcyjne nie są dostępne, domyślną zasadą zamówienia jest „Kup zamiast robić”.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-194">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="ef5a7-195">W związku z tym zostanie utworzone zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-195">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="ef5a7-196">Kupujący dodaje dostawcę, wiąże planowane zamówienie zakupu, a następnie potwierdza zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-196">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="ef5a7-197">Gdy towary, które zostały nabyte, dotarły do sklepu, operator sklepu przeszukuje powiązane zamówienie zakupu i odbiera towary.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-197">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="ef5a7-198">Zamówienie jest teraz ukończone, towary można pobrać i zapakować w związku z zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-198">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="ef5a7-199">Pole finanse księguje fakturę zakupu i fakturę sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-199">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="ef5a7-200">Na poniższej ilustracji przedstawiono proces dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-200">The following illustration shows the flow for this scenario.</span></span>

![Proces dla scenariusza pokazu](./media/use_rsa_tool_14.png)

<span data-ttu-id="ef5a7-202">Na poniższej ilustracji przedstawiono proces biznesowy dla tego scenariusza w RSAT.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-202">The following illustration shows the business processes for this scenario in RSAT.</span></span>

![Procesy biznesowe dla scenariusza pokazu](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="ef5a7-204">Strategia — nauka najważniejszych</span><span class="sxs-lookup"><span data-stu-id="ef5a7-204">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="ef5a7-205">Dane</span><span class="sxs-lookup"><span data-stu-id="ef5a7-205">Data</span></span>

- <span data-ttu-id="ef5a7-206">Upewnij się, że istnieją reprezentatywne woluminy danych (kopie danych konfiguracji produkcji/złota plus dane zmigrowane).</span><span class="sxs-lookup"><span data-stu-id="ef5a7-206">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="ef5a7-207">Podczas generowania nowych danych za pomocą rejestratora zadań należy utworzyć nazwy testowe, które nie powodują konfliktu z istniejącymi nazwami (na przykład, należy zastosować prefiks jak **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="ef5a7-207">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="ef5a7-208">Za pomocą funkcji przywracania punktów na platformie Azure uruchom ponownie testy w środowiskach spoza warstwy 1.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-208">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="ef5a7-209">Chociaż można skorzystać z funkcji Excel **LOSOWO** i **TERAZ**, to aby wygenerować unikatową kombinację, nakład pracy jest znacznie wysoki.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-209">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="ef5a7-210">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-210">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="ef5a7-211">Rejestrator zadań</span><span class="sxs-lookup"><span data-stu-id="ef5a7-211">Task recorder</span></span>

- <span data-ttu-id="ef5a7-212">Przed rozpoczęciem rejestrowania zdefiniuj scenariusze.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-212">Define scenarios before you start recording.</span></span> <span data-ttu-id="ef5a7-213">Dobrze zarządzany projekt ma wstępnie zdefiniowane scenariusze testowania.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-213">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="ef5a7-214">Aby zbudować przypadek testowy, należy rozważyć przewidywany wynik tych scenariuszy testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-214">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="ef5a7-215">Podziel nagrania, jeśli są wykonywane przez różne role lub jeśli istnieje czas oczekiwania lub zdarzenie zewnętrzne przed wykonaniem następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-215">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="ef5a7-216">Należy unikać wybierania wartości na listach.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-216">Avoid selecting values in lists.</span></span> <span data-ttu-id="ef5a7-217">Zamiast tego należy użyć formatów tekstu, takich jak **FIFO**, **AudioRM** i **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-217">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="ef5a7-218">Po wybraniu opcji na liście zostanie zarejestrowana pozycja wartości na liście, a nie sama wartość.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-218">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="ef5a7-219">Jeśli do tej listy zostaną dodane pozycje, może zmienić się pozycja wartości.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-219">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="ef5a7-220">Z tego względu nagranie będzie używało innego parametru i może mieć wpływ na pozostałą część scenariusza.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-220">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="ef5a7-221">Należy zastanowić się nad zachowaniem wielu użytkowników.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-221">Think about multi-user behavior.</span></span> <span data-ttu-id="ef5a7-222">Na przykład nie zakłada się, że nowo utworzone zamówienie sprzedaży zawsze będzie wybierane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-222">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="ef5a7-223">Zamiast tego należy zawsze używać filtru, aby odnaleźć właściwe zamówienie.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-223">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="ef5a7-224">W celu zapisania nazwy nowo utworzonego produktu należy użyć funkcji Kopiuj w rejestratorze zadań, aby można było jej użyć w łańcuchach przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-224">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="ef5a7-225">Funkcja sprawdzania poprawności w rejestratorze zadań umożliwia ustawienie punktów kontrolnych, które weryfikują poprawność działania kroków.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-225">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="ef5a7-226">RSAT</span><span class="sxs-lookup"><span data-stu-id="ef5a7-226">RSAT</span></span>

- <span data-ttu-id="ef5a7-227">Aby uruchomić test w innej firmie, można zmienić firmę na karcie **ogólne** w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-227">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="ef5a7-228">Upewnij się, że ustawienia i dane są dostępne w nowo wybranej firmie.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-228">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="ef5a7-229">Użytkownik testowy można zmienić na karcie **ogólne** w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-229">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="ef5a7-230">Określ identyfikator e-mail użytkownika, który uruchomi przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-230">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="ef5a7-231">W ten sposób można uruchomić przypadek testowy przy użyciu uprawnień zabezpieczeń określonego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-231">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="ef5a7-232">Aby poczekać przed rozpoczęciem testu, można zdefiniować pauzę na karcie **ogólne** pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-232">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="ef5a7-233">To wstrzymanie może być używane w zadaniu wsadowym (na przykład, jeśli proces przepływu pracy musi zostać wykonany, aby można było wykonać następny krok)</span><span class="sxs-lookup"><span data-stu-id="ef5a7-233">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="ef5a7-234">Zaawansowane skrypty</span><span class="sxs-lookup"><span data-stu-id="ef5a7-234">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="ef5a7-235">Wiersz poleceń</span><span class="sxs-lookup"><span data-stu-id="ef5a7-235">CLI</span></span>

<span data-ttu-id="ef5a7-236">RSAT można wywołać z poziomu okna **Wiersz poleceń** lub **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-236">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="ef5a7-237">Sprawdź, czy zmienna środowiskowa **TestRoot** jest ustawiona jako ścieżka instalacji pakietu RSAT.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-237">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="ef5a7-238">(W systemie Microsoft Windows otwórz **panel sterowania**, wybierz **System i zabezpieczenia  \> System \> Zaawansowane ustawienia systemu**, a następnie wybierz **zmienne środowiskowe**).</span><span class="sxs-lookup"><span data-stu-id="ef5a7-238">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="ef5a7-239">Otwórz okno **Wiersz poleceń** lub **PowerShell** jako administrator.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-239">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="ef5a7-240">Przejdź do katalogu instalacyjnego narzędzia RSAT.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-240">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="ef5a7-241">Lista wszystkich poleceń.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-241">List all commands.</span></span>

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

#### <a name=""></a><span data-ttu-id="ef5a7-242">?</span><span class="sxs-lookup"><span data-stu-id="ef5a7-242">?</span></span> 
<span data-ttu-id="ef5a7-243">Pokazuje pomoc dotyczącą wszystkich dostępnych poleceń i ich parametrów.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-243">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="ef5a7-244">Parametry opcjonalne</span><span class="sxs-lookup"><span data-stu-id="ef5a7-244">Optional parameters</span></span>

**``command``**


<span data-ttu-id="ef5a7-245">Gdzie ``[command]`` jest jednym z poleceń określonych poniżej.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-245">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="ef5a7-246">informacje</span><span class="sxs-lookup"><span data-stu-id="ef5a7-246">about</span></span>
<span data-ttu-id="ef5a7-247">Wyświetla obecną wersję.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-247">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="ef5a7-248">cls</span><span class="sxs-lookup"><span data-stu-id="ef5a7-248">cls</span></span>
<span data-ttu-id="ef5a7-249">Czyści ekran.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-249">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="ef5a7-250">pobierz</span><span class="sxs-lookup"><span data-stu-id="ef5a7-250">download</span></span>
<span data-ttu-id="ef5a7-251">Pobiera załączniki dla określonego przypadku testowego do katalogu wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-251">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="ef5a7-252">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-252">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="ef5a7-253">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-253">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-254">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-254">Required parameters</span></span>
<span data-ttu-id="ef5a7-255">**``test_case_id``** Przedstawia identyfikator przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-255">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="ef5a7-256">**``output_dir``** Reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-256">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="ef5a7-257">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-257">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-258">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-258">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="ef5a7-259">edycja</span><span class="sxs-lookup"><span data-stu-id="ef5a7-259">edit</span></span>
<span data-ttu-id="ef5a7-260">Umożliwia otwieranie pliku parametrów w programie Excel i edytowanie go.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-260">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-261">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-261">Required parameters</span></span>
<span data-ttu-id="ef5a7-262">**``excel_file``** Musi zawierać pełną ścieżkę do istniejącego pliku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-262">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-263">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-263">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="ef5a7-264">generate</span><span class="sxs-lookup"><span data-stu-id="ef5a7-264">generate</span></span>
<span data-ttu-id="ef5a7-265">Generuje pliki wykonania testu i parametry dla określonego przypadku testowego w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-265">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="ef5a7-266">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-266">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="ef5a7-267">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-267">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-268">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-268">Required parameters</span></span>
<span data-ttu-id="ef5a7-269">**``test_case_id``** Przedstawia identyfikator przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-269">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="ef5a7-270">**``output_dir``** Reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-270">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="ef5a7-271">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-271">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-272">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-272">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="ef5a7-273">generatederived</span><span class="sxs-lookup"><span data-stu-id="ef5a7-273">generatederived</span></span>
<span data-ttu-id="ef5a7-274">Generuje nowy przypadek testowy pochodzący z dostarczonego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-274">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="ef5a7-275">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-275">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="ef5a7-276">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-276">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-277">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-277">Required parameters</span></span>
<span data-ttu-id="ef5a7-278">**``parent_test_case_id``** Przedstawia identyfikator nadrzędnego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-278">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="ef5a7-279">**``test_plan_id``** Przedstawia identyfikator planu testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-279">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="ef5a7-280">**``test_suite_id``** Przedstawia identyfikator zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-280">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-281">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-281">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="ef5a7-282">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="ef5a7-282">generatetestonly</span></span>
<span data-ttu-id="ef5a7-283">Generuje tylko plik wykonania testu dla określonego przypadku testowego w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-283">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="ef5a7-284">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-284">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="ef5a7-285">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-285">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-286">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-286">Required parameters</span></span>
<span data-ttu-id="ef5a7-287">**``test_case_id``** Przedstawia identyfikator przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-287">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="ef5a7-288">**``output_dir``** Reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-288">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="ef5a7-289">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-289">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-290">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-290">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="ef5a7-291">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="ef5a7-291">generatetestsuite</span></span>
<span data-ttu-id="ef5a7-292">Generuje wszystkie przypadki testowe dla określonego zestawu w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-292">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="ef5a7-293">Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-293">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="ef5a7-294">Jako parametru **test_suiye_id** należy zastosować dowolną wartość z kolumny.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-294">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-295">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-295">Required parameters</span></span>
<span data-ttu-id="ef5a7-296">**``test_suite_name``** Przedstawia nazwę zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-296">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="ef5a7-297">**``output_dir``** Reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-297">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="ef5a7-298">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-298">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-299">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-299">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="ef5a7-300">help</span><span class="sxs-lookup"><span data-stu-id="ef5a7-300">help</span></span>
<span data-ttu-id="ef5a7-301">Identyczny z [?](####?)</span><span class="sxs-lookup"><span data-stu-id="ef5a7-301">Identical to the [?](####?)</span></span> <span data-ttu-id="ef5a7-302">command</span><span class="sxs-lookup"><span data-stu-id="ef5a7-302">command</span></span>


#### <a name="list"></a><span data-ttu-id="ef5a7-303">liście</span><span class="sxs-lookup"><span data-stu-id="ef5a7-303">list</span></span>
<span data-ttu-id="ef5a7-304">Umożliwia wyświetlenie listy wszystkich dostępnych przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-304">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="ef5a7-305">listtestplans</span><span class="sxs-lookup"><span data-stu-id="ef5a7-305">listtestplans</span></span>
<span data-ttu-id="ef5a7-306">Umożliwia wyświetlenie listy wszystkich dostępnych planów testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-306">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="ef5a7-307">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="ef5a7-307">listtestsuite</span></span>
<span data-ttu-id="ef5a7-308">Wyświetla przypadki testowe dla określonego zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-308">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="ef5a7-309">Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="ef5a7-310">Jako parametru **suite_name** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-311">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-311">Required parameters</span></span>
<span data-ttu-id="ef5a7-312">**``suite_name``** Nazwa żądanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-313">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-313">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="ef5a7-314">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="ef5a7-314">listtestsuitenames</span></span>
<span data-ttu-id="ef5a7-315">Umożliwia wyświetlenie listy wszystkich dostępnych zestawów testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-315">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="ef5a7-316">playback</span><span class="sxs-lookup"><span data-stu-id="ef5a7-316">playback</span></span>
<span data-ttu-id="ef5a7-317">Umożliwia ponowne odtworzenie przypadku testowego w pliku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-317">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-318">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-318">Required parameters</span></span>
<span data-ttu-id="ef5a7-319">**``excel_file``** Pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-319">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="ef5a7-320">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-320">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="ef5a7-321">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-321">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="ef5a7-322">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="ef5a7-322">playbackbyid</span></span>
<span data-ttu-id="ef5a7-323">Umożliwia jednoczesne odtworzenie wielu przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-323">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="ef5a7-324">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-324">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="ef5a7-325">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-325">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-326">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-326">Required parameters</span></span>
<span data-ttu-id="ef5a7-327">**``test_case_id1``** Identyfikator dla istniejących przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-327">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="ef5a7-328">**``test_case_id2``** Identyfikator dla istniejących przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-328">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="ef5a7-329">**``test_case_idN``** Identyfikator dla istniejących przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-329">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="ef5a7-330">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-330">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="ef5a7-331">playbackmany</span><span class="sxs-lookup"><span data-stu-id="ef5a7-331">playbackmany</span></span>
<span data-ttu-id="ef5a7-332">Umożliwia jednoczesne odtwarzanie wielu przypadków testowych przy użyciu plików programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-332">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-333">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-333">Required parameters</span></span>
<span data-ttu-id="ef5a7-334">**``excel_file1``** Pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-334">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="ef5a7-335">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-335">File must exist.</span></span>  
<span data-ttu-id="ef5a7-336">**``excel_file2``** Pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-336">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="ef5a7-337">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-337">File must exist.</span></span>  
<span data-ttu-id="ef5a7-338">**``excel_fileN``** Pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-338">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="ef5a7-339">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-339">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="ef5a7-340">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-340">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="ef5a7-341">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="ef5a7-341">playbacksuite</span></span>
<span data-ttu-id="ef5a7-342">Odtwarza wszystkie przypadki testowe z określonego zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-342">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="ef5a7-343">Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-343">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="ef5a7-344">Jako parametru **suite_name** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-344">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-345">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-345">Required parameters</span></span>
<span data-ttu-id="ef5a7-346">**``suite_name``** Nazwa żądanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-346">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-347">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-347">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="ef5a7-348">quit</span><span class="sxs-lookup"><span data-stu-id="ef5a7-348">quit</span></span>
<span data-ttu-id="ef5a7-349">Zamyka aplikację.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-349">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="ef5a7-350">upload</span><span class="sxs-lookup"><span data-stu-id="ef5a7-350">upload</span></span>
<span data-ttu-id="ef5a7-351">Umożliwia przekazanie wszystkich plików należących do określonego zestawu testów lub przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-351">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="ef5a7-352">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-352">Required parameters</span></span>
<span data-ttu-id="ef5a7-353">**``suite_name``** Wszystkie pliki należące do określonego zestawu testów zostaną przesłane.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-353">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="ef5a7-354">**``testcase_id``** Wszystkie pliki należące do określonego przypadku testowego (przypadków testowych) zostaną przesłane.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-354">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-355">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-355">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="ef5a7-356">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="ef5a7-356">uploadrecording</span></span>
<span data-ttu-id="ef5a7-357">Umożliwia przekazanie tylko pliku nagrania należącego do określonych przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-357">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="ef5a7-358">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="ef5a7-358">Required parameters</span></span>
<span data-ttu-id="ef5a7-359">**``testcase_id``** Plik nagrania należący do określonych przypadków testowych zostanie przesłany.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-359">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="ef5a7-360">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ef5a7-360">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="ef5a7-361">usage</span><span class="sxs-lookup"><span data-stu-id="ef5a7-361">usage</span></span>
<span data-ttu-id="ef5a7-362">Pokazuje dwa sposoby wywoływania tej aplikacji: jeden przy użyciu pliku ustawień domyślnych oraz drugi, który udostępnia plik ustawień.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-362">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="ef5a7-363">Przykłady środowiska Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef5a7-363">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="ef5a7-364">Uruchamianie przypadku testowego w pętli</span><span class="sxs-lookup"><span data-stu-id="ef5a7-364">Run a test case in a loop</span></span>

<span data-ttu-id="ef5a7-365">Masz skrypt testowy, który tworzy nowego klienta.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-365">You have a test script that creates a new customer.</span></span> <span data-ttu-id="ef5a7-366">Za pomocą skryptów ten przypadek testowy można uruchomić w pętli, tworząc losowo następujące dane przed uruchomieniem każdej iteracji:</span><span class="sxs-lookup"><span data-stu-id="ef5a7-366">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="ef5a7-367">Identyfikator odbiorcy</span><span class="sxs-lookup"><span data-stu-id="ef5a7-367">Customer ID</span></span>
- <span data-ttu-id="ef5a7-368">Nazwa odbiorcy</span><span class="sxs-lookup"><span data-stu-id="ef5a7-368">Customer name</span></span>
- <span data-ttu-id="ef5a7-369">Adres odbiorcy</span><span class="sxs-lookup"><span data-stu-id="ef5a7-369">Customer address</span></span>

<span data-ttu-id="ef5a7-370">Identyfikator odbiorcy będzie w formacie *ATCUS\<liczba\>*, gdzie \<liczba\> jest wartością z zakresu od **000000001** do **999999999**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-370">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="ef5a7-371">W poniższym przykładzie użyto jednego parametru, **Start**, aby zdefiniować pierwszy użyty numer.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-371">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="ef5a7-372">Do zdefiniowania liczby odbiorców używany jest drugi paramentr **nr**, który musi być utworzony.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-372">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="ef5a7-373">W przypadku każdej iteracji parametry w pliku parametrów programu Excel są zmieniane za pomocą funkcji UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-373">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="ef5a7-374">Następnie wiersz polecenia RSAT jest wywoływany w funkcji RunTestCase</span><span class="sxs-lookup"><span data-stu-id="ef5a7-374">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="ef5a7-375">Otwórz środowisko Microsoft Windows PowerShell Integrated Scripting Environment (ISE) w trybie administratora i wklej następujący kod do okna o nazwie **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-375">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

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

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="ef5a7-376">Uruchom skrypt zależny od danych w Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ef5a7-376">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="ef5a7-377">W poniższym przykładzie użyto wywołania protokołu OData (Open Data Protocol) w celu znalezienia stanu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-377">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="ef5a7-378">Jeśli stan nie jest **fakturowany**, można na przykład wywołać przypadek testowy narzędzia RSAT, które zaksięguje fakturę.</span><span class="sxs-lookup"><span data-stu-id="ef5a7-378">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

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
