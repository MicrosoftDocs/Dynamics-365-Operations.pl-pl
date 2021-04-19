---
title: Dodawanie nowej strony witryny
description: W tym temacie opisano, jak dodać nową stronę witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 4a2ecc3ef3ff3f708cec50e42777b50ec4576e25
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797558"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="b5485-103">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="b5485-103">Add a new site page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b5485-104">W tym temacie opisano, jak dodać nową stronę witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b5485-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b5485-105">Po utworzeniu szablonów i fragmentów dla witryny następnym krokiem jest rozpoczęcie tworzenia stron, które ich używają.</span><span class="sxs-lookup"><span data-stu-id="b5485-105">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="b5485-106">Aby rozpocząć, musisz wybrać szablon lub układ, nazwę strony oraz adres URL strony.</span><span class="sxs-lookup"><span data-stu-id="b5485-106">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="b5485-107">Szablon lub układ</span><span class="sxs-lookup"><span data-stu-id="b5485-107">Template or layout</span></span>

<span data-ttu-id="b5485-108">Dla nowej strony można zastosować szablon lub układ.</span><span class="sxs-lookup"><span data-stu-id="b5485-108">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="b5485-109">Aby uzyskać więcej informacji, zobacz [Omówienie szablonów i układów](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b5485-109">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="b5485-110">Nazwa strony</span><span class="sxs-lookup"><span data-stu-id="b5485-110">Page name</span></span>

<span data-ttu-id="b5485-111">Nazwa strony musi być unikatowa dla danej strony.</span><span class="sxs-lookup"><span data-stu-id="b5485-111">The page name must be unique to your page.</span></span> <span data-ttu-id="b5485-112">Powinna ona być opisowa, aby można było łatwo ją odnaleźć i inne osoby wiedziały, że jest przeznaczona dla strony.</span><span class="sxs-lookup"><span data-stu-id="b5485-112">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="b5485-113">Należy uważnie wybrać nazwę strony, ponieważ nie można jej później zmienić.</span><span class="sxs-lookup"><span data-stu-id="b5485-113">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="b5485-114">Adres URL strony</span><span class="sxs-lookup"><span data-stu-id="b5485-114">Page URL</span></span>

<span data-ttu-id="b5485-115">Można wybrać opcję wprowadzania adresu URL dla nowej strony.</span><span class="sxs-lookup"><span data-stu-id="b5485-115">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="b5485-116">Podczas tworzenia strony można wprowadzić ciąg, który będzie używany do tworzenia pełnego adresu URL.</span><span class="sxs-lookup"><span data-stu-id="b5485-116">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="b5485-117">Ten ciąg określany jest jako względny adres URL lub do informacji o adresie URL.</span><span class="sxs-lookup"><span data-stu-id="b5485-117">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="b5485-118">Cały adres URL jest następnie generowany na podstawie informacji o adresach URL, a nowa strona jest przypisana do niej.</span><span class="sxs-lookup"><span data-stu-id="b5485-118">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="b5485-119">Przed opublikowaniem strony można później zmienić jej adres URL.</span><span class="sxs-lookup"><span data-stu-id="b5485-119">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="b5485-120">Aby uzyskać więcej informacji, zobacz temat [Tworzenie adresu URL strony](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="b5485-120">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b5485-121">Dynamics 365 Commerce rozdziela adresy URL i zawartość.</span><span class="sxs-lookup"><span data-stu-id="b5485-121">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="b5485-122">Innymi słowy, można utworzyć stronę, która nie jest skojarzona z adresem URL i utworzyć adres URL, który nie jest skojarzony ze stroną.</span><span class="sxs-lookup"><span data-stu-id="b5485-122">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="b5485-123">W związku z tym może nastąpić założenie zawartości adresu URL i nie wymaga przestoju, a przekierowywanie jest łatwiejsze do zarządzania.</span><span class="sxs-lookup"><span data-stu-id="b5485-123">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="b5485-124">Dodawanie nowej strony</span><span class="sxs-lookup"><span data-stu-id="b5485-124">Add a new page</span></span>

<span data-ttu-id="b5485-125">Aby dodać nową stronę do swojej witryny, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b5485-125">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="b5485-126">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="b5485-126">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="b5485-127">Wybierz **Nowa strona**.</span><span class="sxs-lookup"><span data-stu-id="b5485-127">Select **New Page**.</span></span>
1. <span data-ttu-id="b5485-128">W oknie dialogowym **Nowa strona** wybierz szablon i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5485-128">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="b5485-129">W polu **Nazwa strony** wprowadź nazwę strony (na przykład **Nowa strona**).</span><span class="sxs-lookup"><span data-stu-id="b5485-129">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="b5485-130">W polu **adres URL** wprowadź ciąg (adres URL), aby dokończyć adres URL (na przykład **mynewpage**).</span><span class="sxs-lookup"><span data-stu-id="b5485-130">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="b5485-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5485-131">Select **OK**.</span></span> <span data-ttu-id="b5485-132">Zostanie wyświetlona strona edytora.</span><span class="sxs-lookup"><span data-stu-id="b5485-132">The page editor appears.</span></span> <span data-ttu-id="b5485-133">Zauważ, że nagłówek i stopka są automatycznie dodawane do strony na podstawie wybranego szablonu.</span><span class="sxs-lookup"><span data-stu-id="b5485-133">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="b5485-134">W konspekcie strony wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="b5485-134">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b5485-135">Zaznacz element **Kontener** i kliknij przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="b5485-135">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="b5485-136">Wybierz **Kontener płynny**, a następnie wybierz przycisk wielokropka i opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="b5485-136">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="b5485-137">Zaznacz **Blok zawartości sformatowanej**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5485-137">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="b5485-138">Wybierz **Blok zawartości sformatowanej**, a następnie wybierz przycisk wielokropka i opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="b5485-138">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="b5485-139">Zaznacz **Element bloku zawartości sformatowanej**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5485-139">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="b5485-140">W okienku właściwości po prawej stronie wybierz pozycję **Akapit**, a następnie w polu wprowadź **Tekst testowy**.</span><span class="sxs-lookup"><span data-stu-id="b5485-140">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="b5485-141">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="b5485-141">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="b5485-142">W polu **Komentarze** wprowadź **Dodawanie nowej strony**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5485-142">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="b5485-143">Wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="b5485-143">Select **Preview** to preview your page.</span></span> <span data-ttu-id="b5485-144">Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.</span><span class="sxs-lookup"><span data-stu-id="b5485-144">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="b5485-145">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="b5485-145">Select **Publish**.</span></span>
1. <span data-ttu-id="b5485-146">W ścieżce nawigacji (struktura nawigacyjna) wybierz firmę **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="b5485-146">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="b5485-147">W okienku nawigacji po lewej stronie zaznacz **adresy URL**.</span><span class="sxs-lookup"><span data-stu-id="b5485-147">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="b5485-148">Na liście znajdź i zaznacz URL (**mynewpage**).</span><span class="sxs-lookup"><span data-stu-id="b5485-148">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="b5485-149">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="b5485-149">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b5485-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b5485-150">Additional resources</span></span>

[<span data-ttu-id="b5485-151">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="b5485-151">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="b5485-152">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="b5485-152">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="b5485-153">Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="b5485-153">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="b5485-154">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="b5485-154">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="b5485-155">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="b5485-155">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="b5485-156">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="b5485-156">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="b5485-157">Weryfikowanie dostępności zawartości strony</span><span class="sxs-lookup"><span data-stu-id="b5485-157">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="b5485-158">Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL</span><span class="sxs-lookup"><span data-stu-id="b5485-158">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
