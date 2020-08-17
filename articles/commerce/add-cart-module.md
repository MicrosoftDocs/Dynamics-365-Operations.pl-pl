---
title: Moduł koszyka
description: W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: f21268ed4cffed1d5c789f722796cdf05e965819
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621043"
---
# <a name="cart-module"></a><span data-ttu-id="b83f1-103">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="b83f1-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b83f1-104">W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b83f1-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b83f1-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="b83f1-105">Overview</span></span>

<span data-ttu-id="b83f1-106">Moduł koszyka wyświetla towary, które zostały dodane do koszyka, zanim odbiorca przejdzie do procesu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="b83f1-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="b83f1-107">Ten moduł pokazuje również podsumowanie zamówień i pozwala odbiorcy na zastosowanie lub usunięcie kodów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="b83f1-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="b83f1-108">Moduł koszyk obsługuje wykonanie transakcji zalogowanych uzytkowników i gości.</span><span class="sxs-lookup"><span data-stu-id="b83f1-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="b83f1-109">Ponadto obsługuje łącze **Powrót do zakupów**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="b83f1-110">Można skonfigurować marszrutę dla tego łącza w **Ustawienia witryny \> Rozszerzenia \> Marszruty**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="b83f1-111">Moduł koszyka służy do renderowania danych na podstawie identyfikatora koszyka, który jest plikiem cookie przeglądarki dostępnym w witrynie.</span><span class="sxs-lookup"><span data-stu-id="b83f1-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="b83f1-112">Poniższy obraz przedstawia przykład strony koszyka w witrynie Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="b83f1-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Przykład modułu koszyka](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="b83f1-114">Właściwości modułu koszyka i gniazda</span><span class="sxs-lookup"><span data-stu-id="b83f1-114">Cart module properties and slots</span></span>

<span data-ttu-id="b83f1-115">Moduł koszyka ma właściwość **Nagłówka**, która może być ustawiona na wartości takie jak **Torba na zakupy** i **Elementy w koszyku**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="b83f1-116">Moduły, których można używać w module koszyka</span><span class="sxs-lookup"><span data-stu-id="b83f1-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="b83f1-117">**Blok zawartości zaawansowanej** — ten moduł obsługuje obsługę komunikacji niestandardowej w module koszyka.</span><span class="sxs-lookup"><span data-stu-id="b83f1-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="b83f1-118">Komunikaty są prowadzone przez system zarządzania zawartością (CMS).</span><span class="sxs-lookup"><span data-stu-id="b83f1-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="b83f1-119">Można dodać dowolny komunikat, na przykład „w przypadku problemów z zamówieniem, skontaktuj się z firmą 1-800-Fabrikam”.</span><span class="sxs-lookup"><span data-stu-id="b83f1-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="b83f1-120">**Wybór sklepu** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania.</span><span class="sxs-lookup"><span data-stu-id="b83f1-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="b83f1-121">Umożliwia użytkownikom wprowadzenie lokalizacji, w której znajdują się bliskie sklepy.</span><span class="sxs-lookup"><span data-stu-id="b83f1-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="b83f1-122">Aby uzyskać więcej informacji na temat tego modułu, należy zapoznać się z tematem [moduł selector sklepów](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="b83f1-122">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="b83f1-123">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="b83f1-123">Module properties</span></span>

<span data-ttu-id="b83f1-124">Następujące ustawienia modułu koszyka mogą być skonfigurowane w **Ustawienia witryny \> Rozszerzenia**:</span><span class="sxs-lookup"><span data-stu-id="b83f1-124">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="b83f1-125">**Ilość maksymalna** — To ustawienie jest używane do określania maksymalnej liczby każdej pozycji, którą można dodać do koszyka.</span><span class="sxs-lookup"><span data-stu-id="b83f1-125">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="b83f1-126">Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.</span><span class="sxs-lookup"><span data-stu-id="b83f1-126">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="b83f1-127">**Zapasy** — Aby uzyskać informacje dotyczące sposobu stosowania ustawień zapasów, należy zapoznać się z tematem [stosowanie ustawień zapasów](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b83f1-127">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="b83f1-128">**Powrót do zakupów** — ta właściwość służy do określania trasy dla łącza **Powrót do zakupów**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-128">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="b83f1-129">Marszrutę można skonfigurować na poziomie witryny, umożliwiając detalistom przejęcie odbiorcy z powrotem na stronę główną lub na inną stronę w witrynie.</span><span class="sxs-lookup"><span data-stu-id="b83f1-129">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="b83f1-130">Interakcja Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="b83f1-130">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="b83f1-131">Moduł koszyka pobiera informacje o produktach za pomocą interfejsów API Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="b83f1-131">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="b83f1-132">Identyfikator koszyka z pliku cookie przeglądarki jest używany do pobierania wszystkich informacji o produktach z Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="b83f1-132">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="b83f1-133">Dodawanie modułu koszyka do strony</span><span class="sxs-lookup"><span data-stu-id="b83f1-133">Add a cart module to a page</span></span>

<span data-ttu-id="b83f1-134">Aby dodać moduł koszyka do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b83f1-134">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b83f1-135">Przejdź do **Fragmenty strony**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.</span><span class="sxs-lookup"><span data-stu-id="b83f1-135">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="b83f1-136">W oknie dialogowym **Nowy fragment strony** wybierz moduł **Koszyk**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-136">In the **New Page Fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="b83f1-137">W obszarze **Nazwa fragmentu strony** wprowadź nazwę **Fragment koszyka**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-137">Under **Page Fragment Name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="b83f1-138">Wybierz gniazdo **Koszyk**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-138">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="b83f1-139">W okienku właściwości po prawej stronie wybierz symbol ołówka, wprowadź tekst nagłówka w polu, a następnie zaznacz symbol znacznika wyboru.</span><span class="sxs-lookup"><span data-stu-id="b83f1-139">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="b83f1-140">W gnieździe **Koszyk** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-140">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b83f1-141">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Selektor sklepu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-141">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b83f1-142">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="b83f1-142">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="b83f1-143">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="b83f1-143">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="b83f1-144">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wpisz nazwę szablonu.</span><span class="sxs-lookup"><span data-stu-id="b83f1-144">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="b83f1-145">W drzewie konspektu wybierz **Treść**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-145">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="b83f1-146">W oknie dialogowym **Wybierz fragment strony** wybierz **Fragment koszyka**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-146">In the **Select Page Fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="b83f1-147">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="b83f1-147">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="b83f1-148">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.</span><span class="sxs-lookup"><span data-stu-id="b83f1-148">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="b83f1-149">W oknie dialogowym **Wybierz szablon** wybierz utworzony szablon, wprowadź nazwę strony, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b83f1-149">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="b83f1-150">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="b83f1-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="b83f1-151">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="b83f1-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b83f1-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b83f1-152">Additional resources</span></span>

[<span data-ttu-id="b83f1-153">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="b83f1-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b83f1-154">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="b83f1-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="b83f1-155">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="b83f1-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="b83f1-156">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="b83f1-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="b83f1-157">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="b83f1-157">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="b83f1-158">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="b83f1-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="b83f1-159">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="b83f1-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="b83f1-160">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="b83f1-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="b83f1-161">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="b83f1-161">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="b83f1-162">Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="b83f1-162">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
