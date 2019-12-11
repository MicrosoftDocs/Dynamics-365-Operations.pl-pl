---
title: Kojarzenie witryny e-Commerce z kanałem online
description: W tym temacie opisano sposób powiązania witryny firmy Microsoft Dynamics 365 Commerce z co najmniej jednym sklepem internetowym.
author: stuharg
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: bicyclingfool
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e0fad51fcb092c95103356f17618a647dd166b95
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697370"
---
# <a name="associate-an-e-commerce-site-with-an-online-channel"></a><span data-ttu-id="1f26e-103">Kojarzenie witryny e-Commerce z kanałem online</span><span class="sxs-lookup"><span data-stu-id="1f26e-103">Associate an e-Commerce site with an online channel</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="1f26e-104">W tym temacie opisano sposób powiązania witryny firmy Microsoft Dynamics 365 Commerce z co najmniej jednym sklepem internetowym.</span><span class="sxs-lookup"><span data-stu-id="1f26e-104">This topic explains how to bind your Microsoft Dynamics 365 Commerce site to one or more online stores.</span></span> 

<span data-ttu-id="1f26e-105">Po zainicjowaniu obsługi handlu elektronicznego za pomocą portalu Microsoft Dynamics Lifecycle Services (usługi LCS) można przystąpić do utworzenia pierwszej witryny e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="1f26e-105">After you've provisioned e-Commerce by using the Microsoft Dynamics Lifecycle Services (LCS) portal, you're ready to establish your first e-Commerce website.</span></span> <span data-ttu-id="1f26e-106">W ramach początkowego tworzenia witryny skojarz witrynę z wcześniej utworzonym sklepem internetowym.</span><span class="sxs-lookup"><span data-stu-id="1f26e-106">As part of the initial site creation, you associate the site with an online store that was previously created.</span></span> <span data-ttu-id="1f26e-107">Ten krok wiąże witrynę ze kanałem online i umożliwia wyświetlanie w witrynie hierarchii nawigacji, produktów, kategorii, cen, opcji wysyłki i wszystkich innych zdefiniowanych w sklepie internetowym.</span><span class="sxs-lookup"><span data-stu-id="1f26e-107">This step binds the site to an online channel and lets the site show the navigation hierarchy, products, categories, prices, shipping options, and everything else that you defined in the online store.</span></span>

<span data-ttu-id="1f26e-108">Aby utworzyć nową witrynę i skojarzyć z nią sklep internetowy, w usługi LCS wybierz łącze do środowiska tworzenia witryn.</span><span class="sxs-lookup"><span data-stu-id="1f26e-108">To establish a new site and associate an online store with it, in LCS, select the link for the site authoring environment.</span></span> <span data-ttu-id="1f26e-109">Następnie na stronie dla środowiska tworzenia witryn wybierz opcję **Nowa witryna**.</span><span class="sxs-lookup"><span data-stu-id="1f26e-109">Then, on the page for the site authoring environment, select **New site**.</span></span> <span data-ttu-id="1f26e-110">W oknie dialogowym **Nowa witryna** należy podać podstawowe informacje o witrynie.</span><span class="sxs-lookup"><span data-stu-id="1f26e-110">In the **New site** dialog box, you must provide some basic information about your site.</span></span> <span data-ttu-id="1f26e-111">Aby zapoznać się z kompletnymi informacjami na temat, które należy podać, zawiera sekcja [Tworzenie nowej witryny e-Commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="1f26e-111">For a complete explanation of the information that you must provide, see [Create a new e-Commerce site](create-ecommerce-site.md).</span></span>

<span data-ttu-id="1f26e-112">Po utworzeniu witryny można sprawdzić, czy jest skojarzona ze swoim sklepem internetowym, wybierając kartę **produkty.** Powinien być widoczny asortyment produktów, które zostały przypisane do sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="1f26e-112">After your site is created, you can verify that it's associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="1f26e-113">Aby uzyskać dostęp do produktów według kategorii, można również skorzystać z pola rozwijanego znajdującego się w lewej górnej części strony.</span><span class="sxs-lookup"><span data-stu-id="1f26e-113">You can also use the drop-down field in the upper left of the page to access the products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1f26e-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1f26e-114">Additional resources</span></span>

[<span data-ttu-id="1f26e-115">Omówienie sklepu internetowego</span><span class="sxs-lookup"><span data-stu-id="1f26e-115">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="1f26e-116">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="1f26e-116">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="1f26e-117">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="1f26e-117">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="1f26e-118">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="1f26e-118">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="1f26e-119">Dodaj obsługę dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="1f26e-119">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="1f26e-120">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1f26e-120">Enable location-based store detection</span></span>](enable-store-detection.md)

[<span data-ttu-id="1f26e-121">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="1f26e-121">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
