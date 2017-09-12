---
title: "Nazewnictwo numerów i nazw wariantów produktu"
description: "W tym temacie opisano sposób ustawiania nazewnictwa numerów produktów w celu zastąpienia stałego formatu [numer produktu głównego — konfiguracja — rozmiar — kolor — styl numeracji] format. Nowe nazewnictwo ma format docelowy zawierający numer produktu głównego, aktywne wymiary produktu i separatory tekstu wybrane przez użytkownika. Można też ustalić zasady nazewnictwa dla nazw produktów. Można ponadto skonstruować konwencję nazewnictwa do identyfikowania konfiguracji, które są tworzone przez konfigurator produktów oparty na ograniczeniach. Te konwencje nazewnictwa mogą zawierać atrybuty wybrane przez użytkownika."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d1a9ced00d8dc09e59512056392a250a76ba5b97
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="c19ad-107">Nazewnictwo numerów i nazw wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="c19ad-107">Nomenclature of product variant numbers and names</span></span>

<span data-ttu-id="c19ad-108">W tym temacie opisano sposób ustawiania nazewnictwa numerów produktów w celu zastąpienia stałego formatu [numer produktu głównego — konfiguracja — rozmiar — kolor — styl numeracji] format.</span><span class="sxs-lookup"><span data-stu-id="c19ad-108">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="c19ad-109">Nowe nazewnictwo ma format docelowy zawierający numer produktu głównego, aktywne wymiary produktu i separatory tekstu wybrane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c19ad-109">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="c19ad-110">Można też ustalić zasady nazewnictwa dla nazw produktów.</span><span class="sxs-lookup"><span data-stu-id="c19ad-110">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="c19ad-111">Można ponadto skonstruować konwencję nazewnictwa do identyfikowania konfiguracji, które są tworzone przez konfigurator produktów oparty na ograniczeniach.</span><span class="sxs-lookup"><span data-stu-id="c19ad-111">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="c19ad-112">Te konwencje nazewnictwa mogą zawierać atrybuty wybrane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c19ad-112">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="c19ad-113">Nowe nazewnictwa numerów wariantu produktu i nazw wariantów produktu pozwalają na uwzględnienie segmentów w identyfikatorach wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-113">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="c19ad-114">Segmenty te mogą zawierać numer i nazwę produktu głównego, identyfikator i nazwy wymiarów produktu, sekwencje numerów, stałe tekstowe i atrybuty.</span><span class="sxs-lookup"><span data-stu-id="c19ad-114">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="c19ad-115">Ta funkcja umożliwia szybkie znalezienie konkretnego wariantu produktu podczas tworzenia zamówienia sprzedaży lub zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-115">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="c19ad-116">Zarówno nazewnictwo numerów wariantu produktu i jak i nazewnictwo nazw wariantu produktu tworzy się przy użyciu strony **Nazewnictwo produktów**.</span><span class="sxs-lookup"><span data-stu-id="c19ad-116">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="c19ad-117">Aby otworzyć tę stronę, kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="c19ad-117">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="c19ad-118">Nazewnictwo predefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="c19ad-118">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="c19ad-119">Warianty produktu są generowane dla produktów głównych zgodnie z jedną z trzech technologii konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="c19ad-119">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="c19ad-120">Wstępnie zdefiniowane warianty</span><span class="sxs-lookup"><span data-stu-id="c19ad-120">Predefined variants</span></span>
-   <span data-ttu-id="c19ad-121">Oparte na ograniczeniach</span><span class="sxs-lookup"><span data-stu-id="c19ad-121">Constraint-based</span></span>
-   <span data-ttu-id="c19ad-122">Oparte na wymiarze</span><span class="sxs-lookup"><span data-stu-id="c19ad-122">Dimension-based</span></span>

<span data-ttu-id="c19ad-123">Każdy wariant produktu ma numer i nazwę, a konwencje nazewnictwa identyfikacji wariantów produktu pozwalają wybrać segmenty, które zostaną umieszczone w każdym numerze lub nazwie wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-123">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="c19ad-124">Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**:</span><span class="sxs-lookup"><span data-stu-id="c19ad-124">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="c19ad-125">Numer produktu głównego</span><span class="sxs-lookup"><span data-stu-id="c19ad-125">Product master number</span></span>
-   <span data-ttu-id="c19ad-126">Nazwa produktu głównego</span><span class="sxs-lookup"><span data-stu-id="c19ad-126">Product master name</span></span>
-   <span data-ttu-id="c19ad-127">Wartość sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="c19ad-127">Number sequence value</span></span>
-   <span data-ttu-id="c19ad-128">Stała tekstowa</span><span class="sxs-lookup"><span data-stu-id="c19ad-128">Text constant</span></span>
-   <span data-ttu-id="c19ad-129">Wymiary produktu</span><span class="sxs-lookup"><span data-stu-id="c19ad-129">Product dimensions</span></span>
    -   <span data-ttu-id="c19ad-130">Nazwa lub identyfikator konfiguracji</span><span class="sxs-lookup"><span data-stu-id="c19ad-130">Configuration ID or name</span></span>
    -   <span data-ttu-id="c19ad-131">Nazwa lub identyfikator koloru</span><span class="sxs-lookup"><span data-stu-id="c19ad-131">Color ID or name</span></span>
    -   <span data-ttu-id="c19ad-132">Nazwa lub identyfikator rozmiaru</span><span class="sxs-lookup"><span data-stu-id="c19ad-132">Size ID or name</span></span>
    -   <span data-ttu-id="c19ad-133">Nazwa lub identyfikator stylu</span><span class="sxs-lookup"><span data-stu-id="c19ad-133">Style ID or name</span></span>

<span data-ttu-id="c19ad-134">Po zdefiniowaniu nazewnictwa identyfikacji wariantu produktu można je skojarzyć z grupą wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-134">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="c19ad-135">Wszystkim produktom głównym odwołującym się do tej grupy wymiarów produktu zostaną przypisane numery wariantów produktu zgodnie z konwencją nazewnictwa.</span><span class="sxs-lookup"><span data-stu-id="c19ad-135">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="c19ad-136">Jednak nomenklatur nazw wariantów produktów nie można skojarzyć z grupami wymiarów produktów.</span><span class="sxs-lookup"><span data-stu-id="c19ad-136">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="c19ad-137">Można również przypisać nazewnictwo identyfikacji wariantu produktu bezpośrednio do produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="c19ad-137">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="c19ad-138">W takim przypadku wariantom produktu, które należą do produktu głównego, zostaną przypisane numery oraz nazwy wariantów produktu zgodnie z nomenklaturami.</span><span class="sxs-lookup"><span data-stu-id="c19ad-138">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="c19ad-139">Przykład</span><span class="sxs-lookup"><span data-stu-id="c19ad-139">Example</span></span>

<span data-ttu-id="c19ad-140">Koszulka (TS1234) jest wytwarzana w 3 rozmiarach (S, M, L), czterech kolorach (czerwony, zielony, niebieski, żółty) i dwóch stylach (polo, w serek).</span><span class="sxs-lookup"><span data-stu-id="c19ad-140">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="c19ad-141">Z tego względu możliwe są 24 (= 3 x 4 x 2) warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-141">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="c19ad-142">Można utworzyć nazewnictwo numerów wariantów produktu, która zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="c19ad-142">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="c19ad-143">Numer produktu głównego</span><span class="sxs-lookup"><span data-stu-id="c19ad-143">Product master number</span></span>
2.  <span data-ttu-id="c19ad-144">Stała tekstowa: „-”</span><span class="sxs-lookup"><span data-stu-id="c19ad-144">Text constant: "-"</span></span>
3.  <span data-ttu-id="c19ad-145">Kolor</span><span class="sxs-lookup"><span data-stu-id="c19ad-145">Color</span></span>
4.  <span data-ttu-id="c19ad-146">Stała tekstowa: „-”</span><span class="sxs-lookup"><span data-stu-id="c19ad-146">Text constant: "-"</span></span>
5.  <span data-ttu-id="c19ad-147">Rozmiar</span><span class="sxs-lookup"><span data-stu-id="c19ad-147">Size</span></span>
6.  <span data-ttu-id="c19ad-148">Stała tekstowa: „-”</span><span class="sxs-lookup"><span data-stu-id="c19ad-148">Text constant: "-"</span></span>
7.  <span data-ttu-id="c19ad-149">Styl</span><span class="sxs-lookup"><span data-stu-id="c19ad-149">Style</span></span>

<span data-ttu-id="c19ad-150">W tym przypadku numer wariantu produktu czerwonej, małej koszulki polo będzie następujący: TS1234-czerwony-mały-polo.</span><span class="sxs-lookup"><span data-stu-id="c19ad-150">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraintbased-configurations"></a><span data-ttu-id="c19ad-151">Nazewnictwo konfiguracji opartych na ograniczeniach</span><span class="sxs-lookup"><span data-stu-id="c19ad-151">Nomenclature of constraintbased configurations</span></span>
<span data-ttu-id="c19ad-152">W konfiguracjach opartych na ograniczeniach można utworzyć dedykowaną konwencję nazewnictwa dla wymiaru konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-152">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="c19ad-153">Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**:</span><span class="sxs-lookup"><span data-stu-id="c19ad-153">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="c19ad-154">Wartość sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="c19ad-154">Number sequence value</span></span>
-   <span data-ttu-id="c19ad-155">Stała tekstowa</span><span class="sxs-lookup"><span data-stu-id="c19ad-155">Text constant</span></span>
-   <span data-ttu-id="c19ad-156">Wartość atrybutu</span><span class="sxs-lookup"><span data-stu-id="c19ad-156">Attribute value</span></span>

<span data-ttu-id="c19ad-157">Każdy składnik w modelu konfiguracji produktu może mieć własne nazewnictwo konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c19ad-157">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="c19ad-158">Mogą być stosowane tylko atrybuty należące do składnika.</span><span class="sxs-lookup"><span data-stu-id="c19ad-158">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="c19ad-159">Atrybuty ze składników podrzędnych i wymagań użytkownika nie mogą być stosowane.</span><span class="sxs-lookup"><span data-stu-id="c19ad-159">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="c19ad-160">Przykład</span><span class="sxs-lookup"><span data-stu-id="c19ad-160">Example</span></span>

<span data-ttu-id="c19ad-161">Model konfiguracji produktu ma składnik główny posiadający dwa atrybuty:</span><span class="sxs-lookup"><span data-stu-id="c19ad-161">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="c19ad-162">Materiał (plastik, drewno, stal)</span><span class="sxs-lookup"><span data-stu-id="c19ad-162">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="c19ad-163">Długość (10...100)</span><span class="sxs-lookup"><span data-stu-id="c19ad-163">Length (10...100)</span></span>

<span data-ttu-id="c19ad-164">Można utworzyć nazewnictwo konfiguracji, która zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="c19ad-164">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="c19ad-165">Wartość atrybutu: Materiał</span><span class="sxs-lookup"><span data-stu-id="c19ad-165">Attribute value: Material</span></span>
2.  <span data-ttu-id="c19ad-166">Stała tekstowa: „AAA”</span><span class="sxs-lookup"><span data-stu-id="c19ad-166">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="c19ad-167">Wartość atrybutu: Długość</span><span class="sxs-lookup"><span data-stu-id="c19ad-167">Attribute value: Length</span></span>

<span data-ttu-id="c19ad-168">W tym przypadku identyfikator konfiguracji dla materiału „drewno” o długości 78 będzie DrewnoAAA78.</span><span class="sxs-lookup"><span data-stu-id="c19ad-168">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimensionbased-configurations"></a><span data-ttu-id="c19ad-169">Nazewnictwo konfiguracji opartych na wymiarach</span><span class="sxs-lookup"><span data-stu-id="c19ad-169">Nomenclature of dimensionbased configurations</span></span>
<span data-ttu-id="c19ad-170">W konfiguracjach opartych na wymiarach można utworzyć dedykowaną konwencję nazewnictwa dla wymiaru konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-170">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="c19ad-171">Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**:</span><span class="sxs-lookup"><span data-stu-id="c19ad-171">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="c19ad-172">Wartość sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="c19ad-172">Number sequence value</span></span>
-   <span data-ttu-id="c19ad-173">Stała tekstowa</span><span class="sxs-lookup"><span data-stu-id="c19ad-173">Text constant</span></span>
-   <span data-ttu-id="c19ad-174">Element grupy konfiguracji</span><span class="sxs-lookup"><span data-stu-id="c19ad-174">Configuration group item</span></span>

<span data-ttu-id="c19ad-175">Nazewnictwo konfiguracji można zdefiniować dla listy składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="c19ad-175">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="c19ad-176">Przykład</span><span class="sxs-lookup"><span data-stu-id="c19ad-176">Example</span></span>

<span data-ttu-id="c19ad-177">Lista BOM ma cztery wiersze BOM, które są podzielone na dwie grupy konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="c19ad-177">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="c19ad-178">Wiersz BOM: M0007, Standardowa szafa</span><span class="sxs-lookup"><span data-stu-id="c19ad-178">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="c19ad-179">Grupa konfiguracji: Szafa</span><span class="sxs-lookup"><span data-stu-id="c19ad-179">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="c19ad-180">Wiersz BOM: M0008, Szafa o wysokiej jakości</span><span class="sxs-lookup"><span data-stu-id="c19ad-180">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="c19ad-181">Grupa konfiguracji: Szafa</span><span class="sxs-lookup"><span data-stu-id="c19ad-181">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="c19ad-182">Wiersz BOM: M0021, Przednia kratka z tkaniny</span><span class="sxs-lookup"><span data-stu-id="c19ad-182">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="c19ad-183">Grupa konfiguracji: Przednia kratka</span><span class="sxs-lookup"><span data-stu-id="c19ad-183">Configuration group: Front grill</span></span>
-   <span data-ttu-id="c19ad-184">Wiersz BOM: M0022, Przednia kratka z metalu</span><span class="sxs-lookup"><span data-stu-id="c19ad-184">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="c19ad-185">Grupa konfiguracji: Przednia kratka</span><span class="sxs-lookup"><span data-stu-id="c19ad-185">Configuration group: Front grill</span></span>

<span data-ttu-id="c19ad-186">Można utworzyć nazewnictwo konfiguracji, która zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="c19ad-186">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="c19ad-187">Grupa konfiguracji: Szafa</span><span class="sxs-lookup"><span data-stu-id="c19ad-187">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="c19ad-188">Stała tekstowa: „&”</span><span class="sxs-lookup"><span data-stu-id="c19ad-188">Text constant: "&"</span></span>
3.  <span data-ttu-id="c19ad-189">Grupa konfiguracji: Przednia kratka</span><span class="sxs-lookup"><span data-stu-id="c19ad-189">Configuration group: Front grill</span></span>

<span data-ttu-id="c19ad-190">W tym przypadku identyfikator konfiguracji standardowej szafy z przednią kratką z tkaniny będzie miał wartość M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="c19ad-190">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="c19ad-191">Nazewnictwo kombinacji wariantów produktu i konfiguracji</span><span class="sxs-lookup"><span data-stu-id="c19ad-191">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="c19ad-192">Jeśli do konfigurowania wariantów produktu głównego jest używana technologia konfiguracji opartej na ograniczeniach lub na wymiarach, warianty produktu mogą otrzymywać numery wariantów produktu zawierające nazewnictwo z wymiaru konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c19ad-192">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="c19ad-193">Aby skonfigurować warianty, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c19ad-193">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="c19ad-194">Na stronie **Nazewnictwo produktów** zdefiniuj nazewnictwo numerów wariantów produktu zawierające wymiar konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c19ad-194">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="c19ad-195">Przypisz tę konwencję nazewnictwa do grupy wymiarów produktu zawierającej wymiar konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c19ad-195">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="c19ad-196">Zdefiniuj nazewnictwo konfiguracji dla składników lub list BOM, które będą używane do konfigurowania wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-196">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="c19ad-197">Można też ustalić zasady nazewnictwa dla nazw wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-197">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="c19ad-198">Aby uwzględnić nazwę lub identyfikator konfiguracji można skonfigurować nazwy wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-198">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="c19ad-199">Przykład konfiguracji opartych na ograniczeniach</span><span class="sxs-lookup"><span data-stu-id="c19ad-199">Example for constraint-based configurations</span></span>

<span data-ttu-id="c19ad-200">W tym przykładzie użyta jest konwencja nazewnictwa numerów wariantów produktu składająca się z następujących segmentów:</span><span class="sxs-lookup"><span data-stu-id="c19ad-200">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="c19ad-201">Numer produktu głównego</span><span class="sxs-lookup"><span data-stu-id="c19ad-201">Product master number</span></span>
2.  <span data-ttu-id="c19ad-202">Stała tekstowa „\_”</span><span class="sxs-lookup"><span data-stu-id="c19ad-202">Text constant "\_"</span></span>
3.  <span data-ttu-id="c19ad-203">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="c19ad-203">Configuration</span></span>

<span data-ttu-id="c19ad-204">Nazewnictwo konfiguracji zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="c19ad-204">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="c19ad-205">Wartość atrybutu: Materiał</span><span class="sxs-lookup"><span data-stu-id="c19ad-205">Attribute value: Material</span></span>
2.  <span data-ttu-id="c19ad-206">Stała tekstowa: „AAA”</span><span class="sxs-lookup"><span data-stu-id="c19ad-206">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="c19ad-207">Wartość atrybutu: Długość</span><span class="sxs-lookup"><span data-stu-id="c19ad-207">Attribute value: Length</span></span>

<span data-ttu-id="c19ad-208">Można wprowadzić następujące wartości segmentów:</span><span class="sxs-lookup"><span data-stu-id="c19ad-208">You enter the following values for segments:</span></span>

-   <span data-ttu-id="c19ad-209">Numer produktu głównego = **M0099**</span><span class="sxs-lookup"><span data-stu-id="c19ad-209">Product master number = **M0099**</span></span>
-   <span data-ttu-id="c19ad-210">Materiał = **Plastik**</span><span class="sxs-lookup"><span data-stu-id="c19ad-210">Material = **Plastic**</span></span>
-   <span data-ttu-id="c19ad-211">Długość = **12**</span><span class="sxs-lookup"><span data-stu-id="c19ad-211">Length = **12**</span></span>

<span data-ttu-id="c19ad-212">W tym przypadku numer wariantu produktu będzie miał wartość M0099\_PlastikAAA12.</span><span class="sxs-lookup"><span data-stu-id="c19ad-212">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="c19ad-213">Przykład konfiguracji opartych na wymiarach</span><span class="sxs-lookup"><span data-stu-id="c19ad-213">Example for dimension-based configurations</span></span>

<span data-ttu-id="c19ad-214">W tym przykładzie użyta jest konwencja nazewnictwa numerów wariantów produktu składająca się z następujących segmentów:</span><span class="sxs-lookup"><span data-stu-id="c19ad-214">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="c19ad-215">Numer produktu głównego</span><span class="sxs-lookup"><span data-stu-id="c19ad-215">Product master number</span></span>
2.  <span data-ttu-id="c19ad-216">Stała tekstowa: „//”</span><span class="sxs-lookup"><span data-stu-id="c19ad-216">Text constant "//"</span></span>
3.  <span data-ttu-id="c19ad-217">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="c19ad-217">Configuration</span></span>

<span data-ttu-id="c19ad-218">Nazewnictwo konfiguracji zawiera następujące segmenty:</span><span class="sxs-lookup"><span data-stu-id="c19ad-218">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="c19ad-219">Grupa konfiguracji: Szafa</span><span class="sxs-lookup"><span data-stu-id="c19ad-219">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="c19ad-220">Stała tekstowa: „&”</span><span class="sxs-lookup"><span data-stu-id="c19ad-220">Text constant: "&"</span></span>
3.  <span data-ttu-id="c19ad-221">Grupa konfiguracji: Przednia kratka</span><span class="sxs-lookup"><span data-stu-id="c19ad-221">Configuration group: Front grill</span></span>

<span data-ttu-id="c19ad-222">Można wprowadzić następujące wartości segmentów:</span><span class="sxs-lookup"><span data-stu-id="c19ad-222">You enter the following values for segments:</span></span>

-   <span data-ttu-id="c19ad-223">Numer produktu głównego = **D0123**</span><span class="sxs-lookup"><span data-stu-id="c19ad-223">Product master number = **D0123**</span></span>
-   <span data-ttu-id="c19ad-224">Szafa = **M0008**</span><span class="sxs-lookup"><span data-stu-id="c19ad-224">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="c19ad-225">Przednia kratka = **M0022**</span><span class="sxs-lookup"><span data-stu-id="c19ad-225">Front grill = **M0022**</span></span>

<span data-ttu-id="c19ad-226">W tym przypadku numer wariantu produktu będzie miał wartość D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="c19ad-226">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="c19ad-227">Konflikty numeracji</span><span class="sxs-lookup"><span data-stu-id="c19ad-227">Numbering conflicts</span></span>
<span data-ttu-id="c19ad-228">W niektórych przypadkach skonfigurowane nazewnictwo numerów wariantów produktu może nie powodować tworzenia unikatowych numerów wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-228">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="c19ad-229">Na przykład numery wariantów produktu nie będą unikatowe, jeśli jeden aktywny wymiar produktu nie jest uwzględniony w nazewnictwie produktu głównego używającym technologii wstępnie zdefiniowanej konfiguracji wariantów.</span><span class="sxs-lookup"><span data-stu-id="c19ad-229">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="c19ad-230">Konflikty są obsługiwane w różny sposób w zależności od technologii konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c19ad-230">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="c19ad-231">Wstępnie zdefiniowane warianty</span><span class="sxs-lookup"><span data-stu-id="c19ad-231">Predefined variants</span></span>

<span data-ttu-id="c19ad-232">Błąd pojawi się, jeśli zostanie podjęta próba ręcznego utworzenia lub automatycznego wygenerowania wariantów produktu i więcej niż jeden wariant kończy się tym samym numerem wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-232">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="c19ad-233">Aby uniknąć tego scenariusza, należy użyć wszystkich aktywnych wymiarów produktu w grupie wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-233">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="c19ad-234">Ewentualnie należy uwzględnić sekwencję numerów w celu zagwarantowania, że numery wariantów produktu są unikatowe.</span><span class="sxs-lookup"><span data-stu-id="c19ad-234">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="c19ad-235">Konfiguracje oparte na ograniczeniach</span><span class="sxs-lookup"><span data-stu-id="c19ad-235">Constraint-based configurations</span></span>

<span data-ttu-id="c19ad-236">W zależności od nazewnictwa system może próbować przypisać nieunikatowy numer wariantu produktu do konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c19ad-236">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="c19ad-237">W takim przypadku jako numeru wariantu produktu system użyje sekwencji numerów wymiaru konfiguracji. Jeśli tak się stanie, otrzymasz ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="c19ad-237">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="c19ad-238">Aby uniknąć tej sytuacji, należy dołączyć wystarczającą liczbę atrybutów do nazewnictwa w celu zagwarantowania unikatowych numerów wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="c19ad-238">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="c19ad-239">Należy również upewnić się, że opcja **Użyj ponownie** jest włączona dla składnika.</span><span class="sxs-lookup"><span data-stu-id="c19ad-239">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="c19ad-240">Konfiguracje oparte na wymiarach</span><span class="sxs-lookup"><span data-stu-id="c19ad-240">Dimension-based configurations</span></span>

<span data-ttu-id="c19ad-241">Podczas jednego kroku procesu konfiguracji system proponuje wartość konfiguracji zgodną z konwencją nazewnictwa.</span><span class="sxs-lookup"><span data-stu-id="c19ad-241">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="c19ad-242">W tym kroku można ręcznie zmienić wartość konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c19ad-242">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="c19ad-243">Podczas zapisywania konfiguracji system sprawdza, czy wartość konfiguracji jest unikatowa.</span><span class="sxs-lookup"><span data-stu-id="c19ad-243">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="c19ad-244">Jeśli wprowadzona wartość nie jest unikatowa, pojawi się komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="c19ad-244">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="c19ad-245">Aby zapisać konfigurację, należy wprowadzić niepowtarzalną wartość konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c19ad-245">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="see-also"></a><span data-ttu-id="c19ad-246">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="c19ad-246">See also</span></span>
--------

[<span data-ttu-id="c19ad-247">Tworzenie nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="c19ad-247">Create a product number nomenclature for predefined product variants</span></span>](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-predefined-variants-2016-11)

[<span data-ttu-id="c19ad-248">Tworzenie konwencji nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="c19ad-248">Create a product number nomenclature for configured product variants</span></span>](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-product-variants_2016_11)


