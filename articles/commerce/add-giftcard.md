---
title: Moduł kart upominkowych
description: W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 4cc947b9d6f3cfa51bce2155170c49e9529d0f7d
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761088"
---
# <a name="gift-card-module"></a><span data-ttu-id="6b74a-103">Moduł kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="6b74a-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="6b74a-104">W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6b74a-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6b74a-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6b74a-105">Overview</span></span>

<span data-ttu-id="6b74a-106">Moduły kart upominkowych można używać w module realizacji transakcji w celu przyjmowania kart upominkowych, bardzo popularnej metody płatności w transakcjach handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="6b74a-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="6b74a-107">Moduł kart upominkowych wspiera Dynamics 365, SVS i karty upominkowe Givex.</span><span class="sxs-lookup"><span data-stu-id="6b74a-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="6b74a-108">Karty upominkowe SVS i Givex są realizowane przez dostawcę płatności Adyen.</span><span class="sxs-lookup"><span data-stu-id="6b74a-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="6b74a-109">Aby uzyskać więcej informacji na temat obsługi zewnętrznych kart upominkowych, takich jak SVS i Givex, zajrzyj do [Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="6b74a-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

<span data-ttu-id="6b74a-110">Dostępne są dwa moduły karty upominkowej:</span><span class="sxs-lookup"><span data-stu-id="6b74a-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="6b74a-111">**Karta upominkowa** — ten moduł może być używany na stronie realizacji transakcji, aby zrealizować kartę upominkową jako ofertę płatności.</span><span class="sxs-lookup"><span data-stu-id="6b74a-111">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="6b74a-112">**Sprawdzanie salda karty upominkowej** — ten moduł może być używany na dowolnej stronie w celu sprawdzenia salda na karcie upominkowej.</span><span class="sxs-lookup"><span data-stu-id="6b74a-112">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="6b74a-113">Ten moduł jest dostępny w Commerce w wersji 10.0.14 i nowszej.</span><span class="sxs-lookup"><span data-stu-id="6b74a-113">This module is available in Commerce release 10.0.14 and later.</span></span>

<span data-ttu-id="6b74a-114">Poniższy obraz pokazuje przykład modułu karty podarunkowej na stronie realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="6b74a-114">The following image shows an example of a gift card module on a checkout page.</span></span>

![Przykład modułu na karty upominkowej](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="6b74a-116">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="6b74a-116">Module properties</span></span>

- <span data-ttu-id="6b74a-117">**Pokaż dodatkowe pola** — ta właściwość określa pola, które mają być wyświetlane w przypadku kart upominkowych, oprócz numeru karty upominkowej, który jest zawsze domyślnie wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="6b74a-117">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="6b74a-118">Na przykład niektóre karty upominkowe umożliwiają wyświetlanie osobistego numeru identyfikacyjnego (PIN), a inne umożliwiają wyświetlanie numeru PIN i daty ważności.</span><span class="sxs-lookup"><span data-stu-id="6b74a-118">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="6b74a-119">Można również ustawić tę właściwość na „Brak”, co spowoduje wyświetlenie numeru karty upominkowej bez dodatkowych pól.</span><span class="sxs-lookup"><span data-stu-id="6b74a-119">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="6b74a-120">Obsługiwane wartości:</span><span class="sxs-lookup"><span data-stu-id="6b74a-120">Supported values:</span></span>
-   <span data-ttu-id="6b74a-121">PIN</span><span class="sxs-lookup"><span data-stu-id="6b74a-121">PIN</span></span>
-   <span data-ttu-id="6b74a-122">Data ważności</span><span class="sxs-lookup"><span data-stu-id="6b74a-122">Expiration date</span></span>
-   <span data-ttu-id="6b74a-123">Numer PIN i data ważności</span><span class="sxs-lookup"><span data-stu-id="6b74a-123">PIN and expiration date</span></span> 
-   <span data-ttu-id="6b74a-124">None</span><span class="sxs-lookup"><span data-stu-id="6b74a-124">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="6b74a-125">Ustawienia witryny dla modułów kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="6b74a-125">Site settings for gift card modules</span></span>

<span data-ttu-id="6b74a-126">W konstruktorze witryn Commerce w **Ustawienia witryny \> Rozszerzenia** istnieje ustawienie modułu kart upominkowych o nazwie **Obsługiwany typ karty upominkowej**.</span><span class="sxs-lookup"><span data-stu-id="6b74a-126">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="6b74a-127">To ustawienie obsługuje trzy wartości:</span><span class="sxs-lookup"><span data-stu-id="6b74a-127">This setting supports three values:</span></span>
- <span data-ttu-id="6b74a-128">**Dynamics 365 — karta upominkowa** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6b74a-128">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="6b74a-129">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="6b74a-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="6b74a-130">**Karty upominkowe SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="6b74a-130">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="6b74a-131">To ustawienie jest obsługiwane dla użytkowników anonimowych oraz zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="6b74a-131">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="6b74a-132">**Karty upominkowe Dynamics 365, SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365, SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="6b74a-132">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="6b74a-133">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="6b74a-133">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="6b74a-134">Dodawanie modułu kart upominkowych do strony</span><span class="sxs-lookup"><span data-stu-id="6b74a-134">Add a gift card module to a page</span></span>

<span data-ttu-id="6b74a-135">Aby uzyskać instrukcje dotyczące dodawania modułu kart upominkowych do strony realizacji transakcji i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="6b74a-135">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6b74a-136">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6b74a-136">Additional resources</span></span>

[<span data-ttu-id="6b74a-137">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="6b74a-137">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="6b74a-138">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="6b74a-138">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="6b74a-139">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="6b74a-139">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="6b74a-140">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="6b74a-140">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="6b74a-141">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="6b74a-141">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="6b74a-142">Moduł Opcje dostawy</span><span class="sxs-lookup"><span data-stu-id="6b74a-142">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="6b74a-143">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="6b74a-143">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="6b74a-144">Obsługa zewnętrznych kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="6b74a-144">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
