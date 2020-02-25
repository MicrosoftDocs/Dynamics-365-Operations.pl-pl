---
title: Strony i moduły zarządzania kontem
description: Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8787a7b01ecf15752569d2a3a8d7804fe492e63d
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025723"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="13f16-103">Strony i moduły zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="13f16-103">Account management pages and modules</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="13f16-104">Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="13f16-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="13f16-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="13f16-105">Overview</span></span>

<span data-ttu-id="13f16-106">Zarządzanie kontami odnosi się do grupy stron służącej do zarządzania informacjami powiązanymi z kontem użytkownika w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="13f16-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="13f16-107">Strony zarządzania kontami obejmują stronę docelową zarządzanie kontami, atrona profil użytkownika, atrona adres użytkownika, strona historia zamówień, strona szczegóły zamówienia, strona lojalnościowa i strona listy życzeń.</span><span class="sxs-lookup"><span data-stu-id="13f16-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="13f16-108">Strona docelowa zarządzania kontami</span><span class="sxs-lookup"><span data-stu-id="13f16-108">Account management landing page</span></span>

<span data-ttu-id="13f16-109">Na stronie docelowej zarządzania kontami są używane następujące moduły:</span><span class="sxs-lookup"><span data-stu-id="13f16-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="13f16-110">**Kontener** — wszystkie moduły strony ładunkowej modułu Zarządzanie kontami powinny być umieszczone w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="13f16-110">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="13f16-111">**Kafelek powitalny konta** — ten moduł służy do dostarczania wiadomości powitalnej na stronie zarządzania kontami.</span><span class="sxs-lookup"><span data-stu-id="13f16-111">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="13f16-112">Zawiera on właściwości nagłówka.</span><span class="sxs-lookup"><span data-stu-id="13f16-112">It includes properties for the heading.</span></span>
- <span data-ttu-id="13f16-113">**Ogólny kafelek konta** — ten moduł może służyć do udostępniania nagłówków i łączy do stron zarządzania kontami, np. stron historia zamówień lub „Mój profil”.</span><span class="sxs-lookup"><span data-stu-id="13f16-113">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="13f16-114">Moduł kafelków ogólnych może być używany do konfigurowania kafelków na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="13f16-114">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="13f16-115">W firmie Fabrikam ten moduł jest używany w łączach stron „Historia zamówień” i „Mój profil” na stronie spocznik zarządzania kontami.</span><span class="sxs-lookup"><span data-stu-id="13f16-115">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="13f16-116">**Kafelek listy życzeń konta** — ten moduł służy do podania podsumowania towarów z listy życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="13f16-116">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="13f16-117">Na przykład może to być stan, „na liście życzeń znajduje się 10 pozycji”.</span><span class="sxs-lookup"><span data-stu-id="13f16-117">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="13f16-118">Zawiera on właściwości nagłówka i łącze „Wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="13f16-118">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="13f16-119">Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony lista życzeń.</span><span class="sxs-lookup"><span data-stu-id="13f16-119">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="13f16-120">**Kafelek adresu konta** — ten moduł służy do podawania podsumowania adresu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="13f16-120">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="13f16-121">Na przykład może to być stan, „Dwa adresy dodane do konta”.</span><span class="sxs-lookup"><span data-stu-id="13f16-121">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="13f16-122">Zawiera on właściwości nagłówka i łącze „Wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="13f16-122">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="13f16-123">Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony adres użytkownika.</span><span class="sxs-lookup"><span data-stu-id="13f16-123">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="13f16-124">**Kafelek lojalnościowy konta** — ten moduł służy do wyświetlania informacji o programie lojalnościowym i łączenia ich z tymi informacjami.</span><span class="sxs-lookup"><span data-stu-id="13f16-124">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="13f16-125">Ten kafelek ma dwa stany: jeden stan przedstawia łącza, aby przyłączyć się do karty lojalnościowej, jeśli użytkownik nie jest już członkiem progamu.</span><span class="sxs-lookup"><span data-stu-id="13f16-125">This tile has two states: one state shows links to join a loyalty progam if the user is not a member already.</span></span> <span data-ttu-id="13f16-126">W innym stanie są wyświetlane łącza umożliwiające wyświetlenie strony szczegóły dotyczące lojalności, gdy użytkownik jest już członkiem.</span><span class="sxs-lookup"><span data-stu-id="13f16-126">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="13f16-127">Właściwości obejmują nagłówek, łącze „Zarejestruj się” i łącze „Wyświetl lojalność”.</span><span class="sxs-lookup"><span data-stu-id="13f16-127">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="13f16-128">Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony program lojalnościowy użytkownika.</span><span class="sxs-lookup"><span data-stu-id="13f16-128">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="13f16-129">Łącze „Zarejestruj się” powinno być skonfigurowane tak, aby przekierowywać na stronę, na której użytkownicy mogą dołączać się do programu lojalnościowego.</span><span class="sxs-lookup"><span data-stu-id="13f16-129">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="13f16-130">Strona historii zamówień</span><span class="sxs-lookup"><span data-stu-id="13f16-130">Order history page</span></span>

<span data-ttu-id="13f16-131">Strona historia zamówień korzysta z modułu historia zamówień w celu wyświetlenia wszystkich ostatnich zamówień złożonych przez tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="13f16-131">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="13f16-132">Strona szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="13f16-132">Order details page</span></span>

<span data-ttu-id="13f16-133">Strona szczegóły zamówienia zawiera szczegółowe informacje dotyczące poszczególnych zamówień i jest dostępna na stronie historia zamówień.</span><span class="sxs-lookup"><span data-stu-id="13f16-133">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="13f16-134">Używa modułu szczegóły zamówienia, który wymaga identyfikatora sprzedaży lub identyfikatora transakcji w celu pobrania szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="13f16-134">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="13f16-135">Strona profil użytkownika</span><span class="sxs-lookup"><span data-stu-id="13f16-135">User profile page</span></span>

<span data-ttu-id="13f16-136">Na stronie profilu użytkownika są wyświetlane szczegóły dotyczące konta użytkownika, takie jak nazwa użytkownika i adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="13f16-136">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="13f16-137">Używa on szczegółów profilu użytkownika i modułu edytuj profil użytkownika.</span><span class="sxs-lookup"><span data-stu-id="13f16-137">It uses the user profile details and user profile edit modules.</span></span> <span data-ttu-id="13f16-138">Chociaż adresu e-mail nie da się usunąć, można go edytować.</span><span class="sxs-lookup"><span data-stu-id="13f16-138">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="13f16-139">Strona profilu użytkownika zawiera także preferencje użytkownika, które umożliwiają użytkownikowi włączenie lub rezygnację z niektórych funkcji, takich jak personalizacja list rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="13f16-139">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features, such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="13f16-140">Strona adres e-mail użytkownika</span><span class="sxs-lookup"><span data-stu-id="13f16-140">User address page</span></span>

<span data-ttu-id="13f16-141">Na stronie adres użytkownika jest wyświetlana lista adresów skojarzonych z danym kontem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="13f16-141">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="13f16-142">Użytkownik albo dostarczył te adresy w trakcie realizacji transakcji, albo dodał je bezpośrednio na tej stronie.</span><span class="sxs-lookup"><span data-stu-id="13f16-142">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="13f16-143">Używany jest moduł adres użytkownika służący do dodawania i edytowania adresów, ustawiania adresu podstawowego oraz renderowania istniejących adresów na stronie.</span><span class="sxs-lookup"><span data-stu-id="13f16-143">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="13f16-144">Strona listy życzeń</span><span class="sxs-lookup"><span data-stu-id="13f16-144">Wish list page</span></span>

<span data-ttu-id="13f16-145">Na stronie listy życzeń są wyświetlane towary dodane do listy życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="13f16-145">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="13f16-146">Moduł listy życzeń używa do renderowania elementów listy życzeń.</span><span class="sxs-lookup"><span data-stu-id="13f16-146">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="13f16-147">Strona lojalnościowa</span><span class="sxs-lookup"><span data-stu-id="13f16-147">Loyalty page</span></span>

<span data-ttu-id="13f16-148">Na stronie lojalnościowej odbiorcy można zobaczyć szczegóły programu lojalnościowego lub, jeśli są już członkami programów lojalnościowych.</span><span class="sxs-lookup"><span data-stu-id="13f16-148">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="13f16-149">Mogą również wyświetlać punkty zdobyte i zrealizowane w ostatnich transakcjach.</span><span class="sxs-lookup"><span data-stu-id="13f16-149">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="13f16-150">Na stronie jest używany moduł szczegóły lojalnościowe w celu pokazania szczegółów dotyczących lojalności.</span><span class="sxs-lookup"><span data-stu-id="13f16-150">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="13f16-151">Aby dołączyć do programu lojalnościowego, strona marketingowa może zostać utworzona za pomocą konta lojalnościowego i modułów zasad lojalności.</span><span class="sxs-lookup"><span data-stu-id="13f16-151">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="13f16-152">Jeśli użytkownik nie jest członkiem programu lojalnościowego, moduły te pozwolą użytkownikowi zarejestrować się.</span><span class="sxs-lookup"><span data-stu-id="13f16-152">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13f16-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="13f16-153">Additional resources</span></span>

[<span data-ttu-id="13f16-154">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="13f16-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="13f16-155">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="13f16-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="13f16-156">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="13f16-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="13f16-157">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="13f16-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="13f16-158">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="13f16-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="13f16-159">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="13f16-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="13f16-160">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="13f16-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="13f16-161">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="13f16-161">Footer module</span></span>](author-footer-module.md)
