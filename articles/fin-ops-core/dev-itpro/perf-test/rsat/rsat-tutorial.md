---
title: Samouczek narzędzia Regression Suite Automation Tool
description: W tym temacie przedstawiono sposób użycia narzędzia Regression suite automation tool (RSAT). Opisuje on różne funkcje i zawiera przykłady korzystania z funkcji zaawansowanego tworzenia skryptów.
author: robinarh
manager: AnnBe
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: b8866d43ea8b6b6bea34c01cbcbc9e3575081c4c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568387"
---
# <a name="regression-suite-automation-tool-tutorial"></a><span data-ttu-id="9d9a8-104">Samouczek narzędzia Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="9d9a8-104">Regression suite automation tool tutorial</span></span>

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="9d9a8-105">Tę stronę można pobrać i zapisać w formacie PDF przy użyciu narzędzi dostępnych w przeglądarce internetowej.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-105">Use your internet browser tools to download and save this page in pdf format.</span></span>

<span data-ttu-id="9d9a8-106">Ten samouczek dotyczy niektórych zaawansowanych funkcji narzędzia Regression suite automation tool (RSAT), który zawiera przypisanie demonstracyjne oraz opisuje strategię i najważniejsze punkty szkoleniowe.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="notable-features-of-rsat-and-task-recorder"></a><span data-ttu-id="9d9a8-107">Funkcje narzędzi RSAT i Rejestratora zadań</span><span class="sxs-lookup"><span data-stu-id="9d9a8-107">Notable Features of RSAT and Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="9d9a8-108">Sprawdź wartość pola</span><span class="sxs-lookup"><span data-stu-id="9d9a8-108">Validate a field value</span></span>

<span data-ttu-id="9d9a8-109">Narzędzia RSAT umożliwiają uwzględnianie etapów sprawdzania poprawności w ramach testowania w celu weryfikacji oczekiwanych wartości.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-109">RSAT allows you to include validation steps within your test case to validate expected values.</span></span> <span data-ttu-id="9d9a8-110">Aby uzyskać informacje dotyczące tej funkcji, należy zapoznać się z artykułem [Sprawdzanie oczekiwanych wartości](rsat-validate-expected.md).</span><span class="sxs-lookup"><span data-stu-id="9d9a8-110">For information about this feature, see the article [Validate expected values](rsat-validate-expected.md).</span></span>

<span data-ttu-id="9d9a8-111">W poniższym przykładzie pokazano, jak można skorzystać z tej funkcji w celu sprawdzenia, czy dostępne zapasy przekraczają 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="9d9a8-111">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="9d9a8-112">W danych demonstracyjnych firmy **USMF** utwórz nagranie zadań, które mają następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="9d9a8-112">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="9d9a8-113">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-113">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="9d9a8-114">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="9d9a8-115">Na przykład filtruj według pola z wartością **1000** dla **Numeru elementu**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-115">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="9d9a8-116">Wybierz **Dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-116">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="9d9a8-117">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="9d9a8-118">Na przykład wyfiltruj według pola **Oddział** z wartością **1**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-118">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="9d9a8-119">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-119">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="9d9a8-120">Sprawdź, czy wartość pola **W sumie dostępne** to **411.0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-120">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="9d9a8-121">Zapisz nagranie zadania jako **nagranie dewelopera** i dołącz je do przypadku testowego w usłudze Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-121">Save the task recording as a **developer recording** and attach it to your test case in Azure Devops.</span></span>
3. <span data-ttu-id="9d9a8-122">Dodaj przypadek testowy do planu testu i załaduj przypadek testowy do pakietu RSAT.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-122">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="9d9a8-123">Otwórz plik parametrów programu Excel i przejdź na kartę **TestCaseSteps**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-123">Open the Excel parameter file and go to the **TestCaseSteps** tab.</span></span>
5. <span data-ttu-id="9d9a8-124">Aby sprawdzić, czy dostępne zapasy będą zawsze mieć wartość większą niż **0**, przejdź do kroku **sprawdzania sumy dostępnych** i zmień wartość z **411** na **0**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-124">To validate whether the inventory on-hand will always be more than **0**, go to the **Validate Total Available** step and change its value from **411** to **0**.</span></span> <span data-ttu-id="9d9a8-125">Zmień wartość pola **Operator** ze znaku równości (**=**) na znak większości (**\>**).</span><span class="sxs-lookup"><span data-stu-id="9d9a8-125">Change the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>
6. <span data-ttu-id="9d9a8-126">Zapisz i zamknij plik parametrów w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-126">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="9d9a8-127">Kliknij przycisk **Przekaż**, aby zapisać dokonane zmiany w pliku parametrów programu Excel w Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-127">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="9d9a8-128">Jeśli wartość w polu **Łączna ilość dostępna** dla określonego towaru w magazynie jest większa od 0 (zero), testy zostaną przekazane niezależnie od wartości rzeczywistej dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-128">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="saved-variables-and-chaining-of-test-cases"></a><span data-ttu-id="9d9a8-129">Zapisane zmienne i łańcuchy przypadków testowych</span><span class="sxs-lookup"><span data-stu-id="9d9a8-129">Saved variables and chaining of test cases</span></span>

<span data-ttu-id="9d9a8-130">Jedną z najważniejszych funkcji narzędzia RSAT jest łączenie przypadków testowych w łańcuchy (to znaczy zdolność testu do przekazywania zmiennych do innych testów).</span><span class="sxs-lookup"><span data-stu-id="9d9a8-130">One of the key features of RSAT is the chaining of test cases, that is, the ability of a test to pass variables to other tests.</span></span> <span data-ttu-id="9d9a8-131">Aby uzyskać więcej informacji, zajrzyj do artykułu [Skopiuj zmienne do łańcuchowych przypadków testowych](rsat-chain-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="9d9a8-131">For more information, see the article [Copy variables to chain test cases](rsat-chain-test-cases.md).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="9d9a8-132">Pochodny przypadek testowy</span><span class="sxs-lookup"><span data-stu-id="9d9a8-132">Derived test case</span></span>

<span data-ttu-id="9d9a8-133">Narzędzia RSAT umożliwiają korzystanie z tego samego zapisu zadań w wielu przypadkach testowych, umożliwiając uruchamianie zadań z różnymi konfiguracjami danych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-133">RSAT lets you use the same task recording with multiple test cases, enabling a task to run with different data configurations.</span></span> <span data-ttu-id="9d9a8-134">Aby uzyskać więcej informacji, zajrzyj do artykułu [Przypadki testu pochodnego](rsat-derived-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="9d9a8-134">See the article [Derived test cases](rsat-derived-test-cases.md) for more information.</span></span>

### <a name="validate-notifications-and-messages"></a><span data-ttu-id="9d9a8-135">Sprawdzanie poprawności powiadomień i komunikatów</span><span class="sxs-lookup"><span data-stu-id="9d9a8-135">Validate notifications and messages</span></span>

<span data-ttu-id="9d9a8-136">Za pomocą tej funkcji można sprawdzić, czy akcja wystąpiła.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-136">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="9d9a8-137">Na przykład podczas tworzenia zlecenia produkcyjnego, szacowanego, a następnie rozpoczętego, aplikacja wyświetla komunikat „produkcja – rozpoczęcie” informujący o rozpoczęciu zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-137">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Produkcja — Powiadomienie o rozpoczęciu](./media/use_rsa_tool_05.png)

<span data-ttu-id="9d9a8-139">Można sprawdzić poprawność tej wiadomości za pośrednictwem narzędzia RSAT, wprowadzając tekst **Weryfikacja komunikatu** na karcie pliku parametrów programu Excel w celu odpowiedniego nagrania.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-139">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Karta weryfikacji komunikatu](./media/use_rsa_tool_06.png)

<span data-ttu-id="9d9a8-141">Po uruchomieniu przypadku testowego komunikat w pliku parametrów programu Excel jest porównywany z komunikatem wyświetlanym.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-141">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="9d9a8-142">Jeśli wiadomości nie pasują do siebie, przypadek testowy nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-142">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="9d9a8-143">Można wprowadzić więcej niż jedną wiadomość na karcie **Weryfikacja komunikatu** w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-143">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="9d9a8-144">Komunikatami mogą być także komunikaty o błędach lub ostrzeżenia, a nie komunikaty informacyjne.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-144">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="snapshot"></a><span data-ttu-id="9d9a8-145">Migawka</span><span class="sxs-lookup"><span data-stu-id="9d9a8-145">Snapshot</span></span>

<span data-ttu-id="9d9a8-146">Ta funkcja wykonuje zrzuty ekranu czynności, które zostały wykonane podczas rejestrowania zadań.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-146">This feature takes screenshots of the steps that were performed during task recording.</span></span> <span data-ttu-id="9d9a8-147">Jest on przydatny do celów inspekcji lub debugowania.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-147">It is useful for auditing or debugging purposes.</span></span>

- <span data-ttu-id="9d9a8-148">Aby skorzystać z tej funkcji, należy otworzyć plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-148">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="9d9a8-149">Po uruchomieniu przypadku testowego narzędzia RSAT generują migawki (obrazy) kroków w folderze odtwarzania przypadków testowych w katalogu roboczym.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-149">When your run the test case, RSAT will generate snapshots (images) of the steps in the playback folder of the test cases in the working diretory.</span></span> <span data-ttu-id="9d9a8-150">Jeśli używana jest starsza wersja narzędzia RSAT, obrazy są zapisywane w **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, utowrzony jest osobny folder dla każdego uruchomionego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-150">If you are using an older version of RSAT, the images are saved to **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

## <a name="assignment"></a><span data-ttu-id="9d9a8-151">Przypisanie</span><span class="sxs-lookup"><span data-stu-id="9d9a8-151">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="9d9a8-152">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="9d9a8-152">Scenario</span></span>

1. <span data-ttu-id="9d9a8-153">Konstruktor produktów tworzy nowy wydany produkt.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-153">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="9d9a8-154">Menedżer produkcji inicjuje zlecenie produkcyjne w celu przeniesienia poziomu zapasów do dwóch sztuk.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-154">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="9d9a8-155">Produkcja rozpoczyna się i kończy zlecenie produkcyjne oraz sprawdza, czy ilość dostępnych zapasów wynosi dwie sztuki.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-155">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="9d9a8-156">Zespół sprzedaży otrzymuje zamówienie na cztery części nowego produktu.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-156">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="9d9a8-157">Z tego względu zespół sprzedaży aktualizuje zapotrzebowanie netto za pośrednictwem planu dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-157">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="9d9a8-158">Ponieważ żadne dodatkowe zdolności produkcyjne nie są dostępne, domyślną zasadą zamówienia jest „Kup zamiast robić”.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-158">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="9d9a8-159">W związku z tym zostanie utworzone zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-159">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="9d9a8-160">Kupujący dodaje dostawcę, wiąże planowane zamówienie zakupu, a następnie potwierdza zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-160">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="9d9a8-161">Gdy towary, które zostały nabyte, dotarły do sklepu, operator sklepu przeszukuje powiązane zamówienie zakupu i odbiera towary.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-161">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="9d9a8-162">Zamówienie jest teraz ukończone, towary można pobrać i zapakować w związku z zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-162">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="9d9a8-163">Pole finanse księguje fakturę zakupu i fakturę sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-163">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="9d9a8-164">Na poniższej ilustracji przedstawiono proces dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-164">The following illustration shows the flow for this scenario.</span></span>

![Proces dla scenariusza pokazu](./media/use_rsa_tool_14.png)

<span data-ttu-id="9d9a8-166">Na poniższej ilustracji przedstawiono hierarchię procesów biznesowych dla tego scenariusza w narzędziu do modelowania procesów biznesowych usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-166">The following illustration shows the business processes hierarchy for this scenario in the LCS Business Process Modeler.</span></span>

![Procesy biznesowe dla scenariusza pokazu](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="9d9a8-168">Strategia — nauka najważniejszych</span><span class="sxs-lookup"><span data-stu-id="9d9a8-168">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="9d9a8-169">Dane</span><span class="sxs-lookup"><span data-stu-id="9d9a8-169">Data</span></span>

- <span data-ttu-id="9d9a8-170">Upewnij się, że istnieją reprezentatywne woluminy danych (kopie danych konfiguracji produkcji/złota plus dane zmigrowane).</span><span class="sxs-lookup"><span data-stu-id="9d9a8-170">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="9d9a8-171">Podczas generowania nowych danych za pomocą rejestratora zadań należy utworzyć nazwy testowe, które nie powodują konfliktu z istniejącymi nazwami (na przykład, należy zastosować prefiks jak **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="9d9a8-171">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="9d9a8-172">Za pomocą funkcji przywracania punktów na platformie Azure uruchom ponownie testy w środowiskach spoza warstwy 1.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-172">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="9d9a8-173">Chociaż można skorzystać z funkcji Excel **LOSOWO** i **TERAZ**, to aby wygenerować unikatową kombinację, nakład pracy jest znacznie wysoki.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-173">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="9d9a8-174">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-174">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="9d9a8-175">Rejestrator zadań</span><span class="sxs-lookup"><span data-stu-id="9d9a8-175">Task recorder</span></span>

- <span data-ttu-id="9d9a8-176">Przed rozpoczęciem rejestrowania zdefiniuj scenariusze.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-176">Define scenarios before you start recording.</span></span> <span data-ttu-id="9d9a8-177">Dobrze zarządzany projekt ma wstępnie zdefiniowane scenariusze testowania.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-177">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="9d9a8-178">Aby zbudować przypadek testowy, należy rozważyć przewidywany wynik tych scenariuszy testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-178">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="9d9a8-179">Podziel nagrania, jeśli są wykonywane przez różne role lub jeśli istnieje czas oczekiwania lub zdarzenie zewnętrzne przed wykonaniem następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-179">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="9d9a8-180">Należy unikać wybierania wartości na listach.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-180">Avoid selecting values in lists.</span></span> <span data-ttu-id="9d9a8-181">Zamiast tego należy użyć formatów tekstu, takich jak **FIFO**, **AudioRM** i **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-181">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="9d9a8-182">Po wybraniu opcji na liście zostanie zarejestrowana pozycja wartości na liście, a nie sama wartość.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-182">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="9d9a8-183">Jeśli do tej listy zostaną dodane pozycje, może zmienić się pozycja wartości.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-183">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="9d9a8-184">Z tego względu nagranie będzie używało innego parametru i może mieć wpływ na pozostałą część scenariusza.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-184">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="9d9a8-185">Należy zastanowić się nad zachowaniem wielu użytkowników.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-185">Think about multi-user behavior.</span></span> <span data-ttu-id="9d9a8-186">Na przykład nie zakłada się, że nowo utworzone zamówienie sprzedaży zawsze będzie wybierane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-186">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="9d9a8-187">Zamiast tego należy zawsze używać filtru, aby odnaleźć właściwe zamówienie.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-187">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="9d9a8-188">W celu zapisania nazwy nowo utworzonego produktu należy użyć funkcji Kopiuj w rejestratorze zadań, aby można było jej użyć w łańcuchach przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-188">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="9d9a8-189">Funkcja sprawdzania poprawności w rejestratorze zadań umożliwia ustawienie punktów kontrolnych, które weryfikują poprawność działania kroków.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-189">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="9d9a8-190">RSAT</span><span class="sxs-lookup"><span data-stu-id="9d9a8-190">RSAT</span></span>

- <span data-ttu-id="9d9a8-191">Aby uruchomić test w innej firmie, można zmienić firmę na karcie **ogólne** w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-191">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="9d9a8-192">Upewnij się, że ustawienia i dane są dostępne w nowo wybranej firmie.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-192">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="9d9a8-193">Użytkownik testowy można zmienić na karcie **ogólne** w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-193">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="9d9a8-194">Określ identyfikator e-mail użytkownika, który uruchomi przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-194">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="9d9a8-195">W ten sposób można uruchomić przypadek testowy przy użyciu uprawnień zabezpieczeń określonego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-195">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="9d9a8-196">Aby poczekać przed rozpoczęciem testu, można zdefiniować pauzę na karcie **ogólne** pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-196">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="9d9a8-197">To wstrzymanie może być używane w zadaniu wsadowym (na przykład, jeśli proces przepływu pracy musi zostać wykonany, aby można było wykonać następny krok)</span><span class="sxs-lookup"><span data-stu-id="9d9a8-197">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="9d9a8-198">Zaawansowane skrypty</span><span class="sxs-lookup"><span data-stu-id="9d9a8-198">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="9d9a8-199">Wiersz poleceń</span><span class="sxs-lookup"><span data-stu-id="9d9a8-199">CLI</span></span>

<span data-ttu-id="9d9a8-200">RSAT można wywołać z poziomu okna **Wiersz poleceń** lub **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-200">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="9d9a8-201">Sprawdź, czy zmienna środowiskowa **TestRoot** jest ustawiona jako ścieżka instalacji pakietu RSAT.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-201">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="9d9a8-202">(W systemie Microsoft Windows otwórz **panel sterowania**, wybierz **System i zabezpieczenia  \> System \> Zaawansowane ustawienia systemu**, a następnie wybierz **zmienne środowiskowe**).</span><span class="sxs-lookup"><span data-stu-id="9d9a8-202">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="9d9a8-203">Otwórz okno **Wiersz poleceń** lub **PowerShell** jako administrator.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-203">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="9d9a8-204">Przejdź do katalogu instalacyjnego narzędzia RSAT.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-204">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="9d9a8-205">Lista wszystkich poleceń.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-205">List all commands.</span></span>

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

#### <a name=""></a><span data-ttu-id="9d9a8-206">?</span><span class="sxs-lookup"><span data-stu-id="9d9a8-206">?</span></span>

<span data-ttu-id="9d9a8-207">Pokazuje pomoc dotyczącą wszystkich dostępnych poleceń i ich parametrów.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-207">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a><span data-ttu-id="9d9a8-208">?: Parametry opcjonalne</span><span class="sxs-lookup"><span data-stu-id="9d9a8-208">?: Optional parameters</span></span>

<span data-ttu-id="9d9a8-209">`command`: gdzie ``[command]`` jest jednym z poleceń określonych poniżej.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-209">`command`: Where ``[command]`` is one of the commands specified below.</span></span>

#### <a name="about"></a><span data-ttu-id="9d9a8-210">informacje</span><span class="sxs-lookup"><span data-stu-id="9d9a8-210">about</span></span>

<span data-ttu-id="9d9a8-211">Wyświetla obecną wersję.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-211">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="9d9a8-212">cls</span><span class="sxs-lookup"><span data-stu-id="9d9a8-212">cls</span></span>

<span data-ttu-id="9d9a8-213">Czyści ekran.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-213">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a><span data-ttu-id="9d9a8-214">pobierz</span><span class="sxs-lookup"><span data-stu-id="9d9a8-214">download</span></span>

<span data-ttu-id="9d9a8-215">Pobiera załączniki dla określonego przypadku testowego do katalogu wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-215">Downloads attachments for the specified test case to the output directory.</span></span>
<span data-ttu-id="9d9a8-216">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-216">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="9d9a8-217">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-217">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="download-required-parameters"></a><span data-ttu-id="9d9a8-218">download: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-218">download: required parameters</span></span>

+ <span data-ttu-id="9d9a8-219">`test_case_id`: przedstawia identyfikator przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-219">`test_case_id`: Represents the test case ID.</span></span>
+ <span data-ttu-id="9d9a8-220">`output_dir`: reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-220">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="9d9a8-221">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-221">The directory must exist.</span></span>

##### <a name="download-examples"></a><span data-ttu-id="9d9a8-222">download: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-222">download: examples</span></span>

`download 123 c:\temp\rsat`

`download 765 c:\rsat\last`

#### <a name="edit"></a><span data-ttu-id="9d9a8-223">edytuj</span><span class="sxs-lookup"><span data-stu-id="9d9a8-223">edit</span></span>

<span data-ttu-id="9d9a8-224">Umożliwia otwieranie pliku parametrów w programie Excel i edytowanie go.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-224">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a><span data-ttu-id="9d9a8-225">edit: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-225">edit: required parameters</span></span>

+ <span data-ttu-id="9d9a8-226">`excel_file`: musi zawierać pełną ścieżkę do istniejącego pliku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-226">`excel_file`: Must contain a full path to an existing Excel file.</span></span>

##### <a name="edit-examples"></a><span data-ttu-id="9d9a8-227">edit: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-227">edit: examples</span></span>

`edit c:\RSAT\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a><span data-ttu-id="9d9a8-228">generate</span><span class="sxs-lookup"><span data-stu-id="9d9a8-228">generate</span></span>

<span data-ttu-id="9d9a8-229">Generuje pliki wykonania testu i parametry dla określonego przypadku testowego w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-229">Generates test execution and parameter files for the specified test case in the output directory.</span></span> <span data-ttu-id="9d9a8-230">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-230">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="9d9a8-231">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-231">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="generate-required-parameters"></a><span data-ttu-id="9d9a8-232">generate: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-232">generate: required parameters</span></span>

+ <span data-ttu-id="9d9a8-233">`test_case_id`: przedstawia identyfikator przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-233">`test_case_id`: Represents the test case ID.</span></span>
+ <span data-ttu-id="9d9a8-234">`output_dir`: reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-234">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="9d9a8-235">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-235">The directory must exist.</span></span>

##### <a name="generate-examples"></a><span data-ttu-id="9d9a8-236">generate: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-236">generate: examples</span></span>

`generate 123 c:\temp\rsat`

`generate 765 c:\rsat\last`

#### <a name="generatederived"></a><span data-ttu-id="9d9a8-237">generatederived</span><span class="sxs-lookup"><span data-stu-id="9d9a8-237">generatederived</span></span>

<span data-ttu-id="9d9a8-238">Generuje nowy przypadek testowy pochodzący z dostarczonego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-238">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="9d9a8-239">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-239">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="9d9a8-240">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-240">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-required-parameters"></a><span data-ttu-id="9d9a8-241">generatederived: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-241">generatederived: required parameters</span></span>

+ <span data-ttu-id="9d9a8-242">`parent_test_case_id`: przedstawia identyfikator nadrzędnego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-242">`parent_test_case_id`: Represents the parent test case ID.</span></span>
+ <span data-ttu-id="9d9a8-243">`test_plan_id`: przedstawia identyfikator planu testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-243">`test_plan_id`: Represents the test plan ID.</span></span>
+ <span data-ttu-id="9d9a8-244">`test_suite_id`: przedstawia identyfikator zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-244">`test_suite_id`: Represents the test suite ID.</span></span>

##### <a name="generatederived-examples"></a><span data-ttu-id="9d9a8-245">generatederived: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-245">generatederived: examples</span></span>

`generatederived 123 8901 678`

#### <a name="generatetestonly"></a><span data-ttu-id="9d9a8-246">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="9d9a8-246">generatetestonly</span></span>

<span data-ttu-id="9d9a8-247">Generuje tylko plik wykonania testu dla określonego przypadku testowego w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-247">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="9d9a8-248">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-248">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="9d9a8-249">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-249">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="generatetestonly-required-parameters"></a><span data-ttu-id="9d9a8-250">generatetestonly: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-250">generatetestonly: required parameters</span></span>

+ <span data-ttu-id="9d9a8-251">`test_case_id`: przedstawia identyfikator przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-251">`test_case_id`: Represents the test case ID.</span></span>
+ <span data-ttu-id="9d9a8-252">`output_dir`: reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-252">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="9d9a8-253">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-253">The directory must exist.</span></span>

##### <a name="generatetestonly-examples"></a><span data-ttu-id="9d9a8-254">generatetestonly: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-254">generatetestonly: examples</span></span>

`generatetestonly 123 c:\temp\rsat`

`generatetestonly 765 c:\rsat\last`

#### <a name="generatetestsuite"></a><span data-ttu-id="9d9a8-255">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="9d9a8-255">generatetestsuite</span></span>

<span data-ttu-id="9d9a8-256">Generuje wszystkie przypadki testowe dla określonego zestawu w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-256">Generates all test cases for the specified suite in the output directory.</span></span> <span data-ttu-id="9d9a8-257">Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-257">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="9d9a8-258">Jako parametru **test_suiye_id** należy zastosować dowolną wartość z kolumny.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-258">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="generatetestsuite-required-parameters"></a><span data-ttu-id="9d9a8-259">generatetestsuite: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-259">generatetestsuite: required parameters</span></span>

+ <span data-ttu-id="9d9a8-260">`test_suite_name`: przedstawia nazwę zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-260">`test_suite_name`: Represents the test suite name.</span></span>
+ <span data-ttu-id="9d9a8-261">`output_dir`: reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-261">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="9d9a8-262">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-262">The directory must exist.</span></span>

##### <a name="generatetestsuite-examples"></a><span data-ttu-id="9d9a8-263">generatetestsuite: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-263">generatetestsuite: examples</span></span>

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite Purchase c:\rsat\last`

#### <a name="help"></a><span data-ttu-id="9d9a8-264">help</span><span class="sxs-lookup"><span data-stu-id="9d9a8-264">help</span></span>

<span data-ttu-id="9d9a8-265">Identyczny z [?](#section)</span><span class="sxs-lookup"><span data-stu-id="9d9a8-265">Identical to the [?](#section)</span></span> <span data-ttu-id="9d9a8-266">polecenie.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-266">command.</span></span>

#### <a name="list"></a><span data-ttu-id="9d9a8-267">liście</span><span class="sxs-lookup"><span data-stu-id="9d9a8-267">list</span></span>

<span data-ttu-id="9d9a8-268">Umożliwia wyświetlenie listy wszystkich dostępnych przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-268">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a><span data-ttu-id="9d9a8-269">listtestplans</span><span class="sxs-lookup"><span data-stu-id="9d9a8-269">listtestplans</span></span>

<span data-ttu-id="9d9a8-270">Umożliwia wyświetlenie listy wszystkich dostępnych planów testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-270">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a><span data-ttu-id="9d9a8-271">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="9d9a8-271">listtestsuite</span></span>

<span data-ttu-id="9d9a8-272">Wyświetla przypadki testowe dla określonego zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-272">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="9d9a8-273">Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-273">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="9d9a8-274">Jako parametru **suite_name** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-274">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="listtestsuite-required-parameters"></a><span data-ttu-id="9d9a8-275">listtestsuite: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-275">listtestsuite: required parameters</span></span>

+ <span data-ttu-id="9d9a8-276">`suite_name`: nazwa żądanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-276">`suite_name`: Name of the desired suite.</span></span>

##### <a name="listtestsuite-examples"></a><span data-ttu-id="9d9a8-277">listtestsuite: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-277">listtestsuite: examples</span></span>

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitenames"></a><span data-ttu-id="9d9a8-278">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="9d9a8-278">listtestsuitenames</span></span>

<span data-ttu-id="9d9a8-279">Umożliwia wyświetlenie listy wszystkich dostępnych zestawów testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-279">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a><span data-ttu-id="9d9a8-280">playback</span><span class="sxs-lookup"><span data-stu-id="9d9a8-280">playback</span></span>

<span data-ttu-id="9d9a8-281">Umożliwia ponowne odtworzenie przypadku testowego w pliku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-281">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="playback-required-parameters"></a><span data-ttu-id="9d9a8-282">playback: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-282">playback: required parameters</span></span>

+ <span data-ttu-id="9d9a8-283">`excel_file`: pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-283">`excel_file`: A full path to the Excel file.</span></span> <span data-ttu-id="9d9a8-284">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-284">File must exist.</span></span>

##### <a name="playback-examples"></a><span data-ttu-id="9d9a8-285">playback: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-285">playback: examples</span></span>

`playback c:\RSAT\TestCaseParameters\sample1.xlsx`

`playback e:\temp\test.xlsx`

#### <a name="playbackbyid"></a><span data-ttu-id="9d9a8-286">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="9d9a8-286">playbackbyid</span></span>

<span data-ttu-id="9d9a8-287">Umożliwia jednoczesne odtworzenie wielu przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-287">Plays back multiple test cases at once.</span></span> <span data-ttu-id="9d9a8-288">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-288">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="9d9a8-289">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-289">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-required-parameters"></a><span data-ttu-id="9d9a8-290">playbackbyid: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-290">playbackbyid: required parameters</span></span>

+ <span data-ttu-id="9d9a8-291">`test_case_id1`: identyfikator dla istniejących przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-291">`test_case_id1`: ID of exisiting test case.</span></span>
+ <span data-ttu-id="9d9a8-292">`test_case_id2`: identyfikator dla istniejących przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-292">`test_case_id2`: ID of exisiting test case.</span></span>
+ <span data-ttu-id="9d9a8-293">`test_case_idN`: identyfikator dla istniejących przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-293">`test_case_idN`: ID of exisiting test case.</span></span>

##### <a name="playbackbyid-examples"></a><span data-ttu-id="9d9a8-294">playbackbyid: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-294">playbackbyid: examples</span></span>

`playbackbyid 878`

`playbackbyid 2345 667 135`

#### <a name="playbackmany"></a><span data-ttu-id="9d9a8-295">playbackmany</span><span class="sxs-lookup"><span data-stu-id="9d9a8-295">playbackmany</span></span>

<span data-ttu-id="9d9a8-296">Umożliwia jednoczesne odtwarzanie wielu przypadków testowych przy użyciu plików programu Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-296">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="playbackmany-required-parameters"></a><span data-ttu-id="9d9a8-297">playbackmany: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-297">playbackmany: required parameters</span></span>

+ <span data-ttu-id="9d9a8-298">`excel_file1`: pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-298">`excel_file1`: Full path to the Excel file.</span></span> <span data-ttu-id="9d9a8-299">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-299">File must exist.</span></span>
+ <span data-ttu-id="9d9a8-300">`excel_file2`: pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-300">`excel_file2`: Full path to the Excel file.</span></span> <span data-ttu-id="9d9a8-301">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-301">File must exist.</span></span>
+ <span data-ttu-id="9d9a8-302">`excel_fileN`: pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-302">`excel_fileN`: Full path to the Excel file.</span></span> <span data-ttu-id="9d9a8-303">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-303">File must exist.</span></span>

##### <a name="playbackmany-examples"></a><span data-ttu-id="9d9a8-304">playbackmany: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-304">playbackmany: examples</span></span>

`playbackmany c:\RSAT\TestCaseParameters\param1.xlsx`

`playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a><span data-ttu-id="9d9a8-305">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="9d9a8-305">playbacksuite</span></span>

<span data-ttu-id="9d9a8-306">Odtwarza wszystkie przypadki testowe z określonego zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-306">Plays back all test cases from the specified test suite.</span></span>
<span data-ttu-id="9d9a8-307">Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-307">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="9d9a8-308">Jako parametru **suite_name** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-308">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="playbacksuite-required-parameters"></a><span data-ttu-id="9d9a8-309">playbacksuite: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-309">playbacksuite: required parameters</span></span>

+ <span data-ttu-id="9d9a8-310">`suite_name`: nazwa żądanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-310">`suite_name`: Name of the desired suite.</span></span>

##### <a name="playbacksuite-examples"></a><span data-ttu-id="9d9a8-311">playbacksuite: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-311">playbacksuite: examples</span></span>

`playbacksuite suiteName`

`playbacksuite sample_suite`

#### <a name="quit"></a><span data-ttu-id="9d9a8-312">quit</span><span class="sxs-lookup"><span data-stu-id="9d9a8-312">quit</span></span>

<span data-ttu-id="9d9a8-313">Zamyka aplikację.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-313">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

#### <a name="upload"></a><span data-ttu-id="9d9a8-314">upload</span><span class="sxs-lookup"><span data-stu-id="9d9a8-314">upload</span></span>

<span data-ttu-id="9d9a8-315">Umożliwia przekazanie wszystkich plików należących do określonego zestawu testów lub przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-315">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="upload-required-parameters"></a><span data-ttu-id="9d9a8-316">upload: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-316">upload: required parameters</span></span>

+ <span data-ttu-id="9d9a8-317">`suite_name`: wszystkie pliki należące do określonego zestawu testów zostaną przesłane.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-317">`suite_name`: All files belonging to the specified test suite will be uploaded.</span></span>
+ <span data-ttu-id="9d9a8-318">`testcase_id`: wszystkie pliki należące do określonego przypadku testowego (przypadków testowych) zostaną przesłane.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-318">`testcase_id`: All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="upload-examples"></a><span data-ttu-id="9d9a8-319">upload: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-319">upload: examples</span></span>

`upload sample_suite`

`upload 123`

`upload 123 456`

#### <a name="uploadrecording"></a><span data-ttu-id="9d9a8-320">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="9d9a8-320">uploadrecording</span></span>

<span data-ttu-id="9d9a8-321">Umożliwia przekazanie tylko pliku nagrania należącego do określonych przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-321">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="uploadrecording-required-parameters"></a><span data-ttu-id="9d9a8-322">uploadrecording: wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="9d9a8-322">uploadrecording: required parameters</span></span>

+ <span data-ttu-id="9d9a8-323">`testcase_id`: plik nagrania należący do określonych przypadków testowych zostanie przesłany.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-323">`testcase_id`: Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="uploadrecording-examples"></a><span data-ttu-id="9d9a8-324">uploadrecording: przykłady</span><span class="sxs-lookup"><span data-stu-id="9d9a8-324">uploadrecording: examples</span></span>

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a><span data-ttu-id="9d9a8-325">usage</span><span class="sxs-lookup"><span data-stu-id="9d9a8-325">usage</span></span>

<span data-ttu-id="9d9a8-326">Pokazuje dwa sposoby wywoływania tej aplikacji: jeden przy użyciu pliku ustawień domyślnych oraz drugi, który udostępnia plik ustawień.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-326">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

### <a name="windows-powershell-examples"></a><span data-ttu-id="9d9a8-327">Przykłady środowiska Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d9a8-327">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="9d9a8-328">Uruchamianie przypadku testowego w pętli</span><span class="sxs-lookup"><span data-stu-id="9d9a8-328">Run a test case in a loop</span></span>

<span data-ttu-id="9d9a8-329">Masz skrypt testowy, który tworzy nowego klienta.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-329">You have a test script that creates a new customer.</span></span> <span data-ttu-id="9d9a8-330">Za pomocą skryptów ten przypadek testowy można uruchomić w pętli, tworząc losowo następujące dane przed uruchomieniem każdej iteracji:</span><span class="sxs-lookup"><span data-stu-id="9d9a8-330">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="9d9a8-331">Identyfikator odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9d9a8-331">Customer ID</span></span>
- <span data-ttu-id="9d9a8-332">Nazwa odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9d9a8-332">Customer name</span></span>
- <span data-ttu-id="9d9a8-333">Adres odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9d9a8-333">Customer address</span></span>

<span data-ttu-id="9d9a8-334">Identyfikator odbiorcy będzie w formacie *ATCUS\<number\>*, gdzie \<number\> jest wartością z zakresu od **000000001** do **999999999**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-334">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="9d9a8-335">W poniższym przykładzie użyto jednego parametru, **Start**, aby zdefiniować pierwszy użyty numer.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-335">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="9d9a8-336">Do zdefiniowania liczby odbiorców używany jest drugi paramentr **nr**, który musi być utworzony.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-336">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="9d9a8-337">W przypadku każdej iteracji parametry w pliku parametrów programu Excel są zmieniane za pomocą funkcji UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-337">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="9d9a8-338">Następnie wiersz polecenia RSAT jest wywoływany w funkcji RunTestCase</span><span class="sxs-lookup"><span data-stu-id="9d9a8-338">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="9d9a8-339">Otwórz środowisko Microsoft Windows PowerShell Integrated Scripting Environment (ISE) w trybie administratora i wklej następujący kod do okna o nazwie **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-339">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

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

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="9d9a8-340">Uruchom skrypt zależny od danych w Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="9d9a8-340">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="9d9a8-341">W poniższym przykładzie użyto wywołania protokołu OData (Open Data Protocol) w celu znalezienia stanu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-341">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="9d9a8-342">Jeśli stan nie jest **fakturowany**, można na przykład wywołać przypadek testowy narzędzia RSAT, które zaksięguje fakturę.</span><span class="sxs-lookup"><span data-stu-id="9d9a8-342">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]