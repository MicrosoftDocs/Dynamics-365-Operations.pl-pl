---
title: Moduł nagłówka
description: W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: cec138ebefbd2beb2f1cf6302ce58d8bbc5c4bbd
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261451"
---
# <a name="header-module"></a><span data-ttu-id="225e7-103">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="225e7-103">Header module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="225e7-104">W tym temacie opisano moduły nagłówka i sposób tworzenia nagłówków stron w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="225e7-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="225e7-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="225e7-105">Overview</span></span>

<span data-ttu-id="225e7-106">W Dynamics 365 Commerce nagłówek strony składa się z wielu modułów, takich jak nagłówek, menu nawigacji, wyszukiwanie, transparent i pole zgody na pliki cookie.</span><span class="sxs-lookup"><span data-stu-id="225e7-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="225e7-107">Moduł nagłówka zawiera logo witryny, łącza do hierarchii nawigacji, łącza do innych stron w witrynie, symbol koszyka, symbol Wishlist, opcje logowania i pasek wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="225e7-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="225e7-108">Moduł nagłówka jest automatycznie optymalizowany dla urządzenia, na którym jest oglądana witryna (czyli inaczej urządzenie stacjonarne lub urządzenie przenośne).</span><span class="sxs-lookup"><span data-stu-id="225e7-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="225e7-109">Na przykład na urządzeniu przenośnym pasek nawigacji jest zwinięty do przycisku **Menu** (który jest czasami nazywany *menu hamburgerowym*).</span><span class="sxs-lookup"><span data-stu-id="225e7-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header-module"></a><span data-ttu-id="225e7-110">Moduł właściwości nagłówka</span><span class="sxs-lookup"><span data-stu-id="225e7-110">Properties of a header module</span></span>

<span data-ttu-id="225e7-111">Moduł nagłówka obsługuje **Logo**, **Łącze logo** i właściwości **Łącza do Moje konto**.</span><span class="sxs-lookup"><span data-stu-id="225e7-111">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="225e7-112">Właściwości **Logo** i **Łącze logo** są używane do definiowania logo na stronie.</span><span class="sxs-lookup"><span data-stu-id="225e7-112">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="225e7-113">Aby uzyskać więcej informacji, zobacz [Dodawanie logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="225e7-113">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="225e7-114">Za pomocą **Łącza do Moje konto** można zdefiniować strony kont, które właściciel witryny chce wyświetlić szybkie łącza w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="225e7-114">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="225e7-115">Moduły dostępne w module nagłówka</span><span class="sxs-lookup"><span data-stu-id="225e7-115">Modules that are available in a header module</span></span>

<span data-ttu-id="225e7-116">W module nagłówka mogą być używane następujące moduły:</span><span class="sxs-lookup"><span data-stu-id="225e7-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="225e7-117">**Menu nawigacji** — menu nawigacji reprezentuje hierarchię nawigacji kanału i inne statyczne łącza nawigacji.</span><span class="sxs-lookup"><span data-stu-id="225e7-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="225e7-118">Hierarchię nawigacji kanału można skonfigurować w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="225e7-118">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="225e7-119">Menu nawigacji zawiera właściwość **Źródło nawigacji**, która służy do określania elementów menu nawigacji serwera sieci sprzedaży i statycznych elementów menu jako źródła.</span><span class="sxs-lookup"><span data-stu-id="225e7-119">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="225e7-120">Jeśli statyczne elementy menu są określone jako źródło, można podać łącza względne do innych stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="225e7-120">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="225e7-121">Skonfigurowane elementy zostaną wyświetlone jako nawigacja w nagłówkach.</span><span class="sxs-lookup"><span data-stu-id="225e7-121">Configured items then appear as header navigation.</span></span> 
- <span data-ttu-id="225e7-122">**Pasek wyszukiwania** — moduł wyszukiwania umożliwia użytkownikom wprowadzanie kryteriów wyszukiwania, co pozwala na wyszukiwanie produktów.</span><span class="sxs-lookup"><span data-stu-id="225e7-122">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="225e7-123">Adres URL domyślnej strony wyszukiwania oraz parametry kwerendy wyszukiwania muszą być podane w **Ustawienia witryny \> Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="225e7-123">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="225e7-124">Moduł wyszukiwania ma właściwości pozwalające pominąć przycisk Wyszukaj lub etykieta w razie konieczności.</span><span class="sxs-lookup"><span data-stu-id="225e7-124">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="225e7-125">Moduł wyszukiwania obsługuje także opcje automatycznego sugerowania, takie jak produkt, słowo kluczowe i wyniki wyszukiwania kategorii.</span><span class="sxs-lookup"><span data-stu-id="225e7-125">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>
- <span data-ttu-id="225e7-126">**Ikona koszyka** — moduł ikony koszyka reprezentuje ikonę koszyka, w której w danym momencie jest wyświetlana liczba pozycji w koszyku.</span><span class="sxs-lookup"><span data-stu-id="225e7-126">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="225e7-127">Aby uzyskać więcej informacji, zajrzyj do [Moduł ikony koszyka](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="225e7-127">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="225e7-128">Utwórz moduł nagłówka dla strony</span><span class="sxs-lookup"><span data-stu-id="225e7-128">Create a header module for a page</span></span>

<span data-ttu-id="225e7-129">Aby utworzyć moduł nagłówka, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="225e7-129">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="225e7-130">Utwórz fragment o nazwie **Fragment nagłówka** i dodaj do niego moduł kontenera.</span><span class="sxs-lookup"><span data-stu-id="225e7-130">Create a fragment that is named **Header fragment**, and add a container module to it.</span></span>
1. <span data-ttu-id="225e7-131">W okienku właściwości modułu kontenerów określ właściwość **Szerokość** na **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="225e7-131">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="225e7-132">Dodaj moduły zgody na transparent i plik cookie dotyczące awansowania do modułu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="225e7-132">Add a promo banner and cookie consent modules to the container module.</span></span>
1. <span data-ttu-id="225e7-133">Dodaj kolejny moduł kontenera do fragmentu i ustaw wartosć **Szerokość** na **Wypełnij kontener**.</span><span class="sxs-lookup"><span data-stu-id="225e7-133">Add another container module to the fragment, and set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="225e7-134">Dodaj moduł nagłówka do drugiego modułu kontenera.</span><span class="sxs-lookup"><span data-stu-id="225e7-134">Add a header module to the second container module.</span></span>
1. <span data-ttu-id="225e7-135">Dodaj moduł **menu nawigacji** w gnieździe menu nawigacji modułu nagłówka.</span><span class="sxs-lookup"><span data-stu-id="225e7-135">In the **Navigation menu** slot of the header module, add a navigation menu module.</span></span> 
1. <span data-ttu-id="225e7-136">W okienku właściwości modułu menu nawigacji skonfiguruj właściwości modułu menu nawigacji.</span><span class="sxs-lookup"><span data-stu-id="225e7-136">In the property pane for the navigation menu module, configure the properties of the navigation menu module.</span></span>
1. <span data-ttu-id="225e7-137">W gnieździe **wyszukiwania** modułu nagłówka dodaj moduł wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="225e7-137">In the **Search** slot of the header module, add a search module.</span></span> 
1. <span data-ttu-id="225e7-138">W okienku właściwości modułu wyszukiwania skonfiguruj właściwości modułu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="225e7-138">In the property pane for the search module, configure the properties of the search module.</span></span> 
1. <span data-ttu-id="225e7-139">W gnieździe **Ikona koszyka** w module nagłówka dodaj moduł ikony koszyka.</span><span class="sxs-lookup"><span data-stu-id="225e7-139">In the **Cart icon** slot of the header module, add a cart icon module.</span></span> 
1. <span data-ttu-id="225e7-140">W okienku właściwości modułu ikony koszyka skonfiguruj właściwości modułu ikony koszyka.</span><span class="sxs-lookup"><span data-stu-id="225e7-140">In the property pane for the cart icon module, configure the properties of the cart icon module.</span></span> <span data-ttu-id="225e7-141">Jeśli ikona koszyka ma wyświetlać mini-koszyk po najechaniu na nią kursorem, wybierz wartość **Prada** dla opcji **Pokazuj mini-koszyk**.</span><span class="sxs-lookup"><span data-stu-id="225e7-141">If you want the cart icon to display a mini cart when hovered over, select **True** for **Show mini cart**.</span></span>
1. <span data-ttu-id="225e7-142">Zapisz fragment strony, zakończ jego edycję, a następnie go opublikuj.</span><span class="sxs-lookup"><span data-stu-id="225e7-142">Save the page fragment, finish editing, and publish it.</span></span> 


<span data-ttu-id="225e7-143">Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.</span><span class="sxs-lookup"><span data-stu-id="225e7-143">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="225e7-144">W gnieździe **Grupa główna** strony domyślnej dodaj fragment nagłówka zawierający moduł nagłówka do nagłówka.</span><span class="sxs-lookup"><span data-stu-id="225e7-144">In the **Main** slot of the default page, add the header page fragment that contains the header module to the header.</span></span>
1. <span data-ttu-id="225e7-145">Zapisz szablon, zakończ jego edycję, a następnie go opublikuj.</span><span class="sxs-lookup"><span data-stu-id="225e7-145">Save the template, finish editing, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="225e7-146">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="225e7-146">Additional resources</span></span>

[<span data-ttu-id="225e7-147">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="225e7-147">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="225e7-148">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="225e7-148">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="225e7-149">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="225e7-149">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="225e7-150">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="225e7-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="225e7-151">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="225e7-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="225e7-152">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="225e7-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="225e7-153">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="225e7-153">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="225e7-154">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="225e7-154">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="225e7-155">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="225e7-155">Footer module</span></span>](author-footer-module.md)
