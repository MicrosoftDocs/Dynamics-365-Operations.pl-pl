---
title: Rozpocznij pracę z optymalizacją planowania
description: W tym temacie wyjaśniono, jak zacząć używanie funkcji optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 05/06/2020
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
ms.openlocfilehash: ce1bbb18e9a448e84d001a4195421d2b0e4af5be
ms.sourcegitcommit: c0d37fdd70f3dec4605fdee6f981f84a49be9b9e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2020
ms.locfileid: "3339885"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="55e7c-103">Rozpocznij pracę z optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="55e7c-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="55e7c-104">Funkcja optymalizacji planowania nie obsługuje obecnie wszystkich funkcji dostępnych w aparacie planowania wbudowanym w rozwiązanie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="55e7c-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="55e7c-105">Dlatego ważne jest, aby ocenić, czy aktualnie dostępna w optymalizacji planowania funkcja ma spełniać wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="55e7c-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="55e7c-106">Domyślnie funkcja optymalizacji planowania nie jest domyślnie włączona w usłudze Dynamics Lifecycle Services (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="55e7c-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="55e7c-107">Z tego względu użytkownik ma możliwość wykonania oceny przed jej włączeniem.</span><span class="sxs-lookup"><span data-stu-id="55e7c-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="55e7c-108">Ostatecznie Optymalizacja planowania zastąpi istniejący wbudowany silnik planowania Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="55e7c-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="55e7c-109">Przed włączeniem optymalizacji planowania zdecydowanie zaleca się dokonanie oceny wyników analizy pasującej do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="55e7c-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="55e7c-110">Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="55e7c-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="55e7c-111">Dostępność</span><span class="sxs-lookup"><span data-stu-id="55e7c-111">Availability</span></span>
<span data-ttu-id="55e7c-112">Optymalizacja planowania jest obecnie dostępna w następujących regionach geograficznych platformy Azure: Stany Zjednoczone, Kanada, Europa, Wielka Brytania i Australia.</span><span class="sxs-lookup"><span data-stu-id="55e7c-112">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="55e7c-113">W przypadku próby zainstalowania dodatku z innego regionu geograficznego usługi LCS wyświetlą komunikat informujący, że ten region geograficzny nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="55e7c-113">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="55e7c-114">Pamiętaj, że optymalizacja planowania nie obsługuje wdrożeń lokalnych aplikacji Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="55e7c-114">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="55e7c-115">Licencjonowanie</span><span class="sxs-lookup"><span data-stu-id="55e7c-115">Licensing</span></span>

<span data-ttu-id="55e7c-116">Jeśli planowanie główne można uruchomić za pomocą bieżącej licencji, nie trzeba kupować dodatkowej licencji, aby zacząć korzystać z optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="55e7c-116">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="55e7c-117">Instalacja aplikacji dodatkowych</span><span class="sxs-lookup"><span data-stu-id="55e7c-117">Install the add-in</span></span>

<span data-ttu-id="55e7c-118">Aby skorzystać z optymalizacji planowania, zainstaluj dodatek optymalizacji planowania dla Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="55e7c-118">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="55e7c-119">Można uzyskać dostęp do dodatku z projektu usługi LCS i włączyć funkcję optymalizacji planowania z poziomu interfejsu użytkownika Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="55e7c-119">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="55e7c-120">Wymóg optymalizacji planowania to środowisko wysokiej dostępności z włączonymi usługami LCS w warstwie 2 lub wyższej (a nie środowisko OneBox) z aplikacją Dynamics 365 Supply Chain Management w wersji 10.0.7 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="55e7c-120">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="55e7c-121">W przypadku próby zainstalowania dodatku w środowisku OneBox instalacja nie zostanie zakończona i trzeba będzie ją anulować.</span><span class="sxs-lookup"><span data-stu-id="55e7c-121">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="55e7c-122">Zaloguj się do usługi LCS i otwórz żądane środowisko.</span><span class="sxs-lookup"><span data-stu-id="55e7c-122">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="55e7c-123">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="55e7c-123">Go to **Full details**.</span></span>
1. <span data-ttu-id="55e7c-124">Przewiń w dół do pozycji skróconej karty **Zarządzaj dodatkami środowiskowymi**.</span><span class="sxs-lookup"><span data-stu-id="55e7c-124">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="55e7c-125">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="55e7c-125">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="55e7c-126">Wybierz **Planowanie optymalizacji**.</span><span class="sxs-lookup"><span data-stu-id="55e7c-126">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="55e7c-127">Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.</span><span class="sxs-lookup"><span data-stu-id="55e7c-127">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="55e7c-128">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="55e7c-128">Select **Install**.</span></span>
1. <span data-ttu-id="55e7c-129">W skróconej karcie **Dodatki środowiska** widać, czy jest instalowana Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="55e7c-129">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="55e7c-130">Po kilku minutach **Instalowanie** zmieni się na **Zainstalowane** (konieczne może być odświeżenie strony).</span><span class="sxs-lookup"><span data-stu-id="55e7c-130">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="55e7c-131">Po zainstalowaniu można już aktywować optymalizację planowania w systemie Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="55e7c-131">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="55e7c-132">Integracja optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="55e7c-132">Planning Optimization integration</span></span>

<span data-ttu-id="55e7c-133">Aby określić, czy dodatek optymalizacji planowania ma być używany w planowaniu głównym, należy przejść do **Planowanie główne** \> **Ustawienia** \> **Integracja optymalizacji planowania**.</span><span class="sxs-lookup"><span data-stu-id="55e7c-133">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="55e7c-134">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="55e7c-134">Connection status</span></span>

<span data-ttu-id="55e7c-135">Stan połączenia wskazuje bieżący stan połączenia między Supply Chain Management a usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="55e7c-135">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="55e7c-136">Poniższa tabela przedstawia możliwe wartości.</span><span class="sxs-lookup"><span data-stu-id="55e7c-136">The following table shows the possible values.</span></span>

| <span data-ttu-id="55e7c-137">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="55e7c-137">Connection status</span></span> | <span data-ttu-id="55e7c-138">Opis</span><span class="sxs-lookup"><span data-stu-id="55e7c-138">Description</span></span> | <span data-ttu-id="55e7c-139">Czy można użyć optymalizacji planowania?</span><span class="sxs-lookup"><span data-stu-id="55e7c-139">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="55e7c-140">Połączono</span><span class="sxs-lookup"><span data-stu-id="55e7c-140">Connected</span></span> | <span data-ttu-id="55e7c-141">Ustanowiono połączenie między usługą optymalizacji planowania i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="55e7c-141">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="55e7c-142">Tak</span><span class="sxs-lookup"><span data-stu-id="55e7c-142">Yes</span></span> |
| <span data-ttu-id="55e7c-143">Włączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="55e7c-143">Enabling connection</span></span> | <span data-ttu-id="55e7c-144">Obecnie trwa żądanie włączenia połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="55e7c-144">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="55e7c-145">Nie</span><span class="sxs-lookup"><span data-stu-id="55e7c-145">No</span></span> |
| <span data-ttu-id="55e7c-146">Rozłączono</span><span class="sxs-lookup"><span data-stu-id="55e7c-146">Disconnected</span></span> | <span data-ttu-id="55e7c-147">Nie istnieje połączenie z usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="55e7c-147">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="55e7c-148">Połączenie można włączyć z usługi LCS, jak opisano wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="55e7c-148">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="55e7c-149">Nie</span><span class="sxs-lookup"><span data-stu-id="55e7c-149">No</span></span> |
| <span data-ttu-id="55e7c-150">Wyłączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="55e7c-150">Disabling connection</span></span> | <span data-ttu-id="55e7c-151">Obecnie trwa żądanie wyłączania połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="55e7c-151">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="55e7c-152">Nie</span><span class="sxs-lookup"><span data-stu-id="55e7c-152">No</span></span> |
| <span data-ttu-id="55e7c-153">Pobieranie informacji o stanie</span><span class="sxs-lookup"><span data-stu-id="55e7c-153">Getting status</span></span> | <span data-ttu-id="55e7c-154">System oczekuje na informacje o stanie z usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="55e7c-154">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="55e7c-155">Nie</span><span class="sxs-lookup"><span data-stu-id="55e7c-155">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="55e7c-156">Opcja Zastosuj optymalizację planowania</span><span class="sxs-lookup"><span data-stu-id="55e7c-156">The Use Planning Optimization option</span></span>

<span data-ttu-id="55e7c-157">Ustawienie opcji **Zastosuj optymalizację** planowania określa, który Aparat planowania będzie używany w planowaniu głównym:</span><span class="sxs-lookup"><span data-stu-id="55e7c-157">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="55e7c-158">**Tak** — Optymalizacja planowania jest używana do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="55e7c-158">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="55e7c-159">**Nie** – wbudowany silnik planowania Supply Chain Management jest używany do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="55e7c-159">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="55e7c-160">Jeśli istniejące zadania wsadowe planowania utworzone dla wbudowanego silnika planowania Supply Chain Management dostaw są wyzwalane, a opcja **Użyj optymalizacji planowania** jest ustawiona na wartość **tak**, zadania te nie powiodą się.</span><span class="sxs-lookup"><span data-stu-id="55e7c-160">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="55e7c-161">Integracja z ustawieniami</span><span class="sxs-lookup"><span data-stu-id="55e7c-161">Integration with the setup</span></span>

<span data-ttu-id="55e7c-162">Jeśli opcja Podgląd optymalizacji planowania jest włączona, planowanie główne jest wykonywane przy użyciu dodatku Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="55e7c-162">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="55e7c-163">W takim przypadku wpływa to na wyniki i funkcje planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="55e7c-163">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="55e7c-164">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="55e7c-164">Additional resources</span></span>

[<span data-ttu-id="55e7c-165">Warunki i postanowienia dla wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="55e7c-165">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="55e7c-166">Omówienie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="55e7c-166">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="55e7c-167">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="55e7c-167">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="55e7c-168">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="55e7c-168">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="55e7c-169">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="55e7c-169">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="55e7c-170">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="55e7c-170">Cancel a planning job</span></span>](cancel-planning-job.md)
