---
title: Rozpocznij pracę z optymalizacją planowania
description: W tym temacie wyjaśniono, jak zacząć używanie funkcji optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
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
ms.openlocfilehash: 54ad180b7f4691ead3563b077eadadc3b9b20588
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "4435669"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="c899e-103">Rozpoczęcie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="c899e-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c899e-104">Zgodnie ze [wcześniejszą informacją](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), optymalizacja planowania zastąpi istniejący wbudowany aparat planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="c899e-104">As [previously announced](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), Planning Optimization is scheduled to replace the existing built-in master planning engine.</span></span>

<span data-ttu-id="c899e-105">Jeśli obecnie jest używany wbudowany aparat planowania głównego, należy teraz rozpocząć planowanie migracji do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-105">If you currently use the built-in master planning engine, you should start planning your migration to Planning Optimization now.</span></span> <span data-ttu-id="c899e-106">Ważne jest natychmiastowe rozpoczęcie procesu migracji, ponieważ wymuszenie wycofania może mieć wpływ na operacje.</span><span class="sxs-lookup"><span data-stu-id="c899e-106">It is important to start the migration process right away because your operations may be impacted when deprecation is enforced.</span></span> <span data-ttu-id="c899e-107">Aby uniknąć wymuszania wycofania w ostatniej chwili, zdecydowanie zachęcamy do ukończenia migracji przed 1 grudnia 2020.</span><span class="sxs-lookup"><span data-stu-id="c899e-107">To avoid last-minutes issues when deprecation is enforced, we strongly encourage you to complete the migration before December 1, 2020.</span></span> 

<span data-ttu-id="c899e-108">Funkcja optymalizacji planowania nie obsługuje obecnie wszystkich funkcji dostępnych w aparacie planowania wbudowanym w rozwiązanie Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c899e-108">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Supply Chain Management.</span></span> <span data-ttu-id="c899e-109">Dlatego ważne jest, aby ocenić, czy aktualnie dostępna w optymalizacji planowania funkcja ma spełniać wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c899e-109">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="c899e-110">Funkcja optymalizacji planowania nie jest obecnie włączona domyślnie w usługach Dynamics Lifecycle Services (LCS), więc użytkownik ma możliwość wykonania oceny przed jej włączeniem.</span><span class="sxs-lookup"><span data-stu-id="c899e-110">The Planning Optimization functionality isn't currently turned on by default in Dynamics Lifecycle Services (LCS), so you have the opportunity to do your evaluation before the feature is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="c899e-111">Należy zażądać wyjątku od migracji do optymalizacji planowania, jeśli proces planowania głównego nie obejmuje produkcji (wygenerowane planowane zlecenia produkcyjne utworzone w ramach planowania głównego), a wbudowany aparat planowania głównego jest wymagany od wersji 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="c899e-111">You need to request an exception from migration to Planning Optimization if your master planning process does not include production (master planning generated planned production orders) and you require the built-in master planning engine beyond version 10.0.15.</span></span> <span data-ttu-id="c899e-112">Począwszy od wersji 10.0.16, w środowiskach, w których uruchomiono wbudowane planowanie główne bez generowania planowanych zleceń produkcyjnych, jest wyświetlany błąd.</span><span class="sxs-lookup"><span data-stu-id="c899e-112">Starting in version 10.0.16, an error will be shown in environments when running built-in master planning without generation of planned production orders.</span></span> <span data-ttu-id="c899e-113">Optymalizacja planowania powinna być używana we wszystkich nowych wdrożeniach, które nie generują planowanych zleceń produkcyjnych podczas planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="c899e-113">Planning Optimization should be used for all new deployments that do not generate planned production orders during master planning.</span></span> <span data-ttu-id="c899e-114">Właściciele istniejących środowisk, w których uruchomiono wbudowany aparat planowania głównego bez generowania planowanych zleceń produkcyjnych, otrzymają wiadomości ze szczegółami dotyczącymi procesu wyjątku.</span><span class="sxs-lookup"><span data-stu-id="c899e-114">Owners of existing environments running the built-in master planning engine without generation of Planned production orders, will receive a mail with details about the exception process.</span></span> <span data-ttu-id="c899e-115">Zalecamy współpracę z partnerem w celu oceny i planowania migracji do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-115">We recommend that you work with a partner to evaluate and plan the migration to Planning Optimization.</span></span>

<span data-ttu-id="c899e-116">Przed włączeniem optymalizacji planowania zdecydowanie zaleca się dokonanie oceny wyników analizy pasującej do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-116">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="c899e-117">Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="c899e-117">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="c899e-118">Dostępność</span><span class="sxs-lookup"><span data-stu-id="c899e-118">Availability</span></span>
<span data-ttu-id="c899e-119">Optymalizacja planowania jest obecnie dostępna w następujących regionach geograficznych platformy Azure: Stany Zjednoczone, Kanada, Europa, Wielka Brytania i Australia.</span><span class="sxs-lookup"><span data-stu-id="c899e-119">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="c899e-120">W przypadku próby zainstalowania dodatku z innego regionu geograficznego usługi LCS wyświetlą komunikat informujący, że ten region geograficzny nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="c899e-120">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="c899e-121">Pamiętaj, że optymalizacja planowania nie obsługuje wdrożeń lokalnych aplikacji Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c899e-121">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="c899e-122">Licencjonowanie</span><span class="sxs-lookup"><span data-stu-id="c899e-122">Licensing</span></span>

<span data-ttu-id="c899e-123">Jeśli planowanie główne można uruchomić za pomocą bieżącej licencji, nie trzeba kupować dodatkowej licencji, aby zacząć korzystać z optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-123">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="c899e-124">Instalacja aplikacji dodatkowych</span><span class="sxs-lookup"><span data-stu-id="c899e-124">Install the add-in</span></span>

<span data-ttu-id="c899e-125">Aby skorzystać z optymalizacji planowania, zainstaluj dodatek optymalizacji planowania dla Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c899e-125">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c899e-126">Można uzyskać dostęp do dodatku z projektu usługi LCS i włączyć funkcję optymalizacji planowania z poziomu interfejsu użytkownika Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c899e-126">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="c899e-127">Wymóg optymalizacji planowania to środowisko wysokiej dostępności z włączonymi usługami LCS w warstwie 2 lub wyższej (a nie środowisko OneBox) z aplikacją Dynamics 365 Supply Chain Management w wersji 10.0.7 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="c899e-127">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="c899e-128">W przypadku próby zainstalowania dodatku w środowisku OneBox instalacja nie zostanie zakończona i trzeba będzie ją anulować.</span><span class="sxs-lookup"><span data-stu-id="c899e-128">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="c899e-129">Zaloguj się do usługi LCS i otwórz żądane środowisko.</span><span class="sxs-lookup"><span data-stu-id="c899e-129">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="c899e-130">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="c899e-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="c899e-131">Przewiń w dół do pozycji skróconej karty **Zarządzaj dodatkami środowiskowymi**.</span><span class="sxs-lookup"><span data-stu-id="c899e-131">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="c899e-132">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="c899e-132">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="c899e-133">Wybierz **Planowanie optymalizacji**.</span><span class="sxs-lookup"><span data-stu-id="c899e-133">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="c899e-134">Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.</span><span class="sxs-lookup"><span data-stu-id="c899e-134">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="c899e-135">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="c899e-135">Select **Install**.</span></span>
1. <span data-ttu-id="c899e-136">W skróconej karcie **Dodatki środowiska** widać, czy jest instalowana Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-136">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="c899e-137">Po kilku minutach **Instalowanie** zmieni się na **Zainstalowane** (konieczne może być odświeżenie strony).</span><span class="sxs-lookup"><span data-stu-id="c899e-137">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="c899e-138">Po zainstalowaniu można już aktywować optymalizację planowania w systemie Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c899e-138">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="c899e-139">Głównym celem instalowania dodatku Optymalizacja planowania jest połączenie usługi i środowiska.</span><span class="sxs-lookup"><span data-stu-id="c899e-139">The main purpose of installing the Planning Optimization add-in is to connect the service and the environment.</span></span> <span data-ttu-id="c899e-140">Dlatego należy zainstalować dodatek oddzielnie dla każdego środowiska, w którym będzie używana Optymalizacja planowania, niezależnie od kodu przenoszonego między tymi środowiskami.</span><span class="sxs-lookup"><span data-stu-id="c899e-140">Therefore, you must install the add-in separately on each environment where you will use Planning Optimization, regardless of any code moved between the environments.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="c899e-141">Integracja optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="c899e-141">Planning Optimization integration</span></span>

<span data-ttu-id="c899e-142">Aby określić, czy dodatek optymalizacji planowania ma być używany w planowaniu głównym, należy przejść do **Planowanie główne** \> **Ustawienia** \> **Integracja optymalizacji planowania**.</span><span class="sxs-lookup"><span data-stu-id="c899e-142">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="c899e-143">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="c899e-143">Connection status</span></span>

<span data-ttu-id="c899e-144">Stan połączenia wskazuje bieżący stan połączenia między Supply Chain Management a usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-144">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="c899e-145">Poniższa tabela przedstawia możliwe wartości.</span><span class="sxs-lookup"><span data-stu-id="c899e-145">The following table shows the possible values.</span></span>

| <span data-ttu-id="c899e-146">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="c899e-146">Connection status</span></span> | <span data-ttu-id="c899e-147">Opis</span><span class="sxs-lookup"><span data-stu-id="c899e-147">Description</span></span> | <span data-ttu-id="c899e-148">Czy można użyć optymalizacji planowania?</span><span class="sxs-lookup"><span data-stu-id="c899e-148">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="c899e-149">Połączono</span><span class="sxs-lookup"><span data-stu-id="c899e-149">Connected</span></span> | <span data-ttu-id="c899e-150">Ustanowiono połączenie między usługą optymalizacji planowania i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c899e-150">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="c899e-151">Tak</span><span class="sxs-lookup"><span data-stu-id="c899e-151">Yes</span></span> |
| <span data-ttu-id="c899e-152">Włączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="c899e-152">Enabling connection</span></span> | <span data-ttu-id="c899e-153">Obecnie trwa żądanie włączenia połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-153">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="c899e-154">Nie</span><span class="sxs-lookup"><span data-stu-id="c899e-154">No</span></span> |
| <span data-ttu-id="c899e-155">Rozłączono</span><span class="sxs-lookup"><span data-stu-id="c899e-155">Disconnected</span></span> | <span data-ttu-id="c899e-156">Nie istnieje połączenie z usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-156">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="c899e-157">Połączenie można włączyć z usługi LCS, jak opisano wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="c899e-157">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="c899e-158">Nie</span><span class="sxs-lookup"><span data-stu-id="c899e-158">No</span></span> |
| <span data-ttu-id="c899e-159">Wyłączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="c899e-159">Disabling connection</span></span> | <span data-ttu-id="c899e-160">Obecnie trwa żądanie wyłączania połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-160">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="c899e-161">Nie</span><span class="sxs-lookup"><span data-stu-id="c899e-161">No</span></span> |
| <span data-ttu-id="c899e-162">Pobieranie informacji o stanie</span><span class="sxs-lookup"><span data-stu-id="c899e-162">Getting status</span></span> | <span data-ttu-id="c899e-163">System oczekuje na informacje o stanie z usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-163">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="c899e-164">Nie</span><span class="sxs-lookup"><span data-stu-id="c899e-164">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="c899e-165">Opcja Zastosuj optymalizację planowania</span><span class="sxs-lookup"><span data-stu-id="c899e-165">The Use Planning Optimization option</span></span>

<span data-ttu-id="c899e-166">Ustawienie opcji **Zastosuj optymalizację** planowania określa, który Aparat planowania będzie używany w planowaniu głównym:</span><span class="sxs-lookup"><span data-stu-id="c899e-166">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="c899e-167">**Tak** — Optymalizacja planowania jest używana do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="c899e-167">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="c899e-168">**Nie** – wbudowany silnik planowania Supply Chain Management jest używany do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="c899e-168">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="c899e-169">Jeśli istniejące zadania wsadowe planowania utworzone dla wbudowanego silnika planowania Supply Chain Management dostaw są wyzwalane, a opcja **Użyj optymalizacji planowania** jest ustawiona na wartość **tak**, zadania te nie powiodą się.</span><span class="sxs-lookup"><span data-stu-id="c899e-169">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="c899e-170">Integracja z ustawieniami</span><span class="sxs-lookup"><span data-stu-id="c899e-170">Integration with the setup</span></span>

<span data-ttu-id="c899e-171">Jeśli Optymalizacja planowania jest włączona, planowanie główne jest wykonywane przy użyciu dodatku Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="c899e-171">If the Planning Optimization is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="c899e-172">W takim przypadku wpływa to na wyniki i funkcje planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="c899e-172">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c899e-173">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c899e-173">Additional resources</span></span>

[<span data-ttu-id="c899e-174">Warunki i postanowienia dla wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="c899e-174">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="c899e-175">Omówienie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="c899e-175">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="c899e-176">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="c899e-176">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="c899e-177">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="c899e-177">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="c899e-178">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="c899e-178">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="c899e-179">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="c899e-179">Cancel a planning job</span></span>](cancel-planning-job.md)
