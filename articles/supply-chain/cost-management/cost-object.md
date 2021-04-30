---
title: Obiekty kosztów
description: Ten artykuł zawiera informacje o obiektach kosztów. Wyjaśniono w nim też sposób kumulowania kosztów i ilości. Obiekt kosztów to jednostka, dla której są kumulowane koszty i ilości. Jednostką obiektu kosztów może być produkt lub wariant produktu, takich jak wariant pod względem koloru i stylu.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6829f24b8efa29b39f5ed742d8ca99e09bcef01
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910360"
---
# <a name="cost-objects"></a><span data-ttu-id="0f671-105">Obiekty kosztów</span><span class="sxs-lookup"><span data-stu-id="0f671-105">Cost objects</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f671-106">Ten artykuł zawiera informacje o obiektach kosztów. Wyjaśniono w nim też sposób kumulowania kosztów i ilości.</span><span class="sxs-lookup"><span data-stu-id="0f671-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="0f671-107">Obiekt kosztów to jednostka, dla której są kumulowane koszty i ilości.</span><span class="sxs-lookup"><span data-stu-id="0f671-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="0f671-108">Jednostką obiektu kosztów może być produkt lub wariant produktu, takich jak wariant pod względem koloru i stylu.</span><span class="sxs-lookup"><span data-stu-id="0f671-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

## <a name="cost-objects"></a><span data-ttu-id="0f671-109">Obiekty kosztów</span><span class="sxs-lookup"><span data-stu-id="0f671-109">Cost objects</span></span>

<span data-ttu-id="0f671-110">Na stronie **Obiekty kosztów** znajduje się lista wszystkich obiektów kosztów, które są zarejestrowane dla produktu.</span><span class="sxs-lookup"><span data-stu-id="0f671-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="0f671-111">Obiekty kosztów są definiowane na podstawie danych z następujących źródeł:</span><span class="sxs-lookup"><span data-stu-id="0f671-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="0f671-112">Produkt</span><span class="sxs-lookup"><span data-stu-id="0f671-112">Product</span></span>
-   <span data-ttu-id="0f671-113">Grupa wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="0f671-113">Product dimension group</span></span>
-   <span data-ttu-id="0f671-114">Grupa wymiarów magazynowania</span><span class="sxs-lookup"><span data-stu-id="0f671-114">Storage dimension group</span></span>
-   <span data-ttu-id="0f671-115">Grupa wymiarów śledzenia</span><span class="sxs-lookup"><span data-stu-id="0f671-115">Tracking dimension group</span></span>

<span data-ttu-id="0f671-116">**Uwaga:** obiekt kosztu reprezentuje tylko element kosztów typu **Materiały bezpośrednie**.</span><span class="sxs-lookup"><span data-stu-id="0f671-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="0f671-117">Obiekt kosztów i obiekt magazynu różnią się od siebie tym, że obiekt kosztów jest definiowany przez wymiary magazynowe, które są wybrane dla magazynu finansowego.</span><span class="sxs-lookup"><span data-stu-id="0f671-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="0f671-118">Towar może na przykład mieć następującą konfigurację:</span><span class="sxs-lookup"><span data-stu-id="0f671-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="0f671-119">**Witryna:** Magazyn fizyczny = Tak, Magazyn finansowy = Tak</span><span class="sxs-lookup"><span data-stu-id="0f671-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="0f671-120">**Magazyn:** Magazyn fizyczny = Tak, Magazyn finansowy = Nie</span><span class="sxs-lookup"><span data-stu-id="0f671-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="0f671-121">**Nr partii:** Magazyn fizyczny = Tak, Magazyn finansowy = Nie</span><span class="sxs-lookup"><span data-stu-id="0f671-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="0f671-122">W poniższej tabeli przedstawiono, co jest przedmiotem kosztu i co jest obiektem magazynu.</span><span class="sxs-lookup"><span data-stu-id="0f671-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="0f671-123">Typ obiektu</span><span class="sxs-lookup"><span data-stu-id="0f671-123">Object type</span></span>      | <span data-ttu-id="0f671-124">Numer pozycji</span><span class="sxs-lookup"><span data-stu-id="0f671-124">Item number</span></span> | <span data-ttu-id="0f671-125">Oddział</span><span class="sxs-lookup"><span data-stu-id="0f671-125">Site</span></span> | <span data-ttu-id="0f671-126">Magazyn</span><span class="sxs-lookup"><span data-stu-id="0f671-126">Warehouse</span></span> | <span data-ttu-id="0f671-127">Numer partii</span><span class="sxs-lookup"><span data-stu-id="0f671-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="0f671-128">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="0f671-128">Cost object</span></span>      | <span data-ttu-id="0f671-129">x</span><span class="sxs-lookup"><span data-stu-id="0f671-129">x</span></span>           | <span data-ttu-id="0f671-130">x</span><span class="sxs-lookup"><span data-stu-id="0f671-130">x</span></span>    |           |           |
| <span data-ttu-id="0f671-131">Obiekt magazynu</span><span class="sxs-lookup"><span data-stu-id="0f671-131">Inventory object</span></span> | <span data-ttu-id="0f671-132">x</span><span class="sxs-lookup"><span data-stu-id="0f671-132">x</span></span>           | <span data-ttu-id="0f671-133">x</span><span class="sxs-lookup"><span data-stu-id="0f671-133">x</span></span>    |  <span data-ttu-id="0f671-134">x</span><span class="sxs-lookup"><span data-stu-id="0f671-134">x</span></span>        | <span data-ttu-id="0f671-135">x</span><span class="sxs-lookup"><span data-stu-id="0f671-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="0f671-136">Akumulacja kosztów i ilości</span><span class="sxs-lookup"><span data-stu-id="0f671-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="0f671-137">Pole **Wartość** zawiera sumę z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="0f671-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="0f671-138">Fizyczna wartość kosztu</span><span class="sxs-lookup"><span data-stu-id="0f671-138">Physical cost amount</span></span>
    -   <span data-ttu-id="0f671-139">Wartość finansowa</span><span class="sxs-lookup"><span data-stu-id="0f671-139">Financial cost amount</span></span>
    -   <span data-ttu-id="0f671-140">Korekty</span><span class="sxs-lookup"><span data-stu-id="0f671-140">Adjustments</span></span>
-   <span data-ttu-id="0f671-141">Pole **Ilość** zawiera sumę z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="0f671-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="0f671-142">Odebrano</span><span class="sxs-lookup"><span data-stu-id="0f671-142">Received</span></span>
    -   <span data-ttu-id="0f671-143">Wydane</span><span class="sxs-lookup"><span data-stu-id="0f671-143">Deducted</span></span>
    -   <span data-ttu-id="0f671-144">Zaksięgowana ilość</span><span class="sxs-lookup"><span data-stu-id="0f671-144">Posted quantity</span></span>
-   <span data-ttu-id="0f671-145">Pole **Średni koszt jednostkowy** jest polem obliczanym.</span><span class="sxs-lookup"><span data-stu-id="0f671-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="0f671-146">Wartość jest obliczana przez podzielenie wartości **Wartość** przez wartość **Ilość**.</span><span class="sxs-lookup"><span data-stu-id="0f671-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="0f671-147">**Uwaga:** Parametr **Włącz wartość fizyczną** nie ma wpływu na wcześniejsze obliczenia.</span><span class="sxs-lookup"><span data-stu-id="0f671-147">**Note:** The \*\*Include physical value \*\*parameter has no effect on the preceding calculations.</span></span>

<a name="additional-resources"></a><span data-ttu-id="0f671-148">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0f671-148">Additional resources</span></span>
--------

[<span data-ttu-id="0f671-149">Grupa wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="0f671-149">Product dimension group</span></span>](/dynamicsax-2012/appuser-itpro/about-product-dimensions)

[<span data-ttu-id="0f671-150">Grupa wymiarów magazynowania</span><span class="sxs-lookup"><span data-stu-id="0f671-150">Storage dimension group</span></span>](/dynamicsax-2012//storage-dimension-groups-form)

[<span data-ttu-id="0f671-151">Grupa wymiarów śledzenia</span><span class="sxs-lookup"><span data-stu-id="0f671-151">Tracking dimension group</span></span>](/dynamicsax-2012//tracking-dimension-groups-form)

[<span data-ttu-id="0f671-152">Nowości i zmiany</span><span class="sxs-lookup"><span data-stu-id="0f671-152">What's new or changed</span></span>](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)

[<span data-ttu-id="0f671-153">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="0f671-153">Cost entries</span></span>](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]