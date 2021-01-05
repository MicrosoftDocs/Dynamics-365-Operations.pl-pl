---
title: ABS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ABS w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 3c7156b9990397822a6bea9ed8b3df8f65490572
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683288"
---
# <a name="abs-er-function"></a><span data-ttu-id="4835d-103">ABS, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="4835d-103">ABS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4835d-104">Funkcja `ABS` zwraca wartość bezwzględną (moduł) określonej liczby jako wartość *rzeczywistą*.</span><span class="sxs-lookup"><span data-stu-id="4835d-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="4835d-105">Innymi słowy zwraca liczbę bez znaku.</span><span class="sxs-lookup"><span data-stu-id="4835d-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="4835d-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="4835d-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="4835d-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="4835d-107">Arguments</span></span>

<span data-ttu-id="4835d-108">`number`: *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="4835d-108">`number`: *Real*</span></span>

<span data-ttu-id="4835d-109">Wartość liczbowa, dla której chcesz obliczyć moduł.</span><span class="sxs-lookup"><span data-stu-id="4835d-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="4835d-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="4835d-110">Return values</span></span>

<span data-ttu-id="4835d-111">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="4835d-111">*Real*</span></span>

<span data-ttu-id="4835d-112">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="4835d-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="4835d-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="4835d-113">Example</span></span>

<span data-ttu-id="4835d-114">Funkcja `ABS (-1)` zwraca wartość **1**.</span><span class="sxs-lookup"><span data-stu-id="4835d-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4835d-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4835d-115">Additional resources</span></span>

[<span data-ttu-id="4835d-116">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="4835d-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
