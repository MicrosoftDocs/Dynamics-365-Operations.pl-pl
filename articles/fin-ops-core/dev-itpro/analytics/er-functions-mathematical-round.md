---
title: ROUND, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUND w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9384d5975e4a25d18ff741f87431daa4b0bbd7e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917081"
---
# <span data-ttu-id="ad2fd-103"><a name="ROUND">ROUND, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="ad2fd-103"><a name="ROUND">ROUND ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad2fd-104">Funkcja `ROUND` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej do określonej liczby miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="ad2fd-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="ad2fd-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ad2fd-105">Syntax</span></span>

```
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="ad2fd-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ad2fd-106">Arguments</span></span>

<span data-ttu-id="ad2fd-107">`number`: *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="ad2fd-107">`number`: *Real*</span></span>

<span data-ttu-id="ad2fd-108">Wartość numeryczna do zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="ad2fd-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="ad2fd-109">`decimals`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="ad2fd-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="ad2fd-110">Wartość numeryczna, która reprezentuje liczbę miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="ad2fd-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="ad2fd-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="ad2fd-111">Return values</span></span>

<span data-ttu-id="ad2fd-112">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="ad2fd-112">*Real*</span></span>

<span data-ttu-id="ad2fd-113">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="ad2fd-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ad2fd-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="ad2fd-114">Usage notes</span></span>

<span data-ttu-id="ad2fd-115">Jeśli wartość argumentu `decimals` jest większa niż 0 (zero), podana liczba jest zaokrąglana do tej liczby miejsc po przecinku.</span><span class="sxs-lookup"><span data-stu-id="ad2fd-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="ad2fd-116">Jeśli wartość argumentu `decimals` wynosi **0** (zero), podana liczba jest zaokrąglana do najbliższej liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="ad2fd-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="ad2fd-117">Jeśli wartość argumentu `decimals` jest mniejsza niż 0 (zero), podana liczba jest zaokrąglana do liczby na lewo od separatora dziesiętnego.</span><span class="sxs-lookup"><span data-stu-id="ad2fd-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="ad2fd-118">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="ad2fd-118">Example 1</span></span>

<span data-ttu-id="ad2fd-119">Funkcja `ROUND (1200.767, 2)` zaokrągla do dwóch miejsc po przecinku i zwraca wartość **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="ad2fd-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ad2fd-120">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="ad2fd-120">Example 2</span></span>

<span data-ttu-id="ad2fd-121">Funkcja `ROUND (1200.767, -3)` zaokrągla do najbliższej wielokrotności 1000 i zwraca wartość **1000**.</span><span class="sxs-lookup"><span data-stu-id="ad2fd-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ad2fd-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ad2fd-122">Additional resources</span></span>

[<span data-ttu-id="ad2fd-123">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="ad2fd-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)
