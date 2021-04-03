---
title: NOT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NOT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 9b55b3d8930ece7e2f2925579821ca88749801f7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565887"
---
# <a name="not-er-function"></a><span data-ttu-id="25ff7-103">NOT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="25ff7-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25ff7-104">Funkcja `NOT` zwraca odwróconą wartość logiczną określonego warunku jako wartość *logiczną*.</span><span class="sxs-lookup"><span data-stu-id="25ff7-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="25ff7-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="25ff7-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="25ff7-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="25ff7-106">Arguments</span></span>

<span data-ttu-id="25ff7-107">`condition`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="25ff7-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="25ff7-108">Prawidłowe wyrażenie warunkowe, które musi zostać odwrócone.</span><span class="sxs-lookup"><span data-stu-id="25ff7-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="25ff7-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="25ff7-109">Return values</span></span>

<span data-ttu-id="25ff7-110">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="25ff7-110">*Boolean*</span></span>

<span data-ttu-id="25ff7-111">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="25ff7-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="25ff7-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="25ff7-112">Example</span></span>

<span data-ttu-id="25ff7-113">Funkcja `NOT (TRUE)` zwraca wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="25ff7-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25ff7-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="25ff7-114">Additional resources</span></span>

[<span data-ttu-id="25ff7-115">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="25ff7-115">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]