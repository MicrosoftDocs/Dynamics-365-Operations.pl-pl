---
title: ROUNDDOWN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUNDDOWN w module Raportowanie elektroniczne (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9221476c1c12a7cc3fe2367cdee3ad44e5cbe381
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686889"
---
# <a name="rounddown-er-function"></a><span data-ttu-id="c8c66-103">ROUNDDOWN, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c8c66-103">ROUNDDOWN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8c66-104">Funkcja `ROUNDDOWN` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej w dół do określonej liczby miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="c8c66-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8c66-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c8c66-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="c8c66-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c8c66-106">Arguments</span></span>

<span data-ttu-id="c8c66-107">`number`: *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="c8c66-107">`number`: *Real*</span></span>

<span data-ttu-id="c8c66-108">Wartość numeryczna do zaokrąglenia w dół.</span><span class="sxs-lookup"><span data-stu-id="c8c66-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="c8c66-109">`decimals`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="c8c66-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="c8c66-110">Wartość numeryczna, która reprezentuje liczbę miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="c8c66-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="c8c66-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c8c66-111">Return values</span></span>

<span data-ttu-id="c8c66-112">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="c8c66-112">*Real*</span></span>

<span data-ttu-id="c8c66-113">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="c8c66-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c8c66-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="c8c66-114">Usage notes</span></span>

<span data-ttu-id="c8c66-115">Ta funkcja zachowuje się jak funkcja [ROUND](er-functions-mathematical-round.md), ale zawsze zaokrągla podaną liczbę do dołu (w stronę zera).</span><span class="sxs-lookup"><span data-stu-id="c8c66-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="c8c66-116">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="c8c66-116">Example 1</span></span>

<span data-ttu-id="c8c66-117">Funkcja `ROUNDDOWN (1200.767, 2)` zaokrągla w dół do dwóch miejsc po przecinku i zwraca wartość **1200.76**.</span><span class="sxs-lookup"><span data-stu-id="c8c66-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="c8c66-118">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="c8c66-118">Example 2</span></span>

<span data-ttu-id="c8c66-119">Funkcja `ROUNDDOWN (1700.767, -3)` zaokrągla w dół do najbliższej wielokrotności 1000 i zwraca wartość **1000**.</span><span class="sxs-lookup"><span data-stu-id="c8c66-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8c66-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c8c66-120">Additional resources</span></span>

[<span data-ttu-id="c8c66-121">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="c8c66-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
