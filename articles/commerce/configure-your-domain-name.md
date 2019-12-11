---
title: Konfigurowanie nazwy domeny
description: W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
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
ms.openlocfilehash: 7a988f533757cc3f8555fcf4fb724a22a5b014f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770465"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="e98f3-103">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="e98f3-103">Configure your domain name</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e98f3-104">W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="e98f3-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="e98f3-105">Dodawanie domen podczas inicjowania usługi e-Commerce</span><span class="sxs-lookup"><span data-stu-id="e98f3-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="e98f3-106">Aby skojarzyć domeny z środowiskiem handlu elektronicznego, należy zainicjować e-Commerce w sposób opisany [w temacie Wdrażanie nowej witryny e-Commerce](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="e98f3-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="e98f3-107">Podczas inicjowania użytkownik jest monitowany o podanie informacji, które będą używane w celu zainicjowania obsługi środowiska e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="e98f3-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="e98f3-108">W polu **Obsługiwane nazwy hostów** dodaj wszystkie domeny, które mają być używane w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="e98f3-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="e98f3-109">Wiele domen należy oddzielić średnikiem.</span><span class="sxs-lookup"><span data-stu-id="e98f3-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="e98f3-110">W ten sposób domeny są konfigurowane we wszystkich wymaganych składnikach e-Commerce i są gotowe do użycia podczas przełączania ruchu z sieci dostarczania zawartości (CDN, Content Delivery Network) lub serwera sieci Web, a następnie na frontony e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="e98f3-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="e98f3-111">Dodawanie domen po inicjowaniu usługi e-Commerce</span><span class="sxs-lookup"><span data-stu-id="e98f3-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="e98f3-112">Aby skojarzyć nowe domeny ze środowiskiem e-Commerce po zainicjowaniu usługi e-Commerce, należy przesłać żądanie obsługi.</span><span class="sxs-lookup"><span data-stu-id="e98f3-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e98f3-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e98f3-113">Additional resources</span></span>

[<span data-ttu-id="e98f3-114">Omówienie sklepu internetowego</span><span class="sxs-lookup"><span data-stu-id="e98f3-114">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="e98f3-115">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="e98f3-115">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="e98f3-116">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="e98f3-116">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="e98f3-117">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="e98f3-117">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="e98f3-118">Dodaj obsługę dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="e98f3-118">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="e98f3-119">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="e98f3-119">Enable location-based store detection</span></span>](enable-store-detection.md)

[<span data-ttu-id="e98f3-120">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="e98f3-120">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
