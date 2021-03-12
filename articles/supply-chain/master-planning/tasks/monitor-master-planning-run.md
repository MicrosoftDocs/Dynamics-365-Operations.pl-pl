---
title: Monitorowanie przebiegu planowania głównego
description: W tym temacie opisano sposób, w jaki terminarz produkcji może sprawdzić, czy proces planowania głównego jest w toku.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1cbe2c55ef9e3ed35db30ca927f3472c750c1db5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999813"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="d67f5-103">Monitorowanie przebiegu planowania głównego</span><span class="sxs-lookup"><span data-stu-id="d67f5-103">Monitor a master planning run</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a><span data-ttu-id="d67f5-104">Użycie wykresu Gantta do wizualizacji postępu planowania głównego</span><span class="sxs-lookup"><span data-stu-id="d67f5-104">Use a Gantt chart to visualize master planning progress</span></span>

<span data-ttu-id="d67f5-105">Na stronie **przegląd postępu planowania głównego** można wyświetlić szczegóły historycznego planowania głównego jako wykresu Gantta.</span><span class="sxs-lookup"><span data-stu-id="d67f5-105">From the **View master planning progress** page, you can view details of historical master planning runs as a Gantt chart.</span></span> <span data-ttu-id="d67f5-106">Ta funkcja może pomóc w zrozumieniu czasu poświęcanego na różne fazy planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="d67f5-106">This functionality can help you understand the time that is spent on the various phases of master planning.</span></span> <span data-ttu-id="d67f5-107">W przypadku bieżącego aktywnego zadania planowania na stronie **przegląd postępu planowania głównego** można używać strony do śledzenia postępu i wyświetlania szacowanego czasu pozostałego.</span><span class="sxs-lookup"><span data-stu-id="d67f5-107">For a current active planning job, the **View master planning progress** page can be used to track progress and view the estimated remaining time.</span></span>

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a><span data-ttu-id="d67f5-108">Włączanie funkcji wizualizacji postępu planowania głównego i korzystanie z niej</span><span class="sxs-lookup"><span data-stu-id="d67f5-108">Turn on and use the Master plan progress visualization feature</span></span>

<span data-ttu-id="d67f5-109">Aby skorzystać z tej funkcji, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d67f5-109">To use this functionality, follow these steps.</span></span>

1. <span data-ttu-id="d67f5-110">W obszarze roboczym **Zarządzanie funkcjami** na liście na **nowej** karcie Wybierz opcję **Wizualizacja postępu planowania głównego** z listy.</span><span class="sxs-lookup"><span data-stu-id="d67f5-110">In the **Feature management** workspace, on the **New** tab, select **Master planning progress visualization** in the list.</span></span> <span data-ttu-id="d67f5-111">Jeśli funkcja nie jest wyświetlana na **nowej** karcie, sprawdź, czy **nie jest włączona** i **wszystkie** karty.</span><span class="sxs-lookup"><span data-stu-id="d67f5-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="d67f5-112">Wybierz **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-112">Select **Enable now**.</span></span> <span data-ttu-id="d67f5-113">Możesz też wybrać **harmonogram**, a następnie wybrać czas, w którym funkcja ma być włączona</span><span class="sxs-lookup"><span data-stu-id="d67f5-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

<span data-ttu-id="d67f5-114">Na stronie **przegląd postępu planowania głównego** planowania głównego można wyświetlić zarówno zadania planowania historycznego, jak i aktywne zadania planowania.</span><span class="sxs-lookup"><span data-stu-id="d67f5-114">The **View master planning progress** page can display both historical planning jobs and active planning jobs.</span></span> 

<span data-ttu-id="d67f5-115">Aby wyświetlić zadania planowania historycznego, dostępne są dwie opcje</span><span class="sxs-lookup"><span data-stu-id="d67f5-115">To view historical planning jobs, there are two options.</span></span> 

1. <span data-ttu-id="d67f5-116">Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**, a następnie w okienku akcji wybierz opcję **historia**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-116">Go to **Master planning \> Setup \> Plans \> Master plans**, and then, on the Action Pane, select **History**.</span></span> <span data-ttu-id="d67f5-117">Po zaznaczeniu żądanego zadania wybierz opcję **zapytania**, a następnie wybierz opcję **Wyświetl postęp**</span><span class="sxs-lookup"><span data-stu-id="d67f5-117">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>
1. <span data-ttu-id="d67f5-118">Przejdź do **Planowanie główne \> Obszary robocze \> Planowanie główne** na kafelku planowanie główne kliknij pozycję **historia**</span><span class="sxs-lookup"><span data-stu-id="d67f5-118">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **History**.</span></span> <span data-ttu-id="d67f5-119">Po zaznaczeniu żądanego zadania wybierz opcję **zapytania**, a następnie wybierz opcję **Wyświetl postęp**</span><span class="sxs-lookup"><span data-stu-id="d67f5-119">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="d67f5-120">Aby wyświetlić zadania planowania aktywnego, dostępne są dwie opcje</span><span class="sxs-lookup"><span data-stu-id="d67f5-120">To view active planning jobs, there are two options.</span></span> 
1. <span data-ttu-id="d67f5-121">Przejdź do **Planowanie główne \> Obszary robocze \> Planowanie główne**, w okienku akcji wybierz **Proces planowania produktów niegotowych**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-121">Go to **Master planning \> Workspaces \> Master planning**, on the Action Pane, select **Unfinished planning process**.</span></span> <span data-ttu-id="d67f5-122">Po zaznaczeniu żądanego zadania wybierz opcję **zapytania**, a następnie wybierz opcję **Wyświetl postęp**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-122">With the desired job selected, select **Inquiries**,  and then select **View progress**.</span></span>
1. <span data-ttu-id="d67f5-123">Przejdź do **Planowanie główne \> Obszary robocze \> Planowanie główne** na kafelku planowanie główne kliknij pozycję **Zobacz postęp**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-123">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **View progress**.</span></span> <span data-ttu-id="d67f5-124">Po zaznaczeniu żądanego zadania wybierz opcję **zapytania**, a następnie wybierz opcję **Wyświetl postęp**</span><span class="sxs-lookup"><span data-stu-id="d67f5-124">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="d67f5-125">Uwaga zadania aktywne można wyświetlać tylko w przypadku przetwarzania zadania planowania.</span><span class="sxs-lookup"><span data-stu-id="d67f5-125">Note you can view active jobs only when a planning job is processing.</span></span>

### <a name="analyze-a-master-planning-job"></a><span data-ttu-id="d67f5-126">Analizowanie zadania planowania głównego</span><span class="sxs-lookup"><span data-stu-id="d67f5-126">Analyze a master planning job</span></span>

<span data-ttu-id="d67f5-127">Na wykresie Gantta można rozwinąć każdy z poniższych procesów planowania, aby wyświetlić dodatkowe szczegóły dotyczące czasu trwania:</span><span class="sxs-lookup"><span data-stu-id="d67f5-127">In the Gantt chart, you can expand each of the following planning processes to view additional details about the time that is spent:</span></span>

- <span data-ttu-id="d67f5-128">Przygotowanie</span><span class="sxs-lookup"><span data-stu-id="d67f5-128">Initializing</span></span>
- <span data-ttu-id="d67f5-129">Usuwanie i wstawianie danych</span><span class="sxs-lookup"><span data-stu-id="d67f5-129">Deleting and inserting data</span></span>
- <span data-ttu-id="d67f5-130">Planowanie zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="d67f5-130">Coverage planning</span></span>
- <span data-ttu-id="d67f5-131">Opóźnienia</span><span class="sxs-lookup"><span data-stu-id="d67f5-131">Delays</span></span>
- <span data-ttu-id="d67f5-132">Komunikaty akcji</span><span class="sxs-lookup"><span data-stu-id="d67f5-132">Action messages</span></span>
- <span data-ttu-id="d67f5-133">Finalizacja</span><span class="sxs-lookup"><span data-stu-id="d67f5-133">Finalization</span></span>
- <span data-ttu-id="d67f5-134">Automatyczne akceptowanie</span><span class="sxs-lookup"><span data-stu-id="d67f5-134">Auto-firming</span></span>

<span data-ttu-id="d67f5-135">Wykres Gantta jest przydatnym narzędziem, jeśli ma być wyświetlany wpływ użycia komunikatów akcji.</span><span class="sxs-lookup"><span data-stu-id="d67f5-135">The Gantt chart is a useful tool if you want to view the impact of using action messages.</span></span>

#### <a name="navigation-in-the-gantt-chart"></a><span data-ttu-id="d67f5-136">Nawigacja na wykresie Gantta</span><span class="sxs-lookup"><span data-stu-id="d67f5-136">Navigation in the Gantt chart</span></span>

- <span data-ttu-id="d67f5-137">Aby rozwinąć zaznaczoną grupę i wyświetlić szczegóły, należy wybrać znak plus (**+**) w widoku drzewa.</span><span class="sxs-lookup"><span data-stu-id="d67f5-137">To expand the selected group and show the details, select the plus sign (**+**) in the tree view.</span></span>
- <span data-ttu-id="d67f5-138">Aby zwinąć zaznaczoną grupę, należy wybrać znak minus (**-**) w widoku drzewa.</span><span class="sxs-lookup"><span data-stu-id="d67f5-138">To collapse the selected group, select the minus sign (**–**) in the tree view.</span></span>
- <span data-ttu-id="d67f5-139">Do nawigacji można wykorzystać klawiaturę.</span><span class="sxs-lookup"><span data-stu-id="d67f5-139">You can use your keyboard for navigation.</span></span> <span data-ttu-id="d67f5-140">Za pomocą klawiszy **Strzałka w górę** i **Strzałka w dół** można przechodzić między wierszami.</span><span class="sxs-lookup"><span data-stu-id="d67f5-140">Use the **Up arrow** and **Down arrow** keys to move between rows.</span></span> <span data-ttu-id="d67f5-141">Za pomocą klawiszy **Strzałka w prawo** i **Strzałka w lewo** można rozwijać i zwijać grupy.</span><span class="sxs-lookup"><span data-stu-id="d67f5-141">Use the **Right arrow** and **Left arrow** keys to expand and collapse groups.</span></span>
- <span data-ttu-id="d67f5-142">Aby otworzyć lub zamknąć wszystkie poziomy na wykresie Gantta, wybierz opcję **Rozwiń wszystkie** lub **Zwiń wszystko**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-142">To open or close all levels in the Gantt chart, select **Expand all** or **Collapse all**.</span></span>
- <span data-ttu-id="d67f5-143">Aby wyświetlić odpowiedni czas przetwarzania, umieść wskaźnik myszy nad zadaniem.</span><span class="sxs-lookup"><span data-stu-id="d67f5-143">To view the related processing time, hover over a task.</span></span> <span data-ttu-id="d67f5-144">(Zadania są najniższym poziomem wykresu Gantta.)</span><span class="sxs-lookup"><span data-stu-id="d67f5-144">(Tasks are the lowest level in the Gantt chart.)</span></span>

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a><span data-ttu-id="d67f5-145">Umożliwia wyświetlenie dodatkowego przebiegu planowania głównego w celu porównania zadań</span><span class="sxs-lookup"><span data-stu-id="d67f5-145">View an additional master planning run to compare jobs</span></span>

<span data-ttu-id="d67f5-146">Po wybraniu zadania planowania głównego w polu **Pokaż dodatkowe uruchomienie planowania głównego** można wyświetlić dodatkowy przebieg planowania głównego na wykresie Gantta i porównać te dwa zadania.</span><span class="sxs-lookup"><span data-stu-id="d67f5-146">By selecting a master planning job on field **Show additional master planning run**, you can view an additional master planning run in the Gantt chart and compare the two jobs.</span></span>

#### <a name="bom-level-display"></a><span data-ttu-id="d67f5-147">Wyświetlanie na poziomie BOM</span><span class="sxs-lookup"><span data-stu-id="d67f5-147">BOM-level display</span></span>

<span data-ttu-id="d67f5-148">Poziomy BOM są wyświetlane w różny sposób do planowania zapotrzebowania, opóźnień, akcji i akceptacji.</span><span class="sxs-lookup"><span data-stu-id="d67f5-148">Bill of materials (BOM) levels are shown differently for coverage planning, delays, actions, and firming.</span></span>

- <span data-ttu-id="d67f5-149">**Planowanie zapotrzebowania** — poziomy BOM są wyświetlane zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="d67f5-149">**Coverage planning** – BOM levels are shown as expected.</span></span> <span data-ttu-id="d67f5-150">Są one obliczane od góry do dołu.</span><span class="sxs-lookup"><span data-stu-id="d67f5-150">They are calculated from the top down.</span></span>

    <span data-ttu-id="d67f5-151">**Przykład:** poziom BOM 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="d67f5-151">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="d67f5-152">**Opóźnienia** — poziomy BOM są wyświetlane jako poziomy BOM planowania zapotrzebowania pomnożone przez-1.</span><span class="sxs-lookup"><span data-stu-id="d67f5-152">**Delays** – BOM levels are shown as the coverage planning BOM levels multiplied by –1.</span></span> <span data-ttu-id="d67f5-153">(Innymi słowy, ze znakiem ujemnym.)</span><span class="sxs-lookup"><span data-stu-id="d67f5-153">(In other words, they have a negative sign.)</span></span>

    <span data-ttu-id="d67f5-154">**Przykład:** poziom BOM –2, –1, 0</span><span class="sxs-lookup"><span data-stu-id="d67f5-154">**Example:** BOM level –2, –1, 0</span></span>

- <span data-ttu-id="d67f5-155">**Komunikat akcji** — poziomy BOM są wyświetlane zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="d67f5-155">**Action message** – BOM levels are shown as expected.</span></span> <span data-ttu-id="d67f5-156">Są one obliczane od góry do dołu.</span><span class="sxs-lookup"><span data-stu-id="d67f5-156">They are calculated from the top down.</span></span>

    <span data-ttu-id="d67f5-157">**Przykład:** poziom BOM 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="d67f5-157">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="d67f5-158">**Automatyczne akceptowanie** — poziomy BOM są wyświetlane jako 999 minus poziom BOM planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="d67f5-158">**Auto-firming** – BOM levels are shown as 999 minus the coverage planning BOM level.</span></span>

    <span data-ttu-id="d67f5-159">**Przykład:** poziom BOM 999, 998, 997</span><span class="sxs-lookup"><span data-stu-id="d67f5-159">**Example:** BOM level 999, 998, 997</span></span>

<span data-ttu-id="d67f5-160">W poniższej tabeli podsumowano zachowanie.</span><span class="sxs-lookup"><span data-stu-id="d67f5-160">The following table summarizes the behavior.</span></span>

| <span data-ttu-id="d67f5-161">Wyświetlany poziom BOM</span><span class="sxs-lookup"><span data-stu-id="d67f5-161">BOM level that is shown</span></span> | <span data-ttu-id="d67f5-162">Pozycja gotowa</span><span class="sxs-lookup"><span data-stu-id="d67f5-162">End item</span></span> | <span data-ttu-id="d67f5-163">Składnik podrzędny</span><span class="sxs-lookup"><span data-stu-id="d67f5-163">Subcomponent</span></span> | <span data-ttu-id="d67f5-164">Surowiec</span><span class="sxs-lookup"><span data-stu-id="d67f5-164">Raw material</span></span> |
|---|---|---|---|
| <span data-ttu-id="d67f5-165">Planowanie zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="d67f5-165">Coverage planning</span></span> | <span data-ttu-id="d67f5-166">0</span><span class="sxs-lookup"><span data-stu-id="d67f5-166">0</span></span> | <span data-ttu-id="d67f5-167">1</span><span class="sxs-lookup"><span data-stu-id="d67f5-167">1</span></span> | <span data-ttu-id="d67f5-168">2</span><span class="sxs-lookup"><span data-stu-id="d67f5-168">2</span></span> |
| <span data-ttu-id="d67f5-169">Opóźnienia</span><span class="sxs-lookup"><span data-stu-id="d67f5-169">Delays</span></span> | <span data-ttu-id="d67f5-170">0</span><span class="sxs-lookup"><span data-stu-id="d67f5-170">0</span></span> | <span data-ttu-id="d67f5-171">-1</span><span class="sxs-lookup"><span data-stu-id="d67f5-171">–1</span></span> | <span data-ttu-id="d67f5-172">-2</span><span class="sxs-lookup"><span data-stu-id="d67f5-172">–2</span></span> |
| <span data-ttu-id="d67f5-173">Komunikat akcji</span><span class="sxs-lookup"><span data-stu-id="d67f5-173">Action message</span></span> | <span data-ttu-id="d67f5-174">0</span><span class="sxs-lookup"><span data-stu-id="d67f5-174">0</span></span> | <span data-ttu-id="d67f5-175">1</span><span class="sxs-lookup"><span data-stu-id="d67f5-175">1</span></span> | <span data-ttu-id="d67f5-176">2</span><span class="sxs-lookup"><span data-stu-id="d67f5-176">2</span></span> |
| <span data-ttu-id="d67f5-177">Automatyczne akceptowanie</span><span class="sxs-lookup"><span data-stu-id="d67f5-177">Auto-firming</span></span> | <span data-ttu-id="d67f5-178">999</span><span class="sxs-lookup"><span data-stu-id="d67f5-178">999</span></span> | <span data-ttu-id="d67f5-179">998</span><span class="sxs-lookup"><span data-stu-id="d67f5-179">998</span></span> | <span data-ttu-id="d67f5-180">997</span><span class="sxs-lookup"><span data-stu-id="d67f5-180">997</span></span> |

#### <a name="visualize-progress"></a><span data-ttu-id="d67f5-181">Postęp wizualizacji</span><span class="sxs-lookup"><span data-stu-id="d67f5-181">Visualize progress</span></span>

<span data-ttu-id="d67f5-182">W przypadku wyświetlenia aktualnie uruchomionego zadania planowania głównego postęp jest pokazywany za pośrednictwem kolorów na wykresie Gantta.</span><span class="sxs-lookup"><span data-stu-id="d67f5-182">If you view a master planning job that is currently running, progress is shown through colors in the Gantt chart.</span></span> <span data-ttu-id="d67f5-183">Poniższe kolory dotyczą niebieskiego motywu.</span><span class="sxs-lookup"><span data-stu-id="d67f5-183">The following colors apply to the blue theme.</span></span> <span data-ttu-id="d67f5-184">W przypadku innych kompozycji kolorów kolory są różne.</span><span class="sxs-lookup"><span data-stu-id="d67f5-184">For other color themes, the colors will differ.</span></span>

- <span data-ttu-id="d67f5-185">**Ciemnoniebieski** — zadania planowania zakończonego</span><span class="sxs-lookup"><span data-stu-id="d67f5-185">**Dark blue** – Completed planning tasks.</span></span>
- <span data-ttu-id="d67f5-186">**Pomarańczowy** — zadanie, które jest obecnie w toku.</span><span class="sxs-lookup"><span data-stu-id="d67f5-186">**Orange** – The task that is currently in progress.</span></span>
- <span data-ttu-id="d67f5-187">**Jasnoniebieski** — oszacowanie pozostałych zadań.</span><span class="sxs-lookup"><span data-stu-id="d67f5-187">**Light blue** – The estimate for remaining tasks.</span></span>

<span data-ttu-id="d67f5-188">Kolor jest pokazywany tylko na najniższym poziomie na wykresie Gantta.</span><span class="sxs-lookup"><span data-stu-id="d67f5-188">The color is shown only on the lowest level in the Gantt chart.</span></span> <span data-ttu-id="d67f5-189">Wybierz opcję **Rozwiń wszystko**, aby wyświetlić wszystkie zadania w ramach zadania planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="d67f5-189">Select **Expand all** to view all tasks in the master planning job.</span></span> <span data-ttu-id="d67f5-190">Oszacowanie pozostałych zadań jest oparte na historycznych zadaniach planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="d67f5-190">The estimate of remaining tasks is based on historical master planning jobs.</span></span>

## <a name="run-master-planning-and-track-processing-time"></a><span data-ttu-id="d67f5-191">Uruchamianie planowania głównego i czasu przetwarzania śledzenia</span><span class="sxs-lookup"><span data-stu-id="d67f5-191">Run master planning and track processing time</span></span>

1. <span data-ttu-id="d67f5-192">Na domyślnym pulpicie nawigacyjnym wybierz opcję **Planowanie główne**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-192">On the default dashboard, select **Master planning**.</span></span>
1. <span data-ttu-id="d67f5-193">W polu **Plan** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d67f5-193">In the **Plan** field, enter or select a value.</span></span>
1. <span data-ttu-id="d67f5-194">Wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-194">Select **Run**.</span></span>
1. <span data-ttu-id="d67f5-195">W opcji **Śledź czas przetwarzania** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-195">Set the **Track processing time** option to **Yes**.</span></span>
1. <span data-ttu-id="d67f5-196">W polu **Liczba wątków** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="d67f5-196">In the **Number of threads** field, enter a number.</span></span>
1. <span data-ttu-id="d67f5-197">W **Rekordy do uwzględnienia** na skróconej karcie, wybierz opcję **Filtr**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-197">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="d67f5-198">W siatce wybierz wiersz, w którym **pole** w polu ma wartość **kod towaru**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-198">In the grid, select the row where the **Field** field is set to **Item number**.</span></span>
1. <span data-ttu-id="d67f5-199">Wprowadź wartość w polu **Kryterium**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-199">In the **Criteria** field, enter a value.</span></span>
1. <span data-ttu-id="d67f5-200">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d67f5-200">Select **OK**.</span></span>
