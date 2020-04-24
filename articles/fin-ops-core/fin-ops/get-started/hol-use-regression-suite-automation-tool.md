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
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="f5599-104">Korzystanie z samouczka narzędzia Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="f5599-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="f5599-105">Tę stronę można pobrać i zapisać w formacie PDF przy użyciu narzędzi dostępnych w przeglądarce internetowej.</span><span class="sxs-lookup"><span data-stu-id="f5599-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="f5599-106">Ten samouczek dotyczy niektórych zaawansowanych funkcji narzędzia Regression suite automation tool (RSAT), który zawiera przypisanie demonstracyjne oraz opisuje strategię i najważniejsze punkty szkoleniowe.</span><span class="sxs-lookup"><span data-stu-id="f5599-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span> 

## <a name="notable-features-of-rsat-and-task-recorder"></a><span data-ttu-id="f5599-107">Funkcje narzędzi RSAT i Rejestratora zadań</span><span class="sxs-lookup"><span data-stu-id="f5599-107">Notable Features of RSAT and Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="f5599-108">Sprawdź wartość pola</span><span class="sxs-lookup"><span data-stu-id="f5599-108">Validate a field value</span></span>

<span data-ttu-id="f5599-109">Narzędzia RSAT umożliwiają uwzględnianie etapów sprawdzania poprawności w ramach testowania w celu weryfikacji oczekiwanych wartości.</span><span class="sxs-lookup"><span data-stu-id="f5599-109">RSAT allows you to include validation steps within your test case to validate expected values.</span></span> <span data-ttu-id="f5599-110">Aby uzyskać informacje dotyczące tej funkcji, należy zapoznać się z artykułem [Sprawdzanie oczekiwanych wartości](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span><span class="sxs-lookup"><span data-stu-id="f5599-110">For information about this feature, see the article [Validate expected values](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span></span>

<span data-ttu-id="f5599-111">W poniższym przykładzie pokazano, jak można skorzystać z tej funkcji w celu sprawdzenia, czy dostępne zapasy przekraczają 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="f5599-111">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="f5599-112">W danych demonstracyjnych firmy **USMF** utwórz nagranie zadań, które mają następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="f5599-112">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="f5599-113">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="f5599-113">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="f5599-114">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="f5599-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f5599-115">Na przykład filtruj według pola z wartością **1000** dla **Numeru elementu**.</span><span class="sxs-lookup"><span data-stu-id="f5599-115">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="f5599-116">Wybierz **Dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="f5599-116">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="f5599-117">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="f5599-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f5599-118">Na przykład wyfiltruj według pola **Oddział** z wartością **1**.</span><span class="sxs-lookup"><span data-stu-id="f5599-118">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="f5599-119">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f5599-119">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="f5599-120">Sprawdź, czy wartość pola **W sumie dostępne** to **411.0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="f5599-120">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="f5599-121">Zapisz rejestrowanie zadań i dołącz je do przypadku testowego w usłudze Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="f5599-121">Save the task recording and attach it to your test case in Azure Devops.</span></span>
3. <span data-ttu-id="f5599-122">Dodaj przypadek testowy do planu testu i załaduj przypadek testowy do pakietu RSAT.</span><span class="sxs-lookup"><span data-stu-id="f5599-122">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="f5599-123">Otwórz plik parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-123">Open the Excel parameter file.</span></span> <span data-ttu-id="f5599-124">Na karcie **InventOnhandItem** zostanie wyświetlona sekcja **sprawdzanie poprawności InventOnhandItem** zawierającej pole **operatora.**</span><span class="sxs-lookup"><span data-stu-id="f5599-124">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Pole Operator](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="f5599-126">Aby sprawdzić, czy dostępne zapasy będą zawsze większe niż 0, Zmień wartość w polu **wartość** z **411** na **0** i wartość pola **operator** w znaku równości (**=**) na znak większości (**\>**).</span><span class="sxs-lookup"><span data-stu-id="f5599-126">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Wartości pól wartości i operatora zostały zmienione](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="f5599-128">Zapisz i zamknij plik parametrów w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-128">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="f5599-129">Kliknij przycisk **Przekaż**, aby zapisać dokonane zmiany w pliku parametrów programu Excel w Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="f5599-129">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="f5599-130">Jeśli wartość w polu **Łączna ilość dostępna** dla określonego towaru w magazynie jest większa od 0 (zero), testy zostaną przekazane niezależnie od wartości rzeczywistej dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="f5599-130">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="saved-variables-and-chaining-of-test-cases"></a><span data-ttu-id="f5599-131">Zapisane zmienne i łańcuchy przypadków testowych</span><span class="sxs-lookup"><span data-stu-id="f5599-131">Saved variables and chaining of test cases</span></span>

<span data-ttu-id="f5599-132">Jedną z najważniejszych funkcji narzędzia RSAT jest łączenie przypadków testowych w łańcuchy (to znaczy zdolność testu do przekazywania zmiennych do innych testów).</span><span class="sxs-lookup"><span data-stu-id="f5599-132">One of the key features of RSAT is the chaining of test cases, that is, the ability of a test to pass variables to other tests.</span></span> <span data-ttu-id="f5599-133">Aby uzyskać więcej informacji, zajrzyj do artykułu [Skopiuj zmienne do łańcuchowych przypadków testowych](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="f5599-133">For more information, see the article [Copy variables to chain test cases](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="f5599-134">Pochodny przypadek testowy</span><span class="sxs-lookup"><span data-stu-id="f5599-134">Derived test case</span></span>

<span data-ttu-id="f5599-135">Narzędzia RSAT umożliwiają korzystanie z tego samego zapisu zadań w wielu przypadkach testowych, umożliwiając uruchamianie zadań z różnymi konfiguracjami danych.</span><span class="sxs-lookup"><span data-stu-id="f5599-135">RSAT lets you use the same task recording with multiple test cases, enabling a task to run with different data configurations.</span></span> <span data-ttu-id="f5599-136">Aby uzyskać więcej informacji, zajrzyj do artykułu [Przypadki testu pochodnego](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="f5599-136">See the article [Derived test cases](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) for more information.</span></span>

### <a name="validate-notifications-and-messages"></a><span data-ttu-id="f5599-137">Sprawdzanie poprawności powiadomień i komunikatów</span><span class="sxs-lookup"><span data-stu-id="f5599-137">Validate notifications and messages</span></span>

<span data-ttu-id="f5599-138">Za pomocą tej funkcji można sprawdzić, czy akcja wystąpiła.</span><span class="sxs-lookup"><span data-stu-id="f5599-138">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="f5599-139">Na przykład podczas tworzenia zlecenia produkcyjnego, szacowanego, a następnie rozpoczętego, aplikacja wyświetla komunikat „produkcja – rozpoczęcie” informujący o rozpoczęciu zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="f5599-139">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Produkcja — Powiadomienie o rozpoczęciu](./media/use_rsa_tool_05.png)

<span data-ttu-id="f5599-141">Można sprawdzić poprawność tej wiadomości za pośrednictwem narzędzia RSAT, wprowadzając tekst **Weryfikacja komunikatu** na karcie pliku parametrów programu Excel w celu odpowiedniego nagrania.</span><span class="sxs-lookup"><span data-stu-id="f5599-141">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Karta weryfikacji komunikatu](./media/use_rsa_tool_06.png)

<span data-ttu-id="f5599-143">Po uruchomieniu przypadku testowego komunikat w pliku parametrów programu Excel jest porównywany z komunikatem wyświetlanym.</span><span class="sxs-lookup"><span data-stu-id="f5599-143">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="f5599-144">Jeśli wiadomości nie pasują do siebie, przypadek testowy nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="f5599-144">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="f5599-145">Można wprowadzić więcej niż jedną wiadomość na karcie **Weryfikacja komunikatu** w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-145">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="f5599-146">Komunikatami mogą być także komunikaty o błędach lub ostrzeżenia, a nie komunikaty informacyjne.</span><span class="sxs-lookup"><span data-stu-id="f5599-146">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="snapshot"></a><span data-ttu-id="f5599-147">Migawka</span><span class="sxs-lookup"><span data-stu-id="f5599-147">Snapshot</span></span>

<span data-ttu-id="f5599-148">Ta funkcja wykonuje zrzuty ekranu czynności, które zostały wykonane podczas rejestrowania zadań.</span><span class="sxs-lookup"><span data-stu-id="f5599-148">This feature takes screenshots of the steps that were performed during task recording.</span></span> <span data-ttu-id="f5599-149">Jest on przydatny do celów inspekcji lub debugowania.</span><span class="sxs-lookup"><span data-stu-id="f5599-149">It is useful for auditing or debugging purposes.</span></span>

- <span data-ttu-id="f5599-150">Aby skorzystać z tej funkcji, należy otworzyć plik **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** w folderze instalacyjnym narzędzia RSAT (na przykład **C\\: Program Files (x86)\\Regression Suite Automation Tool**) i zmienić wartość w następujący sposób element z **false** na **true**.</span><span class="sxs-lookup"><span data-stu-id="f5599-150">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="f5599-151">Po uruchomieniu przypadku testowego narzędzia RSAT generują migawki (obrazy) kroków w folderze odtwarzania przypadków testowych w katalogu roboczym.</span><span class="sxs-lookup"><span data-stu-id="f5599-151">When your run the test case, RSAT will generate snapshots (images) of the steps in the playback folder of the test cases in the working diretory.</span></span> <span data-ttu-id="f5599-152">Jeśli używana jest starsza wersja narzędzia RSAT, obrazy są zapisywane w folderze **C:\\użytkownicy\\\<Nazwa użytkownika\>\\AppData\\Roaming\\regressionTool\\odtwarzanie**, utowrzony jest osobny folder dla każdego uruchomionego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-152">If you are using an older version of RSAT, the images are saved to **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

## <a name="assignment"></a><span data-ttu-id="f5599-153">Przypisanie</span><span class="sxs-lookup"><span data-stu-id="f5599-153">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="f5599-154">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="f5599-154">Scenario</span></span>

1. <span data-ttu-id="f5599-155">Konstruktor produktów tworzy nowy wydany produkt.</span><span class="sxs-lookup"><span data-stu-id="f5599-155">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="f5599-156">Menedżer produkcji inicjuje zlecenie produkcyjne w celu przeniesienia poziomu zapasów do dwóch sztuk.</span><span class="sxs-lookup"><span data-stu-id="f5599-156">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="f5599-157">Produkcja rozpoczyna się i kończy zlecenie produkcyjne oraz sprawdza, czy ilość dostępnych zapasów wynosi dwie sztuki.</span><span class="sxs-lookup"><span data-stu-id="f5599-157">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="f5599-158">Zespół sprzedaży otrzymuje zamówienie na cztery części nowego produktu.</span><span class="sxs-lookup"><span data-stu-id="f5599-158">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="f5599-159">Z tego względu zespół sprzedaży aktualizuje zapotrzebowanie netto za pośrednictwem planu dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="f5599-159">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="f5599-160">Ponieważ żadne dodatkowe zdolności produkcyjne nie są dostępne, domyślną zasadą zamówienia jest „Kup zamiast robić”.</span><span class="sxs-lookup"><span data-stu-id="f5599-160">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="f5599-161">W związku z tym zostanie utworzone zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="f5599-161">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="f5599-162">Kupujący dodaje dostawcę, wiąże planowane zamówienie zakupu, a następnie potwierdza zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="f5599-162">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="f5599-163">Gdy towary, które zostały nabyte, dotarły do sklepu, operator sklepu przeszukuje powiązane zamówienie zakupu i odbiera towary.</span><span class="sxs-lookup"><span data-stu-id="f5599-163">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="f5599-164">Zamówienie jest teraz ukończone, towary można pobrać i zapakować w związku z zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f5599-164">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="f5599-165">Pole finanse księguje fakturę zakupu i fakturę sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f5599-165">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="f5599-166">Na poniższej ilustracji przedstawiono proces dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="f5599-166">The following illustration shows the flow for this scenario.</span></span>

![Proces dla scenariusza pokazu](./media/use_rsa_tool_14.png)

<span data-ttu-id="f5599-168">Na poniższej ilustracji przedstawiono hierarchię procesów biznesowych dla tego scenariusza w narzędziu do modelowania procesów biznesowych usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="f5599-168">The following illustration shows the business processes hierarchy for this scenario in the LCS Business Process Modeler.</span></span>

![Procesy biznesowe dla scenariusza pokazu](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="f5599-170">Strategia — nauka najważniejszych</span><span class="sxs-lookup"><span data-stu-id="f5599-170">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="f5599-171">Dane</span><span class="sxs-lookup"><span data-stu-id="f5599-171">Data</span></span>

- <span data-ttu-id="f5599-172">Upewnij się, że istnieją reprezentatywne woluminy danych (kopie danych konfiguracji produkcji/złota plus dane zmigrowane).</span><span class="sxs-lookup"><span data-stu-id="f5599-172">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="f5599-173">Podczas generowania nowych danych za pomocą rejestratora zadań należy utworzyć nazwy testowe, które nie powodują konfliktu z istniejącymi nazwami (na przykład, należy zastosować prefiks jak **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="f5599-173">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="f5599-174">Za pomocą funkcji przywracania punktów na platformie Azure uruchom ponownie testy w środowiskach spoza warstwy 1.</span><span class="sxs-lookup"><span data-stu-id="f5599-174">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="f5599-175">Chociaż można skorzystać z funkcji Excel **LOSOWO** i **TERAZ**, to aby wygenerować unikatową kombinację, nakład pracy jest znacznie wysoki.</span><span class="sxs-lookup"><span data-stu-id="f5599-175">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="f5599-176">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="f5599-176">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="f5599-177">Rejestrator zadań</span><span class="sxs-lookup"><span data-stu-id="f5599-177">Task recorder</span></span>

- <span data-ttu-id="f5599-178">Przed rozpoczęciem rejestrowania zdefiniuj scenariusze.</span><span class="sxs-lookup"><span data-stu-id="f5599-178">Define scenarios before you start recording.</span></span> <span data-ttu-id="f5599-179">Dobrze zarządzany projekt ma wstępnie zdefiniowane scenariusze testowania.</span><span class="sxs-lookup"><span data-stu-id="f5599-179">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="f5599-180">Aby zbudować przypadek testowy, należy rozważyć przewidywany wynik tych scenariuszy testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-180">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="f5599-181">Podziel nagrania, jeśli są wykonywane przez różne role lub jeśli istnieje czas oczekiwania lub zdarzenie zewnętrzne przed wykonaniem następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="f5599-181">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="f5599-182">Należy unikać wybierania wartości na listach.</span><span class="sxs-lookup"><span data-stu-id="f5599-182">Avoid selecting values in lists.</span></span> <span data-ttu-id="f5599-183">Zamiast tego należy użyć formatów tekstu, takich jak **FIFO**, **AudioRM** i **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="f5599-183">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="f5599-184">Po wybraniu opcji na liście zostanie zarejestrowana pozycja wartości na liście, a nie sama wartość.</span><span class="sxs-lookup"><span data-stu-id="f5599-184">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="f5599-185">Jeśli do tej listy zostaną dodane pozycje, może zmienić się pozycja wartości.</span><span class="sxs-lookup"><span data-stu-id="f5599-185">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="f5599-186">Z tego względu nagranie będzie używało innego parametru i może mieć wpływ na pozostałą część scenariusza.</span><span class="sxs-lookup"><span data-stu-id="f5599-186">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="f5599-187">Należy zastanowić się nad zachowaniem wielu użytkowników.</span><span class="sxs-lookup"><span data-stu-id="f5599-187">Think about multi-user behavior.</span></span> <span data-ttu-id="f5599-188">Na przykład nie zakłada się, że nowo utworzone zamówienie sprzedaży zawsze będzie wybierane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="f5599-188">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="f5599-189">Zamiast tego należy zawsze używać filtru, aby odnaleźć właściwe zamówienie.</span><span class="sxs-lookup"><span data-stu-id="f5599-189">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="f5599-190">W celu zapisania nazwy nowo utworzonego produktu należy użyć funkcji Kopiuj w rejestratorze zadań, aby można było jej użyć w łańcuchach przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-190">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="f5599-191">Funkcja sprawdzania poprawności w rejestratorze zadań umożliwia ustawienie punktów kontrolnych, które weryfikują poprawność działania kroków.</span><span class="sxs-lookup"><span data-stu-id="f5599-191">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="f5599-192">RSAT</span><span class="sxs-lookup"><span data-stu-id="f5599-192">RSAT</span></span>

- <span data-ttu-id="f5599-193">Aby uruchomić test w innej firmie, można zmienić firmę na karcie **ogólne** w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-193">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="f5599-194">Upewnij się, że ustawienia i dane są dostępne w nowo wybranej firmie.</span><span class="sxs-lookup"><span data-stu-id="f5599-194">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="f5599-195">Użytkownik testowy można zmienić na karcie **ogólne** w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-195">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="f5599-196">Określ identyfikator e-mail użytkownika, który uruchomi przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="f5599-196">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="f5599-197">W ten sposób można uruchomić przypadek testowy przy użyciu uprawnień zabezpieczeń określonego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f5599-197">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="f5599-198">Aby poczekać przed rozpoczęciem testu, można zdefiniować pauzę na karcie **ogólne** pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-198">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="f5599-199">To wstrzymanie może być używane w zadaniu wsadowym (na przykład, jeśli proces przepływu pracy musi zostać wykonany, aby można było wykonać następny krok)</span><span class="sxs-lookup"><span data-stu-id="f5599-199">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="f5599-200">Zaawansowane skrypty</span><span class="sxs-lookup"><span data-stu-id="f5599-200">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="f5599-201">Wiersz poleceń</span><span class="sxs-lookup"><span data-stu-id="f5599-201">CLI</span></span>

<span data-ttu-id="f5599-202">RSAT można wywołać z poziomu okna **Wiersz poleceń** lub **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f5599-202">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="f5599-203">Sprawdź, czy zmienna środowiskowa **TestRoot** jest ustawiona jako ścieżka instalacji pakietu RSAT.</span><span class="sxs-lookup"><span data-stu-id="f5599-203">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="f5599-204">(W systemie Microsoft Windows otwórz **panel sterowania**, wybierz **System i zabezpieczenia  \> System \> Zaawansowane ustawienia systemu**, a następnie wybierz **zmienne środowiskowe**).</span><span class="sxs-lookup"><span data-stu-id="f5599-204">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="f5599-205">Otwórz okno **Wiersz poleceń** lub **PowerShell** jako administrator.</span><span class="sxs-lookup"><span data-stu-id="f5599-205">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="f5599-206">Przejdź do katalogu instalacyjnego narzędzia RSAT.</span><span class="sxs-lookup"><span data-stu-id="f5599-206">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="f5599-207">Lista wszystkich poleceń.</span><span class="sxs-lookup"><span data-stu-id="f5599-207">List all commands.</span></span>

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

#### <a name=""></a><span data-ttu-id="f5599-208">?</span><span class="sxs-lookup"><span data-stu-id="f5599-208">?</span></span> 
<span data-ttu-id="f5599-209">Pokazuje pomoc dotyczącą wszystkich dostępnych poleceń i ich parametrów.</span><span class="sxs-lookup"><span data-stu-id="f5599-209">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="f5599-210">Parametry opcjonalne</span><span class="sxs-lookup"><span data-stu-id="f5599-210">Optional parameters</span></span>

**``command``**


<span data-ttu-id="f5599-211">Gdzie ``[command]`` jest jednym z poleceń określonych poniżej.</span><span class="sxs-lookup"><span data-stu-id="f5599-211">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="f5599-212">informacje</span><span class="sxs-lookup"><span data-stu-id="f5599-212">about</span></span>
<span data-ttu-id="f5599-213">Wyświetla obecną wersję.</span><span class="sxs-lookup"><span data-stu-id="f5599-213">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="f5599-214">cls</span><span class="sxs-lookup"><span data-stu-id="f5599-214">cls</span></span>
<span data-ttu-id="f5599-215">Czyści ekran.</span><span class="sxs-lookup"><span data-stu-id="f5599-215">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="f5599-216">pobierz</span><span class="sxs-lookup"><span data-stu-id="f5599-216">download</span></span>
<span data-ttu-id="f5599-217">Pobiera załączniki dla określonego przypadku testowego do katalogu wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-217">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="f5599-218">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="f5599-218">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="f5599-219">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="f5599-219">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-220">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-220">Required parameters</span></span>
<span data-ttu-id="f5599-221">**``test_case_id``** Przedstawia identyfikator przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-221">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="f5599-222">**``output_dir``** Reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="f5599-222">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="f5599-223">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="f5599-223">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-224">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-224">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="f5599-225">edycja</span><span class="sxs-lookup"><span data-stu-id="f5599-225">edit</span></span>
<span data-ttu-id="f5599-226">Umożliwia otwieranie pliku parametrów w programie Excel i edytowanie go.</span><span class="sxs-lookup"><span data-stu-id="f5599-226">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-227">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-227">Required parameters</span></span>
<span data-ttu-id="f5599-228">**``excel_file``** Musi zawierać pełną ścieżkę do istniejącego pliku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-228">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-229">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-229">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="f5599-230">generate</span><span class="sxs-lookup"><span data-stu-id="f5599-230">generate</span></span>
<span data-ttu-id="f5599-231">Generuje pliki wykonania testu i parametry dla określonego przypadku testowego w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="f5599-231">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="f5599-232">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="f5599-232">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="f5599-233">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="f5599-233">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-234">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-234">Required parameters</span></span>
<span data-ttu-id="f5599-235">**``test_case_id``** Przedstawia identyfikator przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-235">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="f5599-236">**``output_dir``** Reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="f5599-236">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="f5599-237">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="f5599-237">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-238">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-238">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="f5599-239">generatederived</span><span class="sxs-lookup"><span data-stu-id="f5599-239">generatederived</span></span>
<span data-ttu-id="f5599-240">Generuje nowy przypadek testowy pochodzący z dostarczonego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-240">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="f5599-241">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="f5599-241">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="f5599-242">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="f5599-242">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-243">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-243">Required parameters</span></span>
<span data-ttu-id="f5599-244">**``parent_test_case_id``** Przedstawia identyfikator nadrzędnego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-244">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="f5599-245">**``test_plan_id``** Przedstawia identyfikator planu testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-245">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="f5599-246">**``test_suite_id``** Przedstawia identyfikator zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-246">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-247">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-247">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="f5599-248">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="f5599-248">generatetestonly</span></span>
<span data-ttu-id="f5599-249">Generuje tylko plik wykonania testu dla określonego przypadku testowego w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="f5599-249">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="f5599-250">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="f5599-250">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="f5599-251">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="f5599-251">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-252">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-252">Required parameters</span></span>
<span data-ttu-id="f5599-253">**``test_case_id``** Przedstawia identyfikator przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-253">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="f5599-254">**``output_dir``** Reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="f5599-254">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="f5599-255">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="f5599-255">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-256">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-256">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="f5599-257">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="f5599-257">generatetestsuite</span></span>
<span data-ttu-id="f5599-258">Generuje wszystkie przypadki testowe dla określonego zestawu w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="f5599-258">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="f5599-259">Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe.</span><span class="sxs-lookup"><span data-stu-id="f5599-259">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="f5599-260">Jako parametru **test_suiye_id** należy zastosować dowolną wartość z kolumny.</span><span class="sxs-lookup"><span data-stu-id="f5599-260">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-261">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-261">Required parameters</span></span>
<span data-ttu-id="f5599-262">**``test_suite_name``** Przedstawia nazwę zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-262">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="f5599-263">**``output_dir``** Reprezentuje katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="f5599-263">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="f5599-264">Katalog musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="f5599-264">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-265">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-265">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="f5599-266">help</span><span class="sxs-lookup"><span data-stu-id="f5599-266">help</span></span>
<span data-ttu-id="f5599-267">Identyczny z [?](#section)</span><span class="sxs-lookup"><span data-stu-id="f5599-267">Identical to the [?](#section)</span></span> <span data-ttu-id="f5599-268">command</span><span class="sxs-lookup"><span data-stu-id="f5599-268">command</span></span>


#### <a name="list"></a><span data-ttu-id="f5599-269">liście</span><span class="sxs-lookup"><span data-stu-id="f5599-269">list</span></span>
<span data-ttu-id="f5599-270">Umożliwia wyświetlenie listy wszystkich dostępnych przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-270">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="f5599-271">listtestplans</span><span class="sxs-lookup"><span data-stu-id="f5599-271">listtestplans</span></span>
<span data-ttu-id="f5599-272">Umożliwia wyświetlenie listy wszystkich dostępnych planów testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-272">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="f5599-273">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="f5599-273">listtestsuite</span></span>
<span data-ttu-id="f5599-274">Wyświetla przypadki testowe dla określonego zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-274">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="f5599-275">Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe.</span><span class="sxs-lookup"><span data-stu-id="f5599-275">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="f5599-276">Jako parametru **suite_name** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="f5599-276">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-277">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-277">Required parameters</span></span>
<span data-ttu-id="f5599-278">**``suite_name``** Nazwa żądanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="f5599-278">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-279">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-279">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="f5599-280">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="f5599-280">listtestsuitenames</span></span>
<span data-ttu-id="f5599-281">Umożliwia wyświetlenie listy wszystkich dostępnych zestawów testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-281">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="f5599-282">playback</span><span class="sxs-lookup"><span data-stu-id="f5599-282">playback</span></span>
<span data-ttu-id="f5599-283">Umożliwia ponowne odtworzenie przypadku testowego w pliku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-283">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-284">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-284">Required parameters</span></span>
<span data-ttu-id="f5599-285">**``excel_file``** Pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-285">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="f5599-286">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="f5599-286">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="f5599-287">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-287">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="f5599-288">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="f5599-288">playbackbyid</span></span>
<span data-ttu-id="f5599-289">Umożliwia jednoczesne odtworzenie wielu przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-289">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="f5599-290">Możesz użyć komendy ``list``, aby uzyskać wszystkie dostępne przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="f5599-290">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="f5599-291">Jako parametru **test_case_id** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="f5599-291">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-292">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-292">Required parameters</span></span>
<span data-ttu-id="f5599-293">**``test_case_id1``** Identyfikator dla istniejących przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-293">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="f5599-294">**``test_case_id2``** Identyfikator dla istniejących przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-294">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="f5599-295">**``test_case_idN``** Identyfikator dla istniejących przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-295">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="f5599-296">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-296">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="f5599-297">playbackmany</span><span class="sxs-lookup"><span data-stu-id="f5599-297">playbackmany</span></span>
<span data-ttu-id="f5599-298">Umożliwia jednoczesne odtwarzanie wielu przypadków testowych przy użyciu plików programu Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-298">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-299">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-299">Required parameters</span></span>
<span data-ttu-id="f5599-300">**``excel_file1``** Pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-300">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="f5599-301">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="f5599-301">File must exist.</span></span>  
<span data-ttu-id="f5599-302">**``excel_file2``** Pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-302">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="f5599-303">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="f5599-303">File must exist.</span></span>  
<span data-ttu-id="f5599-304">**``excel_fileN``** Pełna ścieżka do pliku Excel.</span><span class="sxs-lookup"><span data-stu-id="f5599-304">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="f5599-305">Plik musi istnieć.</span><span class="sxs-lookup"><span data-stu-id="f5599-305">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="f5599-306">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-306">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="f5599-307">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="f5599-307">playbacksuite</span></span>
<span data-ttu-id="f5599-308">Odtwarza wszystkie przypadki testowe z określonego zestawu testowego.</span><span class="sxs-lookup"><span data-stu-id="f5599-308">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="f5599-309">Możesz użyć komendy ``listtestsuitenames``, aby uzyskać wszystkie dostępne zestawy testowe.</span><span class="sxs-lookup"><span data-stu-id="f5599-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="f5599-310">Jako parametru **suite_name** należy zastosować dowolną wartość z pierwszej kolumny.</span><span class="sxs-lookup"><span data-stu-id="f5599-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-311">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-311">Required parameters</span></span>
<span data-ttu-id="f5599-312">**``suite_name``** Nazwa żądanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="f5599-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-313">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-313">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="f5599-314">quit</span><span class="sxs-lookup"><span data-stu-id="f5599-314">quit</span></span>
<span data-ttu-id="f5599-315">Zamyka aplikację.</span><span class="sxs-lookup"><span data-stu-id="f5599-315">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="f5599-316">upload</span><span class="sxs-lookup"><span data-stu-id="f5599-316">upload</span></span>
<span data-ttu-id="f5599-317">Umożliwia przekazanie wszystkich plików należących do określonego zestawu testów lub przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-317">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="f5599-318">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-318">Required parameters</span></span>
<span data-ttu-id="f5599-319">**``suite_name``** Wszystkie pliki należące do określonego zestawu testów zostaną przesłane.</span><span class="sxs-lookup"><span data-stu-id="f5599-319">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="f5599-320">**``testcase_id``** Wszystkie pliki należące do określonego przypadku testowego (przypadków testowych) zostaną przesłane.</span><span class="sxs-lookup"><span data-stu-id="f5599-320">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-321">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-321">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="f5599-322">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="f5599-322">uploadrecording</span></span>
<span data-ttu-id="f5599-323">Umożliwia przekazanie tylko pliku nagrania należącego do określonych przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="f5599-323">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="f5599-324">Wymagane parametry</span><span class="sxs-lookup"><span data-stu-id="f5599-324">Required parameters</span></span>
<span data-ttu-id="f5599-325">**``testcase_id``** Plik nagrania należący do określonych przypadków testowych zostanie przesłany.</span><span class="sxs-lookup"><span data-stu-id="f5599-325">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="f5599-326">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f5599-326">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="f5599-327">usage</span><span class="sxs-lookup"><span data-stu-id="f5599-327">usage</span></span>
<span data-ttu-id="f5599-328">Pokazuje dwa sposoby wywoływania tej aplikacji: jeden przy użyciu pliku ustawień domyślnych oraz drugi, który udostępnia plik ustawień.</span><span class="sxs-lookup"><span data-stu-id="f5599-328">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="f5599-329">Przykłady środowiska Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5599-329">Windows PowerShell examples</span></span>

[!IMPORTANT] <span data-ttu-id="f5599-330">Przykładowe skrypty przedstawione poniżej są przeznaczone do celów ilustracyjnych i nie są obsługiwane przez firmę Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f5599-330">The example scripts below are provided AS IS for illustration purposes and are not supported by Microsoft.</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="f5599-331">Uruchamianie przypadku testowego w pętli</span><span class="sxs-lookup"><span data-stu-id="f5599-331">Run a test case in a loop</span></span>

<span data-ttu-id="f5599-332">Masz skrypt testowy, który tworzy nowego klienta.</span><span class="sxs-lookup"><span data-stu-id="f5599-332">You have a test script that creates a new customer.</span></span> <span data-ttu-id="f5599-333">Za pomocą skryptów ten przypadek testowy można uruchomić w pętli, tworząc losowo następujące dane przed uruchomieniem każdej iteracji:</span><span class="sxs-lookup"><span data-stu-id="f5599-333">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="f5599-334">Identyfikator odbiorcy</span><span class="sxs-lookup"><span data-stu-id="f5599-334">Customer ID</span></span>
- <span data-ttu-id="f5599-335">Nazwa odbiorcy</span><span class="sxs-lookup"><span data-stu-id="f5599-335">Customer name</span></span>
- <span data-ttu-id="f5599-336">Adres odbiorcy</span><span class="sxs-lookup"><span data-stu-id="f5599-336">Customer address</span></span>

<span data-ttu-id="f5599-337">Identyfikator odbiorcy będzie w formacie *ATCUS\<liczba\>*, gdzie \<liczba\> jest wartością z zakresu od **000000001** do **999999999**.</span><span class="sxs-lookup"><span data-stu-id="f5599-337">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="f5599-338">W poniższym przykładzie użyto jednego parametru, **Start**, aby zdefiniować pierwszy użyty numer.</span><span class="sxs-lookup"><span data-stu-id="f5599-338">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="f5599-339">Do zdefiniowania liczby odbiorców używany jest drugi paramentr **nr**, który musi być utworzony.</span><span class="sxs-lookup"><span data-stu-id="f5599-339">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="f5599-340">W przypadku każdej iteracji parametry w pliku parametrów programu Excel są zmieniane za pomocą funkcji UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="f5599-340">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="f5599-341">Następnie wiersz polecenia RSAT jest wywoływany w funkcji RunTestCase</span><span class="sxs-lookup"><span data-stu-id="f5599-341">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="f5599-342">Otwórz środowisko Microsoft Windows PowerShell Integrated Scripting Environment (ISE) w trybie administratora i wklej następujący kod do okna o nazwie **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="f5599-342">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

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

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="f5599-343">Uruchom skrypt zależny od danych w Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f5599-343">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="f5599-344">W poniższym przykładzie użyto wywołania protokołu OData (Open Data Protocol) w celu znalezienia stanu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="f5599-344">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="f5599-345">Jeśli stan nie jest **fakturowany**, można na przykład wywołać przypadek testowy narzędzia RSAT, które zaksięguje fakturę.</span><span class="sxs-lookup"><span data-stu-id="f5599-345">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

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
