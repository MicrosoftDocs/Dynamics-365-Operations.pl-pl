---
title: Wymiary produktu
description: Istnieją cztery wymiary produktu — Kolor, Konfiguracja, Rozmiar i Styl. Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych. Kombinacje wymiarów produktu decydują o definicjach wariantów produktu.
author: cvocph
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3391679696c0e1dd84840821480ccbfb544829a6
ms.sourcegitcommit: d0fa8d0140fa81029527edb317623c1a7737c593
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863043"
---
# <a name="product-dimensions"></a><span data-ttu-id="aafae-105">Wymiary produktu</span><span class="sxs-lookup"><span data-stu-id="aafae-105">Product dimensions</span></span>

[!include [banner](../includes/banner.md)]

[!include [Retail name](../includes/retail-name.md)]

<span data-ttu-id="aafae-106">Istnieją cztery wymiary produktu — Kolor, Konfiguracja, Rozmiar i Styl.</span><span class="sxs-lookup"><span data-stu-id="aafae-106">There are four product dimensions -  Color, Configuration, Size and Style.</span></span> <span data-ttu-id="aafae-107">Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych.</span><span class="sxs-lookup"><span data-stu-id="aafae-107">You combine product dimensions in dimension groups and assign dimension groups to product masters.</span></span> <span data-ttu-id="aafae-108">Kombinacje wymiarów produktu decydują o definicjach wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="aafae-108">The combinations of product dimensions determine how product variants are defined.</span></span>

<span data-ttu-id="aafae-109">Wymiary produktu to cechy, które służą do określenia wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="aafae-109">Product dimensions are characteristics that serve to identify a product variant.</span></span> <span data-ttu-id="aafae-110">Kombinacje wymiarów produktu służą do definiowania wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="aafae-110">You can use combinations of product dimensions to define product variants.</span></span> <span data-ttu-id="aafae-111">Należy zdefiniować co najmniej jeden wymiar produktu dla produktu głównego w celu utworzenia wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="aafae-111">You must define at least one product dimension for a product master in order to create a product variant.</span></span>

## <a name="product-variants"></a><span data-ttu-id="aafae-112">Warianty produktu</span><span class="sxs-lookup"><span data-stu-id="aafae-112">Product variants</span></span>

<span data-ttu-id="aafae-113">Warianty produktu są również określane jako elementy.</span><span class="sxs-lookup"><span data-stu-id="aafae-113">Product variants are also referred to as items.</span></span> <span data-ttu-id="aafae-114">Towar to produkt materialny, który nie jest usługą.</span><span class="sxs-lookup"><span data-stu-id="aafae-114">An item is a tangible product, which is not the same as a service.</span></span> <span data-ttu-id="aafae-115">Istnieje również możliwość zdefiniowania produktu głównego typu Usługa.</span><span class="sxs-lookup"><span data-stu-id="aafae-115">It is also possible to define a product master with the Service type.</span></span> <span data-ttu-id="aafae-116">Za pomocą typu Usługa można określić warianty produktu, które zawierają usługi.</span><span class="sxs-lookup"><span data-stu-id="aafae-116">By using the Service type, you can specify product variants that include services.</span></span> <span data-ttu-id="aafae-117">Na przykład można określić produkt główny dla pracy w zakresie doradztwa i warianty produktu dla pracy wykonywanej przez starszych konsultantów i młodszych konsultantów.</span><span class="sxs-lookup"><span data-stu-id="aafae-117">For example, you can specify a product master for Consultancy work and product variants for work that is performed by senior consultants and junior consultants.</span></span>

## <a name="product-dimensions"></a><span data-ttu-id="aafae-118">Wymiary produktu</span><span class="sxs-lookup"><span data-stu-id="aafae-118">Product dimensions</span></span>
<span data-ttu-id="aafae-119">Dostępne są następujące wymiary produktu: Konfiguracja, Kolor, Rozmiar i Styl.</span><span class="sxs-lookup"><span data-stu-id="aafae-119">The following product dimensions are available: Configuration, Color, Size, and Style.</span></span> <span data-ttu-id="aafae-120">Wariant produktu może być generowany na podstawie wartości w wymiarach produktu.</span><span class="sxs-lookup"><span data-stu-id="aafae-120">A product variant can be generated based on the product dimension values.</span></span>

<span data-ttu-id="aafae-121">Wartości wymiarów produktu, takie jak Rozmiar, Kolor i Styl, można tworzyć na stronach **Rozmiar**, **Kolor** i **Styl**, które można otworzyć z następujących lokalizacji: **Zarządzanie informacjami o produktach** &gt; **Ustawienia** &gt; **Grupy wymiarów i wariantów** &gt; **Rozmiary/Kolory/Style**.</span><span class="sxs-lookup"><span data-stu-id="aafae-121">Product dimensions values such as Size, Color and Style can be created on the **Size**, **Color** and **Style** pages, which can be accessed from the following locations: **Product information management** &gt; **Setup** &gt; **Dimension and variant Groups** &gt; **Sizes/Colors/Styles**.</span></span> <span data-ttu-id="aafae-122">Wartości wymiaru produktu dla wymiaru konfiguracji są zwykle tworzone za pomocą konfiguratora produktów lub konfiguratora opartego na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="aafae-122">Product dimension values for the Configuration dimension are typically created using either the Product configurator or the Dimension-based configurator.</span></span> <span data-ttu-id="aafae-123">Wymiary produktu mogą być również tworzone i obsługiwane na stronie **Wymiary produktu**, która jest dostępna z następujących miejsc:</span><span class="sxs-lookup"><span data-stu-id="aafae-123">Product dimensions can also be created and maintained on the **Product dimensions** page, which can be accessed from the following locations:</span></span>
-   <span data-ttu-id="aafae-124">Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Produkty** &gt; **Produkty główne**.</span><span class="sxs-lookup"><span data-stu-id="aafae-124">Click **Product information management** &gt; **Products** &gt; **Product masters**.</span></span> <span data-ttu-id="aafae-125">W **okienku akcji** kliknij pozycję **Wymiary produktu**.</span><span class="sxs-lookup"><span data-stu-id="aafae-125">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="aafae-126">Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Produkty** &gt; **Wszystkie produkty i produkty główne**.</span><span class="sxs-lookup"><span data-stu-id="aafae-126">Click **Product information management** &gt; **Products** &gt; **All products and product masters**.</span></span> <span data-ttu-id="aafae-127">Wybierz produkt główny.</span><span class="sxs-lookup"><span data-stu-id="aafae-127">Select a product master.</span></span> <span data-ttu-id="aafae-128">W **okienku akcji** kliknij pozycję **Wymiary produktu**.</span><span class="sxs-lookup"><span data-stu-id="aafae-128">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="aafae-129">Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="aafae-129">Click **Product information management** &gt; **Released products**.</span></span> <span data-ttu-id="aafae-130">Wybierz produkt główny.</span><span class="sxs-lookup"><span data-stu-id="aafae-130">Select a product master.</span></span> <span data-ttu-id="aafae-131">W **okienku akcji** kliknij pozycję **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="aafae-131">On the **Action Pane**, click **Product**.</span></span> <span data-ttu-id="aafae-132">W grupie **Produkt główny** kliknij **Wymiary produktu**.</span><span class="sxs-lookup"><span data-stu-id="aafae-132">In the **Product master** group, click **Product dimensions**.</span></span>

<span data-ttu-id="aafae-133">Liczba wariantów, które można utworzyć dla towaru jest ograniczona przez liczbę kombinacji wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="aafae-133">The number of variants that you can create for an item is limited by the number of possible product dimension combinations.</span></span>

| <span data-ttu-id="aafae-134">**Wskazówka**</span><span class="sxs-lookup"><span data-stu-id="aafae-134">**Tip**</span></span>                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="aafae-135">Jeśli produkt jest używany, na przykład, w wierszu zamówienia, należy wybrać wymiary produktu do zdefiniowania wariantu produktu, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="aafae-135">When you use a product on, for example, an order line, you select the product dimensions to identify the product variant that you want to work with.</span></span> |

## <a name="example"></a><span data-ttu-id="aafae-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="aafae-136">Example</span></span>
<span data-ttu-id="aafae-137">Firma sprzedaje jeansy.</span><span class="sxs-lookup"><span data-stu-id="aafae-137">A company sells denim jeans.</span></span> <span data-ttu-id="aafae-138">Dla towaru — jeansów — istnieją wymiary Kolor i Rozmiar.</span><span class="sxs-lookup"><span data-stu-id="aafae-138">The item, Jeans, uses the Color and Size product dimensions.</span></span> <span data-ttu-id="aafae-139">Jeansy są sprzedawane w trzech różnych kolorach i sześciu rozmiarach.</span><span class="sxs-lookup"><span data-stu-id="aafae-139">The jeans are sold in three different colors and six different sizes.</span></span> <span data-ttu-id="aafae-140">Kolory to niebieski, czarny, brązowy Rozmiary: XS, S, M, L, XL, XXL Nie wszystkie rozmiary są dostępne w trzech kolorach.</span><span class="sxs-lookup"><span data-stu-id="aafae-140">Colors: Blue, Black, Brown Sizes: XS, S, M, L, XL, XXL Not all sizes are available in all the three colors.</span></span> <span data-ttu-id="aafae-141">Jeżeli wszystkie kombinacje byłyby dostępne, istniałoby 18 różnych typów jeansów.</span><span class="sxs-lookup"><span data-stu-id="aafae-141">If all combinations were available, it would create 18 different types of jeans.</span></span> <span data-ttu-id="aafae-142">W tym przykładzie utworzono tylko dziewięć następujących kombinacji wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="aafae-142">In this example, only the following nine product variant combinations are produced.</span></span>

| <span data-ttu-id="aafae-143">Kolor</span><span class="sxs-lookup"><span data-stu-id="aafae-143">Color</span></span> | <span data-ttu-id="aafae-144">Rozmiar</span><span class="sxs-lookup"><span data-stu-id="aafae-144">Size</span></span> |
|-------|------|
| <span data-ttu-id="aafae-145">Niebieski</span><span class="sxs-lookup"><span data-stu-id="aafae-145">Blue</span></span>  | <span data-ttu-id="aafae-146">XS</span><span class="sxs-lookup"><span data-stu-id="aafae-146">XS</span></span>   |
| <span data-ttu-id="aafae-147">Niebieski</span><span class="sxs-lookup"><span data-stu-id="aafae-147">Blue</span></span>  | <span data-ttu-id="aafae-148">S</span><span class="sxs-lookup"><span data-stu-id="aafae-148">S</span></span>    |
| <span data-ttu-id="aafae-149">Niebieski</span><span class="sxs-lookup"><span data-stu-id="aafae-149">Blue</span></span>  | <span data-ttu-id="aafae-150">P</span><span class="sxs-lookup"><span data-stu-id="aafae-150">M</span></span>    |
| <span data-ttu-id="aafae-151">Czarny</span><span class="sxs-lookup"><span data-stu-id="aafae-151">Black</span></span> | <span data-ttu-id="aafae-152">P</span><span class="sxs-lookup"><span data-stu-id="aafae-152">M</span></span>    |
| <span data-ttu-id="aafae-153">Czarny</span><span class="sxs-lookup"><span data-stu-id="aafae-153">Black</span></span> | <span data-ttu-id="aafae-154">L</span><span class="sxs-lookup"><span data-stu-id="aafae-154">L</span></span>    |
| <span data-ttu-id="aafae-155">Czarny</span><span class="sxs-lookup"><span data-stu-id="aafae-155">Black</span></span> | <span data-ttu-id="aafae-156">XL</span><span class="sxs-lookup"><span data-stu-id="aafae-156">XL</span></span>   |
| <span data-ttu-id="aafae-157">Brązowy</span><span class="sxs-lookup"><span data-stu-id="aafae-157">Brown</span></span> | <span data-ttu-id="aafae-158">W</span><span class="sxs-lookup"><span data-stu-id="aafae-158">L</span></span>    |
| <span data-ttu-id="aafae-159">Brązowy</span><span class="sxs-lookup"><span data-stu-id="aafae-159">Brown</span></span> | <span data-ttu-id="aafae-160">XL</span><span class="sxs-lookup"><span data-stu-id="aafae-160">XL</span></span>   |
| <span data-ttu-id="aafae-161">Brązowy</span><span class="sxs-lookup"><span data-stu-id="aafae-161">Brown</span></span> | <span data-ttu-id="aafae-162">XXL</span><span class="sxs-lookup"><span data-stu-id="aafae-162">XXL</span></span>  |





