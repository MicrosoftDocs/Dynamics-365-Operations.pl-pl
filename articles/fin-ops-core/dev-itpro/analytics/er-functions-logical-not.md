---
title: NOT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NOT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: b15277dba26dc7864193b11a127944daca6b989f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916046"
---
# <span data-ttu-id="a2044-103"><a name="NOT">NOT, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="a2044-103"><a name="NOT">NOT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2044-104">Funkcja `NOT` zwraca odwróconą wartość logiczną określonego warunku jako wartość *logiczną*.</span><span class="sxs-lookup"><span data-stu-id="a2044-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2044-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a2044-105">Syntax</span></span>

```
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="a2044-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="a2044-106">Arguments</span></span>

<span data-ttu-id="a2044-107">`condition`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="a2044-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="a2044-108">Prawidłowe wyrażenie warunkowe, które musi zostać odwrócone.</span><span class="sxs-lookup"><span data-stu-id="a2044-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="a2044-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="a2044-109">Return values</span></span>

<span data-ttu-id="a2044-110">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="a2044-110">*Boolean*</span></span>

<span data-ttu-id="a2044-111">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="a2044-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="a2044-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="a2044-112">Example</span></span>

<span data-ttu-id="a2044-113">Funkcja `NOT (TRUE)` zwraca wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a2044-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a2044-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a2044-114">Additional resources</span></span>

[<span data-ttu-id="a2044-115">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="a2044-115">Logical functions</span></span>](er-functions-category-logical.md)
