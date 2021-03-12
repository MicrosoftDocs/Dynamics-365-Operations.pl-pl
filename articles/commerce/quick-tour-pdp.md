---
title: Omówienie stron szczegółów produktów
description: W tym temacie omówiono strony ze szczegółowymi informacjami o produkcie (PDP) w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b0f50b4e7b78f4a5b9fe674a101476879923e10d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979835"
---
# <a name="product-details-pages-overview"></a><span data-ttu-id="4437e-103">Omówienie stron szczegółów produktów</span><span class="sxs-lookup"><span data-stu-id="4437e-103">Product details pages overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4437e-104">W tym temacie omówiono strony ze szczegółowymi informacjami o produkcie (PDP) w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4437e-104">This topic provides an overview of product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4437e-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="4437e-105">Overview</span></span>

<span data-ttu-id="4437e-106">PDP dostarcza szczegółowych informacji o produkcie, a klienci wybierają opcje produktu, takie jak rozmiar, styl i kolor.</span><span class="sxs-lookup"><span data-stu-id="4437e-106">A PDP provides detailed information about a product, and lets customers select product options such as a size, style, and color.</span></span> <span data-ttu-id="4437e-107">PDP powinien prezentować wszystkie informacje o produktach, których wymaga klient w celu podjęcia decyzji o zakupie.</span><span class="sxs-lookup"><span data-stu-id="4437e-107">A PDP should showcase all the product information that a customer requires to make a purchase decision.</span></span>

<span data-ttu-id="4437e-108">Na poniższe ilustracji pokazano przykład PDP.</span><span class="sxs-lookup"><span data-stu-id="4437e-108">The following illustration shows an example of a PDP.</span></span>

![Przykład strony ze szczegółami dotyczącymi produktu](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a><span data-ttu-id="4437e-110">Moduły nagłówka i stopki</span><span class="sxs-lookup"><span data-stu-id="4437e-110">Header and footer modules</span></span>

<span data-ttu-id="4437e-111">U góry PDP znajduje się nagłówek pokazujący wszystkie kategorie produktów i inne strony, które sprzedawca chce przejrzeć.</span><span class="sxs-lookup"><span data-stu-id="4437e-111">The top of a PDP has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="4437e-112">Dolna część strony zawiera stopkę zawierającą szybkie łącza do różnych tematów, które mogą być przedmiotem zainteresowania odbiorców.</span><span class="sxs-lookup"><span data-stu-id="4437e-112">The bottom of the page has a footer that contains quick links to various topics that might interest customers.</span></span>

## <a name="buy-box-module"></a><span data-ttu-id="4437e-113">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="4437e-113">Buy box module</span></span>

<span data-ttu-id="4437e-114">Najważniejszym modułem układu PDP jest moduł pudełka zakupu, który jest wyświetlany jako pierwszy element w sekcji głównej strony.</span><span class="sxs-lookup"><span data-stu-id="4437e-114">The most important module on a PDP is the buy box module, which appears as the first item in the main section of the page.</span></span> <span data-ttu-id="4437e-115">W module pole zakupu są wyświetlane ważne informacje dotyczące produktu, takie jak nazwa produktu, opis produktu, cena produktu, obrazy produktów i oceny produktów.</span><span class="sxs-lookup"><span data-stu-id="4437e-115">A buy box module shows important product information, such as the product name, the product description, the product price, product images, and product ratings.</span></span>

<span data-ttu-id="4437e-116">Moduł pola zakupu pozwala odbiorcy wybrać opcje produktu (np. rozmiar, styl i kolor) i dodać produkt do koszyka.</span><span class="sxs-lookup"><span data-stu-id="4437e-116">The buy box module lets the customer select product options (for example, a size, style, and color) and add the product to the cart.</span></span> <span data-ttu-id="4437e-117">Umożliwia również kupowanie produktu w trybie online i pobieranie go w sklepie.</span><span class="sxs-lookup"><span data-stu-id="4437e-117">It also lets the customer buy the product online and pick it up in a store.</span></span> <span data-ttu-id="4437e-118">Moduł kupowanie w trybie online i pobierz w sklepie używa integracji z interfejsami programowania aplikacji (API) mapy Bing w celu znalezienia bliskich sklepów lub sklepów w innej lokalizacji określanej przez odbiorcę</span><span class="sxs-lookup"><span data-stu-id="4437e-118">The buy online and pick up in store module uses integration with Bing Maps application programming interfaces (APIs) to find nearby stores or stores in another location that the customer specifies.</span></span>

<span data-ttu-id="4437e-119">Moduł pola zakupu wymaga identyfikatora produktu.</span><span class="sxs-lookup"><span data-stu-id="4437e-119">A buy box module requires a product ID.</span></span> <span data-ttu-id="4437e-120">Ten identyfikator jest pochodną z kontekstu strony.</span><span class="sxs-lookup"><span data-stu-id="4437e-120">This ID is derived from the page context.</span></span> <span data-ttu-id="4437e-121">Jeśli do strony, w której kontekst strony nie zawiera identyfikatora produktu, zostanie dodany moduł pola zakupu, informacje te nie zostaną poprawnie zachowane.</span><span class="sxs-lookup"><span data-stu-id="4437e-121">If a buy box module is added to a page where the page context doesn't include a product ID, it won't render the information correctly.</span></span>

## <a name="product-specifications-module"></a><span data-ttu-id="4437e-122">Moduł specyfikacji produktu</span><span class="sxs-lookup"><span data-stu-id="4437e-122">Product specifications module</span></span>

<span data-ttu-id="4437e-123">Moduł specyfikacji produktu może służyć do prezentowania dodatkowych szczegółów dotyczących produktu.</span><span class="sxs-lookup"><span data-stu-id="4437e-123">The product specifications module can be used to showcase additional details about the product.</span></span> <span data-ttu-id="4437e-124">Te szczegóły są pobierane z atrybutów produktów w Commerce.</span><span class="sxs-lookup"><span data-stu-id="4437e-124">These details are taken from product attributes in Commerce.</span></span> <span data-ttu-id="4437e-125">Moduł specyfikacje produktu pokazuje każdy atrybut, w którym właściwość **widoczne** ma wartość **prawda**.</span><span class="sxs-lookup"><span data-stu-id="4437e-125">The product specifications module shows every attribute where the **visible** property is set to **true**.</span></span> <span data-ttu-id="4437e-126">Do pobrania atrybutów produktu wymagana jest nazwa produktu.</span><span class="sxs-lookup"><span data-stu-id="4437e-126">It requires a product ID to retrieve the product attributes.</span></span>

## <a name="recommendations-module"></a><span data-ttu-id="4437e-127">Moduł rekomendacji</span><span class="sxs-lookup"><span data-stu-id="4437e-127">Recommendations module</span></span>

<span data-ttu-id="4437e-128">Najważniejszym modułem układu PDP jest moduł rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="4437e-128">The recommendations module is an important module on a PDP.</span></span> <span data-ttu-id="4437e-129">Podczas przeglądania produktów przez użytkowników należy przedstawić im więcej opcji, dzięki czemu mogą one znaleźć poprawny produkt i dokonać zakupu.</span><span class="sxs-lookup"><span data-stu-id="4437e-129">While customers browse for products, more product options should be presented to them, so that they can find the correct product and make a purchase.</span></span> <span data-ttu-id="4437e-130">Rekomendacje pomagają klientom w łatwejszym odnajdywaniu powiązanych treści i w dalszym ciągu kupować.</span><span class="sxs-lookup"><span data-stu-id="4437e-130">Recommendations help customers easily discover related content and continue to shop.</span></span>

<span data-ttu-id="4437e-131">Dostępne są różne typy list rekomendacji:</span><span class="sxs-lookup"><span data-stu-id="4437e-131">Different types of recommendation lists are available:</span></span>

- <span data-ttu-id="4437e-132">Lista **Klientom podoba się również** jest oparta na nauczeniu maszynowym.</span><span class="sxs-lookup"><span data-stu-id="4437e-132">The **People also like** list is based on machine learning.</span></span> <span data-ttu-id="4437e-133">Zawiera ona historię transakcji innych odbiorców w celu dostarczenia zaleceń.</span><span class="sxs-lookup"><span data-stu-id="4437e-133">It uses the transaction history of other customers to provide recommendations.</span></span> <span data-ttu-id="4437e-134">Ta lista jest generowana przez usługę rekomendacji i przypomina listę „Klienci, krórzy kupili ten produkt, kupili również...”.</span><span class="sxs-lookup"><span data-stu-id="4437e-134">This list is generated by the recommendations service and resembles "Customers who bought this also bought..." lists.</span></span> <span data-ttu-id="4437e-135">Do wygenerowania tej listy wymagany jest identyfikator produktu.</span><span class="sxs-lookup"><span data-stu-id="4437e-135">A product ID is required to generate this list.</span></span>
- <span data-ttu-id="4437e-136">Listę **pokrewną** można skonfigurować dla produktu w sieci Commerce.</span><span class="sxs-lookup"><span data-stu-id="4437e-136">A **Related** list can be configured for a product in Commerce.</span></span> <span data-ttu-id="4437e-137">Na przykład w przypadku brązowej skórzanej torebki można skonfigurować więcej torebek skórzanych lub zaprojektowanych do celów związanych z podróżą dla powiązanej listy.</span><span class="sxs-lookup"><span data-stu-id="4437e-137">For example, for a brown leather travel handbag, more handbags that are leather-based or designed for travel purposes can be configured for the related list.</span></span> <span data-ttu-id="4437e-138">Inne typy list pokrewnych, takie jak **akcesoria** i **podobne do tego**, można również konfigurować w module Commerce.</span><span class="sxs-lookup"><span data-stu-id="4437e-138">Other types of related lists, such as **Accessories** and **More like this**, can also be configured in Commerce.</span></span> <span data-ttu-id="4437e-139">Do wygenerowania tej listy wymagany jest identyfikator produktu.</span><span class="sxs-lookup"><span data-stu-id="4437e-139">A product ID is required to generate this list.</span></span> <span data-ttu-id="4437e-140">W związku z tym, jeśli w kontekście strony zostanie dodany do strony głównej, lista nie będzie zawierała identyfikatora produktu.</span><span class="sxs-lookup"><span data-stu-id="4437e-140">Therefore, if it's added to a home page, where the page context doesn't include a product ID, the list will be empty.</span></span>
- <span data-ttu-id="4437e-141">Algorithmically wygenerowane listy rekomendacji, takie jak **Trendy**, **Bestsellery** i **Nowości**, mogą być używane na PDPs.</span><span class="sxs-lookup"><span data-stu-id="4437e-141">Algorithmically generated recommendation lists, such as **Trending**, **Best Selling**, and **New**, can be used on PDPs.</span></span> <span data-ttu-id="4437e-142">Chociaż te listy mogą nie być bezpośrednio związane z produktem PDP, są one kolejnym sposobem ułatwienia klientom znalezienia produktów, które mogą je zainteresować.</span><span class="sxs-lookup"><span data-stu-id="4437e-142">Although these lists might not be directly related to the product on the PDP, they are another way to help customers find products that might interest them.</span></span> <span data-ttu-id="4437e-143">Te typy list nie wymagają identyfikatora produktu.</span><span class="sxs-lookup"><span data-stu-id="4437e-143">These types of lists don't require a product ID.</span></span> <span data-ttu-id="4437e-144">Są to listy ogólne, które są generowane na podstawie wzorców zakupów w witrynie.</span><span class="sxs-lookup"><span data-stu-id="4437e-144">They are generic lists that are generated based on shopping patterns across the site.</span></span>
- <span data-ttu-id="4437e-145">Listy redakcyjne są ręcznie wyselekcjonowane.</span><span class="sxs-lookup"><span data-stu-id="4437e-145">Editorial lists are manually curated lists.</span></span> <span data-ttu-id="4437e-146">Na przykład detalista może zdecydować o ręcznym zaprezentowania list produktów, które chce prezentować.</span><span class="sxs-lookup"><span data-stu-id="4437e-146">For example, a retailer might decide to manually curate lists of products that it wants to showcase.</span></span>

## <a name="ratings-and-reviews-modules"></a><span data-ttu-id="4437e-147">Moduły ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="4437e-147">Ratings and reviews modules</span></span>

<span data-ttu-id="4437e-148">Do wyświetlania i dodawania recenzji można używać trzech modułów:</span><span class="sxs-lookup"><span data-stu-id="4437e-148">Three modules can be used to show and add reviews:</span></span>

- <span data-ttu-id="4437e-149">**Recenzje** — Moduł zawiera oceny i przeglądy, które zostały udostępnione przez innych odbiorców.</span><span class="sxs-lookup"><span data-stu-id="4437e-149">**Reviews** – This module lists ratings and reviews that have been provided by other customers.</span></span> <span data-ttu-id="4437e-150">Odbiorcy mogą sortować i filtrować Recenzje.</span><span class="sxs-lookup"><span data-stu-id="4437e-150">Customers can sort and filter the reviews.</span></span> <span data-ttu-id="4437e-151">Do tego modułu Klienci ci powinni również zaznaczyć, czy Recenzje są pomocne, czy nie, i zgłaszać problemy.</span><span class="sxs-lookup"><span data-stu-id="4437e-151">This module also lets customers like or dislike reviews, and report issues.</span></span>
- <span data-ttu-id="4437e-152">**Napisz recenzję** — ten moduł umożliwia pisanie własnych przeglądów produktu.</span><span class="sxs-lookup"><span data-stu-id="4437e-152">**Write review** – This module lets customers write their own reviews of a product.</span></span>
- <span data-ttu-id="4437e-153">**Histogram klasyfikacji** — ten moduł zawiera histogram pokazujący trend klasyfikacji produktu.</span><span class="sxs-lookup"><span data-stu-id="4437e-153">**Ratings histogram** – This module includes a histogram that shows the ratings trend for a product.</span></span>

<span data-ttu-id="4437e-154">Aby uzyskać więcej szczegółowych informacji, zobacz [Omówienie ocen i recenzji](ratings-reviews-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4437e-154">For more details, see [Ratings and reviews overview](ratings-reviews-overview.md).</span></span>

## <a name="marketing-modules"></a><span data-ttu-id="4437e-155">Moduły marketingu</span><span class="sxs-lookup"><span data-stu-id="4437e-155">Marketing modules</span></span>

<span data-ttu-id="4437e-156">Jeśli zawartość marketingowa jest unikatowa dla określonego produktu, do PDP można dodać dowolny moduł marketingowy.</span><span class="sxs-lookup"><span data-stu-id="4437e-156">If marketing content is unique to a specific product, any marketing module can be added to the PDP.</span></span> <span data-ttu-id="4437e-157">Moduły marketingowe można dodawać do PDP przez „wzbogacanie” strony.</span><span class="sxs-lookup"><span data-stu-id="4437e-157">You can add marketing modules to a PDP by "enriching" the page.</span></span> <span data-ttu-id="4437e-158">Więcej informacji zawiera sekcja [wzbogacanie strony produktu](enrich-product-page.md).</span><span class="sxs-lookup"><span data-stu-id="4437e-158">For more details, see [Enrich a product page](enrich-product-page.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4437e-159">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4437e-159">Additional resources</span></span>

[<span data-ttu-id="4437e-160">Omówienie strony głównej</span><span class="sxs-lookup"><span data-stu-id="4437e-160">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="4437e-161">Omówienie stron koszyka i realizacji zamówienia</span><span class="sxs-lookup"><span data-stu-id="4437e-161">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="4437e-162">Omówienie stron zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="4437e-162">Account management pages overview</span></span>](quick-tour-account-management.md)

[<span data-ttu-id="4437e-163">Wzbogacanie strony szczegółów na temat produktu</span><span class="sxs-lookup"><span data-stu-id="4437e-163">Enrich a product details page</span></span>](enrich-product-page.md)
