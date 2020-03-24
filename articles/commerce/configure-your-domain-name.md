---
title: Konfigurowanie nazwy domeny
description: W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym.
author: psimolin
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
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2ad9ca3aee21301ef6d830d7b29982a45cd53f60
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096827"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="96030-103">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="96030-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="96030-104">W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="96030-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="96030-105">Dodawanie domen podczas inicjowania usługi e-Commerce</span><span class="sxs-lookup"><span data-stu-id="96030-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="96030-106">Aby skojarzyć domeny z środowiskiem handlu elektronicznego, należy zainicjować e-Commerce w sposób opisany [w temacie Wdrażanie nowej witryny e-Commerce](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="96030-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="96030-107">Podczas inicjowania użytkownik jest monitowany o podanie informacji, które będą używane w celu zainicjowania obsługi środowiska e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="96030-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="96030-108">W polu **Obsługiwane nazwy hostów** dodaj wszystkie domeny, które mają być używane w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="96030-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="96030-109">Wiele domen należy oddzielić średnikiem.</span><span class="sxs-lookup"><span data-stu-id="96030-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="96030-110">W ten sposób domeny są konfigurowane we wszystkich wymaganych składnikach e-Commerce i są gotowe do użycia podczas przełączania ruchu z sieci dostarczania zawartości (CDN, Content Delivery Network) lub serwera sieci Web, a następnie na frontony e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="96030-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="96030-111">Dodawanie domen po inicjowaniu usługi e-Commerce</span><span class="sxs-lookup"><span data-stu-id="96030-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="96030-112">Aby skojarzyć nowe domeny ze środowiskiem e-Commerce po zainicjowaniu usługi e-Commerce, należy przesłać żądanie obsługi.</span><span class="sxs-lookup"><span data-stu-id="96030-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="96030-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="96030-113">Additional resources</span></span>

[<span data-ttu-id="96030-114">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="96030-114">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="96030-115">Konfigurowanie kanału sklepu internetowego</span><span class="sxs-lookup"><span data-stu-id="96030-115">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="96030-116">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="96030-116">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="96030-117">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="96030-117">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="96030-118">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="96030-118">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="96030-119">Przekaż adresy URL przekierowań luzem</span><span class="sxs-lookup"><span data-stu-id="96030-119">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="96030-120">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="96030-120">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="96030-121">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="96030-121">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="96030-122">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="96030-122">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="96030-123">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="96030-123">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="96030-124">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="96030-124">Enable location-based store detection</span></span>](enable-store-detection.md)
