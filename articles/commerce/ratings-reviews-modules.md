---
title: Moduły ocen i recenzji
description: W tym temacie opisano moduły ocen i recenzji używane na stronach szczegółów produktów w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: 26658ebdbc70613baf30c344664133b9cf5911ca
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243776"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="87e15-103">Moduły ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="87e15-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="87e15-104">W tym temacie opisano moduły ocen i recenzji używane na stronach szczegółów produktów (PDP) w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="87e15-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="87e15-105">Oceny i Recenzje w witrynach e-Commerce umożliwiają klientom zapoznanie się z produktami przed podjęciem decyzji o zakupie oraz stanowią mechanizm zbierania danych o opiniach klientów o tych produktach..</span><span class="sxs-lookup"><span data-stu-id="87e15-105">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="87e15-106">Oceny są wyświetlane na stronach list produktów, na stronach list kategorii, na stronach wyników wyszukiwania oraz na innych stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="87e15-106">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="87e15-107">Histogramy ocen i recenzje produktów są wyświetlane na stronach PDP.</span><span class="sxs-lookup"><span data-stu-id="87e15-107">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="87e15-108">Przez naciśnięcie przycisku **Napisz recenzję** klienci mogą przesyłać oceny i recenzje produktu.</span><span class="sxs-lookup"><span data-stu-id="87e15-108">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="87e15-109">Te funkcje PDP są kontrolowane przez moduły ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="87e15-109">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="87e15-110">Moduły ocen i recenzji na stronach PDP</span><span class="sxs-lookup"><span data-stu-id="87e15-110">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="87e15-111">Na stronach PDP w trzech modułach są wyświetlane podsumowania ocen i recenzji:</span><span class="sxs-lookup"><span data-stu-id="87e15-111">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="87e15-112">Napisz moduł recenzji</span><span class="sxs-lookup"><span data-stu-id="87e15-112">Write review module</span></span>
- <span data-ttu-id="87e15-113">Moduł listy recenzji produktów</span><span class="sxs-lookup"><span data-stu-id="87e15-113">Product reviews list module</span></span>
- <span data-ttu-id="87e15-114">Moduł histogramu ocen</span><span class="sxs-lookup"><span data-stu-id="87e15-114">Ratings histogram module</span></span>
 
<span data-ttu-id="87e15-115">Na poniższej ilustracji przedstawiono jak moduły ocen i recenzji wyglądają na stronach PDP.</span><span class="sxs-lookup"><span data-stu-id="87e15-115">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Moduły ocen i recenzji na stronach PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="87e15-117">Aby uzyskać informacje na temat optymalizowania szablonów i układów PDP, tak aby można było udostępniać konfiguracje dla modułów ocen i recenzji na wielu stronach PDP w witrynie e-Commerce, należy zapoznać się z [Omówienie szablonów i układów](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="87e15-117">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="87e15-118">Na poniższej ilustracji pokazano, jak w oknie dialogowym **Dodaj moduł** są prezentowane moduły ocen i recenzji w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="87e15-118">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="87e15-119">![Dodaj moduł okna dialogowego](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="87e15-119">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="87e15-120">Napisz moduł recenzji</span><span class="sxs-lookup"><span data-stu-id="87e15-120">Write review module</span></span>

<span data-ttu-id="87e15-121">Moduł zapisu recenzji zawiera przycisk **Napisz recenzję**, który pozwala użytkownikom zalogować się, przypisać ocenę i napisać recenzję produktu.</span><span class="sxs-lookup"><span data-stu-id="87e15-121">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="87e15-122">Moduł ten pozwala również edytować wcześniej przesłane oceny lub recenzje.</span><span class="sxs-lookup"><span data-stu-id="87e15-122">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="87e15-123">Ten moduł zazwyczaj pojawia się nad histogramem ocen i modułami listy recenzji produktów na PDP.</span><span class="sxs-lookup"><span data-stu-id="87e15-123">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="87e15-124">Poniższa ilustracja pokazuje okno dialogowe **Napisz recenzję**, które pojawia się, gdy klient wybierze **Napisz recenzję**.</span><span class="sxs-lookup"><span data-stu-id="87e15-124">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="87e15-125">Odbiorca może użyć tego okna dialogowego do przesłania ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="87e15-125">The customer can use this dialog box to submit a rating and a review.</span></span>
<span data-ttu-id="87e15-126">![Napisz okno dialogowe recenzji](media/rnr-eCommerce-write-review-module.png) W poniższej tabeli przedstawiono właściwość modułu pisania recenzji, którą należy skonfigurować w narzędziu do tworzenia treści.</span><span class="sxs-lookup"><span data-stu-id="87e15-126">![Write a review dialog box](media/rnr-eCommerce-write-review-module.png) The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>
| <span data-ttu-id="87e15-127">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="87e15-127">Property name</span></span> | <span data-ttu-id="87e15-128">Wartość</span><span class="sxs-lookup"><span data-stu-id="87e15-128">Value</span></span>        | <span data-ttu-id="87e15-129">Opis właściwości</span><span class="sxs-lookup"><span data-stu-id="87e15-129">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="87e15-130">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="87e15-130">Name</span></span>          | <span data-ttu-id="87e15-131">Napisz recenzję</span><span class="sxs-lookup"><span data-stu-id="87e15-131">Write review</span></span> | <span data-ttu-id="87e15-132">Nazwa modułu pisania recenzji.</span><span class="sxs-lookup"><span data-stu-id="87e15-132">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="87e15-133">Moduł histogramu ocen</span><span class="sxs-lookup"><span data-stu-id="87e15-133">Ratings histogram module</span></span>

<span data-ttu-id="87e15-134">W module histogramu ocen jest wyświetlany histogram klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="87e15-134">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="87e15-135">Ten moduł zwykle pojawia się między modułem recenzji zapisu a modułem listy recenzji produktów na PDP.</span><span class="sxs-lookup"><span data-stu-id="87e15-135">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="87e15-136">Moduł histogramu ocen nie wymaga konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="87e15-136">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="87e15-137">Wystarczy dodać moduł do szablonu PDP.</span><span class="sxs-lookup"><span data-stu-id="87e15-137">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="87e15-138">Poniższe ilustracje pokazują, jak wygląda szablon PDP w Dynamics 365 Commerce, gdy moduły ocen i recenzji są skonfigurowane do wyświetlania na PDP.</span><span class="sxs-lookup"><span data-stu-id="87e15-138">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="87e15-139">![Szablon PDP, gdy oceny i recenzje są skonfigurowane do wyświetlania na PDP](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="87e15-139">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="87e15-140">Moduł listy recenzji produktów</span><span class="sxs-lookup"><span data-stu-id="87e15-140">Product reviews list module</span></span>

<span data-ttu-id="87e15-141">Moduł listy recenzji produktów pokazuje listę recenzji produktów wraz z opcjami sortowania, filtrowania i paginacji.</span><span class="sxs-lookup"><span data-stu-id="87e15-141">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="87e15-142">Ten moduł zazwyczaj znajduje się po module histogramu ocen na PDP.</span><span class="sxs-lookup"><span data-stu-id="87e15-142">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="87e15-143">Poniższa tabela pokazuje właściwości modułu listy recenzji produktów, które należy skonfigurować w narzędziu do tworzenia treści.</span><span class="sxs-lookup"><span data-stu-id="87e15-143">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="87e15-144">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="87e15-144">Property name</span></span>              | <span data-ttu-id="87e15-145">Wartość</span><span class="sxs-lookup"><span data-stu-id="87e15-145">Value</span></span> | <span data-ttu-id="87e15-146">Opis właściwości</span><span class="sxs-lookup"><span data-stu-id="87e15-146">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="87e15-147">Recenzje pokazywane na każdej stronie</span><span class="sxs-lookup"><span data-stu-id="87e15-147">Reviews shown on each page</span></span> | <span data-ttu-id="87e15-148">10</span><span class="sxs-lookup"><span data-stu-id="87e15-148">10</span></span>    | <span data-ttu-id="87e15-149">Liczba recenzji, które powinny być pokazywane jednocześnie na PDP.</span><span class="sxs-lookup"><span data-stu-id="87e15-149">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="87e15-150">Przyciski **Następne** i **Poprzednie** są dołączone, dzięki czemu użytkownicy mogą poruszać się po stronach recenzji.</span><span class="sxs-lookup"><span data-stu-id="87e15-150">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="87e15-151">Histogram ocen — Widok podsumowania</span><span class="sxs-lookup"><span data-stu-id="87e15-151">Ratings histogram – Summary view</span></span>

<span data-ttu-id="87e15-152">Moduł listy recenzji produktów zawiera miejsce, w którym można dodać moduł histogramu ocen.</span><span class="sxs-lookup"><span data-stu-id="87e15-152">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="87e15-153">Poniższa ilustracja pokazuje, jak można dodać moduł histogramu ocen w module listy recenzji produktów w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="87e15-153">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Dodawanie modułu histogramu ocen w module listy recenzji produktów](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="87e15-155">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="87e15-155">Additional resources</span></span>

[<span data-ttu-id="87e15-156">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="87e15-156">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="87e15-157">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="87e15-157">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="87e15-158">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="87e15-158">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="87e15-159">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="87e15-159">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="87e15-160">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="87e15-160">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="87e15-161">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="87e15-161">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="87e15-162">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="87e15-162">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]