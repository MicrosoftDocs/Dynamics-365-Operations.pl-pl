---
title: NUMBERFORMAT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMBERFORMAT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: a05a1e1c4cdb050bff30ea4710da927a537da14c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562716"
---
# <a name="numberformat-er-function"></a><span data-ttu-id="61731-103">NUMBERFORMAT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="61731-103">NUMBERFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61731-104">Funkcja `NUMBERFORMAT` zwraca wartość *Ciąg*, który przedstawia określoną liczbę w określonym formacie i opcjonalnie określonej [kulturze](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="61731-104">The `NUMBERFORMAT` function returns a *String* value that presents the specified number in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="61731-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="61731-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="61731-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="61731-106">Syntax 1</span></span>

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a><span data-ttu-id="61731-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="61731-107">Syntax 2</span></span>

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="61731-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="61731-108">Arguments</span></span>

<span data-ttu-id="61731-109">`number`: *Liczba całkowita* lub *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="61731-109">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="61731-110">Wartość liczbowa, która określa liczbę do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="61731-110">A numeric value that specifies the number that must be formatted.</span></span>

<span data-ttu-id="61731-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="61731-111">`format` : *String*</span></span>

<span data-ttu-id="61731-112">Wartość typu *Ciąg* reprezentująca format.</span><span class="sxs-lookup"><span data-stu-id="61731-112">A *String* value that represents the format.</span></span>

<span data-ttu-id="61731-113">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="61731-113">`culture`: *String*</span></span>

<span data-ttu-id="61731-114">Wartość typu *Ciąg* reprezentująca kulturę do użycia podczas formatowania.</span><span class="sxs-lookup"><span data-stu-id="61731-114">A *String* value that represents the culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="61731-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="61731-115">Return values</span></span>

<span data-ttu-id="61731-116">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="61731-116">*String*</span></span>

<span data-ttu-id="61731-117">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="61731-117">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="61731-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="61731-118">Usage notes</span></span>

<span data-ttu-id="61731-119">Jeśli kultura nie została zdefiniowana jako argument wywołanej funkcji, kontekst, w którym ta funkcja jest uruchamiana, określa kulturę używaną do formatowania liczb.</span><span class="sxs-lookup"><span data-stu-id="61731-119">If the culture isn't defined as an argument of the called function, the context that this function is run in determines the culture that is used to format numbers.</span></span>

## <a name="example-1"></a><span data-ttu-id="61731-120">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="61731-120">Example 1</span></span>

<span data-ttu-id="61731-121">W kulturze **EN-US** funkcja `NUMBERFORMAT (0.45, "p")` zwraca **"45.00 %"**, a funkcja `NUMBERFORMAT (10.45, "#")` zwraca **"10"**.</span><span class="sxs-lookup"><span data-stu-id="61731-121">For the **EN-US** culture, `NUMBERFORMAT (0.45, "p")` returns **"45.00 %"**, and `NUMBERFORMAT (10.45, "#")` returns **"10"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="61731-122">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="61731-122">Example 2</span></span>

<span data-ttu-id="61731-123">Funkcja `NUMBERFORMAT (10/3, "F2", "de")` zwraca **3,33**, a funkcja `NUMBERFORMAT (10/3, "F2", "en-us")` zwraca **3.33**.</span><span class="sxs-lookup"><span data-stu-id="61731-123">`NUMBERFORMAT (10/3, "F2", "de")` returns **3,33**, whereas `NUMBERFORMAT (10/3, "F2", "en-us")` returns **3.33**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61731-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="61731-124">Additional resources</span></span>

[<span data-ttu-id="61731-125">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="61731-125">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]