---
title: Tworzenie witryny handlu elektronicznego
description: W tym temacie opisano kroki i informacje wymagane do utworzenia nowej witryny e-Commerce w konstruktorze witryn Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7177bae911dfa91a645b40581bf23b3ed76562a3
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096781"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="36a8e-103">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="36a8e-103">Create an e-Commerce site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="36a8e-104">W tym temacie opisano kroki i informacje wymagane do utworzenia nowej witryny e-Commerce w konstruktorze witryn Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="36a8e-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="36a8e-105">Przed rozpoczęciem opracowywania witryny e-Commerce, najpierw należy utworzyć nową witrynę w kreatorze witryn.</span><span class="sxs-lookup"><span data-stu-id="36a8e-105">Before you can start developing your e-Commerce site, you must first establish a new site in site builder.</span></span> 


<span data-ttu-id="36a8e-106">Aby rozpocząć opracowywanie witryny e-Commerce, najpierw należy utworzyć nową witrynę w środowisku tworzenia witryn.</span><span class="sxs-lookup"><span data-stu-id="36a8e-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="36a8e-107">Aby można było utworzyć nową witrynę, w Commerce musi być utworzony co najmniej jeden sklep internetowy.</span><span class="sxs-lookup"><span data-stu-id="36a8e-107">Before you can create a new site, at least one online store must be created in Commerce.</span></span> 


## <a name="set-up-your-site"></a><span data-ttu-id="36a8e-108">Konfigurowanie witryny</span><span class="sxs-lookup"><span data-stu-id="36a8e-108">Set up your site</span></span>

<span data-ttu-id="36a8e-109">Aby skonfigurować witrynę, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="36a8e-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="36a8e-110">Otwórz środowisko budowania witryn.</span><span class="sxs-lookup"><span data-stu-id="36a8e-110">Open the site builder environment.</span></span> <span data-ttu-id="36a8e-111">Łącze do kreatora witryn w usłudze Microsoft Lifecycle Services (LCS) można znaleźć na stronie Funkcje środowiska w Commerce.</span><span class="sxs-lookup"><span data-stu-id="36a8e-111">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="36a8e-112">Następnie na stronie głównej dla środowiska tworzenia witryn wybierz opcję **Nowa witryna**.</span><span class="sxs-lookup"><span data-stu-id="36a8e-112">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="36a8e-113">W oknie dialogowym **Nowa witryna** wprowadź następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="36a8e-113">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="36a8e-114">Pole</span><span class="sxs-lookup"><span data-stu-id="36a8e-114">Field</span></span>                               | <span data-ttu-id="36a8e-115">Opis</span><span class="sxs-lookup"><span data-stu-id="36a8e-115">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="36a8e-116">Nazwa witryny</span><span class="sxs-lookup"><span data-stu-id="36a8e-116">Site name</span></span>                           | <span data-ttu-id="36a8e-117">Umożliwia wprowadzenie nazwy wyświetlanej, która powinna być używana w odniesieniu do danej witryny w środowisku tworzenia witryn.</span><span class="sxs-lookup"><span data-stu-id="36a8e-117">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="36a8e-118">Ta nazwa jest widoczna tylko w środowisku autorskim i nie będzie wyświetlana klientom.</span><span class="sxs-lookup"><span data-stu-id="36a8e-118">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="36a8e-119">Grupa zabezpieczeń administratora witryny</span><span class="sxs-lookup"><span data-stu-id="36a8e-119">Site administrator's security group</span></span> | <span data-ttu-id="36a8e-120">Określ grupę zabezpieczeń Microsoft Azure Active Directory (Azure AD), która zarządza użytkownikami dysponującymi rolą administratora witryny w tej witrynie.</span><span class="sxs-lookup"><span data-stu-id="36a8e-120">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="36a8e-121">Kanał domyślny (numer jednostki operacyjnej)</span><span class="sxs-lookup"><span data-stu-id="36a8e-121">Default channel (operating unit number)</span></span> | <span data-ttu-id="36a8e-122">Wybierz sklep internetowy, który będzie pełnić tę witrynę jako sklep sieci Web.</span><span class="sxs-lookup"><span data-stu-id="36a8e-122">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="36a8e-123">Jeśli chcesz, aby witryna e-Commerce obsługiwała wiele sklepów internetowych, musisz skojarzyć te sklepy z serwisem w **Ustawieniach witryny** po skonfigurowaniu witryny.</span><span class="sxs-lookup"><span data-stu-id="36a8e-123">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="36a8e-124">Język domyślny</span><span class="sxs-lookup"><span data-stu-id="36a8e-124">Default language</span></span>                            | <span data-ttu-id="36a8e-125">Umożliwia określenie domyślnego języka dla tego sklepu i rynku online.</span><span class="sxs-lookup"><span data-stu-id="36a8e-125">Specify the default language for this online store and market.</span></span> <span data-ttu-id="36a8e-126">Sklep internetowy może obsługiwać wiele języków.</span><span class="sxs-lookup"><span data-stu-id="36a8e-126">An online store can support multiple languages.</span></span> <span data-ttu-id="36a8e-127">Jeśli chcesz obsługiwać wiele języków dla tego sklepu internetowego lub innego sklepu internetowego, możesz skonfigurować tę obsługę w **Ustawieniach witryny** po skonfigurowaniu witryny.</span><span class="sxs-lookup"><span data-stu-id="36a8e-127">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="36a8e-128">Domena</span><span class="sxs-lookup"><span data-stu-id="36a8e-128">Domain</span></span>                              | <span data-ttu-id="36a8e-129">Wybierz nazwę domeny, która będzie służyć jako domena dla tego sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="36a8e-129">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="36a8e-130">Jeśli nie skonfigurowano żadnych domen w usłudze LCS, to pole można pozostawić puste.</span><span class="sxs-lookup"><span data-stu-id="36a8e-130">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="36a8e-131">Po skonfigurowaniu domeny w usługi LCS, należy ją dodać do swojego sklepu internetowego w **Ustawieniach witryny**.</span><span class="sxs-lookup"><span data-stu-id="36a8e-131">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="36a8e-132">Ścieżka</span><span class="sxs-lookup"><span data-stu-id="36a8e-132">Path</span></span>                              | <span data-ttu-id="36a8e-133">Jeśli witryna obsługuje więcej niż jeden język dla danej nazwy domeny, użyj pola ścieżki, aby utworzyć unikalny adres URL witryny dla tej kombinacji domeny i języka.</span><span class="sxs-lookup"><span data-stu-id="36a8e-133">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="36a8e-134">Jeśli język określony w polu **Język domyślny** jest jedynym językiem, który będzie obsługiwany dla tej domeny, lub będzie używany domyślny język po zlokalizowaniu witryny w dodatkowych językach, zaleca się pozostawienie tego pola pustego.</span><span class="sxs-lookup"><span data-stu-id="36a8e-134">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="36a8e-135">Po utworzeniu witryny można sprawdzić, czy jest skojarzona ze swoim sklepem internetowym, wybierając kartę **Produkty**. Powinien być widoczny asortyment produktów, które zostały przypisane do sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="36a8e-135">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="36a8e-136">Możesz także użyć menu rozwijanego w lewym górnym rogu strony, aby uzyskać dostęp do przydzielonych produktów według kategorii.</span><span class="sxs-lookup"><span data-stu-id="36a8e-136">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="36a8e-137">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="36a8e-137">Additional resources</span></span>

[<span data-ttu-id="36a8e-138">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="36a8e-138">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="36a8e-139">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="36a8e-139">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="36a8e-140">Konfigurowanie kanału sklepu internetowego</span><span class="sxs-lookup"><span data-stu-id="36a8e-140">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="36a8e-141">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="36a8e-141">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="36a8e-142">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="36a8e-142">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="36a8e-143">Przekaż adresy URL przekierowań luzem</span><span class="sxs-lookup"><span data-stu-id="36a8e-143">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="36a8e-144">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="36a8e-144">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="36a8e-145">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="36a8e-145">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="36a8e-146">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="36a8e-146">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="36a8e-147">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="36a8e-147">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="36a8e-148">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="36a8e-148">Enable location-based store detection</span></span>](enable-store-detection.md)
