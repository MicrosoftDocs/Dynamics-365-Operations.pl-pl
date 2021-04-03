---
title: DATEVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATEVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 82feb8284f4b6116a53d174dcdd9b8c09c4fa63a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563565"
---
# <a name="datevalue-er-function"></a><span data-ttu-id="afca8-103">DATEVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="afca8-103">DATEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="afca8-104">Funkcja `DATEVALUE` zwraca wartość *daty*, która jest konwertowana z wartości danego tekstu w określonym formacie i opcjonalnie określonej [kultury](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) na wartość daty.</span><span class="sxs-lookup"><span data-stu-id="afca8-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="afca8-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="afca8-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="afca8-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="afca8-106">Syntax 1</span></span>

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="afca8-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="afca8-107">Syntax 2</span></span>

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="afca8-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="afca8-108">Arguments</span></span>

<span data-ttu-id="afca8-109">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="afca8-109">`text`: *String*</span></span>

<span data-ttu-id="afca8-110">Tekst reprezentujący wartość do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="afca8-110">Text that represents the value to format.</span></span>

<span data-ttu-id="afca8-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="afca8-111">`format`: *String*</span></span>

<span data-ttu-id="afca8-112">Format danego tekstu.</span><span class="sxs-lookup"><span data-stu-id="afca8-112">The format of the given text.</span></span>

<span data-ttu-id="afca8-113">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="afca8-113">`culture`: *String*</span></span>

<span data-ttu-id="afca8-114">Kultura używana do formatowania danego tekstu.</span><span class="sxs-lookup"><span data-stu-id="afca8-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="afca8-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="afca8-115">Return values</span></span>

<span data-ttu-id="afca8-116">*Data*</span><span class="sxs-lookup"><span data-stu-id="afca8-116">*Date*</span></span>

<span data-ttu-id="afca8-117">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="afca8-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="afca8-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="afca8-118">Usage notes</span></span>

<span data-ttu-id="afca8-119">Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący.</span><span class="sxs-lookup"><span data-stu-id="afca8-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="afca8-120">Jeśli na przykład funkcja `DATEVALUE` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej.</span><span class="sxs-lookup"><span data-stu-id="afca8-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="afca8-121">Domyślna wartość `culture` to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="afca8-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="afca8-122">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="afca8-122">Example 1</span></span>

<span data-ttu-id="afca8-123">Funkcja `DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` zwraca datę **21 grudnia 2016 roku** zgodnie z określonym formatem niestandardowym i domyślną kulturą **EN-US** aplikacji.</span><span class="sxs-lookup"><span data-stu-id="afca8-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="afca8-124">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="afca8-124">Example 2</span></span>

<span data-ttu-id="afca8-125">Funkcja `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` zwraca wartość daty **21 stycznia 2016** na podstawie określonego formatu niestandardowego i kultury.</span><span class="sxs-lookup"><span data-stu-id="afca8-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="afca8-126">Natomiast funkcja `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` zgłasza wyjątek w celu poinformowania użytkownika, że podany ciąg nie został rozpoznany jako prawidłowa data.</span><span class="sxs-lookup"><span data-stu-id="afca8-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="afca8-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="afca8-127">Additional resources</span></span>

[<span data-ttu-id="afca8-128">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="afca8-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]