---
title: Moduł kart upominkowych
description: W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 41f808d671bf5e7425390484ea30470e044899d8
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661249"
---
# <a name="gift-card-module"></a><span data-ttu-id="572ae-103">Moduł kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="572ae-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="572ae-104">W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="572ae-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="572ae-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="572ae-105">Overview</span></span>

<span data-ttu-id="572ae-106">Karty upominkowe są powszechną formą płatności, a moduł kart upominkowych może być używany w module realizacji transakcji w celu przyjmowania kart upominkowych.</span><span class="sxs-lookup"><span data-stu-id="572ae-106">Gift cards are a common form of payment, and the gift card module can be used in a checkout module to accept gift cards.</span></span> <span data-ttu-id="572ae-107">Moduł kart upominkowych wspiera Dynamics 365, SVS i karty upominkowe Givex.</span><span class="sxs-lookup"><span data-stu-id="572ae-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="572ae-108">Karty upominkowe SVS i Givex są realizowane przez dostawcę płatności Adyen.</span><span class="sxs-lookup"><span data-stu-id="572ae-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span>

<span data-ttu-id="572ae-109">Aby uzyskać więcej informacji na temat obsługi zewnętrznych kart upominkowych, takich jak SVS i Givex, zajrzyj do [Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md)</span><span class="sxs-lookup"><span data-stu-id="572ae-109">For more information on support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md)</span></span>

<span data-ttu-id="572ae-110">Poniższy obraz pokazuje przykład modułu karty podarunkowej na stronie realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="572ae-110">The following image shows an example of a gift card module on a checkout page.</span></span>

![Przykład modułu na karty upominkowej](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="572ae-112">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="572ae-112">Module properties</span></span>

- <span data-ttu-id="572ae-113">**Pokaż dodatkowe pola** — ta właściwość określa pola, które mają być wyświetlane w przypadku kart upominkowych, oprócz numeru karty upominkowej, który jest zawsze domyślnie wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="572ae-113">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="572ae-114">Na przykład niektóre karty upominkowe umożliwiają wyświetlanie osobistego numeru identyfikacyjnego (PIN), a inne umożliwiają wyświetlanie numeru PIN i daty ważności.</span><span class="sxs-lookup"><span data-stu-id="572ae-114">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="572ae-115">Można również ustawić tę właściwość na „Brak”, co spowoduje wyświetlenie numeru karty upominkowej bez dodatkowych pól.</span><span class="sxs-lookup"><span data-stu-id="572ae-115">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="572ae-116">Obsługiwane wartości:</span><span class="sxs-lookup"><span data-stu-id="572ae-116">Supported values:</span></span>
-   <span data-ttu-id="572ae-117">PIN</span><span class="sxs-lookup"><span data-stu-id="572ae-117">PIN</span></span>
-   <span data-ttu-id="572ae-118">Data ważności</span><span class="sxs-lookup"><span data-stu-id="572ae-118">Expiration date</span></span>
-   <span data-ttu-id="572ae-119">Numer PIN i data ważności</span><span class="sxs-lookup"><span data-stu-id="572ae-119">PIN and expiration date</span></span> 
-   <span data-ttu-id="572ae-120">None</span><span class="sxs-lookup"><span data-stu-id="572ae-120">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="572ae-121">Ustawienia witryny dla modułów kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="572ae-121">Site settings for gift card modules</span></span>

<span data-ttu-id="572ae-122">W konstruktorze witryn Commerce w **Ustawienia witryny \> Rozszerzenia** istnieje ustawienie modułu kart upominkowych o nazwie **Obsługiwany typ karty upominkowej**.</span><span class="sxs-lookup"><span data-stu-id="572ae-122">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="572ae-123">To ustawienie obsługuje trzy wartości:</span><span class="sxs-lookup"><span data-stu-id="572ae-123">This setting supports three values:</span></span>
- <span data-ttu-id="572ae-124">**Dynamics 365 — karta upominkowa** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="572ae-124">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="572ae-125">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="572ae-125">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="572ae-126">**Karty upominkowe SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="572ae-126">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="572ae-127">To ustawienie jest obsługiwane dla użytkowników anonimowych oraz zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="572ae-127">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="572ae-128">**Karty upominkowe Dynamics 365, SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365, SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="572ae-128">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="572ae-129">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="572ae-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="572ae-130">Dodawanie modułu kart upominkowych do strony</span><span class="sxs-lookup"><span data-stu-id="572ae-130">Add a gift card module to a page</span></span>

<span data-ttu-id="572ae-131">Aby uzyskać instrukcje dotyczące dodawania modułu kart upominkowych do strony realizacji transakcji i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="572ae-131">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="572ae-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="572ae-132">Additional resources</span></span>

[<span data-ttu-id="572ae-133">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="572ae-133">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="572ae-134">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="572ae-134">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="572ae-135">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="572ae-135">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="572ae-136">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="572ae-136">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="572ae-137">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="572ae-137">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="572ae-138">Moduł Opcje dostawy</span><span class="sxs-lookup"><span data-stu-id="572ae-138">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="572ae-139">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="572ae-139">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="572ae-140">Obsługa zewnętrznych kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="572ae-140">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
