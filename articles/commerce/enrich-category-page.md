---
title: Wzbogacanie strony docelowej kategorii
description: W tym temacie opisano wzbogacanie stron kategorii w Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8d735b215132b90ca786d6967589496bee73f4d9
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697596"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="78715-103">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="78715-103">Enrich a category landing page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="78715-104">W tym temacie opisano wzbogacanie stron kategorii w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="78715-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="78715-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="78715-105">Overview</span></span>

<span data-ttu-id="78715-106">W handlu jest dostępna domyślna strona początkowa kategorii używana podczas wyświetlania danych kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-106">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="78715-107">Domyślna strona kategorii zawiera wymagane elementy, takie jak rafinerie, skategoryzowane lokowanie produktu, opcje sortowania, podsumowanie wyboru i elementy sterujące stronicowaniem.</span><span class="sxs-lookup"><span data-stu-id="78715-107">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="78715-108">Jednak zamiast korzystania z domyślnej strony kategorii można użyć strony docelowej kategorii „wzbogacone”, która ma więcej zawartości i bardziej konkretne elementy.</span><span class="sxs-lookup"><span data-stu-id="78715-108">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="78715-109">Typowe wzbogacenie może obejmować dodawanie treści marketingowych specyficznych dla kategorii do strony kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-109">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="78715-110">Ta zawartość może zawierać rozmieszczenie produktów z różnych kategorii dla celów sprzedaży krzyżowej, list redakcyjnych, obrazów, filmów wideo i innego tekstu.</span><span class="sxs-lookup"><span data-stu-id="78715-110">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="78715-111">Można zmodyfikować domyślną stronę kategorii lub zdefiniować inną stronę kategorii dla danej kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-111">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Wzbogacona strona docelowa kategorii](./media/CategoryLandingPages.png)

<span data-ttu-id="78715-113">Strona **Produkt** w narzędziu autorskim zawiera listę kategorii z kanału przypisanych do oddziału.</span><span class="sxs-lookup"><span data-stu-id="78715-113">In the authoring tool, the **Product** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="78715-114">Jeśli **Wzbogacone** stan jest zaznaczony dla strony kategorii, dana strona kategorii została wzbogacona.</span><span class="sxs-lookup"><span data-stu-id="78715-114">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="78715-115">W przeciwnym razie używana jest domyślna strona kategorii i zawartość dla danej kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-115">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="78715-116">Możesz wyświetlić podgląd zarówno kategorii wzbogaconej, jak i nie wzbogaconej kategorii, wybierając nazwę kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-116">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="78715-117">Aby wzbogacić stronę kategorii, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="78715-117">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="78715-118">Na stronie **Produkty** wybierz nazwę kategorii, dla której chcesz wzbogacić stronę kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-118">On the **Products** page, select the name of the category that you want to enrich the category page for.</span></span> <span data-ttu-id="78715-119">Domyślna strona kategorii dla wybranej kategorii jest otwierana w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="78715-119">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="78715-120">Wybierz **Wzbogać stronę kategorii**.</span><span class="sxs-lookup"><span data-stu-id="78715-120">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="78715-121">Wybierz szablon dla wzbogaconej strony kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-121">Select a template for the enriched category page.</span></span> <span data-ttu-id="78715-122">W przypadku wprowadzania tylko drobnych zmian można wybrać domyślną stronę kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-122">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="78715-123">Alternatywnie można wybrać określony szablon strony kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-123">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="78715-124">Po wybraniu szablonu zostanie otwarty Edytor stron, a wybrany szablon zostanie użyty do utworzenia nowej strony kategorii dla wybranej kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-124">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="78715-125">Strona jest wyewidencjonowana dla Ciebie i teraz możesz wprowadzić zmiany.</span><span class="sxs-lookup"><span data-stu-id="78715-125">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="78715-126">Moduły korzystające z danych specyfikacji kategorii używają danych z wybranej kategorii.</span><span class="sxs-lookup"><span data-stu-id="78715-126">Modules that use category specification data use the data from your selected category.</span></span>
>
> <span data-ttu-id="78715-127">Ustawienia wybranego szablonu decydują o zmianach, które można wprowadzić w tym szablonie.</span><span class="sxs-lookup"><span data-stu-id="78715-127">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78715-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="78715-128">Additional resources</span></span>

[<span data-ttu-id="78715-129">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="78715-129">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="78715-130">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="78715-130">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="78715-131">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="78715-131">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="78715-132">Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="78715-132">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="78715-133">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="78715-133">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="78715-134">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="78715-134">Enrich a product page</span></span>](enrich-product-page.md)
