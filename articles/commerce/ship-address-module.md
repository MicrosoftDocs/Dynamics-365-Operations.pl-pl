---
title: Moduł adresu wysyłki
description: W tym temacie omówiono moduł adresu wysyłki i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e590c966ca6bd8111df5f91cbac0485afaa45c78
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234420"
---
# <a name="shipping-address-module"></a><span data-ttu-id="6a817-103">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="6a817-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6a817-104">W tym temacie omówiono moduł adresu wysyłki i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a817-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="6a817-105">Moduł adresu wysyłki umożliwia klientom dodanie lub wybranie adresu wysyłki dla zamówienia podczas realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="6a817-105">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="6a817-106">Jeśli klient jest zalogowany, wszystkie adresy, które zostały wcześniej zapisane dla tego klienta, są wyświetlane, a klient może wybrać jeden z nich.</span><span class="sxs-lookup"><span data-stu-id="6a817-106">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="6a817-107">Odbiorca może również dodać nowy adres.</span><span class="sxs-lookup"><span data-stu-id="6a817-107">The customer can also add a new address.</span></span> <span data-ttu-id="6a817-108">Moduł adresu wysyłki jest używany dla wszystkich pozycji w zamówieniu, które wymagają wysyłki.</span><span class="sxs-lookup"><span data-stu-id="6a817-108">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="6a817-109">Formaty adresów wysyłkowych można definiować w module Commerce Headquarter dla każdego kraju lub regionu, a moduł adresów wysyłkowych wymusza reguły specyficzne dla kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="6a817-109">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="6a817-110">Gdy odbiorcy wprowadzają adres wysyłkowy podczas procesu realizacji transakcji, mają możliwość zapisania adresu jako adresu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="6a817-110">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="6a817-111">Ta opcja jest wyświetlana tylko wtedy, gdy odbiorca jest zalogowany do systemu.</span><span class="sxs-lookup"><span data-stu-id="6a817-111">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="6a817-112">Chociaż moduł adresu wysyłki nie zapewnia weryfikacji adresu, tę funkcję można wdrożyć poprzez dostosowanie.</span><span class="sxs-lookup"><span data-stu-id="6a817-112">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="6a817-113">Poniższa ilustracja przedstawia przykład nowego modułu adresu wysyłki na stronie kasy.</span><span class="sxs-lookup"><span data-stu-id="6a817-113">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Przykład modułu adresu wysyłki na stronie realizacja zamówienia](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="6a817-115">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="6a817-115">Module properties</span></span>

| <span data-ttu-id="6a817-116">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="6a817-116">Property name</span></span> | <span data-ttu-id="6a817-117">Wartości</span><span class="sxs-lookup"><span data-stu-id="6a817-117">Values</span></span> | <span data-ttu-id="6a817-118">opis</span><span class="sxs-lookup"><span data-stu-id="6a817-118">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="6a817-119">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="6a817-119">Heading</span></span> | <span data-ttu-id="6a817-120">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="6a817-120">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="6a817-121">Opcjonalny nagłówek modułu adresu wysyłki.</span><span class="sxs-lookup"><span data-stu-id="6a817-121">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="6a817-122">Pokaż typ adresu</span><span class="sxs-lookup"><span data-stu-id="6a817-122">Show address type</span></span> | <span data-ttu-id="6a817-123">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="6a817-123">**True** or **False**</span></span> | <span data-ttu-id="6a817-124">Jeśli ta właściwość opcjonalna ma wartość **Prawda**, wyświetlany jest typ adresu, np. **Dom** lub **Firma**.</span><span class="sxs-lookup"><span data-stu-id="6a817-124">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="6a817-125">Jeśli nie określono typu adresu, adres zostanie automatycznie zapisany jako **Typ**=**Inny**.</span><span class="sxs-lookup"><span data-stu-id="6a817-125">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |
| <span data-ttu-id="6a817-126">Włącz automatyczne sugestie</span><span class="sxs-lookup"><span data-stu-id="6a817-126">Enable auto suggestion</span></span>| <span data-ttu-id="6a817-127">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="6a817-127">**True** or **False**</span></span> | <span data-ttu-id="6a817-128">Jeśli dla tej opcjonalnej właściwości zostanie ustawiona wartość **Prawda**, zostaną dostarczone automatyczne sugestie adresów.</span><span class="sxs-lookup"><span data-stu-id="6a817-128">If this optional property is set to **True**, automatic address suggestions will be provided.</span></span> <span data-ttu-id="6a817-129">Te sugestie są oparte na mapach Bing.</span><span class="sxs-lookup"><span data-stu-id="6a817-129">These suggestions are powered by Bing Maps.</span></span> <span data-ttu-id="6a817-130">Aby uzyskać informacje dotyczące sposobu skonfigurowania integracji Map Bing dla swojej witryny, zobacz moduł [Selektor sklepu](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="6a817-130">For information about how to set up Bing Maps integration for your site, see [Store selector module](store-selector.md).</span></span> <span data-ttu-id="6a817-131">Ta funkcja jest dostępna w wersji Commerce 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="6a817-131">This feature is available as of the Commerce version 10.0.15 release.</span></span>|
|<span data-ttu-id="6a817-132">Opcje automatycznych sugestii</span><span class="sxs-lookup"><span data-stu-id="6a817-132">Auto suggest options</span></span>| <span data-ttu-id="6a817-133">Numer</span><span class="sxs-lookup"><span data-stu-id="6a817-133">A number</span></span>| <span data-ttu-id="6a817-134">Jeśli funkcja automatycznych sugestii adresów jest włączona, można określić dodatkowe opcje, takie jak maksymalna liczba sugerowanych danych.</span><span class="sxs-lookup"><span data-stu-id="6a817-134">If automatic address suggestions are enabled, you can specify additional options, such as the maximum number of suggestions that should be provided.</span></span>|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="6a817-135">Dodaj moduł adresu wysyłki do strony realizacji zamówienia i ustaw wymagane właściwości</span><span class="sxs-lookup"><span data-stu-id="6a817-135">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="6a817-136">Moduł adresu wysyłki można dodać tylko do modułu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="6a817-136">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="6a817-137">Aby uzyskać więcej informacji na temat konfigurowania modułu adresu wysyłki i dodania go do strony realizacji transakcji, zapoznaj się z tematem [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="6a817-137">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a817-138">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6a817-138">Additional resources</span></span>

[<span data-ttu-id="6a817-139">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="6a817-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="6a817-140">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="6a817-140">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="6a817-141">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="6a817-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="6a817-142">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="6a817-142">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="6a817-143">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="6a817-143">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="6a817-144">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="6a817-144">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="6a817-145">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="6a817-145">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="6a817-146">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="6a817-146">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="6a817-147">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="6a817-147">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]