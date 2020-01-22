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
ms.openlocfilehash: 81a596f5206b23001feea553adcdf6c904572775
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917127"
---
# <span data-ttu-id="d4a83-103"><a name="OR">OR, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="d4a83-103"><a name="OR">OR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d4a83-104">Funkcja `OR` zwraca wartość *logiczną* **FALSE**, jeśli żadne wybrane warunki nie zostały spełnione.</span><span class="sxs-lookup"><span data-stu-id="d4a83-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="d4a83-105">Jeśli dowolny wybrany warunek został spełniony, ta funkcja zwraca wartość *logiczną* **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="d4a83-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="d4a83-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="d4a83-106">Syntax</span></span>

```
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="d4a83-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d4a83-107">Arguments</span></span>

<span data-ttu-id="d4a83-108">`condition 1`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="d4a83-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="d4a83-109">Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane.</span><span class="sxs-lookup"><span data-stu-id="d4a83-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="d4a83-110">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="d4a83-110">This argument is required.</span></span>

<span data-ttu-id="d4a83-111">`condition N`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="d4a83-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="d4a83-112">Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane.</span><span class="sxs-lookup"><span data-stu-id="d4a83-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="d4a83-113">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="d4a83-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="d4a83-114">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="d4a83-114">Return values</span></span>

<span data-ttu-id="d4a83-115">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="d4a83-115">*Boolean*</span></span>

<span data-ttu-id="d4a83-116">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="d4a83-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="d4a83-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="d4a83-117">Example</span></span>

<span data-ttu-id="d4a83-118">Funkcja `OR (1=2, "a"="a")` zwraca wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="d4a83-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d4a83-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d4a83-119">Additional resources</span></span>

[<span data-ttu-id="d4a83-120">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="d4a83-120">Logical functions</span></span>](er-functions-category-logical.md)
