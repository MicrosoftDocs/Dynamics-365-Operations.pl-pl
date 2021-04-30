---
title: DATEVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATEVALUE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: cfaf183c61d3663442cbc244239b872b9e1957bb
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891240"
---
# <a name="datevalue-er-function"></a><span data-ttu-id="c1cb2-103">DATEVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c1cb2-103">DATEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1cb2-104">Funkcja `DATEVALUE` zwraca wartość *daty*, która jest konwertowana z wartości danego tekstu w określonym formacie i opcjonalnie określonej [kultury](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) na wartość daty.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="c1cb2-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](/dotnet/standard/base-types/standard-date-and-time-format-strings) i [niestandardowe](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="c1cb2-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="c1cb2-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="c1cb2-106">Syntax 1</span></span>

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="c1cb2-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="c1cb2-107">Syntax 2</span></span>

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="c1cb2-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c1cb2-108">Arguments</span></span>

<span data-ttu-id="c1cb2-109">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c1cb2-109">`text`: *String*</span></span>

<span data-ttu-id="c1cb2-110">Tekst reprezentujący wartość do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-110">Text that represents the value to format.</span></span>

<span data-ttu-id="c1cb2-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c1cb2-111">`format`: *String*</span></span>

<span data-ttu-id="c1cb2-112">Format danego tekstu.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-112">The format of the given text.</span></span>

<span data-ttu-id="c1cb2-113">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c1cb2-113">`culture`: *String*</span></span>

<span data-ttu-id="c1cb2-114">Kultura używana do formatowania danego tekstu.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="c1cb2-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c1cb2-115">Return values</span></span>

<span data-ttu-id="c1cb2-116">*Data*</span><span class="sxs-lookup"><span data-stu-id="c1cb2-116">*Date*</span></span>

<span data-ttu-id="c1cb2-117">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c1cb2-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="c1cb2-118">Usage notes</span></span>

<span data-ttu-id="c1cb2-119">Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="c1cb2-120">Jeśli na przykład funkcja `DATEVALUE` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="c1cb2-121">Domyślna wartość `culture` to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="c1cb2-122">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="c1cb2-122">Example 1</span></span>

<span data-ttu-id="c1cb2-123">Funkcja `DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` zwraca datę **21 grudnia 2016 roku** zgodnie z określonym formatem niestandardowym i domyślną kulturą **EN-US** aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="c1cb2-124">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="c1cb2-124">Example 2</span></span>

<span data-ttu-id="c1cb2-125">Funkcja `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` zwraca wartość daty **21 stycznia 2016** na podstawie określonego formatu niestandardowego i kultury.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="c1cb2-126">Natomiast funkcja `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` zgłasza wyjątek w celu poinformowania użytkownika, że podany ciąg nie został rozpoznany jako prawidłowa data.</span><span class="sxs-lookup"><span data-stu-id="c1cb2-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c1cb2-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c1cb2-127">Additional resources</span></span>

[<span data-ttu-id="c1cb2-128">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="c1cb2-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]