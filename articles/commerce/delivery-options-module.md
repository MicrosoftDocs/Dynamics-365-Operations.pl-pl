---
title: Moduł Opcje dostawy
description: W tym temacie omówiono moduły opcji dostarczania i wyjaśniono, jak je skonfigurować w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: f97dcd42e22e319d9af7cbf57fce7c10d8565d04
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802003"
---
# <a name="delivery-options-module"></a><span data-ttu-id="c5aff-103">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="c5aff-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c5aff-104">W tym temacie omówiono moduły opcji dostarczania i wyjaśniono, jak je skonfigurować w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c5aff-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c5aff-105">Moduły opcji dostawy umożliwiają klientom wybranie metody dostawy, np. wysyłki lub odbioru, na potrzeby zamówienia online.</span><span class="sxs-lookup"><span data-stu-id="c5aff-105">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="c5aff-106">Adres wysyłkowy jest wymagany w celu określenia metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="c5aff-106">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="c5aff-107">W przypadku zmiany adresu dostawy należy ponownie pobrać opcje dostawy.</span><span class="sxs-lookup"><span data-stu-id="c5aff-107">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="c5aff-108">Jeśli zamówienie uwzględnia tylko towary, które zostaną odebrane w sklepie, ten moduł jest automatycznie ukrywany.</span><span class="sxs-lookup"><span data-stu-id="c5aff-108">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="c5aff-109">Aby uzyskać informacje dotyczące konfigurowania metod dostawy, należy zapoznać się z tematem [Konfiguracja kanału online](channel-setup-online.md) i [Ustaw metody dostawy](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="c5aff-109">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="c5aff-110">Z każdym z trybów dostawy można przypisana opłata.</span><span class="sxs-lookup"><span data-stu-id="c5aff-110">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="c5aff-111">Więcej informacji na temat konfigurowania opłat za sklep internetowy, należy zapoznać się z [Wielokanałowe zaawansowane opłaty automatyczne](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="c5aff-111">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="c5aff-112">W programie Commerce w wersji 10.0.13 moduł opcji dostawy został zaktualizowany w taki sposób, aby obsługiwał funkcje **Opłata za nagłówek bez podziału** i **Wysyłka jako opłata liniowa**.</span><span class="sxs-lookup"><span data-stu-id="c5aff-112">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="c5aff-113">Jeśli dopuszczalna wartość jest wyłączona, oczekuje się, że przepływ pracy w module handlu elektronicznego nie pozwoli na przetworzenie trybu dostawy dla towarów w koszyku (tzn. niektóre towary są wybierane do wysyłki, ale inne są wybierane do odbioru).</span><span class="sxs-lookup"><span data-stu-id="c5aff-113">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="c5aff-114">Funkcja **Opłata za nagłówek bez podziału** wymaga włączenia flagi **Włącz obsługę spójnego trybu dostawy w kanale** w module Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="c5aff-114">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag be turned on in Commerce headquarters.</span></span> <span data-ttu-id="c5aff-115">Po włączeniu tej flagi opłaty transportowe będą stosowane na poziomie nagłówka lub na poziomie wiersza, w zależności od konfiguracji w module Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="c5aff-115">When that flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="c5aff-116">Kompozycja Fabrikam obsługuje tryb mieszany dostawy, w którym niektóre towary są wybierane do wysyłki, ale inne zostały wybrane do pobrania.</span><span class="sxs-lookup"><span data-stu-id="c5aff-116">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="c5aff-117">W tym trybie opłaty za wysyłkę będą klasyfikowane dla wszystkich towarów, które zostały wybrane w trybie dostawy.</span><span class="sxs-lookup"><span data-stu-id="c5aff-117">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="c5aff-118">Aby można było korzystać z mieszanej metody dostawy, należy najpierw skonfigurować funkcję **Opłata za nagłówek bez podziału** w module Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="c5aff-118">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="c5aff-119">Aby uzyskać więcej informacji o tej konfiguracji, przejrzyj [Proporcjonalne dzielenie opłat z nagłówka między pasujące wiersze sprzedaży](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="c5aff-119">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="c5aff-120">Jeśli opłaty transportowe mają zastosowanie do towarów w wierszach, można je wyświetlić w wierszu koszyka dla każdego towaru.</span><span class="sxs-lookup"><span data-stu-id="c5aff-120">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="c5aff-121">Ta funkcja wymaga włączenia właściwości **Pokazuj pozycję online opłat za wysyłkę** dla modułu koszyka i modułu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="c5aff-121">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="c5aff-122">Aby uzyskać więcej informacji, zobacz [Moduł koszyka](add-cart-module.md) i [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="c5aff-122">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="c5aff-123">Poniższa ilustracja pokazuje przykład opcji dostawy na stronie realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c5aff-123">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Przykład modułu opcji dostawy na stronie realizacja zamówienia](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="c5aff-125">Właściwości modułu Opcje dostawy</span><span class="sxs-lookup"><span data-stu-id="c5aff-125">Delivery options module properties</span></span>

| <span data-ttu-id="c5aff-126">Właściwość</span><span class="sxs-lookup"><span data-stu-id="c5aff-126">Property</span></span> | <span data-ttu-id="c5aff-127">Wartości</span><span class="sxs-lookup"><span data-stu-id="c5aff-127">Values</span></span> | <span data-ttu-id="c5aff-128">opis</span><span class="sxs-lookup"><span data-stu-id="c5aff-128">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="c5aff-129">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="c5aff-129">Heading</span></span> | <span data-ttu-id="c5aff-130">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="c5aff-130">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="c5aff-131">Opcjonalny nagłówek modułu opcje dostawy.</span><span class="sxs-lookup"><span data-stu-id="c5aff-131">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="c5aff-132">Niestandardowa nazwa klasy CSS</span><span class="sxs-lookup"><span data-stu-id="c5aff-132">Custom CSS class name</span></span> | <span data-ttu-id="c5aff-133">Tekst</span><span class="sxs-lookup"><span data-stu-id="c5aff-133">Text</span></span> | <span data-ttu-id="c5aff-134">Niestandardowa nazwa klasy arkuszy stylów kaskadowych (CSS), która będzie używana do renderowania tego modułu (jeśli ma zastosowanie).</span><span class="sxs-lookup"><span data-stu-id="c5aff-134">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="c5aff-135">Filtruj opcję trybu dostawy</span><span class="sxs-lookup"><span data-stu-id="c5aff-135">Filter Delivery Mode Option</span></span> | <span data-ttu-id="c5aff-136">**Nie filtruj** lub **Tryby bez wysyłki**</span><span class="sxs-lookup"><span data-stu-id="c5aff-136">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="c5aff-137">Wartość określająca, czy moduł opcji dostawy powinien filtrować wszystkie tryby dostaw inne niż wysyłkowe.</span><span class="sxs-lookup"><span data-stu-id="c5aff-137">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="c5aff-138">Dodaj moduł opcji dostawy do strony realizacji zamówienia i ustaw wymagane właściwości</span><span class="sxs-lookup"><span data-stu-id="c5aff-138">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="c5aff-139">Moduł opcji dostawy można dodać tylko do modułu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="c5aff-139">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="c5aff-140">Aby uzyskać więcej informacji na temat konfigurowania modułu opcji dostawy i dodania go do strony realizacji transakcji, zapoznaj się z tematem [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="c5aff-140">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c5aff-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c5aff-141">Additional resources</span></span>

[<span data-ttu-id="c5aff-142">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="c5aff-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c5aff-143">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="c5aff-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c5aff-144">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="c5aff-144">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="c5aff-145">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="c5aff-145">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="c5aff-146">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="c5aff-146">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="c5aff-147">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="c5aff-147">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="c5aff-148">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="c5aff-148">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="c5aff-149">Konfiguracja kanału online</span><span class="sxs-lookup"><span data-stu-id="c5aff-149">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="c5aff-150">Wielokanałowe zaawansowane opłaty automatyczne</span><span class="sxs-lookup"><span data-stu-id="c5aff-150">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="c5aff-151">Proporcjonalne dzielenie opłat z nagłówka między pasujące wiersze sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c5aff-151">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="c5aff-152">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="c5aff-152">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]