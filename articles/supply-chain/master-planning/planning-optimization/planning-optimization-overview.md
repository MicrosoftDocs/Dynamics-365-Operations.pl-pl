---
title: Omówienie planowania optymalizacji
description: Ten temat zawiera omówienie funkcji sprzedaży przez biuro obsługi w optymalizacji planowania.
author: ChristianRytt
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 5ecfa8ac4db050ee1e38f3b420d81beba19b9409
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812962"
---
# <a name="planning-optimization-overview"></a><span data-ttu-id="71bb1-103">Omówienie planowania optymalizacji</span><span class="sxs-lookup"><span data-stu-id="71bb1-103">Planning Optimization overview</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="71bb1-104">Dodatek do optymalizacji planowania dla rozwiązania Microsoft Dynamics 365 Supply Chain Management umożliwia naliczenie planowania głównego poza Dynamics 365 Supply Chain Management i pokrewną bazą danych SQL.</span><span class="sxs-lookup"><span data-stu-id="71bb1-104">The Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management enables master planning calculation to occur outside Dynamics 365 Supply Chain Management and the related SQL database.</span></span> <span data-ttu-id="71bb1-105">Korzyści związane z funkcjami optymalizacji planowania obejmują lepszą wydajność i minimalny wpływ na bazę danych SQL podczas uruchamiania planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="71bb1-105">The benefits that are associated with the Planning Optimization functionality include improved performance and minimal impact on SQL database during master planning runs.</span></span> <span data-ttu-id="71bb1-106">Szybkie przebiegi planowania można wykonać nawet w godzinach pracy, dzięki czemu terminarze mogą natychmiast reagować na zmiany popytu lub parametrów.</span><span class="sxs-lookup"><span data-stu-id="71bb1-106">Quick planning runs can be done even during office hours, so that planners can immediately react to demand or parameter changes.</span></span>

<span data-ttu-id="71bb1-107">Aby skorzystać z optymalizacji planowania, należy zainstalować dodatek Optymalizacja planowania z projektu w Microsoft Dynamics usługach Lifecycle Services (usługi LCS) i włączyć funkcję optymalizacji planowania w module Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="71bb1-107">To use Planning Optimization, you must install the Planning Optimization Add-in from your project in Microsoft Dynamics Lifecycle Services (LCS) and turn on the Planning Optimization functionality in Supply Chain Management.</span></span> <span data-ttu-id="71bb1-108">Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z optymalizacją planowania](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="71bb1-108">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="71bb1-109">Na poniższej ilustracji przedstawiono zalety uruchamiania optymalizacji planowania w godzinach pracy.</span><span class="sxs-lookup"><span data-stu-id="71bb1-109">The following illustration shows the advantage of running Planning Optimization during office hours.</span></span>

![Zalety uruchomienia optymalizacji planowania w godzinach pracy](media/PlanningOptimization1.png)

## <a name="improved-performance"></a><span data-ttu-id="71bb1-111">Zwiększona wydajność</span><span class="sxs-lookup"><span data-stu-id="71bb1-111">Improved performance</span></span>

<span data-ttu-id="71bb1-112">Optymalizacja planowania może być używana w scenariuszach obejmujących długotrwałe plany główne.</span><span class="sxs-lookup"><span data-stu-id="71bb1-112">Planning Optimization can be used in scenarios that involve long-running master plans.</span></span> <span data-ttu-id="71bb1-113">Jest on opracowany z myślą o bardzo szybkich obliczeniach dotyczących bardzo dużych ilości danych.</span><span class="sxs-lookup"><span data-stu-id="71bb1-113">It's specifically designed for very fast calculations that involve very large volumes of data.</span></span> <span data-ttu-id="71bb1-114">Ponieważ jest on zbudowany jako usługa wielodostępna funkcji Hyper-i ma skalowalność, wiele wystąpień może równocześnie pracować w celu obliczenia planu.</span><span class="sxs-lookup"><span data-stu-id="71bb1-114">Because it's built as a hyper-scalable multitenant service, multiple instances can work together simultaneously to calculate the plan.</span></span> <span data-ttu-id="71bb1-115">Ponadto usługa planowania usuwa ładunek planowania głównego z systemu i pracuje ze strumieniem danych, który minimalizuje obciążenie serwera.</span><span class="sxs-lookup"><span data-stu-id="71bb1-115">Additionally, the planning service removes the load of master planning from your system and works with a data stream that minimizes the server load.</span></span>

<span data-ttu-id="71bb1-116">Optymalizacja planowania może pomóc w osiągnięciu następujących celów:</span><span class="sxs-lookup"><span data-stu-id="71bb1-116">Planning Optimization can help you achieve the following goals:</span></span>

- <span data-ttu-id="71bb1-117">Zwiększanie wydajności planowania za pomocą krótszego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="71bb1-117">Improve planning performance through a shorter runtime.</span></span>
- <span data-ttu-id="71bb1-118">Zmniejszenie wpływu na inne procesy w trakcie procesu planowania głównego</span><span class="sxs-lookup"><span data-stu-id="71bb1-118">Reduce the impact on other processes during the master planning run.</span></span>
- <span data-ttu-id="71bb1-119">Należy wykonać częstsze procedury planowania.</span><span class="sxs-lookup"><span data-stu-id="71bb1-119">Do more frequent planning runs.</span></span> <span data-ttu-id="71bb1-120">(Nie ma ograniczeń do codziennego uruchamiania.)</span><span class="sxs-lookup"><span data-stu-id="71bb1-120">(You aren't limited to daily runs.)</span></span>
- <span data-ttu-id="71bb1-121">Należy mieć pewność, że przyszły rozwój rynku nie spowoduje przeciążenia systemu planowania.</span><span class="sxs-lookup"><span data-stu-id="71bb1-121">Be confident that future business growth won't overload the planning system.</span></span>

## <a name="architecture-and-data-flow"></a><span data-ttu-id="71bb1-122">Architektura i przepływ danych</span><span class="sxs-lookup"><span data-stu-id="71bb1-122">Architecture and data flow</span></span>

<span data-ttu-id="71bb1-123">Jeśli dodatek Optymalizacja planowania jest zainstalowany z usługi LCS, ustanawiane jest bezpieczne połączenie z usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="71bb1-123">When the Planning Optimization Add-in is installed from LCS, a secure connection to the Planning Optimization service is established.</span></span> <span data-ttu-id="71bb1-124">Usługa znajduje się w tym samym kraju lub regionie centrum danych, co wystąpienie Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="71bb1-124">The service is located in the same data center country or region as the related Supply Chain Management instance.</span></span> <span data-ttu-id="71bb1-125">Po skonfigurowaniu optymalizacji planowania, po uruchomieniu modułu planowanie główne, dane główne i dane transakcyjne są wysyłane z modułu Supply Chain Management do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="71bb1-125">After Planning Optimization is set up, when master planning is run, master data and transactional data are sent from Supply Chain Management to the Planning Optimization service.</span></span>

<span data-ttu-id="71bb1-126">Jeśli dodatek Optymalizacja planowania nie zostanie odinstalowany, wszystkie powiązane dane w usłudze optymalizacji planowania są usuwane.</span><span class="sxs-lookup"><span data-stu-id="71bb1-126">If the Planning Optimization Add-in is uninstalled, all related data in the Planning Optimization service is removed.</span></span>

### <a name="high-level-data-flow-for-regeneration-runs"></a><span data-ttu-id="71bb1-127">Przepływ danych wysokiego poziomu dla przebiegów regeneracji</span><span class="sxs-lookup"><span data-stu-id="71bb1-127">High-level data flow for regeneration runs</span></span>

1. <span data-ttu-id="71bb1-128">Klient Supply Chain Management wysyła sygnał zażądania uruchomienia planowania z optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="71bb1-128">The Supply Chain Management client sends a signal to request a planning run from Planning Optimization.</span></span>
2. <span data-ttu-id="71bb1-129">Optymalizacja planowania żąda wymaganych danych za pośrednictwem zintegrowanego łącznika.</span><span class="sxs-lookup"><span data-stu-id="71bb1-129">Planning Optimization requests the required data via the integrated connector.</span></span>
3. <span data-ttu-id="71bb1-130">Baza danych SQL wysyła żądane informacje o konfiguracji, wzorcu i danych transakcyjnych w celu planowania optymalizacji za pośrednictwem łącznika.</span><span class="sxs-lookup"><span data-stu-id="71bb1-130">The SQL database sends the requested information about setup, master, and transactional data to Planning Optimization via the connector.</span></span> <span data-ttu-id="71bb1-131">Łącznik przetwarza informacje pomiędzy Supply Chain Management i usługa optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="71bb1-131">The connector translates information between Supply Chain Management and the Planning Optimization service.</span></span>
4. <span data-ttu-id="71bb1-132">Usługa optymalizacji planowania zawiera dane związane z planowaniem w pamięci i wykonuje wymagane obliczenia.</span><span class="sxs-lookup"><span data-stu-id="71bb1-132">The Planning Optimization service holds planning-related data in memory and does the required calculations.</span></span>
5. <span data-ttu-id="71bb1-133">Wyniki planowania są wysyłane do bazy danych Supply Chain Management za pośrednictwem łącznika.</span><span class="sxs-lookup"><span data-stu-id="71bb1-133">The planning result is sent to the Supply Chain Management database via the connector.</span></span> <span data-ttu-id="71bb1-134">Wyniki zawierają informacje, takie jak planowane zamówienia i informacje dotyczące oznaczania transakcji.</span><span class="sxs-lookup"><span data-stu-id="71bb1-134">The results include information such as planned orders and pegging information.</span></span> <span data-ttu-id="71bb1-135">Optymalizacja planowania wysyła sygnał do modułu Supply Chain Management w celu wskazania, że przebieg planowania został zakończony.</span><span class="sxs-lookup"><span data-stu-id="71bb1-135">Planning Optimization sends a signal to Supply Chain Management to indicate that the planning run has been completed.</span></span> <span data-ttu-id="71bb1-136">Wysyła również odpowiednie komunikaty i ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="71bb1-136">It also sends any relevant messages and warnings.</span></span>

<span data-ttu-id="71bb1-137">Ilustracja poniżej przedstawia przepływ danych.</span><span class="sxs-lookup"><span data-stu-id="71bb1-137">The following illustration shows the data flow.</span></span>

![Przepływ danych dla przebiegów regeneracji](media/PlanningOptimization2.png)

## <a name="related-resources"></a><span data-ttu-id="71bb1-139">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="71bb1-139">Related resources</span></span>

[<span data-ttu-id="71bb1-140">Rozpocznij pracę z optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="71bb1-140">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="71bb1-141">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="71bb1-141">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="71bb1-142">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="71bb1-142">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="71bb1-143">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="71bb1-143">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="71bb1-144">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="71bb1-144">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]