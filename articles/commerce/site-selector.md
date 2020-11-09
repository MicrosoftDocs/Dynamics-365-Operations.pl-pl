---
title: Moduł wyboru witryny
description: W tym temacie opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: bd54695f54b501631f916328c05bfd47e538d50d
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055837"
---
# <a name="site-selector-module"></a><span data-ttu-id="9604c-103">Moduł wyboru witryny</span><span class="sxs-lookup"><span data-stu-id="9604c-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="9604c-104">W tym temacie opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9604c-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9604c-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="9604c-105">Overview</span></span>

<span data-ttu-id="9604c-106">Jeśli firma ma różne oddziały między rynkami, regionami i lokalizacjami, użytkownicy witryny muszą w prosty sposób przełączać się między witrynami i wybierać ich preferowaną witrynę w zakresie zakupów.</span><span class="sxs-lookup"><span data-stu-id="9604c-106">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="9604c-107">Aby można było uwzględnić ten scenariusz, moduł selektor witryn umożliwia przeglądanie użytkowników w wielu witrynach.</span><span class="sxs-lookup"><span data-stu-id="9604c-107">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="9604c-108">Dla modułu wyboru witryn należy skonfigurować listę witryn (rynków, regionów lub ustawień regionalnych), które użytkownicy witryny mogą przeglądać.</span><span class="sxs-lookup"><span data-stu-id="9604c-108">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="9604c-109">Moduł wyboru witryny do stron nadrzędnych jest dostępny w wydaniu Dynamics 365 Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="9604c-109">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="9604c-110">Na poniższej ilustracji przedstawiono przykład modułu wyboru witryny, który jest proponowany w nagłówku strony witryny.</span><span class="sxs-lookup"><span data-stu-id="9604c-110">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Przykład modułu wyboru witryn w nagłówku strony witryny](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="9604c-112">Właściwości Modułu wyboru witryny</span><span class="sxs-lookup"><span data-stu-id="9604c-112">Site selector module properties</span></span>

| <span data-ttu-id="9604c-113">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="9604c-113">Property name</span></span> | <span data-ttu-id="9604c-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="9604c-114">Value</span></span>                 | <span data-ttu-id="9604c-115">opis</span><span class="sxs-lookup"><span data-stu-id="9604c-115">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="9604c-116">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="9604c-116">Heading</span></span>       | <span data-ttu-id="9604c-117">Tekst</span><span class="sxs-lookup"><span data-stu-id="9604c-117">Text</span></span>                  | <span data-ttu-id="9604c-118">Nagłówek modułu.</span><span class="sxs-lookup"><span data-stu-id="9604c-118">The heading for the module.</span></span> |
| <span data-ttu-id="9604c-119">Opcje witryny</span><span class="sxs-lookup"><span data-stu-id="9604c-119">Site options</span></span>  | <span data-ttu-id="9604c-120">Nazwa, obraz, adres URL</span><span class="sxs-lookup"><span data-stu-id="9604c-120">Name, Image, URL</span></span>      | <span data-ttu-id="9604c-121">Ta właściwość określa nazwę, łącze do strony głównej witryny oraz opcjonalny obraz, który ma być wyświetlany dla każdej witryny uwzględnionej w module.</span><span class="sxs-lookup"><span data-stu-id="9604c-121">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="9604c-122">Obraz może być flagą lub pewną reprezentacją rynku, regionu lub ustawień regionalnych.</span><span class="sxs-lookup"><span data-stu-id="9604c-122">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="9604c-123">Dodawanie modułu wyboru witryny do nowej strony</span><span class="sxs-lookup"><span data-stu-id="9604c-123">Add a site selector module to a page</span></span>

<span data-ttu-id="9604c-124">Moduł selektor witryn można dodać do [modułu nagłówka](author-header-module.md) w ramach gniazda selektora witryn.</span><span class="sxs-lookup"><span data-stu-id="9604c-124">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="9604c-125">Po dodaniu możesz zdefiniować nagłówek modułu i opcje witryny.</span><span class="sxs-lookup"><span data-stu-id="9604c-125">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9604c-126">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9604c-126">Additional resources</span></span>

[<span data-ttu-id="9604c-127">Przegląd biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="9604c-127">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9604c-128">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="9604c-128">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="9604c-129">Moduł szlaków nawigacyjnych</span><span class="sxs-lookup"><span data-stu-id="9604c-129">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="9604c-130">Moduł menu nawigacji</span><span class="sxs-lookup"><span data-stu-id="9604c-130">Navigation menu module</span></span>](nav-menu-module.md)
