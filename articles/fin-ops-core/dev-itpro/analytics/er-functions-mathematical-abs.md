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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b53535d1a000b72577be5c6284cc4676c43d591b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744606"
---
# <a name="abs-er-function"></a><span data-ttu-id="2da34-103">ABS, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="2da34-103">ABS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2da34-104">Funkcja `ABS` zwraca wartość bezwzględną (moduł) określonej liczby jako wartość *rzeczywistą*.</span><span class="sxs-lookup"><span data-stu-id="2da34-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="2da34-105">Innymi słowy zwraca liczbę bez znaku.</span><span class="sxs-lookup"><span data-stu-id="2da34-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="2da34-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="2da34-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="2da34-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="2da34-107">Arguments</span></span>

<span data-ttu-id="2da34-108">`number`: *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="2da34-108">`number`: *Real*</span></span>

<span data-ttu-id="2da34-109">Wartość liczbowa, dla której chcesz obliczyć moduł.</span><span class="sxs-lookup"><span data-stu-id="2da34-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="2da34-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="2da34-110">Return values</span></span>

<span data-ttu-id="2da34-111">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="2da34-111">*Real*</span></span>

<span data-ttu-id="2da34-112">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="2da34-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="2da34-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="2da34-113">Example</span></span>

<span data-ttu-id="2da34-114">Funkcja `ABS (-1)` zwraca wartość **1**.</span><span class="sxs-lookup"><span data-stu-id="2da34-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2da34-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2da34-115">Additional resources</span></span>

[<span data-ttu-id="2da34-116">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="2da34-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
