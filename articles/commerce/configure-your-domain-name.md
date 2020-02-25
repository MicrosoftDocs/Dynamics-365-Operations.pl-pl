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
ms.openlocfilehash: 4db774783dba4b1cea9552da3cff29a9528bd496
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002181"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="01e1b-103">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="01e1b-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="01e1b-104">W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="01e1b-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="01e1b-105">Dodawanie domen podczas inicjowania usługi e-Commerce</span><span class="sxs-lookup"><span data-stu-id="01e1b-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="01e1b-106">Aby skojarzyć domeny z środowiskiem handlu elektronicznego, należy zainicjować e-Commerce w sposób opisany [w temacie Wdrażanie nowej witryny e-Commerce](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="01e1b-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="01e1b-107">Podczas inicjowania użytkownik jest monitowany o podanie informacji, które będą używane w celu zainicjowania obsługi środowiska e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="01e1b-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="01e1b-108">W polu **Obsługiwane nazwy hostów** dodaj wszystkie domeny, które mają być używane w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="01e1b-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="01e1b-109">Wiele domen należy oddzielić średnikiem.</span><span class="sxs-lookup"><span data-stu-id="01e1b-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="01e1b-110">W ten sposób domeny są konfigurowane we wszystkich wymaganych składnikach e-Commerce i są gotowe do użycia podczas przełączania ruchu z sieci dostarczania zawartości (CDN, Content Delivery Network) lub serwera sieci Web, a następnie na frontony e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="01e1b-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="01e1b-111">Dodawanie domen po inicjowaniu usługi e-Commerce</span><span class="sxs-lookup"><span data-stu-id="01e1b-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="01e1b-112">Aby skojarzyć nowe domeny ze środowiskiem e-Commerce po zainicjowaniu usługi e-Commerce, należy przesłać żądanie obsługi.</span><span class="sxs-lookup"><span data-stu-id="01e1b-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="01e1b-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="01e1b-113">Additional resources</span></span>

[<span data-ttu-id="01e1b-114">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="01e1b-114">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="01e1b-115">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="01e1b-115">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="01e1b-116">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="01e1b-116">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="01e1b-117">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="01e1b-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="01e1b-118">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="01e1b-118">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="01e1b-119">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="01e1b-119">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="01e1b-120">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="01e1b-120">Enable location-based store detection</span></span>](enable-store-detection.md)
