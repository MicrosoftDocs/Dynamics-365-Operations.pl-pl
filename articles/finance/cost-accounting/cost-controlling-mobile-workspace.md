---
title: Mobilny obszar roboczy Kontrola kosztów
description: Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego Kontrola kosztów. Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 27381a408df64b8f11323b2f164d242bb2c4b6c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249708"
---
# <a name="cost-controlling-mobile-workspace"></a><span data-ttu-id="0e39e-104">Mobilny obszar roboczy Kontrola kosztów</span><span class="sxs-lookup"><span data-stu-id="0e39e-104">Cost controlling mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e39e-105">Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego **Kontrola kosztów**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-105">This topic provides information about the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="0e39e-106">Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie.</span><span class="sxs-lookup"><span data-stu-id="0e39e-106">This workspace lets cost center managers view information about cost center performance anytime and anywhere.</span></span>

<span data-ttu-id="0e39e-107">Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji mobilnej Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0e39e-107">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="0e39e-108">Przegląd</span><span class="sxs-lookup"><span data-stu-id="0e39e-108">Overview</span></span>
<span data-ttu-id="0e39e-109">Mobilny obszar roboczy **Kontrola kosztów** zapewnia natychmiastowy podgląd wyników działania centrów kosztów poprzez porównanie kosztów rzeczywistych z kosztami budżetowymi.</span><span class="sxs-lookup"><span data-stu-id="0e39e-109">The **Cost controlling** mobile workspace provides an instant view of the current performance of cost centers by comparing actual costs against the budgeted costs.</span></span> <span data-ttu-id="0e39e-110">W widoku można przechodzić do stanów poszczególnych składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="0e39e-110">You can drill down to the status of individual cost elements.</span></span>

<span data-ttu-id="0e39e-111">Na przykład pracownik otrzymuje zaproszenie na międzynarodową konferencję, ale organizacja musi pokryć wszystkie wydatki na podróż.</span><span class="sxs-lookup"><span data-stu-id="0e39e-111">For example, an employee receives an invitation to an international conference, but the organization must cover all the travel expenses.</span></span> <span data-ttu-id="0e39e-112">Pracownik pyta przełożonego, czy może wziąć udział w konferencji.</span><span class="sxs-lookup"><span data-stu-id="0e39e-112">The employee asks his manager whether he can attend the conference.</span></span> <span data-ttu-id="0e39e-113">Przełożony otwiera mobilny obszar roboczy **Kontrola kosztów** na swoim telefonie komórkowym i sprawdza, czy ma budżet na pokrycie kosztów udziału pracownika w konferencji.</span><span class="sxs-lookup"><span data-stu-id="0e39e-113">The manager opens the **Cost controlling** mobile workspace on her mobile device to see whether she has budget for the employee to attend the conference.</span></span>

### <a name="data-security"></a><span data-ttu-id="0e39e-114">Bezpieczeństwo danych</span><span class="sxs-lookup"><span data-stu-id="0e39e-114">Data security</span></span>
<span data-ttu-id="0e39e-115">Dane w komórkowym obszarze roboczym **Kontrola kosztów** są zabezpieczone poświadczeniami użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0e39e-115">The data in the **Cost controlling** mobile workspace is secured through user credentials.</span></span> <span data-ttu-id="0e39e-116">Menedżerowie centrów kosztów mają pozwolenie na wgląd tylko w dane swoich centrów kosztów.</span><span class="sxs-lookup"><span data-stu-id="0e39e-116">Cost center managers are allowed to see data only for their own cost center.</span></span> <span data-ttu-id="0e39e-117">Zabezpieczenia na poziomie dostępu są administrowane w module **Rachunek kosztów**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-117">The access-level security is managed in the **Cost accounting** module.</span></span>

<span data-ttu-id="0e39e-118">Księgowi kosztów definiują konfigurację mobilnego obszaru roboczego **Kontrola kosztów** w module **Rachunek kosztów**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-118">Cost accountants define the configuration of the **Cost controlling** mobile workspace in the **Cost accounting** module.</span></span> <span data-ttu-id="0e39e-119">Po opublikowaniu obszaru roboczego w aplikacji komórkowej jest on dostępny w tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0e39e-119">After the workspace is published to the mobile app, it's available in the app.</span></span> <span data-ttu-id="0e39e-120">Dzięki temu menedżerowie centrów kosztów w organizacji mogą wyświetlać dane w tym samym formacie.</span><span class="sxs-lookup"><span data-stu-id="0e39e-120">Therefore, all cost center managers in the organization can view data in the same format.</span></span>

### <a name="actions-views-and-links"></a><span data-ttu-id="0e39e-121">Akcje, widoki i łącza</span><span class="sxs-lookup"><span data-stu-id="0e39e-121">Actions, views, and links</span></span>
<span data-ttu-id="0e39e-122">Mobilny obszar roboczy **Kontrola kosztów** oferuje następujące czynności, widoki i łącza:</span><span class="sxs-lookup"><span data-stu-id="0e39e-122">The **Cost controlling** mobile workspace provides the following actions, views, and links:</span></span>

-   <span data-ttu-id="0e39e-123">**Akcje:**</span><span class="sxs-lookup"><span data-stu-id="0e39e-123">**Actions:**</span></span>

    -   <span data-ttu-id="0e39e-124">Użyj **Wybierz konfigurację**, aby wybrać układ.</span><span class="sxs-lookup"><span data-stu-id="0e39e-124">Use **Select configuration** to select a layout.</span></span>
    -   <span data-ttu-id="0e39e-125">Użyj **Wybierz obiekt kosztu**, aby wybrać centra kosztów, według których mają zostać wyfiltrowane dane.</span><span class="sxs-lookup"><span data-stu-id="0e39e-125">Use **Select cost object** to select the cost centers to filter data on.</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="0e39e-126">Centra kosztów wyświetlane na liście zależą od dostępu udzielonego w module **Rachunek kosztów**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-126">The cost centers that appear in the list depend on the access that is granted in the **Cost accounting** module.</span></span>

-   <span data-ttu-id="0e39e-127">**Widoki:** Zależnie od wybranych akcji oraz konfiguracji w module **Rachunek kosztów** można przeglądać poniższe informacje na kartach:</span><span class="sxs-lookup"><span data-stu-id="0e39e-127">**Views:** Based on the actions that are selected and the configuration in the **Cost accounting** module, you can view the following information on the cards:</span></span>

    -   <span data-ttu-id="0e39e-128">Rzeczywisty a budżetowy (bieżący okres)</span><span class="sxs-lookup"><span data-stu-id="0e39e-128">Actual vs budget (current period)</span></span>
    -   <span data-ttu-id="0e39e-129">Rzeczywisty a skorygowany budżetowy (bieżący okres)</span><span class="sxs-lookup"><span data-stu-id="0e39e-129">Actual vs revised budget (current period)</span></span>
    -   <span data-ttu-id="0e39e-130">Wartości rzeczywiste a budżet (poprzedni okres)</span><span class="sxs-lookup"><span data-stu-id="0e39e-130">Actual vs budget (previous period)</span></span>
    -   <span data-ttu-id="0e39e-131">Wartości rzeczywiste a skorygowany budżet (poprzedni okres)</span><span class="sxs-lookup"><span data-stu-id="0e39e-131">Actual vs revised budget (previous period)</span></span>
    -   <span data-ttu-id="0e39e-132">Wartości rzeczywiste a budżet (od początku roku)</span><span class="sxs-lookup"><span data-stu-id="0e39e-132">Actual vs budget (year to date)</span></span>
    -   <span data-ttu-id="0e39e-133">Wartości rzeczywiste a skorygowany budżet (od początku roku)</span><span class="sxs-lookup"><span data-stu-id="0e39e-133">Actual vs revised budget (year to date)</span></span>

    <span data-ttu-id="0e39e-134">Na każdej karcie są wyświetlane następujące kwoty: wartości rzeczywiste, budżet, odchylenie i % odchylenia.</span><span class="sxs-lookup"><span data-stu-id="0e39e-134">The following amounts are shown on every card: Actual, Budget, Variance, and Variance %.</span></span>

-   <span data-ttu-id="0e39e-135">**Linki:**</span><span class="sxs-lookup"><span data-stu-id="0e39e-135">**Links:**</span></span>

    -   <span data-ttu-id="0e39e-136">Szczegóły bieżącego okresu</span><span class="sxs-lookup"><span data-stu-id="0e39e-136">Details for current period</span></span>
    -   <span data-ttu-id="0e39e-137">Szczegóły poprzedniego okresu</span><span class="sxs-lookup"><span data-stu-id="0e39e-137">Details for previous period</span></span>
    -   <span data-ttu-id="0e39e-138">Szczegóły okresu od początku roku</span><span class="sxs-lookup"><span data-stu-id="0e39e-138">Details for year to date</span></span>

    <span data-ttu-id="0e39e-139">Po wybraniu łącza jest wyświetlana karta dla każdego składnika kosztów.</span><span class="sxs-lookup"><span data-stu-id="0e39e-139">When you select a link, a card is shown for each cost element.</span></span> <span data-ttu-id="0e39e-140">Na każdej karcie są wyświetlane następujące kwoty: wartości rzeczywiste, budżet, odchylenie budżetu, % odchylenia budżetu, skorygowany budżet, odchylenie skorygowanego budżetu i % odchylenia skorygowanego budżetu.</span><span class="sxs-lookup"><span data-stu-id="0e39e-140">The following amounts are shown on every card: Actual, Budget, Budget variance, Budget variance %, Revised budget, Revised budget variance, and Revised budget variance %.</span></span>
    
    <span data-ttu-id="0e39e-141">[![Karta składnika kosztu ](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span><span class="sxs-lookup"><span data-stu-id="0e39e-141">[![Card for a cost element](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0e39e-142">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="0e39e-142">Prerequisites</span></span>
<span data-ttu-id="0e39e-143">Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.</span><span class="sxs-lookup"><span data-stu-id="0e39e-143">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a><span data-ttu-id="0e39e-144">Warunki wstępne w przypadku korzystania z Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="0e39e-144">Prerequisites if you use Microsoft Dynamics 365 Finance</span></span>
<span data-ttu-id="0e39e-145">Jeśli w organizacji wdrożono rozwiązanie Finance, administrator systemu musi opublikować mobilny obszar roboczy **Kontrola kosztów**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-145">If Finance has been deployed for your organization, the system administrator must publish the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="0e39e-146">Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="0e39e-146">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="0e39e-147">Warunki wstępne, jeśli jest używana jest wersja 1611 z aktualizacją platformy 3. lub nowszą</span><span class="sxs-lookup"><span data-stu-id="0e39e-147">Prerequisites if you use version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="0e39e-148">Jeśli w organizacji wdrożono rozwiązanie Finance w wersji 1611 z aktualizacją platformy 3. lub nowszą, administrator systemu musi wykonać następujące zadania wstępne.</span><span class="sxs-lookup"><span data-stu-id="0e39e-148">If version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="0e39e-149">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="0e39e-149">Prerequisite</span></span></th>
<th><span data-ttu-id="0e39e-150">Rola</span><span class="sxs-lookup"><span data-stu-id="0e39e-150">Role</span></span></th>
<th><span data-ttu-id="0e39e-151">opis</span><span class="sxs-lookup"><span data-stu-id="0e39e-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0e39e-152">Zainstalowanie poprawki KB 4013633.</span><span class="sxs-lookup"><span data-stu-id="0e39e-152">Implement KB 4013633.</span></span></td>
<td><span data-ttu-id="0e39e-153">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="0e39e-153">System administrator</span></span></td>

<td><span data-ttu-id="0e39e-154">KB 4013633 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Kontrola kosztów</strong>.</span><span class="sxs-lookup"><span data-stu-id="0e39e-154">KB 4013633 is an X++ update or metadata hotfix that contains the <strong>Cost controlling</strong> mobile workspace.</span></span> <span data-ttu-id="0e39e-155">W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:</span><span class="sxs-lookup"><span data-stu-id="0e39e-155">To implement KB 4013633, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="0e39e-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="0e39e-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="0e39e-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Zainstaluj poprawkę metadanych</a>.</span><span class="sxs-lookup"><span data-stu-id="0e39e-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="0e39e-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="0e39e-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="0e39e-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Zastosuj wdrażalny pakiet</a></span><span class="sxs-lookup"><span data-stu-id="0e39e-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0e39e-160">Opublikowanie mobilnego obszaru roboczego <strong>Kontrola kosztów</strong>.</span><span class="sxs-lookup"><span data-stu-id="0e39e-160">Publish the <strong>Cost controlling</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="0e39e-161">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="0e39e-161">System administrator</span></span></td>
<td><span data-ttu-id="0e39e-162">Zobacz <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>.</span><span class="sxs-lookup"><span data-stu-id="0e39e-162">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="0e39e-163">Pobieranie i instalowanie aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="0e39e-163">Download and install the mobile app</span></span>
<span data-ttu-id="0e39e-164">Pobieranie i instalowanie aplikacji mobilnej Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="0e39e-164">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="0e39e-165">Telefony Android</span><span class="sxs-lookup"><span data-stu-id="0e39e-165">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="0e39e-166">Telefony iPhone</span><span class="sxs-lookup"><span data-stu-id="0e39e-166">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="0e39e-167">Logowanie do aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="0e39e-167">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="0e39e-168">Uruchom aplikację na urządzeniu komórkowym.</span><span class="sxs-lookup"><span data-stu-id="0e39e-168">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="0e39e-169">Wprowadź adres URL usługi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0e39e-169">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="0e39e-170">Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła.</span><span class="sxs-lookup"><span data-stu-id="0e39e-170">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="0e39e-171">Wprowadź swoje poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="0e39e-171">Enter your credentials.</span></span>
4.  <span data-ttu-id="0e39e-172">Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy.</span><span class="sxs-lookup"><span data-stu-id="0e39e-172">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="0e39e-173">Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="0e39e-173">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="0e39e-174">[![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="0e39e-174">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a><span data-ttu-id="0e39e-175">Wyświetlanie wyników działania centrum kosztów przy użyciu mobilnego obszaru roboczego Kontrola kosztów</span><span class="sxs-lookup"><span data-stu-id="0e39e-175">View the performance of your cost center by using the Cost controlling mobile workspace</span></span>

1.  <span data-ttu-id="0e39e-176">Na urządzeniu przenośnym wybierz obszar roboczy **Kontrola kosztów**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-176">On your mobile device, select the **Cost controlling** workspace.</span></span>
2.  <span data-ttu-id="0e39e-177">Wybierz opcję **Kontrola obiektów kosztów**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-177">Select **Cost object controlling**.</span></span>
3.  <span data-ttu-id="0e39e-178">Wybierz opcję **Akcje**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-178">Select **Actions**.</span></span>
4.  <span data-ttu-id="0e39e-179">Wybierz opcję **Wybierz konfigurację** i wybierz układ kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="0e39e-179">Select **Select configuration** to select a cost controlling layout.</span></span>
5.  <span data-ttu-id="0e39e-180">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-180">Select **Done**.</span></span>
6.  <span data-ttu-id="0e39e-181">Wybierz opcję **Akcje**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-181">Select **Actions**.</span></span>
7.  <span data-ttu-id="0e39e-182">Wybierz opcję **Wybierz obiekt kosztu** i zaznacz centra kosztów, do których przyznano Ci uprawnienie dostępu.</span><span class="sxs-lookup"><span data-stu-id="0e39e-182">Select **Select cost object** to select the cost centers that you've been granted access to.</span></span>
8.  <span data-ttu-id="0e39e-183">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-183">Select **Done**.</span></span>
9.  <span data-ttu-id="0e39e-184">Wyświetl całościowe wyniki działania centrum kosztów.</span><span class="sxs-lookup"><span data-stu-id="0e39e-184">View the overall performance of your cost center.</span></span>
10. <span data-ttu-id="0e39e-185">Kliknij łącze **Szczegóły bieżącego okresu**.</span><span class="sxs-lookup"><span data-stu-id="0e39e-185">Select the **Details for current period** link.</span></span>
11. <span data-ttu-id="0e39e-186">Wyświetl wyniki działania poszczególnych składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="0e39e-186">View the performance of individual cost elements.</span></span>
12. <span data-ttu-id="0e39e-187">Można także wyszukiwać konkretne składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="0e39e-187">You can also search for specific cost elements.</span></span>

