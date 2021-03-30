---
title: Dostosowywanie nawigacji w witrynie
description: W tym temacie opisano sposób tworzenia dostosowanej hierarchii nawigacji w trybie online do organizowania produktów w celu ich przejrzenia w witrynie Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: cfd0a9559eb2b596adb822b228929e6855711bb4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222616"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="f0b8e-103">Dostosowywanie nawigacji w witrynie</span><span class="sxs-lookup"><span data-stu-id="f0b8e-103">Customize site navigation</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f0b8e-104">W tym temacie opisano sposób tworzenia dostosowanej hierarchii nawigacji w trybie online do organizowania produktów w celu ich przejrzenia w witrynie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="f0b8e-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="f0b8e-105">Overview</span></span>

<span data-ttu-id="f0b8e-106">Sklepy online zazwyczaj umożliwiają klientom odkrywanie produktów i przeglądanie ich w różnych kategoriach produktów.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="f0b8e-107">Ta możliwość jest zazwyczaj udostępniana przez karty u góry strony lub przez pasek nawigacyjny po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="f0b8e-108">W Dynamics 365 Commerce można tworzyć strukturę hierarchii nawigacji między kategoriami i produkty uwzględnione w różnych kategoriach oraz zarządzać tymi strukturami.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="f0b8e-109">Tworzenie hierarchii nawigacji kanału</span><span class="sxs-lookup"><span data-stu-id="f0b8e-109">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="f0b8e-110">Aby utworzyć hierarchię nawigacji kanału, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-110">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="f0b8e-111">Wybierz kolejno opcje **Retail i Commerce \> Produkty i kategorie \> Zarządzanie kategoriami i produktami**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-111">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="f0b8e-112">Wybierz **Hierarchie kategorii**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="f0b8e-113">Nazwij hierarchię.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0b8e-114">Tworzona Kategoria najwyższego poziomu jest węzłem głównej kategorii.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="f0b8e-115">Nie będzie on pokazywany w witrynie.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-115">It won't be shown on your site.</span></span> <span data-ttu-id="f0b8e-116">Aby utworzyć hierarchię kategorii, w której w witrynie jest wyświetlany jeden węzeł najwyższego poziomu, należy utworzyć nazwę kategorii i nazwać ją jako podrzędną dla kategorii głównej.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="f0b8e-117">Wybierz opcję **Nowy węzeł kategorii** i nadaj nazwę kategorii.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="f0b8e-118">W razie konieczności kontynuuj tworzenie elementów równorzędnych i podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="f0b8e-119">Teraz można przypisywać produkty do każdej kategorii utworzonej w ramach kategorii najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="f0b8e-120">Dostosowywanie kolejności kategorii</span><span class="sxs-lookup"><span data-stu-id="f0b8e-120">Customize the order of categories</span></span>

<span data-ttu-id="f0b8e-121">Kategorie definiowane przez użytkownika są domyślnie wyświetlane w kolejności alfabetycznej w witrynie.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="f0b8e-122">Można jednak również dostosować kolejność wyświetlania kategorii.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="f0b8e-123">Przypisywanie typu hierarchii kategorii</span><span class="sxs-lookup"><span data-stu-id="f0b8e-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="f0b8e-124">Wybierz kolejno opcje **Retail i Commerce \> Produkty i kategorie \> Zarządzanie kategoriami i produktami**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-124">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="f0b8e-125">Wybierz **Hierarchie kategorii**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="f0b8e-126">Następnie w okienku akcji na karcie **Hierarchie kategorii** w grupie **Konfiguracja** wybierz opcję **Powiązanie typu hierarchii**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="f0b8e-127">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-127">Select **New**.</span></span>
1. <span data-ttu-id="f0b8e-128">W polu **Typ hierarchii kategorii** wybierz opcję **Hierarchia nawigacji kanału**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-128">In the **Category hierarchy type** field, select **Channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="f0b8e-129">W polu **hierarchia kategorii** wybierz utworzoną wcześniej hierarchię nawigacji kanałów.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="f0b8e-130">Opublikuj nowe lub zaktualizowane hierarchie nawigacji</span><span class="sxs-lookup"><span data-stu-id="f0b8e-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="f0b8e-131">Aby uczynić hierarchię nawigacji dostępną w Twoim sklepem online, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="f0b8e-132">Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-132">Go to **Retail and Commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="f0b8e-133">W drzewie po lewej stronie wybierz sklep internetowy.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="f0b8e-134">Wybierz **Publikowanie aktualizacji kanału**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="f0b8e-135">Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="f0b8e-136">Na liście znajdź i zaznacz **Zadanie 1040**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="f0b8e-137">Wybierz opcję **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-137">Select **Run now**.</span></span>
1. <span data-ttu-id="f0b8e-138">Powtórz kroki 5 i 6 dla zadań 1070 i 1150.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="f0b8e-139">Wyświetlanie kategorii w witrynie</span><span class="sxs-lookup"><span data-stu-id="f0b8e-139">Show categories on your site</span></span>

<span data-ttu-id="f0b8e-140">Aby wyświetlić hierarchię kategorii w witrynie sklep online, należy dodać moduł menu nawigacji w odpowiedniej lokalizacji w szablonie lub fragmencie.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="f0b8e-141">W module menu nawigacji zostanie wyświetlona hierarchia nawigacji, pod warunkiem, że hierarchia nawigacji zostanie opublikowana w kanale, z którym jest związana ta witryna.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="f0b8e-142">Moduł menu nawigacji, który jest dołączony do biblioteki modułów, umożliwia użytkownikom poruszanie się wyłącznie do kategorii, które nie mają podkategorii.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-142">The navigation menu module that is included in the module library lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="f0b8e-143">Jeśli odbiorcy powinni mieć możliwość nawigowania do kategorii, które mają podkategorie, należy dostosować Moduł menu nawigacji.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="f0b8e-144">Dodawanie niestandardowych opcji nawigacji</span><span class="sxs-lookup"><span data-stu-id="f0b8e-144">Add custom navigation options</span></span>

<span data-ttu-id="f0b8e-145">W menu nawigacji można dodać opcje nawigacji, które nie należą do hierarchii kategorii produktów.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="f0b8e-146">Na przykład na końcu listy kategorii produktów można dodać element **Skontaktuj się z nami** wskazujący na stronę kontaktową utworzoną dla witryny.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="f0b8e-147">Aby dodać niestandardowe opcje nawigacji do menu nawigacji, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="f0b8e-148">W szablonie lub fragmencie, który chcesz dostosować, wybierz moduł menu nawigacji.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="f0b8e-149">W okienku właściwości na karcie **Dane** wybierz **Dodaj pozycję**, aby utworzyć nowy element nawigacji w systemie Content Management System (CMS).</span><span class="sxs-lookup"><span data-stu-id="f0b8e-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="f0b8e-150">Wprowadź tekst łącza i adres URL</span><span class="sxs-lookup"><span data-stu-id="f0b8e-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="f0b8e-151">Powtórz kroki 2 i 3, aby dodać kolejne opcje nawigacji niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="f0b8e-152">Po zakończeniu wybierz opcję **Zapisz**, aby zapisać szablon lub fragment, a następnie wybierz przycisk **Zakończ edycję**, aby go zaewidencjonować.</span><span class="sxs-lookup"><span data-stu-id="f0b8e-152">When you've finished, select **Save** to save the template or fragment, and then select **Finish editing** to check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0b8e-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f0b8e-153">Additional resources</span></span>

[<span data-ttu-id="f0b8e-154">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="f0b8e-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="f0b8e-155">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="f0b8e-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="f0b8e-156">Praca z układami predefiniowanymi</span><span class="sxs-lookup"><span data-stu-id="f0b8e-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="f0b8e-157">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="f0b8e-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="f0b8e-158">Praca z modułami</span><span class="sxs-lookup"><span data-stu-id="f0b8e-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="f0b8e-159">Tworzenie adresu URL strony</span><span class="sxs-lookup"><span data-stu-id="f0b8e-159">Create a page URL</span></span>](create-page-url.md)

[<span data-ttu-id="f0b8e-160">Praca z grupami publikowania</span><span class="sxs-lookup"><span data-stu-id="f0b8e-160">Work with publish groups</span></span>](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]