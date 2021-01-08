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
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fa6b98bb41c0845cfa3ab36767f304ad70f46399
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2020
ms.locfileid: "4415105"
---
# <a name="gift-card-module"></a><span data-ttu-id="5a192-103">Moduł kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="5a192-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5a192-104">W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5a192-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5a192-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="5a192-105">Overview</span></span>

<span data-ttu-id="5a192-106">Moduły kart upominkowych można używać w module realizacji transakcji w celu przyjmowania kart upominkowych, bardzo popularnej metody płatności w transakcjach handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="5a192-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="5a192-107">Moduł kart upominkowych wspiera Dynamics 365, SVS i karty upominkowe Givex.</span><span class="sxs-lookup"><span data-stu-id="5a192-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="5a192-108">Karty upominkowe SVS i Givex są realizowane przez dostawcę płatności Adyen.</span><span class="sxs-lookup"><span data-stu-id="5a192-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="5a192-109">Aby uzyskać więcej informacji na temat obsługi zewnętrznych kart upominkowych, takich jak SVS i Givex, zajrzyj do [Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="5a192-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5a192-110">Obsługa realizowania kart upominkowych SVS i Givex w procesie realizacji transakcji jest dostępna w wydaniu Dynamics 365 Commerce 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="5a192-110">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="5a192-111">Dostępne są dwa moduły karty upominkowej:</span><span class="sxs-lookup"><span data-stu-id="5a192-111">There are two gift card modules available:</span></span>

- <span data-ttu-id="5a192-112">**Karta upominkowa** — ten moduł może być używany na stronie realizacji transakcji, aby zrealizować kartę upominkową jako ofertę płatności.</span><span class="sxs-lookup"><span data-stu-id="5a192-112">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="5a192-113">**Sprawdzanie salda karty upominkowej** — ten moduł może być używany na dowolnej stronie w celu sprawdzenia salda na karcie upominkowej.</span><span class="sxs-lookup"><span data-stu-id="5a192-113">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="5a192-114">Ten moduł jest dostępny w Commerce w wersji 10.0.14 i nowszej.</span><span class="sxs-lookup"><span data-stu-id="5a192-114">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="5a192-115">Obsługa modułu kontroli salda kart upominkowych jest dostępna w wydaniu Dynamics 365 Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="5a192-115">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="5a192-116">Poniższy obraz pokazuje przykład modułu karty podarunkowej na stronie realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="5a192-116">The following image shows an example of a gift card module on a checkout page.</span></span>

![Przykład modułu na karty upominkowej](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="5a192-118">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="5a192-118">Module properties</span></span>

- <span data-ttu-id="5a192-119">**Pokaż dodatkowe pola** — ta właściwość określa pola, które mają być wyświetlane w przypadku kart upominkowych, oprócz numeru karty upominkowej, który jest zawsze domyślnie wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="5a192-119">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="5a192-120">Na przykład niektóre karty upominkowe umożliwiają wyświetlanie osobistego numeru identyfikacyjnego (PIN), a inne umożliwiają wyświetlanie numeru PIN i daty ważności.</span><span class="sxs-lookup"><span data-stu-id="5a192-120">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="5a192-121">Można również ustawić tę właściwość na „Brak”, co spowoduje wyświetlenie numeru karty upominkowej bez dodatkowych pól.</span><span class="sxs-lookup"><span data-stu-id="5a192-121">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="5a192-122">Obsługiwane wartości:</span><span class="sxs-lookup"><span data-stu-id="5a192-122">Supported values:</span></span>
-   <span data-ttu-id="5a192-123">PIN</span><span class="sxs-lookup"><span data-stu-id="5a192-123">PIN</span></span>
-   <span data-ttu-id="5a192-124">Data ważności</span><span class="sxs-lookup"><span data-stu-id="5a192-124">Expiration date</span></span>
-   <span data-ttu-id="5a192-125">Numer PIN i data ważności</span><span class="sxs-lookup"><span data-stu-id="5a192-125">PIN and expiration date</span></span> 
-   <span data-ttu-id="5a192-126">None</span><span class="sxs-lookup"><span data-stu-id="5a192-126">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="5a192-127">Ustawienia witryny dla modułów kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="5a192-127">Site settings for gift card modules</span></span>

<span data-ttu-id="5a192-128">W konstruktorze witryn Commerce w **Ustawienia witryny \> Rozszerzenia** istnieje ustawienie modułu kart upominkowych o nazwie **Obsługiwany typ karty upominkowej**.</span><span class="sxs-lookup"><span data-stu-id="5a192-128">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="5a192-129">To ustawienie obsługuje trzy wartości:</span><span class="sxs-lookup"><span data-stu-id="5a192-129">This setting supports three values:</span></span>
- <span data-ttu-id="5a192-130">**Dynamics 365 — karta upominkowa** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5a192-130">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="5a192-131">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="5a192-131">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="5a192-132">**Karty upominkowe SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="5a192-132">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="5a192-133">To ustawienie jest obsługiwane dla użytkowników anonimowych oraz zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="5a192-133">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="5a192-134">**Karty upominkowe Dynamics 365, SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365, SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="5a192-134">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="5a192-135">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="5a192-135">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a192-136">Te ustawienia są dostępne w wydaniu Dynamics 365 Commerce 10.0.11 i są wymagane tylko wtedy, gdy potrzebna jest pomoc techniczna dla kart upominkowych SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="5a192-136">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="5a192-137">W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="5a192-137">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="5a192-138">Aby uzyskać instrukcje dotyczące aktualizowania pliku appsettings.json, zajrzyj do [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="5a192-138">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="5a192-139">Dodawanie modułu kart upominkowych do strony</span><span class="sxs-lookup"><span data-stu-id="5a192-139">Add a gift card module to a page</span></span>

<span data-ttu-id="5a192-140">Aby uzyskać instrukcje dotyczące dodawania modułu kart upominkowych do strony realizacji transakcji i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="5a192-140">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5a192-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5a192-141">Additional resources</span></span>

[<span data-ttu-id="5a192-142">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="5a192-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="5a192-143">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="5a192-143">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="5a192-144">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="5a192-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="5a192-145">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="5a192-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="5a192-146">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="5a192-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="5a192-147">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="5a192-147">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="5a192-148">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="5a192-148">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="5a192-149">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="5a192-149">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="5a192-150">Obsługa zewnętrznych kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="5a192-150">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="5a192-151">Aktualizacje zestawu SDK i biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="5a192-151">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
