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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435109"
---
# <a name="inventory-object-values"></a><span data-ttu-id="9cdba-103">Wartości obiektu zapasów</span><span class="sxs-lookup"><span data-stu-id="9cdba-103">Inventory object values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9cdba-104">Ten artykuł zawiera informacje o sposobie obliczania wartości obiektu zapasów.</span><span class="sxs-lookup"><span data-stu-id="9cdba-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="9cdba-105">Nowa funkcja o nazwie **Ilość fizyczna** pozwala zobaczyć wartości zapasów określonego obiektu magazynu.</span><span class="sxs-lookup"><span data-stu-id="9cdba-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="9cdba-106">Obiekt kosztów reprezentuje poziom podmiotu, w którym są wykonywane operacje księgowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="9cdba-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="9cdba-107">Aby uzyskać więcej informacji o obiektach kosztów, zobacz temat [Obiekty kosztów](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="9cdba-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="9cdba-108">Aby wyświetlić wartości określonego obiektu zapasów, kliknij opcję **Ilość fizyczna** na stronie **Obiekt kosztów**.</span><span class="sxs-lookup"><span data-stu-id="9cdba-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="9cdba-109">Obliczanie wartości obiektu zapasów:</span><span class="sxs-lookup"><span data-stu-id="9cdba-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="9cdba-110">Obiekt zapasów.Wartość = Obiekt kosztów.Średni koszt jednostkowy × Obiekt zapasów.Ilość</span><span class="sxs-lookup"><span data-stu-id="9cdba-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="9cdba-111">Poniższy przykład pokazuje sposób obliczania wartości obiektu zapasów i obiektu kosztów.</span><span class="sxs-lookup"><span data-stu-id="9cdba-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="9cdba-112">Zarejestrowane są dwa zdarzenia dokumentu przyjęcia produktów dla pozycji A:</span><span class="sxs-lookup"><span data-stu-id="9cdba-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="9cdba-113">Dokument przyjęcia produktów 1: ilość = 100 sztuk., Kwota = 1000,00 USD, Oddział = 1, Magazyn = 11, Nr partii</span><span class="sxs-lookup"><span data-stu-id="9cdba-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="9cdba-114">= B1</span><span class="sxs-lookup"><span data-stu-id="9cdba-114">= B1</span></span>
-   <span data-ttu-id="9cdba-115">Dokument przyjęcia produktów 2: ilość = 50 sztuk., Kwota = 800,00 USD, Oddział = 1, Magazyn = 11, Nr partii</span><span class="sxs-lookup"><span data-stu-id="9cdba-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="9cdba-116">= B2</span><span class="sxs-lookup"><span data-stu-id="9cdba-116">= B2</span></span>

<span data-ttu-id="9cdba-117">Poniższa tabela przedstawia wynik obliczeń dla obiektu kosztów.</span><span class="sxs-lookup"><span data-stu-id="9cdba-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="9cdba-118">Wyniki można wyświetlać na stronie **Obiekt kosztów**.</span><span class="sxs-lookup"><span data-stu-id="9cdba-118">You can view the result on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="9cdba-119">Typ obiektu</span><span class="sxs-lookup"><span data-stu-id="9cdba-119">Object type</span></span></th>
<th><span data-ttu-id="9cdba-120">Numer pozycji</span><span class="sxs-lookup"><span data-stu-id="9cdba-120">Item number</span></span></th>
<th><span data-ttu-id="9cdba-121">Oddział</span><span class="sxs-lookup"><span data-stu-id="9cdba-121">Site</span></span></th>
<th><span data-ttu-id="9cdba-122">Ilość</span><span class="sxs-lookup"><span data-stu-id="9cdba-122">Quantity</span></span></th>
<th><span data-ttu-id="9cdba-123">Jednostka magazynowa</span><span class="sxs-lookup"><span data-stu-id="9cdba-123">Inventory unit</span></span></th>
<th><span data-ttu-id="9cdba-124">Wartość</span><span class="sxs-lookup"><span data-stu-id="9cdba-124">Value</span></span></th>
<th><span data-ttu-id="9cdba-125">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="9cdba-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9cdba-126">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9cdba-126">Cost object</span></span></td>
<td><span data-ttu-id="9cdba-127">I</span><span class="sxs-lookup"><span data-stu-id="9cdba-127">A</span></span></td>
<td><span data-ttu-id="9cdba-128">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="9cdba-128">1</span></span></td>
<td><span data-ttu-id="9cdba-129">150</span><span class="sxs-lookup"><span data-stu-id="9cdba-129">150</span></span></td>
<td><span data-ttu-id="9cdba-130">Szt.</span><span class="sxs-lookup"><span data-stu-id="9cdba-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="9cdba-131">1800,00 USD</span><span class="sxs-lookup"><span data-stu-id="9cdba-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="9cdba-132">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="9cdba-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9cdba-133">Poniższa tabela przedstawia wynik obliczeń dla obiektu magazynu.</span><span class="sxs-lookup"><span data-stu-id="9cdba-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="9cdba-134">Wyniki można wyświetlać, klikając **Ilość fizyczna** na stronie **Obiekt kosztów**.</span><span class="sxs-lookup"><span data-stu-id="9cdba-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="9cdba-135">Typ obiektu</span><span class="sxs-lookup"><span data-stu-id="9cdba-135">Object type</span></span></th>
<th><span data-ttu-id="9cdba-136">Numer pozycji</span><span class="sxs-lookup"><span data-stu-id="9cdba-136">Item number</span></span></th>
<th><span data-ttu-id="9cdba-137">Oddział</span><span class="sxs-lookup"><span data-stu-id="9cdba-137">Site</span></span></th>
<th><span data-ttu-id="9cdba-138">Magazyn</span><span class="sxs-lookup"><span data-stu-id="9cdba-138">Warehouse</span></span></th>
<th><span data-ttu-id="9cdba-139">Numer partii</span><span class="sxs-lookup"><span data-stu-id="9cdba-139">Batch No.</span></span></th>
<th><span data-ttu-id="9cdba-140">Ilość</span><span class="sxs-lookup"><span data-stu-id="9cdba-140">Quantity</span></span></th>
<th><span data-ttu-id="9cdba-141">Jednostka magazynowa</span><span class="sxs-lookup"><span data-stu-id="9cdba-141">Inventory unit</span></span></th>
<th><span data-ttu-id="9cdba-142">Wartość</span><span class="sxs-lookup"><span data-stu-id="9cdba-142">Value</span></span></th>
<th><span data-ttu-id="9cdba-143">Średni koszt jednostkowy</span><span class="sxs-lookup"><span data-stu-id="9cdba-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9cdba-144">Obiekt magazynu</span><span class="sxs-lookup"><span data-stu-id="9cdba-144">Inventory object</span></span></td>
<td><span data-ttu-id="9cdba-145">I</span><span class="sxs-lookup"><span data-stu-id="9cdba-145">A</span></span></td>
<td><span data-ttu-id="9cdba-146">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="9cdba-146">1</span></span></td>
<td><span data-ttu-id="9cdba-147">11</span><span class="sxs-lookup"><span data-stu-id="9cdba-147">11</span></span></td>
<td><span data-ttu-id="9cdba-148">B1</span><span class="sxs-lookup"><span data-stu-id="9cdba-148">B1</span></span></td>
<td><span data-ttu-id="9cdba-149">100</span><span class="sxs-lookup"><span data-stu-id="9cdba-149">100</span></span></td>
<td><span data-ttu-id="9cdba-150">Szt.</span><span class="sxs-lookup"><span data-stu-id="9cdba-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="9cdba-151">1200,00 USD</span><span class="sxs-lookup"><span data-stu-id="9cdba-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="9cdba-152">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="9cdba-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9cdba-153">Obiekt magazynu</span><span class="sxs-lookup"><span data-stu-id="9cdba-153">Inventory object</span></span></td>
<td><span data-ttu-id="9cdba-154">A</span><span class="sxs-lookup"><span data-stu-id="9cdba-154">A</span></span></td>
<td><span data-ttu-id="9cdba-155">1</span><span class="sxs-lookup"><span data-stu-id="9cdba-155">1</span></span></td>
<td><span data-ttu-id="9cdba-156">11</span><span class="sxs-lookup"><span data-stu-id="9cdba-156">11</span></span></td>
<td><span data-ttu-id="9cdba-157">B2</span><span class="sxs-lookup"><span data-stu-id="9cdba-157">B2</span></span></td>
<td><span data-ttu-id="9cdba-158">50</span><span class="sxs-lookup"><span data-stu-id="9cdba-158">50</span></span></td>
<td><span data-ttu-id="9cdba-159">Szt.</span><span class="sxs-lookup"><span data-stu-id="9cdba-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="9cdba-160">600,00 USD</span><span class="sxs-lookup"><span data-stu-id="9cdba-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="9cdba-161">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="9cdba-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="9cdba-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9cdba-162">Additional resources</span></span>
--------

[<span data-ttu-id="9cdba-163">Obiekty kosztów</span><span class="sxs-lookup"><span data-stu-id="9cdba-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="9cdba-164">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="9cdba-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="9cdba-165">Nowości i zmiany</span><span class="sxs-lookup"><span data-stu-id="9cdba-165">What's new and changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)



