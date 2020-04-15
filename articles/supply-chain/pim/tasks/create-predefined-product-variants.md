---
title: Tworzenie wstępnie zdefiniowanych wariantów produktu
description: Ta procedura prowadzi przez proces tworzenia wariantów produktu dla produktu głównego przy użyciu kombinacji wymiarów produktu.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 678e2d7207628529530dcf3decd094583d3dff22
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150127"
---
# <a name="create-predefined-product-variants"></a><span data-ttu-id="6bc32-103">Tworzenie wstępnie zdefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="6bc32-103">Create predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6bc32-104">Ta procedura prowadzi przez proces tworzenia wariantów produktu dla produktu głównego przy użyciu kombinacji wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="6bc32-104">This procedure walks through creating product variants for a product master using the combinations of product dimensions.</span></span> <span data-ttu-id="6bc32-105">Do stworzenia tej procedury wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="6bc32-105">The demo company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-master"></a><span data-ttu-id="6bc32-106">Tworzenie produktu głównego</span><span class="sxs-lookup"><span data-stu-id="6bc32-106">Create a product master</span></span>
1. <span data-ttu-id="6bc32-107">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkty > Produkty główne.</span><span class="sxs-lookup"><span data-stu-id="6bc32-107">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="6bc32-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6bc32-108">Click New.</span></span>
3. <span data-ttu-id="6bc32-109">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="6bc32-110">Ręczne wprowadzenie numeru produktu jest konieczne tylko wtedy, jeśli dla pola numeru produktu nie skonfigurowano sekwencji identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="6bc32-110">Entering a product number manually is only required if no number sequence has been set for the product number field.</span></span> <span data-ttu-id="6bc32-111">Innymi słowy pomiń ten krok, jeśli pole ma ustawioną sekwencję identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="6bc32-111">In other words, skip the step if number sequence has been set for the field.</span></span>  
4. <span data-ttu-id="6bc32-112">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-112">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="6bc32-113">W polu Grupa wymiarów produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-113">In the Product dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="6bc32-114">Wybierz grupę wymiarów produkt SizeCol (rozmiar i kolor).</span><span class="sxs-lookup"><span data-stu-id="6bc32-114">Select the product dimension group SizeCol (Size and Color).</span></span>  
6. <span data-ttu-id="6bc32-115">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6bc32-115">Click OK.</span></span>

## <a name="add-product-dimensions"></a><span data-ttu-id="6bc32-116">Dodawanie wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="6bc32-116">Add product dimensions</span></span>
1. <span data-ttu-id="6bc32-117">Kliknij opcję Wymiary produktu.</span><span class="sxs-lookup"><span data-stu-id="6bc32-117">Click Product dimensions.</span></span>
    * <span data-ttu-id="6bc32-118">W tym przykładzie pokazano, jak ręcznie wprowadzić wymiary produktu.</span><span class="sxs-lookup"><span data-stu-id="6bc32-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="6bc32-119">Można także wybrać grupę rozmiaru, koloru lub stylu zawierającą wartości wymiarów produktu, których chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="6bc32-119">You can also choose to select a size, color or style group that includes the product dimension values you want to use.</span></span>  
2. <span data-ttu-id="6bc32-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6bc32-120">Click New.</span></span>
3. <span data-ttu-id="6bc32-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="6bc32-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="6bc32-122">W polu Rozmiar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-122">In the Size field, enter or select a value.</span></span>
5. <span data-ttu-id="6bc32-123">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-123">In the Name field, type a value.</span></span>
6. <span data-ttu-id="6bc32-124">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6bc32-124">Click New.</span></span>
7. <span data-ttu-id="6bc32-125">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="6bc32-125">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="6bc32-126">W polu Rozmiar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-126">In the Size field, enter or select a value.</span></span>
9. <span data-ttu-id="6bc32-127">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-127">In the Name field, type a value.</span></span>
10. <span data-ttu-id="6bc32-128">Kliknij kartę Kolory.</span><span class="sxs-lookup"><span data-stu-id="6bc32-128">Click the Colors tab.</span></span>
11. <span data-ttu-id="6bc32-129">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6bc32-129">Click New.</span></span>
12. <span data-ttu-id="6bc32-130">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="6bc32-130">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="6bc32-131">W polu Kolor wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-131">In the Color field, enter or select a value.</span></span>
14. <span data-ttu-id="6bc32-132">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-132">In the Name field, type a value.</span></span>
15. <span data-ttu-id="6bc32-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6bc32-133">Click New.</span></span>
16. <span data-ttu-id="6bc32-134">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="6bc32-134">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="6bc32-135">W polu Kolor wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-135">In the Color field, enter or select a value.</span></span>
18. <span data-ttu-id="6bc32-136">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6bc32-136">In the Name field, type a value.</span></span>
19. <span data-ttu-id="6bc32-137">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6bc32-137">Click Save.</span></span>
20. <span data-ttu-id="6bc32-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6bc32-138">Close the page.</span></span>

## <a name="generate-product-variants"></a><span data-ttu-id="6bc32-139">Generowanie wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="6bc32-139">Generate product variants</span></span>
1. <span data-ttu-id="6bc32-140">Kliknij opcję Warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="6bc32-140">Click Product variants.</span></span>
2. <span data-ttu-id="6bc32-141">Kliknij opcję Sugestie dotyczące wariantów.</span><span class="sxs-lookup"><span data-stu-id="6bc32-141">Click Variant suggestions.</span></span>
3. <span data-ttu-id="6bc32-142">Kliknij opcję Zaznacz wszystko.</span><span class="sxs-lookup"><span data-stu-id="6bc32-142">Click Select all.</span></span>
    * <span data-ttu-id="6bc32-143">W tym przykładzie są zaznaczone wszystkie możliwe warianty.</span><span class="sxs-lookup"><span data-stu-id="6bc32-143">In this example, all possible variants are selected.</span></span> <span data-ttu-id="6bc32-144">Jeśli do tworzenia wariantów będzie używany tylko podzbiór możliwych kombinacji wymiarów produktu, można wybrać poszczególne elementy.</span><span class="sxs-lookup"><span data-stu-id="6bc32-144">If only a subset of the possible product dimension combinations will be used to create variants, you can select the individual entries.</span></span>  
4. <span data-ttu-id="6bc32-145">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="6bc32-145">Click Create.</span></span>
    * <span data-ttu-id="6bc32-146">Opisy wszystkich wariantów można wygenerować na podstawie kombinacji wartości wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="6bc32-146">You can generate descriptions for all your variants based on the combination of product dimension values.</span></span> <span data-ttu-id="6bc32-147">Opisy są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="6bc32-147">The descriptions are optional.</span></span>  
5. <span data-ttu-id="6bc32-148">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6bc32-148">Click Save.</span></span>

