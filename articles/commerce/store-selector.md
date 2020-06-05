---
title: Moduł wyboru sklepu
description: W tym temacie opisano moduł wyboru sklepu i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 460d05ca29d5b8da70a971a649d9edd786f7260d
ms.sourcegitcommit: 15c5ec742d648c5f3506d031a2ab6150dcbae348
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378215"
---
# <a name="store-selector-module"></a><span data-ttu-id="839a0-103">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="839a0-103">Store selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="839a0-104">W tym temacie opisano moduł wyboru sklepu i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="839a0-104">This topic covers the store selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="839a0-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="839a0-105">Overview</span></span>

<span data-ttu-id="839a0-106">Moduł wyboru sklepu jest używany dla scenariusza odbiorcy „kupowanie w trybie online” (BOPIS).</span><span class="sxs-lookup"><span data-stu-id="839a0-106">A store selector module is used for the "buy online, pick up in store"" (BOPIS) customer scenario.</span></span> <span data-ttu-id="839a0-107">Wyświetla listę sklepów, w których produkt jest dostępny do odbioru, a także godziny przechowywania i zapasy produktów dla każdego sklepu.</span><span class="sxs-lookup"><span data-stu-id="839a0-107">It displays a list of stores where a product is available for pickup, as well as store hours and product inventory for each store.</span></span>

<span data-ttu-id="839a0-108">Moduł wyboru sklepu wymaga kontekstu produktu i lokalizacji wyszukiwania, aby znaleźć sklepy.</span><span class="sxs-lookup"><span data-stu-id="839a0-108">The store selector module requires the context of a product and a search location to find stores.</span></span> <span data-ttu-id="839a0-109">W przypadku braku lokalizacji wyszukiwania domyślna jest lokalizacja przeglądarki klienta, pod warunkiem, że klient wyrazi zgodę.</span><span class="sxs-lookup"><span data-stu-id="839a0-109">In the absence of a search location, it defaults to the customer's browser location, provided that the customer gives consent.</span></span> <span data-ttu-id="839a0-110">Moduł ma pole wprowadzania, które pozwala klientowi wprowadzić lokalizację (kod pocztowy lub miasto i stan), aby znaleźć sklepy w pobliżu.</span><span class="sxs-lookup"><span data-stu-id="839a0-110">The module has an input box which allows the customer to enter a location (zipcode, or city and state) to find stores that are nearby.</span></span>

<span data-ttu-id="839a0-111">Moduł wyboru sklepu jest zintegrowany z aplikacją do geokodowania Bing Maps Geocoding (API) służy do konwersji lokalizacji na szerokość i długość geograficzną.</span><span class="sxs-lookup"><span data-stu-id="839a0-111">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="839a0-112">Klucz interfejsu API map usługi Bing jest wymagany i należy go dodać do strony udostępnione parametry Commerce w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="839a0-112">A Bing Maps API key is required and must be added to the Commerce shared parameters page in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="839a0-113">Moduł wyboru sklepu można dodać do modułu pola zakupu na stronie szczegółów produktu (PDP), aby wyświetlić sklepy, w których produkt jest dostępny do odbioru.</span><span class="sxs-lookup"><span data-stu-id="839a0-113">The store selector module can be added to a buy box module on the product details page (PDP) to display stores where a product is available for pickup.</span></span> <span data-ttu-id="839a0-114">Można go również dodać do modułu koszyka.</span><span class="sxs-lookup"><span data-stu-id="839a0-114">It can also be added to a cart module.</span></span> <span data-ttu-id="839a0-115">W przypadku dodania do modułu koszyka w module wyboru sklepów są wyświetlane opcje pobrania dla każdego towaru w wierszu koszyka.</span><span class="sxs-lookup"><span data-stu-id="839a0-115">When added to a cart module, the store selector module displays pickup options for each cart line item.</span></span> <span data-ttu-id="839a0-116">Ponadto, z kodowaniem niestandardowym, ten moduł można dodać do innych stron lub modułów za pomocą rozszerzeń i dostosowań.</span><span class="sxs-lookup"><span data-stu-id="839a0-116">In addition, with custom coding this module can be added to other pages or modules via extensions and customizations.</span></span>

<span data-ttu-id="839a0-117">Aby scenariusz BOPIS działał, w produktach należy skonfigurować tryb dostawy „odbiór klienta”.</span><span class="sxs-lookup"><span data-stu-id="839a0-117">For the BOPIS scenario to work, products should be configured with the "customer pickup" delivery mode.</span></span> <span data-ttu-id="839a0-118">W przeciwnym razie moduł nie będzie wyświetlany na odpowiednich stronach.</span><span class="sxs-lookup"><span data-stu-id="839a0-118">Otherwise, the module will not be shown on the respective pages.</span></span> <span data-ttu-id="839a0-119">Aby uzyskać szczegółowe informacje dotyczące konfigurowania metody dostawy, należy zapoznać się z tematem [Ustaw metody dostawy](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="839a0-119">For details on how to configure the delivery mode, see [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="839a0-120">Poniższy obraz pokazuje przykład modułu wyboru sklepu używanego w PDP.</span><span class="sxs-lookup"><span data-stu-id="839a0-120">The following image shows an example of a store selector module used on a PDP.</span></span>

![Przykład modułu wyboru sklepu](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a><span data-ttu-id="839a0-122">Użycie modułu wyboru sklepu w e-commerce</span><span class="sxs-lookup"><span data-stu-id="839a0-122">Store selector module usage in e-Commerce</span></span>

- <span data-ttu-id="839a0-123">Moduł wyboru sklepu można wykorzystać na stronie szczegółów produktu (PDP), aby znaleźć pobliskie sklepy, w których produkt jest dostępny do odbioru.</span><span class="sxs-lookup"><span data-stu-id="839a0-123">A store selector module can be used on a product details page (PDP) to find nearby stores where a product is available for pickup.</span></span>
- <span data-ttu-id="839a0-124">Moduł wyboru sklepu można wykorzystać na stronie koszyka, aby znaleźć pobliskie sklepy, w których produkt w koszyku jest dostępny do odbioru.</span><span class="sxs-lookup"><span data-stu-id="839a0-124">A store selector module can be used on a cart page to find nearby stores where a product in the cart is available for pickup.</span></span>

## <a name="store-selector-module-properties"></a><span data-ttu-id="839a0-125">Właściwości Modułu wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="839a0-125">Store selector module properties</span></span>

| <span data-ttu-id="839a0-126">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="839a0-126">Property name</span></span>             | <span data-ttu-id="839a0-127">Wartość</span><span class="sxs-lookup"><span data-stu-id="839a0-127">Value</span></span>                 | <span data-ttu-id="839a0-128">opis</span><span class="sxs-lookup"><span data-stu-id="839a0-128">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="839a0-129">Promień wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="839a0-129">Search radius</span></span> | <span data-ttu-id="839a0-130">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="839a0-130">Number</span></span> | <span data-ttu-id="839a0-131">Określa promień wyszukiwania dla sklepów w milach.</span><span class="sxs-lookup"><span data-stu-id="839a0-131">Defines the search radius for stores, in miles.</span></span> <span data-ttu-id="839a0-132">Jeśli nie określono żadnej wartości, używany jest domyślny promień wyszukiwania, 50 mil.</span><span class="sxs-lookup"><span data-stu-id="839a0-132">If no value is specified, the default search radius of 50 miles is used.</span></span>|
|<span data-ttu-id="839a0-133">Warunki świadczenia usług</span><span class="sxs-lookup"><span data-stu-id="839a0-133">Terms of Service</span></span> | <span data-ttu-id="839a0-134">Adres URL</span><span class="sxs-lookup"><span data-stu-id="839a0-134">URL</span></span>    |  <span data-ttu-id="839a0-135">Dla usługi Bing Maps jest wymagane łącze URL Warunki świadczenia usługi.</span><span class="sxs-lookup"><span data-stu-id="839a0-135">The terms of service URL that is required for the Bing Maps service.</span></span> |

## <a name="add-a-store-selector-module-to-a-page"></a><span data-ttu-id="839a0-136">Dodawanie modułu wyboru sklepu do nowej strony</span><span class="sxs-lookup"><span data-stu-id="839a0-136">Add a store selector module to a page</span></span>

<span data-ttu-id="839a0-137">Moduł wyboru sklepu wymaga kontekstu produktu, więc można go używać tylko w polu zakupu i module koszyka.</span><span class="sxs-lookup"><span data-stu-id="839a0-137">A store selector module needs the context of a product, so it can only be used within buy box and cart modules.</span></span> <span data-ttu-id="839a0-138">Moduły wyboru sklepów nie działają poza tymi modułami.</span><span class="sxs-lookup"><span data-stu-id="839a0-138">Store selector modules do not function outside these modules.</span></span>

- <span data-ttu-id="839a0-139">Aby uzyskać informacje o tym, jak dodać moduł wyboru sklepu do modułu pole zakupy, zajrzyj [Moduł pola zakupu](add-buy-box.md).</span><span class="sxs-lookup"><span data-stu-id="839a0-139">For information on how to add a store selector module to a buy box module, see [Buy box module](add-buy-box.md).</span></span> 
- <span data-ttu-id="839a0-140">Aby uzyskać informacje o tym, jak dodać moduł wyboru sklepu do modułu koszyka, zajrzyj [Moduł koszyka](add-cart-module.md)</span><span class="sxs-lookup"><span data-stu-id="839a0-140">For information on how to add a store selector module to a cart module, see [Cart module](add-cart-module.md)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="839a0-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="839a0-141">Additional resources</span></span>

[<span data-ttu-id="839a0-142">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="839a0-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="839a0-143">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="839a0-143">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="839a0-144">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="839a0-144">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="839a0-145">Krótki przewodnik PDP</span><span class="sxs-lookup"><span data-stu-id="839a0-145">Quick tour of PDP</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="839a0-146">Krótki przewodnik po Koszyku i realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="839a0-146">Quick tour of Cart and checkout</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="839a0-147">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="839a0-147">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[<span data-ttu-id="839a0-148">Zarządzanie mapami Bing dla organizacji</span><span class="sxs-lookup"><span data-stu-id="839a0-148">Manage Bing Maps for your organization</span></span>](dev-itpro/manage-bing-maps.md)
