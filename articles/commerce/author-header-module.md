---
title: Moduł nagłówka
description: W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 569fb5ac3d30be30044ef9b928ecf1f6dde20aab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211431"
---
# <a name="header-module"></a><span data-ttu-id="62a58-103">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="62a58-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="62a58-104">W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="62a58-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="62a58-105">W systemie Dynamics 365 Commerce nagłówek strony jest konfigurowany jako fragment strony, który zawiera moduły nagłówek, banner promocyjny i zgoda na wykorzystanie pliku cookie.</span><span class="sxs-lookup"><span data-stu-id="62a58-105">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="62a58-106">Moduł nagłówka zawiera logo witryny, łącza do hierarchii nawigacji, łącza do innych stron w witrynie, ikonę koszyka, symbol Wishlist, opcje logowania i pasek wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="62a58-106">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="62a58-107">Moduł nagłówka jest automatycznie optymalizowany dla urządzenia, na którym jest oglądana witryna (czyli inaczej urządzenie stacjonarne lub urządzenie przenośne).</span><span class="sxs-lookup"><span data-stu-id="62a58-107">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="62a58-108">Na przykład na urządzeniu przenośnym pasek nawigacji jest zwinięty do przycisku **Menu** (który jest czasami nazywany *menu hamburgerowym*).</span><span class="sxs-lookup"><span data-stu-id="62a58-108">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="62a58-109">Poniższy obraz pokazuje przykład modułu nagłówka na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="62a58-109">The following image shows an example of a header module on a home page.</span></span>

![Przykład modułu nagłówka](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="62a58-111">Moduł właściwości nagłówka</span><span class="sxs-lookup"><span data-stu-id="62a58-111">Properties of a header module</span></span>

<span data-ttu-id="62a58-112">Moduł nagłówka obsługuje **Logo**, **Łącze logo** i właściwości **Łącza do Moje konto**.</span><span class="sxs-lookup"><span data-stu-id="62a58-112">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="62a58-113">Właściwości **Logo** i **Łącze logo** są używane do definiowania logo na stronie.</span><span class="sxs-lookup"><span data-stu-id="62a58-113">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="62a58-114">Aby uzyskać więcej informacji, zobacz [Dodawanie logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="62a58-114">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="62a58-115">Za pomocą **Łącza do Moje konto** można zdefiniować strony kont, które właściciel witryny chce wyświetlić szybkie łącza w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="62a58-115">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="62a58-116">Moduły dostępne w module nagłówka</span><span class="sxs-lookup"><span data-stu-id="62a58-116">Modules that are available within a header module</span></span>

<span data-ttu-id="62a58-117">W module nagłówka mogą być używane następujące moduły:</span><span class="sxs-lookup"><span data-stu-id="62a58-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="62a58-118">**Menu nawigacji** — menu nawigacji reprezentuje hierarchię nawigacji kanału i inne statyczne łącza nawigacji.</span><span class="sxs-lookup"><span data-stu-id="62a58-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="62a58-119">Aby uzyskać więcej informacji, zobacz [Nawigacja modułu menu](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="62a58-119">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="62a58-120">**Pasek wyszukiwania** — moduł wyszukiwania umożliwia użytkownikom wprowadzanie kryteriów wyszukiwania, co pozwala na wyszukiwanie produktów.</span><span class="sxs-lookup"><span data-stu-id="62a58-120">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="62a58-121">Adres URL domyślnej strony wyszukiwania oraz parametry kwerendy wyszukiwania muszą być podane w **Ustawienia witryny \> Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="62a58-121">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="62a58-122">Moduł wyszukiwania ma właściwości pozwalające pominąć przycisk Wyszukaj lub etykieta w razie konieczności.</span><span class="sxs-lookup"><span data-stu-id="62a58-122">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="62a58-123">Moduł wyszukiwania obsługuje także opcje automatycznego sugerowania, takie jak produkt, słowo kluczowe i wyniki wyszukiwania kategorii.</span><span class="sxs-lookup"><span data-stu-id="62a58-123">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="62a58-124">**Ikona koszyka** — moduł ikony koszyka reprezentuje ikonę koszyka, w której w danym momencie jest wyświetlana liczba pozycji w koszyku.</span><span class="sxs-lookup"><span data-stu-id="62a58-124">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="62a58-125">Aby uzyskać więcej informacji, zajrzyj do [Moduł ikony koszyka](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="62a58-125">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

- <span data-ttu-id="62a58-126">**Wybór witryn** — moduł wyboru witryny umożliwia przeglądanie przez użytkowników różnych wstępnie zdefiniowanych witryn na podstawie rynku, regionów i ustawień regionalnych.</span><span class="sxs-lookup"><span data-stu-id="62a58-126">**Site selector** - The site selector module lets users browse across different predefined sites, based on market, regions, and locales.</span></span> <span data-ttu-id="62a58-127">Aby uzyskać więcej informacji, zajrzyj do [Moduł wyboru witryn](site-selector.md).</span><span class="sxs-lookup"><span data-stu-id="62a58-127">For more information, see [Site selector module](site-selector.md).</span></span>

- <span data-ttu-id="62a58-128">**Wybór sklepów** — moduł wyboru sklepu może być uwzględniony w gnieździe wyboru sklepu w module nagłówka.</span><span class="sxs-lookup"><span data-stu-id="62a58-128">**Store selector** - The store selector module can be included in a header module's store selector slot.</span></span> <span data-ttu-id="62a58-129">Umożliwia on przeglądanie i znajdowanie pobliskich sklepów.</span><span class="sxs-lookup"><span data-stu-id="62a58-129">It lets users browse and find nearby stores.</span></span> <span data-ttu-id="62a58-130">Użytkownicy mogą również określić preferowany sklep.</span><span class="sxs-lookup"><span data-stu-id="62a58-130">Users can also specify a preferred store.</span></span> <span data-ttu-id="62a58-131">Ten sklep zostanie następnie wyświetlony w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="62a58-131">That store will then be shown in the header.</span></span> <span data-ttu-id="62a58-132">Gdy moduł Selector magazynu jest uwzględniony w module nagłówka, jego właściwość **Tryb** musi mieć ustawioną wartość **Znajdź sklepy**.</span><span class="sxs-lookup"><span data-stu-id="62a58-132">When the store selector module is included in the header module, its **Mode** property must be set to **Find stores**.</span></span> <span data-ttu-id="62a58-133">Aby uzyskać więcej informacji, zajrzyj do [Moduł wyboru sklepów](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="62a58-133">For more information, see [Store selector module](store-selector.md).</span></span>

> [!NOTE]
> - <span data-ttu-id="62a58-134">Obsługa korzystania z modułu ikon koszyka w modułach nagłówków jest dostępna w Dynamics 365 Commerce w wydaniu 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="62a58-134">Support for using the cart icon module in header modules is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>
> - <span data-ttu-id="62a58-135">Obsługa korzystania z modułu wyboru witryn w modułach nagłówków jest dostępna w Dynamics 365 Commerce w wydaniu 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="62a58-135">Support for using the site selector module in header modules is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>
> - <span data-ttu-id="62a58-136">Obsługa korzystania z modułu wyboru sklepu w modułach nagłówków jest dostępna w Dynamics 365 Commerce w wydaniu 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="62a58-136">Support for using the store selector module in header modules is available in the Dynamics 365 Commerce 10.0.15 release.</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="62a58-137">Utwórz fragment nagłówka dla strony</span><span class="sxs-lookup"><span data-stu-id="62a58-137">Create a header fragment for a page</span></span>

<span data-ttu-id="62a58-138">Aby utworzyć fragment nagłówka, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="62a58-138">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="62a58-139">Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.</span><span class="sxs-lookup"><span data-stu-id="62a58-139">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="62a58-140">W oknie dialogowym **Nowy fragment** wybierz moduł **Kontener**, wprowadź nazwę dla fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="62a58-140">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="62a58-141">Wybierz gniazdo **Domyślny kontener**, a następnie w okienku właściwości po prawej stronie określ właściwość **Szerokość** na **Wypełnij ekran**.</span><span class="sxs-lookup"><span data-stu-id="62a58-141">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="62a58-142">W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="62a58-142">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="62a58-143">W oknie dialogowym **Dodawanie modułu** wybierz moduły **Baner promocyjny**, **Nagłówek** i **Zgoda na pliki cookie** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="62a58-143">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="62a58-144">W okienku właściwości modułu **Banner promocyjny** wybierz opcję **Dodaj wiadomość**, a następnie wybierz opcję **Wiadomość**.</span><span class="sxs-lookup"><span data-stu-id="62a58-144">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="62a58-145">W oknie dialogowym **Wiadomość** dodaj tekst łącza oraz łącza do materiałów promocyjnych, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="62a58-145">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="62a58-146">W okienku właściwości modułu **Zgody na wykorzystanie plików cookie** dodaj i skonfiguruj tekst oraz łącze do strony opisującej politykę prywatności witryny.</span><span class="sxs-lookup"><span data-stu-id="62a58-146">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="62a58-147">W gnieździe **Menu nawigacji** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="62a58-147">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="62a58-148">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Menu nawigacji** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="62a58-148">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="62a58-149">W okienku właściwości modułu menu nawigacji, w obszarze **Źródło menu nawigacji** wybierz opcję **Retail Server**.</span><span class="sxs-lookup"><span data-stu-id="62a58-149">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="62a58-150">W okienku właściwości modułu menu nawigacji, w obszarze **Elementy menu statycznego** wybierz opcję **Dodaj element menu**, a następnie wybierz pozycję **Element menu**.</span><span class="sxs-lookup"><span data-stu-id="62a58-150">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="62a58-151">W oknie dialogowym **Elementu menu**, w obszarze **Tekst elementu menu** wprowadź wartość „kontakt”.</span><span class="sxs-lookup"><span data-stu-id="62a58-151">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="62a58-152">W oknie dialogowym **Element menu**, w obszarze **Cel łącza w elemencie menu** wybierz opcję **Dodaj łącze**.</span><span class="sxs-lookup"><span data-stu-id="62a58-152">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="62a58-153">W oknie dialogowym **Dodaj łącze** wybierz łącze do strony „Kontakt”, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="62a58-153">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="62a58-154">W oknie dialogowym **Element menu** wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="62a58-154">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="62a58-155">W gnieździe **Wyszukiwanie** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="62a58-155">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="62a58-156">W oknie dialogowym **Dodaj moduł** wybierz moduł **Wyszukiwanie** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="62a58-156">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="62a58-157">W okienku właściwości modułu wyszukiwania skonfiguruj właściwości wedle potrzeby.</span><span class="sxs-lookup"><span data-stu-id="62a58-157">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="62a58-158">W gnieździe **Ikona koszyka** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="62a58-158">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="62a58-159">W oknie dialogowym **Dodaj moduł** wybierz moduł **Ikona koszyka** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="62a58-159">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="62a58-160">W okienku właściwości modułu ikony koszyka skonfiguruj właściwości wedle potrzeby.</span><span class="sxs-lookup"><span data-stu-id="62a58-160">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="62a58-161">Jeśli ikona koszyka ma wyświetlać podsumowanie koszyka (zwanego również „koszykiem mini”), zaznaczając opcję **Wyświetlanie koszyka mini**.</span><span class="sxs-lookup"><span data-stu-id="62a58-161">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="62a58-162">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="62a58-162">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="62a58-163">Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.</span><span class="sxs-lookup"><span data-stu-id="62a58-163">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="62a58-164">W gnieździe **Nagłówek** w module **Strona domyślna** dodaj fragment stopki, który został utworzony.</span><span class="sxs-lookup"><span data-stu-id="62a58-164">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="62a58-165">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="62a58-165">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62a58-166">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="62a58-166">Additional resources</span></span>

[<span data-ttu-id="62a58-167">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="62a58-167">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="62a58-168">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="62a58-168">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="62a58-169">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="62a58-169">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="62a58-170">Moduł transparentu promocyjnego</span><span class="sxs-lookup"><span data-stu-id="62a58-170">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="62a58-171">Moduł Menu nawigacji</span><span class="sxs-lookup"><span data-stu-id="62a58-171">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="62a58-172">Zgoda na plik cookie</span><span class="sxs-lookup"><span data-stu-id="62a58-172">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="62a58-173">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="62a58-173">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="62a58-174">Moduł wyboru witryny</span><span class="sxs-lookup"><span data-stu-id="62a58-174">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="62a58-175">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="62a58-175">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]