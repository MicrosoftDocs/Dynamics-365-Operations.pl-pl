---
title: Zastosuj ustawienia zapasów
description: W tym temacie opisano ustawienia zapasów oraz sposób ich stosowania w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: d7d25fd62efca52dd2d60ed3435104c3507a1d19
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817616"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="4d6ef-103">Zastosuj ustawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="4d6ef-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4d6ef-104">W tym temacie opisano ustawienia zapasów oraz sposób ich stosowania w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4d6ef-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="4d6ef-105">Overview</span></span>

<span data-ttu-id="4d6ef-106">Ustawienia zapasów określają, czy zapasy powinny być sprawdzane przed dodaniem produktów do koszyka.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-106">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="4d6ef-107">Definiują również komunikaty promocyjne dotyczące zapasów, takie jak „w magazynie” i „zostało tylko parę sztuk”.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-107">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="4d6ef-108">Te ustawienia gwarantują, że produkt nie może zostać zakupiony, jeśli nie jest w stanie zapasów.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-108">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="4d6ef-109">Dynamics 365 Commerce umożliwia oszacowanie dostępnych zapasów dla produktów.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-109">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="4d6ef-110">Aby uzyskać informacje dotyczące sposobu obliczania szacowanej dostępności zapasów, należy zapoznać się z tematem [Oblicz dostępność zapasów dla kanałów sieci sprzedaży](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="4d6ef-110">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="4d6ef-111">W konstruktorze witryn Commerce można definiować progi i zakresy zapasów dla produktu lub kategorii.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-111">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="4d6ef-112">Określają one, czy zapasy mogą być klasyfikowane jako w magazynie, małe ilości czy wyprzedane.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-112">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="4d6ef-113">Aby uzyskać szczegółowe informacje, należy zapoznać się z tematem [Konfigurowanie buforów zapasów i poziomów zapasów](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4d6ef-113">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4d6ef-114">Obsługa progów i zakresów zapasów jest dostępna w wersji Dynamics 365 Commerce 10.0.12.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-114">Support for inventory thresholds and ranges is available in the Dynamics 365 Commerce 10.0.12 release.</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="4d6ef-115">Ustawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="4d6ef-115">Inventory settings</span></span>

<span data-ttu-id="4d6ef-116">W module Commerce ustawienia zapasów są definiowane w **Ustawienia witryny \> Rozszerzenia \> Zarządzanie zapasami** w konstruktorze witryn.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-116">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="4d6ef-117">Istnieją cztery ustawienia zapasów, z których jedna jest przestarzała (przestarzałe):</span><span class="sxs-lookup"><span data-stu-id="4d6ef-117">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="4d6ef-118">**Włączanie sprawdzania zapasów w aplikacji** — to ustawienie powoduje włączenie sprawdzania zapasów produktów.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-118">**Enable inventory check on app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="4d6ef-119">Pole zakupu, koszyk i pobieranie w modułach sklepów będą sprawdzać magazyn produktów i zezwalać na dodanie produktu do koszyka tylko wtedy, gdy zapasy są dostępne.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-119">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="4d6ef-120">**Poziom zapasów na podstawie** — to ustawienie określa sposób obliczania poziomów zapasów.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-120">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="4d6ef-121">Dostępne wartości to **Razem dostępne**, **Dostępne fizycznie** i **Próg wyprzedania**.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-121">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="4d6ef-122">W Commerce można zdefiniować próg i zakresy zapasów dla każdego produktu i kategorii.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-122">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="4d6ef-123">Interfejsy API magazynu zwracają informacje o zapasach produktów dla zarówno właściwości **Razem dostępne**, jak i właściwości **Fizycznie dostępne**.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-123">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="4d6ef-124">Detalista decyduje, czy wartość **Razem dostępne** lub **Fizycznie dostępne** powinna być używana do określenia licznika zapasów i odpowiednich zakresów w Stanach zapasów i poza magazynem.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-124">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="4d6ef-125">Wartość **Próg wyprzedania** ustawienia **Poziom zapasów na podstawie** jest starsza (przestarzała), nieaktualna.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-125">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="4d6ef-126">Po wybraniu tej opcji Inwentaryzacja jest określana na podstawie wyników wartości **Razem dostępne**, ale próg jest definiowany przez ustawienie wartości liczbowej **Próg wyprzedania**, które zostało opisane w dalszej części tego pola.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-126">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="4d6ef-127">To ustawienie progu ma zastosowanie w odniesieniu do wszystkich produktów w witrynie handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-127">This threshold setting applies to all products across an e-Commerce site.</span></span> <span data-ttu-id="4d6ef-128">Jeśli zapasy są poniżej numeru progowego, produkt jest uważany za zapasy.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-128">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="4d6ef-129">W przeciwnym razie zostanie uznane za dostępne w magazynie.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-129">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="4d6ef-130">Możliwości wartości **Próg wyprzedania** są ograniczone i nie zaleca się używania jej w wersji 10.0.12 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-130">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="4d6ef-131">**Zakresy zapasów** — to ustawienie definiuje zakresy zapasów, które są wyświetlane w wiadomościach w modułach witryny.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-131">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="4d6ef-132">Ma to zastosowanie tylko wtedy, gdy wybrano wartość **Razem Dostępne** lub **Dostępne Fizycznie** dla poziomu **Poziom zapasów w oparciu o ustawienie**.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-132">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="4d6ef-133">Dostępne wartości to **Wszystkie**, **Mała ilość i wyprzedane** oraz **Wyprzedane**.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-133">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="4d6ef-134">Po wybraniu opcji **Wszystkie** zostaną wyświetlone komunikaty dotyczące wszystkich zakresów magazynowych (komunikat dostępny) do wykroczenia zapasów (komunikat „wyprzedane”).</span><span class="sxs-lookup"><span data-stu-id="4d6ef-134">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="4d6ef-135">Po wybraniu opcji **Mała ilość i wyprzedane** zostaną wyświetlone komunikaty dotyczące wszystkich zakresów magazynowych poza zakresem dostępnym (komunikat „Dostępny”).</span><span class="sxs-lookup"><span data-stu-id="4d6ef-135">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="4d6ef-136">W przypadku wybrania **Wyprzedane** będzie wyświetlany tylko komunikat „wyprzedane”.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-136">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="4d6ef-137">**Próg wyprzedania** — to stare ustawienie numeryczne zacznie obowiązywać tylko wtedy, gdy wartość **Próg wyprzedania** zostanie wybrana dla ustawienia **Poziom zapasów na podstawie**.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-137">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="4d6ef-138">Te ustawienia są dostępne w wydaniu Dynamics 365 Commerce 10.0.12.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-138">These settings are available in the Dynamics 365 Commerce 10.0.12 release.</span></span> <span data-ttu-id="4d6ef-139">W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-139">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="4d6ef-140">Aby uzyskać instrukcje dotyczące aktualizowania pliku appsettings.json, zajrzyj do [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="4d6ef-140">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="4d6ef-141">Moduły korzystające z ustawień zapasów</span><span class="sxs-lookup"><span data-stu-id="4d6ef-141">Modules that use inventory settings</span></span>

<span data-ttu-id="4d6ef-142">Pole Kup, Wishlist, selektor sklepu, koszyk i ikony koszyka Użyj ustawień zapasów, aby wyświetlić zakresy i komunikaty magazynowe.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-142">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="4d6ef-143">Poniższy obraz przedstawia przykład strony ze szczegółowymi informacjami o produkcie (PDP), która pokazuje komunikat w magazynie („Dostępny”).</span><span class="sxs-lookup"><span data-stu-id="4d6ef-143">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Przykład modułu PDP, który ma komunikat w magazynie](./media/pdp-InStock.png)

<span data-ttu-id="4d6ef-145">Poniższy obraz pokazuje przykład PDP, który wyświetla komunikat „Wyprzedano”.</span><span class="sxs-lookup"><span data-stu-id="4d6ef-145">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Przykład modułu PDP, który ma komunikat o wyprzedaniu](./media/pdp-outofstock.png)

<span data-ttu-id="4d6ef-147">Poniższy obraz pokazuje przykład wózka z komunikatem o stanie magazynowym („Dostępne”).</span><span class="sxs-lookup"><span data-stu-id="4d6ef-147">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Przykład modułu koszyka, który ma komunikat w magazynie](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="4d6ef-149">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4d6ef-149">Additional resources</span></span>

[<span data-ttu-id="4d6ef-150">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="4d6ef-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4d6ef-151">Konfigurowanie buforów zapasów i poziomów zapasów</span><span class="sxs-lookup"><span data-stu-id="4d6ef-151">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="4d6ef-152">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="4d6ef-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="4d6ef-153">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="4d6ef-153">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="4d6ef-154">Strony i moduły zarządzania kontem</span><span class="sxs-lookup"><span data-stu-id="4d6ef-154">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="4d6ef-155">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="4d6ef-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="4d6ef-156">Aktualizacje zestawu SDK i biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="4d6ef-156">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
