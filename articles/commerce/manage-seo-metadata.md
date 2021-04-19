---
title: Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania
description: W tym temacie opisano sposób zarządzania metadanymi optymalizacji aparatu wyszukiwania (SEO) w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1e03ef346df92a94b0a403f241d0f7d1f64fd210
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794218"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="072f3-103">Zarządzanie metadanymi SEO</span><span class="sxs-lookup"><span data-stu-id="072f3-103">Manage SEO metadata</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="072f3-104">W tym temacie opisano sposób zarządzania metadanymi optymalizacji aparatu wyszukiwania (SEO) w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="072f3-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="072f3-105">Metadane funkcji optymalizacji wyszukiwania dla witryny można zarządzać za pomocą map witryn i metadanych strony.</span><span class="sxs-lookup"><span data-stu-id="072f3-105">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="072f3-106">Mapy witryny</span><span class="sxs-lookup"><span data-stu-id="072f3-106">Site maps</span></span>

<span data-ttu-id="072f3-107">Mapa witryny to lista stron witryny w formacie XML, która jest czytelna dla maszyn.</span><span class="sxs-lookup"><span data-stu-id="072f3-107">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="072f3-108">Jest ona przeznaczona do używania przez silniki wyszukiwania, dzięki czemu mogą one zapewnić lepsze wyniki wyszukiwania w witrynie.</span><span class="sxs-lookup"><span data-stu-id="072f3-108">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="072f3-109">Mapy witryn mogą być ręcznie wprowadzane do silników wyszukiwania lub publikowane w pliku robots.txt.</span><span class="sxs-lookup"><span data-stu-id="072f3-109">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="072f3-110">Dynamics 365 Commerce obsługuje automatyczne generowanie map witryn.</span><span class="sxs-lookup"><span data-stu-id="072f3-110">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="072f3-111">Mapy witryn są automatycznie aktualizowane podczas publikowania i cofnięcia publikowania stron.</span><span class="sxs-lookup"><span data-stu-id="072f3-111">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="072f3-112">Włącz generowanie mapy witryny</span><span class="sxs-lookup"><span data-stu-id="072f3-112">Turn on site map generation</span></span>

1. <span data-ttu-id="072f3-113">Zaloguj się do narzędzia autorskiego.</span><span class="sxs-lookup"><span data-stu-id="072f3-113">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="072f3-114">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="072f3-114">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="072f3-115">W okienku nawigacji po lewej stronie zaznacz **Zarządzanie witryną**.</span><span class="sxs-lookup"><span data-stu-id="072f3-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="072f3-116">Upewnij się, że opcja **Mapy witryny włączone** jest włączona</span><span class="sxs-lookup"><span data-stu-id="072f3-116">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="072f3-117">Metadane strony</span><span class="sxs-lookup"><span data-stu-id="072f3-117">Page metadata</span></span>

<span data-ttu-id="072f3-118">Dynamics 365 Commerce umożliwia zarządzanie metadanymi funkcji optymalizacji dla poszczególnych stron.</span><span class="sxs-lookup"><span data-stu-id="072f3-118">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="072f3-119">Informacje te można wyświetlać i modyfikować w sekcji **Właściwości adresu SEO** w kontenerze stron.</span><span class="sxs-lookup"><span data-stu-id="072f3-119">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="072f3-120">Obecnie obsługiwane są następujące właściwości metadanych SEO:</span><span class="sxs-lookup"><span data-stu-id="072f3-120">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="072f3-121">Nazwa</span><span class="sxs-lookup"><span data-stu-id="072f3-121">Title</span></span>
- <span data-ttu-id="072f3-122">Opis</span><span class="sxs-lookup"><span data-stu-id="072f3-122">Description</span></span>
- <span data-ttu-id="072f3-123">słowa kluczowe SEO</span><span class="sxs-lookup"><span data-stu-id="072f3-123">SEO keywords</span></span>
- <span data-ttu-id="072f3-124">etykiety aria</span><span class="sxs-lookup"><span data-stu-id="072f3-124">Aria labels</span></span>
- <span data-ttu-id="072f3-125">noindex</span><span class="sxs-lookup"><span data-stu-id="072f3-125">noindex</span></span>
- <span data-ttu-id="072f3-126">nofollow</span><span class="sxs-lookup"><span data-stu-id="072f3-126">nofollow</span></span>
- <span data-ttu-id="072f3-127">noarchive</span><span class="sxs-lookup"><span data-stu-id="072f3-127">noarchive</span></span>
- <span data-ttu-id="072f3-128">nocache</span><span class="sxs-lookup"><span data-stu-id="072f3-128">nocache</span></span>
- <span data-ttu-id="072f3-129">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="072f3-129">noOpenDirectoryProject</span></span>
- <span data-ttu-id="072f3-130">nosnippet</span><span class="sxs-lookup"><span data-stu-id="072f3-130">nosnippet</span></span>
- <span data-ttu-id="072f3-131">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="072f3-131">noImageIndex</span></span>
- <span data-ttu-id="072f3-132">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="072f3-132">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="072f3-133">Modyfikuj metadane strony</span><span class="sxs-lookup"><span data-stu-id="072f3-133">Modify page metadata</span></span>

<span data-ttu-id="072f3-134">Aby skonfigurować metadane strony, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="072f3-134">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="072f3-135">W obszarze **Witryny** wybierz firmę **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="072f3-135">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="072f3-136">W okienku nawigacji po lewej stronie wybierz **Strony**.</span><span class="sxs-lookup"><span data-stu-id="072f3-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="072f3-137">Wybierz stronę główną, aby otworzyć ją w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="072f3-137">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="072f3-138">Na pasku poleceń wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="072f3-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="072f3-139">W okienku właściwości po prawej stronie rozwiń **Domyślne tagi metadanych**.</span><span class="sxs-lookup"><span data-stu-id="072f3-139">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="072f3-140">Aby dodać nowy tag metadanych, wybierz opcję **Dodaj**, a następnie wprowadź znacznik w polu.</span><span class="sxs-lookup"><span data-stu-id="072f3-140">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span> <span data-ttu-id="072f3-141">Aby usunąć istniejący tag metadanych, należy wybrać symbol kosza na śmieci.</span><span class="sxs-lookup"><span data-stu-id="072f3-141">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>
1. <span data-ttu-id="072f3-142">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="072f3-142">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="072f3-143">W polu **Komentarze** wprowadź **Zaktualizowane Tagi metadanych**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="072f3-143">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="072f3-144">Wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="072f3-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="072f3-145">Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.</span><span class="sxs-lookup"><span data-stu-id="072f3-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="072f3-146">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="072f3-146">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="072f3-147">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="072f3-147">Additional resources</span></span>

[<span data-ttu-id="072f3-148">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="072f3-148">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="072f3-149">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="072f3-149">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="072f3-150">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="072f3-150">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="072f3-151">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="072f3-151">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="072f3-152">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="072f3-152">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="072f3-153">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="072f3-153">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="072f3-154">Weryfikowanie dostępności zawartości strony</span><span class="sxs-lookup"><span data-stu-id="072f3-154">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="072f3-155">Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL</span><span class="sxs-lookup"><span data-stu-id="072f3-155">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
