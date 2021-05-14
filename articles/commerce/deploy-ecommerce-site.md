---
title: Wdrażanie nowej dzierżawy handlu elektronicznego
description: W tym temacie opisano sposób wdrażania nowej witryny e-Commerce Dynamics 365 Commerce za pomocą Lifecycle Services (usługi LCS) Microsoft Dynamics.
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b228babfd32a4191eeed2a6d924a8b99f1a5311
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936713"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="a07b5-103">Wdrażanie nowej dzierżawy handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="a07b5-103">Deploy a new e-commerce tenant</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a07b5-104">W tym temacie opisano sposób wdrażania nowej witryny e-Commerce Dynamics 365 Commerce za pomocą Lifecycle Services (usługi LCS) Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="a07b5-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="a07b5-105">Microsoft Dynamics Lifecycle Services (usługi LCS) to oparty na chmurze obszar roboczy, za pomocą którego partnerzy i klienci mogą zarządzać swoimi projektami i środowiskami, wyświetlać najnowsze informacje o produktach i funkcjach Microsoft Dynamics oraz tworzyć, śledzić i przeglądać zdarzenia pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="a07b5-105">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="a07b5-106">Funkcje zarządzania e-Commerce są zintegrowane z usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="a07b5-106">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="a07b5-107">Aby dowiedzieć się więcej o usługi LCS, zobacz [Przewodnik użytkownika usługi Lifecycle Services](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="a07b5-107">To learn more about LCS, see the [Lifecycle Services User Guide](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="a07b5-108">Rozpocznij</span><span class="sxs-lookup"><span data-stu-id="a07b5-108">Get started</span></span>

<span data-ttu-id="a07b5-109">Aby można było zainicjować e-Commerce, należy zainicjować projekt, środowisko i Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="a07b5-109">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="a07b5-110">Aby wykonać inicjalizację w usługi LCS, trzeba mieć uprawnienia do roli Właściciel projektu lub Menedżer środowiska.</span><span class="sxs-lookup"><span data-stu-id="a07b5-110">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="a07b5-111">Topologie środowiska produkcyjnego i piaskownicy są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="a07b5-111">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="a07b5-112">Aby uzyskać więcej informacji o środowiskach, należy zapoznać się z tematem [Planowanie środowiska](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="a07b5-112">For more information about environments, see [Environment planning](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="a07b5-113">Aby uzyskać więcej informacji na temat dzienników RCSU, zobacz temat [Inicjowanie Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="a07b5-113">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="a07b5-114">Inicjalizowanie e-Commerce</span><span class="sxs-lookup"><span data-stu-id="a07b5-114">Initialize e-commerce</span></span>

<span data-ttu-id="a07b5-115">Ta procedura służy do inicjowania funkcji e-Commerce w istniejącym środowisku.</span><span class="sxs-lookup"><span data-stu-id="a07b5-115">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="a07b5-116">Przed rozpoczęciem należy upewnić się, że istnieją następujące wymagane informacje:</span><span class="sxs-lookup"><span data-stu-id="a07b5-116">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="a07b5-117">RCSU, który będzie używany.</span><span class="sxs-lookup"><span data-stu-id="a07b5-117">The RCSU that will be used.</span></span>
- <span data-ttu-id="a07b5-118">Grupa zabezpieczeń Microsoft Azure Active Directory, która będzie używana dla administratorów systemu w e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a07b5-118">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="a07b5-119">Grupa zabezpieczeń Azure Active Directory Microsoft, która będzie używana dla moderatorów ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="a07b5-119">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="a07b5-120">Domeny, które będą skojarzone ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="a07b5-120">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="a07b5-121">Ponadto można zebrać następujące informacje opcjonalne:</span><span class="sxs-lookup"><span data-stu-id="a07b5-121">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="a07b5-122">Azure AD informacje o relacji od firmy do konsumenta (B2C):</span><span class="sxs-lookup"><span data-stu-id="a07b5-122">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="a07b5-123">Nazwa dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="a07b5-123">Tenant Name.</span></span>
    - <span data-ttu-id="a07b5-124">Identyfikator klienta.</span><span class="sxs-lookup"><span data-stu-id="a07b5-124">Client ID.</span></span>
    - <span data-ttu-id="a07b5-125">Niestandardowa domena logowania.</span><span class="sxs-lookup"><span data-stu-id="a07b5-125">Login Custom Domain.</span></span>
    - <span data-ttu-id="a07b5-126">Odpowiedź URL.</span><span class="sxs-lookup"><span data-stu-id="a07b5-126">Reply URL.</span></span>
    - <span data-ttu-id="a07b5-127">Identyfikator zasad logowania i rejestracji.</span><span class="sxs-lookup"><span data-stu-id="a07b5-127">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="a07b5-128">Identyfikator zasad resetowania haseł.</span><span class="sxs-lookup"><span data-stu-id="a07b5-128">Reset password Policy ID.</span></span>
    - <span data-ttu-id="a07b5-129">Edytuj identyfikator zasad profilu.</span><span class="sxs-lookup"><span data-stu-id="a07b5-129">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="a07b5-130">Te informacje można dodać później za pośrednictwem zlecenia usługi.</span><span class="sxs-lookup"><span data-stu-id="a07b5-130">This information can be added later, through a service request.</span></span>

<span data-ttu-id="a07b5-131">Po zebraniu wymaganych informacji należy wykonać poniższe kroki w celu zainicjowania e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a07b5-131">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="a07b5-132">Zaloguj się w [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="a07b5-132">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="a07b5-133">Otwórz projekt zawierający środowisko, w którym chcesz zainicjować e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a07b5-133">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="a07b5-134">W sekcji **środowiska** wybierz środowisko.</span><span class="sxs-lookup"><span data-stu-id="a07b5-134">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="a07b5-135">W obszarze **Funkcje środowiska** wybierz łącze **zarządzanie detaliczne**.</span><span class="sxs-lookup"><span data-stu-id="a07b5-135">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="a07b5-136">Na karcie **e-Commerce** wybierz opcję **ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="a07b5-136">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="a07b5-137">Zostanie wyświetlone okno dialogowe, w którym należy wprowadzić informacje wymagane do zainicjowania obsługi administracyjnej.</span><span class="sxs-lookup"><span data-stu-id="a07b5-137">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="a07b5-138">Wprowadź wymagane informacje, a następnie przejdź do następnej strony.</span><span class="sxs-lookup"><span data-stu-id="a07b5-138">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="a07b5-139">Na następnej stronie wpisz wymagane informacje, a następnie prześlij formularz.</span><span class="sxs-lookup"><span data-stu-id="a07b5-139">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="a07b5-140">Powrócisz na kartę **e-Commerce**, w której powinny być widoczne informacje o uruchomieniu inicjalizacji.</span><span class="sxs-lookup"><span data-stu-id="a07b5-140">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="a07b5-141">Aby wyświetlić stan inicjalizacji, należy **odświeżyć** lub wrócić na kartę **e-Commerce** później.</span><span class="sxs-lookup"><span data-stu-id="a07b5-141">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="a07b5-142">Gdy e-Commerce jest inicjowany z usługi LCS, system Inicjuje obsługę kilku składników wymaganych w e-Commerce i kojarzy je ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="a07b5-142">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="a07b5-143">Po zakończeniu obsługi administracyjnej karta **e-Commerce** na stronie **Zarządzanie Retail** jest aktualizowana w celu uwzględnienia tej zmiany.</span><span class="sxs-lookup"><span data-stu-id="a07b5-143">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="a07b5-144">Na stronie są wyświetlane najnowsze wdrożenia dostosowań oraz stan wszystkich innych trwających wdrożeń.</span><span class="sxs-lookup"><span data-stu-id="a07b5-144">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="a07b5-145">Zawiera także łącza do witryny e-Commerce oraz narzędzia do zarządzania witryną e-Commerce, gdzie tworzone są witryny.</span><span class="sxs-lookup"><span data-stu-id="a07b5-145">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="a07b5-146">Dostęp do konstruktora witryn</span><span class="sxs-lookup"><span data-stu-id="a07b5-146">Access Commerce site builder</span></span>

<span data-ttu-id="a07b5-147">Aby uzyskać dostęp do konstruktora witryn, przejdź na kartę **e-Commerce** na stronie **Zarządzanie Retail** w usłudze LCS i wybierz **narzędzia zarządzania witryny e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="a07b5-147">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="a07b5-148">Strona docelowa konstruktora witryn umożliwia wyświetlenie widoku na poziomie dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="a07b5-148">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="a07b5-149">Z poziomu tej strony można:</span><span class="sxs-lookup"><span data-stu-id="a07b5-149">From this page, you can:</span></span>

- <span data-ttu-id="a07b5-150">Modyfikować ustawienia na poziomie dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="a07b5-150">Modify tenant-level settings.</span></span>
- <span data-ttu-id="a07b5-151">Przechodzić do dowolnych utworzonych witryn i mających uprawnienia do wyświetlania.</span><span class="sxs-lookup"><span data-stu-id="a07b5-151">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="a07b5-152">Uzyskać dostęp do funkcji ocen, takich jak moderowania i reportowania.</span><span class="sxs-lookup"><span data-stu-id="a07b5-152">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="a07b5-153">Stworzyć nową witrynę.</span><span class="sxs-lookup"><span data-stu-id="a07b5-153">Create a new site.</span></span> <span data-ttu-id="a07b5-154">Aby uzyskać więcej informacji dotyczących sposobu tworzenia nowej witryny, zobacz [Tworzenie nowej witryny e-Commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="a07b5-154">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="a07b5-155">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a07b5-155">Additional resources</span></span>

[<span data-ttu-id="a07b5-156">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="a07b5-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="a07b5-157">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="a07b5-157">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="a07b5-158">Kojarzenie witryny Dynamics 365 Commerce z kanałem online</span><span class="sxs-lookup"><span data-stu-id="a07b5-158">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="a07b5-159">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="a07b5-159">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="a07b5-160">Zbiorowe przekazanie przekierowań adresów URL</span><span class="sxs-lookup"><span data-stu-id="a07b5-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="a07b5-161">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="a07b5-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="a07b5-162">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="a07b5-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="a07b5-163">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="a07b5-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="a07b5-164">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="a07b5-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="a07b5-165">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a07b5-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]