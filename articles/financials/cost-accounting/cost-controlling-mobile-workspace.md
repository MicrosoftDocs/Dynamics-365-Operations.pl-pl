---
title: "Mobilny obszar roboczy Kontrola kosztów"
description: "Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego Kontrola kosztów. Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie."
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: e4c9b62456253d0d1710168d8aac1ac20e70e425
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---

# <a name="cost-controlling-mobile-workspace"></a><span data-ttu-id="ace09-104">Mobilny obszar roboczy Kontrola kosztów</span><span class="sxs-lookup"><span data-stu-id="ace09-104">Cost controlling mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ace09-105">Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego **Kontrola kosztów**.</span><span class="sxs-lookup"><span data-stu-id="ace09-105">This topic provides information about the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="ace09-106">Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie.</span><span class="sxs-lookup"><span data-stu-id="ace09-106">This workspace lets cost center managers view information about cost center performance anytime and anywhere.</span></span>

<span data-ttu-id="ace09-107">Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji komórkowej Microsoft Dynamics 365 for Unified Operations.</span><span class="sxs-lookup"><span data-stu-id="ace09-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="ace09-108">Przegląd</span><span class="sxs-lookup"><span data-stu-id="ace09-108">Overview</span></span>
<span data-ttu-id="ace09-109">Mobilny obszar roboczy **Kontrola kosztów** zapewnia natychmiastowy podgląd wyników działania centrów kosztów poprzez porównanie kosztów rzeczywistych z kosztami budżetowymi.</span><span class="sxs-lookup"><span data-stu-id="ace09-109">The **Cost controlling** mobile workspace provides an instant view of the current performance of cost centers by comparing actual costs against the budgeted costs.</span></span> <span data-ttu-id="ace09-110">W widoku można przechodzić do stanów poszczególnych składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="ace09-110">You can drill down to the status of individual cost elements.</span></span>

<span data-ttu-id="ace09-111">Na przykład pracownik otrzymuje zaproszenie na międzynarodową konferencję, ale organizacja musi pokryć wszystkie wydatki na podróż.</span><span class="sxs-lookup"><span data-stu-id="ace09-111">For example, an employee receives an invitation to an international conference, but the organization must cover all the travel expenses.</span></span> <span data-ttu-id="ace09-112">Pracownik pyta przełożonego, czy może wziąć udział w konferencji.</span><span class="sxs-lookup"><span data-stu-id="ace09-112">The employee asks his manager whether he can attend the conference.</span></span> <span data-ttu-id="ace09-113">Przełożony otwiera mobilny obszar roboczy **Kontrola kosztów** na swoim telefonie komórkowym i sprawdza, czy ma budżet na pokrycie kosztów udziału pracownika w konferencji.</span><span class="sxs-lookup"><span data-stu-id="ace09-113">The manager opens the **Cost controlling** mobile workspace on her mobile device to see whether she has budget for the employee to attend the conference.</span></span>

### <a name="data-security"></a><span data-ttu-id="ace09-114">Bezpieczeństwo danych</span><span class="sxs-lookup"><span data-stu-id="ace09-114">Data security</span></span>
<span data-ttu-id="ace09-115">Dane w komórkowym obszarze roboczym **Kontrola kosztów** są zabezpieczone poświadczeniami użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ace09-115">The data in the **Cost controlling** mobile workspace is secured through user credentials.</span></span> <span data-ttu-id="ace09-116">Menedżerowie centrów kosztów mają pozwolenie na wgląd tylko w dane swoich centrów kosztów.</span><span class="sxs-lookup"><span data-stu-id="ace09-116">Cost center managers are allowed to see data only for their own cost center.</span></span> <span data-ttu-id="ace09-117">Zabezpieczenia na poziomie dostępu są administrowane w module **Rachunek kosztów**.</span><span class="sxs-lookup"><span data-stu-id="ace09-117">The access-level security is managed in the **Cost accounting** module.</span></span>

<span data-ttu-id="ace09-118">Księgowi kosztów definiują konfigurację mobilnego obszaru roboczego **Kontrola kosztów** w module **Rachunek kosztów**.</span><span class="sxs-lookup"><span data-stu-id="ace09-118">Cost accountants define the configuration of the **Cost controlling** mobile workspace in the **Cost accounting** module.</span></span> <span data-ttu-id="ace09-119">Po opublikowaniu obszaru roboczego w aplikacji komórkowej jest on dostępny w tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ace09-119">After the workspace is published to the mobile app, it's available in the app.</span></span> <span data-ttu-id="ace09-120">Dzięki temu menedżerowie centrów kosztów w organizacji mogą wyświetlać dane w tym samym formacie.</span><span class="sxs-lookup"><span data-stu-id="ace09-120">Therefore, all cost center managers in the organization can view data in the same format.</span></span>

### <a name="actions-views-and-links"></a><span data-ttu-id="ace09-121">Akcje, widoki i łącza</span><span class="sxs-lookup"><span data-stu-id="ace09-121">Actions, views, and links</span></span>
<span data-ttu-id="ace09-122">Mobilny obszar roboczy **Kontrola kosztów** oferuje następujące czynności, widoki i łącza:</span><span class="sxs-lookup"><span data-stu-id="ace09-122">The **Cost controlling** mobile workspace provides the following actions, views, and links:</span></span>

-   <span data-ttu-id="ace09-123">**Akcje:**</span><span class="sxs-lookup"><span data-stu-id="ace09-123">**Actions:**</span></span>

    -   <span data-ttu-id="ace09-124">Użyj **Wybierz konfigurację**, aby wybrać układ.</span><span class="sxs-lookup"><span data-stu-id="ace09-124">Use **Select configuration** to select a layout.</span></span>
    -   <span data-ttu-id="ace09-125">Użyj **Wybierz obiekt kosztu**, aby wybrać centra kosztów, według których mają zostać wyfiltrowane dane.</span><span class="sxs-lookup"><span data-stu-id="ace09-125">Use **Select cost object** to select the cost centers to filter data on.</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="ace09-126">Centra kosztów wyświetlane na liście zależą od dostępu udzielonego w module **Rachunek kosztów**.</span><span class="sxs-lookup"><span data-stu-id="ace09-126">The cost centers that appear in the list depend on the access that is granted in the **Cost accounting** module.</span></span>

-   <span data-ttu-id="ace09-127">**Widoki:** Zależnie od wybranych akcji oraz konfiguracji w module **Rachunek kosztów** można przeglądać poniższe informacje na kartach:</span><span class="sxs-lookup"><span data-stu-id="ace09-127">**Views:** Based on the actions that are selected and the configuration in the **Cost accounting** module, you can view the following information on the cards:</span></span>

    -   <span data-ttu-id="ace09-128">Rzeczywisty a budżetowy (bieżący okres)</span><span class="sxs-lookup"><span data-stu-id="ace09-128">Actual vs budget (current period)</span></span>
    -   <span data-ttu-id="ace09-129">Rzeczywisty a skorygowany budżetowy (bieżący okres)</span><span class="sxs-lookup"><span data-stu-id="ace09-129">Actual vs revised budget (current period)</span></span>
    -   <span data-ttu-id="ace09-130">Wartości rzeczywiste a budżet (poprzedni okres)</span><span class="sxs-lookup"><span data-stu-id="ace09-130">Actual vs budget (previous period)</span></span>
    -   <span data-ttu-id="ace09-131">Wartości rzeczywiste a skorygowany budżet (poprzedni okres)</span><span class="sxs-lookup"><span data-stu-id="ace09-131">Actual vs revised budget (previous period)</span></span>
    -   <span data-ttu-id="ace09-132">Wartości rzeczywiste a budżet (od początku roku)</span><span class="sxs-lookup"><span data-stu-id="ace09-132">Actual vs budget (year to date)</span></span>
    -   <span data-ttu-id="ace09-133">Wartości rzeczywiste a skorygowany budżet (od początku roku)</span><span class="sxs-lookup"><span data-stu-id="ace09-133">Actual vs revised budget (year to date)</span></span>

    <span data-ttu-id="ace09-134">Na każdej karcie są wyświetlane następujące kwoty: wartości rzeczywiste, budżet, odchylenie i % odchylenia.</span><span class="sxs-lookup"><span data-stu-id="ace09-134">The following amounts are shown on every card: Actual, Budget, Variance, and Variance %.</span></span>

-   <span data-ttu-id="ace09-135">**Linki:**</span><span class="sxs-lookup"><span data-stu-id="ace09-135">**Links:**</span></span>

    -   <span data-ttu-id="ace09-136">Szczegóły bieżącego okresu</span><span class="sxs-lookup"><span data-stu-id="ace09-136">Details for current period</span></span>
    -   <span data-ttu-id="ace09-137">Szczegóły poprzedniego okresu</span><span class="sxs-lookup"><span data-stu-id="ace09-137">Details for previous period</span></span>
    -   <span data-ttu-id="ace09-138">Szczegóły okresu od początku roku</span><span class="sxs-lookup"><span data-stu-id="ace09-138">Details for year to date</span></span>

    <span data-ttu-id="ace09-139">Po wybraniu łącza jest wyświetlana karta dla każdego składnika kosztów.</span><span class="sxs-lookup"><span data-stu-id="ace09-139">When you select a link, a card is shown for each cost element.</span></span> <span data-ttu-id="ace09-140">Na każdej karcie są wyświetlane następujące kwoty: wartości rzeczywiste, budżet, odchylenie budżetu, % odchylenia budżetu, skorygowany budżet, odchylenie skorygowanego budżetu i % odchylenia skorygowanego budżetu.</span><span class="sxs-lookup"><span data-stu-id="ace09-140">The following amounts are shown on every card: Actual, Budget, Budget variance, Budget variance %, Revised budget, Revised budget variance, and Revised budget variance %.</span></span>
    
    <span data-ttu-id="ace09-141">[![Karta składnika kosztu ](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span><span class="sxs-lookup"><span data-stu-id="ace09-141">[![Card for a cost element](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ace09-142">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ace09-142">Prerequisites</span></span>
<span data-ttu-id="ace09-143">Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.</span><span class="sxs-lookup"><span data-stu-id="ace09-143">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="ace09-144">Warunki wstępne w przypadku korzystania z programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ace09-144">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations, Enterprise edition</span></span>
<span data-ttu-id="ace09-145">Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, administrator systemu musi opublikować mobilny obszar roboczy **Kontrola kosztów**.</span><span class="sxs-lookup"><span data-stu-id="ace09-145">If Microsoft Dynamics 365 for Finance and Operations, Enterprise edition has been deployed for your organization, the system administrator must publish the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="ace09-146">Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="ace09-146">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="ace09-147">Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą</span><span class="sxs-lookup"><span data-stu-id="ace09-147">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later</span></span>
<span data-ttu-id="ace09-148">Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą, administrator systemu musi wykonać następujące zadania wstępne.</span><span class="sxs-lookup"><span data-stu-id="ace09-148">If Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ace09-149">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="ace09-149">Prerequisite</span></span></th>
<th><span data-ttu-id="ace09-150">Rola</span><span class="sxs-lookup"><span data-stu-id="ace09-150">Role</span></span></th>
<th><span data-ttu-id="ace09-151">opis</span><span class="sxs-lookup"><span data-stu-id="ace09-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ace09-152">Zainstalowanie poprawki KB 4013633.</span><span class="sxs-lookup"><span data-stu-id="ace09-152">Implement KB 4013633.</span></span></td>
<td><span data-ttu-id="ace09-153">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="ace09-153">System administrator</span></span></td>

<td><span data-ttu-id="ace09-154">KB 4013633 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Kontrola kosztów</strong>.</span><span class="sxs-lookup"><span data-stu-id="ace09-154">KB 4013633 is an X++ update or metadata hotfix that contains the <strong>Cost controlling</strong> mobile workspace.</span></span> <span data-ttu-id="ace09-155">W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:</span><span class="sxs-lookup"><span data-stu-id="ace09-155">To implement KB 4013633, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="ace09-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="ace09-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="ace09-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Zainstaluj poprawkę metadanych</a>.</span><span class="sxs-lookup"><span data-stu-id="ace09-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="ace09-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ace09-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="ace09-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Zastosuj wdrażalny pakiet</a></span><span class="sxs-lookup"><span data-stu-id="ace09-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ace09-160">Opublikowanie mobilnego obszaru roboczego <strong>Kontrola kosztów</strong>.</span><span class="sxs-lookup"><span data-stu-id="ace09-160">Publish the <strong>Cost controlling</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="ace09-161">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="ace09-161">System administrator</span></span></td>
<td><span data-ttu-id="ace09-162">Zobacz <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>.</span><span class="sxs-lookup"><span data-stu-id="ace09-162">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="ace09-163">Pobieranie i instalowanie aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="ace09-163">Download and install the mobile app</span></span>
<span data-ttu-id="ace09-164">Pobierz i zainstaluj aplikację komórkową Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="ace09-164">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="ace09-165">Telefony z systemem Android</span><span class="sxs-lookup"><span data-stu-id="ace09-165">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="ace09-166">Telefony iPhone</span><span class="sxs-lookup"><span data-stu-id="ace09-166">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="ace09-167">Logowanie do aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="ace09-167">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="ace09-168">Uruchom aplikację na urządzeniu komórkowym.</span><span class="sxs-lookup"><span data-stu-id="ace09-168">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="ace09-169">Wprowadź adres URL usługi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ace09-169">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="ace09-170">Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła.</span><span class="sxs-lookup"><span data-stu-id="ace09-170">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="ace09-171">Wprowadź swoje poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="ace09-171">Enter your credentials.</span></span>
4.  <span data-ttu-id="ace09-172">Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy.</span><span class="sxs-lookup"><span data-stu-id="ace09-172">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="ace09-173">Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="ace09-173">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="ace09-174">[![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="ace09-174">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a><span data-ttu-id="ace09-175">Wyświetlanie wyników działania centrum kosztów przy użyciu mobilnego obszaru roboczego Kontrola kosztów</span><span class="sxs-lookup"><span data-stu-id="ace09-175">View the performance of your cost center by using the Cost controlling mobile workspace</span></span>

1.  <span data-ttu-id="ace09-176">Na urządzeniu przenośnym wybierz obszar roboczy **Kontrola kosztów**.</span><span class="sxs-lookup"><span data-stu-id="ace09-176">On your mobile device, select the **Cost controlling** workspace.</span></span>
2.  <span data-ttu-id="ace09-177">Wybierz opcję **Kontrola obiektów kosztów**.</span><span class="sxs-lookup"><span data-stu-id="ace09-177">Select **Cost object controlling**.</span></span>
3.  <span data-ttu-id="ace09-178">Wybierz opcję **Akcje**.</span><span class="sxs-lookup"><span data-stu-id="ace09-178">Select **Actions**.</span></span>
4.  <span data-ttu-id="ace09-179">Wybierz opcję **Wybierz konfigurację** i wybierz układ kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="ace09-179">Select **Select configuration** to select a cost controlling layout.</span></span>
5.  <span data-ttu-id="ace09-180">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="ace09-180">Select **Done**.</span></span>
6.  <span data-ttu-id="ace09-181">Wybierz opcję **Akcje**.</span><span class="sxs-lookup"><span data-stu-id="ace09-181">Select **Actions**.</span></span>
7.  <span data-ttu-id="ace09-182">Wybierz opcję **Wybierz obiekt kosztu** i zaznacz centra kosztów, do których przyznano Ci uprawnienie dostępu.</span><span class="sxs-lookup"><span data-stu-id="ace09-182">Select **Select cost object** to select the cost centers that you've been granted access to.</span></span>
8.  <span data-ttu-id="ace09-183">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="ace09-183">Select **Done**.</span></span>
9.  <span data-ttu-id="ace09-184">Wyświetl całościowe wyniki działania centrum kosztów.</span><span class="sxs-lookup"><span data-stu-id="ace09-184">View the overall performance of your cost center.</span></span>
10. <span data-ttu-id="ace09-185">Kliknij łącze **Szczegóły bieżącego okresu**.</span><span class="sxs-lookup"><span data-stu-id="ace09-185">Select the **Details for current period** link.</span></span>
11. <span data-ttu-id="ace09-186">Wyświetl wyniki działania poszczególnych składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="ace09-186">View the performance of individual cost elements.</span></span>
12. <span data-ttu-id="ace09-187">Można także wyszukiwać konkretne składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="ace09-187">You can also search for specific cost elements.</span></span>


