---
title: DAYOFYEAR, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DAYOFYEAR w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 569e988db91ff992fb7db6e7fd6e8c6aa6a1a3e8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746922"
---
# <a name="dayofyear-er-function"></a><span data-ttu-id="c1bf6-103">DAYOFYEAR, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c1bf6-103">DAYOFYEAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1bf6-104">Funkcja `DAYOFYEAR` zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między 1 stycznia a określoną datą.</span><span class="sxs-lookup"><span data-stu-id="c1bf6-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1bf6-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c1bf6-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="c1bf6-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c1bf6-106">Arguments</span></span>

<span data-ttu-id="c1bf6-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="c1bf6-107">`date`: *Date*</span></span>

<span data-ttu-id="c1bf6-108">Wartość daty, która reprezentuje datę do użycia do obliczania liczby dni.</span><span class="sxs-lookup"><span data-stu-id="c1bf6-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="c1bf6-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c1bf6-109">Return values</span></span>

<span data-ttu-id="c1bf6-110">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="c1bf6-110">*Integer*</span></span>

<span data-ttu-id="c1bf6-111">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="c1bf6-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="c1bf6-112">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="c1bf6-112">Example 1</span></span>

<span data-ttu-id="c1bf6-113">Funkcja `DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` zwraca wartość **61**.</span><span class="sxs-lookup"><span data-stu-id="c1bf6-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c1bf6-114">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="c1bf6-114">Example 2</span></span>

<span data-ttu-id="c1bf6-115">Funkcja `DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` zwraca wartość **1**.</span><span class="sxs-lookup"><span data-stu-id="c1bf6-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c1bf6-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c1bf6-116">Additional resources</span></span>

[<span data-ttu-id="c1bf6-117">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="c1bf6-117">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]