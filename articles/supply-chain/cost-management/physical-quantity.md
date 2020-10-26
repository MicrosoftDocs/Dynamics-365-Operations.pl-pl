---
title: Wartości obiektu zapasów
description: Ten artykuł zawiera informacje o sposobie obliczania wartości obiektu zapasów.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: daa36dad4009cc25b89363dcff6b4496205522e3
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981494"
---
# <a name="inventory-object-values"></a><span data-ttu-id="9758a-103">Wartości obiektu zapasów</span><span class="sxs-lookup"><span data-stu-id="9758a-103">Inventory object values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9758a-104">Ten artykuł zawiera informacje o sposobie obliczania wartości obiektu zapasów.</span><span class="sxs-lookup"><span data-stu-id="9758a-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="9758a-105">Nowa funkcja o nazwie **Ilość fizyczna** pozwala zobaczyć wartości zapasów określonego obiektu magazynu.</span><span class="sxs-lookup"><span data-stu-id="9758a-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="9758a-106">Obiekt kosztów reprezentuje poziom podmiotu, w którym są wykonywane operacje księgowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="9758a-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="9758a-107">Aby uzyskać więcej informacji o obiektach kosztów, zobacz temat [Obiekty kosztów](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="9758a-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="9758a-108">Aby wyświetlić wartości określonego obiektu zapasów, kliknij opcję **Ilość fizyczna** na stronie **Obiekt kosztów**.</span><span class="sxs-lookup"><span data-stu-id="9758a-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="9758a-109">Obliczanie wartości obiektu zapasów:</span><span class="sxs-lookup"><span data-stu-id="9758a-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="9758a-110">Obiekt zapasów.Wartość = Obiekt kosztów.Średni koszt jednostkowy × Obiekt zapasów.Ilość</span><span class="sxs-lookup"><span data-stu-id="9758a-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="9758a-111">Poniższy przykład pokazuje sposób obliczania wartości obiektu zapasów i obiektu kosztów.</span><span class="sxs-lookup"><span data-stu-id="9758a-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="9758a-112">Zarejestrowane są dwa zdarzenia dokumentu przyjęcia produktów dla pozycji A:</span><span class="sxs-lookup"><span data-stu-id="9758a-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="9758a-113">Dokument przyjęcia produktów 1: ilość = 100 sztuk., Kwota = 1000,00 USD, Oddział = 1, Magazyn = 11, Nr partii</span><span class="sxs-lookup"><span data-stu-id="9758a-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="9758a-114">= B1</span><span class="sxs-lookup"><span data-stu-id="9758a-114">= B1</span></span>
-   <span data-ttu-id="9758a-115">Dokument przyjęcia produktów 2: ilość = 50 sztuk., Kwota = 800,00 USD, Oddział = 1, Magazyn = 11, Nr partii</span><span class="sxs-lookup"><span data-stu-id="9758a-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="9758a-116">= B2</span><span class="sxs-lookup"><span data-stu-id="9758a-116">= B2</span></span>

<span data-ttu-id="9758a-117">Poniższa tabela przedstawia wynik obliczeń dla obiektu kosztów.</span><span class="sxs-lookup"><span data-stu-id="9758a-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="9758a-118">Wyniki można wyświetlać na stronie **Obiekt kosztów**.</span><span class="sxs-lookup"><span data-stu-id="9758a-118">You can view the result on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9758a-119">Typ obiektu</span><span class="sxs-lookup"><span data-stu-id="9758a-119">Object type</span></span></th>
<th><span data-ttu-id="9758a-120">Numer pozycji</span><span class="sxs-lookup"><span data-stu-id="9758a-120">Item number</span></span></th>
<th><span data-ttu-id="9758a-121">Oddział</span><span class="sxs-lookup"><span data-stu-id="9758a-121">Site</span></span></th>
<th><span data-ttu-id="9758a-122">Ilość</span><span class="sxs-lookup"><span data-stu-id="9758a-122">Quantity</span></span></th>
<th><span data-ttu-id="9758a-123">Jednostka magazynowa</span><span class="sxs-lookup"><span data-stu-id="9758a-123">Inventory unit</span></span></th>
<th><span data-ttu-id="9758a-124">Wartość</span><span class="sxs-lookup"><span data-stu-id="9758a-124">Value</span></span></th>
<th><span data-ttu-id="9758a-125">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="9758a-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9758a-126">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9758a-126">Cost object</span></span></td>
<td><span data-ttu-id="9758a-127">I</span><span class="sxs-lookup"><span data-stu-id="9758a-127">A</span></span></td>
<td><span data-ttu-id="9758a-128">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="9758a-128">1</span></span></td>
<td><span data-ttu-id="9758a-129">150</span><span class="sxs-lookup"><span data-stu-id="9758a-129">150</span></span></td>
<td><span data-ttu-id="9758a-130">Szt.</span><span class="sxs-lookup"><span data-stu-id="9758a-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="9758a-131">1800,00 USD</span><span class="sxs-lookup"><span data-stu-id="9758a-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="9758a-132">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="9758a-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9758a-133">Poniższa tabela przedstawia wynik obliczeń dla obiektu magazynu.</span><span class="sxs-lookup"><span data-stu-id="9758a-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="9758a-134">Wyniki można wyświetlać, klikając **Ilość fizyczna** na stronie **Obiekt kosztów**.</span><span class="sxs-lookup"><span data-stu-id="9758a-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9758a-135">Typ obiektu</span><span class="sxs-lookup"><span data-stu-id="9758a-135">Object type</span></span></th>
<th><span data-ttu-id="9758a-136">Numer pozycji</span><span class="sxs-lookup"><span data-stu-id="9758a-136">Item number</span></span></th>
<th><span data-ttu-id="9758a-137">Oddział</span><span class="sxs-lookup"><span data-stu-id="9758a-137">Site</span></span></th>
<th><span data-ttu-id="9758a-138">Magazyn</span><span class="sxs-lookup"><span data-stu-id="9758a-138">Warehouse</span></span></th>
<th><span data-ttu-id="9758a-139">Numer partii</span><span class="sxs-lookup"><span data-stu-id="9758a-139">Batch No.</span></span></th>
<th><span data-ttu-id="9758a-140">Ilość</span><span class="sxs-lookup"><span data-stu-id="9758a-140">Quantity</span></span></th>
<th><span data-ttu-id="9758a-141">Jednostka magazynowa</span><span class="sxs-lookup"><span data-stu-id="9758a-141">Inventory unit</span></span></th>
<th><span data-ttu-id="9758a-142">Wartość</span><span class="sxs-lookup"><span data-stu-id="9758a-142">Value</span></span></th>
<th><span data-ttu-id="9758a-143">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="9758a-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9758a-144">Obiekt magazynu</span><span class="sxs-lookup"><span data-stu-id="9758a-144">Inventory object</span></span></td>
<td><span data-ttu-id="9758a-145">I</span><span class="sxs-lookup"><span data-stu-id="9758a-145">A</span></span></td>
<td><span data-ttu-id="9758a-146">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="9758a-146">1</span></span></td>
<td><span data-ttu-id="9758a-147">11</span><span class="sxs-lookup"><span data-stu-id="9758a-147">11</span></span></td>
<td><span data-ttu-id="9758a-148">B1</span><span class="sxs-lookup"><span data-stu-id="9758a-148">B1</span></span></td>
<td><span data-ttu-id="9758a-149">100</span><span class="sxs-lookup"><span data-stu-id="9758a-149">100</span></span></td>
<td><span data-ttu-id="9758a-150">Szt.</span><span class="sxs-lookup"><span data-stu-id="9758a-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="9758a-151">1200,00 USD</span><span class="sxs-lookup"><span data-stu-id="9758a-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="9758a-152">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="9758a-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9758a-153">Obiekt magazynu</span><span class="sxs-lookup"><span data-stu-id="9758a-153">Inventory object</span></span></td>
<td><span data-ttu-id="9758a-154">A</span><span class="sxs-lookup"><span data-stu-id="9758a-154">A</span></span></td>
<td><span data-ttu-id="9758a-155">1</span><span class="sxs-lookup"><span data-stu-id="9758a-155">1</span></span></td>
<td><span data-ttu-id="9758a-156">11</span><span class="sxs-lookup"><span data-stu-id="9758a-156">11</span></span></td>
<td><span data-ttu-id="9758a-157">B2</span><span class="sxs-lookup"><span data-stu-id="9758a-157">B2</span></span></td>
<td><span data-ttu-id="9758a-158">50</span><span class="sxs-lookup"><span data-stu-id="9758a-158">50</span></span></td>
<td><span data-ttu-id="9758a-159">Szt.</span><span class="sxs-lookup"><span data-stu-id="9758a-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="9758a-160">600,00 USD</span><span class="sxs-lookup"><span data-stu-id="9758a-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="9758a-161">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="9758a-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="9758a-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9758a-162">Additional resources</span></span>
--------

[<span data-ttu-id="9758a-163">Obiekty kosztów</span><span class="sxs-lookup"><span data-stu-id="9758a-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="9758a-164">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="9758a-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="9758a-165">Nowości i zmiany</span><span class="sxs-lookup"><span data-stu-id="9758a-165">What's new and changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)



