---
title: ROUNDUP, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUNDUP w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: d23a984bd59c4d2d37c407e3fcfed9c7017dcc7f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569342"
---
# <a name="roundup-er-function"></a><span data-ttu-id="9a862-103">ROUNDUP, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="9a862-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a862-104">Funkcja `ROUNDUP` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej w górę do określonej liczby miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="9a862-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a862-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9a862-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="9a862-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="9a862-106">Arguments</span></span>

<span data-ttu-id="9a862-107">`number`: *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="9a862-107">`number`: *Real*</span></span>

<span data-ttu-id="9a862-108">Wartość numeryczna do zaokrąglenia w górę.</span><span class="sxs-lookup"><span data-stu-id="9a862-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="9a862-109">`decimals`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="9a862-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="9a862-110">Wartość numeryczna, która reprezentuje liczbę miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="9a862-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="9a862-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="9a862-111">Return values</span></span>

<span data-ttu-id="9a862-112">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="9a862-112">*Real*</span></span>

<span data-ttu-id="9a862-113">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="9a862-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9a862-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="9a862-114">Usage notes</span></span>

<span data-ttu-id="9a862-115">Ta funkcja zachowuje się jak funkcja [ROUND](er-functions-mathematical-round.md), ale zawsze zaokrągla podaną liczbę do góry (od zera).</span><span class="sxs-lookup"><span data-stu-id="9a862-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="9a862-116">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="9a862-116">Example 1</span></span>

<span data-ttu-id="9a862-117">Funkcja `ROUNDUP (1200.763, 2)` zaokrągla w górę do dwóch miejsc po przecinku i zwraca wartość **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="9a862-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="9a862-118">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="9a862-118">Example 2</span></span>

<span data-ttu-id="9a862-119">Funkcja `ROUNDUP (1200.767, -3)` zaokrągla w górę do najbliższej wielokrotności 1,000 i zwraca wartość **2000**.</span><span class="sxs-lookup"><span data-stu-id="9a862-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a862-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9a862-120">Additional resources</span></span>

[<span data-ttu-id="9a862-121">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="9a862-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]