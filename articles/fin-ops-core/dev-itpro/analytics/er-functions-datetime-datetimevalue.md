---
title: DATETIMEVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATETIMEVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 29d81599563dec2827fa8a82c86b74cb9e34eea2
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070697"
---
# <span data-ttu-id="08d65-103"><a name="DATETIMEVALUE">DATETIMEVALUE, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="08d65-103"><a name="DATETIMEVALUE">DATETIMEVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08d65-104">Funkcja `DATETIMEVALUE` zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości tekstowej w określonym formacie i opcjonalnie określonej [kulturze](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) na wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="08d65-104">The `DATETIMEVALUE` function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date/time value.</span></span> <span data-ttu-id="08d65-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="08d65-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="08d65-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="08d65-106">Syntax 1</span></span>

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="08d65-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="08d65-107">Syntax 2</span></span>

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="08d65-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="08d65-108">Arguments</span></span>

<span data-ttu-id="08d65-109">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="08d65-109">`text`: *String*</span></span>

<span data-ttu-id="08d65-110">Tekst reprezentujący wartość do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="08d65-110">Text that represents the value to format.</span></span>

<span data-ttu-id="08d65-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="08d65-111">`format`: *String*</span></span>

<span data-ttu-id="08d65-112">Format danego tekstu.</span><span class="sxs-lookup"><span data-stu-id="08d65-112">The format of the given text.</span></span>

<span data-ttu-id="08d65-113">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="08d65-113">`culture`: *String*</span></span>

<span data-ttu-id="08d65-114">Kultura używana do formatowania danego tekstu.</span><span class="sxs-lookup"><span data-stu-id="08d65-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="08d65-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="08d65-115">Return values</span></span>

<span data-ttu-id="08d65-116">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="08d65-116">*DateTime*</span></span>

<span data-ttu-id="08d65-117">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="08d65-117">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="08d65-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="08d65-118">Usage notes</span></span>

<span data-ttu-id="08d65-119">Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący.</span><span class="sxs-lookup"><span data-stu-id="08d65-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="08d65-120">Jeśli na przykład funkcja `DATETIMEVALUE` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej.</span><span class="sxs-lookup"><span data-stu-id="08d65-120">For example, if the `DATETIMEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="08d65-121">Domyślna wartość `culture` to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="08d65-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="08d65-122">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="08d65-122">Example 1</span></span>

<span data-ttu-id="08d65-123">Funkcja `DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` zwraca datę **2:55:00 21 grudnia 2016 roku** zgodnie z określonym formatem niestandardowym i domyślną kulturą **EN-US** aplikacji.</span><span class="sxs-lookup"><span data-stu-id="08d65-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="08d65-124">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="08d65-124">Example 2</span></span>

<span data-ttu-id="08d65-125">Funkcja `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` zwraca **2:55:00 21 grudnia 2016** na podstawie określonego formatu niestandardowego i kultury.</span><span class="sxs-lookup"><span data-stu-id="08d65-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="08d65-126">Natomiast funkcja `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` zgłasza wyjątek w celu poinformowania użytkownika, że podany ciąg nie został rozpoznany jako prawidłowa wartość daty/godziny dla określonej kultury.</span><span class="sxs-lookup"><span data-stu-id="08d65-126">However, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date/time value for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="08d65-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="08d65-127">Additional resources</span></span>

[<span data-ttu-id="08d65-128">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="08d65-128">Date and time functions</span></span>](er-functions-category-datetime.md)
