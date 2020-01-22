---
title: ADDDAYS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ADDDAYS w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: dd1290538c506cd0db6eb21a304ff9812c808f17
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916460"
---
# <span data-ttu-id="dd1e1-103"><a name="ADDDAYS">ADDDAYS, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="dd1e1-103"><a name="ADDDAYS">ADDDAYS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd1e1-104">Funkcja `ADDDAYS` oblicza wartość *Data/godzina*, która jest określoną liczbą dni przed wybraną datą rozpoczęcia lub po niej.</span><span class="sxs-lookup"><span data-stu-id="dd1e1-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="dd1e1-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="dd1e1-105">Syntax</span></span>

```
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="dd1e1-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="dd1e1-106">Arguments</span></span>

<span data-ttu-id="dd1e1-107">`datetime`: *Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="dd1e1-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="dd1e1-108">Wartość daty/godziny, która reprezentuje datę początkową.</span><span class="sxs-lookup"><span data-stu-id="dd1e1-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="dd1e1-109">`days`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="dd1e1-109">`days`: *Integer*</span></span>

<span data-ttu-id="dd1e1-110">Liczba dni przed lub po `datetime`.</span><span class="sxs-lookup"><span data-stu-id="dd1e1-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="dd1e1-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="dd1e1-111">Return values</span></span>

<span data-ttu-id="dd1e1-112">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="dd1e1-112">*DateTime*</span></span>

<span data-ttu-id="dd1e1-113">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="dd1e1-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="dd1e1-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="dd1e1-114">Usage notes</span></span>

<span data-ttu-id="dd1e1-115">Wartość dodatnia elementu `days` generuje przyszłą datę.</span><span class="sxs-lookup"><span data-stu-id="dd1e1-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="dd1e1-116">Wartość ujemna generuje datę przeszłą.</span><span class="sxs-lookup"><span data-stu-id="dd1e1-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="dd1e1-117">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="dd1e1-117">Example 1</span></span>

<span data-ttu-id="dd1e1-118">Funkcja `ADDDAYS (NOW(), 7)` zwraca datę i godzinę siedem dni w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="dd1e1-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="dd1e1-119">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="dd1e1-119">Example 2</span></span>

<span data-ttu-id="dd1e1-120">Funkcja `ADDDAYS (NOW(), -3)` zwraca datę i godzinę trzy dni w przeszłości.</span><span class="sxs-lookup"><span data-stu-id="dd1e1-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd1e1-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="dd1e1-121">Additional resources</span></span>

[<span data-ttu-id="dd1e1-122">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="dd1e1-122">Date and time functions</span></span>](er-functions-category-datetime.md)
