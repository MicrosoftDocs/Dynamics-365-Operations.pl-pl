---
title: Omówienie konfiguracji produktów opartych na wymiarach
description: Konfiguracja produktu oparta na wymiarach to prosty sposób tworzenia wielu wariantów produktu z jednego produktu głównego i jego BOM.
author: cvocph
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad8c2c82f9104a350d37534e4d70372da82f40a7
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815049"
---
# <a name="dimension-based-product-configuration-overview"></a><span data-ttu-id="79c38-103">Omówienie konfiguracji produktów opartych na wymiarach</span><span class="sxs-lookup"><span data-stu-id="79c38-103">Dimension-based product configuration overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79c38-104">Konfiguracja produktu oparta na wymiarach to prosty sposób tworzenia wielu wariantów produktu z jednego produktu głównego i jego BOM.</span><span class="sxs-lookup"><span data-stu-id="79c38-104">Dimension-based product configuration represents a simple solution for creating many product variants from a single product master and its bill of materials.</span></span>

<span data-ttu-id="79c38-105">Konfiguracja produktów oparta na wymiarach jest jedną z trzech wbudowanych technologii konfiguracji produktów.</span><span class="sxs-lookup"><span data-stu-id="79c38-105">Dimension-based product configuration is one of the three built-in product configuration technologies.</span></span> <span data-ttu-id="79c38-106">Dwie pozostałe konfiguracje to wstępnie zdefiniowane warianty i konfiguracja oparta na ograniczeniach.</span><span class="sxs-lookup"><span data-stu-id="79c38-106">The two other technologies are predefined variants and constraint-based configuration.</span></span> <span data-ttu-id="79c38-107">Wszystkie trzy technologie używają produktu głównego jako punktu wyjścia i umożliwiają użytkownikowi tworzenie wielu wariantów dla jednego produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="79c38-107">All three technologies use a product master as the starting point and allow the user to create many product variants for one product master.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="79c38-108">Podstawowe pojęcia</span><span class="sxs-lookup"><span data-stu-id="79c38-108">Key concepts</span></span>
<span data-ttu-id="79c38-109">Podstawą konfiguracji opartej na wymiarach są następujące pojęcia:</span><span class="sxs-lookup"><span data-stu-id="79c38-109">Dimension-based product configuration is based on the following key concepts:</span></span>

-   <span data-ttu-id="79c38-110">Produkty główne</span><span class="sxs-lookup"><span data-stu-id="79c38-110">Product masters</span></span>
-   <span data-ttu-id="79c38-111">Konfiguracja wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="79c38-111">Configuration product dimension</span></span>
-   <span data-ttu-id="79c38-112">Grupy konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79c38-112">Configuration groups</span></span>
-   <span data-ttu-id="79c38-113">Lista składowa (BOM)</span><span class="sxs-lookup"><span data-stu-id="79c38-113">Bill of materials (BOM)</span></span>
-   <span data-ttu-id="79c38-114">Marszruta konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79c38-114">Configuration route</span></span>
-   <span data-ttu-id="79c38-115">Reguły konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79c38-115">Configuration rules</span></span>

### <a name="product-masters"></a><span data-ttu-id="79c38-116">Produkty główne</span><span class="sxs-lookup"><span data-stu-id="79c38-116">Product masters</span></span>

<span data-ttu-id="79c38-117">Produkt główny jest punktem wyjścia dla każdego procesu konfiguracji produktów.</span><span class="sxs-lookup"><span data-stu-id="79c38-117">A product master is the starting point for any product configuration process.</span></span> <span data-ttu-id="79c38-118">Konfiguracja produktu oparta na wymiarach wymaga produktu głównego z konkretną technologią konfiguracji i grupy wymiaru produktu zawierającej wymiar produktu konfigurowanego.</span><span class="sxs-lookup"><span data-stu-id="79c38-118">For the dimension-based product configuration, you need a product master with this particular configuration technology and a product dimension group that includes the configuration product dimension.</span></span>

### <a name="configuration-product-dimension"></a><span data-ttu-id="79c38-119">Konfiguracja wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="79c38-119">Configuration product dimension</span></span>

<span data-ttu-id="79c38-120">Wymiar konfiguracji produktu jest używany do identyfikacji wariantów produktów dla produktu głównego z technologią konfiguracji opartą na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="79c38-120">The configuration product dimension is used to identify the product variants for a product master with the dimension-based configuration technology.</span></span> <span data-ttu-id="79c38-121">Wartość wymiaru konfiguracji jest określona przez użytkownika i powinna pomagać w identyfikowaniu poszczególnych kombinacji.</span><span class="sxs-lookup"><span data-stu-id="79c38-121">The configuration dimension value is entered by the user and should help to identify the individual product variants.</span></span>

### <a name="configuration-groups"></a><span data-ttu-id="79c38-122">Grupy konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79c38-122">Configuration groups</span></span>

<span data-ttu-id="79c38-123">Grupy konfiguracji są określane w centralnym repozytorium i mogą być używane dla wszystkich modeli konfiguracji produktu opartych na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="79c38-123">Configuration groups are defined in a central repository and can be used for all dimension-based product configuration models.</span></span> <span data-ttu-id="79c38-124">Grupy konfiguracji są skojarzone z poszczególnymi wierszami BOM i spajają grupę wierszy, które wzajemnie się wykluczają.</span><span class="sxs-lookup"><span data-stu-id="79c38-124">Configuration groups are associated to the individual BOM lines and hold together a group of lines that are mutually exclusive.</span></span> <span data-ttu-id="79c38-125">Oznacza to, że dla jednego wariantu produktu można wybrać tylko jeden wiersz w grupie.</span><span class="sxs-lookup"><span data-stu-id="79c38-125">This means that only one line in a group can be selected for a single product variant.</span></span>

### <a name="bill-of-materials-bom"></a><span data-ttu-id="79c38-126">Lista składowa (BOM)</span><span class="sxs-lookup"><span data-stu-id="79c38-126">Bill of materials (BOM)</span></span>

<span data-ttu-id="79c38-127">BOM odpowiada blokom konstrukcyjnym dla konfiguracji produktu opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="79c38-127">The BOM represent the building blocks for a dimension-based product configuration.</span></span> <span data-ttu-id="79c38-128">Musi zawierać wszystkie różne produkty, które mogą być używane w dowolnym wariancie produktu.</span><span class="sxs-lookup"><span data-stu-id="79c38-128">It must include all the different products that can be used in any product variant.</span></span> <span data-ttu-id="79c38-129">Każdy wiersz w BOM może się odwoływać do grupy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="79c38-129">Each line in the BOM can reference a configuration group.</span></span> <span data-ttu-id="79c38-130">Jeśli wiersz nie odwołuje się do grupy konfiguracji, będzie on uwzględniony we wszystkich wariantach produktu.</span><span class="sxs-lookup"><span data-stu-id="79c38-130">If a line doesn’t reference a configuration group, it will be included in all product variants.</span></span>

### <a name="configuration-route"></a><span data-ttu-id="79c38-131">Marszruta konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79c38-131">Configuration route</span></span>

<span data-ttu-id="79c38-132">Marszruta konfiguracji określa kolejność grup konfiguracji, w jakiej będą one wyświetlane użytkownikowi w procesie konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="79c38-132">The configuration route determines the sequence of the configuration groups, as they will be displayed to the user during the product configuration process.</span></span>

### <a name="configuration-rules"></a><span data-ttu-id="79c38-133">Reguły konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79c38-133">Configuration rules</span></span>

<span data-ttu-id="79c38-134">Reguły konfiguracji stanowią mechanizm zapewniający, że produkt wchodzący w skład jednej grupy konfiguracji w BOM wymusza włączenia lub wyłączenia produktu w innej grupie konfiguracji w tym samym BOM.</span><span class="sxs-lookup"><span data-stu-id="79c38-134">The configuration rules represent a mechanism for ensuring that a product included in one configuration group in a BOM enforces either an inclusion or an exclusion of a product in a different configuration group in the same BOM.</span></span>

## <a name="product-modeling-process"></a><span data-ttu-id="79c38-135">Proces modelowania produktu</span><span class="sxs-lookup"><span data-stu-id="79c38-135">Product modeling process</span></span>
<span data-ttu-id="79c38-136">Naturalna sekwencja budowania modelu produktu dla produktu opartego na wymiarach rozpoczyna się od zdefiniowania konfiguracji odpowiednich grup.</span><span class="sxs-lookup"><span data-stu-id="79c38-136">The natural sequence for building a product model for a dimension-based product starts with defining the relevant configuration groups.</span></span> <span data-ttu-id="79c38-137">Należy upewnić się, że wszystkie produkty, które będą używane w BOM, zostały wydane firmie, dla której tworzony jest model produktu.</span><span class="sxs-lookup"><span data-stu-id="79c38-137">It is important to ensure that all products which will be used in the BOM have been released to the company that the product model is built for.</span></span> <span data-ttu-id="79c38-138">Gdy te blok konstrukcyjne są na swoich miejscach, użytkownik może utworzyć BOM i przypisać grupy konfiguracji do wszystkich odpowiednich wierszy BOM.</span><span class="sxs-lookup"><span data-stu-id="79c38-138">With these building blocks in place, the user can create the BOM and assign configuration groups to all relevant BOM lines.</span></span> <span data-ttu-id="79c38-139">Kiedy BOM jest gotowy, można zdefiniować marszrutę konfiguracji dla uporządkowania grup konfiguracji we właściwej kolejności.</span><span class="sxs-lookup"><span data-stu-id="79c38-139">When the BOM is complete, a configuration route can be defined for ordering the configuration groups in the proper sequence.</span></span> <span data-ttu-id="79c38-140">[![Proces modelowania produktów opartych na wymiarach](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Jeżeli istnieją określone produkty z różnych grup konfiguracji, które muszą lub nie mogą być używane razem, można utworzyć reguły konfiguracji, które wymuszą relacje między tymi produktami.</span><span class="sxs-lookup"><span data-stu-id="79c38-140">[![Dimension-based product modeling process](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) If there are certain products from different configuration groups that either must or must not be used together, you can create configuration rules that will enforce these product relationships.</span></span> <span data-ttu-id="79c38-141">Po powiązaniu BOM z produktem głównym opartym na wymiarach za pomocą wersji BOM i po zatwierdzeniu oraz aktywowaniu jednego i drugiego, można utworzyć konfiguracje produktów i wprowadzić nazwę dla każdej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="79c38-141">After the BOM has been tied together with a dimension-based product master through a BOM version and both have been approved and activated, you can create product configurations and enter a name for each configuration.</span></span> <span data-ttu-id="79c38-142">Konfiguracje mogą być definiowane zanim jakiekolwiek transakcje są generowane lub można to zrobić, gdy wystąpi potrzeba konkretnych konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="79c38-142">The configurations can be defined before any transactions are generated or it can be done when the need for a certain configuration occurs.</span></span>

### <a name="suggested-use"></a><span data-ttu-id="79c38-143">Sugerowane zastosowanie</span><span class="sxs-lookup"><span data-stu-id="79c38-143">Suggested use</span></span>

<span data-ttu-id="79c38-144">Technologia konfiguracji opartej na wymiarach najlepiej nadaje się do produktów ze ograniczoną zmiennością i kombinacją standardowych rozmiaru, koloru, stylu i konfiguracji wymiarów produktu, i jest ona nieodpowiednia do identyfikowania konkretnych wariantów produktów.</span><span class="sxs-lookup"><span data-stu-id="79c38-144">The dimension-based configuration technology is best used for products with limited variability and the combination of the standard product dimensions size, color, style, and configuration is unsuitable for identifying a specific product variant.</span></span> <span data-ttu-id="79c38-145">Przykładem może być rower z konkretną wysokością ramy, średnicą koła i rytem hamulców oraz różnymi rodzajami przerzutek.</span><span class="sxs-lookup"><span data-stu-id="79c38-145">An example could be bicycle with frame height, wheel size, brake types, and different gears.</span></span>

### <a name="next-step"></a><span data-ttu-id="79c38-146">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="79c38-146">Next step</span></span> 

<span data-ttu-id="79c38-147">Poniżej znajduje się wykaz ośmiu przewodników po zadaniach w kolejności, w jakiej należy je ukończyć.</span><span class="sxs-lookup"><span data-stu-id="79c38-147">The following eight task guides are listed in the order in which you should complete them.</span></span> 

1.  [<span data-ttu-id="79c38-148">Tworzenie produktu głównego opartego na wymiarach</span><span class="sxs-lookup"><span data-stu-id="79c38-148">Create a dimension-based product master</span></span>](tasks/create-dimension-based-product-master.md)
2.  [<span data-ttu-id="79c38-149">Zwalnianie produktu głównego opartego na wymiarach</span><span class="sxs-lookup"><span data-stu-id="79c38-149">Release a dimension-based product master</span></span>](tasks/release-dimension-based-product-master.md)
3.  [<span data-ttu-id="79c38-150">Wypełnianie podstawowych ustawień zwolnionego produktu głównego</span><span class="sxs-lookup"><span data-stu-id="79c38-150">Complete basic setup of a released product master</span></span>](tasks/complete-basic-setup-released-product-master.md)
4.  [<span data-ttu-id="79c38-151">Definiowanie grup konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79c38-151">Define configuration groups</span></span>](tasks/define-configuration-groups.md)
5.  [<span data-ttu-id="79c38-152">Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach</span><span class="sxs-lookup"><span data-stu-id="79c38-152">Create a bill of materials for a dimension-based product master</span></span>](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [<span data-ttu-id="79c38-153">Definiowanie marszrut konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79c38-153">Define configuration routes</span></span>](tasks/define-configuration-route.md)
7.  [<span data-ttu-id="79c38-154">Tworzenie reguł konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79c38-154">Create configuration rules</span></span>](tasks/create-configuration-rules.md)
8.  [<span data-ttu-id="79c38-155">Tworzenie konfiguracji opartych na wymiarach</span><span class="sxs-lookup"><span data-stu-id="79c38-155">Create dimension-based configurations</span></span>](tasks/create-dimension-based-configurations.md)

