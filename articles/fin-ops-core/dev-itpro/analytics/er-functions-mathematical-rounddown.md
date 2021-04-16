---
title: ROUNDDOWN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUNDDOWN w module Raportowanie elektroniczne (ER).
author: NickSelin
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
ms.openlocfilehash: 89fc134ec11a47506211ce68ec3aaf966d9a308b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744470"
---
# <a name="rounddown-er-function"></a><span data-ttu-id="41095-103">ROUNDDOWN, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="41095-103">ROUNDDOWN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="41095-104">Funkcja `ROUNDDOWN` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej w dół do określonej liczby miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="41095-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="41095-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="41095-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="41095-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="41095-106">Arguments</span></span>

<span data-ttu-id="41095-107">`number`: *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="41095-107">`number`: *Real*</span></span>

<span data-ttu-id="41095-108">Wartość numeryczna do zaokrąglenia w dół.</span><span class="sxs-lookup"><span data-stu-id="41095-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="41095-109">`decimals`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="41095-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="41095-110">Wartość numeryczna, która reprezentuje liczbę miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="41095-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="41095-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="41095-111">Return values</span></span>

<span data-ttu-id="41095-112">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="41095-112">*Real*</span></span>

<span data-ttu-id="41095-113">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="41095-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="41095-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="41095-114">Usage notes</span></span>

<span data-ttu-id="41095-115">Ta funkcja zachowuje się jak funkcja [ROUND](er-functions-mathematical-round.md), ale zawsze zaokrągla podaną liczbę do dołu (w stronę zera).</span><span class="sxs-lookup"><span data-stu-id="41095-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="41095-116">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="41095-116">Example 1</span></span>

<span data-ttu-id="41095-117">Funkcja `ROUNDDOWN (1200.767, 2)` zaokrągla w dół do dwóch miejsc po przecinku i zwraca wartość **1200.76**.</span><span class="sxs-lookup"><span data-stu-id="41095-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="41095-118">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="41095-118">Example 2</span></span>

<span data-ttu-id="41095-119">Funkcja `ROUNDDOWN (1700.767, -3)` zaokrągla w dół do najbliższej wielokrotności 1000 i zwraca wartość **1000**.</span><span class="sxs-lookup"><span data-stu-id="41095-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="41095-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="41095-120">Additional resources</span></span>

[<span data-ttu-id="41095-121">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="41095-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]