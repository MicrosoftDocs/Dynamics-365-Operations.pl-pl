---
title: Strony i moduły zarządzania kontem
description: Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 29523d03fb687684dae7d0ce08208905cce702df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206638"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="31290-103">Strony i moduły zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="31290-103">Account management pages and modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="31290-104">Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="31290-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="31290-105">Zarządzanie kontami odnosi się do grupy stron służącej do zarządzania informacjami powiązanymi z kontem użytkownika w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="31290-105">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="31290-106">Strony zarządzania kontami obejmują stronę docelową zarządzanie kontami, atrona profil użytkownika, atrona adres użytkownika, strona historia zamówień, strona szczegóły zamówienia, strona lojalnościowa i strona listy życzeń.</span><span class="sxs-lookup"><span data-stu-id="31290-106">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="31290-107">Strona docelowa zarządzania kontami</span><span class="sxs-lookup"><span data-stu-id="31290-107">Account management landing page</span></span>

<span data-ttu-id="31290-108">Na stronie docelowej zarządzania kontami są używane następujące moduły:</span><span class="sxs-lookup"><span data-stu-id="31290-108">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="31290-109">**Kontener** — wszystkie moduły strony ładunkowej modułu Zarządzanie kontami powinny być umieszczone w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="31290-109">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="31290-110">**Kafelek powitalny konta** — ten moduł służy do dostarczania wiadomości powitalnej na stronie zarządzania kontami.</span><span class="sxs-lookup"><span data-stu-id="31290-110">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="31290-111">Zawiera on właściwości nagłówka.</span><span class="sxs-lookup"><span data-stu-id="31290-111">It includes properties for the heading.</span></span>
- <span data-ttu-id="31290-112">**Ogólny kafelek konta** — ten moduł może służyć do udostępniania nagłówków i łączy do stron zarządzania kontami, np. stron historia zamówień lub „Mój profil”.</span><span class="sxs-lookup"><span data-stu-id="31290-112">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="31290-113">Moduł kafelków ogólnych może być używany do konfigurowania kafelków na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="31290-113">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="31290-114">W firmie Fabrikam ten moduł jest używany w łączach stron „Historia zamówień” i „Mój profil” na stronie spocznik zarządzania kontami.</span><span class="sxs-lookup"><span data-stu-id="31290-114">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="31290-115">**Kafelek listy życzeń konta** — ten moduł służy do podania podsumowania towarów z listy życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="31290-115">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="31290-116">Na przykład może to być stan, „na liście życzeń znajduje się 10 pozycji”.</span><span class="sxs-lookup"><span data-stu-id="31290-116">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="31290-117">Zawiera on właściwości nagłówka i łącze „Wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="31290-117">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="31290-118">Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony lista życzeń.</span><span class="sxs-lookup"><span data-stu-id="31290-118">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="31290-119">**Kafelek adresu konta** — ten moduł służy do podawania podsumowania adresu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="31290-119">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="31290-120">Na przykład może to być stan, „Dwa adresy dodane do konta”.</span><span class="sxs-lookup"><span data-stu-id="31290-120">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="31290-121">Zawiera on właściwości nagłówka i łącze „Wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="31290-121">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="31290-122">Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony adres użytkownika.</span><span class="sxs-lookup"><span data-stu-id="31290-122">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="31290-123">**Kafelek lojalnościowy konta** — ten moduł służy do wyświetlania informacji o programie lojalnościowym i łączenia ich z tymi informacjami.</span><span class="sxs-lookup"><span data-stu-id="31290-123">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="31290-124">Ten kafelek ma dwa stany: jeden stan przedstawia łącza, aby przyłączyć się do karty lojalnościowej, jeśli użytkownik nie jest już członkiem progamu.</span><span class="sxs-lookup"><span data-stu-id="31290-124">This tile has two states: one state shows links to join a loyalty progam if the user is not a member already.</span></span> <span data-ttu-id="31290-125">W innym stanie są wyświetlane łącza umożliwiające wyświetlenie strony szczegóły dotyczące lojalności, gdy użytkownik jest już członkiem.</span><span class="sxs-lookup"><span data-stu-id="31290-125">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="31290-126">Właściwości obejmują nagłówek, łącze „Zarejestruj się” i łącze „Wyświetl lojalność”.</span><span class="sxs-lookup"><span data-stu-id="31290-126">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="31290-127">Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony program lojalnościowy użytkownika.</span><span class="sxs-lookup"><span data-stu-id="31290-127">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="31290-128">Łącze „Zarejestruj się” powinno być skonfigurowane tak, aby przekierowywać na stronę, na której użytkownicy mogą dołączać się do programu lojalnościowego.</span><span class="sxs-lookup"><span data-stu-id="31290-128">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="31290-129">Strona historii zamówień</span><span class="sxs-lookup"><span data-stu-id="31290-129">Order history page</span></span>

<span data-ttu-id="31290-130">Strona historia zamówień korzysta z modułu historia zamówień w celu wyświetlenia wszystkich ostatnich zamówień złożonych przez tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="31290-130">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="31290-131">Strona szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="31290-131">Order details page</span></span>

<span data-ttu-id="31290-132">Strona szczegóły zamówienia zawiera szczegółowe informacje dotyczące poszczególnych zamówień i jest dostępna na stronie historia zamówień.</span><span class="sxs-lookup"><span data-stu-id="31290-132">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="31290-133">Używa modułu szczegóły zamówienia, który wymaga identyfikatora sprzedaży lub identyfikatora transakcji w celu pobrania szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="31290-133">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="31290-134">Strona profil użytkownika</span><span class="sxs-lookup"><span data-stu-id="31290-134">User profile page</span></span>

<span data-ttu-id="31290-135">Na stronie profilu użytkownika są wyświetlane szczegóły dotyczące konta użytkownika, takie jak nazwa użytkownika i adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="31290-135">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="31290-136">Używa on szczegółów profilu użytkownika i modułu edytuj profil użytkownika.</span><span class="sxs-lookup"><span data-stu-id="31290-136">It uses the user profile details and user profile edit modules.</span></span> <span data-ttu-id="31290-137">Chociaż adresu e-mail nie da się usunąć, można go edytować.</span><span class="sxs-lookup"><span data-stu-id="31290-137">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="31290-138">Strona profilu użytkownika zawiera także preferencje użytkownika, które umożliwiają użytkownikowi włączenie lub rezygnację z niektórych funkcji, takich jak personalizacja list rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="31290-138">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features, such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="31290-139">Strona adres e-mail użytkownika</span><span class="sxs-lookup"><span data-stu-id="31290-139">User address page</span></span>

<span data-ttu-id="31290-140">Na stronie adres użytkownika jest wyświetlana lista adresów skojarzonych z danym kontem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="31290-140">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="31290-141">Użytkownik albo dostarczył te adresy w trakcie realizacji transakcji, albo dodał je bezpośrednio na tej stronie.</span><span class="sxs-lookup"><span data-stu-id="31290-141">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="31290-142">Używany jest moduł adres użytkownika służący do dodawania i edytowania adresów, ustawiania adresu podstawowego oraz renderowania istniejących adresów na stronie.</span><span class="sxs-lookup"><span data-stu-id="31290-142">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="31290-143">Strona listy życzeń</span><span class="sxs-lookup"><span data-stu-id="31290-143">Wish list page</span></span>

<span data-ttu-id="31290-144">Na stronie listy życzeń są wyświetlane towary dodane do listy życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="31290-144">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="31290-145">Moduł listy życzeń używa do renderowania elementów listy życzeń.</span><span class="sxs-lookup"><span data-stu-id="31290-145">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="31290-146">Strona lojalnościowa</span><span class="sxs-lookup"><span data-stu-id="31290-146">Loyalty page</span></span>

<span data-ttu-id="31290-147">Na stronie lojalnościowej odbiorcy można zobaczyć szczegóły programu lojalnościowego lub, jeśli są już członkami programów lojalnościowych.</span><span class="sxs-lookup"><span data-stu-id="31290-147">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="31290-148">Mogą również wyświetlać punkty zdobyte i zrealizowane w ostatnich transakcjach.</span><span class="sxs-lookup"><span data-stu-id="31290-148">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="31290-149">Na stronie jest używany moduł szczegóły lojalnościowe w celu pokazania szczegółów dotyczących lojalności.</span><span class="sxs-lookup"><span data-stu-id="31290-149">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="31290-150">Aby dołączyć do programu lojalnościowego, strona marketingowa może zostać utworzona za pomocą konta lojalnościowego i modułów zasad lojalności.</span><span class="sxs-lookup"><span data-stu-id="31290-150">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="31290-151">Jeśli użytkownik nie jest członkiem programu lojalnościowego, moduły te pozwolą użytkownikowi zarejestrować się.</span><span class="sxs-lookup"><span data-stu-id="31290-151">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31290-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="31290-152">Additional resources</span></span>

[<span data-ttu-id="31290-153">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="31290-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="31290-154">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="31290-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="31290-155">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="31290-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="31290-156">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="31290-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="31290-157">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="31290-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="31290-158">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="31290-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="31290-159">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="31290-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="31290-160">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="31290-160">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]