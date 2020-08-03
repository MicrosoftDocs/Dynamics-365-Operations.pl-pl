---
title: Ustanowienie środowiska oceny rozwiązania Dynamics 365 Commerce
description: W tym temacie opisano sposób aprowizowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e5ce2002c66a1c36d5647d3c76684b394fc1ff79
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599857"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="68659-103">Ustanowienie środowiska oceny rozwiązania Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="68659-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="68659-104">W tym temacie opisano sposób aprowizowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="68659-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="68659-105">Przed rozpoczęciem zalecane jest wykonanie szybkiego przeglądu tego tematu w celu uzyskania informacji na temat wymaganego procesu.</span><span class="sxs-lookup"><span data-stu-id="68659-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="68659-106">Środowiska testowe w handlu są zazwyczaj niedostępne i są przyznawane partnerom i odbiorcom na żądanie.</span><span class="sxs-lookup"><span data-stu-id="68659-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="68659-107">Aby uzyskać więcej informacji, skontaktuj się z partnerem firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68659-107">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="68659-108">Omówienie</span><span class="sxs-lookup"><span data-stu-id="68659-108">Overview</span></span>

<span data-ttu-id="68659-109">Aby pomyślnie aprowizować środowisko oceny rozwiązania Commerce, musisz utworzyć projekt, który ma określoną nazwę i typ produktu.</span><span class="sxs-lookup"><span data-stu-id="68659-109">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="68659-110">Środowisko i Commerce Scale Unit (CSU) mają także określone parametry, których należy użyć w celu spodziewanego późniejszego aprowizowania na platformie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="68659-110">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="68659-111">Instrukcje w tym temacie opisują wszystkie wymagane kroki do zakończenia aprowizowania i parametry, których należy użyć.</span><span class="sxs-lookup"><span data-stu-id="68659-111">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="68659-112">Po pomyślnym aprowizowaniu środowiska oceny rozwiązania Commerce istnieje kilka kroków aprowizacji, które należy wykonać, aby przygotować to środowisko do użytku.</span><span class="sxs-lookup"><span data-stu-id="68659-112">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="68659-113">Niektóre kroki są opcjonalne, w zależności od aspektów systemu, które mają być oceniane.</span><span class="sxs-lookup"><span data-stu-id="68659-113">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="68659-114">Opcjonalne kroki można wykonać później.</span><span class="sxs-lookup"><span data-stu-id="68659-114">You can always complete the optional steps later.</span></span>

<span data-ttu-id="68659-115">Aby uzyskać informacje dotyczące sposobu konfigurowania środowiska oceny usługi Commerce po jego aprowizowaniu, zobacz [Konfigurowanie środowiska oceny usługi Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="68659-115">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="68659-116">Aby uzyskać informacje dotyczące sposobu konfigurowania opcjonalnych funkcji środowiska oceny usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska oceny usługi Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="68659-116">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="68659-117">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="68659-117">Prerequisites</span></span>

<span data-ttu-id="68659-118">Zanim będzie można aprowizować środowisko oceny usługi Commerce, muszą zostać spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="68659-118">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="68659-119">Masz dostęp do portalu Lifecycle Services (LCS) rozwiązania Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="68659-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="68659-120">Użytkownik jest istniejącym partnerem Microsoft Dynamics 365 lub odbiorcą i może tworzyć projekt Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="68659-120">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="68659-121">Masz uprawnienia administratora do subskrypcji Microsoft Azure lub jesteś w kontakcie z administratorem subskrypcji, który może pomóc w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="68659-121">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="68659-122">Twój identyfikator dzierżawy Azure Active Directory (Azure AD) jest dostępny.</span><span class="sxs-lookup"><span data-stu-id="68659-122">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="68659-123">Utworzono grupę zabezpieczeń usługi Azure AD, która ma być używana jako Grupa administratorów systemu w e-Commerce i jest dostępny jej identyfikator.</span><span class="sxs-lookup"><span data-stu-id="68659-123">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="68659-124">Utworzono grupę zabezpieczeń usługi Azure AD, która ma być używana jako grupa moderatorów ocen i recenzji, i jest dostępny jej identyfikator.</span><span class="sxs-lookup"><span data-stu-id="68659-124">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="68659-125">(Ta grupa zabezpieczeń może być taka sama jak grupa administratorów systemu e-Commerce).</span><span class="sxs-lookup"><span data-stu-id="68659-125">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="68659-126">Należy zauważyć, że ta lista nie wymienia wszystkiego.</span><span class="sxs-lookup"><span data-stu-id="68659-126">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="68659-127">Jeśli napotkasz jakiekolwiek problemy, skontaktuj się z partnerem Microsoft w celu uzyskania pomocy.</span><span class="sxs-lookup"><span data-stu-id="68659-127">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="68659-128">Aprowizowanie środowiska oceny usługi Commerce</span><span class="sxs-lookup"><span data-stu-id="68659-128">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="68659-129">Te procedury wyjaśniają, jak aprowizować środowisko oceny Commerce.</span><span class="sxs-lookup"><span data-stu-id="68659-129">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="68659-130">Po ich pomyślnym ukończeniu środowisko oceny usługi Commerce będzie gotowe do konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="68659-130">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="68659-131">Wszystkie działania opisane w tym miejscu są wykonywane w portalu usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="68659-131">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="68659-132">Utwórz nowy projekt</span><span class="sxs-lookup"><span data-stu-id="68659-132">Create a new project</span></span>

<span data-ttu-id="68659-133">Aby utworzyć nowy projekt w usłudze LCS, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68659-133">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="68659-134">Na stronie głównej usługi LCS wybierz znak plus (**+**), aby utworzyć projekt.</span><span class="sxs-lookup"><span data-stu-id="68659-134">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="68659-135">W okienku po prawej stronie wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="68659-135">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="68659-136">Jeśli jesteś partnerem, wybierz pozycję **Wykonaj migrację, twórz rozwiązania i poznaj rozwiązanie**.</span><span class="sxs-lookup"><span data-stu-id="68659-136">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="68659-137">Jeśli jesteś klientem, wybierz pozycję **Potencjalne przedsprzedaże**.</span><span class="sxs-lookup"><span data-stu-id="68659-137">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="68659-138">Wprowadź nazwę, opis i branżę.</span><span class="sxs-lookup"><span data-stu-id="68659-138">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="68659-139">W polu **Nazwa produktu** wybierz pozycję **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="68659-139">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="68659-140">W polu **Wersja produktu** wybierz pozycję **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="68659-140">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="68659-141">W polu **Metodologia** wybierz pozycję **Metodologia implementacji aplikacji Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="68659-141">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="68659-142">Opcjonalnie: możesz zaimportować role i użytkowników z istniejącego projektu.</span><span class="sxs-lookup"><span data-stu-id="68659-142">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="68659-143">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="68659-143">Select **Create**.</span></span> <span data-ttu-id="68659-144">Zostanie wyświetlony widok projektu.</span><span class="sxs-lookup"><span data-stu-id="68659-144">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="68659-145">Dodawanie łącznika platformy Azure</span><span class="sxs-lookup"><span data-stu-id="68659-145">Add the Azure Connector</span></span>

<span data-ttu-id="68659-146">Aby dodać łącznik Azure Connector do projektu usługi LCS, wykonaj kroki opisane w [Proces przygotowania obsługi Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span><span class="sxs-lookup"><span data-stu-id="68659-146">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="68659-147">Wdrażanie środowiska</span><span class="sxs-lookup"><span data-stu-id="68659-147">Deploy the environment</span></span>

<span data-ttu-id="68659-148">Aby wdrożyć środowisko, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68659-148">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="68659-149">Być może nie trzeba będzie wykonywać kroków 6, 7 i/lub 8, ponieważ strony z jedną opcją są pomijane.</span><span class="sxs-lookup"><span data-stu-id="68659-149">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="68659-150">W widoku **Parametry środowiska** potwierdź, że tekst **Dynamics 365 Commerce — demo (10.0.* x* z aktualizacją platformy *xx*)\*\* pojawia się bezpośrednio nad polem **Nazwa środowiska**.</span><span class="sxs-lookup"><span data-stu-id="68659-150">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="68659-151">Aby uzyskać szczegółowe informacje, zobacz ilustrację wyświetlaną po kroku 8.</span><span class="sxs-lookup"><span data-stu-id="68659-151">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="68659-152">W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="68659-152">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="68659-153">Wybierz pozycję **Dodaj**, aby dodać środowisko.</span><span class="sxs-lookup"><span data-stu-id="68659-153">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="68659-154">W polu **wersja aplikacji** wybierz najbardziej aktualną wersję.</span><span class="sxs-lookup"><span data-stu-id="68659-154">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="68659-155">Jeśli masz określoną potrzebę wybrania wersji aplikacji innej niż wersja najbardziej aktualna, nie wybieraj wersji przed **10.0.8**.</span><span class="sxs-lookup"><span data-stu-id="68659-155">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.8**.</span></span>
1. <span data-ttu-id="68659-156">W polu **wersja platformy** użyj wersji platformy, która jest automatycznie wybierana dla wybranej wersji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="68659-156">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Wybieranie wersji aplikacji i platformy](./media/project1.png)

1. <span data-ttu-id="68659-158">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="68659-158">Select **Next**.</span></span>
1. <span data-ttu-id="68659-159">Wybierz pozycję **Pokaz** jako topologię środowiska.</span><span class="sxs-lookup"><span data-stu-id="68659-159">Select **Demo** as the environment topology.</span></span>

    ![Wybieranie topologii środowiska 1](./media/project2.png)

1. <span data-ttu-id="68659-161">Na stronie **Wdrażanie środowiska** wprowadź nazwę środowiska.</span><span class="sxs-lookup"><span data-stu-id="68659-161">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="68659-162">Pozostaw ustawienia zaawansowane niezmienione.</span><span class="sxs-lookup"><span data-stu-id="68659-162">Leave the advanced settings as they are.</span></span>

    ![Strona wdrażania środowiska](./media/project4.png)

1. <span data-ttu-id="68659-164">Dostosuj rozmiar maszyny wirtualnej zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="68659-164">Adjust the VM size as required.</span></span> <span data-ttu-id="68659-165">(Zalecamy użycie dla maszyny wirtualnej jednostki magazynowej \[SKU\] **D13 v2**).</span><span class="sxs-lookup"><span data-stu-id="68659-165">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="68659-166">Zapoznaj się z cenami i warunkami licencjonowania, a następnie zaznacz pole wyboru, aby wskazać, że zgadzasz się z nimi.</span><span class="sxs-lookup"><span data-stu-id="68659-166">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="68659-167">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="68659-167">Select **Next**.</span></span>
1. <span data-ttu-id="68659-168">Sprawdź, czy szczegóły są poprawne, na stronie potwierdzenia wdrożenia, a następnie wybierz pozycję **Wdróż**.</span><span class="sxs-lookup"><span data-stu-id="68659-168">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="68659-169">Powrócisz do widoku **Środowiska hostowane w chmurze**, a Twoje środowisko powinno pojawić się na liście.</span><span class="sxs-lookup"><span data-stu-id="68659-169">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="68659-170">Żądane środowisko będzie wyświetlane jako kolejkowane, a następnie wdrożone.</span><span class="sxs-lookup"><span data-stu-id="68659-170">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="68659-171">Zakończenie przepływów pracy środowiska potrwa pewien czas.</span><span class="sxs-lookup"><span data-stu-id="68659-171">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="68659-172">W związku z tym sprawdź ponownie po około sześciu do dziewięciu godzin.</span><span class="sxs-lookup"><span data-stu-id="68659-172">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="68659-173">Przed kontynuowaniem upewnij się, że stan środowiska to **Wdrożone**.</span><span class="sxs-lookup"><span data-stu-id="68659-173">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="68659-174">Inicjowanie Commerce Scale Unit (w chmurze)</span><span class="sxs-lookup"><span data-stu-id="68659-174">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="68659-175">Aby zainicjować jednostkę CSU, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68659-175">To initialize CSU, follow these steps.</span></span>

1. <span data-ttu-id="68659-176">W widoku **Środowiska hostowane w chmurze** wybierz środowisko na liście.</span><span class="sxs-lookup"><span data-stu-id="68659-176">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="68659-177">W widoku środowiska po prawej stronie wybierz pozycję **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="68659-177">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="68659-178">Zostanie wyświetlony widok szczegółów środowiska.</span><span class="sxs-lookup"><span data-stu-id="68659-178">The environment details view appears.</span></span>
1. <span data-ttu-id="68659-179">W obszarze **Funkcje środowiska** wybierz pozycję **Zarządzaj**.</span><span class="sxs-lookup"><span data-stu-id="68659-179">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="68659-180">Na karcie **Handel** wybierz pozycję **Inicjuj**.</span><span class="sxs-lookup"><span data-stu-id="68659-180">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="68659-181">Pojawi się widok parametrów inicjacji jednostki CSU.</span><span class="sxs-lookup"><span data-stu-id="68659-181">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="68659-182">W polu **Region** wybierz region, który jest taki sam lub podobny do regionu, do którego wdrożono środowisko.</span><span class="sxs-lookup"><span data-stu-id="68659-182">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="68659-183">Pole **Wersja** powinno pozostać niezmienione.</span><span class="sxs-lookup"><span data-stu-id="68659-183">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="68659-184">Wybierz pozycję **Inicjuj**.</span><span class="sxs-lookup"><span data-stu-id="68659-184">Select **Initialize**.</span></span>
1. <span data-ttu-id="68659-185">Sprawdź, czy szczegóły są poprawne, na stronie potwierdzenia wdrożenia, a następnie wybierz pozycję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="68659-185">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="68659-186">Widok **Zarządzanie handlem** jest wyświetlany ponownie, jeśli jest wybrana karta **Handel**.</span><span class="sxs-lookup"><span data-stu-id="68659-186">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="68659-187">CSU zostało dodane do kolejki w celu zainicjowania obsługi administracyjnej.</span><span class="sxs-lookup"><span data-stu-id="68659-187">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="68659-188">Przed kontynuowaniem upewnij się, że stan jednostki CSU to **Powodzenie**.</span><span class="sxs-lookup"><span data-stu-id="68659-188">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="68659-189">Inicjowanie trwa około dwóch do pięciu godzin.</span><span class="sxs-lookup"><span data-stu-id="68659-189">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="68659-190">Jeśli nie możesz znaleźć łącza **Zarządzaj** w widoku Szczegóły środowiska, skontaktuj się z osobą kontaktową z firmą Microsoft w celu uzyskania pomocy.</span><span class="sxs-lookup"><span data-stu-id="68659-190">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="68659-191">Inicjalizowanie e-Commerce</span><span class="sxs-lookup"><span data-stu-id="68659-191">Initialize e-Commerce</span></span>

<span data-ttu-id="68659-192">Aby zainicjować usługę e-Commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68659-192">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="68659-193">Na karcie **Handel elektroniczny** przejrzyj zgodę na korzystanie z oceny, a następnie wybierz pozycję **Instalator**.</span><span class="sxs-lookup"><span data-stu-id="68659-193">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="68659-194">W polu **Nazwa środowiska handlu elektronicznego** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="68659-194">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="68659-195">Należy mieć świadomość, że nazwa ta będzie widoczne w niektórych adresach URL wskazujących na to wystąpienie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="68659-195">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="68659-196">W polu **Nazwa Commerce Scale Unit** wybierz z listy jednostkę CSU.</span><span class="sxs-lookup"><span data-stu-id="68659-196">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="68659-197">(Lista powinna mieć tylko jedną opcję).</span><span class="sxs-lookup"><span data-stu-id="68659-197">(The list should have only one option.)</span></span>

    <span data-ttu-id="68659-198">Pole **Geografia handlu elektronicznego** jest ustawiane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="68659-198">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="68659-199">Wybierz przycisk **Dalej**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="68659-199">Select **Next** to continue.</span></span>
1. <span data-ttu-id="68659-200">W polu **Obsługiwane nazwy hostów** wprowadź dowolną prawidłową domenę, na przykład `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="68659-200">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="68659-201">W polu **Grupa zabezpieczeń usługi AAD dla administratora systemu** wprowadź kilka pierwszych liter nazwy grupy zabezpieczeń, której chcesz użyć, a następnie wybierz symbol lupy, aby wyświetlić wyniki wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="68659-201">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="68659-202">Wybierz prawidłową grupę zabezpieczeń na liście.</span><span class="sxs-lookup"><span data-stu-id="68659-202">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="68659-203">W polu **Grupa zabezpieczeń usługi AAD dla moderatora ocen i recenzji** wprowadź kilka pierwszych liter nazwy grupy zabezpieczeń, której chcesz użyć, a następnie wybierz symbol lupy, aby wyświetlić wyniki wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="68659-203">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="68659-204">Wybierz prawidłową grupę zabezpieczeń na liście.</span><span class="sxs-lookup"><span data-stu-id="68659-204">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="68659-205">Zostaw opcję **Włącz obsługę ocen i recenzji** ustawioną na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="68659-205">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="68659-206">Wybierz pozycję **Inicjuj**.</span><span class="sxs-lookup"><span data-stu-id="68659-206">Select **Initialize**.</span></span> <span data-ttu-id="68659-207">Widok **Zarządzanie handlem** jest wyświetlany ponownie, jeśli jest wybrana karta **e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="68659-207">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="68659-208">Inicjowanie usługi e-Commerce zostało rozpoczęte.</span><span class="sxs-lookup"><span data-stu-id="68659-208">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="68659-209">Przed kontynuowaniem poczekaj, aż stan inicjowania usługi e-Commerce zmieni się na **Inicjowanie powiodło się**.</span><span class="sxs-lookup"><span data-stu-id="68659-209">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="68659-210">W prawym dolnym rogu sekcji **Linki** zanotuj adresy URL następujących linków:</span><span class="sxs-lookup"><span data-stu-id="68659-210">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="68659-211">**Witryna usługi e-Commerce** — link do katalogu głównego witryny usługi e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="68659-211">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="68659-212">**Konstruktor witryn handlu elektronicznego** — link do narzędzia do zarządzania witryną.</span><span class="sxs-lookup"><span data-stu-id="68659-212">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68659-213">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="68659-213">Next steps</span></span>

<span data-ttu-id="68659-214">Aby kontynuować proces aprowizowania i konfigurowania środowiska oceny usługi Commerce, zobacz [Konfigurowanie środowiska oceny usługi Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="68659-214">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="68659-215">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="68659-215">Additional resources</span></span>

[<span data-ttu-id="68659-216">Omówienie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="68659-216">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="68659-217">Konfigurowanie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="68659-217">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="68659-218">Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="68659-218">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="68659-219">Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="68659-219">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="68659-220">Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="68659-220">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="68659-221">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="68659-221">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="68659-222">Commerce Scale Unit (w chmurze)</span><span class="sxs-lookup"><span data-stu-id="68659-222">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="68659-223">Portal Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="68659-223">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="68659-224">Witryna Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="68659-224">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
