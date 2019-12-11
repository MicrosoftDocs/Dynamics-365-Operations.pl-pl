---
title: Wdrażanie nowej dzierżawy e-commerce
description: W tym temacie opisano sposób wdrażania nowej dzierżawy e-Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS).
author: psimolin
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c2632632b9b21dd3a88e9a4df0e65cfd28e579d2
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697458"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="8550c-103">Wdrażanie nowej dzierżawy e-commerce</span><span class="sxs-lookup"><span data-stu-id="8550c-103">Deploy a new e-Commerce tenant</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="8550c-104">W tym temacie opisano sposób wdrażania nowej witryny e-Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="8550c-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="8550c-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="8550c-105">Overview</span></span>
    
<span data-ttu-id="8550c-106">Microsoft Dynamics Lifecycle Services (usługi LCS) to oparty na chmurze obszar roboczy, za pomocą którego partnerzy i klienci mogą zarządzać swoimi projektami i środowiskami, wyświetlać najnowsze informacje o produktach i funkcjach Microsoft Dynamics oraz tworzyć, śledzić i przeglądać zdarzenia pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="8550c-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="8550c-107">Funkcje zarządzania e-Commerce są zintegrowane z usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="8550c-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="8550c-108">Aby dowiedzieć się więcej o usługi LCS, zobacz [Przewodnik użytkownika usługi Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="8550c-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="8550c-109">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="8550c-109">Get started</span></span>

<span data-ttu-id="8550c-110">Aby można było zainicjować e-Commerce, należy zainicjować projekt, środowisko i Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="8550c-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="8550c-111">Aby wykonać inicjalizację w usługi LCS, trzeba mieć uprawnienia do roli Właściciel projektu lub Menedżer środowiska.</span><span class="sxs-lookup"><span data-stu-id="8550c-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="8550c-112">Topologie środowiska produkcyjnego i piaskownicy są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="8550c-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="8550c-113">Aby uzyskać więcej informacji o środowiskach, należy zapoznać się z tematem [Planowanie środowiska](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="8550c-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="8550c-114">Aby uzyskać więcej informacji na temat dzienników RCSU, zobacz temat [Inicjowanie Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="8550c-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="8550c-115">Inicjalizowanie e-Commerce</span><span class="sxs-lookup"><span data-stu-id="8550c-115">Initialize e-Commerce</span></span>

<span data-ttu-id="8550c-116">Ta procedura służy do inicjowania funkcji e-Commerce w istniejącym środowisku.</span><span class="sxs-lookup"><span data-stu-id="8550c-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="8550c-117">Przed rozpoczęciem należy upewnić się, że istnieją następujące wymagane informacje:</span><span class="sxs-lookup"><span data-stu-id="8550c-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="8550c-118">RCSU, który będzie używany.</span><span class="sxs-lookup"><span data-stu-id="8550c-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="8550c-119">Grupa zabezpieczeń Azure Active Directory Microsoft, która będzie używana dla administratorów systemu w e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="8550c-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="8550c-120">Grupa zabezpieczeń Azure Active Directory Microsoft, która będzie używana dla moderatorów ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="8550c-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="8550c-121">Domeny, które będą skojarzone ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="8550c-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="8550c-122">Ponadto można zebrać następujące informacje opcjonalne:</span><span class="sxs-lookup"><span data-stu-id="8550c-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="8550c-123">Azure AD informacje o relacji od firmy do konsumenta (B2C):</span><span class="sxs-lookup"><span data-stu-id="8550c-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="8550c-124">Nazwa dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="8550c-124">Tenant Name.</span></span>
    - <span data-ttu-id="8550c-125">Identyfikator klienta.</span><span class="sxs-lookup"><span data-stu-id="8550c-125">Client ID.</span></span>
    - <span data-ttu-id="8550c-126">Niestandardowa domena logowania.</span><span class="sxs-lookup"><span data-stu-id="8550c-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="8550c-127">Odpowiedź URL.</span><span class="sxs-lookup"><span data-stu-id="8550c-127">Reply URL.</span></span>
    - <span data-ttu-id="8550c-128">Identyfikator zasad logowania i rejestracji.</span><span class="sxs-lookup"><span data-stu-id="8550c-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="8550c-129">Identyfikator zasad resetowania haseł.</span><span class="sxs-lookup"><span data-stu-id="8550c-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="8550c-130">Edytuj identyfikator zasad profilu.</span><span class="sxs-lookup"><span data-stu-id="8550c-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="8550c-131">Te informacje można dodać później za pośrednictwem zlecenia usługi.</span><span class="sxs-lookup"><span data-stu-id="8550c-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="8550c-132">Po zebraniu wymaganych informacji należy wykonać poniższe kroki w celu zainicjowania e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="8550c-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="8550c-133">Zaloguj się w [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="8550c-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="8550c-134">Otwórz projekt zawierający środowisko, w którym chcesz zainicjować e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="8550c-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="8550c-135">W sekcji **środowiska** wybierz środowisko.</span><span class="sxs-lookup"><span data-stu-id="8550c-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="8550c-136">W obszarze **Funkcje środowiska** wybierz łącze **zarządzanie detaliczne**.</span><span class="sxs-lookup"><span data-stu-id="8550c-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="8550c-137">Na karcie **e-Commerce** wybierz opcję **ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="8550c-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="8550c-138">Zostanie wyświetlone okno dialogowe, w którym należy wprowadzić informacje wymagane do zainicjowania obsługi administracyjnej.</span><span class="sxs-lookup"><span data-stu-id="8550c-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="8550c-139">Wprowadź wymagane informacje, a następnie przejdź do następnej strony.</span><span class="sxs-lookup"><span data-stu-id="8550c-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="8550c-140">Na następnej stronie wpisz wymagane informacje, a następnie prześlij formularz.</span><span class="sxs-lookup"><span data-stu-id="8550c-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="8550c-141">Powrócisz na kartę **e-Commerce**, w której powinny być widoczne informacje o uruchomieniu inicjalizacji.</span><span class="sxs-lookup"><span data-stu-id="8550c-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="8550c-142">Aby wyświetlić stan inicjalizacji, należy **odświeżyć** lub wrócić na kartę **e-Commerce** później.</span><span class="sxs-lookup"><span data-stu-id="8550c-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="8550c-143">Gdy e-Commerce jest inicjowany z usługi LCS, system Inicjuje obsługę kilku składników wymaganych w e-Commerce i kojarzy je ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="8550c-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="8550c-144">Po zakończeniu obsługi administracyjnej karta **e-Commerce** na stronie **zarządzania detalicznego** jest aktualizowana w celu uwzględnienia tej zmiany.</span><span class="sxs-lookup"><span data-stu-id="8550c-144">After provisioning is completed, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="8550c-145">Na stronie są wyświetlane najnowsze wdrożenia dostosowań oraz stan wszystkich innych trwających wdrożeń.</span><span class="sxs-lookup"><span data-stu-id="8550c-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="8550c-146">Zawiera także łącza do witryny e-Commerce oraz narzędzia do zarządzania oddziałem e-Commerce (narzędzie autorskie).</span><span class="sxs-lookup"><span data-stu-id="8550c-146">It also includes links to the e-Commerce site and the e-Commerce site management tool (the authoring tool).</span></span>

## <a name="access-the-authoring-environment"></a><span data-ttu-id="8550c-147">Dostęp do środowiska autorskiego</span><span class="sxs-lookup"><span data-stu-id="8550c-147">Access the authoring environment</span></span>

<span data-ttu-id="8550c-148">Aby uzyskać dostęp do środowiska projektowego, przejdź do karty **e-Commerce** na stronie **Zarządzanie detalicznymi**.</span><span class="sxs-lookup"><span data-stu-id="8550c-148">To access the authoring environment, go to the **e-Commerce** tab on the **Retail management** page.</span></span> <span data-ttu-id="8550c-149">W tym miejscu znajdują się łącza do witryny e-Commerce oraz narzędzia do zarządzania oddziałem.</span><span class="sxs-lookup"><span data-stu-id="8550c-149">There, you will find links to your e-Commerce site and the site management tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8550c-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8550c-150">Additional resources</span></span>

[<span data-ttu-id="8550c-151">Omówienie sklepu internetowego</span><span class="sxs-lookup"><span data-stu-id="8550c-151">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="8550c-152">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8550c-152">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="8550c-153">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="8550c-153">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="8550c-154">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="8550c-154">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="8550c-155">Dodaj obsługę dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="8550c-155">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="8550c-156">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="8550c-156">Enable location-based store detection</span></span>](enable-store-detection.md)

[<span data-ttu-id="8550c-157">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="8550c-157">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
