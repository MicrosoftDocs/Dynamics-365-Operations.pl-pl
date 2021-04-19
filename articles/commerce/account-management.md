---
title: Strony i moduły zarządzania kontem
description: Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: df4959a61f1b2948c62a558523a848ff8b2fe0a8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796301"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="06296-103">Strony i moduły zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="06296-103">Account management pages and modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="06296-104">Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="06296-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="06296-105">Zarządzanie kontami odnosi się do grupy stron służącej do zarządzania informacjami powiązanymi z kontem użytkownika w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="06296-105">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="06296-106">Strony zarządzania kontami obejmują stronę docelową zarządzanie kontami, atrona profil użytkownika, atrona adres użytkownika, strona historia zamówień, strona szczegóły zamówienia, strona lojalnościowa i strona listy życzeń.</span><span class="sxs-lookup"><span data-stu-id="06296-106">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="06296-107">Strona docelowa zarządzania kontami</span><span class="sxs-lookup"><span data-stu-id="06296-107">Account management landing page</span></span>

<span data-ttu-id="06296-108">Na stronie docelowej zarządzania kontami są używane następujące moduły:</span><span class="sxs-lookup"><span data-stu-id="06296-108">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="06296-109">**Kontener** — wszystkie moduły strony ładunkowej modułu Zarządzanie kontami powinny być umieszczone w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="06296-109">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="06296-110">**Kafelek powitalny konta** — ten moduł służy do dostarczania wiadomości powitalnej na stronie zarządzania kontami.</span><span class="sxs-lookup"><span data-stu-id="06296-110">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="06296-111">Zawiera on właściwości nagłówka.</span><span class="sxs-lookup"><span data-stu-id="06296-111">It includes properties for the heading.</span></span>
- <span data-ttu-id="06296-112">**Ogólny kafelek konta** — ten moduł może służyć do udostępniania nagłówków i łączy do stron zarządzania kontami, np. stron historia zamówień lub „Mój profil”.</span><span class="sxs-lookup"><span data-stu-id="06296-112">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="06296-113">Moduł kafelków ogólnych może być używany do konfigurowania kafelków na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="06296-113">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="06296-114">W firmie Fabrikam ten moduł jest używany w łączach stron „Historia zamówień” i „Mój profil” na stronie spocznik zarządzania kontami.</span><span class="sxs-lookup"><span data-stu-id="06296-114">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="06296-115">**Kafelek listy życzeń konta** — ten moduł służy do podania podsumowania towarów z listy życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="06296-115">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="06296-116">Na przykład może to być stan, „na liście życzeń znajduje się 10 pozycji”.</span><span class="sxs-lookup"><span data-stu-id="06296-116">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="06296-117">Zawiera on właściwości nagłówka i łącze „Wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="06296-117">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="06296-118">Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony lista życzeń.</span><span class="sxs-lookup"><span data-stu-id="06296-118">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="06296-119">**Kafelek adresu konta** — ten moduł służy do podawania podsumowania adresu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="06296-119">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="06296-120">Na przykład może to być stan, „Dwa adresy dodane do konta”.</span><span class="sxs-lookup"><span data-stu-id="06296-120">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="06296-121">Zawiera on właściwości nagłówka i łącze „Wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="06296-121">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="06296-122">Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony adres użytkownika.</span><span class="sxs-lookup"><span data-stu-id="06296-122">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="06296-123">**Kafelek lojalnościowy konta** — ten moduł służy do wyświetlania informacji o programie lojalnościowym i łączenia ich z tymi informacjami.</span><span class="sxs-lookup"><span data-stu-id="06296-123">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="06296-124">Ten kafelek ma dwa stany: jeden stan przedstawia łącza, aby przyłączyć się do karty lojalnościowej, jeśli użytkownik nie jest już członkiem progamu.</span><span class="sxs-lookup"><span data-stu-id="06296-124">This tile has two states: one state shows links to join a loyalty program if the user is not a member already.</span></span> <span data-ttu-id="06296-125">W innym stanie są wyświetlane łącza umożliwiające wyświetlenie strony szczegóły dotyczące lojalności, gdy użytkownik jest już członkiem.</span><span class="sxs-lookup"><span data-stu-id="06296-125">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="06296-126">Właściwości obejmują nagłówek, łącze „Zarejestruj się” i łącze „Wyświetl lojalność”.</span><span class="sxs-lookup"><span data-stu-id="06296-126">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="06296-127">Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony program lojalnościowy użytkownika.</span><span class="sxs-lookup"><span data-stu-id="06296-127">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="06296-128">Łącze „Zarejestruj się” powinno być skonfigurowane tak, aby przekierowywać na stronę, na której użytkownicy mogą dołączać się do programu lojalnościowego.</span><span class="sxs-lookup"><span data-stu-id="06296-128">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="06296-129">Strona historii zamówień</span><span class="sxs-lookup"><span data-stu-id="06296-129">Order history page</span></span>

<span data-ttu-id="06296-130">Strona historia zamówień korzysta z modułu historia zamówień w celu wyświetlenia wszystkich ostatnich zamówień złożonych przez tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="06296-130">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="06296-131">Strona szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="06296-131">Order details page</span></span>

<span data-ttu-id="06296-132">Strona szczegóły zamówienia zawiera szczegółowe informacje dotyczące poszczególnych zamówień i jest dostępna na stronie historia zamówień.</span><span class="sxs-lookup"><span data-stu-id="06296-132">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="06296-133">Używa modułu szczegóły zamówienia, który wymaga identyfikatora sprzedaży lub identyfikatora transakcji w celu pobrania szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="06296-133">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="my-profile-page"></a><span data-ttu-id="06296-134">Strona Mój profil</span><span class="sxs-lookup"><span data-stu-id="06296-134">My profile page</span></span>

<span data-ttu-id="06296-135">Na stronie Mój profil można wyświetlić szczegóły profilu konta użytkownika, korzystając z modułu profilu konta.</span><span class="sxs-lookup"><span data-stu-id="06296-135">The My profile page shows the user's account profile details using the account profile module.</span></span> <span data-ttu-id="06296-136">Na stronie pokazano adres e-mail skojarzony z kontem użytkownika, a także preferencje ustawione dla tego konta.</span><span class="sxs-lookup"><span data-stu-id="06296-136">The page shows the email address associated with the user's account, as well as preferences set up for the account.</span></span> <span data-ttu-id="06296-137">W przypadku konfigurowania niestandardowych atrybutów odbiorcy, w sekcji „Informacje dodatkowe” są także wyświetlane te atrybuty.</span><span class="sxs-lookup"><span data-stu-id="06296-137">If setting up custom customer attributes, an "Additional Information" section will also display those attributes.</span></span> <span data-ttu-id="06296-138">Użytkownicy mogą edytować swoje imię i nazwisko, preferencje lub dodatkowe informacje (jeśli są dostępne).</span><span class="sxs-lookup"><span data-stu-id="06296-138">Users can edit their name, preferences, or additional information (if available).</span></span>

### <a name="user-address-page"></a><span data-ttu-id="06296-139">Strona adres e-mail użytkownika</span><span class="sxs-lookup"><span data-stu-id="06296-139">User address page</span></span>

<span data-ttu-id="06296-140">Na stronie adres użytkownika jest wyświetlana lista adresów skojarzonych z danym kontem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="06296-140">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="06296-141">Użytkownik albo dostarczył te adresy w trakcie realizacji transakcji, albo dodał je bezpośrednio na tej stronie.</span><span class="sxs-lookup"><span data-stu-id="06296-141">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="06296-142">Używany jest moduł adres użytkownika służący do dodawania i edytowania adresów, ustawiania adresu podstawowego oraz renderowania istniejących adresów na stronie.</span><span class="sxs-lookup"><span data-stu-id="06296-142">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="06296-143">Strona listy życzeń</span><span class="sxs-lookup"><span data-stu-id="06296-143">Wish list page</span></span>

<span data-ttu-id="06296-144">Na stronie listy życzeń są wyświetlane towary dodane do listy życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="06296-144">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="06296-145">Moduł listy życzeń używa do renderowania elementów listy życzeń.</span><span class="sxs-lookup"><span data-stu-id="06296-145">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="06296-146">Strona lojalnościowa</span><span class="sxs-lookup"><span data-stu-id="06296-146">Loyalty page</span></span>

<span data-ttu-id="06296-147">Na stronie lojalnościowej odbiorcy można zobaczyć szczegóły programu lojalnościowego lub, jeśli są już członkami programów lojalnościowych.</span><span class="sxs-lookup"><span data-stu-id="06296-147">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="06296-148">Mogą również wyświetlać punkty zdobyte i zrealizowane w ostatnich transakcjach.</span><span class="sxs-lookup"><span data-stu-id="06296-148">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="06296-149">Na stronie jest używany moduł szczegóły lojalnościowe w celu pokazania szczegółów dotyczących lojalności.</span><span class="sxs-lookup"><span data-stu-id="06296-149">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="06296-150">Aby dołączyć do programu lojalnościowego, strona marketingowa może zostać utworzona za pomocą konta lojalnościowego i modułów zasad lojalności.</span><span class="sxs-lookup"><span data-stu-id="06296-150">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="06296-151">Jeśli użytkownik nie jest członkiem programu lojalnościowego, moduły te pozwolą użytkownikowi zarejestrować się.</span><span class="sxs-lookup"><span data-stu-id="06296-151">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="06296-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="06296-152">Additional resources</span></span>

[<span data-ttu-id="06296-153">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="06296-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="06296-154">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="06296-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="06296-155">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="06296-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="06296-156">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="06296-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="06296-157">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="06296-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="06296-158">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="06296-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="06296-159">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="06296-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="06296-160">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="06296-160">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]