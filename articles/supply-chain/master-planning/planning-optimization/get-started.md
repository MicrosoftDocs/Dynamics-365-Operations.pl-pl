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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 50633d1e5dd47b61e074d33a9d77a1f9ece0c223
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263381"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="15c34-103">Rozpoczęcie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="15c34-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="15c34-104">Zgodnie ze [wcześniejszą informacją](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), optymalizacja planowania zastąpi istniejący wbudowany aparat planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="15c34-104">As [previously announced](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), Planning Optimization is scheduled to replace the existing built-in master planning engine.</span></span>

<span data-ttu-id="15c34-105">Jeśli obecnie jest używany wbudowany aparat planowania głównego, należy teraz rozpocząć planowanie migracji do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-105">If you currently use the built-in master planning engine, you should start planning your migration to Planning Optimization now.</span></span> <span data-ttu-id="15c34-106">Ważne jest natychmiastowe rozpoczęcie procesu migracji, ponieważ wymuszenie wycofania może mieć wpływ na operacje.</span><span class="sxs-lookup"><span data-stu-id="15c34-106">It is important to start the migration process right away because your operations may be impacted when deprecation is enforced.</span></span> <span data-ttu-id="15c34-107">Aby uniknąć wymuszania wycofania w ostatniej chwili, zdecydowanie zachęcamy do ukończenia migracji przed 1 grudnia 2020.</span><span class="sxs-lookup"><span data-stu-id="15c34-107">To avoid last-minutes issues when deprecation is enforced, we strongly encourage you to complete the migration before December 1, 2020.</span></span> 

<span data-ttu-id="15c34-108">Funkcja optymalizacji planowania nie obsługuje obecnie wszystkich funkcji dostępnych w aparacie planowania wbudowanym w rozwiązanie Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15c34-108">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Supply Chain Management.</span></span> <span data-ttu-id="15c34-109">Dlatego ważne jest, aby ocenić, czy aktualnie dostępna w optymalizacji planowania funkcja ma spełniać wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="15c34-109">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="15c34-110">Funkcja optymalizacji planowania nie jest obecnie włączona domyślnie w usługach Dynamics Lifecycle Services (LCS), więc użytkownik ma możliwość wykonania oceny przed jej włączeniem.</span><span class="sxs-lookup"><span data-stu-id="15c34-110">The Planning Optimization functionality isn't currently turned on by default in Dynamics Lifecycle Services (LCS), so you have the opportunity to do your evaluation before the feature is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="15c34-111">Należy zażądać wyjątku od migracji do optymalizacji planowania, jeśli proces planowania głównego nie obejmuje produkcji (wygenerowane planowane zlecenia produkcyjne utworzone w ramach planowania głównego), a wbudowany aparat planowania głównego jest wymagany od wersji 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="15c34-111">You need to request an exception from migration to Planning Optimization if your master planning process does not include production (master planning generated planned production orders) and you require the built-in master planning engine beyond version 10.0.15.</span></span> <span data-ttu-id="15c34-112">Począwszy od wersji 10.0.16, w środowiskach, w których uruchomiono wbudowane planowanie główne bez generowania planowanych zleceń produkcyjnych, jest wyświetlany błąd.</span><span class="sxs-lookup"><span data-stu-id="15c34-112">Starting in version 10.0.16, an error will be shown in environments when running built-in master planning without generation of planned production orders.</span></span> <span data-ttu-id="15c34-113">Optymalizacja planowania powinna być używana we wszystkich nowych wdrożeniach, które nie generują planowanych zleceń produkcyjnych podczas planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="15c34-113">Planning Optimization should be used for all new deployments that do not generate planned production orders during master planning.</span></span> <span data-ttu-id="15c34-114">Właściciele istniejących środowisk, w których uruchomiono wbudowany aparat planowania głównego bez generowania planowanych zleceń produkcyjnych, otrzymają wiadomości ze szczegółami dotyczącymi procesu wyjątku.</span><span class="sxs-lookup"><span data-stu-id="15c34-114">Owners of existing environments running the built-in master planning engine without generation of Planned production orders, will receive a mail with details about the exception process.</span></span> <span data-ttu-id="15c34-115">Zalecamy współpracę z partnerem w celu oceny i planowania migracji do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-115">We recommend that you work with a partner to evaluate and plan the migration to Planning Optimization.</span></span>

<span data-ttu-id="15c34-116">Przed włączeniem optymalizacji planowania zdecydowanie zaleca się dokonanie oceny wyników analizy pasującej do optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-116">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="15c34-117">Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="15c34-117">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="availability"></a><span data-ttu-id="15c34-118">Dostępność</span><span class="sxs-lookup"><span data-stu-id="15c34-118">Availability</span></span>

<span data-ttu-id="15c34-119">Optymalizacja planowania jest obecnie dostępna w następujących regionach geograficznych platformy Azure: Stany Zjednoczone, Kanada, Europa, Zjednoczone Królestwo, Australia oraz Azja i Pacyfik.</span><span class="sxs-lookup"><span data-stu-id="15c34-119">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, Australia, and Asia Pacific.</span></span> <span data-ttu-id="15c34-120">W przypadku próby zainstalowania dodatku z innego regionu geograficznego usługi LCS wyświetlą komunikat informujący, że ten region geograficzny nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="15c34-120">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="15c34-121">Pamiętaj, że optymalizacja planowania nie obsługuje wdrożeń lokalnych aplikacji Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15c34-121">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

## <a name="licensing"></a><span data-ttu-id="15c34-122">Licencjonowanie</span><span class="sxs-lookup"><span data-stu-id="15c34-122">Licensing</span></span>

<span data-ttu-id="15c34-123">Jeśli planowanie główne można uruchomić za pomocą bieżącej licencji, nie trzeba kupować dodatkowej licencji, aby zacząć korzystać z optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-123">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

## <a name="install-and-enable-planning-optimization"></a><span data-ttu-id="15c34-124">Instalowanie i włączanie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="15c34-124">Install and enable Planning Optimization</span></span>

<span data-ttu-id="15c34-125">Aby korzystać z optymalizacji planowania, musisz się upewnić, że w systemie są spełnione wszystkie wymagania wstępne, a następnie włącz klucz licencji i zainstaluj dodatek Optymalizacja planowania dla aplikacji Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15c34-125">To use Planning Optimization, you must make sure your system has all of the prerequisites in place and then enable its license key and install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="15c34-126">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="15c34-126">Prerequisites</span></span>

<span data-ttu-id="15c34-127">Przed zainstalowaniem dodatku Optymalizacja planowania muszą zostać spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="15c34-127">Before you install the Planning Optimization Add-in, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="15c34-128">Musisz uruchamiać aplikację Supply Chain Management w środowisku wysokiej dostępności z włączonymi usługami LCS w warstwie 2 lub wyższej (nie środowisko OneBox) z aplikacją Dynamics 365 Supply Chain Management w wersji 10.0.7 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="15c34-128">You must be running Supply Chain Management on an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="15c34-129">W przypadku próby zainstalowania dodatku w środowisku OneBox instalacja nie zostanie zakończona i trzeba będzie ją anulować.</span><span class="sxs-lookup"><span data-stu-id="15c34-129">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

- <span data-ttu-id="15c34-130">Należy skonfigurować system do integracji z platformą Power Platform.</span><span class="sxs-lookup"><span data-stu-id="15c34-130">Your system must be set up for Power Platform integration.</span></span> <span data-ttu-id="15c34-131">Aby uzyskać więcej informacji, zobacz [Wymagania wstępne dotyczące konfigurowania dodatków](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#prerequisites-for-setting-up-add-ins) oraz [Konfigurowanie dodatków](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#set-up-add-ins).</span><span class="sxs-lookup"><span data-stu-id="15c34-131">For more information, see [Prerequisites for setting up add-ins](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#prerequisites-for-setting-up-add-ins) and [Set up add-ins](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#set-up-add-ins).</span></span>

### <a name="enable-the-planning-optimization-license"></a><span data-ttu-id="15c34-132">Włączanie licencji optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="15c34-132">Enable the Planning Optimization license</span></span>

<span data-ttu-id="15c34-133">Aby korzystać z optymalizacji planowania, należy włączyć klucz konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="15c34-133">To use Planning Optimization, you must enable its configuration key.</span></span> <span data-ttu-id="15c34-134">W tym celu:</span><span class="sxs-lookup"><span data-stu-id="15c34-134">To do so:</span></span>

1. <span data-ttu-id="15c34-135">Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="15c34-135">Put your system into maintenance mode, as described in [Maintenance mode](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="15c34-136">Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.</span><span class="sxs-lookup"><span data-stu-id="15c34-136">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="15c34-137">Na karcie **Klucze konfiguracji** zaznacz pole wyboru **Optymalizacja planowania**.</span><span class="sxs-lookup"><span data-stu-id="15c34-137">On the **Configuration keys** tab, select the check box for **Planning Optimization**.</span></span>
1. <span data-ttu-id="15c34-138">Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="15c34-138">Turn off maintenance mode, as described in [Maintenance mode](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

### <a name="install-the-planning-optimization-add-in"></a><span data-ttu-id="15c34-139">Instalowanie dodatku Optymalizacja planowania</span><span class="sxs-lookup"><span data-stu-id="15c34-139">Install the Planning Optimization Add-in</span></span>

<span data-ttu-id="15c34-140">Musisz zainstalować dodatek z projektu usługi LCS i włączyć funkcję optymalizacji planowania z poziomu interfejsu użytkownika Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15c34-140">You must install the add-in from your LCS project and then turn on the Planning Optimization functionality from the Supply Chain Management user interface.</span></span>

<span data-ttu-id="15c34-141">Aby zainstalować dodatek Optymalizacja planowania:</span><span class="sxs-lookup"><span data-stu-id="15c34-141">To install the Planning Optimization Add-in:</span></span>

1. <span data-ttu-id="15c34-142">Zaloguj się do usługi LCS i otwórz żądane środowisko.</span><span class="sxs-lookup"><span data-stu-id="15c34-142">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="15c34-143">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="15c34-143">Go to **Full details**.</span></span>
1. <span data-ttu-id="15c34-144">Przewiń w dół do pozycji skróconej karty **Zarządzaj dodatkami środowiskowymi**.</span><span class="sxs-lookup"><span data-stu-id="15c34-144">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="15c34-145">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="15c34-145">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="15c34-146">Wybierz **Planowanie optymalizacji**.</span><span class="sxs-lookup"><span data-stu-id="15c34-146">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="15c34-147">Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.</span><span class="sxs-lookup"><span data-stu-id="15c34-147">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="15c34-148">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="15c34-148">Select **Install**.</span></span>
1. <span data-ttu-id="15c34-149">Na skróconej karcie **Dodatki środowiska** widać, czy jest instalowana Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-149">On the **Environment add-ins** FastTab, you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="15c34-150">Po kilku minutach **Instalowanie** zmieni się na **Zainstalowane** (konieczne może być odświeżenie strony).</span><span class="sxs-lookup"><span data-stu-id="15c34-150">After a few minutes, **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="15c34-151">Po zainstalowaniu można już aktywować optymalizację planowania w systemie Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15c34-151">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="15c34-152">Głównym celem instalowania dodatku Optymalizacja planowania jest połączenie usługi i środowiska.</span><span class="sxs-lookup"><span data-stu-id="15c34-152">The main purpose of installing the Planning Optimization Add-in is to connect the service and the environment.</span></span> <span data-ttu-id="15c34-153">Dlatego należy zainstalować dodatek oddzielnie dla każdego środowiska, w którym będzie używana Optymalizacja planowania, niezależnie od kodu przenoszonego między tymi środowiskami.</span><span class="sxs-lookup"><span data-stu-id="15c34-153">Therefore, you must install the add-in separately on each environment where you will use Planning Optimization, regardless of any code moved between the environments.</span></span>

## <a name="integrate-planning-optimization-with-your-system"></a><span data-ttu-id="15c34-154">Integrowanie optymalizacji planowania z systemem</span><span class="sxs-lookup"><span data-stu-id="15c34-154">Integrate Planning Optimization with your system</span></span>

<span data-ttu-id="15c34-155">Aby określić, czy dodatek optymalizacji planowania ma być używany w planowaniu głównym, należy przejść do **Planowanie główne** \> **Ustawienia** \> **Integracja optymalizacji planowania**.</span><span class="sxs-lookup"><span data-stu-id="15c34-155">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

### <a name="connection-status"></a><span data-ttu-id="15c34-156">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="15c34-156">Connection status</span></span>

<span data-ttu-id="15c34-157">Stan połączenia wskazuje bieżący stan połączenia między Supply Chain Management a usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-157">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="15c34-158">Poniższa tabela przedstawia możliwe wartości.</span><span class="sxs-lookup"><span data-stu-id="15c34-158">The following table shows the possible values.</span></span>

| <span data-ttu-id="15c34-159">Stan połączenia</span><span class="sxs-lookup"><span data-stu-id="15c34-159">Connection status</span></span> | <span data-ttu-id="15c34-160">Opis</span><span class="sxs-lookup"><span data-stu-id="15c34-160">Description</span></span> | <span data-ttu-id="15c34-161">Czy można użyć optymalizacji planowania?</span><span class="sxs-lookup"><span data-stu-id="15c34-161">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="15c34-162">Połączono</span><span class="sxs-lookup"><span data-stu-id="15c34-162">Connected</span></span> | <span data-ttu-id="15c34-163">Ustanowiono połączenie między usługą optymalizacji planowania i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15c34-163">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="15c34-164">Tak</span><span class="sxs-lookup"><span data-stu-id="15c34-164">Yes</span></span> |
| <span data-ttu-id="15c34-165">Włączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="15c34-165">Enabling connection</span></span> | <span data-ttu-id="15c34-166">Obecnie trwa żądanie włączenia połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-166">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="15c34-167">Nie</span><span class="sxs-lookup"><span data-stu-id="15c34-167">No</span></span> |
| <span data-ttu-id="15c34-168">Rozłączono</span><span class="sxs-lookup"><span data-stu-id="15c34-168">Disconnected</span></span> | <span data-ttu-id="15c34-169">Nie istnieje połączenie z usługą optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-169">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="15c34-170">Połączenie można włączyć z usługi LCS, jak opisano wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="15c34-170">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="15c34-171">Nie</span><span class="sxs-lookup"><span data-stu-id="15c34-171">No</span></span> |
| <span data-ttu-id="15c34-172">Wyłączanie połączenia</span><span class="sxs-lookup"><span data-stu-id="15c34-172">Disabling connection</span></span> | <span data-ttu-id="15c34-173">Obecnie trwa żądanie wyłączania połączenia do usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-173">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="15c34-174">Nie</span><span class="sxs-lookup"><span data-stu-id="15c34-174">No</span></span> |
| <span data-ttu-id="15c34-175">Pobieranie informacji o stanie</span><span class="sxs-lookup"><span data-stu-id="15c34-175">Getting status</span></span> | <span data-ttu-id="15c34-176">System oczekuje na informacje o stanie z usługi optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-176">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="15c34-177">Nie</span><span class="sxs-lookup"><span data-stu-id="15c34-177">No</span></span> |

### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="15c34-178">Opcja Zastosuj optymalizację planowania</span><span class="sxs-lookup"><span data-stu-id="15c34-178">The Use Planning Optimization option</span></span>

<span data-ttu-id="15c34-179">Ustawienie opcji **Zastosuj optymalizację** planowania określa, który Aparat planowania będzie używany w planowaniu głównym:</span><span class="sxs-lookup"><span data-stu-id="15c34-179">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="15c34-180">**Tak** — Optymalizacja planowania jest używana do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="15c34-180">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="15c34-181">**Nie** – wbudowany silnik planowania Supply Chain Management jest używany do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="15c34-181">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="15c34-182">Jeśli istniejące zadania wsadowe planowania utworzone dla wbudowanego silnika planowania Supply Chain Management dostaw są wyzwalane, a opcja **Użyj optymalizacji planowania** jest ustawiona na wartość **tak**, zadania te nie powiodą się.</span><span class="sxs-lookup"><span data-stu-id="15c34-182">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="15c34-183">Integracja z ustawieniami</span><span class="sxs-lookup"><span data-stu-id="15c34-183">Integration with the setup</span></span>

<span data-ttu-id="15c34-184">Jeśli Optymalizacja planowania jest włączona, planowanie główne jest wykonywane przy użyciu dodatku Optymalizacja planowania.</span><span class="sxs-lookup"><span data-stu-id="15c34-184">If the Planning Optimization is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="15c34-185">W takim przypadku wpływa to na wyniki i funkcje planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="15c34-185">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="15c34-186">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="15c34-186">Additional resources</span></span>

[<span data-ttu-id="15c34-187">Warunki i postanowienia dla wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="15c34-187">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="15c34-188">Omówienie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="15c34-188">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="15c34-189">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="15c34-189">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="15c34-190">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="15c34-190">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="15c34-191">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="15c34-191">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="15c34-192">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="15c34-192">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]