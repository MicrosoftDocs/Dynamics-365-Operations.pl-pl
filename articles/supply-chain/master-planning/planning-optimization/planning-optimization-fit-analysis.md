---
title: Analiza dopasowywania optymalizacją planowania
description: W tym temacie wyjaśniono, jak sprawdzić bieżącą konfigurację i dane, porównując je z możliwościami funkcji optymalizacji planowania.
author: ChristianRytt
manager: AnnBe
ms.date: 1030/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 26b067f8526df16474c0ab52d0abf816170ff5cb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774030"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a><span data-ttu-id="1e0d9-103">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="1e0d9-103">Planning Optimization fit analysis</span></span>

<span data-ttu-id="1e0d9-104">Aby sprawdzić zgodność bieżących ustawień i danych z funkcją optymalizacji planowania, przejdź do **Planowanie główne** \> **Ustawienia** \> **Analiza dopasowywania optymalizacją planowania**, a następnie wybierz opcję **Uruchom analizę**.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-104">To see how compatible your current setup and data are with the Planning Optimization functionality, go to **Master planning** \> **Setup** \> **Planning Optimization fit analysis**, and then select **Run analysis**.</span></span> <span data-ttu-id="1e0d9-105">Jeśli analiza wykryje niespójności, zostaną one wyświetlone na tej samej stronie.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-105">If the analysis finds any inconsistencies, they are listed on the same page.</span></span> <span data-ttu-id="1e0d9-106">(Analiza może potrwać kilka minut.)</span><span class="sxs-lookup"><span data-stu-id="1e0d9-106">(The analysis can take a few minutes to run.)</span></span>

> [!NOTE]
> <span data-ttu-id="1e0d9-107">W przypadku znalezienia niespójności nadal można skorzystać z optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-107">If inconsistencies are found, you can still use Planning Optimization.</span></span> <span data-ttu-id="1e0d9-108">Wyniki analizy dopasowania pokazują tylko miejsca, w których usługa planowania nie będzie przestrzegać bieżących ustawień.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-108">The results of the fit analysis just show places where the planning service won't honor your current setup.</span></span> <span data-ttu-id="1e0d9-109">Innymi słowy pokazują one miejsca, w których niektóre procesy mogą być ignorowane lub mogą być nieobsługiwane.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-109">In other words, they show places where some processes might be ignored or might not be supported.</span></span>

## <a name="analysis-results-example-1"></a><span data-ttu-id="1e0d9-110">Wyniki analizy: przykład 1</span><span class="sxs-lookup"><span data-stu-id="1e0d9-110">Analysis results: Example 1</span></span>

- <span data-ttu-id="1e0d9-111">**Funkcja:** produkcja</span><span class="sxs-lookup"><span data-stu-id="1e0d9-111">**Feature:** Production</span></span>
- <span data-ttu-id="1e0d9-112">**Problem:** Towary z poziomem BOM większym od zera: 56</span><span class="sxs-lookup"><span data-stu-id="1e0d9-112">**Issue:** Items with BOM level greater than zero: 56</span></span>
- <span data-ttu-id="1e0d9-113">**Wyjaśnienie:** odnaleziona analiza dopasowania odnalazła 56 towarów, które mają konfigurację BOM dla produkcji.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-113">**Explanation:** The fit analysis found 56 items that have a bill of materials (BOM) setup for production.</span></span> <span data-ttu-id="1e0d9-114">Ponieważ bieżąca wersja funkcji optymalizacji planowania nie obsługuje produkcji, optymalizacja planowania spowoduje generowanie planowanych zamówień zakupu zamiast planowanych zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-114">Because the current version of Planning Optimization doesn't support production, Planning Optimization will generate planned purchase orders instead of planned production orders.</span></span> <span data-ttu-id="1e0d9-115">Wyświetlone zostanie także ostrzeżenie, w którym znajdują się odnośne towary.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-115">It will also show a warning that lists the affected items.</span></span>

### <a name="analysis-results-example-2"></a><span data-ttu-id="1e0d9-116">Wyniki analizy: przykład 2</span><span class="sxs-lookup"><span data-stu-id="1e0d9-116">Analysis results: Example 2</span></span>

- <span data-ttu-id="1e0d9-117">**Funkcja:** akcje</span><span class="sxs-lookup"><span data-stu-id="1e0d9-117">**Feature:** Actions</span></span>
- <span data-ttu-id="1e0d9-118">**Problem:** Grupy zapotrzebowania z włączoną opcją obliczania akcji: 6</span><span class="sxs-lookup"><span data-stu-id="1e0d9-118">**Issue:** Coverage groups with actions calculation enabled: 6</span></span>
- <span data-ttu-id="1e0d9-119">**Wyjaśnienie:** znaleziono analizę dopasowania z sześcioma grupami zapotrzebowania, w których jest włączone Obliczanie akcji.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-119">**Explanation:** The fit analysis found six coverage groups where action calculation is turned on.</span></span> <span data-ttu-id="1e0d9-120">Ponieważ bieżąca wersja funkcji optymalizacji planowania nie obsługuje akcji, podczas planowania głównego nie zostaną wygenerowane żadne akcje.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-120">Because the current version of Planning Optimization doesn't support actions, no actions will be generated during master planning.</span></span>

## <a name="related-resources"></a><span data-ttu-id="1e0d9-121">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="1e0d9-121">Related resources</span></span>

[<span data-ttu-id="1e0d9-122">Omówienie planowania optymalizacji</span><span class="sxs-lookup"><span data-stu-id="1e0d9-122">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="1e0d9-123">Rozpocznij pracę z optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="1e0d9-123">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="1e0d9-124">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="1e0d9-124">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="1e0d9-125">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="1e0d9-125">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="1e0d9-126">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="1e0d9-126">Cancel a planning job</span></span>](cancel-planning-job.md)
