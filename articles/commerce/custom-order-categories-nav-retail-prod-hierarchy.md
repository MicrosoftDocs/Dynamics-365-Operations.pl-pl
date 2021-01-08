---
title: Zmiana porządku sortowania dla podmiotów merchandisingowych
description: W tym temacie objaśniono koncepcje związane z kontrolowaniem kolejności wyświetlania dla różnych jednostek związanych z merchandisingiem w Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b983cb5c63db171c76d34375a93a2b9086185d3a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414948"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a><span data-ttu-id="32d1a-103">Zmiana porządku sortowania dla podmiotów merchandisingowych</span><span class="sxs-lookup"><span data-stu-id="32d1a-103">Change the sort order for merchandising entities</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="32d1a-104">Detaliści uważają znajdowanie produktów za podstawowe narzędzie do wykrywania produktów na potrzeby interakcji z klientami we wszystkich kanałach.</span><span class="sxs-lookup"><span data-stu-id="32d1a-104">Retailers consider product discovery a primary tool for customer interaction across all channels.</span></span> <span data-ttu-id="32d1a-105">Klienci mogą łatwo odkrywać produkty, korzystając z różnych funkcji.</span><span class="sxs-lookup"><span data-stu-id="32d1a-105">Various functionality can help customers easily discover products.</span></span> <span data-ttu-id="32d1a-106">Na przykład mogą przeglądać kategorie, wyszukiwać i filtrować.</span><span class="sxs-lookup"><span data-stu-id="32d1a-106">For example, they can browse categories, search, and filter.</span></span>

<span data-ttu-id="32d1a-107">W tym temacie objaśniono koncepcje związane z kontrolowaniem kolejności wyświetlania dla różnych jednostek związanych z merchandisingiem.</span><span class="sxs-lookup"><span data-stu-id="32d1a-107">This topic explains the concepts that are related to controlling the display order for various merchandising-related entities.</span></span> <span data-ttu-id="32d1a-108">Omówiono również sposób zmieniania kolejności sortowania.</span><span class="sxs-lookup"><span data-stu-id="32d1a-108">It also explains how to change the sort order.</span></span>

## <a name="overview"></a><span data-ttu-id="32d1a-109">Przegląd</span><span class="sxs-lookup"><span data-stu-id="32d1a-109">Overview</span></span>

<span data-ttu-id="32d1a-110">Obsługa sortowania różnych jednostek dotyczących merchandisingu została ulepszona.</span><span class="sxs-lookup"><span data-stu-id="32d1a-110">The support for sorting various merchandising-related entities has been enhanced.</span></span> <span data-ttu-id="32d1a-111">Ta obsługa jest teraz lepiej wyrównana z istniejącymi scenariuszami klientów, które wcześniej wymagały rozszerzeń od partnerów implementacji.</span><span class="sxs-lookup"><span data-stu-id="32d1a-111">This support is now better aligned with existing customer scenarios that previously required extensions from implementation partners.</span></span>

<span data-ttu-id="32d1a-112">W wersjach Retail starszych niż wersja 10.0.5 kolejność sortowania kategorii w hierarchii nawigacji była alfabetyczna.</span><span class="sxs-lookup"><span data-stu-id="32d1a-112">In versions of Retail that are earlier than version 10.0.5, the sort order for categories in the navigation hierarchy was alphabetical.</span></span> <span data-ttu-id="32d1a-113">Nowa funkcja niestandardowej kolejności sortowania umożliwia menedżerom ds. merchadisingu konfigurowanie kolejności sortowania różnych jednostek związanych z merchandisingiem dla wszystkich klientów końcowych.</span><span class="sxs-lookup"><span data-stu-id="32d1a-113">The new custom sort order functionality lets merchandising managers configure the sort order for various merchandising-related entities across all end-user clients.</span></span> <span data-ttu-id="32d1a-114">Do tych klientów należą: Centrala (HQ) i biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="32d1a-114">These clients include headquarters (HQ) and call centers.</span></span>

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a><span data-ttu-id="32d1a-115">Skonfiguruj kolejność wyświetlania dla kategorii w hierarchii produktów</span><span class="sxs-lookup"><span data-stu-id="32d1a-115">Configure the display order for categories in the product hierarchy</span></span>

<span data-ttu-id="32d1a-116">Aby można było wykonać tę procedurę, w środowisku muszą być zainstalowane dane pokazowe.</span><span class="sxs-lookup"><span data-stu-id="32d1a-116">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="32d1a-117">Wybierz kolejno opcje **Retail i Commerce \> Produkty i kategorie \> Hierarchia produktów Commerce**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-117">Go to **Retail and Commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
2. <span data-ttu-id="32d1a-118">Kliknij opcję **Edytuj hierarchię kategorii**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-118">Click **Edit category hierarchy**.</span></span>
3. <span data-ttu-id="32d1a-119">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-119">Click **Edit**.</span></span>
4. <span data-ttu-id="32d1a-120">W drzewie rozwiń **WSZYSTKO \> Sporty akcji**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-120">In the tree, expand **ALL \> Action Sports**.</span></span>
5. <span data-ttu-id="32d1a-121">W drzewie rozwiń **WSZYSTKO \> Sporty drużynowe**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-121">In the tree, expand **ALL \> Team Sports**.</span></span>
6. <span data-ttu-id="32d1a-122">W polu **Kolejność wyświetlania** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="32d1a-122">In the **Display order** field, enter a number.</span></span> <span data-ttu-id="32d1a-123">(Liczba może być ujemna.)</span><span class="sxs-lookup"><span data-stu-id="32d1a-123">(The number can be negative.)</span></span>
7. <span data-ttu-id="32d1a-124">Powtórz kroki od 4 do 6 dla wszystkich dodatkowych kategorii, których kolejność chcesz zmienić.</span><span class="sxs-lookup"><span data-stu-id="32d1a-124">Repeat steps 4 through 6 for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="32d1a-125">Kolejność wyświetlania dla hierarchii nawigacji kanału zostanie odzwierciedlona w HQ dla hierarchii produktów handlu i zwolnionych produktów według kategorii.</span><span class="sxs-lookup"><span data-stu-id="32d1a-125">The display order for the channel navigation hierarchy will be reflected in HQ for the commerce product hierarchy and released products by category.</span></span>

![Hierarchia produktów niestandardowo posortowana z wartościami ujemnymi](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Zwolnione produkty według kategorii — sortowanie niestandardowe na podstawie hierarchii produktów](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a><span data-ttu-id="32d1a-128">Skonfiguruj kolejność wyświetlania dla kategorii w hierarchii kategorii nawigacji</span><span class="sxs-lookup"><span data-stu-id="32d1a-128">Configure the display order for categories in the channel navigation hierarchy</span></span>

<span data-ttu-id="32d1a-129">Aby można było wykonać tę procedurę, w środowisku muszą być zainstalowane dane pokazowe.</span><span class="sxs-lookup"><span data-stu-id="32d1a-129">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="32d1a-130">Przejdź do **Retail i Commerce \> Produkty i kategorie \> Kategorie nawigacji kanału**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-130">Go to **Retail and Commerce \> Products and categories \> Channel navigation categories**.</span></span>
2. <span data-ttu-id="32d1a-131">Z listy wybierz hierarchię **nawigacji Moda**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-131">In the list, select the **Fashion navigation** hierarchy.</span></span>
3. <span data-ttu-id="32d1a-132">Kliknij opcję **Edytuj hierarchię kategorii**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-132">Click **Edit category hierarchy**.</span></span>
4. <span data-ttu-id="32d1a-133">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-133">Click **Edit**.</span></span>
5. <span data-ttu-id="32d1a-134">W drzewie wybierz **Moda \> Moda damska \> Buty damskie**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-134">In the tree, select **Fashion \> Womenswear \> Womens Shoes**.</span></span>
6. <span data-ttu-id="32d1a-135">W polu **Kolejność wyświetlania** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="32d1a-135">In the **Display order** field, enter a number.</span></span>
7. <span data-ttu-id="32d1a-136">W drzewie wybierz **Moda \> Moda damska \> Bluzki**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-136">In the tree, select **Fashion \> Womenswear \> Tops**.</span></span>

    <span data-ttu-id="32d1a-137">Analogicznie, można określić kolejność sortowania dla podkategorii.</span><span class="sxs-lookup"><span data-stu-id="32d1a-137">Likewise, you can define the sort order for the sub-categories.</span></span>

8. <span data-ttu-id="32d1a-138">W drzewie wybierz **Moda \> Moda męska \> Koszule codzienne**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-138">In the tree, select **Fashion \> Menswear \> Casual Shirts**.</span></span>
9. <span data-ttu-id="32d1a-139">W polu **Kolejność wyświetlania** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="32d1a-139">In the **Display order** field, enter a number.</span></span>
10. <span data-ttu-id="32d1a-140">W drzewie wybierz **Moda \> Moda męska \> Płaszcze i kurtki**.</span><span class="sxs-lookup"><span data-stu-id="32d1a-140">In the tree, select **Fashion \> Menswear \> Coats & Jackets**.</span></span>
11. <span data-ttu-id="32d1a-141">W polu **Kolejność wyświetlania** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="32d1a-141">In the **Display order** field, enter a number.</span></span>
12. <span data-ttu-id="32d1a-142">Powtórz dla wszystkich dodatkowych kategorii, których kolejność chcesz zmienić.</span><span class="sxs-lookup"><span data-stu-id="32d1a-142">Repeat for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="32d1a-143">Kolejność wyświetlania dla hierarchii nawigacji kanału jest odzwierciedlona w HQ, katalogu i kanałach.</span><span class="sxs-lookup"><span data-stu-id="32d1a-143">The display order for the channel navigation hierarchy is reflected in HQ, catalog, and channels.</span></span>

![Niestandardowa hierarchia nawigacji kanału](./media/ChannelNavCustomSorted.png)

![Hierarchia nawigacji katalogu sortowanie niestandardowa na podstawie hierarchii nawigacji kanału](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![Punkt sprzedaży z niestandardowymi kategoriami posortowanymi](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> <span data-ttu-id="32d1a-147">Domyślnie ta funkcja niestandardowego sortowania jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="32d1a-147">By default the custom sort order feature is turned off.</span></span> <span data-ttu-id="32d1a-148">Aby dowiedzieć się, jak włączyć tę funkcję i inne funkcje, zobacz [Zarządzanie funkcjami](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="32d1a-148">To learn how to turn on this feature and other features, see [Feature management](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span></span>
