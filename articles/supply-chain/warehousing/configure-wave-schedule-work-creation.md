---
title: Planowanie tworzenia pracy podczas grupy czynności
description: W tym temacie opisano sposób konfigurowania i używania metody przetwarzania grupy czynności planowania tworzenia pracy.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 36a450f78695f617056875f8d236fe46bc66aaaf
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501229"
---
# <a name="schedule-work-creation-during-wave"></a><span data-ttu-id="77683-103">Planowanie tworzenia pracy podczas grupy czynności</span><span class="sxs-lookup"><span data-stu-id="77683-103">Schedule work creation during wave</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="77683-104">Użyj funkcji *planowania tworzenia pracy* jako części procesu obsługi grupy czynności, aby zwiększyć przepustowość przetwarzania grupy czynności, ponieważ system tworzy pracę przy użyciu przetwarzania równoległego.</span><span class="sxs-lookup"><span data-stu-id="77683-104">Use the *Schedule work creation* feature as part of your waving process to help increase wave processing throughput by having the system create work using parallel processing.</span></span>

<span data-ttu-id="77683-105">Gdy ta funkcja jest włączona, automatycznie zostanie utworzona planowana praca, która będzie ostatecznie przetwarzana w celu utworzenia rzeczywistej pracy.</span><span class="sxs-lookup"><span data-stu-id="77683-105">When the functionality is enabled, planned work will automatically get created, which the system will eventually process to create actual work.</span></span> <span data-ttu-id="77683-106">Jeśli liczba wierszy ładunku grupy czynności osiągnie wstępnie określony próg, system utworzy rzeczywistą pracę szybciej, stosując równoległe przetwarzanie asynchroniczne.</span><span class="sxs-lookup"><span data-stu-id="77683-106">If the number of wave load lines reaches a predetermined threshold, the system will create actual work more quickly by applying parallel, asynchronous processing.</span></span>

## <a name="enable-the-schedule-work-creation-feature"></a><span data-ttu-id="77683-107">Włącz funkcję planowania tworzenia pracy</span><span class="sxs-lookup"><span data-stu-id="77683-107">Enable the Schedule work creation feature</span></span>

### <a name="enable-the-feature-in-feature-management"></a><span data-ttu-id="77683-108">Włącz funkcję w zarządzaniu funkcjami</span><span class="sxs-lookup"><span data-stu-id="77683-108">Enable the feature in feature management</span></span>

<span data-ttu-id="77683-109">Aby móc używać funkcji *Planowanie tworzenia pracy*, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="77683-109">Before you can use the *Schedule work creation* feature, it must be turned on in your system.</span></span> <span data-ttu-id="77683-110">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="77683-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="77683-111">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="77683-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="77683-112">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="77683-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="77683-113">**Nazwa funkcji:** *Planowanie tworzenia pracy*</span><span class="sxs-lookup"><span data-stu-id="77683-113">**Feature name:** *Schedule work creation*</span></span>

> [!NOTE]
> <span data-ttu-id="77683-114">Aby można było włączyć *planowanie tworzenia pracy*, należy włączyć funkcję *blokowania pracy w całej organizacji*.</span><span class="sxs-lookup"><span data-stu-id="77683-114">The *Organization-wide work blocking* feature must be enabled before you can enable *Schedule work creation*.</span></span>

### <a name="manually-enable-batch-processing-of-waves"></a><span data-ttu-id="77683-115">Ręczne włączanie przetwarzania wsadowego grup czynności</span><span class="sxs-lookup"><span data-stu-id="77683-115">Manually enable batch processing of waves</span></span>

<span data-ttu-id="77683-116">Aby można było korzystać z równoległej metody asynchronicznej tworzenia pracy magazynowej, proces grupy czynności musi być uruchomiony w partii.</span><span class="sxs-lookup"><span data-stu-id="77683-116">To take advantage of a parallel asynchronous method to create warehouse work, your wave process must be running in batch.</span></span> <span data-ttu-id="77683-117">Aby to skonfigurować:</span><span class="sxs-lookup"><span data-stu-id="77683-117">To set this up:</span></span>

1. <span data-ttu-id="77683-118">Wybierz kolejno opcje  **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="77683-118">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>

1. <span data-ttu-id="77683-119">Na karcie **Ogólne** ustaw opcję **Przetwarzaj grupy czynności partiami** na *Tak*.</span><span class="sxs-lookup"><span data-stu-id="77683-119">On the **General** tab, set **Process waves in batch** to *Yes*.</span></span> <span data-ttu-id="77683-120">Opcjonalnie możesz również wybrać dedykowaną **grupę przetwarzania wsadowego grupy czynności**, aby uniemożliwić uruchomienie przetwarzania kolejki przetwarzania wsadowego w tym samym czasie, co inne procesy.</span><span class="sxs-lookup"><span data-stu-id="77683-120">Optionally, you can also select a dedicated **Wave processing batch group** to prevent your batch queue processing from running at the same time as other processes.</span></span>

1. <span data-ttu-id="77683-121">Ustaw **czas oczekiwania na blokadę (ms)**, który ma zastosowanie, gdy system przetwarza kilka grup czynności w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="77683-121">Set the **Wait for lock (ms) time**, which applies when the system is processing several waves at the same time.</span></span> <span data-ttu-id="77683-122">W przypadku większości procesów grup czynności zalecane jest użycie wartości *60 000*.</span><span class="sxs-lookup"><span data-stu-id="77683-122">For most larger waving processes, we recommend a value of *60000*.</span></span>

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a><span data-ttu-id="77683-123">Ręcznie włącz nową metodę kroku grupy czynności dla istniejących szablonów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="77683-123">Manually enable the new wave step method for existing wave templates</span></span>

<span data-ttu-id="77683-124">Rozpocznij od utworzenia nowej metody kroku grupy czynności i włączenia jej do równoległego przetwarzania zadań asynchronicznych.</span><span class="sxs-lookup"><span data-stu-id="77683-124">Start by creating the new wave step method and enabling it for parallel asynchronous task processing.</span></span>

1. <span data-ttu-id="77683-125">Wybierz kolejno opcje  **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="77683-125">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>

1. <span data-ttu-id="77683-126">Wybierz opcję  **Ponownie utwórz metody** i zauważ, że do listy metod przetwarzania grupy czynności, których można używać w szablonach grupy czynności wysyłki, dodano metodę *WHSScheduleWorkCreationWaveStepMethod*.</span><span class="sxs-lookup"><span data-stu-id="77683-126">Select  **Regenerate method** and note that *WHSScheduleWorkCreationWaveStepMethod* has been added to the list of wave process methods you can use in your shipping wave templates.</span></span>

1. <span data-ttu-id="77683-127">Wybierz rekord z **nazwą metody** *WHSScheduleWorkCreationWaveStepMethod* i wybierz **Konfiguracja zadania**.</span><span class="sxs-lookup"><span data-stu-id="77683-127">Select the record with the **Method name** *WHSScheduleWorkCreationWaveStepMethod* and select **Task configuration**.</span></span>

1. <span data-ttu-id="77683-128">Aby dodać nowy wiersz do siatki, wybierz opcję **Nowy** w okienku akcji i użyj następujących ustawień:</span><span class="sxs-lookup"><span data-stu-id="77683-128">To add a new row to the grid, select **New** on the Action Pane and use the following settings:</span></span>

    - <span data-ttu-id="77683-129">**Magazyn** — umożliwia wybranie magazynu, który ma być podstawą do zaplanowania przetwarzania tworzenia pracy.</span><span class="sxs-lookup"><span data-stu-id="77683-129">**Warehouse** - Select the warehouse you will use to schedule work creation processing.</span></span>

    - <span data-ttu-id="77683-130">**Maksymalna liczba zadań wsadowych** — umożliwia określenie maksymalnej liczby zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="77683-130">**Maximum number of batch tasks** - Specify a maximum number of batch tasks.</span></span> <span data-ttu-id="77683-131">W większości przypadków ta wartość powinna być w przedziale od 8 do 16, jednak zalecamy eksperymentowanie z ustawieniami optymalnymi na podstawie scenariuszy.</span><span class="sxs-lookup"><span data-stu-id="77683-131">In most cases, this value should be in the range from 8-16, however we recommend that you experiment with the optimal setting based on your scenarios.</span></span>

    - <span data-ttu-id="77683-132">**Grupa przetwarzania wsadowego grupy czynności** — wybierz dedykowaną grupę przetwarzania grupy czynności w celu zoptymalizowania przetwarzania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="77683-132">**Wave processing batch group** - Select a dedicated wave processing batch group to optimize your batch queue processing.</span></span>

<span data-ttu-id="77683-133">Teraz można zaktualizować istniejący szablon grupy czynności (lub utworzyć nowy), aby użyć metody przetwarzania grupy czynności *Planowanie tworzenia pracy*.</span><span class="sxs-lookup"><span data-stu-id="77683-133">Now you are ready to update an existing wave template (or create a new one) to use the *Schedule work creation* wave processing method.</span></span>

1. <span data-ttu-id="77683-134">Wybierz kolejno opcje  **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="77683-134">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>

1. <span data-ttu-id="77683-135">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="77683-135">Select **Edit** on the Action Pane.</span></span>

1. <span data-ttu-id="77683-136">W okienku listy wybierz szablon grupy czynności, który chcesz zaktualizować (w przypadku testowania danych pokazowych możesz użyć *domyślnej wysyłki w 24 godziny*).</span><span class="sxs-lookup"><span data-stu-id="77683-136">In the list pane, select the wave template you would like to update (if you are testing using demo data, then you could use *24 Shipping default*).</span></span>

1. <span data-ttu-id="77683-137">Rozwiń skróconą kartę **Metody** i zaznacz wiersz z **nazwą** *Planowanie tworzenia pracy* w siatce **Pozostałe metody**.</span><span class="sxs-lookup"><span data-stu-id="77683-137">Expand the **Methods** FastTab and select the row with the **Name** *Schedule work creation* in the **Remaining methods** grid.</span></span>

1. <span data-ttu-id="77683-138">Wybierz strzałkę wskazującą kolumnę **Wybrane metody**, aby przenieść wybrany wiersz do tej kolumny.</span><span class="sxs-lookup"><span data-stu-id="77683-138">Select the arrow pointing to the **Selected methods** column to move the selected row to that column.</span></span> <span data-ttu-id="77683-139">(W danym momencie może być używana tylko jedna wybrana metoda *WHSScheduleWorkCreationWaveStepMethod* lub *createWork*, w związku z tym istniejący wiersz o **nazwie metody** *createWork* zostanie automatycznie przeniesiony do siatki metod **Pozostałe metody**).</span><span class="sxs-lookup"><span data-stu-id="77683-139">(You can only have one selected method at a time that uses either *WHSScheduleWorkCreationWaveStepMethod* or *createWork*, so the existing row with **Method name** *createWork* is automatically moved to the **Remaining methods** grid.)</span></span>

## <a name="set-wave-task-processing-threshold-data"></a><span data-ttu-id="77683-140">Ustaw dane progowe przetwarzania zadań grupy czynności</span><span class="sxs-lookup"><span data-stu-id="77683-140">Set wave task processing threshold data</span></span>

<span data-ttu-id="77683-141">System utworzy domyślne dane progowe przetwarzania zadań grupy czynności podczas pierwszego przetwarzania grupy czynności z użyciem dowolnego przetwarzania opartego na zadaniu.</span><span class="sxs-lookup"><span data-stu-id="77683-141">The system will create default wave task processing threshold data the first time a wave process runs using any task-based processing.</span></span> <span data-ttu-id="77683-142">Dane służą do kontrolowania, kiedy przetwarzanie grupy czynności będzie wykonywane asynchronicznie i będzie oparte na zadaniach, co pozwala na równoległe przetwarzanie i tworzenie pracy.</span><span class="sxs-lookup"><span data-stu-id="77683-142">The data is used to control when wave processing will run asynchronously and be task-based, which enables it to process and create work in parallel.</span></span>

<span data-ttu-id="77683-143">Dane domyślne początkowo korzystają z wartości progowej 15 dla minimalnej liczby wierszy ładunku (MINIMUMWAVELOADLINES).</span><span class="sxs-lookup"><span data-stu-id="77683-143">The default data will initially use a threshold value of 15 for the minimum number of load lines (MINIMUMWAVELOADLINES).</span></span> <span data-ttu-id="77683-144">Oznacza to, że gdy system przetwarza ładunek grupy czynności z więcej niż 15 wierszami, będzie używać asynchronicznego przetwarzania zadań.</span><span class="sxs-lookup"><span data-stu-id="77683-144">This means that when the system processes a wave with more than 15 loads lines, it will use asynchronous task processing.</span></span> <span data-ttu-id="77683-145">Dane te można ręcznie wstawiać/aktualizować w tabeli **WHSWaveTaskProcessingThresholdParameters** w środowiskach testowych, ale jeśli musisz zmienić to ustawienie w środowisku produkcyjnym, skontaktuj się z pomocą techniczną firmy Microsoft, aby poprosić o aktualizację.</span><span class="sxs-lookup"><span data-stu-id="77683-145">You can manually insert/update this data in the **WHSWaveTaskProcessingThresholdParameters** table in your test environments, but if you need to change this setting in a production environment, you must contact Microsoft Support to request the update.</span></span>

## <a name="work-with-the-feature"></a><span data-ttu-id="77683-146">Pracuj z funkcją</span><span class="sxs-lookup"><span data-stu-id="77683-146">Work with the feature</span></span>

<span data-ttu-id="77683-147">Gdy jest włączona funkcja *planowania tworzenia pracy*, przetwarzanie grupy czynności utworzy planowaną pracę, która będzie ostatecznie używana przez nowy proces tworzenia pracy.</span><span class="sxs-lookup"><span data-stu-id="77683-147">When the *Schedule work creation* functionality is enabled, wave processing will create planned work, which will eventually be used by the new work creation process.</span></span> <span data-ttu-id="77683-148">Podczas tworzenia pracy praca zostanie zablokowana za pomocą funkcji *blokowania pracy w całej organizacji*.</span><span class="sxs-lookup"><span data-stu-id="77683-148">During work creation, the work will be blocked using the *Organization-wide work blocking* feature.</span></span>

<span data-ttu-id="77683-149">Poniższy schemat blokowy pokazuje, jak planowana praca jest tworzona podczas przetwarzania grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="77683-149">The following flowchart shows how planned work is created during wave processing.</span></span>

![Planowanie tworzenia pracy](media/schedule-work-creation-process.png)

### <a name="planned-work"></a><span data-ttu-id="77683-151">Zaplanowana praca</span><span class="sxs-lookup"><span data-stu-id="77683-151">Planned work</span></span>

<span data-ttu-id="77683-152">Strona **szczegółów planowanej pracy** (**Zarządzanie magazynem \> Praca \> Szczegóły planowanej pracy**) zawiera informacje o planowanej pracy, która jest początkowo tworzona podczas przetwarzania grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="77683-152">The **Planned work details** page (**Warehouse management \> Work \> Planned work details**) shows information about the planned work, which is initially created during wave processing.</span></span> <span data-ttu-id="77683-153">Dostępne są następujące wartości opcji **Stan procesu**:</span><span class="sxs-lookup"><span data-stu-id="77683-153">The following **Process status** values are available:</span></span>

- <span data-ttu-id="77683-154">**W kolejce** — planowana praca oczekuje na utworzenie pracy.</span><span class="sxs-lookup"><span data-stu-id="77683-154">**Queued** - The planned work is waiting to be used to create work.</span></span>
- <span data-ttu-id="77683-155">**Zakończono** — planowana praca została użyta do utworzenia pracy.</span><span class="sxs-lookup"><span data-stu-id="77683-155">**Completed** - The planned work has been used to create work.</span></span>
- <span data-ttu-id="77683-156">**Niepowodzenie** — przetwarzanie grupy czynności nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="77683-156">**Failed** – The wave processing has failed.</span></span> <span data-ttu-id="77683-157">Należy zauważyć, że praca planowana może mieć stan **Niepowodzenie** z rzeczywistą pracą lub bez niej.</span><span class="sxs-lookup"><span data-stu-id="77683-157">Note that the planned work can be in a **Failed** state with or without related actual work.</span></span> <span data-ttu-id="77683-158">Jeśli rzeczywisty proces tworzenia pracy nie powiedzie się, rzeczywista praca pozostaje w stanie *Anulowana*.</span><span class="sxs-lookup"><span data-stu-id="77683-158">When the actual work creation process fails, the actual work remains in status *Cancelled*.</span></span>

### <a name="batch-job-for-the-work-creation-process"></a><span data-ttu-id="77683-159">Zadanie wsadowe dla procesu tworzenia pracy</span><span class="sxs-lookup"><span data-stu-id="77683-159">Batch job for the work creation process</span></span>

<span data-ttu-id="77683-160">Aby wyświetlić zadania wsadowe przetwarzania grup czynności, wybierz **Zadania wsadowe** w okienku akcji na stronie **Wszystkie grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="77683-160">To view the batch jobs for processing waves, select **Batch jobs** on the Action Pane on the **All waves** page.</span></span>

<span data-ttu-id="77683-161">W tym miejscu można wyświetlić wszystkie szczegóły zadania wsadowego dla każdego z identyfikatorów zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="77683-161">From here, you can view all the batch task details for each of the batch job IDs.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]