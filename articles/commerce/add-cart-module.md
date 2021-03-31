---
title: Moduł koszyka
description: W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5b0ce69f57e6ba691803752280466b41ced7c521
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206494"
---
# <a name="cart-module"></a><span data-ttu-id="4b1bd-103">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="4b1bd-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4b1bd-104">W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4b1bd-105">Moduł koszyka wyświetla towary, które zostały dodane do koszyka, zanim odbiorca przejdzie do procesu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-105">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="4b1bd-106">Ten moduł pokazuje również podsumowanie zamówień i pozwala odbiorcy na zastosowanie lub usunięcie kodów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-106">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="4b1bd-107">Moduł koszyk obsługuje wykonanie transakcji zalogowanych uzytkowników i gości.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-107">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="4b1bd-108">Ponadto obsługuje łącze **Powrót do zakupów**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-108">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="4b1bd-109">Można skonfigurować marszrutę dla tego łącza w **Ustawienia witryny \> Rozszerzenia \> Marszruty**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-109">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="4b1bd-110">Moduł koszyka służy do renderowania danych na podstawie identyfikatora koszyka, który jest plikiem cookie przeglądarki dostępnym w witrynie.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-110">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="4b1bd-111">Poniższy obraz przedstawia przykład strony koszyka w witrynie Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-111">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Przykład modułu koszyka w witrynie Fabrikam](./media/cart2.PNG)

<span data-ttu-id="4b1bd-113">Poniższy obraz przedstawia przykład strony koszyka w witrynie Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-113">The following image shows an example of a cart page on the Fabrikam site.</span></span> <span data-ttu-id="4b1bd-114">W tym przykładzie istnieje opłata manipulacyjna dla pozycji w wierszu.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-114">In this example, there is a handling fee for a line item.</span></span>

![Przykład modułu koszyka z opłatą manipulacyjną dla pozycji w wierszu](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="4b1bd-116">Właściwości modułu koszyka i gniazda</span><span class="sxs-lookup"><span data-stu-id="4b1bd-116">Cart module properties and slots</span></span>

| <span data-ttu-id="4b1bd-117">Właściwość</span><span class="sxs-lookup"><span data-stu-id="4b1bd-117">Property</span></span> | <span data-ttu-id="4b1bd-118">Wartości</span><span class="sxs-lookup"><span data-stu-id="4b1bd-118">Values</span></span> | <span data-ttu-id="4b1bd-119">opis</span><span class="sxs-lookup"><span data-stu-id="4b1bd-119">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="4b1bd-120">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="4b1bd-120">Heading</span></span> | <span data-ttu-id="4b1bd-121">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="4b1bd-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="4b1bd-122">Nagłówek koszyka, na przykład „Torba na zakupy” lub „Produkty w Twoim koszyku”.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-122">A heading for the cart, such as "Shopping bag" or "Items in your cart."</span></span> |
| <span data-ttu-id="4b1bd-123">Pokaż błędy niedostępnych w magazynie</span><span class="sxs-lookup"><span data-stu-id="4b1bd-123">Show out of stock errors</span></span> | <span data-ttu-id="4b1bd-124">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="4b1bd-124">**True** or **False**</span></span> | <span data-ttu-id="4b1bd-125">Jeśli ta właściwość ma wartość **Prawda**, na stronie kozyka będą widoczne błędy dotyczące zapasów.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-125">If this property is set to **True**, the cart page will show stock-related errors.</span></span> <span data-ttu-id="4b1bd-126">Zaleca się ustawienie tej właściwości na **Prawda**, jeśli sprawdzanie zapasów jest wykonywane w odniesieniu do danego oddziału.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-126">We recommend that you set this property to **True** if inventory checks are applied on the site.</span></span> |
| <span data-ttu-id="4b1bd-127">Pokaż opłaty transportowe dla pozycji w wierszu</span><span class="sxs-lookup"><span data-stu-id="4b1bd-127">Show shipping charges for line items</span></span> | <span data-ttu-id="4b1bd-128">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="4b1bd-128">**True** or **False**</span></span> | <span data-ttu-id="4b1bd-129">Jeśli ta właściwość ma wartość **Prawda**, pozycje w wierszu koszyka będą pokazywały opłaty transportowe, jeśli te informacje są dostępne.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-129">If this property is set to **True**, cart line items will show the shipping charges, if this information is available.</span></span> <span data-ttu-id="4b1bd-130">Ta funkcja nie jest obsługiwana w motywie Fabrikam, ponieważ użytkownicy wybierają tylko wysyłkę w ramach przepływu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-130">This feature isn't supported in the Fabrikam theme, because users select shipping only in the checkout flow.</span></span> <span data-ttu-id="4b1bd-131">Tę funkcję można jednak włączyć w innych przepływach pracy, jeśli ma ona zastosowania.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-131">However, this feature can be turned on in other workflows if it's applicable.</span></span> |
| <span data-ttu-id="4b1bd-132">Wyświetl dostępne promocje</span><span class="sxs-lookup"><span data-stu-id="4b1bd-132">Show available promotions</span></span>| <span data-ttu-id="4b1bd-133">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="4b1bd-133">**True** or **False**</span></span> | <span data-ttu-id="4b1bd-134">Jeśli właściwość ma wartość **Prawda**, w koszyku są pokazuje dostępne promocje oparte na pozycjach w koszyku.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-134">If this property is set to **True**, the cart shows available promotions, based on items in the cart.</span></span> <span data-ttu-id="4b1bd-135">Ta funkcja nie jest dostępna tylko w Dynamics 365 Commerce w wersji 10.0.16.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-135">This capability is available in the Dynamics 365 Commerce 10.0.16 release.</span></span> |

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="4b1bd-136">Moduły, których można używać w module koszyka</span><span class="sxs-lookup"><span data-stu-id="4b1bd-136">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="4b1bd-137">**Blok zawartości zaawansowanej** — ten moduł obsługuje obsługę komunikacji niestandardowej w module koszyka.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-137">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="4b1bd-138">Komunikaty są prowadzone przez system zarządzania zawartością (CMS).</span><span class="sxs-lookup"><span data-stu-id="4b1bd-138">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="4b1bd-139">Można dodać dowolny komunikat, na przykład „w przypadku problemów z zamówieniem, skontaktuj się z firmą 1-800-Fabrikam”.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-139">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="4b1bd-140">**Wybór sklepu** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-140">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="4b1bd-141">Umożliwia użytkownikom wprowadzenie lokalizacji, w której znajdują się bliskie sklepy.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-141">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="4b1bd-142">Aby uzyskać więcej informacji na temat tego modułu, należy zapoznać się z tematem [moduł selector sklepów](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="4b1bd-142">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="4b1bd-143">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="4b1bd-143">Module properties</span></span>

<span data-ttu-id="4b1bd-144">Następujące ustawienia modułu koszyka mogą być skonfigurowane w **Ustawienia witryny \> Rozszerzenia**:</span><span class="sxs-lookup"><span data-stu-id="4b1bd-144">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="4b1bd-145">**Ilość maksymalna** — To ustawienie jest używane do określania maksymalnej liczby każdej pozycji, którą można dodać do koszyka.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-145">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="4b1bd-146">Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-146">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="4b1bd-147">**Zapasy** — Aby uzyskać informacje dotyczące sposobu stosowania ustawień zapasów, należy zapoznać się z tematem [stosowanie ustawień zapasów](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4b1bd-147">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="4b1bd-148">**Powrót do zakupów** — ta właściwość służy do określania trasy dla łącza **Powrót do zakupów**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-148">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="4b1bd-149">Marszrutę można skonfigurować na poziomie witryny, umożliwiając detalistom przejęcie odbiorcy z powrotem na stronę główną lub na inną stronę w witrynie.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-149">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b1bd-150">W Dynamics 365 Commerce w wersji 10.0.14 i nowszych towary w koszyku są agregowane na podstawie ustawień zdefiniowanych w profilu funkcji online sklepu internetowego w module Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-150">In the Dynamics 365 Commerce 10.0.14 release and later, items in the cart are aggregated based on the settings that are defined in the online functionality profile for the online store in Commerce headquarters.</span></span> <span data-ttu-id="4b1bd-151">Aby uzyskać więcej informacji na temat tworzenia profilu funkcji online i ustawiania właściwości wymaganych do agregacji, należy zapoznać się z tematem [Tworzenie profilu funkcji online](online-functionality-profile.md).</span><span class="sxs-lookup"><span data-stu-id="4b1bd-151">For more information about how to create an online functionality profile and set the properties that are required for aggregation, see [Create an online functionality profile](online-functionality-profile.md).</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="4b1bd-152">Interakcja Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="4b1bd-152">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="4b1bd-153">Moduł koszyka pobiera informacje o produktach za pomocą interfejsów API Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-153">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="4b1bd-154">Identyfikator koszyka z pliku cookie przeglądarki jest używany do pobierania wszystkich informacji o produktach z Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-154">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="4b1bd-155">Dodawanie modułu koszyka do strony</span><span class="sxs-lookup"><span data-stu-id="4b1bd-155">Add a cart module to a page</span></span>

<span data-ttu-id="4b1bd-156">Aby dodać moduł koszyka do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-156">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="4b1bd-157">Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-157">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="4b1bd-158">W oknie dialogowym **Nowy fragment** wybierz moduł **Koszyk**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-158">In the **New fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="4b1bd-159">W obszarze **Nazwa fragmentu** wprowadź nazwę **Fragment koszyka**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-159">Under **Fragment name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="4b1bd-160">Wybierz gniazdo **Koszyk**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-160">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="4b1bd-161">W okienku właściwości po prawej stronie wybierz symbol ołówka, wprowadź tekst nagłówka w polu, a następnie zaznacz symbol znacznika wyboru.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-161">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="4b1bd-162">W gnieździe **Koszyk** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-162">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4b1bd-163">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Selektor sklepu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-163">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4b1bd-164">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-164">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="4b1bd-165">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-165">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="4b1bd-166">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wpisz nazwę szablonu.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-166">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="4b1bd-167">W drzewie konspektu wybierz **Treść**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-167">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="4b1bd-168">W oknie dialogowym **Wybierz fragment** wybierz **Fragment koszyka**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-168">In the **Select fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="4b1bd-169">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-169">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="4b1bd-170">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-170">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="4b1bd-171">W oknie dialogowym **Wybierz szablon** wybierz utworzony szablon, wprowadź nazwę strony, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-171">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="4b1bd-172">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-172">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="4b1bd-173">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="4b1bd-173">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b1bd-174">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4b1bd-174">Additional resources</span></span>

[<span data-ttu-id="4b1bd-175">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="4b1bd-175">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="4b1bd-176">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="4b1bd-176">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="4b1bd-177">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="4b1bd-177">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="4b1bd-178">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="4b1bd-178">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="4b1bd-179">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="4b1bd-179">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="4b1bd-180">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="4b1bd-180">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="4b1bd-181">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="4b1bd-181">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="4b1bd-182">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="4b1bd-182">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="4b1bd-183">Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="4b1bd-183">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)

[<span data-ttu-id="4b1bd-184">Tworzenie profilu funkcji online</span><span class="sxs-lookup"><span data-stu-id="4b1bd-184">Create an online functionality profile</span></span>](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]