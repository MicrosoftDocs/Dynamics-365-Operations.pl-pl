---
title: Moduł nagłówka
description: W tym temacie opisano moduły nagłówka i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885485"
---
# <a name="header-module"></a><span data-ttu-id="ea71d-103">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="ea71d-103">Header module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ea71d-104">W tym temacie opisano moduły nagłówka i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ea71d-104">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ea71d-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="ea71d-105">Overview</span></span>

<span data-ttu-id="ea71d-106">Moduł nagłówka jest specjalnym kontenerem używanym do obsługiwania wszystkich modułów, które będą wyświetlane w nagłówku strony.</span><span class="sxs-lookup"><span data-stu-id="ea71d-106">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="ea71d-107">Może to być na przykład logo witryny, łącza do hierarchii nawigacji, łącza do innych stron w witrynie oraz na pasku wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ea71d-107">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="ea71d-108">Moduł nagłówka jest automatycznie optymalizowany dla urządzenia, na którym jest oglądana witryna (czyli urządzenie stacjonarne lub urządzenie przenośne).</span><span class="sxs-lookup"><span data-stu-id="ea71d-108">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="ea71d-109">Na przykład na urządzeniu przenośnym pasek nawigacji jest zwinięty do przycisku **Menu** (który jest czasami nazywany *menu hamburgerowym*).</span><span class="sxs-lookup"><span data-stu-id="ea71d-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="ea71d-110">Właściwości nagłówka</span><span class="sxs-lookup"><span data-stu-id="ea71d-110">Properties of a header</span></span>

<span data-ttu-id="ea71d-111">Podobnie jak większość ogólnych kontenerów, moduł nagłówka obsługuje właściwości **nagłówka** i **szerokości**.</span><span class="sxs-lookup"><span data-stu-id="ea71d-111">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="ea71d-112">Moduł nagłówka ma wiele gniazd.</span><span class="sxs-lookup"><span data-stu-id="ea71d-112">A header module has multiple slots.</span></span> <span data-ttu-id="ea71d-113">Na przykład istnieją gniazda dla komunikatu informacyjnego, menu nawigacji, logo, paska wyszukiwania, ikony koszyka, ikony listy życzeń i informacji o koncie.</span><span class="sxs-lookup"><span data-stu-id="ea71d-113">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="ea71d-114">Każde gniazdo obsługuje określony zbiór modułów.</span><span class="sxs-lookup"><span data-stu-id="ea71d-114">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="ea71d-115">Moduły dostępne w module nagłówka</span><span class="sxs-lookup"><span data-stu-id="ea71d-115">Modules that are available in a header module</span></span>

<span data-ttu-id="ea71d-116">W module nagłówka mogą być używane następujące moduły:</span><span class="sxs-lookup"><span data-stu-id="ea71d-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="ea71d-117">**Menu nawigacji** — menu nawigacji reprezentuje hierarchię nawigacji kanału i inne statyczne łącza nawigacji.</span><span class="sxs-lookup"><span data-stu-id="ea71d-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="ea71d-118">Hierarchię nawigacji kanału można skonfigurować w Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="ea71d-118">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="ea71d-119">Skonfigurowane elementy zostaną wyświetlone jako nawigacja w nagłówkach.</span><span class="sxs-lookup"><span data-stu-id="ea71d-119">Configured items then appear as header navigation.</span></span> <span data-ttu-id="ea71d-120">Ponadto można konfigurować statyczne łącza nawigacji oraz łącza względne do innych stron w witrynie e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="ea71d-120">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="ea71d-121">Nagłówek może być wyrównany do lewej, do prawej lub do środka.</span><span class="sxs-lookup"><span data-stu-id="ea71d-121">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="ea71d-122">**Ikona koszyka** — ikona koszyka jest specjalną ikoną, która reprezentuje koszyk.</span><span class="sxs-lookup"><span data-stu-id="ea71d-122">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="ea71d-123">Jest ona wyświetlana w nagłówku i wskazuje liczbę pozycji w koszyku.</span><span class="sxs-lookup"><span data-stu-id="ea71d-123">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="ea71d-124">Łącze do strony koszyka powinno towarzyszyć ikonie koszyka, dzięki czemu odbiorcy mogą zostać przekierowani do strony koszyka podczas interakcji z tą ikoną.</span><span class="sxs-lookup"><span data-stu-id="ea71d-124">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="ea71d-125">**Ikona listy życzeń** — ikona listy życzeń jest wyświetlana w nagłówku i wskazuje liczbę towarów, które zostały dodane do listy życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="ea71d-125">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="ea71d-126">Łącze do strony życzeń powinno towarzyszyć tej ikonie, dzięki czemu odbiorcy mogą zostać przekierowani do strony życzeń podczas interakcji z tą ikoną.</span><span class="sxs-lookup"><span data-stu-id="ea71d-126">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="ea71d-127">**Moduł rejestracji** — w nagłówku jest wyświetlany moduł rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="ea71d-127">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="ea71d-128">Klienci mogą zalogować się do konta lub zarejestrować się w celu uwzględnienia konta.</span><span class="sxs-lookup"><span data-stu-id="ea71d-128">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="ea71d-129">Jeśli odbiorca jest już zalogowany, można tak skonfigurować moduł, aby pokazywał łącza do strony konta, strony historii zamówień lub innej strony.</span><span class="sxs-lookup"><span data-stu-id="ea71d-129">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="ea71d-130">**Moduł logo** — ten moduł pokazuje logo reprezentujące sprzedawcę i markę.</span><span class="sxs-lookup"><span data-stu-id="ea71d-130">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="ea71d-131">Jest to obraz, który ma łącze.</span><span class="sxs-lookup"><span data-stu-id="ea71d-131">It's an image that has a link.</span></span> <span data-ttu-id="ea71d-132">Łącze jest zazwyczaj skonfigurowane w taki sposób, aby zostało przekierowaniem na stronę główną, dlatego klienci mogą szybko powrócić do strony głównej z dowolnej strony w witrynie.</span><span class="sxs-lookup"><span data-stu-id="ea71d-132">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="ea71d-133">**Alert** — w nagłówku jest wyświetlany alert i jest on używany do wyświetlania komunikatu w wierszu, który ma zastosowanie do wszystkich stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="ea71d-133">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="ea71d-134">Na przykład alert może zawierać komunikat, na przykład „sprzedaż roczna kończy się za 2 dni”.</span><span class="sxs-lookup"><span data-stu-id="ea71d-134">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="ea71d-135">**Pasek wyszukiwania** — pasek wyszukiwania umożliwia użytkownikom wprowadzanie kryteriów wyszukiwania, co pozwala na wyszukiwanie produktów.</span><span class="sxs-lookup"><span data-stu-id="ea71d-135">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="ea71d-136">Moduł musi być skonfigurowany z adresem URL strony wyników wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ea71d-136">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="ea71d-137">Można skonfigurować parametr ciągu kwerendy (wartość domyślna to **„q”**).</span><span class="sxs-lookup"><span data-stu-id="ea71d-137">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="ea71d-138">Na pasku wyszukiwania jest zaproponowane gniazdo automatycznego sugerowania, w którym należy dodać moduł automatycznego sugerowania.</span><span class="sxs-lookup"><span data-stu-id="ea71d-138">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="ea71d-139">**Automatyczne sugerowanie** — moduł automatycznego sugerowania pokazuje automatycznie sugerowane wyniki.</span><span class="sxs-lookup"><span data-stu-id="ea71d-139">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="ea71d-140">Wyniki mogą być słowami kluczowymi, produktami lub kategoriami, w których wyszukiwany jest termin wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ea71d-140">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="ea71d-141">Tworzenie modułu nagłówka</span><span class="sxs-lookup"><span data-stu-id="ea71d-141">Create a header module</span></span>

<span data-ttu-id="ea71d-142">Aby utworzyć moduł nagłówka, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="ea71d-142">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="ea71d-143">Utwórz fragment strony zawierający moduł nagłówka.</span><span class="sxs-lookup"><span data-stu-id="ea71d-143">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="ea71d-144">Dodaj moduły do gniazd w module nagłówka.</span><span class="sxs-lookup"><span data-stu-id="ea71d-144">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="ea71d-145">Umożliwia zaktualizowanie ustawień dla każdego modułu.</span><span class="sxs-lookup"><span data-stu-id="ea71d-145">Update the settings for each module.</span></span>
1. <span data-ttu-id="ea71d-146">Zapisz jako fragment strony.</span><span class="sxs-lookup"><span data-stu-id="ea71d-146">Save the page fragment.</span></span> 
1. <span data-ttu-id="ea71d-147">Zaewidencjonuj stronę i opublikuj ją.</span><span class="sxs-lookup"><span data-stu-id="ea71d-147">Check in the page, and publish it.</span></span>

<span data-ttu-id="ea71d-148">Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.</span><span class="sxs-lookup"><span data-stu-id="ea71d-148">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="ea71d-149">Na stronie domyślne dodaj fragment strony zawierający moduł nagłówka do nagłówka w głównym gnieździe.</span><span class="sxs-lookup"><span data-stu-id="ea71d-149">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="ea71d-150">Zapisz szablon.</span><span class="sxs-lookup"><span data-stu-id="ea71d-150">Save the template.</span></span> 
1. <span data-ttu-id="ea71d-151">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="ea71d-151">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ea71d-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ea71d-152">Additional resources</span></span>

[<span data-ttu-id="ea71d-153">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="ea71d-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ea71d-154">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="ea71d-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ea71d-155">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="ea71d-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ea71d-156">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="ea71d-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ea71d-157">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="ea71d-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ea71d-158">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="ea71d-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ea71d-159">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="ea71d-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ea71d-160">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="ea71d-160">Footer module</span></span>](author-footer-module.md)
