---
title: Omówienie stron szczegółów produktów
description: W tym temacie omówiono strony ze szczegółowymi informacjami o produkcie (PDP) w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3b02d50adbfcda27d590bcb87fd9669d67d4a01c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697872"
---
# <a name="overview-of-product-details-pages"></a><span data-ttu-id="18093-103">Omówienie stron szczegółów produktów</span><span class="sxs-lookup"><span data-stu-id="18093-103">Overview of product details pages</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="18093-104">W tym temacie omówiono strony ze szczegółowymi informacjami o produkcie (PDP) w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="18093-104">This topic provides an overview of product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="18093-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="18093-105">Overview</span></span>

<span data-ttu-id="18093-106">PDP dostarcza szczegółowych informacji o produkcie, a klienci wybierają opcje produktu, takie jak rozmiar, styl i kolor.</span><span class="sxs-lookup"><span data-stu-id="18093-106">A PDP provides detailed information about a product, and lets customers select product options such as a size, style, and color.</span></span> <span data-ttu-id="18093-107">PDP powinien prezentować wszystkie informacje o produktach, których wymaga klient w celu podjęcia decyzji o zakupie.</span><span class="sxs-lookup"><span data-stu-id="18093-107">A PDP should showcase all the product information that a customer requires to make a purchase decision.</span></span>

<span data-ttu-id="18093-108">Na poniższe ilustracji pokazano przykład PDP.</span><span class="sxs-lookup"><span data-stu-id="18093-108">The following illustration shows an example of a PDP.</span></span>

![Przykład strony ze szczegółami dotyczącymi produktu](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a><span data-ttu-id="18093-110">Moduły nagłówka i stopki</span><span class="sxs-lookup"><span data-stu-id="18093-110">Header and footer modules</span></span>

<span data-ttu-id="18093-111">U góry PDP znajduje się nagłówek pokazujący wszystkie kategorie produktów i inne strony, które sprzedawca chce przejrzeć.</span><span class="sxs-lookup"><span data-stu-id="18093-111">The top of a PDP has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="18093-112">Dolna część strony zawiera stopkę zawierającą szybkie łącza do różnych tematów, które mogą być przedmiotem zainteresowania odbiorców.</span><span class="sxs-lookup"><span data-stu-id="18093-112">The bottom of the page has a footer that contains quick links to various topics that might interest customers.</span></span>

## <a name="buy-box-module"></a><span data-ttu-id="18093-113">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="18093-113">Buy box module</span></span>

<span data-ttu-id="18093-114">Najważniejszym modułem układu PDP jest moduł pudełka zakupu.</span><span class="sxs-lookup"><span data-stu-id="18093-114">The most important module on a PDP is the buy box module.</span></span> <span data-ttu-id="18093-115">Dlatego jest to pierwszy element w sekcji głównej strony.</span><span class="sxs-lookup"><span data-stu-id="18093-115">Therefore, it's the first item in the main section of the page.</span></span> <span data-ttu-id="18093-116">Moduł pudełka z kupowaniem jest modułem kontenera i obsługuje kilka modułów zawierających najważniejsze informacje o produkcie.</span><span class="sxs-lookup"><span data-stu-id="18093-116">A buy box module is a container module and hosts several modules that contain the most important information about the product.</span></span> <span data-ttu-id="18093-117">Informacje te obejmują nazwę produktu, obrazy produktów, opis, cenę i oceny produktów.</span><span class="sxs-lookup"><span data-stu-id="18093-117">This information includes the product name, product images, the description, the price, and product ratings.</span></span>

<span data-ttu-id="18093-118">Moduł pola zakupu pozwala odbiorcy wybrać opcje produktu (np. rozmiar, styl i kolor) i dodać produkt do koszyka.</span><span class="sxs-lookup"><span data-stu-id="18093-118">The buy box module lets the customer select product options (for example, a size, style, and color) and add the product to the cart.</span></span> <span data-ttu-id="18093-119">Umożliwia również kupowanie produktu w trybie online i pobieranie go w sklepie.</span><span class="sxs-lookup"><span data-stu-id="18093-119">It also lets the customer buy the product online and pick it up in a store.</span></span> <span data-ttu-id="18093-120">Moduł kupowanie w trybie online i pobierz w sklepie używa integracji z interfejsami programowania aplikacji (API) mapy Bing w celu znalezienia bliskich sklepów lub sklepów w innej lokalizacji określanej przez odbiorcę</span><span class="sxs-lookup"><span data-stu-id="18093-120">The buy online and pick up in store module uses integration with Bing Maps application programming interfaces (APIs) to find nearby stores or stores in another location that the customer specifies.</span></span>

<span data-ttu-id="18093-121">Moduł pola zakupu wymaga identyfikatora produktu.</span><span class="sxs-lookup"><span data-stu-id="18093-121">A buy box module requires a product ID.</span></span> <span data-ttu-id="18093-122">Ten identyfikator jest pochodną z kontekstu strony.</span><span class="sxs-lookup"><span data-stu-id="18093-122">This ID is derived from the page context.</span></span> <span data-ttu-id="18093-123">Jeśli do strony, w której kontekst strony nie zawiera identyfikatora produktu, zostanie dodany moduł pola zakupu, informacje te nie zostaną poprawnie zachowane.</span><span class="sxs-lookup"><span data-stu-id="18093-123">If a buy box module is added to a page where the page context doesn't include a product ID, it won't render the information correctly.</span></span>

## <a name="product-specifications-module"></a><span data-ttu-id="18093-124">Moduł specyfikacji produktu</span><span class="sxs-lookup"><span data-stu-id="18093-124">Product specifications module</span></span>

<span data-ttu-id="18093-125">Moduł specyfikacji produktu może służyć do prezentowania dodatkowych szczegółów dotyczących produktu.</span><span class="sxs-lookup"><span data-stu-id="18093-125">The product specifications module can be used to showcase additional details about the product.</span></span> <span data-ttu-id="18093-126">Te szczegóły są pobierane z atrybutów produktów w Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="18093-126">These details are taken from product attributes in Dynamics 365 Retail.</span></span> <span data-ttu-id="18093-127">Moduł specyfikacje produktu pokazuje każdy atrybut, w którym właściwość **widoczne** ma wartość **prawda**.</span><span class="sxs-lookup"><span data-stu-id="18093-127">The product specifications module shows every attribute where the **visible** property is set to **true**.</span></span> <span data-ttu-id="18093-128">Do pobrania atrybutów produktu wymagana jest nazwa produktu.</span><span class="sxs-lookup"><span data-stu-id="18093-128">It requires a product ID to retrieve the product attributes.</span></span>

## <a name="recommendations-module"></a><span data-ttu-id="18093-129">Moduł rekomendacji</span><span class="sxs-lookup"><span data-stu-id="18093-129">Recommendations module</span></span>

<span data-ttu-id="18093-130">Najważniejszym modułem układu PDP jest moduł rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="18093-130">The recommendations module is an important module on a PDP.</span></span> <span data-ttu-id="18093-131">Podczas przeglądania produktów przez użytkowników należy przedstawić im więcej opcji, dzięki czemu mogą one znaleźć poprawny produkt i dokonać zakupu.</span><span class="sxs-lookup"><span data-stu-id="18093-131">While customers browse for products, more product options should be presented to them, so that they can find the correct product and make a purchase.</span></span> <span data-ttu-id="18093-132">Rekomendacje pomagają klientom w łatwejszym odnajdywaniu powiązanych treści i w dalszym ciągu kupować.</span><span class="sxs-lookup"><span data-stu-id="18093-132">Recommendations help customers easily discover related content and continue to shop.</span></span>

<span data-ttu-id="18093-133">Dostępne są różne typy list rekomendacji:</span><span class="sxs-lookup"><span data-stu-id="18093-133">Different types of recommendation lists are available:</span></span>

- <span data-ttu-id="18093-134">Lista **Klientom podoba się również** jest oparta na nauczeniu maszynowym.</span><span class="sxs-lookup"><span data-stu-id="18093-134">The **People also like** list is based on machine learning.</span></span> <span data-ttu-id="18093-135">Zawiera ona historię transakcji innych odbiorców w celu dostarczenia zaleceń.</span><span class="sxs-lookup"><span data-stu-id="18093-135">It uses the transaction history of other customers to provide recommendations.</span></span> <span data-ttu-id="18093-136">Ta lista jest generowana przez usługę rekomendacji i przypomina listę „Klienci, krórzy kupili ten produkt, kupili również...”.</span><span class="sxs-lookup"><span data-stu-id="18093-136">This list is generated by the recommendations service and resembles "Customers who bought this also bought..." lists.</span></span> <span data-ttu-id="18093-137">Do wygenerowania tej listy wymagany jest identyfikator produktu.</span><span class="sxs-lookup"><span data-stu-id="18093-137">A product ID is required to generate this list.</span></span>
- <span data-ttu-id="18093-138">Listę **pokrewną** można skonfigurować dla produktu w sieci Retail.</span><span class="sxs-lookup"><span data-stu-id="18093-138">A **Related** list can be configured for a product in Retail.</span></span> <span data-ttu-id="18093-139">Na przykład w przypadku brązowej skórzanej torebki można skonfigurować więcej torebek skórzanych lub zaprojektowanych do celów związanych z podróżą dla powiązanej listy.</span><span class="sxs-lookup"><span data-stu-id="18093-139">For example, for a brown leather travel handbag, more handbags that are leather-based or designed for travel purposes can be configured for the related list.</span></span> <span data-ttu-id="18093-140">Inne typy list pokrewnych, takie jak **akcesoria** i **podobne do tego**, można również konfigurować w module Retail.</span><span class="sxs-lookup"><span data-stu-id="18093-140">Other types of related lists, such as **Accessories** and **More like this**, can also be configured in Retail.</span></span> <span data-ttu-id="18093-141">Do wygenerowania tej listy wymagany jest identyfikator produktu.</span><span class="sxs-lookup"><span data-stu-id="18093-141">A product ID is required to generate this list.</span></span> <span data-ttu-id="18093-142">W związku z tym, jeśli w kontekście strony zostanie dodany do strony głównej, lista nie będzie zawierała identyfikatora produktu.</span><span class="sxs-lookup"><span data-stu-id="18093-142">Therefore, if it's added to a home page, where the page context doesn't include a product ID, the list will be empty.</span></span>
- <span data-ttu-id="18093-143">Algorithmically wygenerowane listy rekomendacji, takie jak **Trendy**, **Bestsellery** i **Nowości**, mogą być używane na PDPs.</span><span class="sxs-lookup"><span data-stu-id="18093-143">Algorithmically generated recommendation lists, such as **Trending**, **Best Selling**, and **New**, can be used on PDPs.</span></span> <span data-ttu-id="18093-144">Chociaż te listy mogą nie być bezpośrednio związane z produktem PDP, są one kolejnym sposobem ułatwienia klientom znalezienia produktów, które mogą je zainteresować.</span><span class="sxs-lookup"><span data-stu-id="18093-144">Although these lists might not be directly related to the product on the PDP, they are another way to help customers find products that might interest them.</span></span> <span data-ttu-id="18093-145">Te typy list nie wymagają identyfikatora produktu.</span><span class="sxs-lookup"><span data-stu-id="18093-145">These types of lists don't require a product ID.</span></span> <span data-ttu-id="18093-146">Są to listy ogólne, które są generowane na podstawie wzorców zakupów w witrynie.</span><span class="sxs-lookup"><span data-stu-id="18093-146">They are generic lists that are generated based on shopping patterns across the site.</span></span>
- <span data-ttu-id="18093-147">Listy redakcyjne są ręcznie wyselekcjonowane.</span><span class="sxs-lookup"><span data-stu-id="18093-147">Editorial lists are manually curated lists.</span></span> <span data-ttu-id="18093-148">Na przykład detalista może zdecydować o ręcznym zaprezentowania list produktów, które chce prezentować.</span><span class="sxs-lookup"><span data-stu-id="18093-148">For example, a retailer might decide to manually curate lists of products that it wants to showcase.</span></span>

## <a name="ratings-and-reviews-module"></a><span data-ttu-id="18093-149">Moduły ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="18093-149">Ratings and reviews module</span></span>

<span data-ttu-id="18093-150">Moduł oceny i Recenzje zawiera oceny i przeglądy, które zostały udostępnione przez innych odbiorców.</span><span class="sxs-lookup"><span data-stu-id="18093-150">The ratings and reviews module shows ratings and reviews that have been provided by other customers.</span></span> <span data-ttu-id="18093-151">Umożliwia także wpisywanie przez odbiorcę własnego przeglądu produktu.</span><span class="sxs-lookup"><span data-stu-id="18093-151">It also lets a customer write his or her own review of the product.</span></span> <span data-ttu-id="18093-152">Ponadto zawiera on histogram przedstawiający trend klasyfikacji produktu.</span><span class="sxs-lookup"><span data-stu-id="18093-152">Additionally, it includes a histogram that shows the ratings trend for the product.</span></span> <span data-ttu-id="18093-153">Aby uzyskać więcej szczegółowych informacji, zobacz [Omówienie ocen i recenzji](ratings-reviews-overview.md).</span><span class="sxs-lookup"><span data-stu-id="18093-153">For more details, see [Ratings and reviews overview](ratings-reviews-overview.md).</span></span>

## <a name="marketing-modules"></a><span data-ttu-id="18093-154">Moduły marketingu</span><span class="sxs-lookup"><span data-stu-id="18093-154">Marketing modules</span></span>

<span data-ttu-id="18093-155">Jeśli zawartość marketingowa jest unikatowa dla określonego produktu, do PDP można dodać dowolny moduł marketingowy.</span><span class="sxs-lookup"><span data-stu-id="18093-155">If marketing content is unique to a specific product, any marketing module can be added to the PDP.</span></span> <span data-ttu-id="18093-156">Moduły marketingowe można dodawać do PDP przez „wzbogacanie” strony.</span><span class="sxs-lookup"><span data-stu-id="18093-156">You can add marketing modules to a PDP by "enriching" the page.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="18093-157">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="18093-157">Additional resources</span></span>

[<span data-ttu-id="18093-158">Omówienie strony głównej</span><span class="sxs-lookup"><span data-stu-id="18093-158">Overview of the home page</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="18093-159">Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="18093-159">Overview of default category landing page and search results page</span></span>](category-search-page-overview.md)

[<span data-ttu-id="18093-160">Omówienie stron koszyka i realizacji zamówienia</span><span class="sxs-lookup"><span data-stu-id="18093-160">Overview of cart and checkout pages</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="18093-161">Omówienie stron zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="18093-161">Overview of account management pages</span></span>](quick-tour-account-management.md)
