---
title: Moduł kart upominkowych
description: W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8db7e597241f1fd552f6b960c2b57b0ba83da949
ms.sourcegitcommit: efde05c758b2e02960760d875569d780d77d5550
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/29/2021
ms.locfileid: "5962770"
---
# <a name="gift-card-module"></a><span data-ttu-id="71c0a-103">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="71c0a-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="71c0a-104">W tym temacie opisano moduły kart upominkowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="71c0a-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="71c0a-105">Moduły kart upominkowych można używać w module realizacji transakcji w celu przyjmowania kart upominkowych, bardzo popularnej metody płatności w transakcjach handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="71c0a-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="71c0a-106">Moduł kart upominkowych wspiera Dynamics 365, SVS i karty upominkowe Givex.</span><span class="sxs-lookup"><span data-stu-id="71c0a-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="71c0a-107">Karty upominkowe SVS i Givex są realizowane przez dostawcę płatności Adyen.</span><span class="sxs-lookup"><span data-stu-id="71c0a-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="71c0a-108">Aby uzyskać więcej informacji na temat obsługi zewnętrznych kart upominkowych, takich jak SVS i Givex, zajrzyj do [Obsługa zewnętrznych kart upominkowych](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="71c0a-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="71c0a-109">Obsługa realizowania kart upominkowych SVS i Givex w procesie realizacji transakcji jest dostępna w wydaniu Dynamics 365 Commerce 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="71c0a-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="71c0a-110">Dostępne są dwa moduły karty upominkowej:</span><span class="sxs-lookup"><span data-stu-id="71c0a-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="71c0a-111">**Karta upominkowa** — ten moduł może być używany na stronie realizacji transakcji, aby zrealizować kartę upominkową jako ofertę płatności.</span><span class="sxs-lookup"><span data-stu-id="71c0a-111">**Gift card** – This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="71c0a-112">**Sprawdzanie salda karty upominkowej** — ten moduł może być używany na dowolnej stronie w celu sprawdzenia salda na karcie upominkowej.</span><span class="sxs-lookup"><span data-stu-id="71c0a-112">**Gift card balance check** – This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="71c0a-113">Ten moduł jest dostępny w Commerce w wersji 10.0.14 i nowszej.</span><span class="sxs-lookup"><span data-stu-id="71c0a-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="71c0a-114">Obsługa modułu kontroli salda kart upominkowych jest dostępna w wydaniu Dynamics 365 Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="71c0a-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="71c0a-115">Poniższy obraz pokazuje przykład modułu karty podarunkowej na stronie realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="71c0a-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Przykład modułu na karty upominkowej](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="71c0a-117">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="71c0a-117">Module properties</span></span>

- <span data-ttu-id="71c0a-118">**Pokaż dodatkowe pola** — ta właściwość określa pola, które mają być wyświetlane w przypadku kart upominkowych, oprócz numeru karty upominkowej, który jest zawsze domyślnie wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="71c0a-118">**Show additional fields** – This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="71c0a-119">Na przykład niektóre karty upominkowe umożliwiają wyświetlanie osobistego numeru identyfikacyjnego (PIN), a inne umożliwiają wyświetlanie numeru PIN i daty ważności.</span><span class="sxs-lookup"><span data-stu-id="71c0a-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="71c0a-120">Można również ustawić tę właściwość na „Brak”, co spowoduje wyświetlenie numeru karty upominkowej bez dodatkowych pól.</span><span class="sxs-lookup"><span data-stu-id="71c0a-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="71c0a-121">Obsługiwane wartości:</span><span class="sxs-lookup"><span data-stu-id="71c0a-121">Supported values:</span></span>
-   <span data-ttu-id="71c0a-122">PIN</span><span class="sxs-lookup"><span data-stu-id="71c0a-122">PIN</span></span>
-   <span data-ttu-id="71c0a-123">Data ważności</span><span class="sxs-lookup"><span data-stu-id="71c0a-123">Expiration date</span></span>
-   <span data-ttu-id="71c0a-124">Numer PIN i data ważności</span><span class="sxs-lookup"><span data-stu-id="71c0a-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="71c0a-125">None</span><span class="sxs-lookup"><span data-stu-id="71c0a-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="71c0a-126">Ustawienia witryny dla modułów kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="71c0a-126">Site settings for gift card modules</span></span>

<span data-ttu-id="71c0a-127">W konstruktorze witryn Commerce w **Ustawienia witryny \> Rozszerzenia** istnieje ustawienie modułu kart upominkowych o nazwie **Obsługiwany typ karty upominkowej**.</span><span class="sxs-lookup"><span data-stu-id="71c0a-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="71c0a-128">To ustawienie obsługuje trzy wartości:</span><span class="sxs-lookup"><span data-stu-id="71c0a-128">This setting supports three values:</span></span>
- <span data-ttu-id="71c0a-129">**Dynamics 365 — karta upominkowa** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="71c0a-129">**Dynamics 365 gift card** – When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="71c0a-130">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="71c0a-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="71c0a-131">**Karty upominkowe SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="71c0a-131">**SVS and Givex gift cards** – When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="71c0a-132">To ustawienie jest obsługiwane dla użytkowników anonimowych oraz zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="71c0a-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="71c0a-133">**Karty upominkowe Dynamics 365, SVS i Givex** — po zastosowaniu tego ustawienia moduł kart upominkowych umożliwia realizację kart upominkowych Dynamics 365, SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="71c0a-133">**Dynamics 365, SVS, and Givex gift cards** – When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="71c0a-134">To ustawienie jest obsługiwane tylko dla użytkowników zalogowanych w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="71c0a-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71c0a-135">Te ustawienia są dostępne w wydaniu Dynamics 365 Commerce 10.0.11 i są wymagane tylko wtedy, gdy potrzebna jest pomoc techniczna dla kart upominkowych SVS i Givex.</span><span class="sxs-lookup"><span data-stu-id="71c0a-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="71c0a-136">W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="71c0a-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="71c0a-137">Aby uzyskać instrukcje dotyczące aktualizowania pliku appsettings.json, zajrzyj do [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="71c0a-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a><span data-ttu-id="71c0a-138">Rozszerzanie wewnętrznych kart upominkowych do użytku w witrynach handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="71c0a-138">Extend internal gift cards for use in e-commerce storefronts</span></span>

<span data-ttu-id="71c0a-139">Domyślnie wewnętrzne karty upominkowe nie są przystosowane do używania w witrynach handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="71c0a-139">By default, internal gift cards aren't optimized for use in e-commerce storefronts.</span></span> <span data-ttu-id="71c0a-140">Dlatego zanim zezwolisz na to, aby wewnętrzne karty upominkowe zostały użyte do płatności, musisz je skonfigurować za pomocą rozszerzeń, które ułatwiają ich zabezpieczanie.</span><span class="sxs-lookup"><span data-stu-id="71c0a-140">Therefore, before you allow internal gift cards to be used for payment, you should configure them with extensions that help make them more secure.</span></span> <span data-ttu-id="71c0a-141">Oto obszary kart upominkowych, które należy rozszerzyć, zanim zezwolisz na używanie w środowisku produkcyjnym wewnętrznych kart upominkowych:</span><span class="sxs-lookup"><span data-stu-id="71c0a-141">Here are the gift card areas that you should extend before you allow internal gift cards to be used in production:</span></span>

- <span data-ttu-id="71c0a-142">**Numer karty upominkowej** — Sekwencje numerów służą do generowania numerów kart upominkowych dla wewnętrznych kart upominkowych.</span><span class="sxs-lookup"><span data-stu-id="71c0a-142">**Gift card number** – Number sequences are used to generate gift card numbers for internal gift cards.</span></span> <span data-ttu-id="71c0a-143">Ponieważ sekwencje numerów można łatwo przewidzieć, należy rozszerzyć generowanie numerów kart upominkowych, tak aby numery wystawianych kart upominkowych były wybierane losowo, w sposób kryptograficznie bezpieczny.</span><span class="sxs-lookup"><span data-stu-id="71c0a-143">Because number sequences can easily be predicted, you should extend the generation of gift card numbers so that random, cryptographically secure strings are used for the gift card numbers that are issued.</span></span>
- <span data-ttu-id="71c0a-144">**GetBalance** — Interfejs API **GetBalance** służy do odczytywania sald karty upominkowej.</span><span class="sxs-lookup"><span data-stu-id="71c0a-144">**GetBalance** – The **GetBalance** API is used to look up gift card balances.</span></span> <span data-ttu-id="71c0a-145">Domyślnie ten interfejs API jest publiczny.</span><span class="sxs-lookup"><span data-stu-id="71c0a-145">By default, this API public.</span></span> <span data-ttu-id="71c0a-146">Jeśli do wyszukiwania sald karty upominkowej nie jest wymagany numer PIN, istnieje ryzyko użycia interfejsu API **GetBalance** do wyszukiwania numerów kart upominkowych z saldami.</span><span class="sxs-lookup"><span data-stu-id="71c0a-146">If a PIN isn't required to look up gift card balances, there is a risk that brute force attacks could use the **GetBalance** API to try to look up gift card numbers that have balances.</span></span> <span data-ttu-id="71c0a-147">Wdrożenie zarówno wymagań dotyczących numeru PIN dla wewnętrznych kart upominkowych, jak i dławienie interfejsu API pomaga złagodzić ryzyko.</span><span class="sxs-lookup"><span data-stu-id="71c0a-147">By implementing both PIN requirements for internal gift cards and API throttling, you can help mitigate the risk.</span></span>
- <span data-ttu-id="71c0a-148">**PIN** — domyślnie wewnętrzne karty upominkowe nie obsługują numeru PIN.</span><span class="sxs-lookup"><span data-stu-id="71c0a-148">**PIN** – By default, internal gift cards don't support PINs.</span></span> <span data-ttu-id="71c0a-149">Wewnętrzne karty upominkowe należy rozszerzyć o wymóg podania PIN w celu odczytania salda.</span><span class="sxs-lookup"><span data-stu-id="71c0a-149">You should extend internal gift cards so that a PIN is required to look up balances.</span></span> <span data-ttu-id="71c0a-150">Ta funkcja umożliwia także blokowanie kart upominkowych po kolejnych niepoprawnych próbach wprowadzenia numeru PIN.</span><span class="sxs-lookup"><span data-stu-id="71c0a-150">This functionality can also be used to lock gift cards after consecutive incorrect attempts to enter the PIN.</span></span>

## <a name="enable-gift-card-payments-for-guest-checkout"></a><span data-ttu-id="71c0a-151">Włączanie płatności kartą upominkową podczas realizacji transakcji przez gościa</span><span class="sxs-lookup"><span data-stu-id="71c0a-151">Enable gift card payments for guest checkout</span></span>

<span data-ttu-id="71c0a-152">Domyślnie płatności kartą upominkową nie są dostępne podczas realizacji transakcji przez gościa (anonimowego).</span><span class="sxs-lookup"><span data-stu-id="71c0a-152">By default, gift card payments aren't enabled for guest (anonymous) checkout.</span></span> <span data-ttu-id="71c0a-153">Aby je włączyć, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="71c0a-153">To enable them, follow these steps.</span></span>

1. <span data-ttu-id="71c0a-154">W centrali Commerce przejdź do lokalizacji **Retail i Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Operacje punktu sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="71c0a-154">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS Operations**.</span></span>
1. <span data-ttu-id="71c0a-155">Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) nagłówek siatki, a następnie wybierz polecenie **Wstaw kolumny**.</span><span class="sxs-lookup"><span data-stu-id="71c0a-155">Select and hold (or right-click) the header of the grid, and then select **Insert columns**.</span></span>
1. <span data-ttu-id="71c0a-156">W oknie dialogowym **Wstawianie kolumn** zaznacz pole wyboru **AllowAnonymousAccess**.</span><span class="sxs-lookup"><span data-stu-id="71c0a-156">In the **Insert columns** dialog box, select the **AllowAnonymousAccess** check box.</span></span>
1. <span data-ttu-id="71c0a-157">Wybierz **Aktualizuj**.</span><span class="sxs-lookup"><span data-stu-id="71c0a-157">Select **Update**.</span></span>
1. <span data-ttu-id="71c0a-158">W przypadku operacji **520** (saldo na karcie upominkowej) i **214** ustaw wartość **AllowAnonymousAccess** na **1**.</span><span class="sxs-lookup"><span data-stu-id="71c0a-158">For operations **520** (Gift card balance) and **214**, set the **AllowAnonymousAccess** value to **1**.</span></span>
1. <span data-ttu-id="71c0a-159">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="71c0a-159">Select **Save**.</span></span>
1. <span data-ttu-id="71c0a-160">Wykonaj zadanie harmonogram **1090**, aby zsynchronizować zmiany z bazą danych kanału.</span><span class="sxs-lookup"><span data-stu-id="71c0a-160">Run the **1090** scheduler job to sync changes to the channel database.</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="71c0a-161">Dodawanie modułu kart upominkowych do strony</span><span class="sxs-lookup"><span data-stu-id="71c0a-161">Add a gift card module to a page</span></span>

<span data-ttu-id="71c0a-162">Aby uzyskać instrukcje dotyczące dodawania modułu kart upominkowych do strony realizacji transakcji i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="71c0a-162">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71c0a-163">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="71c0a-163">Additional resources</span></span>

[<span data-ttu-id="71c0a-164">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="71c0a-164">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="71c0a-165">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="71c0a-165">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="71c0a-166">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="71c0a-166">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="71c0a-167">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="71c0a-167">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="71c0a-168">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="71c0a-168">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="71c0a-169">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="71c0a-169">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="71c0a-170">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="71c0a-170">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="71c0a-171">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="71c0a-171">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="71c0a-172">Obsługa zewnętrznych kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="71c0a-172">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="71c0a-173">Aktualizacje zestawu SDK i biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="71c0a-173">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
