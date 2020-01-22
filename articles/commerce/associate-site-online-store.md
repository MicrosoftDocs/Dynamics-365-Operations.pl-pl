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
ms.openlocfilehash: 62d3c168967bd680b3ded56e627730324f2a5ec6
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945589"
---
# <a name="associate-an-e-commerce-site-with-an-online-channel"></a><span data-ttu-id="c0d09-103">Kojarzenie witryny e-Commerce z kanałem online</span><span class="sxs-lookup"><span data-stu-id="c0d09-103">Associate an e-Commerce site with an online channel</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="c0d09-104">W tym temacie opisano sposób powiązania witryny firmy Microsoft Dynamics 365 Commerce z co najmniej jednym sklepem internetowym.</span><span class="sxs-lookup"><span data-stu-id="c0d09-104">This topic explains how to bind your Microsoft Dynamics 365 Commerce site to one or more online stores.</span></span> 

<span data-ttu-id="c0d09-105">Po zainicjowaniu obsługi handlu elektronicznego za pomocą portalu Microsoft Dynamics Lifecycle Services (usługi LCS) można przystąpić do utworzenia pierwszej witryny e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0d09-105">After you've provisioned e-Commerce by using the Microsoft Dynamics Lifecycle Services (LCS) portal, you're ready to establish your first e-Commerce website.</span></span> <span data-ttu-id="c0d09-106">W ramach początkowego tworzenia witryny skojarz witrynę z wcześniej utworzonym sklepem internetowym.</span><span class="sxs-lookup"><span data-stu-id="c0d09-106">As part of the initial site creation, you associate the site with an online store that was previously created.</span></span> <span data-ttu-id="c0d09-107">Ten krok wiąże witrynę ze kanałem online i umożliwia wyświetlanie w witrynie hierarchii nawigacji, produktów, kategorii, cen, opcji wysyłki i wszystkich innych zdefiniowanych w sklepie internetowym.</span><span class="sxs-lookup"><span data-stu-id="c0d09-107">This step binds the site to an online channel and lets the site show the navigation hierarchy, products, categories, prices, shipping options, and everything else that you defined in the online store.</span></span>

<span data-ttu-id="c0d09-108">Aby utworzyć nową witrynę i skojarzyć z nią sklep internetowy, w usługi LCS wybierz łącze do środowiska tworzenia witryn.</span><span class="sxs-lookup"><span data-stu-id="c0d09-108">To establish a new site and associate an online store with it, in LCS, select the link for the site authoring environment.</span></span> <span data-ttu-id="c0d09-109">Następnie na stronie dla środowiska tworzenia witryn wybierz opcję **Nowa witryna**.</span><span class="sxs-lookup"><span data-stu-id="c0d09-109">Then, on the page for the site authoring environment, select **New site**.</span></span> <span data-ttu-id="c0d09-110">W oknie dialogowym **Nowa witryna** należy podać podstawowe informacje o witrynie.</span><span class="sxs-lookup"><span data-stu-id="c0d09-110">In the **New site** dialog box, you must provide some basic information about your site.</span></span> <span data-ttu-id="c0d09-111">Aby zapoznać się z kompletnymi informacjami na temat, które należy podać, zawiera sekcja [Tworzenie nowej witryny e-Commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="c0d09-111">For a complete explanation of the information that you must provide, see [Create a new e-Commerce site](create-ecommerce-site.md).</span></span>

<span data-ttu-id="c0d09-112">Po utworzeniu witryny można sprawdzić, czy jest skojarzona ze swoim sklepem internetowym, wybierając kartę **produkty.** Powinien być widoczny asortyment produktów, które zostały przypisane do sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="c0d09-112">After your site is created, you can verify that it's associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="c0d09-113">Aby uzyskać dostęp do produktów według kategorii, można również skorzystać z pola rozwijanego znajdującego się w lewej górnej części strony.</span><span class="sxs-lookup"><span data-stu-id="c0d09-113">You can also use the drop-down field in the upper left of the page to access the products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c0d09-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c0d09-114">Additional resources</span></span>

[<span data-ttu-id="c0d09-115">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="c0d09-115">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="c0d09-116">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="c0d09-116">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="c0d09-117">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="c0d09-117">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="c0d09-118">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="c0d09-118">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="c0d09-119">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="c0d09-119">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="c0d09-120">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="c0d09-120">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="c0d09-121">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="c0d09-121">Enable location-based store detection</span></span>](enable-store-detection.md)
