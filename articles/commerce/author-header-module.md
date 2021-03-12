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
ms.openlocfilehash: 1373397c4499ed65835bcc71c6fc628ff356e4e7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991522"
---
# <a name="header-module"></a><span data-ttu-id="69583-103">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="69583-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="69583-104">W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="69583-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="69583-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="69583-105">Overview</span></span>

<span data-ttu-id="69583-106">W systemie Dynamics 365 Commerce nagłówek strony jest konfigurowany jako fragment strony, który zawiera moduły nagłówek, banner promocyjny i zgoda na wykorzystanie pliku cookie.</span><span class="sxs-lookup"><span data-stu-id="69583-106">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="69583-107">Moduł nagłówka zawiera logo witryny, łącza do hierarchii nawigacji, łącza do innych stron w witrynie, ikonę koszyka, symbol Wishlist, opcje logowania i pasek wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="69583-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="69583-108">Moduł nagłówka jest automatycznie optymalizowany dla urządzenia, na którym jest oglądana witryna (czyli inaczej urządzenie stacjonarne lub urządzenie przenośne).</span><span class="sxs-lookup"><span data-stu-id="69583-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="69583-109">Na przykład na urządzeniu przenośnym pasek nawigacji jest zwinięty do przycisku **Menu** (który jest czasami nazywany *menu hamburgerowym*).</span><span class="sxs-lookup"><span data-stu-id="69583-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="69583-110">Poniższy obraz pokazuje przykład modułu nagłówka na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="69583-110">The following image shows an example of a header module on a home page.</span></span>

![Przykład modułu nagłówka](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="69583-112">Moduł właściwości nagłówka</span><span class="sxs-lookup"><span data-stu-id="69583-112">Properties of a header module</span></span>

<span data-ttu-id="69583-113">Moduł nagłówka obsługuje **Logo**, **Łącze logo** i właściwości **Łącza do Moje konto**.</span><span class="sxs-lookup"><span data-stu-id="69583-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="69583-114">Właściwości **Logo** i **Łącze logo** są używane do definiowania logo na stronie.</span><span class="sxs-lookup"><span data-stu-id="69583-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="69583-115">Aby uzyskać więcej informacji, zobacz [Dodawanie logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="69583-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="69583-116">Za pomocą **Łącza do Moje konto** można zdefiniować strony kont, które właściciel witryny chce wyświetlić szybkie łącza w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="69583-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="69583-117">Moduły dostępne w module nagłówka</span><span class="sxs-lookup"><span data-stu-id="69583-117">Modules that are available within a header module</span></span>

<span data-ttu-id="69583-118">W module nagłówka mogą być używane następujące moduły:</span><span class="sxs-lookup"><span data-stu-id="69583-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="69583-119">**Menu nawigacji** — menu nawigacji reprezentuje hierarchię nawigacji kanału i inne statyczne łącza nawigacji.</span><span class="sxs-lookup"><span data-stu-id="69583-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="69583-120">Aby uzyskać więcej informacji, zobacz [Nawigacja modułu menu](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="69583-120">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="69583-121">**Pasek wyszukiwania** — moduł wyszukiwania umożliwia użytkownikom wprowadzanie kryteriów wyszukiwania, co pozwala na wyszukiwanie produktów.</span><span class="sxs-lookup"><span data-stu-id="69583-121">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="69583-122">Adres URL domyślnej strony wyszukiwania oraz parametry kwerendy wyszukiwania muszą być podane w **Ustawienia witryny \> Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="69583-122">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="69583-123">Moduł wyszukiwania ma właściwości pozwalające pominąć przycisk Wyszukaj lub etykieta w razie konieczności.</span><span class="sxs-lookup"><span data-stu-id="69583-123">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="69583-124">Moduł wyszukiwania obsługuje także opcje automatycznego sugerowania, takie jak produkt, słowo kluczowe i wyniki wyszukiwania kategorii.</span><span class="sxs-lookup"><span data-stu-id="69583-124">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="69583-125">**Ikona koszyka** — moduł ikony koszyka reprezentuje ikonę koszyka, w której w danym momencie jest wyświetlana liczba pozycji w koszyku.</span><span class="sxs-lookup"><span data-stu-id="69583-125">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="69583-126">Aby uzyskać więcej informacji, zajrzyj do [Moduł ikony koszyka](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="69583-126">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

- <span data-ttu-id="69583-127">**Wybór witryn** — moduł wyboru witryny umożliwia przeglądanie przez użytkowników różnych wstępnie zdefiniowanych witryn na podstawie rynku, regionów i ustawień regionalnych.</span><span class="sxs-lookup"><span data-stu-id="69583-127">**Site selector** - The site selector module lets users browse across different predefined sites, based on market, regions, and locales.</span></span> <span data-ttu-id="69583-128">Aby uzyskać więcej informacji, zajrzyj do [Moduł wyboru witryn](site-selector.md).</span><span class="sxs-lookup"><span data-stu-id="69583-128">For more information, see [Site selector module](site-selector.md).</span></span>

- <span data-ttu-id="69583-129">**Wybór sklepów** — moduł wyboru sklepu może być uwzględniony w gnieździe wyboru sklepu w module nagłówka.</span><span class="sxs-lookup"><span data-stu-id="69583-129">**Store selector** - The store selector module can be included in a header module's store selector slot.</span></span> <span data-ttu-id="69583-130">Umożliwia on przeglądanie i znajdowanie pobliskich sklepów.</span><span class="sxs-lookup"><span data-stu-id="69583-130">It lets users browse and find nearby stores.</span></span> <span data-ttu-id="69583-131">Użytkownicy mogą również określić preferowany sklep.</span><span class="sxs-lookup"><span data-stu-id="69583-131">Users can also specify a preferred store.</span></span> <span data-ttu-id="69583-132">Ten sklep zostanie następnie wyświetlony w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="69583-132">That store will then be shown in the header.</span></span> <span data-ttu-id="69583-133">Gdy moduł Selector magazynu jest uwzględniony w module nagłówka, jego właściwość **Tryb** musi mieć ustawioną wartość **Znajdź sklepy**.</span><span class="sxs-lookup"><span data-stu-id="69583-133">When the store selector module is included in the header module, its **Mode** property must be set to **Find stores**.</span></span> <span data-ttu-id="69583-134">Aby uzyskać więcej informacji, zajrzyj do [Moduł wyboru sklepów](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="69583-134">For more information, see [Store selector module](store-selector.md).</span></span>

> [!NOTE]
> - <span data-ttu-id="69583-135">Obsługa korzystania z modułu ikon koszyka w modułach nagłówków jest dostępna w Dynamics 365 Commerce w wydaniu 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="69583-135">Support for using the cart icon module in header modules is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>
> - <span data-ttu-id="69583-136">Obsługa korzystania z modułu wyboru witryn w modułach nagłówków jest dostępna w Dynamics 365 Commerce w wydaniu 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="69583-136">Support for using the site selector module in header modules is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>
> - <span data-ttu-id="69583-137">Obsługa korzystania z modułu wyboru sklepu w modułach nagłówków jest dostępna w Dynamics 365 Commerce w wydaniu 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="69583-137">Support for using the store selector module in header modules is available in the Dynamics 365 Commerce 10.0.15 release.</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="69583-138">Utwórz fragment nagłówka dla strony</span><span class="sxs-lookup"><span data-stu-id="69583-138">Create a header fragment for a page</span></span>

<span data-ttu-id="69583-139">Aby utworzyć fragment nagłówka, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="69583-139">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="69583-140">Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.</span><span class="sxs-lookup"><span data-stu-id="69583-140">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="69583-141">W oknie dialogowym **Nowy fragment** wybierz moduł **Kontener**, wprowadź nazwę dla fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="69583-141">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="69583-142">Wybierz gniazdo **Domyślny kontener**, a następnie w okienku właściwości po prawej stronie określ właściwość **Szerokość** na **Wypełnij ekran**.</span><span class="sxs-lookup"><span data-stu-id="69583-142">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="69583-143">W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="69583-143">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="69583-144">W oknie dialogowym **Dodawanie modułu** wybierz moduły **Baner promocyjny**, **Nagłówek** i **Zgoda na pliki cookie** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="69583-144">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="69583-145">W okienku właściwości modułu **Banner promocyjny** wybierz opcję **Dodaj wiadomość**, a następnie wybierz opcję **Wiadomość**.</span><span class="sxs-lookup"><span data-stu-id="69583-145">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="69583-146">W oknie dialogowym **Wiadomość** dodaj tekst łącza oraz łącza do materiałów promocyjnych, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="69583-146">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="69583-147">W okienku właściwości modułu **Zgody na wykorzystanie plików cookie** dodaj i skonfiguruj tekst oraz łącze do strony opisującej politykę prywatności witryny.</span><span class="sxs-lookup"><span data-stu-id="69583-147">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="69583-148">W gnieździe **Menu nawigacji** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="69583-148">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="69583-149">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Menu nawigacji** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="69583-149">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="69583-150">W okienku właściwości modułu menu nawigacji, w obszarze **Źródło menu nawigacji** wybierz opcję **Retail Server**.</span><span class="sxs-lookup"><span data-stu-id="69583-150">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="69583-151">W okienku właściwości modułu menu nawigacji, w obszarze **Elementy menu statycznego** wybierz opcję **Dodaj element menu**, a następnie wybierz pozycję **Element menu**.</span><span class="sxs-lookup"><span data-stu-id="69583-151">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="69583-152">W oknie dialogowym **Elementu menu**, w obszarze **Tekst elementu menu** wprowadź wartość „kontakt”.</span><span class="sxs-lookup"><span data-stu-id="69583-152">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="69583-153">W oknie dialogowym **Element menu**, w obszarze **Cel łącza w elemencie menu** wybierz opcję **Dodaj łącze**.</span><span class="sxs-lookup"><span data-stu-id="69583-153">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="69583-154">W oknie dialogowym **Dodaj łącze** wybierz łącze do strony „Kontakt”, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="69583-154">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="69583-155">W oknie dialogowym **Element menu** wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="69583-155">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="69583-156">W gnieździe **Wyszukiwanie** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="69583-156">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="69583-157">W oknie dialogowym **Dodaj moduł** wybierz moduł **Wyszukiwanie** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="69583-157">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="69583-158">W okienku właściwości modułu wyszukiwania skonfiguruj właściwości wedle potrzeby.</span><span class="sxs-lookup"><span data-stu-id="69583-158">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="69583-159">W gnieździe **Ikona koszyka** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="69583-159">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="69583-160">W oknie dialogowym **Dodaj moduł** wybierz moduł **Ikona koszyka** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="69583-160">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="69583-161">W okienku właściwości modułu ikony koszyka skonfiguruj właściwości wedle potrzeby.</span><span class="sxs-lookup"><span data-stu-id="69583-161">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="69583-162">Jeśli ikona koszyka ma wyświetlać podsumowanie koszyka (zwanego również „koszykiem mini”), zaznaczając opcję **Wyświetlanie koszyka mini**.</span><span class="sxs-lookup"><span data-stu-id="69583-162">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="69583-163">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="69583-163">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="69583-164">Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.</span><span class="sxs-lookup"><span data-stu-id="69583-164">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="69583-165">W gnieździe **Nagłówek** w module **Strona domyślna** dodaj fragment stopki, który został utworzony.</span><span class="sxs-lookup"><span data-stu-id="69583-165">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="69583-166">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="69583-166">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="69583-167">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="69583-167">Additional resources</span></span>

[<span data-ttu-id="69583-168">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="69583-168">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="69583-169">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="69583-169">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="69583-170">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="69583-170">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="69583-171">Moduł transparentu promocyjnego</span><span class="sxs-lookup"><span data-stu-id="69583-171">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="69583-172">Moduł Menu nawigacji</span><span class="sxs-lookup"><span data-stu-id="69583-172">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="69583-173">Zgoda na plik cookie</span><span class="sxs-lookup"><span data-stu-id="69583-173">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="69583-174">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="69583-174">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="69583-175">Moduł wyboru witryny</span><span class="sxs-lookup"><span data-stu-id="69583-175">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="69583-176">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="69583-176">Store selector module</span></span>](store-selector.md)
