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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 98b91a983c60bb99280763f7f7a944d08f535e60
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686010"
---
# <a name="intvalue-er-function"></a><span data-ttu-id="efc25-103">INTVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="efc25-103">INTVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efc25-104">Funkcja `INTVALUE` zwraca wartość *Int*, która reprezentuje określony ciąg.</span><span class="sxs-lookup"><span data-stu-id="efc25-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="efc25-105">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="efc25-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="efc25-106">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="efc25-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="efc25-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="efc25-107">Arguments</span></span>

<span data-ttu-id="efc25-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="efc25-108">`text`: *String*</span></span>

<span data-ttu-id="efc25-109">Wartość tekstowa, która musi zostać przekonwertowana na liczbę typu *Int*.</span><span class="sxs-lookup"><span data-stu-id="efc25-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="efc25-110">`number`: *Liczba rzeczywista* lub *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="efc25-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="efc25-111">Liczbowa wartość *rzeczywista* lub *całkowita*, która musi zostać przekonwertowana na liczbę typu *Int*.</span><span class="sxs-lookup"><span data-stu-id="efc25-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="efc25-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="efc25-112">Return values</span></span>

<span data-ttu-id="efc25-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="efc25-113">*Int*</span></span>

<span data-ttu-id="efc25-114">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="efc25-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="efc25-115">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="efc25-115">Usage notes</span></span>

<span data-ttu-id="efc25-116">Wszystkie miejsca dziesiętne są obcinane.</span><span class="sxs-lookup"><span data-stu-id="efc25-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="efc25-117">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="efc25-117">Example 1</span></span>

<span data-ttu-id="efc25-118">Funkcja `INTVALUE ("100.77")` zwraca wartość *Int* wynoszącą **100**.</span><span class="sxs-lookup"><span data-stu-id="efc25-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="efc25-119">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="efc25-119">Example 2</span></span>

<span data-ttu-id="efc25-120">Funkcja `INTVALUE (-100.77)` zwraca wartość *Int* wynoszącą **-100**.</span><span class="sxs-lookup"><span data-stu-id="efc25-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="efc25-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="efc25-121">Additional resources</span></span>

[<span data-ttu-id="efc25-122">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="efc25-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
