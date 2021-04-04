---
title: INT64VALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji INT64VALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 9db2e9abcac36a8331a494c886218bbfc82e93aa
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561501"
---
# <a name="int64value-er-function"></a><span data-ttu-id="c4115-103">INT64VALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c4115-103">INT64VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4115-104">Funkcja `INT64VALUE` zwraca wartość *Int64*, która reprezentuje określony ciąg.</span><span class="sxs-lookup"><span data-stu-id="c4115-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="c4115-105">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="c4115-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="c4115-106">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="c4115-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="c4115-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c4115-107">Arguments</span></span>

<span data-ttu-id="c4115-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c4115-108">`text`: *String*</span></span>

<span data-ttu-id="c4115-109">Wartość tekstowa, która musi zostać przekonwertowana na liczbę typu *Int64*.</span><span class="sxs-lookup"><span data-stu-id="c4115-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="c4115-110">`number`: *Liczba rzeczywista* lub *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="c4115-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="c4115-111">Liczbowa wartość *rzeczywista* lub *całkowita*, która musi zostać przekonwertowana na liczbę typu *Int64*.</span><span class="sxs-lookup"><span data-stu-id="c4115-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="c4115-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c4115-112">Return values</span></span>

<span data-ttu-id="c4115-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="c4115-113">*Int64*</span></span>

<span data-ttu-id="c4115-114">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="c4115-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c4115-115">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="c4115-115">Usage notes</span></span>

<span data-ttu-id="c4115-116">Wszystkie miejsca dziesiętne są obcinane.</span><span class="sxs-lookup"><span data-stu-id="c4115-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="c4115-117">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="c4115-117">Example 1</span></span>

<span data-ttu-id="c4115-118">Funkcja `INT64VALUE ("22565422744")` zwraca wartość *Int64* wynoszącą **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="c4115-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c4115-119">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="c4115-119">Example 2</span></span>

<span data-ttu-id="c4115-120">Funkcja `INT64VALUE ( VALUE("22565422744.77"))` zwraca wartość *Int64* wynoszącą **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="c4115-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4115-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c4115-121">Additional resources</span></span>

[<span data-ttu-id="c4115-122">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="c4115-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]