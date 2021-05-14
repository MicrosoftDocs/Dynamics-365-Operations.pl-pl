---
title: Stosowanie ustawień jednostki miary
description: W tym temacie opisano ustawienia jednostki miary oraz sposób ich stosowania w systemie Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/23/2021
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
ms.openlocfilehash: 2c5750ae506978dfac842eebf4ba6036322bdd7f
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937611"
---
# <a name="apply-unit-of-measure-settings"></a><span data-ttu-id="8a48a-103">Stosowanie ustawień jednostki miary</span><span class="sxs-lookup"><span data-stu-id="8a48a-103">Apply unit of measure settings</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="8a48a-104">W tym temacie opisano ustawienia jednostki miary oraz sposób ich stosowania w systemie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8a48a-104">This topic covers unit of measure settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8a48a-105">Produkt może być sprzedawany w różnych jednostkach, na przykład „sztuka”, „para” i „tuzin”.</span><span class="sxs-lookup"><span data-stu-id="8a48a-105">A product can be sold in different units, such as "each," "pair," and "dozen."</span></span> <span data-ttu-id="8a48a-106">W centrali Commerce może być zdefiniowana jednostka miary sprzedaży dla produktu i pokazywana w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="8a48a-106">In Commerce headquarters, the sell-by unit of measure can be defined for a product and shown on an e-commerce site.</span></span> <span data-ttu-id="8a48a-107">Jeśli na przykład sprzedawca detaliczny sprzedaje produkt zarówno pojedynczo, jak i w tuzinach, dostępne jednostki miary mogą być pokazywane razem z innymi informacjami o produkcie.</span><span class="sxs-lookup"><span data-stu-id="8a48a-107">For example, if a retailer sells a product both individually and in dozens, the available units of measure can be shown together with other product information.</span></span>

<span data-ttu-id="8a48a-108">W przykładzie na poniższej ilustracji jednostka miary sprzedaży **szt.** (sztuka) została skonfigurowana dla produktu w centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="8a48a-108">In the example in the following illustration, a sell-by unit of measure of **ea** (each) has been configured for a product in Commerce headquarters.</span></span>

![Przykład produktu ze skonfigurowaną jednostką miary w centrali Commerce](./media/Productunit-headquarters.PNG)

> [!NOTE]
> <span data-ttu-id="8a48a-110">Obsługa stosowania i pokazywania jednostki miary jest dostępna od wersji 10.0.19 systemu Commerce.</span><span class="sxs-lookup"><span data-stu-id="8a48a-110">Support for applying and showing the unit of measure is available as of the Commerce version 10.0.19 release.</span></span>

## <a name="unit-of-measure-settings"></a><span data-ttu-id="8a48a-111">Ustawienia jednostki miary</span><span class="sxs-lookup"><span data-stu-id="8a48a-111">Unit of measure settings</span></span>

<span data-ttu-id="8a48a-112">Ustawienia wyświetlania jednostki miary są definiowane w konstruktorze witryn Commerce, na ekranie **Ustawienia witryny \> Rozszerzenia \> Wyświetl jednostkę miary produktów**.</span><span class="sxs-lookup"><span data-stu-id="8a48a-112">Unit of measure display settings are defined in Commerce site builder, at **Site settings \> Extensions \> Display unit of measure for products**.</span></span> <span data-ttu-id="8a48a-113">Dostępne są trzy obsługiwane ustawienia:</span><span class="sxs-lookup"><span data-stu-id="8a48a-113">There are three supported settings:</span></span>

- <span data-ttu-id="8a48a-114">**Nie wyświetlaj** — po wybraniu tego ustawienia witryna handlu elektronicznego nie będzie wyświetlać jednostki miary produktu.</span><span class="sxs-lookup"><span data-stu-id="8a48a-114">**Do not display** – When this setting is selected, the e-commerce site won't show the unit of measure for the product.</span></span> <span data-ttu-id="8a48a-115">To zachowanie jest zachowaniem domyślnym.</span><span class="sxs-lookup"><span data-stu-id="8a48a-115">This behavior is the default behavior.</span></span>
- <span data-ttu-id="8a48a-116">**Wyświetl podczas kupowania produktu** — gdy to ustawienie jest zaznaczone, jednostka miary jest wyświetlana na stronach szczegółów produktu, koszyka, realizacji zamówienia, historii zamówień i szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8a48a-116">**Display in the product buying experience** – When this setting is selected, the unit of measure is shown on product details, cart, checkout, order history, and order details pages.</span></span>
- <span data-ttu-id="8a48a-117">**Wyświetl podczas przeglądania i kupowania produktu** — gdy to ustawienie jest zaznaczone, jednostka miary jest wyświetlana podczas kupowania produktów, a także podczas przeglądania produktów.</span><span class="sxs-lookup"><span data-stu-id="8a48a-117">**Display in the product browsing and buying experience** – When this setting is selected, the unit of measure is shown on the product buying experience pages and also during the product browsing experience.</span></span> <span data-ttu-id="8a48a-118">W ramach tego zachowania jednostki miary są pokazywane w wynikach wyszukiwania i modułach kolekcji produktów.</span><span class="sxs-lookup"><span data-stu-id="8a48a-118">As part of this behavior, units of measure are shown in search results and product collection modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a48a-119">Ustawienia wyświetlania jednostek miary są dostępne od wersji 10.0.19 systemu Commerce.</span><span class="sxs-lookup"><span data-stu-id="8a48a-119">Unit of measure display settings are available as of the Commerce version 10.0.19 release.</span></span> <span data-ttu-id="8a48a-120">W przypadku aktualizacji ze starszej wersji Commerce należy ręcznie zaktualizować plik appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="8a48a-120">If you're updating from an older version of Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="8a48a-121">Aby uzyskać instrukcje, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="8a48a-121">For instructions, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-unit-of-measure-settings"></a><span data-ttu-id="8a48a-122">Moduły korzystające z ustawień jednostki miary</span><span class="sxs-lookup"><span data-stu-id="8a48a-122">Modules that use unit of measure settings</span></span>

<span data-ttu-id="8a48a-123">Moduły, w których są używane ustawienia jednostki miary, to między innymi pole zakupu, lista życzeń, ikona koszyka, ikona koszyka, kontener wyników wyszukiwania, kolekcja produktów, realizacja zamówienia i szczegóły zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8a48a-123">Modules that use the unit of measure settings include the buy box, wishlist, cart, cart icon, search results container, product collection, checkout, and order details modules.</span></span>

<span data-ttu-id="8a48a-124">Na przykładzie na poniższej ilustracji na stronie szczegółów produktu (PDP) jest pokazana jednostka miary (**szt.**) produktu.</span><span class="sxs-lookup"><span data-stu-id="8a48a-124">In the example in the following illustration, a product details page (PDP) shows the unit of measure (**ea**) for a product.</span></span>

![Przykład PDP z jednostką miary](./media/Productunit-PDP.png)

<span data-ttu-id="8a48a-126">Na przykładzie na poniższej ilustracji w module kolekcji produktów jest pokazana jednostka miary (**szt.**) produktu.</span><span class="sxs-lookup"><span data-stu-id="8a48a-126">In the example in the following illustration, a product collection module shows the unit of measure (**ea**) for a product.</span></span>

![Przykład modułu kolekcji produktów z jednostką miary](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a><span data-ttu-id="8a48a-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8a48a-128">Additional resources</span></span>

[<span data-ttu-id="8a48a-129">Przegląd biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="8a48a-129">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8a48a-130">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="8a48a-130">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="8a48a-131">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="8a48a-131">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8a48a-132">Strony i moduły zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="8a48a-132">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="8a48a-133">Aktualizacje zestawu SDK i biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="8a48a-133">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
