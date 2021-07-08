---
title: Obciążenia pracą dotyczące uruchomienia produkcji dla jednostek skalowania chmury i urządzenia brzegowego
description: W tym temacie opisano, jak działa obciążenie pracą nad wykonywaniem produkcji z jednostkami skali w chmurze i urządzenia brzegowego.
author: cabeln
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: b1e2006c0d9b9effe331a644aaaa9fa33ff2fb7c
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270542"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a><span data-ttu-id="865cb-103">Obciążenia pracą dotyczące uruchomienia produkcji dla jednostek skalowania chmury i urządzenia brzegowego</span><span class="sxs-lookup"><span data-stu-id="865cb-103">Manufacturing execution workloads for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]

> [!WARNING]
> <span data-ttu-id="865cb-104">Obciążenie związane z produkcją jest w tym momencie dostępne w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="865cb-104">The manufacturing execution workload is available in preview at this point in time.</span></span>
> <span data-ttu-id="865cb-105">Nie wszystkie funkcje biznesowe są w pełni obsługiwane w podglądzie publicznym, gdy są używane jednostki skali obciążenia pracą.</span><span class="sxs-lookup"><span data-stu-id="865cb-105">Some business functionality isn't fully supported in the public preview when workload scale units are used.</span></span>

<span data-ttu-id="865cb-106">W wykonaniu produkcyjnym jednostki wagowe zapewniają następujące możliwości:</span><span class="sxs-lookup"><span data-stu-id="865cb-106">In manufacturing execution, scale units deliver the following capabilities:</span></span>

- <span data-ttu-id="865cb-107">Operatorzy maszyn i kierownicy mogą uzyskać dostęp do operacyjnego planu produkcji.</span><span class="sxs-lookup"><span data-stu-id="865cb-107">Machine operators and shop floor supervisors can access the operational production plan.</span></span>
- <span data-ttu-id="865cb-108">Operatorzy maszynowi mogą regularnie aktualizować plan, uruchamiając dyskretne i przetwarzające zadania produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="865cb-108">Machine operators can keep the plan up to date by running discrete and process manufacturing jobs.</span></span>
- <span data-ttu-id="865cb-109">Kierownik produkcji może skorygować plan operacyjny.</span><span class="sxs-lookup"><span data-stu-id="865cb-109">The shop floor supervisor can adjust the operational plan.</span></span>
- <span data-ttu-id="865cb-110">Pracownicy mogą uzyskać dostęp do modułu czas i frekwencja do zarejestrowania i wyrejestrowania się na brzegu, aby zapewnić poprawne Obliczanie wynagrodzeń pracowników.</span><span class="sxs-lookup"><span data-stu-id="865cb-110">Workers can access time and attendance for clock-in and clock-out on the edge, to ensure correct worker pay calculation.</span></span>

<span data-ttu-id="865cb-111">W tym temacie opisano, jak działa obciążenie pracą nad wykonywaniem produkcji z jednostkami skali w chmurze i urządzenia brzegowego.</span><span class="sxs-lookup"><span data-stu-id="865cb-111">This topic describes how manufacturing execution workloads work with cloud and edge scale units.</span></span>

## <a name="the-manufacturing-lifecycle"></a><span data-ttu-id="865cb-112">Cykl produkcyjny</span><span class="sxs-lookup"><span data-stu-id="865cb-112">The manufacturing lifecycle</span></span>

<span data-ttu-id="865cb-113">Na poniższej ilustracji przedstawiono cykl produkcyjny podzielony na trzy etapy: *Planowanie*, *wykonywanie* i *finalizowanie*.</span><span class="sxs-lookup"><span data-stu-id="865cb-113">As the following illustration shows, the manufacturing lifecycle is divided into three phases: *Plan*, *Execute*, and *Finalize*.</span></span>

<span data-ttu-id="865cb-114">[![Fazy uruchamiania produkcji w przypadku korzystania z jednego środowiska](media/mes-phases.png "Fazy uruchamiania produkcji w przypadku korzystania z jednego środowiska")](media/mes-phases-large.png)</span><span class="sxs-lookup"><span data-stu-id="865cb-114">[![Manufacturing execution phases when a single environment is used](media/mes-phases.png "Manufacturing execution phases when a single environment is used")](media/mes-phases-large.png)</span></span>

<span data-ttu-id="865cb-115">_Faza planu_ obejmuje definicje produktów, planowanie, tworzenie i planowanie zamówień oraz zwalnianie.</span><span class="sxs-lookup"><span data-stu-id="865cb-115">The _Plan_ phase includes product definition, planning, order creation and scheduling, and release.</span></span> <span data-ttu-id="865cb-116">Krok wydania wskazuje przejście z fazy _planu_ do fazy _wykonania_.</span><span class="sxs-lookup"><span data-stu-id="865cb-116">The release step indicates the transition from the _Plan_ phase to the _Execute_ phase.</span></span> <span data-ttu-id="865cb-117">Po zwolnieniu zlecenia produkcyjnego zadania zlecenia produkcyjnego będą widoczne w oddziale produkcyjnym i gotowe do wykonania.</span><span class="sxs-lookup"><span data-stu-id="865cb-117">When a production order is released, the production order jobs will be visible on the production floor and ready for execution.</span></span>

<span data-ttu-id="865cb-118">Jeśli zadanie produkcji jest oznaczone jako ukończone, następuje przejście z _fazy wykonania_ do _fazy finalizowania_.</span><span class="sxs-lookup"><span data-stu-id="865cb-118">When a production job is marked as completed, it moves from the _Execute_ phase to the _Finalize_ phase.</span></span> <span data-ttu-id="865cb-119">W fazie _finalizowania_ rejestracje z fazy *wykonania* przechodzą przez przepływ pracy zatwierdzania, gdzie są one obliczane, zatwierdzane i przenoszone.</span><span class="sxs-lookup"><span data-stu-id="865cb-119">In the _Finalize_ phase, the registrations from the *Execute* phase go through an approval workflow, where they are calculated, approved, and transferred.</span></span> <span data-ttu-id="865cb-120">W tym momencie zlecenie produkcyjne zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="865cb-120">At that point, the production order is completed.</span></span> <span data-ttu-id="865cb-121">Z tego powodu generowana jest podstawa wynagrodzenia pracowników.</span><span class="sxs-lookup"><span data-stu-id="865cb-121">Therefore, the basis for the workers' pay is generated.</span></span>

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a><span data-ttu-id="865cb-122">Dzielenie fazy wykonania na oddzielne obciążenie pracą</span><span class="sxs-lookup"><span data-stu-id="865cb-122">Splitting the Execute phase into a separate workload</span></span>

<span data-ttu-id="865cb-123">W poniższej ilustracji pokazano, kiedy są używane jednostki skalowania, _faza wykonania_ jest dzielona jako oddzielne obciążenie pracą.</span><span class="sxs-lookup"><span data-stu-id="865cb-123">As the following illustration shows, when scale units are used, the _Execute_ phase is split out as a separate workload.</span></span>

<span data-ttu-id="865cb-124">[![Fazy uruchamiania produkcji podczas używania jednostek miary](media/mes-phases-workloads.png "Fazy uruchamiania produkcji podczas używania jednostek miary")](media/mes-phases-workloads-large.png)</span><span class="sxs-lookup"><span data-stu-id="865cb-124">[![Manufacturing execution phases when scale units are used](media/mes-phases-workloads.png "Manufacturing execution phases when scale units are used")](media/mes-phases-workloads-large.png)</span></span>

<span data-ttu-id="865cb-125">Obecnie model pochodzi z instalacji z jednym wystąpieniem do modelu opartego na centrum i jednostkach skali.</span><span class="sxs-lookup"><span data-stu-id="865cb-125">The model now goes from a single-instance installation to a model that is based on the hub and scale units.</span></span> <span data-ttu-id="865cb-126">Fazy _Planowanie_ i _Finalizacja_ są wykonywane jako operacje zaplecza w centrali, a obciążenie pracą nad produkcją jest wykonywane na jednostkach skali.</span><span class="sxs-lookup"><span data-stu-id="865cb-126">The _Plan_ and _Finalize_ phases run as back-office operations on the hub, and the manufacturing execution workload runs on the scale units.</span></span> <span data-ttu-id="865cb-127">Dane są przesyłane asynchronicznie między jednostkami centrum i skali.</span><span class="sxs-lookup"><span data-stu-id="865cb-127">Data is transferred asynchronously between the hub and scale units.</span></span>

<span data-ttu-id="865cb-128">Po zwolnieniu zlecenia produkcyjnego w centrum wszystkie dane wymagane do przetworzenia zadań produkcyjnych są przenoszone do jednostki skali.</span><span class="sxs-lookup"><span data-stu-id="865cb-128">When a production order is released on the hub, all data that is required to process production jobs is transferred to the scale unit.</span></span> <span data-ttu-id="865cb-129">Dane te obejmują zlecenia produkcyjne, marszruty produkcji, BOM i produkty.</span><span class="sxs-lookup"><span data-stu-id="865cb-129">This data includes production orders, production routes, bills of materials, and products.</span></span> <span data-ttu-id="865cb-130">Dane, które nie są związane ze zleceniem produkcyjnym (np. działania pośrednie, kody nieobecności i parametry produkcji) są również przenoszone z centrum do jednostki skali.</span><span class="sxs-lookup"><span data-stu-id="865cb-130">Data that isn't related to a production order (such as indirect activities, absence codes, and production parameters) is also transferred from the hub to the scale unit.</span></span> <span data-ttu-id="865cb-131">Z reguły dane pochodzące z centrum i przenoszone do jednostki skali mogą być tworzone lub aktualizowane tylko w centrali.</span><span class="sxs-lookup"><span data-stu-id="865cb-131">As a rule, data that originates from the hub and that is transferred to the scale unit can be created or updated only on the hub.</span></span> <span data-ttu-id="865cb-132">Na przykład nie można utworzyć nowego kodu nieobecności lub działania pośredniego w jednostce skali, &mdash;które mogą być używane tylko do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="865cb-132">For example, a new absence code or indirect activity can't be created on the scale unit&mdash;they can be used only for registration.</span></span> <span data-ttu-id="865cb-133">Rejestracje dokonywane w jednostkach skali podczas wykonywania są następnie przenoszone do centrum, w którym są przetwarzane Zatwierdzanie czasu i obecności, zapasy i aktualizacje finansowe.</span><span class="sxs-lookup"><span data-stu-id="865cb-133">The registrations that are made on the scale unit during execution are then transferred to the hub, where time and attendance approval, inventory, and financial updates are processed.</span></span>

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a><span data-ttu-id="865cb-134">Zadania modułu uruchomienie produkcji, które mogą być uruchamiane przy obciążeniu</span><span class="sxs-lookup"><span data-stu-id="865cb-134">Manufacturing execution tasks that can be run on workloads</span></span>

<span data-ttu-id="865cb-135">Następujące zadania dotyczące wykonania produkcji mogą być obecnie uruchamiane przy obciążeniu, gdy używane są jednostki skali:</span><span class="sxs-lookup"><span data-stu-id="865cb-135">The following manufacturing execution tasks can currently be run on workloads when scale units are used:</span></span>

- <span data-ttu-id="865cb-136">Rejestrowanie, logowanie, Wyrejestrowywanie i nieobecność</span><span class="sxs-lookup"><span data-stu-id="865cb-136">Clock-in, log-in, clock-out, and absence</span></span>
- <span data-ttu-id="865cb-137">Uruchom zadanie</span><span class="sxs-lookup"><span data-stu-id="865cb-137">Start job</span></span>
- <span data-ttu-id="865cb-138">Pakiety zadań</span><span class="sxs-lookup"><span data-stu-id="865cb-138">Bundle jobs</span></span>
- <span data-ttu-id="865cb-139">Zgłaszanie postępu</span><span class="sxs-lookup"><span data-stu-id="865cb-139">Report progress</span></span>
- <span data-ttu-id="865cb-140">Raportuj odpadki</span><span class="sxs-lookup"><span data-stu-id="865cb-140">Report scrap</span></span>
- <span data-ttu-id="865cb-141">Działanie pośrednie</span><span class="sxs-lookup"><span data-stu-id="865cb-141">Indirect activity</span></span>
- <span data-ttu-id="865cb-142">Przerwa</span><span class="sxs-lookup"><span data-stu-id="865cb-142">Break</span></span>
- <span data-ttu-id="865cb-143">Raportuj jako zakończone i odłożone (wymaga uruchomienia obciążenia wykonawczego magazynu na jednostce skalowania patrz również [Reportuj jako zakończone i odłożone na jednostce skalowania](#RAF))</span><span class="sxs-lookup"><span data-stu-id="865cb-143">Report as finished and putaway (requires that you also run the warehouse execution workload on your scale unit, see also [Report as finished and putaway on a scale unit](#RAF))</span></span>

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a><span data-ttu-id="865cb-144">Praca z obciążeniem pracą produkcyjną w centrum</span><span class="sxs-lookup"><span data-stu-id="865cb-144">Working with manufacturing execution workloads on the hub</span></span>

<span data-ttu-id="865cb-145">Zazwyczaj procesy wymagane do uruchomienia obciążeń uruchomienia produkcji są automatycznie uruchamiane w celu zsynchronizowania centrum i wszystkich jednostek skalowania w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="865cb-145">Usually, the processes that are required to run manufacturing execution workloads run automatically to keep the hub and all the scale units in sync, as needed.</span></span> <span data-ttu-id="865cb-146">Jeśli jednak występują problemy, można ręcznie wyzwolić przetwarzanie rejestracji wstępnych otrzymanych z obciążenia pracą i/lub sprawdzić dziennik przetwarzania rejestracji.</span><span class="sxs-lookup"><span data-stu-id="865cb-146">However, if you're having trouble, you can manually trigger the processing of raw registrations that are received from workloads and/or check the registration processing log.</span></span>

### <a name="manually-process-raw-registrations"></a><span data-ttu-id="865cb-147">Ręczne przetwarzanie rejestracji wstępnych</span><span class="sxs-lookup"><span data-stu-id="865cb-147">Manually process raw registrations</span></span>

<span data-ttu-id="865cb-148">Zadanie wsadowe w module Supply Chain Management jest uruchamiane automatycznie w celu przetworzenia wszystkich rejestracji, które zostały przyjęte na podstawie obciążeń.</span><span class="sxs-lookup"><span data-stu-id="865cb-148">A batch job in Supply Chain Management runs automatically to process all the registrations that have been received from the workloads.</span></span> <span data-ttu-id="865cb-149">To zadanie tworzy wymagane arkusze produkcyjne i wpisy w dzienniku połowowym podczas przetwarzania rejestracji dla ukończonego zadania dotyczącego obciążenia pracą.</span><span class="sxs-lookup"><span data-stu-id="865cb-149">This job creates the required production journals and logbook entries when a registration is processed for a completed job on the workload.</span></span>

<span data-ttu-id="865cb-150">Mimo że zadanie zazwyczaj jest uruchamiane automatycznie, można je uruchomić ręcznie w dowolnym momencie, logując się do koncentratora i przechodząc do **kontroli produkcji\> Okresowe zadania \>Zarządzanie obciążeniem backoffice\> Przetwarzanie rejestracji wstępnych**.</span><span class="sxs-lookup"><span data-stu-id="865cb-150">Although the job usually runs automatically, you can run it manually at any time by signing in to the hub and going to **Production control \> Periodic tasks \> Backoffice workload management \> Process raw registrations**.</span></span>

### <a name="check-the-raw-registration-processing-log"></a><span data-ttu-id="865cb-151">Sprawdź dziennik przetwarzania rejestracji nieprzetworzonej</span><span class="sxs-lookup"><span data-stu-id="865cb-151">Check the raw registration processing log</span></span>

<span data-ttu-id="865cb-152">Aby przejrzeć dziennik przetwarzania rejestracji, zaloguj się do centrum, a następnie przejdź do obszaru **Kontrola produkcji \> Zadania okresowe \> Zarządzanie przepływem pracy backoffice \> Dziennik przetwarzania rejestracji wstępnych**.</span><span class="sxs-lookup"><span data-stu-id="865cb-152">To review the registration processing log, sign in to the hub, and go to **Production control \> Periodic tasks \> Backoffice workload management \> Raw registration processing log**.</span></span> <span data-ttu-id="865cb-153">Na stronie **Dziennik przetwarzania rejestracji wstępnych** jest wyświetlana lista przetworzonych rejestracji wstępnych oraz stan każdej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="865cb-153">The **Raw registration processing log** page shows a list of processed raw registrations and the status of each registration.</span></span>

<span data-ttu-id="865cb-154">![Strona dziennika przetwarzania rejestracji nieprzetworzonej](media/mes-processing-log.png "Strona dziennika przetwarzania rejestracji nieprzetworzonej")</span><span class="sxs-lookup"><span data-stu-id="865cb-154">![Raw registration processing log page](media/mes-processing-log.png "Raw registration processing log page")</span></span>

<span data-ttu-id="865cb-155">Można pracować z dowolną rejestracją na liście, zaznaczając ją, a następnie wybierając jeden z następujących przycisków w okienku akcji:</span><span class="sxs-lookup"><span data-stu-id="865cb-155">You can work on any registration in the list by selecting it and then selecting one of the following buttons on the Action Pane:</span></span>

- <span data-ttu-id="865cb-156">**Proces** — umożliwia ręczne przetworzenie wybranej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="865cb-156">**Process** – Manually process the selected registration.</span></span> <span data-ttu-id="865cb-157">Ta akcja może być przydatna, jeśli zadanie _Rejestracji wstępnych procesu_ nie zostało uruchomione lub nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="865cb-157">This action can be useful if the _Process raw registrations_ job hasn't run, or if it failed.</span></span>
- <span data-ttu-id="865cb-158">**Anuluj** — umożliwia anulowanie wybranej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="865cb-158">**Cancel** – Cancel the selected registration.</span></span>

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a><span data-ttu-id="865cb-159">Praca z obciążeniem pracą produkcyjną na jednostce skali</span><span class="sxs-lookup"><span data-stu-id="865cb-159">Working with manufacturing execution workloads on a scale unit</span></span>

<span data-ttu-id="865cb-160">Zazwyczaj procesy wymagane do uruchomienia obciążeń uruchomienia produkcji są automatycznie uruchamiane w celu zsynchronizowania centrum i wszystkich jednostek skalowania w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="865cb-160">Usually, the processes that are required to run manufacturing execution workloads run automatically to keep the hub and all the scale units in sync, as needed.</span></span> <span data-ttu-id="865cb-161">Jeśli jednak występują problemy, można sprawdzić historię zamówień, które zostały przetworzone na jednostkę skali, lub ręcznie uruchomić _Centrum wytwarzania na potrzeby skalowania procesora komunikatów jednostki_.</span><span class="sxs-lookup"><span data-stu-id="865cb-161">However, if you're having trouble, you can check the history of orders that have been processed on a scale unit or manually run the _Manufacturing hub to scale unit message processor_ job.</span></span>

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a><span data-ttu-id="865cb-162">Umożliwia wyświetlenie historii zadań produkcji, które zostały przetworzone na jednostkę skali</span><span class="sxs-lookup"><span data-stu-id="865cb-162">View the history of manufacturing jobs that have been processed on a scale unit</span></span>

<span data-ttu-id="865cb-163">Aby przejrzeć historię zadań produkcji, które zostały przetworzone na jednostkę skali, należy zalogować się na jednostce skalowania i przejść do obszaru **Kontrola produkcji \> Zadania okresowe \>Zarządzanie obciążeniem backoffice  \> Historia przetwarzania zadań produkcji**.</span><span class="sxs-lookup"><span data-stu-id="865cb-163">To review the history of manufacturing jobs that have been processed on a scale unit, sign in to the scale unit machine, and go to **Production control \> Periodic tasks \> Backoffice workload management \> Manufacturing jobs processing history**.</span></span> <span data-ttu-id="865cb-164">Na stronie **Historia przetwarzania zadań produkcji** jest wyświetlana historia przetwarzania zleceń produkcyjnych na jednostkę skali.</span><span class="sxs-lookup"><span data-stu-id="865cb-164">The **Manufacturing jobs processing history** page shows the processing history of the production orders on the scale unit.</span></span> <span data-ttu-id="865cb-165">Można pracować z dowolnym zleceniem produkcji na liście, zaznaczając go, a następnie wybierając jeden z następujących przycisków w okienku akcji:</span><span class="sxs-lookup"><span data-stu-id="865cb-165">You can work on any production order in the list by selecting it and then selecting one of the following buttons on the Action Pane:</span></span>

- <span data-ttu-id="865cb-166">**Proces** — umożliwia ręczne przetworzenie wybranego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="865cb-166">**Process** – Manually process the selected production order.</span></span>
- <span data-ttu-id="865cb-167">**Anuluj** — umożliwia anulowanie wybranego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="865cb-167">**Cancel** – Cancel the selected production order.</span></span>

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a><span data-ttu-id="865cb-168">Zadanie procesora w ramach centrum produkcji dla wiadomości jednostki skalowania</span><span class="sxs-lookup"><span data-stu-id="865cb-168">Manufacturing hub to scale unit message processor job</span></span>

<span data-ttu-id="865cb-169">_Zadanie procesora produkcyjnego w centrum produkcji_ przetwarza dane z centrum do jednostki skali.</span><span class="sxs-lookup"><span data-stu-id="865cb-169">The _Manufacturing hub to scale unit message processor_ job processes data from the hub to the scale unit.</span></span> <span data-ttu-id="865cb-170">To zadanie jest uruchamiane automatycznie po wdrożeniu obciążenia pracą modułu uruchomienie produkcji.</span><span class="sxs-lookup"><span data-stu-id="865cb-170">This job is automatically started when the manufacturing execution workload is deployed.</span></span> <span data-ttu-id="865cb-171">Można jednak uruchomić ją ręcznie w dowolnym momencie, przechodząc do **Kontrola produkcji \> Zadania okresowe \> Zarządzanie obciążeniem backoffice \> Zadanie procesora w ramach centrum produkcji dla wiadomości jednostki skalowania**.</span><span class="sxs-lookup"><span data-stu-id="865cb-171">However, you can run it manually at any time by going to **Production control \> Periodic tasks \> Backoffice workload management \> Manufacturing hub to scale unit message processor**.</span></span>

<a name="RAF"></a>

## <a name="report-as-finished-and-putaway-on-a-scale-unit"></a><span data-ttu-id="865cb-172">Zgłoś jako gotowe i odłóż na jednostce skalowania</span><span class="sxs-lookup"><span data-stu-id="865cb-172">Report as finished and putaway on a scale unit</span></span>

<!-- KFM: 
This section describes how to enable the abilities to report as finished and then putaway finished items when you are using to a scale unit.

### Enable and use report as finished and putaway on a scale unit -->

<span data-ttu-id="865cb-173">W bieżącej wersji operacje raportowania jako zakończone i odłożone (dla produktów gotowych, półproduktów i produktów ubocznych) są obsługiwane przez [obciążenie wykonawcze magazynu](cloud-edge-workload-warehousing.md) (a nie przez obciążenie wykonawcze produkcji).</span><span class="sxs-lookup"><span data-stu-id="865cb-173">In the current release, report as finished and putaway operations (for finished products, co-products, and by-products) are supported by the [warehouse execution workload](cloud-edge-workload-warehousing.md) (not the manufacturing execution workload).</span></span> <span data-ttu-id="865cb-174">Aby korzystać z tej funkcji w przypadku połączenia z jednostką skalowania, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="865cb-174">Therefore, to use this functionality when connected to a scale unit, you must do the following:</span></span>

- <span data-ttu-id="865cb-175">Zainstaluj zarówno obciążenie wykonawcze magazynu, jak i obciążenie wykonawcze produkcji na swojej jednostce skalowania.</span><span class="sxs-lookup"><span data-stu-id="865cb-175">Install both the warehouse execution workload and the manufacturing execution workload on your scale unit.</span></span>
- <span data-ttu-id="865cb-176">Użyj aplikacji mobilnej Warehouse Management, aby zgłosić jako zakończone i przetworzyć pracę odłożenia.</span><span class="sxs-lookup"><span data-stu-id="865cb-176">Use the Warehouse Management mobile app to report as finished and process the putaway work.</span></span> <span data-ttu-id="865cb-177">Interfejs wykonywania produkcji nie obsługuje obecnie tych procesów.</span><span class="sxs-lookup"><span data-stu-id="865cb-177">The production floor execution interface does not currently support these processes.</span></span>

<!-- KFM: API details needed

### Customize report as finished and putaway functionality

 -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
