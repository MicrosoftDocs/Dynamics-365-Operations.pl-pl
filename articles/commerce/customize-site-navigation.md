---
title: Dostosowywanie nawigacji w witrynie
description: W tym temacie opisano sposób tworzenia dostosowanej hierarchii nawigacji w trybie online do organizowania produktów w celu ich przejrzenia w witrynie Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8e1efb4a7484bd4626886c0f9aa40c3e4dfe304a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697481"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="13c0c-103">Dostosowywanie nawigacji w witrynie</span><span class="sxs-lookup"><span data-stu-id="13c0c-103">Customize site navigation</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="13c0c-104">W tym temacie opisano sposób tworzenia dostosowanej hierarchii nawigacji w trybie online do organizowania produktów w celu ich przejrzenia w witrynie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="13c0c-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="13c0c-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="13c0c-105">Overview</span></span>

<span data-ttu-id="13c0c-106">Sklepy online zazwyczaj umożliwiają klientom odkrywanie produktów i przeglądanie ich w różnych kategoriach produktów.</span><span class="sxs-lookup"><span data-stu-id="13c0c-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="13c0c-107">Ta możliwość jest zazwyczaj udostępniana przez karty u góry strony lub przez pasek nawigacyjny po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="13c0c-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="13c0c-108">W Dynamics 365 Commerce można tworzyć strukturę hierarchii nawigacji między kategoriami i produkty uwzględnione w różnych kategoriach oraz zarządzać tymi strukturami.</span><span class="sxs-lookup"><span data-stu-id="13c0c-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-retail-channel-navigation-hierarchy"></a><span data-ttu-id="13c0c-109">Tworzenie hierarchii nawigacji kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="13c0c-109">Create a retail channel navigation hierarchy</span></span>

<span data-ttu-id="13c0c-110">Aby utworzyć hierarchię nawigacji kanału sprzedaży detalicznej, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="13c0c-110">To create a retail channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="13c0c-111">Wybierz kolejno opcje **Handel detaliczny i inny \> Produkty i kategorie \> Zarządzanie kategoriami i produktami**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-111">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="13c0c-112">Wybierz **Hierarchie kategorii**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="13c0c-113">Nazwij hierarchię.</span><span class="sxs-lookup"><span data-stu-id="13c0c-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="13c0c-114">Tworzona Kategoria najwyższego poziomu jest węzłem głównej kategorii.</span><span class="sxs-lookup"><span data-stu-id="13c0c-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="13c0c-115">Nie będzie on pokazywany w witrynie.</span><span class="sxs-lookup"><span data-stu-id="13c0c-115">It won't be shown on your site.</span></span> <span data-ttu-id="13c0c-116">Aby utworzyć hierarchię kategorii, w której w witrynie jest wyświetlany jeden węzeł najwyższego poziomu, należy utworzyć nazwę kategorii i nazwać ją jako podrzędną dla kategorii głównej.</span><span class="sxs-lookup"><span data-stu-id="13c0c-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="13c0c-117">Wybierz opcję **Nowy węzeł kategorii** i nadaj nazwę kategorii.</span><span class="sxs-lookup"><span data-stu-id="13c0c-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="13c0c-118">W razie konieczności kontynuuj tworzenie elementów równorzędnych i podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="13c0c-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="13c0c-119">Teraz można przypisywać produkty do każdej kategorii utworzonej w ramach kategorii najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="13c0c-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="13c0c-120">Dostosowywanie kolejności kategorii</span><span class="sxs-lookup"><span data-stu-id="13c0c-120">Customize the order of categories</span></span>

<span data-ttu-id="13c0c-121">Kategorie definiowane przez użytkownika są domyślnie wyświetlane w kolejności alfabetycznej w witrynie.</span><span class="sxs-lookup"><span data-stu-id="13c0c-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="13c0c-122">Można jednak również dostosować kolejność wyświetlania kategorii.</span><span class="sxs-lookup"><span data-stu-id="13c0c-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="13c0c-123">Przypisywanie typu hierarchii kategorii</span><span class="sxs-lookup"><span data-stu-id="13c0c-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="13c0c-124">Wybierz kolejno opcje **Handel detaliczny i inny \> Produkty i kategorie \> Zarządzanie kategoriami i produktami**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-124">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="13c0c-125">Wybierz **Hierarchie kategorii**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="13c0c-126">Następnie w okienku akcji na karcie **Hierarchie kategorii** w grupie **Konfiguracja** wybierz opcję **Powiązanie typu hierarchii**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="13c0c-127">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-127">Select **New**.</span></span>
1. <span data-ttu-id="13c0c-128">W polu **Typ hierarchii kategorii** wybierz opcję **Hierarchia nawigacji kanału sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-128">In the **Category hierarchy type** field, select **Retail channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="13c0c-129">W polu **hierarchia kategorii** wybierz utworzoną wcześniej hierarchię nawigacji kanałów.</span><span class="sxs-lookup"><span data-stu-id="13c0c-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="13c0c-130">Opublikuj nowe lub zaktualizowane hierarchie nawigacji</span><span class="sxs-lookup"><span data-stu-id="13c0c-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="13c0c-131">Aby uczynić hierarchię nawigacji dostępną w Twoim sklepem online, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="13c0c-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="13c0c-132">Wybierz kolejno opcje **Handel detaliczny \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-132">Go to **Retail \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="13c0c-133">W drzewie po lewej stronie wybierz sklep internetowy.</span><span class="sxs-lookup"><span data-stu-id="13c0c-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="13c0c-134">Wybierz **Publikowanie aktualizacji kanału**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="13c0c-135">Wybierz kolejno opcje **Handel detaliczny \> Dane IT sieci sprzedaży \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-135">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="13c0c-136">Na liście znajdź i zaznacz **Zadanie 1040**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="13c0c-137">Wybierz opcję **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="13c0c-137">Select **Run now**.</span></span>
1. <span data-ttu-id="13c0c-138">Powtórz kroki 5 i 6 dla zadań 1070 i 1150.</span><span class="sxs-lookup"><span data-stu-id="13c0c-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="13c0c-139">Wyświetlanie kategorii w witrynie</span><span class="sxs-lookup"><span data-stu-id="13c0c-139">Show categories on your site</span></span>

<span data-ttu-id="13c0c-140">Aby wyświetlić hierarchię kategorii w witrynie sklep online, należy dodać moduł menu nawigacji w odpowiedniej lokalizacji w szablonie lub fragmencie.</span><span class="sxs-lookup"><span data-stu-id="13c0c-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="13c0c-141">W module menu nawigacji zostanie wyświetlona hierarchia nawigacji, pod warunkiem, że hierarchia nawigacji w sieci sprzedaży zostanie opublikowana w kanale, z którym jest związana ta witryna.</span><span class="sxs-lookup"><span data-stu-id="13c0c-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your retail navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="13c0c-142">Moduł menu nawigacji, który jest dołączony do zestawu Store Starter Kit, umożliwia użytkownikom poruszanie się wyłącznie do kategorii, które nie mają podkategorii.</span><span class="sxs-lookup"><span data-stu-id="13c0c-142">The navigation menu module that is included in the store starter kit lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="13c0c-143">Jeśli odbiorcy powinni mieć możliwość nawigowania do kategorii, które mają podkategorie, należy dostosować Moduł menu nawigacji.</span><span class="sxs-lookup"><span data-stu-id="13c0c-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="13c0c-144">Dodawanie niestandardowych opcji nawigacji</span><span class="sxs-lookup"><span data-stu-id="13c0c-144">Add custom navigation options</span></span>

<span data-ttu-id="13c0c-145">W menu nawigacji można dodać opcje nawigacji, które nie należą do hierarchii kategorii produktów.</span><span class="sxs-lookup"><span data-stu-id="13c0c-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="13c0c-146">Na przykład na końcu listy kategorii produktów można dodać element **Skontaktuj się z nami** wskazujący na stronę kontaktową utworzoną dla witryny.</span><span class="sxs-lookup"><span data-stu-id="13c0c-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="13c0c-147">Aby dodać niestandardowe opcje nawigacji do menu nawigacji, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="13c0c-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="13c0c-148">W szablonie lub fragmencie, który chcesz dostosować, wybierz moduł menu nawigacji.</span><span class="sxs-lookup"><span data-stu-id="13c0c-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="13c0c-149">W okienku właściwości na karcie **Dane** wybierz **Dodaj pozycję**, aby utworzyć nowy element nawigacji w systemie Content Management System (CMS).</span><span class="sxs-lookup"><span data-stu-id="13c0c-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="13c0c-150">Wprowadź tekst łącza i adres URL</span><span class="sxs-lookup"><span data-stu-id="13c0c-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="13c0c-151">Powtórz kroki 2 i 3, aby dodać kolejne opcje nawigacji niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="13c0c-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="13c0c-152">Po zakończeniu zapisz szablon lub fragment i zaewidencjonuj go.</span><span class="sxs-lookup"><span data-stu-id="13c0c-152">When you've finished, save the template or fragment, and check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13c0c-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="13c0c-153">Additional resources</span></span>

[<span data-ttu-id="13c0c-154">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="13c0c-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="13c0c-155">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="13c0c-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="13c0c-156">Praca z układami predefiniowanymi</span><span class="sxs-lookup"><span data-stu-id="13c0c-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="13c0c-157">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="13c0c-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="13c0c-158">Praca z modułami</span><span class="sxs-lookup"><span data-stu-id="13c0c-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="13c0c-159">Tworzenie adresu URL strony</span><span class="sxs-lookup"><span data-stu-id="13c0c-159">Create a page URL</span></span>](create-page-url.md)
