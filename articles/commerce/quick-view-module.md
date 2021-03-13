---
title: Moduł szybkiego podglądu
description: W tym temacie omówiono moduły szybkiego podglądu i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 7e8244a06c515029b559b2061d9a25c7355e9e14
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097059"
---
# <a name="quick-view-module"></a><span data-ttu-id="109de-103">Moduł szybkiego podglądu</span><span class="sxs-lookup"><span data-stu-id="109de-103">Quick view module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="109de-104">W tym temacie omówiono moduły szybkiego podglądu i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="109de-104">This topic covers quick view modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="109de-105">Moduł szybkiego podglądu pozwala użytkownikom szybko przeglądać informacje o produkcie podczas przeglądania produktów na stronie listy i dodawać jeden lub więcej produktów do koszyka ze strony listy, bez konieczności przechodzenia do strony szczegółów produktu (PDP).</span><span class="sxs-lookup"><span data-stu-id="109de-105">The quick view module lets users quickly view product information when they browse products on a list page, and add one or more products to the cart from the list page, without having to go to the product details page (PDP).</span></span> <span data-ttu-id="109de-106">Moduł szybkiego podglądu zapewnia przegląd informacji o produkcie, których użytkownicy potrzebują, aby podjąć decyzję „dodaj do koszyka”.</span><span class="sxs-lookup"><span data-stu-id="109de-106">The quick view module provides an overview of the product information that users require to make an "add to cart" decision.</span></span> <span data-ttu-id="109de-107">Zapewnia również łącze do PDP, dzięki czemu użytkownicy mogą przeglądać dodatkowe szczegóły produktu i opcje zakupu.</span><span class="sxs-lookup"><span data-stu-id="109de-107">It also provides a link to the PDP, so that users can view additional product details and purchase options.</span></span>

<span data-ttu-id="109de-108">Moduł szybkiego widoku jest obsługiwany przez [moduły kolekcji produktów](product-collection-module-overview.md) i [wyników wyszukiwania](search-result-module.md).</span><span class="sxs-lookup"><span data-stu-id="109de-108">The quick view module is supported by the [product collection](product-collection-module-overview.md) and [search results](search-result-module.md) modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="109de-109">Moduł szybkiego podglądu jest dostępny od wersji Commerce 10.0.17.</span><span class="sxs-lookup"><span data-stu-id="109de-109">The quick view module is available as of the Commerce version 10.0.17 release.</span></span>

<span data-ttu-id="109de-110">Poniższa ilustracja przedstawia przykład modułu szybkiego podglądu na stronie listy produktów.</span><span class="sxs-lookup"><span data-stu-id="109de-110">The following illustration shows an example of a quick view module on a product list page.</span></span>

![Przykład modułu szybkiego podglądu na stronie listy produktów](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a><span data-ttu-id="109de-112">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="109de-112">Module properties</span></span>

<span data-ttu-id="109de-113">Moduł szybkiego podglądu obsługuje niektóre z tych samych funkcji, co moduł pola zakupu.</span><span class="sxs-lookup"><span data-stu-id="109de-113">The quick view module supports some of the same functions as the buy box module.</span></span> <span data-ttu-id="109de-114">Z tego względu właściwości modułu szybkiego widoku przypominają właściwości modułu pola zakupu.</span><span class="sxs-lookup"><span data-stu-id="109de-114">Therefore, the properties of a quick view module resemble the properties of a buy box module.</span></span>

| <span data-ttu-id="109de-115">Właściwość</span><span class="sxs-lookup"><span data-stu-id="109de-115">Property</span></span> | <span data-ttu-id="109de-116">Wartości</span><span class="sxs-lookup"><span data-stu-id="109de-116">Values</span></span> | <span data-ttu-id="109de-117">opis</span><span class="sxs-lookup"><span data-stu-id="109de-117">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="109de-118">Znacznik nagłówka</span><span class="sxs-lookup"><span data-stu-id="109de-118">Heading tag</span></span> | <span data-ttu-id="109de-119">**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**</span><span class="sxs-lookup"><span data-stu-id="109de-119">**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**</span></span> | <span data-ttu-id="109de-120">Ta właściwość definiuje znacznik nagłówka dla produktu.</span><span class="sxs-lookup"><span data-stu-id="109de-120">This property defines the heading tag for the product title.</span></span> <span data-ttu-id="109de-121">Jeśli moduł szybkiego podglądu znajduje się u góry strony, ta właściwość powinna być ustawiona na **H1**, aby spełnić standardy dostępności.</span><span class="sxs-lookup"><span data-stu-id="109de-121">If the quick view module is at the top of the page, this property should be set to **H1** to meet accessibility standards.</span></span> |
| <span data-ttu-id="109de-122">Zezwalaj na cenę niestandardową</span><span class="sxs-lookup"><span data-stu-id="109de-122">Allow custom price</span></span> | <span data-ttu-id="109de-123">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="109de-123">**True** or **False**</span></span> | <span data-ttu-id="109de-124">Jeśli właściwość ma wartość **True**, użytkownik może wprowadzić cenę niestandardową.</span><span class="sxs-lookup"><span data-stu-id="109de-124">If this property is set to **True**, the user can enter a custom price.</span></span> |
| <span data-ttu-id="109de-125">Cena minimalna</span><span class="sxs-lookup"><span data-stu-id="109de-125">Minimum price</span></span> | <span data-ttu-id="109de-126">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="109de-126">Integer</span></span> | <span data-ttu-id="109de-127">Ta właściwość ma zastosowanie tylko w przypadku, gdy właściwość **Zezwalaj na cenę niestandardową** ma wartość **True**.</span><span class="sxs-lookup"><span data-stu-id="109de-127">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="109de-128">Określa minimalną cenę, jaką użytkownik może wprowadzić (na przykład $1).</span><span class="sxs-lookup"><span data-stu-id="109de-128">It defines the minimum price that the user can enter (for example, $1).</span></span> |
| <span data-ttu-id="109de-129">Cena maksymalna</span><span class="sxs-lookup"><span data-stu-id="109de-129">Maximum price</span></span> | <span data-ttu-id="109de-130">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="109de-130">Integer</span></span> | <span data-ttu-id="109de-131">Ta właściwość ma zastosowanie tylko w przypadku, gdy właściwość **Zezwalaj na cenę niestandardową** ma wartość **True**.</span><span class="sxs-lookup"><span data-stu-id="109de-131">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="109de-132">Określa maksymalną cenę, jaką użytkownik może wprowadzić (na przykład $1,000).</span><span class="sxs-lookup"><span data-stu-id="109de-132">It defines the maximum price that the user can enter (for example, $1,000).</span></span> |

## <a name="commerce-site-builder-settings"></a><span data-ttu-id="109de-133">Ustawienia konstruktora witryn</span><span class="sxs-lookup"><span data-stu-id="109de-133">Commerce site builder settings</span></span>

<span data-ttu-id="109de-134">Podobnie jak moduł pola zakupu, moduł szybkiego wyświetlania respektuje ustawienia w **Ustawienia witryny \> Rozszerzenia \> Dodaj produkt do koszyka**.</span><span class="sxs-lookup"><span data-stu-id="109de-134">Like the buy box module, the quick view module respects the settings at **Site Settings \> Extensions \> Add product to cart**.</span></span> <span data-ttu-id="109de-135">Jednak ustawienie **Przejdź do strony koszyka** jest ignorowane, ponieważ jest niezgodne z celem modułu szybkiego podglądu, którym jest umożliwienie użytkownikom przeglądania wielu produktów na stronie listy i dodawania ich do koszyka bez opuszczania strony z listą.</span><span class="sxs-lookup"><span data-stu-id="109de-135">However, the **Navigate to cart page** setting is ignored, because it's inconsistent with the purpose of the quick view module, which is to enable users to browse multiple products on a list page and add them to the cart without moving away from the list page.</span></span>

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a><span data-ttu-id="109de-136">Dodaj moduł szybkiego podglądu do modułu kolekcji produktów</span><span class="sxs-lookup"><span data-stu-id="109de-136">Add a quick view module to a product collection module</span></span>

<span data-ttu-id="109de-137">Do kolekcji produktów i modułów wyników wyszukiwania można dodać moduł szybkiego podglądu.</span><span class="sxs-lookup"><span data-stu-id="109de-137">A quick view module can be added to the product collection and search results modules.</span></span>

<span data-ttu-id="109de-138">Aby dodać moduł szybkiego podglądu do modułu kolekcji produktów w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="109de-138">To add a quick view module to a product collection module in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="109de-139">Przejdź do **Strony**, a następnie wybierz stronę główną witryny Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="109de-139">Go to **Pages**, and then select the home page for the Fabrikam site.</span></span>
1. <span data-ttu-id="109de-140">Przejdź do dowolnego modułu **Kolekcji produktów** na stronie głównej, wybierz wielokropek (**...**), a następnie wybierz opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="109de-140">Go to any **Product Collection** module on the homepage, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="109de-141">W oknie dialogowym **Dodaj moduł** wybierz moduł **Szybkiego podglądu** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="109de-141">In the **Add Module** dialog box, select the **Quick View** module, and then select **OK**.</span></span>
1. <span data-ttu-id="109de-142">W okienku właściwości modułu **Szybki podgląd** wybierz pozycję **Nagłówek**.</span><span class="sxs-lookup"><span data-stu-id="109de-142">In the properties pane of the **Quick View** module, select **Heading**.</span></span> <span data-ttu-id="109de-143">W oknie dialogowym **Nagłówek** ustaw w polu **Poziom nagłówka** wartość **H2**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="109de-143">In the **Heading** dialog box, set the **Heading Level** field to **H2**, and then select **OK**.</span></span>
1. <span data-ttu-id="109de-144">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="109de-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="109de-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="109de-145">Additional resources</span></span>

[<span data-ttu-id="109de-146">Przegląd biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="109de-146">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="109de-147">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="109de-147">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="109de-148">Moduł kolekcji produktów</span><span class="sxs-lookup"><span data-stu-id="109de-148">Product collection module</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="109de-149">Moduł wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="109de-149">Search results module</span></span>](search-result-module.md)
