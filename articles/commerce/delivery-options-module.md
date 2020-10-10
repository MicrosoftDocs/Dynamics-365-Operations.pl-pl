---
title: Moduł Opcje dostawy
description: W tym temacie omówiono moduły opcji dostarczania i wyjaśniono, jak je skonfigurować w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 39e597b88afcca69623b1a23acc95e4da3873082
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818306"
---
# <a name="delivery-options-module"></a><span data-ttu-id="6f242-103">Moduł Opcje dostawy</span><span class="sxs-lookup"><span data-stu-id="6f242-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6f242-104">W tym temacie omówiono moduły opcji dostarczania i wyjaśniono, jak je skonfigurować w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6f242-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6f242-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6f242-105">Overview</span></span>

<span data-ttu-id="6f242-106">Moduły opcji dostawy umożliwiają klientom wybranie metody dostawy, np. wysyłki lub odbioru, na potrzeby zamówienia online.</span><span class="sxs-lookup"><span data-stu-id="6f242-106">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="6f242-107">Adres wysyłkowy jest wymagany w celu określenia metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="6f242-107">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="6f242-108">W przypadku zmiany adresu dostawy należy ponownie pobrać opcje dostawy.</span><span class="sxs-lookup"><span data-stu-id="6f242-108">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="6f242-109">Jeśli zamówienie uwzględnia tylko towary, które zostaną odebrane w sklepie, ten moduł jest automatycznie ukrywany.</span><span class="sxs-lookup"><span data-stu-id="6f242-109">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="6f242-110">Aby uzyskać informacje dotyczące konfigurowania metod dostawy, należy zapoznać się z tematem [Konfiguracja kanału online](channel-setup-online.md) i [Ustaw metody dostawy](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="6f242-110">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="6f242-111">Z każdym z trybów dostawy można przypisana opłata.</span><span class="sxs-lookup"><span data-stu-id="6f242-111">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="6f242-112">Więcej informacji na temat konfigurowania opłat za sklep internetowy, należy zapoznać się z [Wielokanałowe zaawansowane opłaty automatyczne](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="6f242-112">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="6f242-113">W programie Commerce w wersji 10.0.13 moduł opcji dostawy został zaktualizowany w taki sposób, aby obsługiwał funkcje **Opłata za nagłówek bez podziału** i **Wysyłka jako opłata liniowa**.</span><span class="sxs-lookup"><span data-stu-id="6f242-113">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="6f242-114">Jeśli dopuszczalna wartość jest wyłączona, oczekuje się, że przepływ pracy w module handlu elektronicznego nie pozwoli na przetworzenie trybu dostawy dla towarów w koszyku (tzn. niektóre towary są wybierane do wysyłki, ale inne są wybierane do odbioru).</span><span class="sxs-lookup"><span data-stu-id="6f242-114">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="6f242-115">Funkcja **Opłata za nagłówek bez podziału** wymaga włączenia flagi **Włącz obsługę spójnego trybu dostawy w kanale** w module Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="6f242-115">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag be turned on in Commerce headquarters.</span></span> <span data-ttu-id="6f242-116">Po włączeniu tej flagi opłaty transportowe będą stosowane na poziomie nagłówka lub na poziomie wiersza, w zależności od konfiguracji w module Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="6f242-116">When that flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="6f242-117">Kompozycja Fabrikam obsługuje tryb mieszany dostawy, w którym niektóre towary są wybierane do wysyłki, ale inne zostały wybrane do pobrania.</span><span class="sxs-lookup"><span data-stu-id="6f242-117">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="6f242-118">W tym trybie opłaty za wysyłkę będą klasyfikowane dla wszystkich towarów, które zostały wybrane w trybie dostawy.</span><span class="sxs-lookup"><span data-stu-id="6f242-118">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="6f242-119">Aby można było korzystać z mieszanej metody dostawy, należy najpierw skonfigurować funkcję **Opłata za nagłówek bez podziału** w module Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="6f242-119">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="6f242-120">Aby uzyskać więcej informacji o tej konfiguracji, przejrzyj [Proporcjonalne dzielenie opłat z nagłówka między pasujące wiersze sprzedaży](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="6f242-120">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="6f242-121">Jeśli opłaty transportowe mają zastosowanie do towarów w wierszach, można je wyświetlić w wierszu koszyka dla każdego towaru.</span><span class="sxs-lookup"><span data-stu-id="6f242-121">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="6f242-122">Ta funkcja wymaga włączenia właściwości **Pokazuj pozycję online opłat za wysyłkę** dla modułu koszyka i modułu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="6f242-122">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="6f242-123">Aby uzyskać więcej informacji, zobacz [Moduł koszyka](add-cart-module.md) i [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="6f242-123">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="6f242-124">Poniższa ilustracja pokazuje przykład opcji dostawy na stronie realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="6f242-124">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Przykład modułu opcji dostawy na stronie realizacja zamówienia](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="6f242-126">Właściwości modułu Opcje dostawy</span><span class="sxs-lookup"><span data-stu-id="6f242-126">Delivery options module properties</span></span>

| <span data-ttu-id="6f242-127">Właściwość</span><span class="sxs-lookup"><span data-stu-id="6f242-127">Property</span></span> | <span data-ttu-id="6f242-128">Wartości</span><span class="sxs-lookup"><span data-stu-id="6f242-128">Values</span></span> | <span data-ttu-id="6f242-129">opis</span><span class="sxs-lookup"><span data-stu-id="6f242-129">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="6f242-130">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="6f242-130">Heading</span></span> | <span data-ttu-id="6f242-131">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="6f242-131">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="6f242-132">Opcjonalny nagłówek modułu opcje dostawy.</span><span class="sxs-lookup"><span data-stu-id="6f242-132">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="6f242-133">Niestandardowa nazwa klasy CSS</span><span class="sxs-lookup"><span data-stu-id="6f242-133">Custom CSS class name</span></span> | <span data-ttu-id="6f242-134">Tekst</span><span class="sxs-lookup"><span data-stu-id="6f242-134">Text</span></span> | <span data-ttu-id="6f242-135">Niestandardowa nazwa klasy arkuszy stylów kaskadowych (CSS), która będzie używana do renderowania tego modułu (jeśli ma zastosowanie).</span><span class="sxs-lookup"><span data-stu-id="6f242-135">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="6f242-136">Filtruj opcję trybu dostawy</span><span class="sxs-lookup"><span data-stu-id="6f242-136">Filter Delivery Mode Option</span></span> | <span data-ttu-id="6f242-137">**Nie filtruj** lub **Tryby bez wysyłki**</span><span class="sxs-lookup"><span data-stu-id="6f242-137">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="6f242-138">Wartość określająca, czy moduł opcji dostawy powinien filtrować wszystkie tryby dostaw inne niż wysyłkowe.</span><span class="sxs-lookup"><span data-stu-id="6f242-138">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="6f242-139">Dodaj moduł opcji dostawy do strony realizacji zamówienia i ustaw wymagane właściwości</span><span class="sxs-lookup"><span data-stu-id="6f242-139">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="6f242-140">Moduł opcji dostawy można dodać tylko do modułu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="6f242-140">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="6f242-141">Aby uzyskać więcej informacji na temat konfigurowania modułu opcji dostawy i dodania go do strony realizacji transakcji, zapoznaj się z tematem [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="6f242-141">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f242-142">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6f242-142">Additional resources</span></span>

[<span data-ttu-id="6f242-143">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="6f242-143">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="6f242-144">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="6f242-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="6f242-145">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="6f242-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="6f242-146">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="6f242-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="6f242-147">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="6f242-147">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="6f242-148">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="6f242-148">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="6f242-149">Konfiguracja kanału online</span><span class="sxs-lookup"><span data-stu-id="6f242-149">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="6f242-150">Wielokanałowe zaawansowane opłaty automatyczne</span><span class="sxs-lookup"><span data-stu-id="6f242-150">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="6f242-151">Proporcjonalne dzielenie opłat z nagłówka między pasujące wiersze sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6f242-151">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="6f242-152">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="6f242-152">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
