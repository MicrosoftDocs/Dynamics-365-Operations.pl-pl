---
title: DATETIMEFORMAT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATETIMEFORMAT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 98919f40751a77465ae26acbd46af4396c588b13
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916414"
---
# <span data-ttu-id="44e29-103"><a name="DATETIMEFORMAT">DATETIMEFORMAT, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="44e29-103"><a name="DATETIMEFORMAT">DATETIMEFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="44e29-104">Funkcja `DATETIMEFORMAT` zwraca wartość *Ciąg*, która przedstawia daną wartość daty/godziny jako tekst w określonym formacie i opcjonalnie określonej [kulturze](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="44e29-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="44e29-105">Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="44e29-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="44e29-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="44e29-106">Syntax 1</span></span>

```
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="44e29-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="44e29-107">Syntax 2</span></span>

```
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="44e29-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="44e29-108">Arguments</span></span>

<span data-ttu-id="44e29-109">`datetime`: *Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="44e29-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="44e29-110">Wartość daty i godziny, która reprezentuje datę i godzinę do sformatowania.</span><span class="sxs-lookup"><span data-stu-id="44e29-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="44e29-111">`format`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="44e29-111">`format`: *String*</span></span>

<span data-ttu-id="44e29-112">Format ciągu wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="44e29-112">The format of the output string.</span></span>

<span data-ttu-id="44e29-113">`culture`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="44e29-113">`culture`: *String*</span></span>

<span data-ttu-id="44e29-114">Kultura do użycia na potrzeby formatowania.</span><span class="sxs-lookup"><span data-stu-id="44e29-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="44e29-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="44e29-115">Return values</span></span>

<span data-ttu-id="44e29-116">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="44e29-116">*String*</span></span>

<span data-ttu-id="44e29-117">Wyjściowa wartość ciągu.</span><span class="sxs-lookup"><span data-stu-id="44e29-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="44e29-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="44e29-118">Usage notes</span></span>

<span data-ttu-id="44e29-119">Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący.</span><span class="sxs-lookup"><span data-stu-id="44e29-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="44e29-120">Jeśli na przykład funkcja `DATETIMEFORMAT` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej.</span><span class="sxs-lookup"><span data-stu-id="44e29-120">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="44e29-121">Domyślna wartość `culture` to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="44e29-121">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="44e29-122">Gdy funkcja `DATETIMEFORMAT` konwertuje wartość danej daty/godziny, bierze pod uwagę ustawienia strefy czasowej użytkownika aplikacji, który uruchamia format ER, w którego kontekście jest wywoływana funkcja.</span><span class="sxs-lookup"><span data-stu-id="44e29-122">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="44e29-123">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="44e29-123">Example 1</span></span>

<span data-ttu-id="44e29-124">Funkcja `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` zwraca wartość daty/godziny bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="44e29-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="44e29-125">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="44e29-125">Example 2</span></span>

<span data-ttu-id="44e29-126">Funkcja `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` zwraca bieżącą datę/godzinę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24.12.2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.</span><span class="sxs-lookup"><span data-stu-id="44e29-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="44e29-127">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="44e29-127">Example 3</span></span>

<span data-ttu-id="44e29-128">Funkcja `DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` zwraca wartość ciągu **2019-11-12T08:00:00.0000000-08:00**, gdy jest wywoływana podczas procesu, który został zainicjowany przez użytkownika aplikacji z wartością strefy czasowej **(GMT-08:00) Czas pacyficzny (USA i Kanada)** w sekcji **Preferencje dotyczące języka i kraju/regionu**.</span><span class="sxs-lookup"><span data-stu-id="44e29-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="44e29-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="44e29-129">Additional resources</span></span>

[<span data-ttu-id="44e29-130">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="44e29-130">Date and time functions</span></span>](er-functions-category-datetime.md)
