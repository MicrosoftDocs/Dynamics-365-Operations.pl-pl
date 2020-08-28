---
title: Moduł adresu wysyłki
description: W tym temacie omówiono moduł adresu wysyłki i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 380d268ec0ba64367f090c31408eac1c54d0ff17
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661448"
---
# <a name="shipping-address-module"></a><span data-ttu-id="abb29-103">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="abb29-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="abb29-104">W tym temacie omówiono moduł adresu wysyłki i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="abb29-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="abb29-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="abb29-105">Overview</span></span>

<span data-ttu-id="abb29-106">Moduł adresu wysyłki umożliwia klientom dodanie lub wybranie adresu wysyłki dla zamówienia podczas realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="abb29-106">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="abb29-107">Jeśli klient jest zalogowany, wszystkie adresy, które zostały wcześniej zapisane dla tego klienta, są wyświetlane, a klient może wybrać jeden z nich.</span><span class="sxs-lookup"><span data-stu-id="abb29-107">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="abb29-108">Odbiorca może również dodać nowy adres.</span><span class="sxs-lookup"><span data-stu-id="abb29-108">The customer can also add a new address.</span></span> <span data-ttu-id="abb29-109">Moduł adresu wysyłki jest używany dla wszystkich pozycji w zamówieniu, które wymagają wysyłki.</span><span class="sxs-lookup"><span data-stu-id="abb29-109">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="abb29-110">Formaty adresów wysyłkowych można definiować w module Commerce Headquarter dla każdego kraju lub regionu, a moduł adresów wysyłkowych wymusza reguły specyficzne dla kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="abb29-110">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="abb29-111">Gdy odbiorcy wprowadzają adres wysyłkowy podczas procesu realizacji transakcji, mają możliwość zapisania adresu jako adresu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="abb29-111">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="abb29-112">Ta opcja jest wyświetlana tylko wtedy, gdy odbiorca jest zalogowany do systemu.</span><span class="sxs-lookup"><span data-stu-id="abb29-112">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="abb29-113">Chociaż moduł adresu wysyłki nie zapewnia weryfikacji adresu, tę funkcję można wdrożyć poprzez dostosowanie.</span><span class="sxs-lookup"><span data-stu-id="abb29-113">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="abb29-114">Poniższa ilustracja przedstawia przykład nowego modułu adresu wysyłki na stronie kasy.</span><span class="sxs-lookup"><span data-stu-id="abb29-114">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Przykład modułu adresu wysyłki na stronie realizacja zamówienia](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="abb29-116">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="abb29-116">Module properties</span></span>

| <span data-ttu-id="abb29-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="abb29-117">Property name</span></span> | <span data-ttu-id="abb29-118">Wartości</span><span class="sxs-lookup"><span data-stu-id="abb29-118">Values</span></span> | <span data-ttu-id="abb29-119">opis</span><span class="sxs-lookup"><span data-stu-id="abb29-119">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="abb29-120">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="abb29-120">Heading</span></span> | <span data-ttu-id="abb29-121">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="abb29-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="abb29-122">Opcjonalny nagłówek modułu adresu wysyłki.</span><span class="sxs-lookup"><span data-stu-id="abb29-122">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="abb29-123">Pokaż typ adresu</span><span class="sxs-lookup"><span data-stu-id="abb29-123">Show address type</span></span> | <span data-ttu-id="abb29-124">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="abb29-124">**True** or **False**</span></span> | <span data-ttu-id="abb29-125">Jeśli ta właściwość opcjonalna ma wartość **Prawda**, wyświetlany jest typ adresu, np. **Dom** lub **Firma**.</span><span class="sxs-lookup"><span data-stu-id="abb29-125">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="abb29-126">Jeśli nie określono typu adresu, adres zostanie automatycznie zapisany jako **Typ**=**Inny**.</span><span class="sxs-lookup"><span data-stu-id="abb29-126">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="abb29-127">Dodaj moduł adresu wysyłki do strony realizacji zamówienia i ustaw wymagane właściwości</span><span class="sxs-lookup"><span data-stu-id="abb29-127">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="abb29-128">Moduł adresu wysyłki można dodać tylko do modułu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="abb29-128">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="abb29-129">Aby uzyskać więcej informacji na temat konfigurowania modułu adresu wysyłki i dodania go do strony realizacji transakcji, zapoznaj się z tematem [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="abb29-129">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="abb29-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="abb29-130">Additional resources</span></span>

[<span data-ttu-id="abb29-131">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="abb29-131">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="abb29-132">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="abb29-132">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="abb29-133">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="abb29-133">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="abb29-134">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="abb29-134">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="abb29-135">Moduł Opcje dostawy</span><span class="sxs-lookup"><span data-stu-id="abb29-135">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="abb29-136">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="abb29-136">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="abb29-137">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="abb29-137">Gift card module</span></span>](add-giftcard.md)
