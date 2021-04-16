---
title: DATETIMEFORMAT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATETIMEFORMAT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 859753c04e3b3d3b61d9a61edaf396637ed5a003
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746994"
---
# <a name="datetimeformat-er-function"></a><span data-ttu-id="f12c2-103">DATETIMEFORMAT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="f12c2-103">DATETIMEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f12c2-104">Funkcja `DATETIMEFORMAT` zwraca wartość *Ciąg*, która przedstawia daną wartość daty/godziny jako tekst w określonym formacie i opcjonalnie określonej [kulturze](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="f12c2-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="f12c2-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="f12c2-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="f12c2-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="f12c2-106">Syntax 1</span></span>

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="f12c2-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="f12c2-107">Syntax 2</span></span>

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="f12c2-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f12c2-108">Arguments</span></span>

<span data-ttu-id="f12c2-109">`datetime`: *Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="f12c2-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="f12c2-110">Wartość daty i godziny, która reprezentuje datę i godzinę do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="f12c2-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="f12c2-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f12c2-111">`format`: *String*</span></span>

<span data-ttu-id="f12c2-112">Format ciągu wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="f12c2-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="f12c2-113">W przypadku używania formatu standardowego lub niestandardowego w ciągu formatu jest uwzględniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="f12c2-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="f12c2-114">Na przykład [standardowy](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) format „d” zwraca datę przy użyciu wzorca daty krótkiej, a standardowy modyfikator formatu „D” zwraca datę przy użyciu wzorca daty długiej.</span><span class="sxs-lookup"><span data-stu-id="f12c2-114">For example, the [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="f12c2-115">Ponadto [niestandardowy](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) modyfikator formatu „M” zwraca miesiąc z okresu od 1 do 12, podczas gdy niestandardowy modyfikator formatu „m” zwraca minuty od 0 do 59.</span><span class="sxs-lookup"><span data-stu-id="f12c2-115">Additionally, the [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="f12c2-116">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f12c2-116">`culture`: *String*</span></span>

<span data-ttu-id="f12c2-117">Kultura do użycia na potrzeby formatowania.</span><span class="sxs-lookup"><span data-stu-id="f12c2-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="f12c2-118">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="f12c2-118">Return values</span></span>

<span data-ttu-id="f12c2-119">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f12c2-119">*String*</span></span>

<span data-ttu-id="f12c2-120">Wyjściowa wartość ciągu.</span><span class="sxs-lookup"><span data-stu-id="f12c2-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f12c2-121">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="f12c2-121">Usage notes</span></span>

<span data-ttu-id="f12c2-122">Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący.</span><span class="sxs-lookup"><span data-stu-id="f12c2-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="f12c2-123">Jeśli na przykład funkcja `DATETIMEFORMAT` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej.</span><span class="sxs-lookup"><span data-stu-id="f12c2-123">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="f12c2-124">Domyślna wartość `culture` to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="f12c2-124">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="f12c2-125">Gdy funkcja `DATETIMEFORMAT` konwertuje wartość danej daty/godziny, bierze pod uwagę ustawienia strefy czasowej użytkownika aplikacji, który uruchamia format ER, w którego kontekście jest wywoływana funkcja.</span><span class="sxs-lookup"><span data-stu-id="f12c2-125">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="f12c2-126">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="f12c2-126">Example 1</span></span>

<span data-ttu-id="f12c2-127">Funkcja `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` zwraca wartość daty/godziny bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="f12c2-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="f12c2-128">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="f12c2-128">Example 2</span></span>

<span data-ttu-id="f12c2-129">Funkcja `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` zwraca bieżącą datę/godzinę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24.12.2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.</span><span class="sxs-lookup"><span data-stu-id="f12c2-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="f12c2-130">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="f12c2-130">Example 3</span></span>

<span data-ttu-id="f12c2-131">Funkcja `DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` zwraca wartość ciągu **2019-11-12T08:00:00.0000000-08:00**, gdy funkcja jest wywoływana podczas procesu, który został zainicjowany przez użytkownika aplikacji z wartością strefy czasowej **(GMT-08:00) Czas pacyficzny (USA i Kanada)** w sekcji **Preferencje dotyczące języka i kraju/regionu**.</span><span class="sxs-lookup"><span data-stu-id="f12c2-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when the function is called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f12c2-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f12c2-132">Additional resources</span></span>

[<span data-ttu-id="f12c2-133">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="f12c2-133">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]