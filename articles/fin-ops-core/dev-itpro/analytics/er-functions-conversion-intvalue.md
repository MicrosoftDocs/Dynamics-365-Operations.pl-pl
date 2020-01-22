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
ms.openlocfilehash: 2b279de39cf91c3919145735518034fc60cd3341
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917725"
---
# <span data-ttu-id="edf8f-103"><a name="INTVALUE">INTVALUE, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="edf8f-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="edf8f-104">Funkcja `INTVALUE` zwraca wartość *Int*, która reprezentuje określony ciąg.</span><span class="sxs-lookup"><span data-stu-id="edf8f-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="edf8f-105">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="edf8f-105">Syntax 1</span></span>

```
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="edf8f-106">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="edf8f-106">Syntax 2</span></span>

```
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="edf8f-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="edf8f-107">Arguments</span></span>

<span data-ttu-id="edf8f-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="edf8f-108">`text`: *String*</span></span>

<span data-ttu-id="edf8f-109">Wartość tekstowa, która musi zostać przekonwertowana na liczbę typu *Int*.</span><span class="sxs-lookup"><span data-stu-id="edf8f-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="edf8f-110">`number`: *Liczba rzeczywista* lub *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="edf8f-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="edf8f-111">Liczbowa wartość *rzeczywista* lub *całkowita*, która musi zostać przekonwertowana na liczbę typu *Int*.</span><span class="sxs-lookup"><span data-stu-id="edf8f-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="edf8f-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="edf8f-112">Return values</span></span>

<span data-ttu-id="edf8f-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="edf8f-113">*Int*</span></span>

<span data-ttu-id="edf8f-114">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="edf8f-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="edf8f-115">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="edf8f-115">Usage notes</span></span>

<span data-ttu-id="edf8f-116">Wszystkie miejsca dziesiętne są obcinane.</span><span class="sxs-lookup"><span data-stu-id="edf8f-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="edf8f-117">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="edf8f-117">Example 1</span></span>

<span data-ttu-id="edf8f-118">Funkcja `INTVALUE ("100.77")` zwraca wartość *Int* wynoszącą **100**.</span><span class="sxs-lookup"><span data-stu-id="edf8f-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="edf8f-119">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="edf8f-119">Example 2</span></span>

<span data-ttu-id="edf8f-120">Funkcja `INTVALUE (-100.77)` zwraca wartość *Int* wynoszącą **-100**.</span><span class="sxs-lookup"><span data-stu-id="edf8f-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="edf8f-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="edf8f-121">Additional resources</span></span>

[<span data-ttu-id="edf8f-122">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="edf8f-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
