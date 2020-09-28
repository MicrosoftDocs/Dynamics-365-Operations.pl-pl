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
ms.openlocfilehash: 65eb16c5846b5d194361940667da14b594d7a63c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744894"
---
# <a name="datetimevalue-er-function"></a><span data-ttu-id="91e9b-103">DATETIMEVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="91e9b-103">DATETIMEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91e9b-104">Funkcja `DATETIMEVALUE` zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości tekstowej w określonym formacie i opcjonalnie określonej [kulturze](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) na wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="91e9b-104">The `DATETIMEVALUE` function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date/time value.</span></span> <span data-ttu-id="91e9b-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="91e9b-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="91e9b-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="91e9b-106">Syntax 1</span></span>

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="91e9b-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="91e9b-107">Syntax 2</span></span>

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="91e9b-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="91e9b-108">Arguments</span></span>

<span data-ttu-id="91e9b-109">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="91e9b-109">`text`: *String*</span></span>

<span data-ttu-id="91e9b-110">Tekst reprezentujący wartość do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="91e9b-110">Text that represents the value to format.</span></span>

<span data-ttu-id="91e9b-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="91e9b-111">`format`: *String*</span></span>

<span data-ttu-id="91e9b-112">Format danego tekstu.</span><span class="sxs-lookup"><span data-stu-id="91e9b-112">The format of the given text.</span></span>

<span data-ttu-id="91e9b-113">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="91e9b-113">`culture`: *String*</span></span>

<span data-ttu-id="91e9b-114">Kultura używana do formatowania danego tekstu.</span><span class="sxs-lookup"><span data-stu-id="91e9b-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="91e9b-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="91e9b-115">Return values</span></span>

<span data-ttu-id="91e9b-116">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="91e9b-116">*DateTime*</span></span>

<span data-ttu-id="91e9b-117">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="91e9b-117">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="91e9b-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="91e9b-118">Usage notes</span></span>

<span data-ttu-id="91e9b-119">Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący.</span><span class="sxs-lookup"><span data-stu-id="91e9b-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="91e9b-120">Jeśli na przykład funkcja `DATETIMEVALUE` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej.</span><span class="sxs-lookup"><span data-stu-id="91e9b-120">For example, if the `DATETIMEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="91e9b-121">Domyślna wartość `culture` to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="91e9b-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="91e9b-122">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="91e9b-122">Example 1</span></span>

<span data-ttu-id="91e9b-123">Funkcja `DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` zwraca datę **2:55:00 21 grudnia 2016 roku** zgodnie z określonym formatem niestandardowym i domyślną kulturą **EN-US** aplikacji.</span><span class="sxs-lookup"><span data-stu-id="91e9b-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="91e9b-124">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="91e9b-124">Example 2</span></span>

<span data-ttu-id="91e9b-125">Funkcja `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` zwraca **2:55:00 21 grudnia 2016** na podstawie określonego formatu niestandardowego i kultury.</span><span class="sxs-lookup"><span data-stu-id="91e9b-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="91e9b-126">Natomiast funkcja `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` zgłasza wyjątek w celu poinformowania użytkownika, że podany ciąg nie został rozpoznany jako prawidłowa wartość daty/godziny dla określonej kultury.</span><span class="sxs-lookup"><span data-stu-id="91e9b-126">However, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date/time value for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="91e9b-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="91e9b-127">Additional resources</span></span>

[<span data-ttu-id="91e9b-128">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="91e9b-128">Date and time functions</span></span>](er-functions-category-datetime.md)
