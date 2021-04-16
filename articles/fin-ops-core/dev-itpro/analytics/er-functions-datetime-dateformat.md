---
title: DATEFORMAT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATEFORMAT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 01/04/2021
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
ms.openlocfilehash: 5a38f0016f69792e5beffa5d8224c70d6e5261c4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747042"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="aeda5-103">DATEFORMAT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="aeda5-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aeda5-104">Funkcja `DATEFORMAT` zwraca wartość *Ciąg*, która przedstawia daną wartość daty jako tekst w określonym formacie i opcjonalnie określonej [kulturze](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="aeda5-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="aeda5-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="aeda5-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="aeda5-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="aeda5-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="aeda5-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="aeda5-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="aeda5-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="aeda5-108">Arguments</span></span>

<span data-ttu-id="aeda5-109">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="aeda5-109">`date`: *Date*</span></span>

<span data-ttu-id="aeda5-110">Wartość daty, która reprezentuje datę do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="aeda5-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="aeda5-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="aeda5-111">`format`: *String*</span></span>

<span data-ttu-id="aeda5-112">Format ciągu wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="aeda5-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="aeda5-113">W przypadku używania formatu standardowego lub niestandardowego w ciągu formatu jest uwzględniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="aeda5-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="aeda5-114">Na przykład [standardowy](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) format „d” zwraca datę przy użyciu wzorca daty krótkiej, a standardowy modyfikator formatu „D” zwraca datę przy użyciu wzorca daty długiej.</span><span class="sxs-lookup"><span data-stu-id="aeda5-114">For example, the [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="aeda5-115">Ponadto [niestandardowy](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) modyfikator formatu „M” zwraca miesiąc z okresu od 1 do 12, podczas gdy niestandardowy modyfikator formatu „m” zwraca minuty od 0 do 59.</span><span class="sxs-lookup"><span data-stu-id="aeda5-115">Additionally, the [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="aeda5-116">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="aeda5-116">`culture`: *String*</span></span>

<span data-ttu-id="aeda5-117">Kultura do użycia na potrzeby formatowania.</span><span class="sxs-lookup"><span data-stu-id="aeda5-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="aeda5-118">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="aeda5-118">Return values</span></span>

<span data-ttu-id="aeda5-119">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="aeda5-119">*String*</span></span>

<span data-ttu-id="aeda5-120">Wyjściowa wartość ciągu.</span><span class="sxs-lookup"><span data-stu-id="aeda5-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="aeda5-121">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="aeda5-121">Usage notes</span></span>

<span data-ttu-id="aeda5-122">Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący.</span><span class="sxs-lookup"><span data-stu-id="aeda5-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="aeda5-123">Jeśli na przykład funkcja `DATEFORMAT` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej.</span><span class="sxs-lookup"><span data-stu-id="aeda5-123">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="aeda5-124">Domyślna wartość `culture` to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="aeda5-124">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="aeda5-125">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="aeda5-125">Example 1</span></span>

<span data-ttu-id="aeda5-126">Funkcja `DATEFORMAT (TODAY (), "dd-MM-yyyy")` zwraca datę bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako ciąg **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="aeda5-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="aeda5-127">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="aeda5-127">Example 2</span></span>

<span data-ttu-id="aeda5-128">Funkcja `DATEFORMAT (SESSIONTODAY (), "d", "DE")` zwraca bieżącą datę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24-12-2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.</span><span class="sxs-lookup"><span data-stu-id="aeda5-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aeda5-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="aeda5-129">Additional resources</span></span>

[<span data-ttu-id="aeda5-130">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="aeda5-130">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]