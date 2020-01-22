---
title: DATEFORMAT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATEFORMAT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: c1453be0c93764f9f0364206822a9e3899061a58
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917587"
---
# <span data-ttu-id="ec719-103"><a name="DATEFORMAT">DATEFORMAT, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="ec719-103"><a name="DATEFORMAT">DATEFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec719-104">Funkcja `DATEFORMAT` zwraca wartość *Ciąg*, która przedstawia daną wartość daty jako tekst w określonym formacie i opcjonalnie określonej [kulturze](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="ec719-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="ec719-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="ec719-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="ec719-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="ec719-106">Syntax 1</span></span>

```
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="ec719-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="ec719-107">Syntax 2</span></span>

```
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="ec719-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ec719-108">Arguments</span></span>

<span data-ttu-id="ec719-109">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="ec719-109">`date`: *Date*</span></span>

<span data-ttu-id="ec719-110">Wartość daty, która reprezentuje datę do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="ec719-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="ec719-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ec719-111">`format`: *String*</span></span>

<span data-ttu-id="ec719-112">Format ciągu wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="ec719-112">The format of the output string.</span></span>

<span data-ttu-id="ec719-113">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ec719-113">`culture`: *String*</span></span>

<span data-ttu-id="ec719-114">Kultura do użycia na potrzeby formatowania.</span><span class="sxs-lookup"><span data-stu-id="ec719-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="ec719-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="ec719-115">Return values</span></span>

<span data-ttu-id="ec719-116">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ec719-116">*String*</span></span>

<span data-ttu-id="ec719-117">Wyjściowa wartość ciągu.</span><span class="sxs-lookup"><span data-stu-id="ec719-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ec719-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="ec719-118">Usage notes</span></span>

<span data-ttu-id="ec719-119">Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący.</span><span class="sxs-lookup"><span data-stu-id="ec719-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="ec719-120">Jeśli na przykład funkcja `DATEFORMAT` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej.</span><span class="sxs-lookup"><span data-stu-id="ec719-120">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="ec719-121">Domyślna wartość `culture` to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="ec719-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="ec719-122">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="ec719-122">Example 1</span></span>

<span data-ttu-id="ec719-123">Funkcja `DATEFORMAT (TODAY (), "dd-MM-yyyy")` zwraca datę bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako ciąg **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="ec719-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="ec719-124">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="ec719-124">Example 2</span></span>

<span data-ttu-id="ec719-125">Funkcja `DATEFORMAT (SESSIONTODAY (), "d", "DE")` zwraca bieżącą datę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24-12-2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.</span><span class="sxs-lookup"><span data-stu-id="ec719-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string  **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ec719-126">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ec719-126">Additional resources</span></span>

[<span data-ttu-id="ec719-127">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="ec719-127">Date and time functions</span></span>](er-functions-category-datetime.md)
