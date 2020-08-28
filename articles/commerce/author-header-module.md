---
title: Moduł nagłówka
description: W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e7dde3ba1ad375b309ae66cc6d31ccad85615e45
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686629"
---
# <a name="header-module"></a><span data-ttu-id="46bef-103">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="46bef-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="46bef-104">W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="46bef-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="46bef-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="46bef-105">Overview</span></span>

<span data-ttu-id="46bef-106">W Dynamics 365 Commerce nagłówek strony składa się z wielu modułów, takich jak nagłówek, menu nawigacji, wyszukiwanie, transparent i pole zgody na pliki cookie.</span><span class="sxs-lookup"><span data-stu-id="46bef-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="46bef-107">Moduł nagłówka zawiera logo witryny, łącza do hierarchii nawigacji, łącza do innych stron w witrynie, symbol koszyka, symbol Wishlist, opcje logowania i pasek wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="46bef-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="46bef-108">Moduł nagłówka jest automatycznie optymalizowany dla urządzenia, na którym jest oglądana witryna (czyli inaczej urządzenie stacjonarne lub urządzenie przenośne).</span><span class="sxs-lookup"><span data-stu-id="46bef-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="46bef-109">Na przykład na urządzeniu przenośnym pasek nawigacji jest zwinięty do przycisku **Menu** (który jest czasami nazywany *menu hamburgerowym*).</span><span class="sxs-lookup"><span data-stu-id="46bef-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="46bef-110">Poniższy obraz pokazuje przykład modułu nagłówka na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="46bef-110">The following image shows an example of a header module on a home page.</span></span>

![Przykład modułu nagłówka](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="46bef-112">Moduł właściwości nagłówka</span><span class="sxs-lookup"><span data-stu-id="46bef-112">Properties of a header module</span></span>

<span data-ttu-id="46bef-113">Moduł nagłówka obsługuje **Logo**, **Łącze logo** i właściwości **Łącza do Moje konto**.</span><span class="sxs-lookup"><span data-stu-id="46bef-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="46bef-114">Właściwości **Logo** i **Łącze logo** są używane do definiowania logo na stronie.</span><span class="sxs-lookup"><span data-stu-id="46bef-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="46bef-115">Aby uzyskać więcej informacji, zobacz [Dodawanie logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="46bef-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="46bef-116">Za pomocą **Łącza do Moje konto** można zdefiniować strony kont, które właściciel witryny chce wyświetlić szybkie łącza w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="46bef-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="46bef-117">Moduły dostępne w module nagłówka</span><span class="sxs-lookup"><span data-stu-id="46bef-117">Modules that are available in a header module</span></span>

<span data-ttu-id="46bef-118">W module nagłówka mogą być używane następujące moduły:</span><span class="sxs-lookup"><span data-stu-id="46bef-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="46bef-119">**Menu nawigacji** — menu nawigacji reprezentuje hierarchię nawigacji kanału i inne statyczne łącza nawigacji.</span><span class="sxs-lookup"><span data-stu-id="46bef-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="46bef-120">Hierarchię nawigacji kanału można skonfigurować w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="46bef-120">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="46bef-121">Menu nawigacji zawiera właściwość **Źródło nawigacji**, która służy do określania elementów menu nawigacji serwera sieci sprzedaży i statycznych elementów menu jako źródła.</span><span class="sxs-lookup"><span data-stu-id="46bef-121">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="46bef-122">Jeśli statyczne elementy menu są określone jako źródło, można podać łącza względne do innych stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="46bef-122">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="46bef-123">Skonfigurowane elementy zostaną wyświetlone jako nawigacja w nagłówkach.</span><span class="sxs-lookup"><span data-stu-id="46bef-123">Configured items then appear as header navigation.</span></span> 

- <span data-ttu-id="46bef-124">**Pasek wyszukiwania** — moduł wyszukiwania umożliwia użytkownikom wprowadzanie kryteriów wyszukiwania, co pozwala na wyszukiwanie produktów.</span><span class="sxs-lookup"><span data-stu-id="46bef-124">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="46bef-125">Adres URL domyślnej strony wyszukiwania oraz parametry kwerendy wyszukiwania muszą być podane w **Ustawienia witryny \> Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="46bef-125">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="46bef-126">Moduł wyszukiwania ma właściwości pozwalające pominąć przycisk Wyszukaj lub etykieta w razie konieczności.</span><span class="sxs-lookup"><span data-stu-id="46bef-126">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="46bef-127">Moduł wyszukiwania obsługuje także opcje automatycznego sugerowania, takie jak produkt, słowo kluczowe i wyniki wyszukiwania kategorii.</span><span class="sxs-lookup"><span data-stu-id="46bef-127">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="46bef-128">**Ikona koszyka** — moduł ikony koszyka reprezentuje ikonę koszyka, w której w danym momencie jest wyświetlana liczba pozycji w koszyku.</span><span class="sxs-lookup"><span data-stu-id="46bef-128">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="46bef-129">Aby uzyskać więcej informacji, zajrzyj do [Moduł ikony koszyka](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="46bef-129">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="46bef-130">Utwórz moduł nagłówka dla strony</span><span class="sxs-lookup"><span data-stu-id="46bef-130">Create a header module for a page</span></span>

<span data-ttu-id="46bef-131">Aby utworzyć moduł nagłówka, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="46bef-131">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="46bef-132">Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.</span><span class="sxs-lookup"><span data-stu-id="46bef-132">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="46bef-133">W oknie dialogowym **Nowy fragment strony** wybierz moduł **Kontener**, wprowadź nazwę dla fragmentu strony, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="46bef-133">In the **New page fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="46bef-134">Wybierz gniazdo **Domyślny kontener**, a następnie w okienku właściwości po prawej stronie określ właściwość **Szerokość** na **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="46bef-134">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="46bef-135">W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="46bef-135">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46bef-136">W oknie dialogowym **Dodawanie modułu** wybierz moduły **Baner promocyjny** i **Zgoda na pliki cookie** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="46bef-136">In the **Add Module** dialog box, select the **Promo banner** and **Cookie consent** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="46bef-137">W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="46bef-137">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46bef-138">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="46bef-138">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="46bef-139">Wybierz gniazdo **Kontener**, a następnie w okienku właściwości po prawej stronie określ właściwość **Szerokość** na **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="46bef-139">Select the **Container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="46bef-140">W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="46bef-140">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46bef-141">W oknie dialogowym **Dodaj moduł** wybierz moduł **Nagłówek** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="46bef-141">In the **Add Module** dialog box, select the **Header** module, and then select **OK**.</span></span>
1. <span data-ttu-id="46bef-142">W gnieździe **Menu nawigacji** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="46bef-142">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46bef-143">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Menu nawigacji** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="46bef-143">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="46bef-144">W okienku właściwości modułu menu nawigacji skonfiguruj właściwości wedle potrzeby.</span><span class="sxs-lookup"><span data-stu-id="46bef-144">In the property pane for the navigation menu module, configure the properties as needed.</span></span>
1. <span data-ttu-id="46bef-145">W gnieździe **Wyszukiwanie** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="46bef-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46bef-146">W oknie dialogowym **Dodaj moduł** wybierz moduł **Wyszukiwanie** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="46bef-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="46bef-147">W okienku właściwości modułu wyszukiwania skonfiguruj właściwości wedle potrzeby.</span><span class="sxs-lookup"><span data-stu-id="46bef-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="46bef-148">W gnieździe **Ikona koszyka** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="46bef-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46bef-149">W oknie dialogowym **Dodaj moduł** wybierz moduł **Ikona koszyka** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="46bef-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="46bef-150">W okienku właściwości modułu ikony koszyka skonfiguruj właściwości wedle potrzeby.</span><span class="sxs-lookup"><span data-stu-id="46bef-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="46bef-151">Jeśli ikona koszyka ma wyświetlać podsumowanie koszyka (zwanego również „koszykiem mini”), zaznaczając opcję **Wyświetlanie koszyka mini**.</span><span class="sxs-lookup"><span data-stu-id="46bef-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="46bef-152">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="46bef-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="46bef-153">Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.</span><span class="sxs-lookup"><span data-stu-id="46bef-153">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="46bef-154">W gnieździe **Nagłówek** w module **Strona domyślna** dodaj fragment stopki, który został utworzony.</span><span class="sxs-lookup"><span data-stu-id="46bef-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="46bef-155">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="46bef-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46bef-156">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="46bef-156">Additional resources</span></span>

[<span data-ttu-id="46bef-157">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="46bef-157">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="46bef-158">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="46bef-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="46bef-159">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="46bef-159">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="46bef-160">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="46bef-160">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="46bef-161">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="46bef-161">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="46bef-162">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="46bef-162">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="46bef-163">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="46bef-163">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="46bef-164">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="46bef-164">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="46bef-165">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="46bef-165">Footer module</span></span>](author-footer-module.md)
