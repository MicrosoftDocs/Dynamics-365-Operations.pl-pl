---
title: DAYOFYEAR, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DAYOFYEAR w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: d24aabb582151b0b357b64a988cc932a9c9f3cea
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070674"
---
# <span data-ttu-id="5e58a-103"><a name="DAYOFYEAR">DAYOFYEAR, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="5e58a-103"><a name="DAYOFYEAR">DAYOFYEAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e58a-104">Funkcja `DAYOFYEAR` zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między 1 stycznia a określoną datą.</span><span class="sxs-lookup"><span data-stu-id="5e58a-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e58a-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="5e58a-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="5e58a-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="5e58a-106">Arguments</span></span>

<span data-ttu-id="5e58a-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="5e58a-107">`date`: *Date*</span></span>

<span data-ttu-id="5e58a-108">Wartość daty, która reprezentuje datę do użycia do obliczania liczby dni.</span><span class="sxs-lookup"><span data-stu-id="5e58a-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="5e58a-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="5e58a-109">Return values</span></span>

<span data-ttu-id="5e58a-110">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="5e58a-110">*Integer*</span></span>

<span data-ttu-id="5e58a-111">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="5e58a-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="5e58a-112">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="5e58a-112">Example 1</span></span>

<span data-ttu-id="5e58a-113">Funkcja `DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` zwraca wartość **61**.</span><span class="sxs-lookup"><span data-stu-id="5e58a-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="5e58a-114">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="5e58a-114">Example 2</span></span>

<span data-ttu-id="5e58a-115">Funkcja `DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` zwraca wartość **1**.</span><span class="sxs-lookup"><span data-stu-id="5e58a-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e58a-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5e58a-116">Additional resources</span></span>

[<span data-ttu-id="5e58a-117">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="5e58a-117">Date and time functions</span></span>](er-functions-category-datetime.md)
