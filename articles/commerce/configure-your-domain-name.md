---
title: Konfigurowanie nazwy domeny
description: W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym.
author: psimolin
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
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ac1b0c8baaddd6ca62cc49657fff364df21c14f2
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517136"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="6091d-103">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="6091d-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6091d-104">W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="6091d-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="6091d-105">Dodawanie domen podczas inicjowania usługi e-Commerce</span><span class="sxs-lookup"><span data-stu-id="6091d-105">Add domains during e-commerce initialization</span></span>

<span data-ttu-id="6091d-106">Aby skojarzyć domeny z środowiskiem handlu elektronicznego Dynamics 365 Commerce, należy zainicjować e-Commerce w sposób opisany w temacie [Wdrażanie nowej witryny e-Commerce](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="6091d-106">To associate domains with your Dynamics 365 Commerce e-commerce environment, initialize e-commerce as described in [Deploy a new e-commerce tenant](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="6091d-107">Podczas inicjowania użytkownik jest monitowany o podanie informacji, które będą używane w celu zainicjowania obsługi środowiska e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="6091d-107">During initialization, you're asked to provide information that will be used to provision your e-commerce environment.</span></span> <span data-ttu-id="6091d-108">W polu **Obsługiwane nazwy hostów** dodaj wszystkie domeny, które mają być używane w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="6091d-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="6091d-109">Wiele domen należy oddzielić średnikiem.</span><span class="sxs-lookup"><span data-stu-id="6091d-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="6091d-110">W ten sposób domeny są konfigurowane we wszystkich wymaganych składnikach e-Commerce i są gotowe do użycia podczas przełączania ruchu z sieci dostarczania zawartości (CDN, Content Delivery Network) lub serwera sieci Web, a następnie na frontony e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="6091d-110">In this way, the domains are configured in all the required Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="6091d-111">Dodawanie domen po inicjowaniu usługi e-Commerce</span><span class="sxs-lookup"><span data-stu-id="6091d-111">Add domains after e-commerce initialization</span></span>

<span data-ttu-id="6091d-112">Aby skojarzyć nowe domeny ze środowiskiem e-Commerce po zainicjowaniu usługi e-Commerce, należy przesłać żądanie obsługi.</span><span class="sxs-lookup"><span data-stu-id="6091d-112">To associate new domains with your e-commerce environment after e-commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6091d-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6091d-113">Additional resources</span></span>

[<span data-ttu-id="6091d-114">Wdrażanie nowej dzierżawy handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="6091d-114">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="6091d-115">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="6091d-115">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="6091d-116">Kojarzenie witryny Dynamics 365 Commerce z kanałem online</span><span class="sxs-lookup"><span data-stu-id="6091d-116">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="6091d-117">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="6091d-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="6091d-118">Zbiorowe przekazanie przekierowań adresów URL</span><span class="sxs-lookup"><span data-stu-id="6091d-118">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="6091d-119">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="6091d-119">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="6091d-120">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="6091d-120">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="6091d-121">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="6091d-121">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="6091d-122">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="6091d-122">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="6091d-123">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="6091d-123">Enable location-based store detection</span></span>](enable-store-detection.md)
