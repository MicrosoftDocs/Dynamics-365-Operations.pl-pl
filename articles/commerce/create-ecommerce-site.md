---
title: Tworzenie witryny handlu elektronicznego
description: W tym temacie opisano kroki i informacje wymagane do utworzenia nowej witryny e-Commerce w konstruktorze witryn Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
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
ms.openlocfilehash: ea3517a4f2b84db8a87a97d2f644bb4436f8693f
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533443"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="07891-103">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="07891-103">Create an e-Commerce site</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="07891-104">W tym temacie opisano kroki i informacje wymagane do utworzenia nowej witryny e-Commerce w konstruktorze witryn Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="07891-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="07891-105">Po nadaniu licencji na funkcje handlu elektronicznego, funkcja konstruktora witryn zostanie wdrożona wraz z witryną startową, którą można wykorzystać jako podstawę dla własnego oddziału.</span><span class="sxs-lookup"><span data-stu-id="07891-105">When you license the e-Commerce capabilities, site builder will be provisioned with a starter site that you can use as a basis for your own site.</span></span> <span data-ttu-id="07891-106">Jeśli jednak użytkownik chce rozpocząć od zera lub chce stworzyć drugą witrynę, musi utworzyć nową witrynę w środowisku tworzenia witryn.</span><span class="sxs-lookup"><span data-stu-id="07891-106">However, if you want to start from scratch or if you want to establish a second site, you will need to establish a new site in the site authoring environment.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="07891-107">Konfigurowanie witryny</span><span class="sxs-lookup"><span data-stu-id="07891-107">Set up your site</span></span>

<span data-ttu-id="07891-108">Aby skonfigurować witrynę, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="07891-108">To set up your site, do the following.</span></span>

1. <span data-ttu-id="07891-109">Otwórz środowisko budowania witryn.</span><span class="sxs-lookup"><span data-stu-id="07891-109">Open the site builder environment.</span></span> <span data-ttu-id="07891-110">Łącze do kreatora witryn w usłudze Microsoft Lifecycle Services (LCS) można znaleźć na stronie Funkcje środowiska w Commerce.</span><span class="sxs-lookup"><span data-stu-id="07891-110">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="07891-111">Następnie na stronie głównej dla środowiska tworzenia witryn wybierz opcję **Nowa witryna**.</span><span class="sxs-lookup"><span data-stu-id="07891-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="07891-112">W oknie dialogowym **Nowa witryna** wprowadź następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="07891-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="07891-113">Pole</span><span class="sxs-lookup"><span data-stu-id="07891-113">Field</span></span>                               | <span data-ttu-id="07891-114">Opis</span><span class="sxs-lookup"><span data-stu-id="07891-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="07891-115">Nazwa witryny</span><span class="sxs-lookup"><span data-stu-id="07891-115">Site name</span></span>                           | <span data-ttu-id="07891-116">Umożliwia wprowadzenie nazwy wyświetlanej, która powinna być używana w odniesieniu do danej witryny w środowisku tworzenia witryn.</span><span class="sxs-lookup"><span data-stu-id="07891-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="07891-117">Ta nazwa jest widoczna tylko w środowisku autorskim i nie będzie wyświetlana klientom.</span><span class="sxs-lookup"><span data-stu-id="07891-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="07891-118">Grupa zabezpieczeń administratora witryny</span><span class="sxs-lookup"><span data-stu-id="07891-118">Site administrator's security group</span></span> | <span data-ttu-id="07891-119">Określ grupę zabezpieczeń Microsoft Azure Active Directory (Azure AD), która zarządza użytkownikami dysponującymi rolą administratora witryny w tej witrynie.</span><span class="sxs-lookup"><span data-stu-id="07891-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="07891-120">Kanał domyślny (numer jednostki operacyjnej)</span><span class="sxs-lookup"><span data-stu-id="07891-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="07891-121">Wybierz sklep internetowy, który będzie pełnić tę witrynę jako sklep sieci Web.</span><span class="sxs-lookup"><span data-stu-id="07891-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="07891-122">Jeśli chcesz, aby witryna e-Commerce obsługiwała wiele sklepów internetowych, musisz skojarzyć te sklepy z serwisem w **Ustawieniach witryny** po skonfigurowaniu witryny.</span><span class="sxs-lookup"><span data-stu-id="07891-122">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="07891-123">Język domyślny</span><span class="sxs-lookup"><span data-stu-id="07891-123">Default language</span></span>                            | <span data-ttu-id="07891-124">Umożliwia określenie domyślnego języka dla tego sklepu i rynku online.</span><span class="sxs-lookup"><span data-stu-id="07891-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="07891-125">Sklep internetowy może obsługiwać wiele języków.</span><span class="sxs-lookup"><span data-stu-id="07891-125">An online store can support multiple languages.</span></span> <span data-ttu-id="07891-126">Jeśli chcesz obsługiwać wiele języków dla tego sklepu internetowego lub innego sklepu internetowego, możesz skonfigurować tę obsługę w **Ustawieniach witryny** po skonfigurowaniu witryny.</span><span class="sxs-lookup"><span data-stu-id="07891-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="07891-127">Domena</span><span class="sxs-lookup"><span data-stu-id="07891-127">Domain</span></span>                              | <span data-ttu-id="07891-128">Wybierz nazwę domeny, która będzie służyć jako domena dla tego sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="07891-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="07891-129">Jeśli nie skonfigurowano żadnych domen w usłudze LCS, to pole można pozostawić puste.</span><span class="sxs-lookup"><span data-stu-id="07891-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="07891-130">Po skonfigurowaniu domeny w usługi LCS, należy ją dodać do swojego sklepu internetowego w **Ustawieniach witryny**.</span><span class="sxs-lookup"><span data-stu-id="07891-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="07891-131">Ścieżka</span><span class="sxs-lookup"><span data-stu-id="07891-131">Path</span></span>                              | <span data-ttu-id="07891-132">Jeśli witryna obsługuje więcej niż jeden język dla danej nazwy domeny, użyj pola ścieżki, aby utworzyć unikalny adres URL witryny dla tej kombinacji domeny i języka.</span><span class="sxs-lookup"><span data-stu-id="07891-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="07891-133">Jeśli język określony w polu **Język domyślny** jest jedynym językiem, który będzie obsługiwany dla tej domeny, lub będzie używany domyślny język po zlokalizowaniu witryny w dodatkowych językach, zaleca się pozostawienie tego pola pustego.</span><span class="sxs-lookup"><span data-stu-id="07891-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="07891-134">Po utworzeniu witryny można sprawdzić, czy jest skojarzona ze swoim sklepem internetowym, wybierając kartę **Produkty**. Powinien być widoczny asortyment produktów, które zostały przypisane do sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="07891-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="07891-135">Możesz także użyć menu rozwijanego w lewym górnym rogu strony, aby uzyskać dostęp do przydzielonych produktów według kategorii.</span><span class="sxs-lookup"><span data-stu-id="07891-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="07891-136">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="07891-136">Additional resources</span></span>

[<span data-ttu-id="07891-137">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="07891-137">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="07891-138">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="07891-138">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="07891-139">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="07891-139">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="07891-140">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="07891-140">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="07891-141">Przekaż adresy URL przekierowań luzem</span><span class="sxs-lookup"><span data-stu-id="07891-141">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="07891-142">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="07891-142">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="07891-143">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="07891-143">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="07891-144">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="07891-144">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="07891-145">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="07891-145">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="07891-146">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="07891-146">Enable location-based store detection</span></span>](enable-store-detection.md)
