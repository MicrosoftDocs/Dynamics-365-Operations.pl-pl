---
title: Moduł kart upominkowych
description: W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: c024cc1b16ca60b2277eba2d7045020c2e67c3a0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206302"
---
# <a name="gift-card-module"></a><span data-ttu-id="0162e-103">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="0162e-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0162e-104">W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0162e-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="0162e-105">Moduły kart upominkowych można używać w module realizacji transakcji w celu przyjmowania kart upominkowych, bardzo popularnej metody płatności w transakcjach handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="0162e-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="0162e-106">Moduł kart upominkowych wspiera Dynamics 365, SVS i karty upominkowe Givex.</span><span class="sxs-lookup"><span data-stu-id="0162e-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="0162e-107">Karty upominkowe SVS i Givex są realizowane przez dostawcę płatności Adyen.</span><span class="sxs-lookup"><span data-stu-id="0162e-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="0162e-108">Aby uzyskać więcej informacji na temat obsługi zewnętrznych kart upominkowych, takich jak SVS i Givex, zajrzyj do [Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="0162e-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0162e-109">Obsługa realizowania kart upominkowych SVS i Givex w procesie realizacji transakcji jest dostępna w wydaniu Dynamics 365 Commerce 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="0162e-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="0162e-110">Dostępne są dwa moduły karty upominkowej:</span><span class="sxs-lookup"><span data-stu-id="0162e-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="0162e-111">**Karta upominkowa** — ten moduł może być używany na stronie realizacji transakcji, aby zrealizować kartę upominkową jako ofertę płatności.</span><span class="sxs-lookup"><span data-stu-id="0162e-111">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="0162e-112">**Sprawdzanie salda karty upominkowej** — ten moduł może być używany na dowolnej stronie w celu sprawdzenia salda na karcie upominkowej.</span><span class="sxs-lookup"><span data-stu-id="0162e-112">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="0162e-113">Ten moduł jest dostępny w Commerce w wersji 10.0.14 i nowszej.</span><span class="sxs-lookup"><span data-stu-id="0162e-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="0162e-114">Obsługa modułu kontroli salda kart upominkowych jest dostępna w wydaniu Dynamics 365 Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="0162e-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="0162e-115">Poniższy obraz pokazuje przykład modułu karty podarunkowej na stronie realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="0162e-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Przykład modułu na karty upominkowej](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="0162e-117">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="0162e-117">Module properties</span></span>

- <span data-ttu-id="0162e-118">**Pokaż dodatkowe pola** — ta właściwość określa pola, które mają być wyświetlane w przypadku kart upominkowych, oprócz numeru karty upominkowej, który jest zawsze domyślnie wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="0162e-118">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="0162e-119">Na przykład niektóre karty upominkowe umożliwiają wyświetlanie osobistego numeru identyfikacyjnego (PIN), a inne umożliwiają wyświetlanie numeru PIN i daty ważności.</span><span class="sxs-lookup"><span data-stu-id="0162e-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="0162e-120">Można również ustawić tę właściwość na „Brak”, co spowoduje wyświetlenie numeru karty upominkowej bez dodatkowych pól.</span><span class="sxs-lookup"><span data-stu-id="0162e-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="0162e-121">Obsługiwane wartości:</span><span class="sxs-lookup"><span data-stu-id="0162e-121">Supported values:</span></span>
-   <span data-ttu-id="0162e-122">PIN</span><span class="sxs-lookup"><span data-stu-id="0162e-122">PIN</span></span>
-   <span data-ttu-id="0162e-123">Data ważności</span><span class="sxs-lookup"><span data-stu-id="0162e-123">Expiration date</span></span>
-   <span data-ttu-id="0162e-124">Numer PIN i data ważności</span><span class="sxs-lookup"><span data-stu-id="0162e-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="0162e-125">None</span><span class="sxs-lookup"><span data-stu-id="0162e-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="0162e-126">Ustawienia witryny dla modułów kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="0162e-126">Site settings for gift card modules</span></span>

<span data-ttu-id="0162e-127">W konstruktorze witryn Commerce w **Ustawienia witryny \> Rozszerzenia** istnieje ustawienie modułu kart upominkowych o nazwie **Obsługiwany typ karty upominkowej**.</span><span class="sxs-lookup"><span data-stu-id="0162e-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="0162e-128">To ustawienie obsługuje trzy wartości:</span><span class="sxs-lookup"><span data-stu-id="0162e-128">This setting supports three values:</span></span>
- <span data-ttu-id="0162e-129">**Dynamics 365 — karta upominkowa** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0162e-129">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="0162e-130">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="0162e-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="0162e-131">**Karty upominkowe SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="0162e-131">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="0162e-132">To ustawienie jest obsługiwane dla użytkowników anonimowych oraz zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="0162e-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="0162e-133">**Karty upominkowe Dynamics 365, SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365, SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="0162e-133">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="0162e-134">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="0162e-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0162e-135">Te ustawienia są dostępne w wydaniu Dynamics 365 Commerce 10.0.11 i są wymagane tylko wtedy, gdy potrzebna jest pomoc techniczna dla kart upominkowych SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="0162e-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="0162e-136">W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="0162e-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="0162e-137">Aby uzyskać instrukcje dotyczące aktualizowania pliku appsettings.json, zajrzyj do [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="0162e-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="0162e-138">Dodawanie modułu kart upominkowych do strony</span><span class="sxs-lookup"><span data-stu-id="0162e-138">Add a gift card module to a page</span></span>

<span data-ttu-id="0162e-139">Aby uzyskać instrukcje dotyczące dodawania modułu kart upominkowych do strony realizacji transakcji i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="0162e-139">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0162e-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0162e-140">Additional resources</span></span>

[<span data-ttu-id="0162e-141">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="0162e-141">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0162e-142">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="0162e-142">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="0162e-143">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="0162e-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="0162e-144">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="0162e-144">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="0162e-145">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="0162e-145">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="0162e-146">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="0162e-146">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="0162e-147">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="0162e-147">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="0162e-148">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="0162e-148">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="0162e-149">Obsługa zewnętrznych kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="0162e-149">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="0162e-150">Aktualizacje zestawu SDK i biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="0162e-150">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]