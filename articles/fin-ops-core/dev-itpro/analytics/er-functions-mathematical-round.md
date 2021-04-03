---
title: ROUND, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUND w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 716ac0bbc9fec992ec1bbfc99bfc86434bf97984
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570405"
---
# <a name="round-er-function"></a><span data-ttu-id="180b9-103">ROUND, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="180b9-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="180b9-104">Funkcja `ROUND` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej do określonej liczby miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="180b9-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="180b9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="180b9-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="180b9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="180b9-106">Arguments</span></span>

<span data-ttu-id="180b9-107">`number`: *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="180b9-107">`number`: *Real*</span></span>

<span data-ttu-id="180b9-108">Wartość numeryczna do zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="180b9-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="180b9-109">`decimals`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="180b9-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="180b9-110">Wartość numeryczna, która reprezentuje liczbę miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="180b9-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="180b9-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="180b9-111">Return values</span></span>

<span data-ttu-id="180b9-112">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="180b9-112">*Real*</span></span>

<span data-ttu-id="180b9-113">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="180b9-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="180b9-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="180b9-114">Usage notes</span></span>

<span data-ttu-id="180b9-115">Jeśli wartość argumentu `decimals` jest większa niż 0 (zero), podana liczba jest zaokrąglana do tej liczby miejsc po przecinku.</span><span class="sxs-lookup"><span data-stu-id="180b9-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="180b9-116">Jeśli wartość argumentu `decimals` wynosi **0** (zero), podana liczba jest zaokrąglana do najbliższej parzystej liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="180b9-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest even integer.</span></span>

<span data-ttu-id="180b9-117">Jeśli wartość argumentu `decimals` jest mniejsza niż 0 (zero), podana liczba jest zaokrąglana do liczby na lewo od separatora dziesiętnego.</span><span class="sxs-lookup"><span data-stu-id="180b9-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="180b9-118">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="180b9-118">Example 1</span></span>

<span data-ttu-id="180b9-119">Funkcja `ROUND (1200.767, 2)` zaokrągla do dwóch miejsc po przecinku i zwraca wartość **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="180b9-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="180b9-120">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="180b9-120">Example 2</span></span>

<span data-ttu-id="180b9-121">Funkcja `ROUND (1200.767, -3)` zaokrągla do najbliższej wielokrotności 1000 i zwraca wartość **1000**.</span><span class="sxs-lookup"><span data-stu-id="180b9-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="example-3"></a><span data-ttu-id="180b9-122">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="180b9-122">Example 3</span></span>

<span data-ttu-id="180b9-123">`ROUND (1200.5, 0)` zaokrągla do najbliższej parzystej liczby całkowitej i zwraca wartość **1200**, natomiast `ROUND (1201.5, 0)` działa tak samo i zwraca wartość **1202**.</span><span class="sxs-lookup"><span data-stu-id="180b9-123">`ROUND (1200.5, 0)` rounds to the nearest even integer and returns **1200**, while `ROUND (1201.5, 0)` does the same and returns **1202**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="180b9-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="180b9-124">Additional resources</span></span>

[<span data-ttu-id="180b9-125">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="180b9-125">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]