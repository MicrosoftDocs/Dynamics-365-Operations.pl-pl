---
title: Przegląd biblioteki modułów
description: W tym temacie omówiono bibliotekę modułów Microsoft Dynamics 365 Commerce.
author: anupamar-ms
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
ms.openlocfilehash: fcb0c2317315308de51d8247d23a930f10c3de6f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234300"
---
# <a name="module-library-overview"></a><span data-ttu-id="c3232-103">Przegląd biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="c3232-103">Module library overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c3232-104">W tym temacie omówiono bibliotekę modułów Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3232-104">This topic presents an overview of the Microsoft Dynamics 365 Commerce module library.</span></span>

<span data-ttu-id="c3232-105">Biblioteka modułów Dynamics 365 Commerce to zbiór modułów, za pomocą których można utworzyć witrynę sieci Web e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3232-105">The Dynamics 365 Commerce module library is a collection of modules that can be used to build an e-Commerce website.</span></span> <span data-ttu-id="c3232-106">Moduły mają aspekty interfejsu użytkownika (UI) i aspekty zachowania funkcjonalnego.</span><span class="sxs-lookup"><span data-stu-id="c3232-106">Modules have both user interface (UI) aspects and functional behavior aspects.</span></span>

<span data-ttu-id="c3232-107">Motywy mogą być stosowane do modułów w bibliotece modułów, aby zmieniać ich wygląd i działanie.</span><span class="sxs-lookup"><span data-stu-id="c3232-107">Themes can be applied to the modules in the module library to change their look and feel.</span></span> <span data-ttu-id="c3232-108">W motywach używane są kaskadowe arkusze stylów (CSS).</span><span class="sxs-lookup"><span data-stu-id="c3232-108">The themes use Cascading Style Sheets (CSS).</span></span> <span data-ttu-id="c3232-109">Motyw fikcyjnej witryny e-Commerce o nazwie „Fabrikam” jest dostarczany jako część biblioteki modułów i może być używany jako odwołanie.</span><span class="sxs-lookup"><span data-stu-id="c3232-109">A theme for a fictitious e-Commerce site that is named "Fabrikam" is provided as part of the module library and can be used as a reference.</span></span>

## <a name="module-library-modules"></a><span data-ttu-id="c3232-110">Moduły biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="c3232-110">Module library modules</span></span>

<span data-ttu-id="c3232-111">W bibliotece modułów są dostępne następujące typy modułów:</span><span class="sxs-lookup"><span data-stu-id="c3232-111">The following types of modules are provided in the module library:</span></span>

- <span data-ttu-id="c3232-112">**Moduł kontenerów** — moduł kontenerowy jest prostym modułem działającym jako host dla innych modułów.</span><span class="sxs-lookup"><span data-stu-id="c3232-112">**Container module** – A container module is a simple module that acts as a host for other modules.</span></span> <span data-ttu-id="c3232-113">Steruje on układem modułów znajdujących się wewnątrz tego modułu.</span><span class="sxs-lookup"><span data-stu-id="c3232-113">It controls the layout of the modules that are inside it.</span></span>
- <span data-ttu-id="c3232-114">**Moduły marketingowe** — moduły marketingowe: blok zawartości, blok tekstowy, odtwarzacz wideo i moduły karuzeli.</span><span class="sxs-lookup"><span data-stu-id="c3232-114">**Marketing modules** – Marketing modules include content block, text block, video player, and carousel modules.</span></span> <span data-ttu-id="c3232-115">Wszystkie te moduły mogą być używane do poprezentacji zawartości.</span><span class="sxs-lookup"><span data-stu-id="c3232-115">All these modules can be used to showcase content.</span></span> <span data-ttu-id="c3232-116">Można je umieścić na dowolnej stronie i są sterowane danymi z systemu zarządzania treścią (CMS).</span><span class="sxs-lookup"><span data-stu-id="c3232-116">They can be put on any page and are driven by data from the content management system (CMS).</span></span>
- <span data-ttu-id="c3232-117">**Moduły nagłówka i stopki** — moduły nagłówka i stopki są wyświetlane w nagłówku i stopce wszystkich stron witryny.</span><span class="sxs-lookup"><span data-stu-id="c3232-117">**Header and footer modules** – Header and footer modules appear in the header and footer of all site pages.</span></span> <span data-ttu-id="c3232-118">Moduły te można skonfigurować zgodnie z wymaganiami właściwości.</span><span class="sxs-lookup"><span data-stu-id="c3232-118">These modules can be configured as required through properties.</span></span>
- <span data-ttu-id="c3232-119">**Moduły wyszukiwania** — produkty można wykrywać za pomocą modułu wyszukiwania w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="c3232-119">**Search modules** – Products can be discovered by using the search module in the header.</span></span> <span data-ttu-id="c3232-120">Wyniki wyszukiwania zostaną wyświetlone na stronie wyników wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="c3232-120">Search results appear on the search results page.</span></span> <span data-ttu-id="c3232-121">Produkty można również wykryty na stronach kategorii, które są dedykowanymi stronami dla każdej kategorii obsługiwanej w hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="c3232-121">Products can also be discovered on category pages, which are dedicated pages for each category that is supported in the channel navigation hierarchy.</span></span> <span data-ttu-id="c3232-122">Ponadto moduły elementów uściślających mogą służyć do dalszego filtrowania wyników wyszukiwania i stron kategorii.</span><span class="sxs-lookup"><span data-stu-id="c3232-122">In addition, refiner modules can be used to further filter results on search results and category pages.</span></span>
- <span data-ttu-id="c3232-123">**Moduły strony Szczegóły produktu** — strony z informacjami o produktach używają kilku modułów do wyświetlania informacji o produktach.</span><span class="sxs-lookup"><span data-stu-id="c3232-123">**Product details page modules** – Product details pages use several modules to show product information.</span></span> <span data-ttu-id="c3232-124">Odbiorca modułu pola zakupu dla odbiorców umożliwia wyświetlenie produktów i dodanie ich do koszyka.</span><span class="sxs-lookup"><span data-stu-id="c3232-124">The buy box module lets customers view products and add them to the cart.</span></span> <span data-ttu-id="c3232-125">Inne moduły, takie jak moduł specyfikacji technicznej, zawierają szczegóły dotyczące produktu.</span><span class="sxs-lookup"><span data-stu-id="c3232-125">Other modules, such as the tech specs module, show the product details.</span></span> <span data-ttu-id="c3232-126">Moduł oceny i recenzje może służyć do wyświetlania i udostępniania recenzji.</span><span class="sxs-lookup"><span data-stu-id="c3232-126">The ratings and reviews module can used to view and provide reviews.</span></span>
- <span data-ttu-id="c3232-127">**Kupowanie w trybie online w module sklep** — funkcja kupowania w trybie online w module sklep jest zintegrowana z mapami Bing.</span><span class="sxs-lookup"><span data-stu-id="c3232-127">**Buy online pick up in store module** – The buy online pick up in store module is integrated with Bing Maps.</span></span> <span data-ttu-id="c3232-128">Może służyć do wyszukiwania pobliskich sklepów, w których klienci mogą odbierać produkty nabyte przez nich.</span><span class="sxs-lookup"><span data-stu-id="c3232-128">It can be used to find nearby stores where customers can pick up products that they have purchased.</span></span>
- <span data-ttu-id="c3232-129">**Moduły zakupu** — moduły zakupów zawierają moduł koszyka, który może być używany do dodawania towarów do koszyka.</span><span class="sxs-lookup"><span data-stu-id="c3232-129">**Purchase modules** – Purchase modules include the cart module, which can be used to add items to the cart.</span></span> <span data-ttu-id="c3232-130">Moduł realizacji transakcji zawiera adres wysyłkowy, opcje dostarczania oraz informacje o kartach upominkowych, programie lojalnościowym i karcie kredytowej, dzięki czemu można je przetwarzać.</span><span class="sxs-lookup"><span data-stu-id="c3232-130">The checkout module captures the shipping address, delivery options, and gift card, loyalty program, and credit card information, so that an order can be processed.</span></span> <span data-ttu-id="c3232-131">Po złożeniu zamówienia moduł potwierdzający zamówienie może być używany do wyświetlania szczegółów potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="c3232-131">After an order is placed, the order confirmation module can be used to show the confirmation details.</span></span>
- <span data-ttu-id="c3232-132">**Moduły zarządzania kontami** — odbiorcy mogą zalogować się do istniejącego konta, a moduł zapisywania się pozwala im utworzyć nowe konto.</span><span class="sxs-lookup"><span data-stu-id="c3232-132">**Account management modules** – The sign-in module lets customers sign in to an existing account, and the sign-up module lets them create a new account.</span></span> <span data-ttu-id="c3232-133">Po utworzeniu konta można użyć modułu historii zamówień w celu wyświetlenia ostatnich zamówień, a moduł szczegóły zamówienia może służyć do wyświetlania szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c3232-133">After an account is created, the order history module can be used to view recent orders, and the order details module can be used to view order details.</span></span>
- <span data-ttu-id="c3232-134">**Moduł rekomendacji** — rekomendacje są wyświetlane za pomocą modułu umieszczanie produktu.</span><span class="sxs-lookup"><span data-stu-id="c3232-134">**Recommendations module** – Recommendations are shown by using the product placement module.</span></span> <span data-ttu-id="c3232-135">Moduł ten obsługuje listy algorytmowe i redakcyjne, które można prezentować na dowolnej stronie.</span><span class="sxs-lookup"><span data-stu-id="c3232-135">This module supports algorithmic and editorial lists that can be showcased on any page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3232-136">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c3232-136">Additional resources</span></span>

[<span data-ttu-id="c3232-137">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="c3232-137">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="c3232-138">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="c3232-138">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="c3232-139">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="c3232-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c3232-140">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="c3232-140">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c3232-141">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="c3232-141">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="c3232-142">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="c3232-142">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="c3232-143">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="c3232-143">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]