---
title: Rozpocznij pracę z optymalizacją planowania
description: W tym temacie wyjaśniono, jak zacząć używanie funkcji optymalizacji planowania.
author: ChristianRytt
manager: AnnBe
ms.date: 10/29/2019
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
ms.openlocfilehash: 37c2acb2397b2a0ad69272c0645bd200a8d7910d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774027"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="0d257-103">Rozpocznij pracę z optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="0d257-103">Get started with Planning Optimization</span></span>

<span data-ttu-id="0d257-104">Funkcja optymalizacji planowania nie obsługuje obecnie wszystkich funkcji dostępnych w aparacie planowania wbudowanym w rozwiązanie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d257-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="0d257-105">Dlatego ważne jest, aby ocenić, czy aktualnie dostępna w optymalizacji planowania funkcja ma spełniać wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0d257-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="0d257-106">Domyślnie funkcja optymalizacji planowania nie jest domyślnie włączona w usłudze Dynamics Lifecycle Services (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="0d257-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="0d257-107">Z tego względu użytkownik ma możliwość wykonania oceny przed jej włączeniem.</span><span class="sxs-lookup"><span data-stu-id="0d257-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="0d257-108">Ostatecznie Optymalizacja planowania zastąpi istniejący wbudowany silnik planowania Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d257-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="0d257-109">Przed włączeniem optymalizacji planowania zdecydowanie zaleca się dokonanie oceny wyników analizy pasującej do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="0d257-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="0d257-110">Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="0d257-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="0d257-111">Licencjonowanie</span><span class="sxs-lookup"><span data-stu-id="0d257-111">Licensing</span></span>

<span data-ttu-id="0d257-112">Jeśli planowanie główne można uruchomić za pomocą bieżącej licencji, nie trzeba kupować dodatkowej licencji, aby zacząć korzystać z optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="0d257-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="0d257-113">Instalacja aplikacji dodatkowych</span><span class="sxs-lookup"><span data-stu-id="0d257-113">Install the add-in</span></span>

<span data-ttu-id="0d257-114">Aby skorzystać z optymalizacji planowania, zainstaluj dodatek optymalizacji planowania dla Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d257-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="0d257-115">Można uzyskać dostęp do dodatku z projektu usługi LCS i włączyć funkcję optymalizacji planowania z poziomu interfejsu użytkownika Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d257-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

1. <span data-ttu-id="0d257-116">Zaloguj się do usługi LCS i otwórz żądane środowisko.</span><span class="sxs-lookup"><span data-stu-id="0d257-116">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="0d257-117">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="0d257-117">Go to **Full details**.</span></span>
1. <span data-ttu-id="0d257-118">Wybierz opcję **Zarządzaj** lub przewiń w dół do skróconej karty **dodatków środowiska**.</span><span class="sxs-lookup"><span data-stu-id="0d257-118">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="0d257-119">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="0d257-119">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="0d257-120">Wybierz **Planowanie optymalizacji**.</span><span class="sxs-lookup"><span data-stu-id="0d257-120">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="0d257-121">Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.</span><span class="sxs-lookup"><span data-stu-id="0d257-121">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="0d257-122">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="0d257-122">Select **Install**.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="0d257-123">Integracja optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="0d257-123">Planning Optimization integration</span></span>

<span data-ttu-id="0d257-124">Aby określić, czy dodatek optymalizacji planowania ma być używany w planowaniu głównym, należy przejść do **Planowanie główne** \> **Ustawienia** \> **Integracja optymalizacji planowania** \> **Parametry integracji**.</span><span class="sxs-lookup"><span data-stu-id="0d257-124">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization integration** \> **Integration parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="0d257-125">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="0d257-125">Connection status</span></span>

<span data-ttu-id="0d257-126">Stan połączenia wskazuje bieżący stan połączenia między Supply Chain Management a usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="0d257-126">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="0d257-127">Poniższa tabela przedstawia możliwe wartości.</span><span class="sxs-lookup"><span data-stu-id="0d257-127">The following table shows the possible values.</span></span>

| <span data-ttu-id="0d257-128">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="0d257-128">Connection status</span></span> | <span data-ttu-id="0d257-129">Opis</span><span class="sxs-lookup"><span data-stu-id="0d257-129">Description</span></span> | <span data-ttu-id="0d257-130">Czy można użyć optymalizacji planowania?</span><span class="sxs-lookup"><span data-stu-id="0d257-130">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="0d257-131">Połączono</span><span class="sxs-lookup"><span data-stu-id="0d257-131">Connected</span></span> | <span data-ttu-id="0d257-132">Ustanowiono połączenie między usługą optymalizacji planowania i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d257-132">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="0d257-133">Tak</span><span class="sxs-lookup"><span data-stu-id="0d257-133">Yes</span></span> |
| <span data-ttu-id="0d257-134">Włączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="0d257-134">Enabling connection</span></span> | <span data-ttu-id="0d257-135">Obecnie trwa żądanie włączenia połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="0d257-135">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="0d257-136">Nie</span><span class="sxs-lookup"><span data-stu-id="0d257-136">No</span></span> |
| <span data-ttu-id="0d257-137">Rozłączono</span><span class="sxs-lookup"><span data-stu-id="0d257-137">Disconnected</span></span> | <span data-ttu-id="0d257-138">Nie istnieje połączenie z usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="0d257-138">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="0d257-139">Połączenie można włączyć z usługi LCS, jak opisano wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="0d257-139">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="0d257-140">Nie</span><span class="sxs-lookup"><span data-stu-id="0d257-140">No</span></span> |
| <span data-ttu-id="0d257-141">Wyłączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="0d257-141">Disabling connection</span></span> | <span data-ttu-id="0d257-142">Obecnie trwa żądanie wyłączania połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="0d257-142">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="0d257-143">Nie</span><span class="sxs-lookup"><span data-stu-id="0d257-143">No</span></span> |
| <span data-ttu-id="0d257-144">Pobieranie informacji o stanie</span><span class="sxs-lookup"><span data-stu-id="0d257-144">Getting status</span></span> | <span data-ttu-id="0d257-145">System oczekuje na informacje o stanie z usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="0d257-145">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="0d257-146">Nie</span><span class="sxs-lookup"><span data-stu-id="0d257-146">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="0d257-147">Opcja Zastosuj optymalizację planowania</span><span class="sxs-lookup"><span data-stu-id="0d257-147">The Use Planning Optimization option</span></span>

<span data-ttu-id="0d257-148">Ustawienie opcji **Zastosuj optymalizację** planowania określa, który Aparat planowania będzie używany w planowaniu głównym:</span><span class="sxs-lookup"><span data-stu-id="0d257-148">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="0d257-149">**Tak** — Optymalizacja planowania jest używana do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="0d257-149">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="0d257-150">**Nie** – wbudowany silnik planowania Supply Chain Management jest używany do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="0d257-150">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="0d257-151">Jeśli istniejące zadania wsadowe planowania utworzone dla wbudowanego silnika planowania Supply Chain Management dostaw są wyzwalane, a opcja **Użyj optymalizacji planowania** jest ustawiona na wartość **tak**, zadania te nie powiodą się.</span><span class="sxs-lookup"><span data-stu-id="0d257-151">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="0d257-152">Integracja z ustawieniami</span><span class="sxs-lookup"><span data-stu-id="0d257-152">Integration with the setup</span></span>

<span data-ttu-id="0d257-153">Jeśli opcja Podgląd optymalizacji planowania jest włączona, planowanie główne jest wykonywane przy użyciu dodatku Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="0d257-153">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="0d257-154">W takim przypadku wpływa to na wyniki i funkcje planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="0d257-154">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="0d257-155">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="0d257-155">Related resources</span></span>

[<span data-ttu-id="0d257-156">Warunki i postanowienia dla wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="0d257-156">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="0d257-157">Omówienie planowania optymalizacji</span><span class="sxs-lookup"><span data-stu-id="0d257-157">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="0d257-158">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="0d257-158">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="0d257-159">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="0d257-159">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="0d257-160">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="0d257-160">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="0d257-161">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="0d257-161">Cancel a planning job</span></span>](cancel-planning-job.md)
