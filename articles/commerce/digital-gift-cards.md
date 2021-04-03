---
title: Cyfrowe karty upominkowe w handlu elektronicznym
description: W tym temacie opisano, jak działają cyfrowe karty upominkowe w implementacji handlu elektronicznego Microsoft Dynamics 365 Commerce. Zawiera także przegląd ważnych kroków konfiguracji.
author: anupamar-ms
manager: annbe
ms.date: 12/15/2020
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
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: cbfa84770e4671fdf289e168345d8b815caee4f7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230565"
---
# <a name="e-commerce-digital-gift-cards"></a><span data-ttu-id="146b1-104">Cyfrowe karty upominkowe w handlu elektronicznym</span><span class="sxs-lookup"><span data-stu-id="146b1-104">E-commerce digital gift cards</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="146b1-105">W tym temacie opisano, jak działają cyfrowe karty upominkowe w implementacji handlu elektronicznego Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="146b1-105">This topic describes how digital gift cards work in the e-commerce implementation of Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="146b1-106">Zawiera także przegląd ważnych kroków konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="146b1-106">It also provides an overview of important configuration steps.</span></span>

<span data-ttu-id="146b1-107">W Dynamics 365 Commerce zakup cyfrowych kart podarunkowych przebiega tak samo, jak zakup innych produktów w systemie.</span><span class="sxs-lookup"><span data-stu-id="146b1-107">In Dynamics 365 Commerce, the purchase of digital gift cards follows the same flow as the purchase of other products in the system.</span></span> <span data-ttu-id="146b1-108">Nie trzeba konfigurować żadnych dodatkowych modułów.</span><span class="sxs-lookup"><span data-stu-id="146b1-108">No additional modules have to be configured.</span></span> <span data-ttu-id="146b1-109">Jeśli do koszyka dodano wiele kart podarunkowych, pozycje karty podarunkowej nie są agregowane w jednym wierszu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="146b1-109">If multiple gift cards are added to the cart, the gift card items aren't aggregated on a single sales line.</span></span> <span data-ttu-id="146b1-110">To zachowanie jest wymagane, ponieważ każdy wiersz sprzedaży jest fakturowany przy użyciu oddzielnego numeru karty upominkowej.</span><span class="sxs-lookup"><span data-stu-id="146b1-110">This behavior is required because each sales line is invoiced by using a separate gift card number.</span></span>

<span data-ttu-id="146b1-111">Zakup cyfrowych kart upominkowych jest obsługiwany w Dynamics 365 Commerce w wersji 10.0.16 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="146b1-111">The purchase of digital gift cards is supported in the Dynamics 365 Commerce 10.0.16 release and later.</span></span>

<span data-ttu-id="146b1-112">Na poniższej ilustracji pokazano przykład strony szczegółów produktu (PDP) dotyczącej cyfrowych kart upominkowych w witrynie Fabrikam-e-commerce.</span><span class="sxs-lookup"><span data-stu-id="146b1-112">The following illustration shows an example of the product details page (PDP) for a digital gift card on the Fabrikam e-commerce site.</span></span>

![Przykład cyfrowej karty upominkowej PDP w witrynie handlu elektronicznego firmy Fabrikam](./media/GiftcardPDP.PNG)

## <a name="turn-on-the-digital-gift-card-feature-in-commerce-headquarters"></a><span data-ttu-id="146b1-114">Włączanie funkcji cyfrowych kart upominkowych w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="146b1-114">Turn on the digital gift card feature in Commerce headquarters</span></span>

<span data-ttu-id="146b1-115">Aby przepływ zakupów cyfrowych bonów upominkowych działał w Dynamics 365 Commerce, funkcja **Kupowanie bonów upominkowych w handlu elektronicznym** musi być włączona w centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="146b1-115">For the purchase flow for digital gift cards to work in Dynamics 365 Commerce, the **Purchasing gift card on e-Commerce feature** feature must be turned on in Commerce headquarters.</span></span> <span data-ttu-id="146b1-116">Funkcję można znaleźć w obszarze roboczym **Zarządzania funkcjami** w Commerce headquarters, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="146b1-116">You can find the feature in the **Feature management** workspace in Commerce headquarters, as shown in the following illustration.</span></span>

![Obszar roboczy zarządzania funkcjami w Commerce headquarters](./media/Featureflag.PNG)

## <a name="configure-a-digital-gift-card-in-commerce-headquarters"></a><span data-ttu-id="146b1-118">Skonfiguruj cyfrową kartę upominkową w siedzibie Commerce</span><span class="sxs-lookup"><span data-stu-id="146b1-118">Configure a digital gift card in Commerce headquarters</span></span>

<span data-ttu-id="146b1-119">Produkty z cyfrowymi kartami upominkowymi należy skonfigurować w centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="146b1-119">Digital gift card products should be configured in Commerce headquarters.</span></span> <span data-ttu-id="146b1-120">Proces przypomina proces dla innych produktów.</span><span class="sxs-lookup"><span data-stu-id="146b1-120">The process resembles the process for other products.</span></span> <span data-ttu-id="146b1-121">Jednak poniższe ważne kroki są specyficzne dla konfiguracji kart podarunkowych do zakupu.</span><span class="sxs-lookup"><span data-stu-id="146b1-121">However, the following important steps are specific to the configuration of gift cards for purchase.</span></span> <span data-ttu-id="146b1-122">Aby uzyskać więcej informacji o tworzeniu i konfigurowaniu produktów, należy zapoznać się z tematem [Tworzenie nowego produktu w programie Commerce](create-new-product-commerce.md).</span><span class="sxs-lookup"><span data-stu-id="146b1-122">For more information about how to create and configure products, see [Create a new product in Commerce](create-new-product-commerce.md).</span></span>

- <span data-ttu-id="146b1-123">Podczas konfigurowania produktów cyfrowych kart upominkowych w oknie dialogowym **Nowy produkt** ustaw w polu **Typ produktu** wartość **Usługa**.</span><span class="sxs-lookup"><span data-stu-id="146b1-123">When you configure digital gift card products in the **New product** dialog box, set the **Product type** field to **Service**.</span></span> <span data-ttu-id="146b1-124">(Aby otworzyć okno dialogowe, przejdź do **Handel detaliczny i inny \> Produkty i kategorie \> Produkty według kategorii** i wybierz opcję **Nowy**.) Produkty typu **Usługa** nie są sprawdzane pod kątem dostępnych zapasów przed złożonem zamówieniem.</span><span class="sxs-lookup"><span data-stu-id="146b1-124">(To open the dialog box, go to **Retail and commerce \> Products and categories \> Products by category**, and select **New**.) Products of the **Service** type aren't checked for available inventory before an order is placed.</span></span> <span data-ttu-id="146b1-125">Aby uzyskać więcej informacji, zobacz temat [Tworzenie nowego produktu](create-new-product-commerce.md#create-a-new-product).</span><span class="sxs-lookup"><span data-stu-id="146b1-125">For more information, see [Create a new product](create-new-product-commerce.md#create-a-new-product).</span></span>
- <span data-ttu-id="146b1-126">Na stronie **Parametry commerce**, na karcie **Księgowanie** w polu **Produkt karty upominkowej** należy ustawić **Cyfrową kartę upominkową**, tak jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="146b1-126">On the **Commerce parameters** page, on the **Posting** tab, the **Gift card product** field must be set to **Digital Gift Card**, as shown in the following illustration.</span></span> <span data-ttu-id="146b1-127">Jeśli produkt jest zewnętrzną kartą upominkową, zobacz [Pomoc techniczna dla zewnętrznych kart upominkowych](./dev-itpro/gift-card.md), aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="146b1-127">If the product is an external gift card, see [Support for external gift cards](./dev-itpro/gift-card.md) for more information.</span></span>

    ![Pole produktu karty upominkowej w programie Commerce Headquarters](./media/PostGiftcard.png)

- <span data-ttu-id="146b1-129">Jeśli karta upominkowa musi obsługiwać wiele wstępnie zdefiniowanych kwot (na przykład $25, $50, i $100), do skonfigurowania tych wstępnie zdefiniowanych kwot należy użyć wymiaru **Rozmiar**.</span><span class="sxs-lookup"><span data-stu-id="146b1-129">If a gift card must support multiple predefined amounts (for example, $25, $50, and $100), the **Size** dimension should be used to set up those predefined amounts.</span></span> <span data-ttu-id="146b1-130">Każda wstępnie zdefiniowana kwota będzie wariantem.</span><span class="sxs-lookup"><span data-stu-id="146b1-130">Each predefined amount will be a variant.</span></span> <span data-ttu-id="146b1-131">Aby uzyskać więcej informacji, zobacz temat [Wymiary produktów](https://docs.microsoft.com/dynamics365/supply-chain/pim/product-dimensions?toc=/dynamics365/retail/toc.json).</span><span class="sxs-lookup"><span data-stu-id="146b1-131">For more information, see [Product dimensions](https://docs.microsoft.com/dynamics365/supply-chain/pim/product-dimensions?toc=/dynamics365/retail/toc.json).</span></span>
- <span data-ttu-id="146b1-132">Jeśli klienci muszą mieć możliwość określenia niestandardowej kwoty karty podarunkowej, najpierw skonfiguruj wariant, który pozwala na niestandardową kwotę.</span><span class="sxs-lookup"><span data-stu-id="146b1-132">If customers must be able to specify a custom amount for a gift card, first set up a variant that allows for a custom amount.</span></span> <span data-ttu-id="146b1-133">Następnie otwórz produkt ze strony **Kategorii Zwolnione produkty**, a następnie na skróconej karcie **Commerce** ustaw w polu **Klucz w cenie** wartość **Musi być wejściowa nowa cena**, tak jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="146b1-133">Next, open the product from the **Released products in category** page, and then, on the **Commerce** FastTab, set the **Key in price** field to **Must key in new price**, as shown in the following illustration.</span></span> <span data-ttu-id="146b1-134">To ustawienie zapewnia klientom możliwość wprowadzenia ceny podczas przeglądania produktu na PDP.</span><span class="sxs-lookup"><span data-stu-id="146b1-134">This setting ensures that customers can enter a price when they browse the product on a PDP.</span></span>

    ![Klucz w polu ceny w Commerce headquarters](./media/KeyInPrice.png)

- <span data-ttu-id="146b1-136">Jako tryb dostawy cyfrowych kart upominkowych należy ustawić wartość **Elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="146b1-136">The mode of delivery for a digital gift card must be set to **Electronic**.</span></span> <span data-ttu-id="146b1-137">Na stronie **Tryby dostawy** (**Handel detaliczny i inny \> Ustawienia kanału \> Metody dostawy**) wybierz **Elektroniczną** tryb dostawy w okienku listy, a następnie dodaj do siatki produkt cyfrowych kart upominkowych na skróconej karcie **Produkty**, tak jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="146b1-137">On the **Modes of delivery** page (**Retail and commerce \> Channel setup \> Modes of delivery**), select the **Electronic** mode of delivery in the list pane, and then add the digital gift card product to the grid on the **Products** FastTab, as shown in the following illustration.</span></span> <span data-ttu-id="146b1-138">Aby uzyskać więcej informacji, zobacz temat [Ustaw metody dostawy](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="146b1-138">For more information, see [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

    ![Cyfrowe karty upominkowe na stronie Tryb dostawy w Commerce headquarters](./media/ElectronicMode.PNG)

- <span data-ttu-id="146b1-140">Upewnij się, że w programie Commerce Headquarters utworzono profil funkcji online i skojarzono go z jego sklepem internetowym.</span><span class="sxs-lookup"><span data-stu-id="146b1-140">Make sure that an online functionality profile has been created and associated with your online store in Commerce headquarters.</span></span> <span data-ttu-id="146b1-141">W profilu funkcji dla opcji **Agregacja produktów** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="146b1-141">In the functionality profile, set the **Aggregate products** option to **Yes**.</span></span> <span data-ttu-id="146b1-142">To ustawienie zapewnia agregację wszystkich pozycji z wyjątkiem kart podarunkowych.</span><span class="sxs-lookup"><span data-stu-id="146b1-142">This setting ensures that all items except gift cards are aggregated.</span></span> <span data-ttu-id="146b1-143">Aby uzyskać więcej informacji, zobacz temat [Tworzenie profilu funkcji online](online-functionality-profile.md).</span><span class="sxs-lookup"><span data-stu-id="146b1-143">For more information, see [Create an online functionality profile](online-functionality-profile.md).</span></span>
- <span data-ttu-id="146b1-144">Aby zapewnić, że odbiorcy otrzymają wiadomość e-mail po zafaktureniu karty upominkowej, utwórz nowy typ powiadomienia pocztą e-mail na stronie **Profile powiadomień pocztą e-mail** i ustaw w polu **Typ powiadomienia pocztą e-mail** wartość **Wystaw kartę upominkową**.</span><span class="sxs-lookup"><span data-stu-id="146b1-144">To ensure that customers receive an email after a gift card is invoiced, create a new email notification type on the **Email notification profiles** page, and set the **Email notification type** field to **Issue gift card**.</span></span> <span data-ttu-id="146b1-145">Więcej informacji jest dostępnych w artykule [Konfigurowanie profilu powiadomienia](email-notification-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="146b1-145">For more information, see [Set up an email notification profile](email-notification-profiles.md).</span></span>

## <a name="add-product-images-to-the-commerce-site-builder-media-library"></a><span data-ttu-id="146b1-146">Dodawanie obrazów produktów do biblioteki multimediów konstruktora witryn Commerce</span><span class="sxs-lookup"><span data-stu-id="146b1-146">Add product images to the Commerce site builder Media library</span></span>

<span data-ttu-id="146b1-147">Musisz dodać obrazy produktów dla produktów cyfrowych kart upominkowych do biblioteki multimediów konstruktora witryn Commerce.</span><span class="sxs-lookup"><span data-stu-id="146b1-147">You must add product images for digital gift card products to the Commerce site builder Media library.</span></span> <span data-ttu-id="146b1-148">Upewnij się, że nazwy plików obrazów kart podarunkowych są zgodne z konwencją nazewnictwa zdjęć produktów w Twojej witrynie.</span><span class="sxs-lookup"><span data-stu-id="146b1-148">Make sure that the file names of the gift card image files follow your site's naming conventions for product images.</span></span> <span data-ttu-id="146b1-149">Aby uzyskać więcej informacji, zobacz [Przekazanie obrazów](dam-upload-images.md).</span><span class="sxs-lookup"><span data-stu-id="146b1-149">For more information, see [Upload images](dam-upload-images.md).</span></span>

## <a name="configure-a-custom-amount-for-a-digital-gift-card-in-commerce-site-builder"></a><span data-ttu-id="146b1-150">Skonfiguruj niestandardową kwotę dla cyfrowej karty upominkowej w narzędziu do tworzenia witryn Commerce</span><span class="sxs-lookup"><span data-stu-id="146b1-150">Configure a custom amount for a digital gift card in Commerce site builder</span></span>

<span data-ttu-id="146b1-151">Jeśli cyfrowa karta podarunkowa jest skonfigurowana tak, aby zezwalała na niestandardową kwotę, to zachowanie musi być również włączone w [module pola zakupu](add-buy-box.md) używanym w PDP Twojej witryny.</span><span class="sxs-lookup"><span data-stu-id="146b1-151">If a digital gift card is configured to allow for a custom amount, this behavior must also be enabled in the [buy box module](add-buy-box.md) that is used on your site's PDPs.</span></span> <span data-ttu-id="146b1-152">Moduł pola zakupu obsługuje konfigurację modułu, która pozwala na kwoty niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="146b1-152">The buy box module supports module configuration to allow for custom amounts.</span></span> <span data-ttu-id="146b1-153">Możesz także zdefiniować minimalne i maksymalne kwoty, które są dozwolone dla kwot niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="146b1-153">You can also define the minimum and maximum amounts that are allowed for custom amounts.</span></span>

<span data-ttu-id="146b1-154">Aby skonfigurować niestandardową kwotę dla cyfrowej karty upominkowej w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="146b1-154">To configure a custom amount for a digital gift card in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="146b1-155">Przejdź do modułu pola zakupu, który jest używany w PDP Twojej witryny.</span><span class="sxs-lookup"><span data-stu-id="146b1-155">Go to the buy box module that is used on your site's PDPs.</span></span> <span data-ttu-id="146b1-156">Ten moduł pola zakupu może być zaimplementowany we fragmencie, w szablonie lub na stronie.</span><span class="sxs-lookup"><span data-stu-id="146b1-156">This buy box module might be implemented in a fragment, in a template, or on a page.</span></span>
1. <span data-ttu-id="146b1-157">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="146b1-157">Select **Edit**.</span></span>
1. <span data-ttu-id="146b1-158">W okienku właściwości po prawej stronie zaznacz pole wyboru **Zezwalaj na cenę niestandardową**.</span><span class="sxs-lookup"><span data-stu-id="146b1-158">In the properties pane on the right, select the **Allow custom price** check box.</span></span>
1. <span data-ttu-id="146b1-159">Opcjonalnie: Aby zdefiniować kwoty minimalne i maksymalne dla kwot niestandardowych, wprowadź kwoty w polach **Cena minimalna** i **Cena maksymalna**.</span><span class="sxs-lookup"><span data-stu-id="146b1-159">Optional: To define minimum and maximum amounts for custom amounts, enter amounts under **Minimum price** and **Maximum price**.</span></span>
1. <span data-ttu-id="146b1-160">Wybierz **Zakończ edycję** i następnie wybierz **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="146b1-160">Select **Finish editing**, and then select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="146b1-161">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="146b1-161">Additional resources</span></span>

[<span data-ttu-id="146b1-162">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="146b1-162">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="146b1-163">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="146b1-163">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="146b1-164">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="146b1-164">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="146b1-165">Tworzenie nowego produktu w programie Commerce</span><span class="sxs-lookup"><span data-stu-id="146b1-165">Create a new product in Commerce</span></span>](create-new-product-commerce.md)

[<span data-ttu-id="146b1-166">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="146b1-166">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[<span data-ttu-id="146b1-167">Wymiary produktu</span><span class="sxs-lookup"><span data-stu-id="146b1-167">Product dimensions</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/pim/product-dimensions?toc=/dynamics365/retail/toc.json)

[<span data-ttu-id="146b1-168">Konfigurowanie profilu powiadomienia</span><span class="sxs-lookup"><span data-stu-id="146b1-168">Set up an email notification profile</span></span>](email-notification-profiles.md)

[<span data-ttu-id="146b1-169">Tworzenie profilu funkcji online</span><span class="sxs-lookup"><span data-stu-id="146b1-169">Create an online functionality profile</span></span>](online-functionality-profile.md)

[<span data-ttu-id="146b1-170">Obsługa zewnętrznych kart upominkowych</span><span class="sxs-lookup"><span data-stu-id="146b1-170">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]