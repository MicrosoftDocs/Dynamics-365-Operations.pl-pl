---
title: ABS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ABS w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 2a3613483d53fb265741b5d6a34a91da443dcef7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753151"
---
# <a name="abs-er-function"></a><span data-ttu-id="6853a-103">ABS, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="6853a-103">ABS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6853a-104">Funkcja `ABS` zwraca wartość bezwzględną (moduł) określonej liczby jako wartość *rzeczywistą*.</span><span class="sxs-lookup"><span data-stu-id="6853a-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="6853a-105">Innymi słowy zwraca liczbę bez znaku.</span><span class="sxs-lookup"><span data-stu-id="6853a-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="6853a-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="6853a-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="6853a-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="6853a-107">Arguments</span></span>

<span data-ttu-id="6853a-108">`number`: *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="6853a-108">`number`: *Real*</span></span>

<span data-ttu-id="6853a-109">Wartość liczbowa, dla której chcesz obliczyć moduł.</span><span class="sxs-lookup"><span data-stu-id="6853a-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="6853a-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="6853a-110">Return values</span></span>

<span data-ttu-id="6853a-111">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="6853a-111">*Real*</span></span>

<span data-ttu-id="6853a-112">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="6853a-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="6853a-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="6853a-113">Example</span></span>

<span data-ttu-id="6853a-114">Funkcja `ABS (-1)` zwraca wartość **1**.</span><span class="sxs-lookup"><span data-stu-id="6853a-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6853a-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6853a-115">Additional resources</span></span>

[<span data-ttu-id="6853a-116">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="6853a-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]