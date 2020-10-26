---
title: Nazewnictwo numerów i nazw wariantów produktu
description: W tym temacie opisano sposób ustawiania nazewnictwa numerów produktów w celu zastąpienia stałego formatu [numer produktu głównego — konfiguracja — rozmiar — kolor — styl numeracji] format.
author: roxanadiaconu
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 90c01e4281246d890ef888c56ca137f83e83741c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980490"
---
# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="4c0a5-103">Nazewnictwo numerów i nazw wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="4c0a5-103">Nomenclature of product variant numbers and names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c0a5-104">W tym temacie opisano sposób ustawiania nazewnictwa numerów produktów w celu zastąpienia stałego formatu [numer produktu głównego — konfiguracja — rozmiar — kolor — styl numeracji] format.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-104">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="4c0a5-105">Nowe nazewnictwo ma format docelowy zawierający numer produktu głównego, aktywne wymiary produktu i separatory tekstu wybrane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-105">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="4c0a5-106">Można też ustalić zasady nazewnictwa dla nazw produktów.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-106">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="4c0a5-107">Można ponadto skonstruować konwencję nazewnictwa do identyfikowania konfiguracji, które są tworzone przez konfigurator produktów oparty na ograniczeniach.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-107">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="4c0a5-108">Te konwencje nazewnictwa mogą zawierać atrybuty wybrane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-108">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="4c0a5-109">Nowe nazewnictwa numerów wariantu produktu i nazw wariantów produktu pozwalają na uwzględnienie segmentów w identyfikatorach wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-109">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="4c0a5-110">Segmenty te mogą zawierać numer i nazwę produktu głównego, identyfikator i nazwy wymiarów produktu, sekwencje numerów, stałe tekstowe i atrybuty.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-110">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="4c0a5-111">Ta funkcja umożliwia szybkie znalezienie konkretnego wariantu produktu podczas tworzenia zamówienia sprzedaży lub zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-111">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="4c0a5-112">Zarówno nazewnictwo numerów wariantu produktu i jak i nazewnictwo nazw wariantu produktu tworzy się przy użyciu strony **Nazewnictwo produktów**.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-112">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="4c0a5-113">Aby otworzyć tę stronę, kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-113">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="4c0a5-114">Nazewnictwo predefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="4c0a5-114">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="4c0a5-115">Warianty produktu są generowane dla produktów głównych zgodnie z jedną z trzech technologii konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-115">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="4c0a5-116">Wstępnie zdefiniowane warianty</span><span class="sxs-lookup"><span data-stu-id="4c0a5-116">Predefined variants</span></span>
-   <span data-ttu-id="4c0a5-117">Oparte na ograniczeniach</span><span class="sxs-lookup"><span data-stu-id="4c0a5-117">Constraint-based</span></span>
-   <span data-ttu-id="4c0a5-118">Oparte na wymiarze</span><span class="sxs-lookup"><span data-stu-id="4c0a5-118">Dimension-based</span></span>

<span data-ttu-id="4c0a5-119">Każdy wariant produktu ma numer i nazwę, a konwencje nazewnictwa identyfikacji wariantów produktu pozwalają wybrać segmenty, które zostaną umieszczone w każdym numerze lub nazwie wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-119">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="4c0a5-120">Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-120">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="4c0a5-121">Numer produktu głównego</span><span class="sxs-lookup"><span data-stu-id="4c0a5-121">Product master number</span></span>
-   <span data-ttu-id="4c0a5-122">Nazwa produktu głównego</span><span class="sxs-lookup"><span data-stu-id="4c0a5-122">Product master name</span></span>
-   <span data-ttu-id="4c0a5-123">Wartość sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="4c0a5-123">Number sequence value</span></span>
-   <span data-ttu-id="4c0a5-124">Stała tekstowa</span><span class="sxs-lookup"><span data-stu-id="4c0a5-124">Text constant</span></span>
-   <span data-ttu-id="4c0a5-125">Wymiary produktu</span><span class="sxs-lookup"><span data-stu-id="4c0a5-125">Product dimensions</span></span>
    -   <span data-ttu-id="4c0a5-126">Nazwa lub identyfikator konfiguracji</span><span class="sxs-lookup"><span data-stu-id="4c0a5-126">Configuration ID or name</span></span>
    -   <span data-ttu-id="4c0a5-127">Nazwa lub identyfikator koloru</span><span class="sxs-lookup"><span data-stu-id="4c0a5-127">Color ID or name</span></span>
    -   <span data-ttu-id="4c0a5-128">Nazwa lub identyfikator rozmiaru</span><span class="sxs-lookup"><span data-stu-id="4c0a5-128">Size ID or name</span></span>
    -   <span data-ttu-id="4c0a5-129">Nazwa lub identyfikator stylu</span><span class="sxs-lookup"><span data-stu-id="4c0a5-129">Style ID or name</span></span>

<span data-ttu-id="4c0a5-130">Po zdefiniowaniu nazewnictwa identyfikacji wariantu produktu można je skojarzyć z grupą wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-130">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="4c0a5-131">Wszystkim produktom głównym odwołującym się do tej grupy wymiarów produktu zostaną przypisane numery wariantów produktu zgodnie z konwencją nazewnictwa.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-131">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="4c0a5-132">Jednak nomenklatur nazw wariantów produktów nie można skojarzyć z grupami wymiarów produktów.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-132">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="4c0a5-133">Można również przypisać nazewnictwo identyfikacji wariantu produktu bezpośrednio do produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-133">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="4c0a5-134">W takim przypadku wariantom produktu, które należą do produktu głównego, zostaną przypisane numery oraz nazwy wariantów produktu zgodnie z nomenklaturami.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-134">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="4c0a5-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="4c0a5-135">Example</span></span>

<span data-ttu-id="4c0a5-136">Koszulka (TS1234) jest wytwarzana w 3 rozmiarach (S, M, L), czterech kolorach (czerwony, zielony, niebieski, żółty) i dwóch stylach (polo, w serek).</span><span class="sxs-lookup"><span data-stu-id="4c0a5-136">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="4c0a5-137">Z tego względu możliwe są 24 (= 3 x 4 x 2) warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-137">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="4c0a5-138">Można utworzyć nazewnictwo numerów wariantów produktu, która zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-138">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="4c0a5-139">Numer produktu głównego</span><span class="sxs-lookup"><span data-stu-id="4c0a5-139">Product master number</span></span>
2.  <span data-ttu-id="4c0a5-140">Stała tekstowa: „-”</span><span class="sxs-lookup"><span data-stu-id="4c0a5-140">Text constant: "-"</span></span>
3.  <span data-ttu-id="4c0a5-141">Kolor</span><span class="sxs-lookup"><span data-stu-id="4c0a5-141">Color</span></span>
4.  <span data-ttu-id="4c0a5-142">Stała tekstowa: „-”</span><span class="sxs-lookup"><span data-stu-id="4c0a5-142">Text constant: "-"</span></span>
5.  <span data-ttu-id="4c0a5-143">Rozmiar</span><span class="sxs-lookup"><span data-stu-id="4c0a5-143">Size</span></span>
6.  <span data-ttu-id="4c0a5-144">Stała tekstowa: „-”</span><span class="sxs-lookup"><span data-stu-id="4c0a5-144">Text constant: "-"</span></span>
7.  <span data-ttu-id="4c0a5-145">Styl</span><span class="sxs-lookup"><span data-stu-id="4c0a5-145">Style</span></span>

<span data-ttu-id="4c0a5-146">W tym przypadku numer wariantu produktu czerwonej, małej koszulki polo będzie następujący: TS1234-czerwony-mały-polo.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-146">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraint-based-configurations"></a><span data-ttu-id="4c0a5-147">Nazewnictwo konfiguracji opartych na ograniczeniach</span><span class="sxs-lookup"><span data-stu-id="4c0a5-147">Nomenclature of constraint-based configurations</span></span>
<span data-ttu-id="4c0a5-148">W konfiguracjach opartych na ograniczeniach można utworzyć dedykowaną konwencję nazewnictwa dla wymiaru konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-148">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="4c0a5-149">Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-149">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="4c0a5-150">Wartość sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="4c0a5-150">Number sequence value</span></span>
-   <span data-ttu-id="4c0a5-151">Stała tekstowa</span><span class="sxs-lookup"><span data-stu-id="4c0a5-151">Text constant</span></span>
-   <span data-ttu-id="4c0a5-152">Wartość atrybutu</span><span class="sxs-lookup"><span data-stu-id="4c0a5-152">Attribute value</span></span>

<span data-ttu-id="4c0a5-153">Każdy składnik w modelu konfiguracji produktu może mieć własne nazewnictwo konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-153">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="4c0a5-154">Mogą być stosowane tylko atrybuty należące do składnika.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-154">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="4c0a5-155">Atrybuty ze składników podrzędnych i wymagań użytkownika nie mogą być stosowane.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-155">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="4c0a5-156">Przykład</span><span class="sxs-lookup"><span data-stu-id="4c0a5-156">Example</span></span>

<span data-ttu-id="4c0a5-157">Model konfiguracji produktu ma składnik główny posiadający dwa atrybuty:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-157">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="4c0a5-158">Materiał (plastik, drewno, stal)</span><span class="sxs-lookup"><span data-stu-id="4c0a5-158">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="4c0a5-159">Długość (10...100)</span><span class="sxs-lookup"><span data-stu-id="4c0a5-159">Length (10...100)</span></span>

<span data-ttu-id="4c0a5-160">Można utworzyć nazewnictwo konfiguracji, która zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-160">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="4c0a5-161">Wartość atrybutu: Materiał</span><span class="sxs-lookup"><span data-stu-id="4c0a5-161">Attribute value: Material</span></span>
2.  <span data-ttu-id="4c0a5-162">Stała tekstowa: „AAA”</span><span class="sxs-lookup"><span data-stu-id="4c0a5-162">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="4c0a5-163">Wartość atrybutu: Długość</span><span class="sxs-lookup"><span data-stu-id="4c0a5-163">Attribute value: Length</span></span>

<span data-ttu-id="4c0a5-164">W tym przypadku identyfikator konfiguracji dla materiału „drewno” o długości 78 będzie DrewnoAAA78.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-164">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimension-based-configurations"></a><span data-ttu-id="4c0a5-165">Nazewnictwo konfiguracji opartych na wymiarach</span><span class="sxs-lookup"><span data-stu-id="4c0a5-165">Nomenclature of dimension-based configurations</span></span>
<span data-ttu-id="4c0a5-166">W konfiguracjach opartych na wymiarach można utworzyć dedykowaną konwencję nazewnictwa dla wymiaru konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-166">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="4c0a5-167">Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-167">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="4c0a5-168">Wartość sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="4c0a5-168">Number sequence value</span></span>
-   <span data-ttu-id="4c0a5-169">Stała tekstowa</span><span class="sxs-lookup"><span data-stu-id="4c0a5-169">Text constant</span></span>
-   <span data-ttu-id="4c0a5-170">Element grupy konfiguracji</span><span class="sxs-lookup"><span data-stu-id="4c0a5-170">Configuration group item</span></span>

<span data-ttu-id="4c0a5-171">Nazewnictwo konfiguracji można zdefiniować dla listy składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="4c0a5-171">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="4c0a5-172">Przykład</span><span class="sxs-lookup"><span data-stu-id="4c0a5-172">Example</span></span>

<span data-ttu-id="4c0a5-173">Lista BOM ma cztery wiersze BOM, które są podzielone na dwie grupy konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-173">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="4c0a5-174">Wiersz BOM: M0007, Standardowa szafa</span><span class="sxs-lookup"><span data-stu-id="4c0a5-174">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="4c0a5-175">Grupa konfiguracji: Szafa</span><span class="sxs-lookup"><span data-stu-id="4c0a5-175">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="4c0a5-176">Wiersz BOM: M0008, Szafa o wysokiej jakości</span><span class="sxs-lookup"><span data-stu-id="4c0a5-176">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="4c0a5-177">Grupa konfiguracji: Szafa</span><span class="sxs-lookup"><span data-stu-id="4c0a5-177">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="4c0a5-178">Wiersz BOM: M0021, Przednia kratka z tkaniny</span><span class="sxs-lookup"><span data-stu-id="4c0a5-178">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="4c0a5-179">Grupa konfiguracji: Przednia kratka</span><span class="sxs-lookup"><span data-stu-id="4c0a5-179">Configuration group: Front grill</span></span>
-   <span data-ttu-id="4c0a5-180">Wiersz BOM: M0022, Przednia kratka z metalu</span><span class="sxs-lookup"><span data-stu-id="4c0a5-180">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="4c0a5-181">Grupa konfiguracji: Przednia kratka</span><span class="sxs-lookup"><span data-stu-id="4c0a5-181">Configuration group: Front grill</span></span>

<span data-ttu-id="4c0a5-182">Można utworzyć nazewnictwo konfiguracji, która zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-182">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="4c0a5-183">Grupa konfiguracji: Szafa</span><span class="sxs-lookup"><span data-stu-id="4c0a5-183">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="4c0a5-184">Stała tekstowa: „&”</span><span class="sxs-lookup"><span data-stu-id="4c0a5-184">Text constant: "&"</span></span>
3.  <span data-ttu-id="4c0a5-185">Grupa konfiguracji: Przednia kratka</span><span class="sxs-lookup"><span data-stu-id="4c0a5-185">Configuration group: Front grill</span></span>

<span data-ttu-id="4c0a5-186">W tym przypadku identyfikator konfiguracji standardowej szafy z przednią kratką z tkaniny będzie miał wartość M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-186">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="4c0a5-187">Nazewnictwo kombinacji wariantów produktu i konfiguracji</span><span class="sxs-lookup"><span data-stu-id="4c0a5-187">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="4c0a5-188">Jeśli do konfigurowania wariantów produktu głównego jest używana technologia konfiguracji opartej na ograniczeniach lub na wymiarach, warianty produktu mogą otrzymywać numery wariantów produktu zawierające nazewnictwo z wymiaru konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-188">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="4c0a5-189">Aby skonfigurować warianty, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-189">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="4c0a5-190">Na stronie **Nazewnictwo produktów** zdefiniuj nazewnictwo numerów wariantów produktu zawierające wymiar konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-190">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="4c0a5-191">Przypisz tę konwencję nazewnictwa do grupy wymiarów produktu zawierającej wymiar konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-191">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="4c0a5-192">Zdefiniuj nazewnictwo konfiguracji dla składników lub list BOM, które będą używane do konfigurowania wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-192">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="4c0a5-193">Można też ustalić zasady nazewnictwa dla nazw wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-193">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="4c0a5-194">Aby uwzględnić nazwę lub identyfikator konfiguracji można skonfigurować nazwy wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-194">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="4c0a5-195">Przykład konfiguracji opartych na ograniczeniach</span><span class="sxs-lookup"><span data-stu-id="4c0a5-195">Example for constraint-based configurations</span></span>

<span data-ttu-id="4c0a5-196">W tym przykładzie użyta jest konwencja nazewnictwa numerów wariantów produktu składająca się z następujących segmentów:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-196">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="4c0a5-197">Numer produktu głównego</span><span class="sxs-lookup"><span data-stu-id="4c0a5-197">Product master number</span></span>
2.  <span data-ttu-id="4c0a5-198">Stała tekstowa „\_”</span><span class="sxs-lookup"><span data-stu-id="4c0a5-198">Text constant "\_"</span></span>
3.  <span data-ttu-id="4c0a5-199">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="4c0a5-199">Configuration</span></span>

<span data-ttu-id="4c0a5-200">Nazewnictwo konfiguracji zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-200">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="4c0a5-201">Wartość atrybutu: Materiał</span><span class="sxs-lookup"><span data-stu-id="4c0a5-201">Attribute value: Material</span></span>
2.  <span data-ttu-id="4c0a5-202">Stała tekstowa: „AAA”</span><span class="sxs-lookup"><span data-stu-id="4c0a5-202">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="4c0a5-203">Wartość atrybutu: Długość</span><span class="sxs-lookup"><span data-stu-id="4c0a5-203">Attribute value: Length</span></span>

<span data-ttu-id="4c0a5-204">Można wprowadzić następujące wartości segmentów:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-204">You enter the following values for segments:</span></span>

-   <span data-ttu-id="4c0a5-205">Numer produktu głównego = **M0099**</span><span class="sxs-lookup"><span data-stu-id="4c0a5-205">Product master number = **M0099**</span></span>
-   <span data-ttu-id="4c0a5-206">Materiał = **Plastik**</span><span class="sxs-lookup"><span data-stu-id="4c0a5-206">Material = **Plastic**</span></span>
-   <span data-ttu-id="4c0a5-207">Długość = **12**</span><span class="sxs-lookup"><span data-stu-id="4c0a5-207">Length = **12**</span></span>

<span data-ttu-id="4c0a5-208">W tym przypadku numer wariantu produktu będzie miał wartość M0099\_PlastikAAA12.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-208">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="4c0a5-209">Przykład konfiguracji opartych na wymiarach</span><span class="sxs-lookup"><span data-stu-id="4c0a5-209">Example for dimension-based configurations</span></span>

<span data-ttu-id="4c0a5-210">W tym przykładzie użyta jest konwencja nazewnictwa numerów wariantów produktu składająca się z następujących segmentów:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-210">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="4c0a5-211">Numer produktu głównego</span><span class="sxs-lookup"><span data-stu-id="4c0a5-211">Product master number</span></span>
2.  <span data-ttu-id="4c0a5-212">Stała tekstowa: „//”</span><span class="sxs-lookup"><span data-stu-id="4c0a5-212">Text constant "//"</span></span>
3.  <span data-ttu-id="4c0a5-213">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="4c0a5-213">Configuration</span></span>

<span data-ttu-id="4c0a5-214">Nazewnictwo konfiguracji zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-214">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="4c0a5-215">Grupa konfiguracji: Szafa</span><span class="sxs-lookup"><span data-stu-id="4c0a5-215">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="4c0a5-216">Stała tekstowa: „&”</span><span class="sxs-lookup"><span data-stu-id="4c0a5-216">Text constant: "&"</span></span>
3.  <span data-ttu-id="4c0a5-217">Grupa konfiguracji: Przednia kratka</span><span class="sxs-lookup"><span data-stu-id="4c0a5-217">Configuration group: Front grill</span></span>

<span data-ttu-id="4c0a5-218">Można wprowadzić następujące wartości segmentów:</span><span class="sxs-lookup"><span data-stu-id="4c0a5-218">You enter the following values for segments:</span></span>

-   <span data-ttu-id="4c0a5-219">Numer produktu głównego = **D0123**</span><span class="sxs-lookup"><span data-stu-id="4c0a5-219">Product master number = **D0123**</span></span>
-   <span data-ttu-id="4c0a5-220">Szafa = **M0008**</span><span class="sxs-lookup"><span data-stu-id="4c0a5-220">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="4c0a5-221">Przednia kratka = **M0022**</span><span class="sxs-lookup"><span data-stu-id="4c0a5-221">Front grill = **M0022**</span></span>

<span data-ttu-id="4c0a5-222">W tym przypadku numer wariantu produktu będzie miał wartość D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-222">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="4c0a5-223">Konflikty numeracji</span><span class="sxs-lookup"><span data-stu-id="4c0a5-223">Numbering conflicts</span></span>
<span data-ttu-id="4c0a5-224">W niektórych przypadkach skonfigurowane nazewnictwo numerów wariantów produktu może nie powodować tworzenia unikatowych numerów wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-224">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="4c0a5-225">Na przykład numery wariantów produktu nie będą unikatowe, jeśli jeden aktywny wymiar produktu nie jest uwzględniony w nazewnictwie produktu głównego używającym technologii wstępnie zdefiniowanej konfiguracji wariantów.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-225">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="4c0a5-226">Konflikty są obsługiwane w różny sposób w zależności od technologii konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-226">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="4c0a5-227">Wstępnie zdefiniowane warianty</span><span class="sxs-lookup"><span data-stu-id="4c0a5-227">Predefined variants</span></span>

<span data-ttu-id="4c0a5-228">Błąd pojawi się, jeśli zostanie podjęta próba ręcznego utworzenia lub automatycznego wygenerowania wariantów produktu i więcej niż jeden wariant kończy się tym samym numerem wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-228">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="4c0a5-229">Aby uniknąć tego scenariusza, należy użyć wszystkich aktywnych wymiarów produktu w grupie wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-229">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="4c0a5-230">Ewentualnie należy uwzględnić sekwencję numerów w celu zagwarantowania, że numery wariantów produktu są unikatowe.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-230">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="4c0a5-231">Konfiguracje oparte na ograniczeniach</span><span class="sxs-lookup"><span data-stu-id="4c0a5-231">Constraint-based configurations</span></span>

<span data-ttu-id="4c0a5-232">W zależności od nazewnictwa system może próbować przypisać nieunikatowy numer wariantu produktu do konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-232">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="4c0a5-233">W takim przypadku jako numeru wariantu produktu system użyje sekwencji numerów wymiaru konfiguracji. Jeśli tak się stanie, otrzymasz ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-233">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="4c0a5-234">Aby uniknąć tej sytuacji, należy dołączyć wystarczającą liczbę atrybutów do nazewnictwa w celu zagwarantowania unikatowych numerów wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-234">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="4c0a5-235">Należy również upewnić się, że opcja **Użyj ponownie** jest włączona dla składnika.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-235">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="4c0a5-236">Konfiguracje oparte na wymiarach</span><span class="sxs-lookup"><span data-stu-id="4c0a5-236">Dimension-based configurations</span></span>

<span data-ttu-id="4c0a5-237">Podczas jednego kroku procesu konfiguracji system proponuje wartość konfiguracji zgodną z konwencją nazewnictwa.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-237">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="4c0a5-238">W tym kroku można ręcznie zmienić wartość konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-238">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="4c0a5-239">Podczas zapisywania konfiguracji system sprawdza, czy wartość konfiguracji jest unikatowa.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-239">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="4c0a5-240">Jeśli wprowadzona wartość nie jest unikatowa, pojawi się komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-240">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="4c0a5-241">Aby zapisać konfigurację, należy wprowadzić niepowtarzalną wartość konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4c0a5-241">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="additional-resources"></a><span data-ttu-id="4c0a5-242">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4c0a5-242">Additional resources</span></span>
--------

[<span data-ttu-id="4c0a5-243">Tworzenie konwencji nazewnictwa numerów produktów dla wstępnie zdefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="4c0a5-243">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="4c0a5-244">Tworzenie konwencji nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="4c0a5-244">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)

