---
title: INTVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji INTVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 5e06236bf1d158a4cf579b8b89cc0a5f7d815c38
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042664"
---
# <span data-ttu-id="b56ed-103"><a name="INTVALUE">INTVALUE, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="b56ed-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b56ed-104">Funkcja `INTVALUE` zwraca wartość *Int*, która reprezentuje określony ciąg.</span><span class="sxs-lookup"><span data-stu-id="b56ed-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="b56ed-105">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="b56ed-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="b56ed-106">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="b56ed-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="b56ed-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b56ed-107">Arguments</span></span>

<span data-ttu-id="b56ed-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b56ed-108">`text`: *String*</span></span>

<span data-ttu-id="b56ed-109">Wartość tekstowa, która musi zostać przekonwertowana na liczbę typu *Int*.</span><span class="sxs-lookup"><span data-stu-id="b56ed-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="b56ed-110">`number`: *Liczba rzeczywista* lub *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="b56ed-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="b56ed-111">Liczbowa wartość *rzeczywista* lub *całkowita*, która musi zostać przekonwertowana na liczbę typu *Int*.</span><span class="sxs-lookup"><span data-stu-id="b56ed-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="b56ed-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="b56ed-112">Return values</span></span>

<span data-ttu-id="b56ed-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="b56ed-113">*Int*</span></span>

<span data-ttu-id="b56ed-114">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="b56ed-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b56ed-115">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="b56ed-115">Usage notes</span></span>

<span data-ttu-id="b56ed-116">Wszystkie miejsca dziesiętne są obcinane.</span><span class="sxs-lookup"><span data-stu-id="b56ed-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="b56ed-117">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="b56ed-117">Example 1</span></span>

<span data-ttu-id="b56ed-118">Funkcja `INTVALUE ("100.77")` zwraca wartość *Int* wynoszącą **100**.</span><span class="sxs-lookup"><span data-stu-id="b56ed-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b56ed-119">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="b56ed-119">Example 2</span></span>

<span data-ttu-id="b56ed-120">Funkcja `INTVALUE (-100.77)` zwraca wartość *Int* wynoszącą **-100**.</span><span class="sxs-lookup"><span data-stu-id="b56ed-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b56ed-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b56ed-121">Additional resources</span></span>

[<span data-ttu-id="b56ed-122">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="b56ed-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
