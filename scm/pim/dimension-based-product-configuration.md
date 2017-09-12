---
title: Konfiguracja produktu oparta na wymiarach
description: "Konfiguracja produktu oparta na wymiarach to prosty sposób tworzenia wielu wariantów produktu z jednego produktu głównego i jego BOM."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 89f01401f1d937a72ae7e59b784cf034b48aaf1f
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="dimension-based-product-configuration"></a><span data-ttu-id="eea08-103">Konfiguracja produktu oparta na wymiarach</span><span class="sxs-lookup"><span data-stu-id="eea08-103">Dimension-based product configuration</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="eea08-104">Konfiguracja produktu oparta na wymiarach to prosty sposób tworzenia wielu wariantów produktu z jednego produktu głównego i jego BOM.</span><span class="sxs-lookup"><span data-stu-id="eea08-104">Dimension-based product configuration represents a simple solution for creating many product variants from a single product master and its bill of materials.</span></span>

<span data-ttu-id="eea08-105">Konfiguracja produktów oparta na wymiarach jest jedną z trzech wbudowanych technologii konfiguracji produktów.</span><span class="sxs-lookup"><span data-stu-id="eea08-105">Dimension-based product configuration is one of the three built-in product configuration technologies.</span></span> <span data-ttu-id="eea08-106">Dwie pozostałe konfiguracje to wstępnie zdefiniowane warianty i konfiguracja oparta na ograniczeniach.</span><span class="sxs-lookup"><span data-stu-id="eea08-106">The two other technologies are predefined variants and constraint-based configuration.</span></span> <span data-ttu-id="eea08-107">Wszystkie trzy technologie używają produktu głównego jako punktu wyjścia i umożliwiają użytkownikowi tworzenie wielu wariantów dla jednego produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="eea08-107">All three technologies use a product master as the starting point and allow the user to create many product variants for one product master.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="eea08-108">Podstawowe pojęcia</span><span class="sxs-lookup"><span data-stu-id="eea08-108">Key concepts</span></span>
<span data-ttu-id="eea08-109">Podstawą konfiguracji opartej na wymiarach są następujące pojęcia:</span><span class="sxs-lookup"><span data-stu-id="eea08-109">Dimension-based product configuration is based on the following key concepts:</span></span>

-   <span data-ttu-id="eea08-110">Produkty główne</span><span class="sxs-lookup"><span data-stu-id="eea08-110">Product masters</span></span>
-   <span data-ttu-id="eea08-111">Konfiguracja wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="eea08-111">Configuration product dimension</span></span>
-   <span data-ttu-id="eea08-112">Grupy konfiguracji</span><span class="sxs-lookup"><span data-stu-id="eea08-112">Configuration groups</span></span>
-   <span data-ttu-id="eea08-113">Lista składowa (BOM)</span><span class="sxs-lookup"><span data-stu-id="eea08-113">Bill of materials (BOM)</span></span>
-   <span data-ttu-id="eea08-114">Marszruta konfiguracji</span><span class="sxs-lookup"><span data-stu-id="eea08-114">Configuration route</span></span>
-   <span data-ttu-id="eea08-115">Reguły konfiguracji</span><span class="sxs-lookup"><span data-stu-id="eea08-115">Configuration rules</span></span>

### <a name="product-masters"></a><span data-ttu-id="eea08-116">Produkty główne</span><span class="sxs-lookup"><span data-stu-id="eea08-116">Product masters</span></span>

<span data-ttu-id="eea08-117">Produkt główny jest punktem wyjścia dla każdego procesu konfiguracji produktów.</span><span class="sxs-lookup"><span data-stu-id="eea08-117">A product master is the starting point for any product configuration process.</span></span> <span data-ttu-id="eea08-118">Konfiguracja produktu oparta na wymiarach wymaga produktu głównego z konkretną technologią konfiguracji i grupy wymiaru produktu zawierającej wymiar produktu konfigurowanego.</span><span class="sxs-lookup"><span data-stu-id="eea08-118">For the dimension-based product configuration, you need a product master with this particular configuration technology and a product dimension group that includes the configuration product dimension.</span></span>

### <a name="configuration-product-dimension"></a><span data-ttu-id="eea08-119">Konfiguracja wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="eea08-119">Configuration product dimension</span></span>

<span data-ttu-id="eea08-120">Wymiar konfiguracji produktu jest używany do identyfikacji wariantów produktów dla produktu głównego z technologią konfiguracji opartą na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="eea08-120">The configuration product dimension is used to identify the product variants for a product master with the dimension-based configuration technology.</span></span> <span data-ttu-id="eea08-121">Wartość wymiaru konfiguracji jest określona przez użytkownika i powinna pomagać w identyfikowaniu poszczególnych kombinacji.</span><span class="sxs-lookup"><span data-stu-id="eea08-121">The configuration dimension value is entered by the user and should help to identify the individual product variants.</span></span>

### <a name="configuration-groups"></a><span data-ttu-id="eea08-122">Grupy konfiguracji</span><span class="sxs-lookup"><span data-stu-id="eea08-122">Configuration groups</span></span>

<span data-ttu-id="eea08-123">Grupy konfiguracji są określane w centralnym repozytorium i mogą być używane dla wszystkich modeli konfiguracji produktu opartych na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="eea08-123">Configuration groups are defined in a central repository and can be used for all dimension-based product configuration models.</span></span> <span data-ttu-id="eea08-124">Grupy konfiguracji są skojarzone z poszczególnymi wierszami BOM i spajają grupę wierszy, które wzajemnie się wykluczają.</span><span class="sxs-lookup"><span data-stu-id="eea08-124">Configuration groups are associated to the individual BOM lines and hold together a group of lines that are mutually exclusive.</span></span> <span data-ttu-id="eea08-125">Oznacza to, że dla jednego wariantu produktu można wybrać tylko jeden wiersz w grupie.</span><span class="sxs-lookup"><span data-stu-id="eea08-125">This means that only one line in a group can be selected for a single product variant.</span></span>

### <a name="bill-of-materials-bom"></a><span data-ttu-id="eea08-126">Lista składowa (BOM)</span><span class="sxs-lookup"><span data-stu-id="eea08-126">Bill of materials (BOM)</span></span>

<span data-ttu-id="eea08-127">BOM odpowiada blokom konstrukcyjnym dla konfiguracji produktu opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="eea08-127">The BOM represent the building blocks for a dimension-based product configuration.</span></span> <span data-ttu-id="eea08-128">Musi zawierać wszystkie różne produkty, które mogą być używane w dowolnym wariancie produktu.</span><span class="sxs-lookup"><span data-stu-id="eea08-128">It must include all the different products that can be used in any product variant.</span></span> <span data-ttu-id="eea08-129">Każdy wiersz w BOM może się odwoływać do grupy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="eea08-129">Each line in the BOM can reference a configuration group.</span></span> <span data-ttu-id="eea08-130">Jeśli wiersz nie odwołuje się do grupy konfiguracji, będzie on uwzględniony we wszystkich wariantach produktu.</span><span class="sxs-lookup"><span data-stu-id="eea08-130">If a line doesn’t reference a configuration group, it will be included in all product variants.</span></span>

### <a name="configuration-route"></a><span data-ttu-id="eea08-131">Marszruta konfiguracji</span><span class="sxs-lookup"><span data-stu-id="eea08-131">Configuration route</span></span>

<span data-ttu-id="eea08-132">Marszruta konfiguracji określa kolejność grup konfiguracji, w jakiej będą one wyświetlane użytkownikowi w procesie konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="eea08-132">The configuration route determines the sequence of the configuration groups, as they will be displayed to the user during the product configuration process.</span></span>

### <a name="configuration-rules"></a><span data-ttu-id="eea08-133">Reguły konfiguracji</span><span class="sxs-lookup"><span data-stu-id="eea08-133">Configuration rules</span></span>

<span data-ttu-id="eea08-134">Reguły konfiguracji stanowią mechanizm zapewniający, że produkt wchodzący w skład jednej grupy konfiguracji w BOM wymusza włączenia lub wyłączenia produktu w innej grupie konfiguracji w tym samym BOM.</span><span class="sxs-lookup"><span data-stu-id="eea08-134">The configuration rules represent a mechanism for ensuring that a product included in one configuration group in a BOM enforces either an inclusion or an exclusion of a product in a different configuration group in the same BOM.</span></span>

## <a name="product-modeling-process"></a><span data-ttu-id="eea08-135">Proces modelowania produktu</span><span class="sxs-lookup"><span data-stu-id="eea08-135">Product modeling process</span></span>
<span data-ttu-id="eea08-136">Naturalna sekwencja budowania modelu produktu dla produktu opartego na wymiarach rozpoczyna się od zdefiniowania konfiguracji odpowiednich grup.</span><span class="sxs-lookup"><span data-stu-id="eea08-136">The natural sequence for building a product model for a dimension-based product starts with defining the relevant configuration groups.</span></span> <span data-ttu-id="eea08-137">Należy upewnić się, że zostały zwolnione wszystkie produktów, które będą używane w BOM, do firmy, dla której tworzony jest model produktu.</span><span class="sxs-lookup"><span data-stu-id="eea08-137">It is important to ensure that all products which will be used in the BOM have been relased to the company that the product model is built for.</span></span> <span data-ttu-id="eea08-138">Gdy te blok konstrukcyjne są na swoich miejscach, użytkownik może utworzyć BOM i przypisać grupy konfiguracji do wszystkich odpowiednich wierszy BOM.</span><span class="sxs-lookup"><span data-stu-id="eea08-138">With these building blocks in place, the user can create the BOM and assign configuration groups to all relevant BOM lines.</span></span> <span data-ttu-id="eea08-139">Kiedy BOM jest gotowy, można zdefiniować marszrutę konfiguracji dla uporządkowania grup konfiguracji we właściwej kolejności.</span><span class="sxs-lookup"><span data-stu-id="eea08-139">When the BOM is complete, a configuration route can be defined for ordering the configuration groups in the proper sequence.</span></span> <span data-ttu-id="eea08-140">\[caption id="attachment\_282671" align="alignnone" width="1187"\][![Proces modelowania produktów opartych na wymiarach](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Proces modelowania produktów opartych na wymiarach\[/caption\] Jeśli istnieją pewne produkty z różnych grup konfiguracji, które muszą lub nie mogą być używane razem, można utworzyć reguły konfiguracji, które będą wymuszać relacje tych produktów.</span><span class="sxs-lookup"><span data-stu-id="eea08-140">\[caption id="attachment\_282671" align="alignnone" width="1187"\][![Dimension-based product modeling process](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Dimension-based product modeling process\[/caption\] If there are certain products from different configuration groups that either must or must not be used together, you can create configuration rules that will enforce these product relationships.</span></span> <span data-ttu-id="eea08-141">Po powiązaniu BOM z produktem głównym opartym na wymiarach za pomocą wersji BOM i po zatwierdzeniu oraz aktywowaniu jednego i drugiego, można utworzyć konfiguracje produktów i wprowadzić nazwę dla każdej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="eea08-141">After the BOM has been tied together with a dimension-based product master through a BOM version and both have been approved and activated, you can create product configurations and enter a name for each configuration.</span></span> <span data-ttu-id="eea08-142">Konfiguracje mogą być definiowane zanim jakiekolwiek transakcje są generowane lub można to zrobić, gdy wystąpi potrzeba konkretnych konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="eea08-142">The configurations can be defined before any transactions are generated or it can be done when the need for a certain configuration occurs.</span></span>

### <a name="suggested-use"></a><span data-ttu-id="eea08-143">Sugerowane zastosowanie</span><span class="sxs-lookup"><span data-stu-id="eea08-143">Suggested use</span></span>

<span data-ttu-id="eea08-144">Technologia konfiguracji opartej na wymiarach najlepiej nadaje się do produktów ze ograniczoną zmiennością i kombinacją standardowych rozmiaru, koloru, stylu i konfiguracji wymiarów produktu, i jest ona nieodpowiednia do identyfikowania konkretnych wariantów produktów.</span><span class="sxs-lookup"><span data-stu-id="eea08-144">The dimension-based configuration technology is best used for products with limited variability and the combination of the standard product dimensions size, color, style, and configuration is unsuitable for identifying a specific product variant.</span></span> <span data-ttu-id="eea08-145">Przykładem może być rower z konkretną wysokością ramy, średnicą koła i rytem hamulców oraz różnymi rodzajami przerzutek.</span><span class="sxs-lookup"><span data-stu-id="eea08-145">An example could be bicycle with frame height, wheel size, brake types, and different gears.</span></span>




