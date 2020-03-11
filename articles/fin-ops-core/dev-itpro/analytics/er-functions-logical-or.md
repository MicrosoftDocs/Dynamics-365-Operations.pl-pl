---
title: OR, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji OR w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 2a850b1cbe7224ab1a7b2bd39ac4667304781cbb
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041683"
---
# <span data-ttu-id="69b97-103"><a name="OR">OR, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="69b97-103"><a name="OR">OR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="69b97-104">Funkcja `OR` zwraca wartość *logiczną* **FALSE**, jeśli żadne wybrane warunki nie zostały spełnione.</span><span class="sxs-lookup"><span data-stu-id="69b97-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="69b97-105">Jeśli dowolny wybrany warunek został spełniony, ta funkcja zwraca wartość *logiczną* **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="69b97-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="69b97-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="69b97-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="69b97-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="69b97-107">Arguments</span></span>

<span data-ttu-id="69b97-108">`condition 1`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="69b97-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="69b97-109">Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane.</span><span class="sxs-lookup"><span data-stu-id="69b97-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="69b97-110">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="69b97-110">This argument is required.</span></span>

<span data-ttu-id="69b97-111">`condition N`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="69b97-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="69b97-112">Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane.</span><span class="sxs-lookup"><span data-stu-id="69b97-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="69b97-113">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="69b97-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="69b97-114">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="69b97-114">Return values</span></span>

<span data-ttu-id="69b97-115">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="69b97-115">*Boolean*</span></span>

<span data-ttu-id="69b97-116">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="69b97-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="69b97-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="69b97-117">Example</span></span>

<span data-ttu-id="69b97-118">Funkcja `OR (1=2, "a"="a")` zwraca wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="69b97-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="69b97-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="69b97-119">Additional resources</span></span>

[<span data-ttu-id="69b97-120">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="69b97-120">Logical functions</span></span>](er-functions-category-logical.md)
