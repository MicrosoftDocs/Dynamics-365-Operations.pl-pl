---
title: Rozpocznij pracę z optymalizacją planowania
description: W tym temacie wyjaśniono, jak zacząć używanie funkcji optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 02/10/2020
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
ms.openlocfilehash: 4f9124e824a0b6d5035b2567cb19c2c494390d55
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213522"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="38644-103">Rozpocznij pracę z optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="38644-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="38644-104">Funkcja optymalizacji planowania nie obsługuje obecnie wszystkich funkcji dostępnych w aparacie planowania wbudowanym w rozwiązanie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="38644-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="38644-105">Dlatego ważne jest, aby ocenić, czy aktualnie dostępna w optymalizacji planowania funkcja ma spełniać wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="38644-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="38644-106">Domyślnie funkcja optymalizacji planowania nie jest domyślnie włączona w usłudze Dynamics Lifecycle Services (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="38644-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="38644-107">Z tego względu użytkownik ma możliwość wykonania oceny przed jej włączeniem.</span><span class="sxs-lookup"><span data-stu-id="38644-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="38644-108">Ostatecznie Optymalizacja planowania zastąpi istniejący wbudowany silnik planowania Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="38644-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="38644-109">Przed włączeniem optymalizacji planowania zdecydowanie zaleca się dokonanie oceny wyników analizy pasującej do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="38644-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="38644-110">Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="38644-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="38644-111">Licencjonowanie</span><span class="sxs-lookup"><span data-stu-id="38644-111">Licensing</span></span>

<span data-ttu-id="38644-112">Jeśli planowanie główne można uruchomić za pomocą bieżącej licencji, nie trzeba kupować dodatkowej licencji, aby zacząć korzystać z optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="38644-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="38644-113">Instalacja aplikacji dodatkowych</span><span class="sxs-lookup"><span data-stu-id="38644-113">Install the add-in</span></span>

<span data-ttu-id="38644-114">Aby skorzystać z optymalizacji planowania, zainstaluj dodatek optymalizacji planowania dla Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="38644-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="38644-115">Można uzyskać dostęp do dodatku z projektu usługi LCS i włączyć funkcję optymalizacji planowania z poziomu interfejsu użytkownika Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="38644-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="38644-116">Wymóg na optymalizację planowania to środowisko wysokiej dostępności z włączonymi usługami LCS (a nie środowisko OneBox), z Dynamics 365 Supply Chain Management w wersji 10.0.7 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="38644-116">The requirement for Planning Optimization is an LCS enabled high-availability environment (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span>

1. <span data-ttu-id="38644-117">Zaloguj się do usługi LCS i otwórz żądane środowisko.</span><span class="sxs-lookup"><span data-stu-id="38644-117">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="38644-118">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="38644-118">Go to **Full details**.</span></span>
1. <span data-ttu-id="38644-119">Przewiń w dół do pozycji skróconej karty **Zarządzaj dodatkami środowiskowymi**.</span><span class="sxs-lookup"><span data-stu-id="38644-119">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="38644-120">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="38644-120">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="38644-121">Wybierz **Planowanie optymalizacji**.</span><span class="sxs-lookup"><span data-stu-id="38644-121">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="38644-122">Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.</span><span class="sxs-lookup"><span data-stu-id="38644-122">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="38644-123">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="38644-123">Select **Install**.</span></span>
1. <span data-ttu-id="38644-124">W skróconej karcie **Dodatki środowiska** widać, czy jest instalowana Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="38644-124">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="38644-125">Po kilku minutach **Instalowanie** zmieni się na **Zainstalowane** (konieczne może być odświeżenie strony).</span><span class="sxs-lookup"><span data-stu-id="38644-125">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="38644-126">Po zainstalowaniu można już aktywować optymalizację planowania w systemie Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="38644-126">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="38644-127">Integracja optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="38644-127">Planning Optimization integration</span></span>

<span data-ttu-id="38644-128">Aby określić, czy dodatek optymalizacji planowania ma być używany w planowaniu głównym, należy przejść do **Planowanie główne** \> **Ustawienia** \> **Integracja optymalizacji planowania**.</span><span class="sxs-lookup"><span data-stu-id="38644-128">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="38644-129">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="38644-129">Connection status</span></span>

<span data-ttu-id="38644-130">Stan połączenia wskazuje bieżący stan połączenia między Supply Chain Management a usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="38644-130">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="38644-131">Poniższa tabela przedstawia możliwe wartości.</span><span class="sxs-lookup"><span data-stu-id="38644-131">The following table shows the possible values.</span></span>

| <span data-ttu-id="38644-132">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="38644-132">Connection status</span></span> | <span data-ttu-id="38644-133">Opis</span><span class="sxs-lookup"><span data-stu-id="38644-133">Description</span></span> | <span data-ttu-id="38644-134">Czy można użyć optymalizacji planowania?</span><span class="sxs-lookup"><span data-stu-id="38644-134">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="38644-135">Połączono</span><span class="sxs-lookup"><span data-stu-id="38644-135">Connected</span></span> | <span data-ttu-id="38644-136">Ustanowiono połączenie między usługą optymalizacji planowania i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="38644-136">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="38644-137">Tak</span><span class="sxs-lookup"><span data-stu-id="38644-137">Yes</span></span> |
| <span data-ttu-id="38644-138">Włączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="38644-138">Enabling connection</span></span> | <span data-ttu-id="38644-139">Obecnie trwa żądanie włączenia połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="38644-139">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="38644-140">Nie</span><span class="sxs-lookup"><span data-stu-id="38644-140">No</span></span> |
| <span data-ttu-id="38644-141">Rozłączono</span><span class="sxs-lookup"><span data-stu-id="38644-141">Disconnected</span></span> | <span data-ttu-id="38644-142">Nie istnieje połączenie z usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="38644-142">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="38644-143">Połączenie można włączyć z usługi LCS, jak opisano wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="38644-143">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="38644-144">Nie</span><span class="sxs-lookup"><span data-stu-id="38644-144">No</span></span> |
| <span data-ttu-id="38644-145">Wyłączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="38644-145">Disabling connection</span></span> | <span data-ttu-id="38644-146">Obecnie trwa żądanie wyłączania połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="38644-146">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="38644-147">Nie</span><span class="sxs-lookup"><span data-stu-id="38644-147">No</span></span> |
| <span data-ttu-id="38644-148">Pobieranie informacji o stanie</span><span class="sxs-lookup"><span data-stu-id="38644-148">Getting status</span></span> | <span data-ttu-id="38644-149">System oczekuje na informacje o stanie z usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="38644-149">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="38644-150">Nie</span><span class="sxs-lookup"><span data-stu-id="38644-150">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="38644-151">Opcja Zastosuj optymalizację planowania</span><span class="sxs-lookup"><span data-stu-id="38644-151">The Use Planning Optimization option</span></span>

<span data-ttu-id="38644-152">Ustawienie opcji **Zastosuj optymalizację** planowania określa, który Aparat planowania będzie używany w planowaniu głównym:</span><span class="sxs-lookup"><span data-stu-id="38644-152">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="38644-153">**Tak** — Optymalizacja planowania jest używana do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="38644-153">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="38644-154">**Nie** – wbudowany silnik planowania Supply Chain Management jest używany do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="38644-154">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="38644-155">Jeśli istniejące zadania wsadowe planowania utworzone dla wbudowanego silnika planowania Supply Chain Management dostaw są wyzwalane, a opcja **Użyj optymalizacji planowania** jest ustawiona na wartość **tak**, zadania te nie powiodą się.</span><span class="sxs-lookup"><span data-stu-id="38644-155">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="38644-156">Integracja z ustawieniami</span><span class="sxs-lookup"><span data-stu-id="38644-156">Integration with the setup</span></span>

<span data-ttu-id="38644-157">Jeśli opcja Podgląd optymalizacji planowania jest włączona, planowanie główne jest wykonywane przy użyciu dodatku Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="38644-157">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="38644-158">W takim przypadku wpływa to na wyniki i funkcje planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="38644-158">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="38644-159">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="38644-159">Related resources</span></span>

[<span data-ttu-id="38644-160">Warunki i postanowienia dla wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="38644-160">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="38644-161">Omówienie planowania optymalizacji</span><span class="sxs-lookup"><span data-stu-id="38644-161">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="38644-162">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="38644-162">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="38644-163">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="38644-163">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="38644-164">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="38644-164">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="38644-165">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="38644-165">Cancel a planning job</span></span>](cancel-planning-job.md)
