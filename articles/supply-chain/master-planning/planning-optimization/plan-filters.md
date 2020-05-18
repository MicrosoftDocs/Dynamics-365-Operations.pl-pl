---
title: Stosowanie filtrów do planu
description: W tym temacie wyjaśniono, jak używać filtrów w planie, gdy używana jest funkcja optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 9ddf9934965bd06ec805731a1cc1a667846fa180
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323423"
---
# <a name="apply-filters-to-a-plan"></a><span data-ttu-id="21efc-103">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="21efc-103">Apply filters to a plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="21efc-104">Po użyciu funkcji optymalizacji planowania można zastosować filtr do planu.</span><span class="sxs-lookup"><span data-stu-id="21efc-104">When the Planning Optimization functionality is used, you can apply a filter to a plan.</span></span> <span data-ttu-id="21efc-105">**Filtr planu** będzie zawsze stosowany podczas procesu planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="21efc-105">The **Plan filter** will always be applied during a master planning run.</span></span> <span data-ttu-id="21efc-106">**Filtr planu** jest przydatny, gdy chce się ograniczyć plan do konkretnej grupy towarów i upewnić się, że nie są uwzględniane żadne inne towary jako część wynikowego planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="21efc-106">A **Plan filter** is useful when you want to limit a plan to a specific group of items and make sure that no other items are included as part of the resulting master planning.</span></span>

<span data-ttu-id="21efc-107">Jeśli zastosowano **filtr planu**, a filtr środowiska uruchomieniowego jest również stosowany podczas procesu planowania głównego, w procesie planowania będzie uwzględniany tylko przecięcie dwóch filtrów.</span><span class="sxs-lookup"><span data-stu-id="21efc-107">If a **Plan filter** is applied, and a runtime filter is also applied during the master planning run, only the intersection of the two filters is included in the planning run.</span></span>

<span data-ttu-id="21efc-108">**Filtr planu** można uzyskać dostęp z **planów głównych** podczas planowania optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="21efc-108">The **Plan filter** can be accessed from **Master plans** when Planning Optimization is used.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="21efc-109">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="21efc-109">Example scenario</span></span>

<span data-ttu-id="21efc-110">Filtr planu jest skonfigurowany z pozycjami A, B i C. Następnie uruchamiane są przebiegi planowania głównego dla tego samego planu, ale stosowane są różne filtry czasu wykonywania:</span><span class="sxs-lookup"><span data-stu-id="21efc-110">A plan filter is set up that includes items A, B, and C. Master planning runs are then run for the same plan, but different runtime filters are applied:</span></span>

- <span data-ttu-id="21efc-111">**Filtr środowiska uruchomieniowego zawierający element D**. Nie są planowane żadne elementy, ponieważ nie istnieje przecięcie między filtrem planu a filtrem środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="21efc-111">**Runtime filter that includes item D:** No items are planned, because there is no intersection between the plan filter and the runtime filter.</span></span>
- <span data-ttu-id="21efc-112">**Filtr środowiska uruchomieniowego zawierający element A i D:** w przebiegu planowania uwzględniono tylko element a, ponieważ pozycja D nie jest częścią filtru planu.</span><span class="sxs-lookup"><span data-stu-id="21efc-112">**Runtime filter that includes item A and D:** Only item A is included in the planning run, because item D isn't part of the plan filter.</span></span>
- <span data-ttu-id="21efc-113">**Filtr środowiska uruchomieniowego zawierający element B:** w przebiegu planowania i poprzednim rezultacie planowania uwzględniono tylko element A.</span><span class="sxs-lookup"><span data-stu-id="21efc-113">**Runtime filter that includes item B:** Only item B is included in the planning run, and the previous planning output for item A is kept.</span></span>
- <span data-ttu-id="21efc-114">**Filtr środowiska uruchomieniowego zawierający wszystkie elementy (pusty filtr):** pozycje A, B i C są uwzględnione w procesie planowania i poprzednie dane wyjściowe planowania dla pozycji a i B są zastępowane.</span><span class="sxs-lookup"><span data-stu-id="21efc-114">**Runtime filter that includes all items (blank filter):** Items A, B, and C are included in the planning run, and the previous planning output for items A and B is overwritten.</span></span>

> [!NOTE]
> <span data-ttu-id="21efc-115">Należy unikać ustawiania filtru planu w planie wybranym jako **bieżący dynamiczny plan główny** na stronie **parametrów planowania głównego**.</span><span class="sxs-lookup"><span data-stu-id="21efc-115">You should avoid setting a plan filter on the plan that is selected as **Current dynamic master plan** on the **Master planning parameters** page.</span></span> <span data-ttu-id="21efc-116">W przeciwnym razie funkcje dynamicznego planu głównego będą ograniczone do elementów filtrowanych.</span><span class="sxs-lookup"><span data-stu-id="21efc-116">Otherwise, the dynamic master plan functionality will be limited to the filtered items.</span></span> <span data-ttu-id="21efc-117">Jeśli na przykład zapotrzebowanie netto jest aktualizowane dla towaru, który nie jest częścią filtru planu, wynik nie zostanie wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="21efc-117">For example, if the net requirements are updated for an item that isn't part of the plan filter, no result will be generated.</span></span>

## <a name="related-resources"></a><span data-ttu-id="21efc-118">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="21efc-118">Related resources</span></span>

[<span data-ttu-id="21efc-119">Omówienie planowania optymalizacji</span><span class="sxs-lookup"><span data-stu-id="21efc-119">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="21efc-120">Rozpocznij pracę z optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="21efc-120">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="21efc-121">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="21efc-121">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="21efc-122">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="21efc-122">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="21efc-123">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="21efc-123">Cancel a planning job</span></span>](cancel-planning-job.md)
