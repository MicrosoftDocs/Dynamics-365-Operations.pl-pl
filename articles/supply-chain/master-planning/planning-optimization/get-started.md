---
title: Rozpocznij pracę z optymalizacją planowania
description: W tym temacie wyjaśniono, jak zacząć używanie funkcji optymalizacji planowania.
author: ChristianRytt
manager: AnnBe
ms.date: 01/17/2020
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
ms.openlocfilehash: 3e0371c6addc0412dc2fc105891b012941e92a06
ms.sourcegitcommit: e5a3c85a322a9216b8f176536d664fef40ae0bec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2020
ms.locfileid: "2971471"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="e56c1-103">Rozpocznij pracę z optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="e56c1-103">Get started with Planning Optimization</span></span>

<span data-ttu-id="e56c1-104">Funkcja optymalizacji planowania nie obsługuje obecnie wszystkich funkcji dostępnych w aparacie planowania wbudowanym w rozwiązanie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e56c1-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="e56c1-105">Dlatego ważne jest, aby ocenić, czy aktualnie dostępna w optymalizacji planowania funkcja ma spełniać wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e56c1-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="e56c1-106">Domyślnie funkcja optymalizacji planowania nie jest domyślnie włączona w usłudze Dynamics Lifecycle Services (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="e56c1-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="e56c1-107">Z tego względu użytkownik ma możliwość wykonania oceny przed jej włączeniem.</span><span class="sxs-lookup"><span data-stu-id="e56c1-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="e56c1-108">Ostatecznie Optymalizacja planowania zastąpi istniejący wbudowany silnik planowania Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e56c1-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="e56c1-109">Przed włączeniem optymalizacji planowania zdecydowanie zaleca się dokonanie oceny wyników analizy pasującej do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="e56c1-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="e56c1-110">Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="e56c1-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="e56c1-111">Licencjonowanie</span><span class="sxs-lookup"><span data-stu-id="e56c1-111">Licensing</span></span>

<span data-ttu-id="e56c1-112">Jeśli planowanie główne można uruchomić za pomocą bieżącej licencji, nie trzeba kupować dodatkowej licencji, aby zacząć korzystać z optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="e56c1-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="e56c1-113">Instalacja aplikacji dodatkowych</span><span class="sxs-lookup"><span data-stu-id="e56c1-113">Install the add-in</span></span>

<span data-ttu-id="e56c1-114">Aby skorzystać z optymalizacji planowania, zainstaluj dodatek optymalizacji planowania dla Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e56c1-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="e56c1-115">Można uzyskać dostęp do dodatku z projektu usługi LCS i włączyć funkcję optymalizacji planowania z poziomu interfejsu użytkownika Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e56c1-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

1. <span data-ttu-id="e56c1-116">Zaloguj się do usługi LCS i otwórz żądane środowisko.</span><span class="sxs-lookup"><span data-stu-id="e56c1-116">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="e56c1-117">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="e56c1-117">Go to **Full details**.</span></span>
1. <span data-ttu-id="e56c1-118">Przewiń w dół do pozycji skróconej karty **Zarządzaj dodatkami środowiskowymi**.</span><span class="sxs-lookup"><span data-stu-id="e56c1-118">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="e56c1-119">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="e56c1-119">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="e56c1-120">Wybierz **Planowanie optymalizacji**.</span><span class="sxs-lookup"><span data-stu-id="e56c1-120">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="e56c1-121">Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.</span><span class="sxs-lookup"><span data-stu-id="e56c1-121">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="e56c1-122">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="e56c1-122">Select **Install**.</span></span>
1. <span data-ttu-id="e56c1-123">W skróconej karcie **Dodatki środowiska** widać, czy jest instalowana Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="e56c1-123">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="e56c1-124">Po kilku minutach **Instalowanie** zmieni się na **Zainstalowane** (konieczne może być odświeżenie strony).</span><span class="sxs-lookup"><span data-stu-id="e56c1-124">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="e56c1-125">Po zainstalowaniu można już aktywować optymalizację planowania w systemie Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e56c1-125">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="e56c1-126">Integracja optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="e56c1-126">Planning Optimization integration</span></span>

<span data-ttu-id="e56c1-127">Aby określić, czy dodatek optymalizacji planowania ma być używany w planowaniu głównym, należy przejść do **Planowanie główne** \> **Ustawienia** \> **Integracja optymalizacji planowania**.</span><span class="sxs-lookup"><span data-stu-id="e56c1-127">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="e56c1-128">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="e56c1-128">Connection status</span></span>

<span data-ttu-id="e56c1-129">Stan połączenia wskazuje bieżący stan połączenia między Supply Chain Management a usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="e56c1-129">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="e56c1-130">Poniższa tabela przedstawia możliwe wartości.</span><span class="sxs-lookup"><span data-stu-id="e56c1-130">The following table shows the possible values.</span></span>

| <span data-ttu-id="e56c1-131">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="e56c1-131">Connection status</span></span> | <span data-ttu-id="e56c1-132">Opis</span><span class="sxs-lookup"><span data-stu-id="e56c1-132">Description</span></span> | <span data-ttu-id="e56c1-133">Czy można użyć optymalizacji planowania?</span><span class="sxs-lookup"><span data-stu-id="e56c1-133">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="e56c1-134">Połączono</span><span class="sxs-lookup"><span data-stu-id="e56c1-134">Connected</span></span> | <span data-ttu-id="e56c1-135">Ustanowiono połączenie między usługą optymalizacji planowania i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e56c1-135">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="e56c1-136">Tak</span><span class="sxs-lookup"><span data-stu-id="e56c1-136">Yes</span></span> |
| <span data-ttu-id="e56c1-137">Włączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="e56c1-137">Enabling connection</span></span> | <span data-ttu-id="e56c1-138">Obecnie trwa żądanie włączenia połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="e56c1-138">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="e56c1-139">Nie</span><span class="sxs-lookup"><span data-stu-id="e56c1-139">No</span></span> |
| <span data-ttu-id="e56c1-140">Rozłączono</span><span class="sxs-lookup"><span data-stu-id="e56c1-140">Disconnected</span></span> | <span data-ttu-id="e56c1-141">Nie istnieje połączenie z usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="e56c1-141">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="e56c1-142">Połączenie można włączyć z usługi LCS, jak opisano wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="e56c1-142">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="e56c1-143">Nie</span><span class="sxs-lookup"><span data-stu-id="e56c1-143">No</span></span> |
| <span data-ttu-id="e56c1-144">Wyłączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="e56c1-144">Disabling connection</span></span> | <span data-ttu-id="e56c1-145">Obecnie trwa żądanie wyłączania połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="e56c1-145">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="e56c1-146">Nie</span><span class="sxs-lookup"><span data-stu-id="e56c1-146">No</span></span> |
| <span data-ttu-id="e56c1-147">Pobieranie informacji o stanie</span><span class="sxs-lookup"><span data-stu-id="e56c1-147">Getting status</span></span> | <span data-ttu-id="e56c1-148">System oczekuje na informacje o stanie z usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="e56c1-148">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="e56c1-149">Nie</span><span class="sxs-lookup"><span data-stu-id="e56c1-149">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="e56c1-150">Opcja Zastosuj optymalizację planowania</span><span class="sxs-lookup"><span data-stu-id="e56c1-150">The Use Planning Optimization option</span></span>

<span data-ttu-id="e56c1-151">Ustawienie opcji **Zastosuj optymalizację** planowania określa, który Aparat planowania będzie używany w planowaniu głównym:</span><span class="sxs-lookup"><span data-stu-id="e56c1-151">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="e56c1-152">**Tak** — Optymalizacja planowania jest używana do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="e56c1-152">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="e56c1-153">**Nie** – wbudowany silnik planowania Supply Chain Management jest używany do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="e56c1-153">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="e56c1-154">Jeśli istniejące zadania wsadowe planowania utworzone dla wbudowanego silnika planowania Supply Chain Management dostaw są wyzwalane, a opcja **Użyj optymalizacji planowania** jest ustawiona na wartość **tak**, zadania te nie powiodą się.</span><span class="sxs-lookup"><span data-stu-id="e56c1-154">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="e56c1-155">Integracja z ustawieniami</span><span class="sxs-lookup"><span data-stu-id="e56c1-155">Integration with the setup</span></span>

<span data-ttu-id="e56c1-156">Jeśli opcja Podgląd optymalizacji planowania jest włączona, planowanie główne jest wykonywane przy użyciu dodatku Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="e56c1-156">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="e56c1-157">W takim przypadku wpływa to na wyniki i funkcje planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="e56c1-157">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e56c1-158">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="e56c1-158">Related resources</span></span>

[<span data-ttu-id="e56c1-159">Warunki i postanowienia dla wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="e56c1-159">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="e56c1-160">Omówienie planowania optymalizacji</span><span class="sxs-lookup"><span data-stu-id="e56c1-160">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="e56c1-161">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="e56c1-161">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="e56c1-162">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="e56c1-162">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="e56c1-163">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="e56c1-163">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="e56c1-164">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="e56c1-164">Cancel a planning job</span></span>](cancel-planning-job.md)
