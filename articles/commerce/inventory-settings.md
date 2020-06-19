---
title: Zastosuj ustawienia zapasów
description: W tym temacie opisano ustawienia zapasów oraz sposób ich stosowania w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
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
ms.openlocfilehash: 7fc81c190806a0bdb50569f526589cfa1808ce0c
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417445"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="d500d-103">Zastosuj ustawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="d500d-103">Apply inventory settings</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="d500d-104">W tym temacie opisano ustawienia zapasów oraz sposób ich stosowania w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d500d-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d500d-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="d500d-105">Overview</span></span>

<span data-ttu-id="d500d-106">Ustawienia zapasów określają, czy zapasy powinny być sprawdzane przed dodaniem produktów do koszyka.</span><span class="sxs-lookup"><span data-stu-id="d500d-106">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="d500d-107">Definiują również komunikaty promocyjne dotyczące zapasów, takie jak „w magazynie” i „zostało tylko parę sztuk”.</span><span class="sxs-lookup"><span data-stu-id="d500d-107">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="d500d-108">Te ustawienia gwarantują, że produkt nie może zostać zakupiony, jeśli nie jest w stanie zapasów.</span><span class="sxs-lookup"><span data-stu-id="d500d-108">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="d500d-109">Dynamics 365 Commerce umożliwia oszacowanie dostępnych zapasów dla produktów.</span><span class="sxs-lookup"><span data-stu-id="d500d-109">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="d500d-110">Aby uzyskać informacje dotyczące sposobu obliczania szacowanej dostępności zapasów, należy zapoznać się z tematem [Oblicz dostępność zapasów dla kanałów sieci sprzedaży](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="d500d-110">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="d500d-111">W konstruktorze witryn Commerce można definiować progi i zakresy zapasów dla produktu lub kategorii.</span><span class="sxs-lookup"><span data-stu-id="d500d-111">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="d500d-112">Określają one, czy zapasy mogą być klasyfikowane jako w magazynie, małe ilości czy wyprzedane.</span><span class="sxs-lookup"><span data-stu-id="d500d-112">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="d500d-113">Aby uzyskać szczegółowe informacje, należy zapoznać się z tematem [Konfigurowanie buforów zapasów i poziomów zapasów](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d500d-113">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="d500d-114">Ustawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="d500d-114">Inventory settings</span></span>

<span data-ttu-id="d500d-115">W module Commerce ustawienia zapasów są definiowane w **Ustawienia witryny \> Rozszerzenia \> Zarządzanie zapasami** w konstruktorze witryn.</span><span class="sxs-lookup"><span data-stu-id="d500d-115">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="d500d-116">Istnieją cztery ustawienia zapasów, z których jedna jest przestarzała (przestarzałe):</span><span class="sxs-lookup"><span data-stu-id="d500d-116">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="d500d-117">**Włączanie sprawdzania zapasów w aplikacji** — to ustawienie powoduje włączenie sprawdzania zapasów produktów.</span><span class="sxs-lookup"><span data-stu-id="d500d-117">**Enable inventory check on app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="d500d-118">Pole zakupu, koszyk i pobieranie w modułach sklepów będą sprawdzać magazyn produktów i zezwalać na dodanie produktu do koszyka tylko wtedy, gdy zapasy są dostępne.</span><span class="sxs-lookup"><span data-stu-id="d500d-118">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="d500d-119">**Poziom zapasów na podstawie** — to ustawienie określa sposób obliczania poziomów zapasów.</span><span class="sxs-lookup"><span data-stu-id="d500d-119">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="d500d-120">Dostępne wartości to **Razem dostępne**, **Dostępne fizycznie** i **Próg wyprzedania**.</span><span class="sxs-lookup"><span data-stu-id="d500d-120">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="d500d-121">W Commerce można zdefiniować próg i zakresy zapasów dla każdego produktu i kategorii.</span><span class="sxs-lookup"><span data-stu-id="d500d-121">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="d500d-122">Interfejsy API magazynu zwracają informacje o zapasach produktów dla zarówno właściwości **Razem dostępne**, jak i właściwości **Fizycznie dostępne**.</span><span class="sxs-lookup"><span data-stu-id="d500d-122">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="d500d-123">Detalista decyduje, czy wartość **Razem dostępne** lub **Fizycznie dostępne** powinna być używana do określenia licznika zapasów i odpowiednich zakresów w Stanach zapasów i poza magazynem.</span><span class="sxs-lookup"><span data-stu-id="d500d-123">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="d500d-124">Wartość **Próg wyprzedania** ustawienia **Poziom zapasów na podstawie** jest starsza (przestarzała), nieaktualna.</span><span class="sxs-lookup"><span data-stu-id="d500d-124">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="d500d-125">Po wybraniu tej opcji Inwentaryzacja jest określana na podstawie wyników wartości **Razem dostępne**, ale próg jest definiowany przez ustawienie wartości liczbowej **Próg wyprzedania**, które zostało opisane w dalszej części tego pola.</span><span class="sxs-lookup"><span data-stu-id="d500d-125">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="d500d-126">To ustawienie progu ma zastosowanie w odniesieniu do wszystkich produktów w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="d500d-126">This threshold setting applies to all products across an e-Commerce site.</span></span> <span data-ttu-id="d500d-127">Jeśli zapasy są poniżej numeru progowego, produkt jest uważany za zapasy.</span><span class="sxs-lookup"><span data-stu-id="d500d-127">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="d500d-128">W przeciwnym razie zostanie uznane za dostępne w magazynie.</span><span class="sxs-lookup"><span data-stu-id="d500d-128">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="d500d-129">Możliwości wartości **Próg wyprzedania** są ograniczone i nie zaleca się używania jej w wersji 10.0.12 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="d500d-129">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="d500d-130">**Zakresy zapasów** — to ustawienie definiuje zakresy zapasów, które są wyświetlane w wiadomościach w modułach witryny.</span><span class="sxs-lookup"><span data-stu-id="d500d-130">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="d500d-131">Ma to zastosowanie tylko wtedy, gdy wybrano wartość **Razem Dostępne** lub **Dostępne Fizycznie** dla poziomu **Poziom zapasów w oparciu o ustawienie**.</span><span class="sxs-lookup"><span data-stu-id="d500d-131">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="d500d-132">Dostępne wartości to **Wszystkie**, **Mała ilość i wyprzedane** oraz **Wyprzedane**.</span><span class="sxs-lookup"><span data-stu-id="d500d-132">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="d500d-133">Po wybraniu opcji **Wszystkie** zostaną wyświetlone komunikaty dotyczące wszystkich zakresów magazynowych (komunikat dostępny) do wykroczenia zapasów (komunikat „wyprzedane”).</span><span class="sxs-lookup"><span data-stu-id="d500d-133">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="d500d-134">Po wybraniu opcji **Mała ilość i wyprzedane** zostaną wyświetlone komunikaty dotyczące wszystkich zakresów magazynowych poza zakresem dostępnym (komunikat „Dostępny”).</span><span class="sxs-lookup"><span data-stu-id="d500d-134">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="d500d-135">W przypadku wybrania **Wyprzedane** będzie wyświetlany tylko komunikat „wyprzedane”.</span><span class="sxs-lookup"><span data-stu-id="d500d-135">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="d500d-136">**Próg wyprzedania** — to stare ustawienie numeryczne zacznie obowiązywać tylko wtedy, gdy wartość **Próg wyprzedania** zostanie wybrana dla ustawienia **Poziom zapasów na podstawie**.</span><span class="sxs-lookup"><span data-stu-id="d500d-136">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="d500d-137">Moduły korzystające z ustawień zapasów</span><span class="sxs-lookup"><span data-stu-id="d500d-137">Modules that use inventory settings</span></span>

<span data-ttu-id="d500d-138">Pole Kup, Wishlist, selektor sklepu, koszyk i ikony koszyka Użyj ustawień zapasów, aby wyświetlić zakresy i komunikaty magazynowe.</span><span class="sxs-lookup"><span data-stu-id="d500d-138">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="d500d-139">Poniższy obraz przedstawia przykład strony ze szczegółowymi informacjami o produkcie (PDP), która pokazuje komunikat w magazynie („Dostępny”).</span><span class="sxs-lookup"><span data-stu-id="d500d-139">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Przykład modułu PDP, który ma komunikat w magazynie](./media/pdp-InStock.png)

<span data-ttu-id="d500d-141">Poniższy obraz pokazuje przykład PDP, który wyświetla komunikat „Wyprzedano”.</span><span class="sxs-lookup"><span data-stu-id="d500d-141">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Przykład modułu PDP, który ma komunikat o wyprzedaniu](./media/pdp-outofstock.png)

<span data-ttu-id="d500d-143">Poniższy obraz pokazuje przykład wózka z komunikatem o stanie magazynowym („Dostępne”).</span><span class="sxs-lookup"><span data-stu-id="d500d-143">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Przykład modułu koszyka, który ma komunikat w magazynie](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="d500d-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d500d-145">Additional resources</span></span>

[<span data-ttu-id="d500d-146">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="d500d-146">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d500d-147">Konfigurowanie buforów zapasów i poziomów zapasów</span><span class="sxs-lookup"><span data-stu-id="d500d-147">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="d500d-148">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="d500d-148">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="d500d-149">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="d500d-149">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="d500d-150">Strony i moduły zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="d500d-150">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="d500d-151">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="d500d-151">Store selector module</span></span>](store-selector.md)
