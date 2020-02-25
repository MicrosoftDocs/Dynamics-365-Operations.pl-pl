---
title: Konfigurowanie ocen i recenzji
description: W tym temacie opisano sposób konfigurowania witryny e-Commerce w celu wyświetlania ocen odbiorców i recenzji w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
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
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0aac4b680590a95f465d33950f2933c4a4582e54
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002204"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="ac2a4-103">Konfigurowanie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="ac2a4-103">Configure ratings and reviews</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ac2a4-104">W tym temacie opisano sposób konfigurowania witryny e-Commerce w celu wyświetlania ocen odbiorców i recenzji w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ac2a4-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="ac2a4-105">Overview</span></span>

<span data-ttu-id="ac2a4-106">Oceny i Recenzje w witrynach e-Commerce umożliwiają klientom zapoznanie się z produktami przed podjęciem decyzji o zakupie, kierując ich uwagę na te produkty.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, by showing them what other customers think about those products.</span></span> <span data-ttu-id="ac2a4-107">W przypadku witryn e-Commerce, oceny i recenzje są również mechanizmami zbierania opinii klientów dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="ac2a4-108">Oceny są wyświetlane na stronach list produktów, na stronach list kategorii, na stronach wyników wyszukiwania oraz na innych stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-108">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> <span data-ttu-id="ac2a4-109">Histogramy ocen i recenzje produktów są wyświetlane na stronach szczegółów produktów (stronach PDP).</span><span class="sxs-lookup"><span data-stu-id="ac2a4-109">Ratings histograms and product reviews are shown on product details pages (PDPs).</span></span> <span data-ttu-id="ac2a4-110">Przez naciśnięcie przycisku **Napisz recenzję** klienci mogą przesyłać oceny i recenzje produktu.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-110">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="ac2a4-111">Moduły ocen i recenzji na stronach PDP</span><span class="sxs-lookup"><span data-stu-id="ac2a4-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="ac2a4-112">Na stronach PDP w trzech modułach są wyświetlane podsumowania ocen i recenzji:</span><span class="sxs-lookup"><span data-stu-id="ac2a4-112">Three modules show the ratings and reviews summary on PDPs:</span></span>

- <span data-ttu-id="ac2a4-113">Napisz moduł recenzji</span><span class="sxs-lookup"><span data-stu-id="ac2a4-113">Write review module</span></span>
- <span data-ttu-id="ac2a4-114">Moduł listy recenzji produktów</span><span class="sxs-lookup"><span data-stu-id="ac2a4-114">Product reviews list module</span></span>
- <span data-ttu-id="ac2a4-115">Moduł histogramu ocen</span><span class="sxs-lookup"><span data-stu-id="ac2a4-115">Ratings histogram module</span></span>
 
<span data-ttu-id="ac2a4-116">Na poniższej ilustracji przedstawiono jak moduły ocen i recenzji wyglądają na stronach PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Moduły ocen i recenzji na stronach PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="ac2a4-118">Aby uzyskać informacje na temat optymalizowania szablonów i układów PDP, tak aby można było udostępniać konfiguracje dla modułów ocen i recenzji na wielu stronach PDP w witrynie e-Commerce, należy zapoznać się z [Omówienie szablonów i układów](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ac2a4-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="ac2a4-119">Na poniższej ilustracji pokazano, jak w oknie dialogowym **Dodaj moduł** są prezentowane moduły ocen i recenzji w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>

![Dodaj moduł okna dialogowego](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a><span data-ttu-id="ac2a4-121">Napisz moduł recenzji</span><span class="sxs-lookup"><span data-stu-id="ac2a4-121">Write review module</span></span>

<span data-ttu-id="ac2a4-122">Moduł zapisu recenzji zawiera przycisk **Napisz recenzję**, który pozwala użytkownikom zalogować się, przypisać ocenę i napisać recenzję produktu.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="ac2a4-123">Moduł ten pozwala również edytować wcześniej przesłane oceny lub recenzje.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="ac2a4-124">Ten moduł zazwyczaj pojawia się nad histogramem ocen i modułami listy recenzji produktów na PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>

<span data-ttu-id="ac2a4-125">Poniższa ilustracja pokazuje okno dialogowe **Napisz recenzję**, które pojawia się, gdy klient wybierze **Napisz recenzję**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="ac2a4-126">Odbiorca może użyć tego okna dialogowego do przesłania ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-126">The customer can use this dialog box to submit a rating and a review.</span></span>

![Napisz okno dialogowe recenzji](media/rnr-eCommerce-write-review-module.png)

<span data-ttu-id="ac2a4-128">W poniższej tabeli przedstawiono właściwość modułu recenzji zapisu, którą należy skonfigurować w narzędziu do tworzenia treści.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-128">The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>

| <span data-ttu-id="ac2a4-129">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="ac2a4-129">Property name</span></span> | <span data-ttu-id="ac2a4-130">Wartość</span><span class="sxs-lookup"><span data-stu-id="ac2a4-130">Value</span></span>        | <span data-ttu-id="ac2a4-131">Opis właściwości</span><span class="sxs-lookup"><span data-stu-id="ac2a4-131">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="ac2a4-132">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="ac2a4-132">Name</span></span>          | <span data-ttu-id="ac2a4-133">Napisz recenzję</span><span class="sxs-lookup"><span data-stu-id="ac2a4-133">Write review</span></span> | <span data-ttu-id="ac2a4-134">Nazwa modułu pisania recenzji.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-134">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="ac2a4-135">Moduł histogramu ocen</span><span class="sxs-lookup"><span data-stu-id="ac2a4-135">Ratings histogram module</span></span>

<span data-ttu-id="ac2a4-136">W module histogramu ocen jest wyświetlany histogram klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-136">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="ac2a4-137">Ten moduł zwykle pojawia się między modułem recenzji zapisu a modułem listy recenzji produktów na PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-137">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>

<span data-ttu-id="ac2a4-138">Moduł histogramu ocen nie wymaga konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-138">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="ac2a4-139">Wystarczy dodać moduł do szablonu PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-139">You just have to add the module in the PDP template.</span></span> 

<span data-ttu-id="ac2a4-140">Poniższe ilustracje pokazują, jak wygląda szablon PDP w Dynamics 365 Commerce, gdy moduły ocen i recenzji są skonfigurowane do wyświetlania na PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-140">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>

![Szablon PDP, gdy oceny i recenzje są skonfigurowane do wyświetlania na PDP](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a><span data-ttu-id="ac2a4-142">Moduł listy recenzji produktów</span><span class="sxs-lookup"><span data-stu-id="ac2a4-142">Product reviews list module</span></span>

<span data-ttu-id="ac2a4-143">Moduł listy recenzji produktów pokazuje listę recenzji produktów wraz z opcjami sortowania, filtrowania i paginacji.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-143">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="ac2a4-144">Ten moduł zazwyczaj znajduje się po module histogramu ocen na PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-144">This module typically appears after the ratings histogram module on a PDP.</span></span>

<span data-ttu-id="ac2a4-145">Poniższa tabela pokazuje właściwości modułu listy recenzji produktów, które należy skonfigurować w narzędziu do tworzenia treści.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-145">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="ac2a4-146">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="ac2a4-146">Property name</span></span>              | <span data-ttu-id="ac2a4-147">Wartość</span><span class="sxs-lookup"><span data-stu-id="ac2a4-147">Value</span></span> | <span data-ttu-id="ac2a4-148">Opis właściwości</span><span class="sxs-lookup"><span data-stu-id="ac2a4-148">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="ac2a4-149">Recenzje pokazywane na każdej stronie</span><span class="sxs-lookup"><span data-stu-id="ac2a4-149">Reviews shown on each page</span></span> | <span data-ttu-id="ac2a4-150">10</span><span class="sxs-lookup"><span data-stu-id="ac2a4-150">10</span></span>    | <span data-ttu-id="ac2a4-151">Liczba recenzji, które powinny być pokazywane jednocześnie na PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-151">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="ac2a4-152">Przyciski **Następne** i **Poprzednie** są dołączone, dzięki czemu użytkownicy mogą poruszać się po stronach recenzji.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-152">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="ac2a4-153">Histogram ocen — Widok podsumowania</span><span class="sxs-lookup"><span data-stu-id="ac2a4-153">Ratings histogram – Summary view</span></span>

<span data-ttu-id="ac2a4-154">Moduł listy recenzji produktów zawiera miejsce, w którym można dodać moduł histogramu ocen.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-154">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="ac2a4-155">Poniższa ilustracja pokazuje, jak można dodać moduł histogramu ocen w module listy recenzji produktów w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-155">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Dodawanie modułu histogramu ocen w module listy recenzji produktów](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="ac2a4-157">Skonfiguruj witrynę, aby wyświetlała oceny i recenzje</span><span class="sxs-lookup"><span data-stu-id="ac2a4-157">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="ac2a4-158">Wartości konfiguracji ocen i recenzji, takie jak identyfikator dzierżawcy, długość tekstu recenzji i długość tytułu recenzji, są konfigurowane na poziomie witryny.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-158">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="ac2a4-159">Aby skonfigurować witrynę do wyświetlania ocen i recenzji, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-159">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="ac2a4-160">Przejdź do **Widok główny \> Strony**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-160">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="ac2a4-161">Wybierz nazwę swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-161">Select the name of your site.</span></span> 
1. <span data-ttu-id="ac2a4-162">Przejdź do **Zarządzanie witryną \> Możliwości rozszerzania**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-162">Go to **Site management \> Extensibility**.</span></span> 
1. <span data-ttu-id="ac2a4-163">W polu **Maksymalna długość tekstu recenzji**, wpisz maksymalną liczbę znaków, jaką może zawierać tekst recenzji (na przykład **1000**).</span><span class="sxs-lookup"><span data-stu-id="ac2a4-163">In the **Review Text Max Length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="ac2a4-164">W polu **Maksymalna długość tytułu recenzji**, wpisz maksymalną liczbę znaków, jaką może zawierać tytuł recenzji (na przykład **55**).</span><span class="sxs-lookup"><span data-stu-id="ac2a4-164">In the **Review Title Max Length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="ac2a4-165">Wybierz **Zapisz i opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-165">Select **Save and Publish**.</span></span> 

<span data-ttu-id="ac2a4-166">Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-166">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Konfigurowanie witryny, aby wyświetlała oceny i recenzje](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="ac2a4-168">Łączenie oceny produktu z sekcją recenzji w PDP</span><span class="sxs-lookup"><span data-stu-id="ac2a4-168">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="ac2a4-169">Ocena produktu jest wyświetlana pod tytułem produktu u góry PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-169">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="ac2a4-170">Ocenę produktu można skonfigurować tak, aby była połączona z sekcją **Recenzje** tej samej strony PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-170">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="ac2a4-171">Aby połączyć ocenę produktu z sekcją **Recenzje** PDP, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-171">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="ac2a4-172">Otwórz szablon PDP.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-172">Open the PDP template.</span></span> 
1. <span data-ttu-id="ac2a4-173">Przejdź do **Ustawienia modułu kontenera pola zakupu**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-173">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="ac2a4-174">W **Polu zakupu** wybierz opcję **Oceny produktów**, a następnie zaznacz pole wyboru **Połącz kliknięcie z modułem pełnych ocen**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-174">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="ac2a4-175">Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-175">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Łączenie oceny produktu z sekcją recenzji w PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="ac2a4-177">Konfiguruj łącze do strony prywatność i zasady</span><span class="sxs-lookup"><span data-stu-id="ac2a4-177">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="ac2a4-178">Aby skonfigurować link do strony prywatności i zasad, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-178">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="ac2a4-179">Przejdź do **Widok główny \> Strony**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-179">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="ac2a4-180">Wybierz nazwę swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-180">Select the name of your site.</span></span> 
1. <span data-ttu-id="ac2a4-181">Przejdź do **Zarządzanie witryną \> Możliwości rozszerzania**</span><span class="sxs-lookup"><span data-stu-id="ac2a4-181">Go to **Site management \> Extensibility**</span></span>
1. <span data-ttu-id="ac2a4-182">Na karcie **Marszruty** w obszarze **RNR prywatność i zasady** wybierz opcję **Dodaj łącze**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-182">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="ac2a4-183">Jeśli łącze zostało już wprowadzone i ma zostać zamienione, należy zaznaczyć łącze.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-183">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="ac2a4-184">W oknie dialogowym **Dodawj łącze** wybierz łącze do strony prywatność i zasady, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-184">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="ac2a4-185">Wybierz **Zapisz i opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-185">Select **Save and Publish**.</span></span> 

<span data-ttu-id="ac2a4-186">Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ac2a4-186">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Konfiguracja łącza do strony prywatność i zasady](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a><span data-ttu-id="ac2a4-188">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ac2a4-188">Additional resources</span></span>

[<span data-ttu-id="ac2a4-189">Omówienie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="ac2a4-189">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="ac2a4-190">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="ac2a4-190">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="ac2a4-191">Zarządzanie ocenami i recenzjami</span><span class="sxs-lookup"><span data-stu-id="ac2a4-191">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="ac2a4-192">Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="ac2a4-192">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
