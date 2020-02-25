---
title: Wdrażanie nowej dzierżawy e-commerce
description: W tym temacie opisano sposób wdrażania nowej dzierżawy e-Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS).
author: psimolin
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: 6d7dfcaf244260de5f39a1201ec1ea78e94351e7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001790"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="6c916-103">Wdrażanie nowej dzierżawy e-commerce</span><span class="sxs-lookup"><span data-stu-id="6c916-103">Deploy a new e-Commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6c916-104">W tym temacie opisano sposób wdrażania nowej witryny e-Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="6c916-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="6c916-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6c916-105">Overview</span></span>

<span data-ttu-id="6c916-106">Microsoft Dynamics Lifecycle Services (usługi LCS) to oparty na chmurze obszar roboczy, za pomocą którego partnerzy i klienci mogą zarządzać swoimi projektami i środowiskami, wyświetlać najnowsze informacje o produktach i funkcjach Microsoft Dynamics oraz tworzyć, śledzić i przeglądać zdarzenia pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="6c916-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="6c916-107">Funkcje zarządzania e-Commerce są zintegrowane z usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="6c916-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="6c916-108">Aby dowiedzieć się więcej o usługi LCS, zobacz [Przewodnik użytkownika usługi Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="6c916-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="6c916-109">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="6c916-109">Get started</span></span>

<span data-ttu-id="6c916-110">Aby można było zainicjować e-Commerce, należy zainicjować projekt, środowisko i Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="6c916-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="6c916-111">Aby wykonać inicjalizację w usługi LCS, trzeba mieć uprawnienia do roli Właściciel projektu lub Menedżer środowiska.</span><span class="sxs-lookup"><span data-stu-id="6c916-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="6c916-112">Topologie środowiska produkcyjnego i piaskownicy są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="6c916-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="6c916-113">Aby uzyskać więcej informacji o środowiskach, należy zapoznać się z tematem [Planowanie środowiska](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="6c916-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="6c916-114">Aby uzyskać więcej informacji na temat dzienników RCSU, zobacz temat [Inicjowanie Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="6c916-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="6c916-115">Inicjalizowanie e-Commerce</span><span class="sxs-lookup"><span data-stu-id="6c916-115">Initialize e-Commerce</span></span>

<span data-ttu-id="6c916-116">Ta procedura służy do inicjowania funkcji e-Commerce w istniejącym środowisku.</span><span class="sxs-lookup"><span data-stu-id="6c916-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="6c916-117">Przed rozpoczęciem należy upewnić się, że istnieją następujące wymagane informacje:</span><span class="sxs-lookup"><span data-stu-id="6c916-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="6c916-118">RCSU, który będzie używany.</span><span class="sxs-lookup"><span data-stu-id="6c916-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="6c916-119">Grupa zabezpieczeń Azure Active Directory Microsoft, która będzie używana dla administratorów systemu w e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="6c916-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="6c916-120">Grupa zabezpieczeń Azure Active Directory Microsoft, która będzie używana dla moderatorów ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="6c916-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="6c916-121">Domeny, które będą skojarzone ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="6c916-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="6c916-122">Ponadto można zebrać następujące informacje opcjonalne:</span><span class="sxs-lookup"><span data-stu-id="6c916-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="6c916-123">Azure AD informacje o relacji od firmy do konsumenta (B2C):</span><span class="sxs-lookup"><span data-stu-id="6c916-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="6c916-124">Nazwa dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="6c916-124">Tenant Name.</span></span>
    - <span data-ttu-id="6c916-125">Identyfikator klienta.</span><span class="sxs-lookup"><span data-stu-id="6c916-125">Client ID.</span></span>
    - <span data-ttu-id="6c916-126">Niestandardowa domena logowania.</span><span class="sxs-lookup"><span data-stu-id="6c916-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="6c916-127">Odpowiedź URL.</span><span class="sxs-lookup"><span data-stu-id="6c916-127">Reply URL.</span></span>
    - <span data-ttu-id="6c916-128">Identyfikator zasad logowania i rejestracji.</span><span class="sxs-lookup"><span data-stu-id="6c916-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="6c916-129">Identyfikator zasad resetowania haseł.</span><span class="sxs-lookup"><span data-stu-id="6c916-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="6c916-130">Edytuj identyfikator zasad profilu.</span><span class="sxs-lookup"><span data-stu-id="6c916-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="6c916-131">Te informacje można dodać później za pośrednictwem zlecenia usługi.</span><span class="sxs-lookup"><span data-stu-id="6c916-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="6c916-132">Po zebraniu wymaganych informacji należy wykonać poniższe kroki w celu zainicjowania e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="6c916-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="6c916-133">Zaloguj się w [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="6c916-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="6c916-134">Otwórz projekt zawierający środowisko, w którym chcesz zainicjować e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="6c916-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="6c916-135">W sekcji **środowiska** wybierz środowisko.</span><span class="sxs-lookup"><span data-stu-id="6c916-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="6c916-136">W obszarze **Funkcje środowiska** wybierz łącze **zarządzanie detaliczne**.</span><span class="sxs-lookup"><span data-stu-id="6c916-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="6c916-137">Na karcie **e-Commerce** wybierz opcję **ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="6c916-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="6c916-138">Zostanie wyświetlone okno dialogowe, w którym należy wprowadzić informacje wymagane do zainicjowania obsługi administracyjnej.</span><span class="sxs-lookup"><span data-stu-id="6c916-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="6c916-139">Wprowadź wymagane informacje, a następnie przejdź do następnej strony.</span><span class="sxs-lookup"><span data-stu-id="6c916-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="6c916-140">Na następnej stronie wpisz wymagane informacje, a następnie prześlij formularz.</span><span class="sxs-lookup"><span data-stu-id="6c916-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="6c916-141">Powrócisz na kartę **e-Commerce**, w której powinny być widoczne informacje o uruchomieniu inicjalizacji.</span><span class="sxs-lookup"><span data-stu-id="6c916-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="6c916-142">Aby wyświetlić stan inicjalizacji, należy **odświeżyć** lub wrócić na kartę **e-Commerce** później.</span><span class="sxs-lookup"><span data-stu-id="6c916-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="6c916-143">Gdy e-Commerce jest inicjowany z usługi LCS, system Inicjuje obsługę kilku składników wymaganych w e-Commerce i kojarzy je ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="6c916-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="6c916-144">Po zakończeniu obsługi administracyjnej karta **e-Commerce** na stronie **Zarządzanie Retail** jest aktualizowana w celu uwzględnienia tej zmiany.</span><span class="sxs-lookup"><span data-stu-id="6c916-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="6c916-145">Na stronie są wyświetlane najnowsze wdrożenia dostosowań oraz stan wszystkich innych trwających wdrożeń.</span><span class="sxs-lookup"><span data-stu-id="6c916-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="6c916-146">Zawiera także łącza do witryny e-Commerce oraz narzędzia do zarządzania witryną e-Commerce, gdzie tworzone są witryny.</span><span class="sxs-lookup"><span data-stu-id="6c916-146">It also includes links to the e-Commerce site and the e-Commerce site builder where sites are authored.</span></span>

## <a name="access-site-builder"></a><span data-ttu-id="6c916-147">Dostęp do konstruktora witryn</span><span class="sxs-lookup"><span data-stu-id="6c916-147">Access site builder</span></span>

<span data-ttu-id="6c916-148">Aby uzyskać dostęp do konstruktora witryn, przejdź na kartę **e-Commerce** na stronie **Zarządzanie Retail** w usłudze LCS i wybierz **narzędzia zarządzania witryny e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="6c916-148">To access site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="6c916-149">Strona docelowa konstruktora witryn umożliwia wyświetlenie widoku na poziomie dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="6c916-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="6c916-150">Z poziomu tej strony można:</span><span class="sxs-lookup"><span data-stu-id="6c916-150">From this page, you can:</span></span>

- <span data-ttu-id="6c916-151">Modyfikować ustawienia na poziomie dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="6c916-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="6c916-152">Przechodzić do dowolnych utworzonych witryn i mających uprawnienia do wyświetlania.</span><span class="sxs-lookup"><span data-stu-id="6c916-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="6c916-153">Uzyskać dostęp do funkcji ocen, takich jak moderowania i reportowania.</span><span class="sxs-lookup"><span data-stu-id="6c916-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="6c916-154">Stworzyć nową witrynę.</span><span class="sxs-lookup"><span data-stu-id="6c916-154">Create a new site.</span></span> <span data-ttu-id="6c916-155">Aby uzyskać więcej informacji dotyczących sposobu tworzenia nowej witryny, zobacz [Tworzenie nowej witryny e-Commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="6c916-155">For more information about how to create a new site, see [Create an e-Commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="6c916-156">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6c916-156">Additional resources</span></span>

[<span data-ttu-id="6c916-157">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="6c916-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="6c916-158">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="6c916-158">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="6c916-159">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="6c916-159">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="6c916-160">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="6c916-160">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="6c916-161">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="6c916-161">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="6c916-162">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="6c916-162">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="6c916-163">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="6c916-163">Enable location-based store detection</span></span>](enable-store-detection.md)
