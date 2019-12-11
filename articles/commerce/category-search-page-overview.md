---
title: Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania
description: W tym temacie omówiono domyślną stronę docelową kategorii i stronę wyników wyszukiwania w Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 3835502c33fbc63f68f2d6350d805badb3891568
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697297"
---
# <a name="overview-of-default-category-landing-page-and-search-results-page"></a><span data-ttu-id="ecd76-103">Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="ecd76-103">Overview of default category landing page and search results page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ecd76-104">W tym temacie omówiono domyślną stronę docelową kategorii i stronę wyników wyszukiwania w Microsoft Dynamics 365 Commerce e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="ecd76-104">This topic provides an overview of the default category landing page and search results page in Microsoft Dynamics 365 Commerce e-Commerce.</span></span>

## <a name="default-category-landing-page"></a><span data-ttu-id="ecd76-105">Domyślna strona docelowa kategorii</span><span class="sxs-lookup"><span data-stu-id="ecd76-105">Default category landing page</span></span>

<span data-ttu-id="ecd76-106">Domyślna strona docelowa kategorii to strona, do której zazwyczaj są przyjmowane użytkownicy serwisu www, gdy wybierają kategorię w hierarchii nawigacji.</span><span class="sxs-lookup"><span data-stu-id="ecd76-106">The default category landing page is the page that website users typically are taken to when they select a category in the navigation hierarchy.</span></span> <span data-ttu-id="ecd76-107">Strona kategorii umożliwia przeglądanie, a także sortowanie i modyfikowanie produktów skategoryzowanych.</span><span class="sxs-lookup"><span data-stu-id="ecd76-107">The category page lets you browse, and you can also sort and refine the categorized products.</span></span>

![Domyślna strona docelowa kategorii](./media/SimpleCategoryLandingDressCategory.png)

<span data-ttu-id="ecd76-109">U góry strony znajduje się nagłówek, który pokazuje wszystkie kategorie produktów i inne strony, które podzielił kierownik sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ecd76-109">At the top of the page is a header that shows all the product categories and other pages that the merchandising manager has categorized.</span></span> <span data-ttu-id="ecd76-110">Konfiguracja jest wykonana w ramach konfiguracji hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="ecd76-110">Configuration is done as part of the configuration of the channel navigation hierarchy.</span></span> <span data-ttu-id="ecd76-111">Na dole strony znajduje się stopka zawierająca szybkie linki do różnych tematów, które mogą zainteresować kupującego.</span><span class="sxs-lookup"><span data-stu-id="ecd76-111">At the bottom of the page is a footer that includes quick links to various topics that a shopper might be interested in.</span></span>

<span data-ttu-id="ecd76-112">Następujące składniki są istotne dla danej kategorii:</span><span class="sxs-lookup"><span data-stu-id="ecd76-112">The following components are essential for a category:</span></span>

- <span data-ttu-id="ecd76-113">**Kafelki umieszczenia produktu** pokazują produkty, które zostały zdefiniowane przez Menedżera ds. merchandisingu w kategorii jako część konfiguracji hierarchii nawigacji.</span><span class="sxs-lookup"><span data-stu-id="ecd76-113">**Product placement tiles** show the products that the merchandising manager has defined in a category as part of the configuration of the navigation hierarchy.</span></span>
- <span data-ttu-id="ecd76-114">**Elementy uściślające i podsumowanie wyborów** są filtrami, które dostarczają liczników i służą do poprawiania pozycji.</span><span class="sxs-lookup"><span data-stu-id="ecd76-114">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="ecd76-115">Menedżer ds. merchandisingu konfiguruje je jako część konfiguracji metadanych związanych z kategoriami kanału i atrybutami produktu.</span><span class="sxs-lookup"><span data-stu-id="ecd76-115">The merchandising manager configures them as part of the configuration of the metadata related to channel categories and product attributes.</span></span>
- <span data-ttu-id="ecd76-116">**Opcje sortowania** są używane przez odwiedzających witrynę sieci Web do sortowania produktów.</span><span class="sxs-lookup"><span data-stu-id="ecd76-116">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="ecd76-117">Domyślnie dostępne są następujące opcje sortowania:</span><span class="sxs-lookup"><span data-stu-id="ecd76-117">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="ecd76-118">Cena – od najniższej do najwyższej</span><span class="sxs-lookup"><span data-stu-id="ecd76-118">Price – low to high</span></span>
    - <span data-ttu-id="ecd76-119">Cena – od najwyższej do najniższej</span><span class="sxs-lookup"><span data-stu-id="ecd76-119">Price – high to low</span></span>
    - <span data-ttu-id="ecd76-120">Nazwa produktu – \[A-Z\]</span><span class="sxs-lookup"><span data-stu-id="ecd76-120">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="ecd76-121">Nazwa produktu – \[Z-A\]</span><span class="sxs-lookup"><span data-stu-id="ecd76-121">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="ecd76-122">Ocena – od najniższej do najwyższej</span><span class="sxs-lookup"><span data-stu-id="ecd76-122">Ratings – low to high</span></span>
    - <span data-ttu-id="ecd76-123">Ocena – od najwyższej do najniższej</span><span class="sxs-lookup"><span data-stu-id="ecd76-123">Ratings – high to low</span></span>

- <span data-ttu-id="ecd76-124">**Podział na strony** umożliwia osobom odwiedzającym witrynę przechodzenie z jednej strony skategoryzowanych wyników produktów na inną stronę.</span><span class="sxs-lookup"><span data-stu-id="ecd76-124">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="ecd76-125">**Licznik całkowity** podaje całkowitą liczbę produktów zdefiniowanych w kategorii.</span><span class="sxs-lookup"><span data-stu-id="ecd76-125">**Total count** provides the total number of products that are defined in a category.</span></span>

## <a name="enrich-a-category-landing-page"></a><span data-ttu-id="ecd76-126">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="ecd76-126">Enrich a category landing page</span></span>

<span data-ttu-id="ecd76-127">Jeśli chcesz, aby strona docelowa kategorii zawierała bardziej dostosowane doświadczenie w odniesieniu do konkretnej kategorii, możesz „wzbogacić” stronę do tej kategorii.</span><span class="sxs-lookup"><span data-stu-id="ecd76-127">If you want a category landing page to have a more tailored experience for a specific category, you can "enrich" the category landing page for that category.</span></span> <span data-ttu-id="ecd76-128">Na przykład można dodać marketingowy materiał wideo i kilka opowieści kategorii, aby uzyskać uwagę klienta.</span><span class="sxs-lookup"><span data-stu-id="ecd76-128">For example, you can add a marketing video and some category storytelling to get the shopper's attention.</span></span> <span data-ttu-id="ecd76-129">Aby uzyskać więcej informacji, zapoznaj się z tematem [Wzbogacanie strony docelowej kategorii](enrich-category-page.md).</span><span class="sxs-lookup"><span data-stu-id="ecd76-129">For more information, see [Enrich a category landing page](enrich-category-page.md).</span></span>

![Wzbogacona strona docelowa kategorii](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a><span data-ttu-id="ecd76-131">Automatyczne sugerowanie i wyszukiwanie stron wyników</span><span class="sxs-lookup"><span data-stu-id="ecd76-131">Auto-suggest and search results pages</span></span>

<span data-ttu-id="ecd76-132">Użytkownicy witryny sieci Web mogą eksplorować witrynę, przechodząc do kategorii z hierarchii nawigacji lub wprowadzając wyszukiwany termin w polu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ecd76-132">Website users can explore a site either by going to a category from the navigation hierarchy or by entering a search term in the search field.</span></span>

<span data-ttu-id="ecd76-133">Gdy tylko użytkownicy rozpoczną wpisywanie pola wyszukiwania, będą mieć funkcję automatycznego sugerowania, która sugeruje terminy wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ecd76-133">As soon as users start to type in the search field, they experience the immersive auto-suggest functionality that suggests search terms.</span></span>

<span data-ttu-id="ecd76-134">Oto kilka typów sugestii, które mogą być wyświetlane:</span><span class="sxs-lookup"><span data-stu-id="ecd76-134">Here are some of the types of suggestions that might be shown:</span></span>

- <span data-ttu-id="ecd76-135">**Słowa kluczowe** służą do wyszukiwania towarów we wszystkich produktach w danym kanale.</span><span class="sxs-lookup"><span data-stu-id="ecd76-135">**Keywords** are used to find items across all products that are assorted to the channel.</span></span>
- <span data-ttu-id="ecd76-136">**Produkty** dostarczają bezpośrednich łączy do strony Szczegóły produktu.</span><span class="sxs-lookup"><span data-stu-id="ecd76-136">**Products** provide direct links to the product details page.</span></span>
- <span data-ttu-id="ecd76-137">**Sugestie wyszukiwania kategorii objętej zakresem** mają różne kategorie i umożliwiają użytkownikom wyszukiwanie słów kluczowych w określonych kategoriach.</span><span class="sxs-lookup"><span data-stu-id="ecd76-137">**Scoped category search suggestions** list various categories and let users search for the keyword in a specific category.</span></span>

![immersyjna automatyczna sugestia](./media/ImmersiveAutoSuggestUX.png)

<span data-ttu-id="ecd76-139">Gdy użytkownicy wybiorą jedną z propozycji wyszukiwania słowa kluczowego lub kategorii lub gdy nie ma podanych sugestii dla wyszukiwanego hasła, zostają przekierowani na stronę wyników wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ecd76-139">When users select one of the keyword or scoped category search suggestions, or when there are no suggestions for the search term that they enter, they are redirected to a search results page.</span></span> <span data-ttu-id="ecd76-140">Użytkownicy mogą następnie przeglądać, sortować i udoskonalać listę wyników wyszukiwania, aby znaleźć żądany element.</span><span class="sxs-lookup"><span data-stu-id="ecd76-140">The users can then browse, sort, and refine the list of search results to find the desired item.</span></span>

![Stona docelowa wyszukiwania](./media/SearchLanding.png)

<span data-ttu-id="ecd76-142">Następujące składniki są istotne dla strony wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="ecd76-142">The following components are essential for a search results page:</span></span>

- <span data-ttu-id="ecd76-143">**Kafelki umieszczenia produktu** pokazują produkty dla wyszukiwania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ecd76-143">**Product placement tiles** show the products for the user's search.</span></span> <span data-ttu-id="ecd76-144">Domyślnie te kafelki są sortowane według punktacji Relevancy wyszukiwanej w chmurze dla wyszukiwania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ecd76-144">By default, these tiles are sorted by the cloud-powered search relevancy score for the user search.</span></span>
- <span data-ttu-id="ecd76-145">**Elementy uściślające i podsumowanie wyborów** są filtrami, które dostarczają liczników i służą do poprawiania pozycji.</span><span class="sxs-lookup"><span data-stu-id="ecd76-145">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="ecd76-146">Menedżer ds. merchandisingu konfiguruje je jako część konfiguracji metadanych związanych z „kategoriami kanału i atrybutami produktu”.</span><span class="sxs-lookup"><span data-stu-id="ecd76-146">The merchandising manager configures them as part of the configuration of the "channel categories and product attributes" metadata.</span></span>
- <span data-ttu-id="ecd76-147">**Opcje sortowania** są używane przez odwiedzających witrynę sieci Web do sortowania produktów.</span><span class="sxs-lookup"><span data-stu-id="ecd76-147">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="ecd76-148">Domyślnie dostępne są następujące opcje sortowania:</span><span class="sxs-lookup"><span data-stu-id="ecd76-148">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="ecd76-149">Cena – od najniższej do najwyższej</span><span class="sxs-lookup"><span data-stu-id="ecd76-149">Price – low to high</span></span>
    - <span data-ttu-id="ecd76-150">Cena – od najwyższej do najniższej</span><span class="sxs-lookup"><span data-stu-id="ecd76-150">Price – high to low</span></span>
    - <span data-ttu-id="ecd76-151">Nazwa produktu – \[A-Z\]</span><span class="sxs-lookup"><span data-stu-id="ecd76-151">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="ecd76-152">Nazwa produktu – \[Z-A\]</span><span class="sxs-lookup"><span data-stu-id="ecd76-152">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="ecd76-153">Ocena – od najniższej do najwyższej</span><span class="sxs-lookup"><span data-stu-id="ecd76-153">Ratings – low to high</span></span>
    - <span data-ttu-id="ecd76-154">Ocena – od najwyższej do najniższej</span><span class="sxs-lookup"><span data-stu-id="ecd76-154">Ratings – high to low</span></span>
    - <span data-ttu-id="ecd76-155">Domyślnie</span><span class="sxs-lookup"><span data-stu-id="ecd76-155">Default</span></span>

- <span data-ttu-id="ecd76-156">**Podział na strony** umożliwia osobom odwiedzającym witrynę przechodzenie z jednej strony skategoryzowanych wyników produktów na inną stronę.</span><span class="sxs-lookup"><span data-stu-id="ecd76-156">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="ecd76-157">**Licznik całkowity** podaje całkowitą liczbę produktów zdefiniowanych w kategorii i wyników pasujących do kryteriów wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ecd76-157">**Total count** provides the total number of products that are defined in a category and that match the search criteria.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ecd76-158">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ecd76-158">Additional resources</span></span>

[<span data-ttu-id="ecd76-159">Omówienie strony głównej</span><span class="sxs-lookup"><span data-stu-id="ecd76-159">Overview of the home page</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="ecd76-160">Omówienie stron szczegółów produktów</span><span class="sxs-lookup"><span data-stu-id="ecd76-160">Overview of product details pages</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="ecd76-161">Omówienie stron koszyka i realizacji zamówienia</span><span class="sxs-lookup"><span data-stu-id="ecd76-161">Overview of cart and checkout pages</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="ecd76-162">Omówienie stron zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="ecd76-162">Overview of account management pages</span></span>](quick-tour-account-management.md)

