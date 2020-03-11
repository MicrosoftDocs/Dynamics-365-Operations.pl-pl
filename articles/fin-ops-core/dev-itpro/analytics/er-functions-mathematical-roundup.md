---
title: ROUNDUP, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUNDUP w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 1784ab3587a090c8e5535509a1ba52fc85111daa
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041591"
---
# <span data-ttu-id="78132-103"><a name="ROUNDUP">ROUNDUP, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="78132-103"><a name="ROUNDUP">ROUNDUP ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78132-104">Funkcja `ROUNDUP` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej w górę do określonej liczby miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="78132-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="78132-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="78132-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="78132-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="78132-106">Arguments</span></span>

<span data-ttu-id="78132-107">`number`: *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="78132-107">`number`: *Real*</span></span>

<span data-ttu-id="78132-108">Wartość numeryczna do zaokrąglenia w górę.</span><span class="sxs-lookup"><span data-stu-id="78132-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="78132-109">`decimals`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="78132-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="78132-110">Wartość numeryczna, która reprezentuje liczbę miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="78132-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="78132-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="78132-111">Return values</span></span>

<span data-ttu-id="78132-112">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="78132-112">*Real*</span></span>

<span data-ttu-id="78132-113">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="78132-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="78132-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="78132-114">Usage notes</span></span>

<span data-ttu-id="78132-115">Ta funkcja zachowuje się jak funkcja [ROUND](er-functions-mathematical-round.md), ale zawsze zaokrągla podaną liczbę do góry (od zera).</span><span class="sxs-lookup"><span data-stu-id="78132-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="78132-116">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="78132-116">Example 1</span></span>

<span data-ttu-id="78132-117">Funkcja `ROUNDUP (1200.763, 2)` zaokrągla w górę do dwóch miejsc po przecinku i zwraca wartość **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="78132-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="78132-118">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="78132-118">Example 2</span></span>

<span data-ttu-id="78132-119">Funkcja `ROUNDUP (1200.767, -3)` zaokrągla w górę do najbliższej wielokrotności 1,000 i zwraca wartość **2000**.</span><span class="sxs-lookup"><span data-stu-id="78132-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78132-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="78132-120">Additional resources</span></span>

[<span data-ttu-id="78132-121">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="78132-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
