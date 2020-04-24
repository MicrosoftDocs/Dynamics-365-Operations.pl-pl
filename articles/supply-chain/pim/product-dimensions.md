---
title: Wymiary produktu
description: Istnieją cztery wymiary produktu — Kolor, Konfiguracja, Rozmiar i Styl. Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych. Kombinacje wymiarów produktu decydują o definicjach wariantów produktu.
author: cvocph
manager: tfehr
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5e9b10fa18ada9534ce5e279d4f1f09973a802b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208439"
---
# <a name="product-dimensions"></a><span data-ttu-id="c8889-105">Wymiary produktu</span><span class="sxs-lookup"><span data-stu-id="c8889-105">Product dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8889-106">Istnieją cztery wymiary produktu — Kolor, Konfiguracja, Rozmiar i Styl.</span><span class="sxs-lookup"><span data-stu-id="c8889-106">There are four product dimensions -  Color, Configuration, Size and Style.</span></span> <span data-ttu-id="c8889-107">Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych.</span><span class="sxs-lookup"><span data-stu-id="c8889-107">You combine product dimensions in dimension groups and assign dimension groups to product masters.</span></span> <span data-ttu-id="c8889-108">Kombinacje wymiarów produktu decydują o definicjach wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="c8889-108">The combinations of product dimensions determine how product variants are defined.</span></span>

<span data-ttu-id="c8889-109">Wymiary produktu to cechy, które służą do określenia wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="c8889-109">Product dimensions are characteristics that serve to identify a product variant.</span></span> <span data-ttu-id="c8889-110">Kombinacje wymiarów produktu służą do definiowania wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="c8889-110">You can use combinations of product dimensions to define product variants.</span></span> <span data-ttu-id="c8889-111">Należy zdefiniować co najmniej jeden wymiar produktu dla produktu głównego w celu utworzenia wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="c8889-111">You must define at least one product dimension for a product master in order to create a product variant.</span></span>

## <a name="product-variants"></a><span data-ttu-id="c8889-112">Warianty produktu</span><span class="sxs-lookup"><span data-stu-id="c8889-112">Product variants</span></span>

<span data-ttu-id="c8889-113">Warianty produktu są również określane jako elementy.</span><span class="sxs-lookup"><span data-stu-id="c8889-113">Product variants are also referred to as items.</span></span> <span data-ttu-id="c8889-114">Towar to produkt materialny, który nie jest usługą.</span><span class="sxs-lookup"><span data-stu-id="c8889-114">An item is a tangible product, which is not the same as a service.</span></span> <span data-ttu-id="c8889-115">Istnieje również możliwość zdefiniowania produktu głównego typu Usługa.</span><span class="sxs-lookup"><span data-stu-id="c8889-115">It is also possible to define a product master with the Service type.</span></span> <span data-ttu-id="c8889-116">Za pomocą typu Usługa można określić warianty produktu, które zawierają usługi.</span><span class="sxs-lookup"><span data-stu-id="c8889-116">By using the Service type, you can specify product variants that include services.</span></span> <span data-ttu-id="c8889-117">Na przykład można określić produkt główny dla pracy w zakresie doradztwa i warianty produktu dla pracy wykonywanej przez starszych konsultantów i młodszych konsultantów.</span><span class="sxs-lookup"><span data-stu-id="c8889-117">For example, you can specify a product master for Consultancy work and product variants for work that is performed by senior consultants and junior consultants.</span></span>

## <a name="product-dimensions"></a><span data-ttu-id="c8889-118">Wymiary produktu</span><span class="sxs-lookup"><span data-stu-id="c8889-118">Product dimensions</span></span>
<span data-ttu-id="c8889-119">Dostępne są następujące wymiary produktu: Konfiguracja, Kolor, Rozmiar i Styl.</span><span class="sxs-lookup"><span data-stu-id="c8889-119">The following product dimensions are available: Configuration, Color, Size, and Style.</span></span> <span data-ttu-id="c8889-120">Wariant produktu może być generowany na podstawie wartości w wymiarach produktu.</span><span class="sxs-lookup"><span data-stu-id="c8889-120">A product variant can be generated based on the product dimension values.</span></span>

<span data-ttu-id="c8889-121">Wartości wymiarów produktu, takie jak Rozmiar, Kolor i Styl, można tworzyć na stronach **Rozmiar**, **Kolor** i **Styl**, które można otworzyć z następujących lokalizacji: **Zarządzanie informacjami o produktach** &gt; **Ustawienia** &gt; **Grupy wymiarów i wariantów** &gt; **Rozmiary/Kolory/Style**.</span><span class="sxs-lookup"><span data-stu-id="c8889-121">Product dimensions values such as Size, Color and Style can be created on the **Size**, **Color** and **Style** pages, which can be accessed from the following locations: **Product information management** &gt; **Setup** &gt; **Dimension and variant Groups** &gt; **Sizes/Colors/Styles**.</span></span> <span data-ttu-id="c8889-122">Wartości wymiaru produktu dla wymiaru konfiguracji są zwykle tworzone za pomocą konfiguratora produktów lub konfiguratora opartego na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="c8889-122">Product dimension values for the Configuration dimension are typically created using either the Product configurator or the Dimension-based configurator.</span></span> <span data-ttu-id="c8889-123">Wymiary produktu mogą być również tworzone i obsługiwane na stronie **Wymiary produktu**, która jest dostępna z następujących miejsc:</span><span class="sxs-lookup"><span data-stu-id="c8889-123">Product dimensions can also be created and maintained on the **Product dimensions** page, which can be accessed from the following locations:</span></span>
-   <span data-ttu-id="c8889-124">Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Produkty** &gt; **Produkty główne**.</span><span class="sxs-lookup"><span data-stu-id="c8889-124">Click **Product information management** &gt; **Products** &gt; **Product masters**.</span></span> <span data-ttu-id="c8889-125">W **okienku akcji** kliknij pozycję **Wymiary produktu**.</span><span class="sxs-lookup"><span data-stu-id="c8889-125">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="c8889-126">Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Produkty** &gt; **Wszystkie produkty i produkty główne**.</span><span class="sxs-lookup"><span data-stu-id="c8889-126">Click **Product information management** &gt; **Products** &gt; **All products and product masters**.</span></span> <span data-ttu-id="c8889-127">Wybierz produkt główny.</span><span class="sxs-lookup"><span data-stu-id="c8889-127">Select a product master.</span></span> <span data-ttu-id="c8889-128">W **okienku akcji** kliknij pozycję **Wymiary produktu**.</span><span class="sxs-lookup"><span data-stu-id="c8889-128">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="c8889-129">Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="c8889-129">Click **Product information management** &gt; **Released products**.</span></span> <span data-ttu-id="c8889-130">Wybierz produkt główny.</span><span class="sxs-lookup"><span data-stu-id="c8889-130">Select a product master.</span></span> <span data-ttu-id="c8889-131">W **okienku akcji** kliknij pozycję **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="c8889-131">On the **Action Pane**, click **Product**.</span></span> <span data-ttu-id="c8889-132">W grupie **Produkt główny** kliknij **Wymiary produktu**.</span><span class="sxs-lookup"><span data-stu-id="c8889-132">In the **Product master** group, click **Product dimensions**.</span></span>

<span data-ttu-id="c8889-133">Liczba wariantów, które można utworzyć dla towaru jest ograniczona przez liczbę kombinacji wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="c8889-133">The number of variants that you can create for an item is limited by the number of possible product dimension combinations.</span></span>

| <span data-ttu-id="c8889-134">**Wskazówka**</span><span class="sxs-lookup"><span data-stu-id="c8889-134">**Tip**</span></span>                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c8889-135">Jeśli produkt jest używany, na przykład, w wierszu zamówienia, należy wybrać wymiary produktu do zdefiniowania wariantu produktu, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="c8889-135">When you use a product on, for example, an order line, you select the product dimensions to identify the product variant that you want to work with.</span></span> |

## <a name="example"></a><span data-ttu-id="c8889-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="c8889-136">Example</span></span>
<span data-ttu-id="c8889-137">Firma sprzedaje jeansy.</span><span class="sxs-lookup"><span data-stu-id="c8889-137">A company sells denim jeans.</span></span> <span data-ttu-id="c8889-138">Dla towaru — jeansów — istnieją wymiary Kolor i Rozmiar.</span><span class="sxs-lookup"><span data-stu-id="c8889-138">The item, Jeans, uses the Color and Size product dimensions.</span></span> <span data-ttu-id="c8889-139">Jeansy są sprzedawane w trzech różnych kolorach i sześciu rozmiarach.</span><span class="sxs-lookup"><span data-stu-id="c8889-139">The jeans are sold in three different colors and six different sizes.</span></span> <span data-ttu-id="c8889-140">Kolory to niebieski, czarny, brązowy Rozmiary: XS, S, M, L, XL, XXL Nie wszystkie rozmiary są dostępne w trzech kolorach.</span><span class="sxs-lookup"><span data-stu-id="c8889-140">Colors: Blue, Black, Brown Sizes: XS, S, M, L, XL, XXL Not all sizes are available in all the three colors.</span></span> <span data-ttu-id="c8889-141">Jeżeli wszystkie kombinacje byłyby dostępne, istniałoby 18 różnych typów jeansów.</span><span class="sxs-lookup"><span data-stu-id="c8889-141">If all combinations were available, it would create 18 different types of jeans.</span></span> <span data-ttu-id="c8889-142">W tym przykładzie utworzono tylko dziewięć następujących kombinacji wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="c8889-142">In this example, only the following nine product variant combinations are produced.</span></span>

| <span data-ttu-id="c8889-143">Kolor</span><span class="sxs-lookup"><span data-stu-id="c8889-143">Color</span></span> | <span data-ttu-id="c8889-144">Rozmiar</span><span class="sxs-lookup"><span data-stu-id="c8889-144">Size</span></span> |
|-------|------|
| <span data-ttu-id="c8889-145">Niebieski</span><span class="sxs-lookup"><span data-stu-id="c8889-145">Blue</span></span>  | <span data-ttu-id="c8889-146">XS</span><span class="sxs-lookup"><span data-stu-id="c8889-146">XS</span></span>   |
| <span data-ttu-id="c8889-147">Niebieski</span><span class="sxs-lookup"><span data-stu-id="c8889-147">Blue</span></span>  | <span data-ttu-id="c8889-148">S</span><span class="sxs-lookup"><span data-stu-id="c8889-148">S</span></span>    |
| <span data-ttu-id="c8889-149">Niebieski</span><span class="sxs-lookup"><span data-stu-id="c8889-149">Blue</span></span>  | <span data-ttu-id="c8889-150">P</span><span class="sxs-lookup"><span data-stu-id="c8889-150">M</span></span>    |
| <span data-ttu-id="c8889-151">Czarny</span><span class="sxs-lookup"><span data-stu-id="c8889-151">Black</span></span> | <span data-ttu-id="c8889-152">P</span><span class="sxs-lookup"><span data-stu-id="c8889-152">M</span></span>    |
| <span data-ttu-id="c8889-153">Czarny</span><span class="sxs-lookup"><span data-stu-id="c8889-153">Black</span></span> | <span data-ttu-id="c8889-154">L</span><span class="sxs-lookup"><span data-stu-id="c8889-154">L</span></span>    |
| <span data-ttu-id="c8889-155">Czarny</span><span class="sxs-lookup"><span data-stu-id="c8889-155">Black</span></span> | <span data-ttu-id="c8889-156">XL</span><span class="sxs-lookup"><span data-stu-id="c8889-156">XL</span></span>   |
| <span data-ttu-id="c8889-157">Brązowy</span><span class="sxs-lookup"><span data-stu-id="c8889-157">Brown</span></span> | <span data-ttu-id="c8889-158">W</span><span class="sxs-lookup"><span data-stu-id="c8889-158">L</span></span>    |
| <span data-ttu-id="c8889-159">Brązowy</span><span class="sxs-lookup"><span data-stu-id="c8889-159">Brown</span></span> | <span data-ttu-id="c8889-160">XL</span><span class="sxs-lookup"><span data-stu-id="c8889-160">XL</span></span>   |
| <span data-ttu-id="c8889-161">Brązowy</span><span class="sxs-lookup"><span data-stu-id="c8889-161">Brown</span></span> | <span data-ttu-id="c8889-162">XXL</span><span class="sxs-lookup"><span data-stu-id="c8889-162">XXL</span></span>  |





