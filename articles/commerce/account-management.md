---
title: Strony i moduły zarządzania kontem
description: Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 3986505a7e0e8d33d5b8ff2c06f493335731a8d9
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785395"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="5d5f3-103">Strony i moduły zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="5d5f3-103">Account management pages and modules</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="5d5f3-104">Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5d5f3-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="5d5f3-105">Overview</span></span>

<span data-ttu-id="5d5f3-106">Zarządzanie kontami odnosi się do grupy stron służącej do zarządzania informacjami powiązanymi z kontem użytkownika w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="5d5f3-107">Strony zarządzania kontami obejmują stronę docelową zarządzanie kontami, atrona profil użytkownika, atrona adres użytkownika, strona historia zamówień, strona szczegóły zamówienia, strona lojalnościowa i strona listy życzeń.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="5d5f3-108">Strona docelowa zarządzania kontami</span><span class="sxs-lookup"><span data-stu-id="5d5f3-108">Account management landing page</span></span>

<span data-ttu-id="5d5f3-109">Na stronie docelowej zarządzania kontami są używane następujące moduły:</span><span class="sxs-lookup"><span data-stu-id="5d5f3-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="5d5f3-110">**Rozmieszczenie zawartości** — ten moduł to moduł kontenera przechowujący wszystkie moduły na stronie docelowej zarządzania kontami.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-110">**Content placement** – This module is a container module that holds all the modules on the account management landing page.</span></span>
- <span data-ttu-id="5d5f3-111">**Element powitalny konta** — ten moduł służy do dostarczania wiadomości powitalnej na stronie zarządzania kontami.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-111">**Account welcome item** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="5d5f3-112">Zawiera on właściwości nagłówka i rozmiaru kafelka.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-112">It includes properties for the heading and the tile size.</span></span> <span data-ttu-id="5d5f3-113">Właściwość **Rozmiar kafelka** definiuje szerokość modułu w module umieszczania zawartości.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-113">The **Tile size** property defines the width of the module in the content placement module.</span></span> <span data-ttu-id="5d5f3-114">Wartości mieszczą się w zakresie od **1** do **12**, gdzie **12** oznacza pełną szerokość kontenera umieszczania zawartości.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-114">Values range from **1** through **12**, where **12** represents the full width of the content placement container.</span></span>
- <span data-ttu-id="5d5f3-115">**Element rozmieszczenia zamówienia konta** — ten moduł służy do podsumowania liczby zamówień ustawionych przez konto użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-115">**Account order placement item** – This module is used to provide a summary of the number of orders that have been placed by the user account.</span></span> <span data-ttu-id="5d5f3-116">Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-116">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="5d5f3-117">Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony historia zamówień.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-117">The "view details" link should be configured to redirect to the order history page.</span></span>
- <span data-ttu-id="5d5f3-118">**Element rozmieszczenia profilu konta** — ten moduł służy do podawania podsumowania profilu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-118">**Account profile placement item** – This module is used to provide a summary of the user profile.</span></span> <span data-ttu-id="5d5f3-119">Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-119">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="5d5f3-120">Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony profil użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-120">The "view details" link should be configured to redirect to the user profile page.</span></span>
- <span data-ttu-id="5d5f3-121">**Pozycja listy życzeń konta** — ten moduł służy do podania podsumowania towarów z listy życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-121">**Account wishlist item** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="5d5f3-122">Na przykład może to być stan, „na liście życzeń znajduje się 10 pozycji”.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-122">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="5d5f3-123">Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-123">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="5d5f3-124">Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony lista życzeń.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-124">The "view details" link should be configured to redirect to the wish list page.</span></span>
- <span data-ttu-id="5d5f3-125">**Element adresu konta** — ten moduł służy do podawania podsumowania adresu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-125">**Account address item** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="5d5f3-126">Na przykład może to być stan, „Dwa adresy dodane do konta”.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-126">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="5d5f3-127">Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły”.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-127">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="5d5f3-128">Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony adres użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-128">The "view details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="5d5f3-129">**Pozycja lojalnościowa** — ten moduł służy do wyświetlania informacji o programie lojalnościowym i łączenia ich z tymi informacjami.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-129">**Account loyalty item** – This module is used to show and link to loyalty program information.</span></span> <span data-ttu-id="5d5f3-130">Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły” i łącze „zostań członkiem”.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-130">It includes properties for the heading, the tile size, the "view details" link, and the "become a member" link.</span></span> <span data-ttu-id="5d5f3-131">Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony program lojalnościowy użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-131">The "view details" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="5d5f3-132">Łącze „stanie się członkiem” powinno być skonfigurowane tak, aby przekierowywać na stronę, na której użytkownicy mogą dołączać się do programu lojalnościowego.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-132">The "become a member" link should be configured to redirect to a page where users can join the loyalty program.</span></span>

### <a name="order-history-page"></a><span data-ttu-id="5d5f3-133">Strona historii zamówień</span><span class="sxs-lookup"><span data-stu-id="5d5f3-133">Order history page</span></span>

<span data-ttu-id="5d5f3-134">Strona historia zamówień korzysta z modułu historia zamówień w celu wyświetlenia wszystkich ostatnich zamówień złożonych przez tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-134">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="5d5f3-135">Strona szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="5d5f3-135">Order details page</span></span>

<span data-ttu-id="5d5f3-136">Strona szczegóły zamówienia zawiera szczegółowe informacje dotyczące poszczególnych zamówień i jest dostępna na stronie historia zamówień.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-136">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="5d5f3-137">Używa modułu szczegóły zamówienia, który wymaga identyfikatora sprzedaży lub identyfikatora transakcji w celu pobrania szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-137">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="5d5f3-138">Strona profil użytkownika</span><span class="sxs-lookup"><span data-stu-id="5d5f3-138">User profile page</span></span>

<span data-ttu-id="5d5f3-139">Na stronie profil użytkownika są wyświetlane szczegóły dotyczące konta użytkownika, takie jak nazwa użytkownika i adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-139">The user profile page shows user account details, such as user's name and email address.</span></span> <span data-ttu-id="5d5f3-140">Korzysta z niego moduł profilu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-140">It uses the user profile module.</span></span> <span data-ttu-id="5d5f3-141">Chociaż adresu e-mail nie da się usunąć, można go edytować.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-141">Although the email address can't be removed, it can be edited.</span></span>

### <a name="user-address-page"></a><span data-ttu-id="5d5f3-142">Strona adres e-mail użytkownika</span><span class="sxs-lookup"><span data-stu-id="5d5f3-142">User address page</span></span>

<span data-ttu-id="5d5f3-143">Na stronie adres użytkownika jest wyświetlana lista adresów skojarzonych z danym kontem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-143">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="5d5f3-144">Użytkownik albo dostarczył te adresy w trakcie realizacji transakcji, albo dodał je bezpośrednio na tej stronie.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-144">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="5d5f3-145">Używany jest moduł adres użytkownika służący do dodawania i edytowania adresów, ustawiania adresu podstawowego oraz renderowania istniejących adresów na stronie.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-145">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="5d5f3-146">Strona listy życzeń</span><span class="sxs-lookup"><span data-stu-id="5d5f3-146">Wish list page</span></span>

<span data-ttu-id="5d5f3-147">Na stronie listy życzeń są wyświetlane towary dodane do listy życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-147">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="5d5f3-148">Moduł listy życzeń używa do renderowania elementów listy życzeń.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-148">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="5d5f3-149">Strona lojalnościowa</span><span class="sxs-lookup"><span data-stu-id="5d5f3-149">Loyalty page</span></span>

<span data-ttu-id="5d5f3-150">Na stronie lojalnościowej odbiorcy można przyłączyć się do programu lojalnościowego lub, jeśli są już członkami programów lojalnościowych, wyświetlać szczegóły dotyczące programu.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-150">The loyalty page lets customers join a loyalty program or, if they are already loyalty program members, view their program details.</span></span> <span data-ttu-id="5d5f3-151">Mogą również wyświetlać punkty zdobyte i zrealizowane w ostatnich transakcjach.</span><span class="sxs-lookup"><span data-stu-id="5d5f3-151">They can also view the points that they have earned and redeemed in recent transactions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5d5f3-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5d5f3-152">Additional resources</span></span>

[<span data-ttu-id="5d5f3-153">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="5d5f3-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="5d5f3-154">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="5d5f3-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="5d5f3-155">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="5d5f3-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="5d5f3-156">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="5d5f3-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="5d5f3-157">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="5d5f3-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="5d5f3-158">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="5d5f3-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="5d5f3-159">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="5d5f3-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="5d5f3-160">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="5d5f3-160">Footer module</span></span>](author-footer-module.md)
