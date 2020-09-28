---
title: AND, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji AND w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 4a246496eca0d5a8538ac7f1577957e6b9eae4e3
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743478"
---
# <a name="and-er-function"></a><span data-ttu-id="fb521-103">AND, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="fb521-103">AND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb521-104">Funkcja `AND` zwraca wartość *logiczną* **TRUE**, jeśli wszystkie wybrane warunki zostaną spełnione.</span><span class="sxs-lookup"><span data-stu-id="fb521-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="fb521-105">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="fb521-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb521-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="fb521-106">Syntax</span></span>

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="fb521-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="fb521-107">Arguments</span></span>

<span data-ttu-id="fb521-108">`condition 1`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="fb521-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="fb521-109">Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane.</span><span class="sxs-lookup"><span data-stu-id="fb521-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="fb521-110">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="fb521-110">This argument is required.</span></span>

<span data-ttu-id="fb521-111">`condition N`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="fb521-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="fb521-112">Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane.</span><span class="sxs-lookup"><span data-stu-id="fb521-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="fb521-113">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="fb521-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="fb521-114">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="fb521-114">Return values</span></span>

<span data-ttu-id="fb521-115">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="fb521-115">*Boolean*</span></span>

<span data-ttu-id="fb521-116">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="fb521-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fb521-117">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="fb521-117">Usage notes</span></span>

<span data-ttu-id="fb521-118">W argumentach funkcji logicznych można używać odwołań do źródeł danych, wartości liczbowych i tekstowych, wartości logicznych, operatorów porównania i innych funkcji raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="fb521-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="fb521-119">Jednak wartość wszystkich argumentów musi być obliczana jako wartość *logiczna* **TRUE** lub **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="fb521-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="fb521-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="fb521-120">Example</span></span>

<span data-ttu-id="fb521-121">Funkcja `AND (1=1, "a"="a")` zwraca wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="fb521-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="fb521-122">Funkcja `AND (1=2, "a"="a")` zwraca wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="fb521-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb521-123">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fb521-123">Additional resources</span></span>

[<span data-ttu-id="fb521-124">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="fb521-124">Logical functions</span></span>](er-functions-category-logical.md)
