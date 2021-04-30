---
title: NUMBERFORMAT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMBERFORMAT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 4a383b3f7c0ca7c4e5afc609cc8a7b1b07021b02
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890390"
---
# <a name="numberformat-er-function"></a><span data-ttu-id="977a6-103">NUMBERFORMAT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="977a6-103">NUMBERFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="977a6-104">Funkcja `NUMBERFORMAT` zwraca wartość *Ciąg*, który przedstawia określoną liczbę w określonym formacie i opcjonalnie określonej [kulturze](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="977a6-104">The `NUMBERFORMAT` function returns a *String* value that presents the specified number in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="977a6-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](/dotnet/standard/base-types/standard-numeric-format-strings) i [niestandardowe](/dotnet/standard/base-types/custom-numeric-format-strings).</span><span class="sxs-lookup"><span data-stu-id="977a6-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-numeric-format-strings) and [custom](/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="977a6-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="977a6-106">Syntax 1</span></span>

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a><span data-ttu-id="977a6-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="977a6-107">Syntax 2</span></span>

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="977a6-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="977a6-108">Arguments</span></span>

<span data-ttu-id="977a6-109">`number`: *Liczba całkowita* lub *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="977a6-109">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="977a6-110">Wartość liczbowa, która określa liczbę do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="977a6-110">A numeric value that specifies the number that must be formatted.</span></span>

<span data-ttu-id="977a6-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="977a6-111">`format` : *String*</span></span>

<span data-ttu-id="977a6-112">Wartość typu *Ciąg* reprezentująca format.</span><span class="sxs-lookup"><span data-stu-id="977a6-112">A *String* value that represents the format.</span></span>

<span data-ttu-id="977a6-113">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="977a6-113">`culture`: *String*</span></span>

<span data-ttu-id="977a6-114">Wartość typu *Ciąg* reprezentująca kulturę do użycia podczas formatowania.</span><span class="sxs-lookup"><span data-stu-id="977a6-114">A *String* value that represents the culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="977a6-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="977a6-115">Return values</span></span>

<span data-ttu-id="977a6-116">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="977a6-116">*String*</span></span>

<span data-ttu-id="977a6-117">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="977a6-117">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="977a6-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="977a6-118">Usage notes</span></span>

<span data-ttu-id="977a6-119">Jeśli kultura nie została zdefiniowana jako argument wywołanej funkcji, kontekst, w którym ta funkcja jest uruchamiana, określa kulturę używaną do formatowania liczb.</span><span class="sxs-lookup"><span data-stu-id="977a6-119">If the culture isn't defined as an argument of the called function, the context that this function is run in determines the culture that is used to format numbers.</span></span>

## <a name="example-1"></a><span data-ttu-id="977a6-120">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="977a6-120">Example 1</span></span>

<span data-ttu-id="977a6-121">W kulturze **EN-US** funkcja `NUMBERFORMAT (0.45, "p")` zwraca **"45.00 %"**, a funkcja `NUMBERFORMAT (10.45, "#")` zwraca **"10"**.</span><span class="sxs-lookup"><span data-stu-id="977a6-121">For the **EN-US** culture, `NUMBERFORMAT (0.45, "p")` returns **"45.00 %"**, and `NUMBERFORMAT (10.45, "#")` returns **"10"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="977a6-122">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="977a6-122">Example 2</span></span>

<span data-ttu-id="977a6-123">Funkcja `NUMBERFORMAT (10/3, "F2", "de")` zwraca **3,33**, a funkcja `NUMBERFORMAT (10/3, "F2", "en-us")` zwraca **3.33**.</span><span class="sxs-lookup"><span data-stu-id="977a6-123">`NUMBERFORMAT (10/3, "F2", "de")` returns **3,33**, whereas `NUMBERFORMAT (10/3, "F2", "en-us")` returns **3.33**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="977a6-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="977a6-124">Additional resources</span></span>

[<span data-ttu-id="977a6-125">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="977a6-125">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]