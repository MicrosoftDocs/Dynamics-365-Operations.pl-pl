---
title: Lista funkcji modułu ER w kategorii konwersji typu
description: Ten temat zawiera ogólne informacje o funkcjach konwersji obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 199d51ae8a4dbdd7d2f3bd290a2b487ceb1174dc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752611"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="ce8a6-103">Lista funkcji modułu ER w kategorii konwersji typu</span><span class="sxs-lookup"><span data-stu-id="ce8a6-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce8a6-104">Funkcje konwersji typu w module raportowania elektronicznego (ER) mogą być używane do konwertowania wartości między typami.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="ce8a6-105">Ten temat zawiera podsumowanie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="ce8a6-106">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="ce8a6-106">Type conversion functions</span></span>

| <span data-ttu-id="ce8a6-107">Funkcja</span><span class="sxs-lookup"><span data-stu-id="ce8a6-107">Function</span></span> | <span data-ttu-id="ce8a6-108">Opis</span><span class="sxs-lookup"><span data-stu-id="ce8a6-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="ce8a6-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="ce8a6-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="ce8a6-110">Ta funkcja zwraca wartość *Int64*, która reprezentuje określony ciąg.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="ce8a6-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="ce8a6-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="ce8a6-112">Ta funkcja zwraca wartość *Int*, która reprezentuje określony ciąg.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="ce8a6-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="ce8a6-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="ce8a6-114">Ta funkcja zwraca wartość *rzeczywistą*, która jest konwertowana z określonej wartości typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="ce8a6-115">Podczas konwersji są uwzględniane wybrane separatory dziesiętne i separatory grupowania cyfr.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="ce8a6-116">Wartość</span><span class="sxs-lookup"><span data-stu-id="ce8a6-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="ce8a6-117">Ta funkcja zwraca wartość *rzeczywistą*, która jest konwertowana z określonej wartości typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-container-category"></a><span data-ttu-id="ce8a6-118">Funkcje konwersji typu w kategorii kontenerów</span><span class="sxs-lookup"><span data-stu-id="ce8a6-118">Type conversion functions in the container category</span></span>

<span data-ttu-id="ce8a6-119">W poniższej tabeli opisano funkcje konwersji typu w kategorii [kontenerów](er-functions-category-container.md).</span><span class="sxs-lookup"><span data-stu-id="ce8a6-119">The following table describes the type conversion functions in the [container](er-functions-category-container.md) category.</span></span>

| <span data-ttu-id="ce8a6-120">Funkcja</span><span class="sxs-lookup"><span data-stu-id="ce8a6-120">Function</span></span> | <span data-ttu-id="ce8a6-121">opis</span><span class="sxs-lookup"><span data-stu-id="ce8a6-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="ce8a6-122">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="ce8a6-122">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="ce8a6-123">Funkcja ta przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *Kontener*.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-123">This function converts the specified input of the *String* type to a data item of the *Container* type.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="ce8a6-124">Funkcje konwersji typu w kategorii daty i godziny</span><span class="sxs-lookup"><span data-stu-id="ce8a6-124">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="ce8a6-125">W poniższej tabeli opisano funkcje konwersji typu w [kategorii daty i godziny](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="ce8a6-125">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="ce8a6-126">Funkcja</span><span class="sxs-lookup"><span data-stu-id="ce8a6-126">Function</span></span> | <span data-ttu-id="ce8a6-127">Opis</span><span class="sxs-lookup"><span data-stu-id="ce8a6-127">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="ce8a6-128">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="ce8a6-128">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="ce8a6-129">Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości *Ciąg* w określonym formacie i opcjonalnie określonej kulturze na wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-129">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="ce8a6-130">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="ce8a6-130">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="ce8a6-131">Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości *Data* na wartość daty/godziny w uniwersalnym czasie koordynowanym (czas uniwersalny Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="ce8a6-131">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="ce8a6-132">DateValue</span><span class="sxs-lookup"><span data-stu-id="ce8a6-132">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="ce8a6-133">Ta funkcja zwraca wartość *Data*, która jest konwertowana z danej wartości *Ciąg* w określonym formacie i opcjonalnie określonej kulturze na wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-133">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="ce8a6-134">Funkcje konwersji typu w kategorii listy</span><span class="sxs-lookup"><span data-stu-id="ce8a6-134">Type conversion functions in the list category</span></span>

<span data-ttu-id="ce8a6-135">W poniższej tabeli opisano funkcje konwersji typu w [kategorii listy](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="ce8a6-135">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="ce8a6-136">Funkcja</span><span class="sxs-lookup"><span data-stu-id="ce8a6-136">Function</span></span> | <span data-ttu-id="ce8a6-137">Opis</span><span class="sxs-lookup"><span data-stu-id="ce8a6-137">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="ce8a6-138">Lista</span><span class="sxs-lookup"><span data-stu-id="ce8a6-138">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="ce8a6-139">Ta funkcja zwraca wartość typu *Lista rekordów* jako nową listę utworzoną na podstawie określonych argumentów typu *Kontener (rekord)*.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-139">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="ce8a6-140">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="ce8a6-140">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="ce8a6-141">Ta funkcja zwraca wartość typu *Lista rekordów*, która jest tworzona na podstawie struktury danego argumentu typu *Wyliczenie* lub *Kontener (rekord)*.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-141">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="ce8a6-142">Podział</span><span class="sxs-lookup"><span data-stu-id="ce8a6-142">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="ce8a6-143">Ta funkcja dzieli określoną wartość *Ciąg* na podciągi i zwraca wynik jako nową wartość *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-143">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="ce8a6-144">StringJoin</span><span class="sxs-lookup"><span data-stu-id="ce8a6-144">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="ce8a6-145">Ta funkcja zwraca wartość typu *Ciąg* zawierającą połączone wartości z określonego pola wybranej wartości *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-145">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="ce8a6-146">Wartości mogą być rozdzielone wybranym separatorem.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-146">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="ce8a6-147">Funkcje konwersji typu w kategorii tekstu</span><span class="sxs-lookup"><span data-stu-id="ce8a6-147">Type conversion functions in the text category</span></span>

<span data-ttu-id="ce8a6-148">W poniższej tabeli opisano funkcje konwersji typu w [kategorii tekstu](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="ce8a6-148">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="ce8a6-149">Funkcja</span><span class="sxs-lookup"><span data-stu-id="ce8a6-149">Function</span></span> | <span data-ttu-id="ce8a6-150">Opis</span><span class="sxs-lookup"><span data-stu-id="ce8a6-150">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="ce8a6-151">Char</span><span class="sxs-lookup"><span data-stu-id="ce8a6-151">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="ce8a6-152">Ta funkcja zwraca wartość typu *Ciąg*, która reprezentuje pojedynczy znak, do którego odwołuje się określony numer Unicode.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-152">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="ce8a6-153">GuidValue</span><span class="sxs-lookup"><span data-stu-id="ce8a6-153">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="ce8a6-154">Ta funkcja przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *Identyfikator GUID*.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-154">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="ce8a6-155">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="ce8a6-155">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="ce8a6-156">Ta funkcja zwraca wartość *Ciąg*, która reprezentuje określoną liczbę w określonym formacie i opcjonalnie określonej kulturze.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-156">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="ce8a6-157">QrCode</span><span class="sxs-lookup"><span data-stu-id="ce8a6-157">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="ce8a6-158">Ta funkcja zwraca wartość typu *Kontener*, która przedstawia obraz kodu szybkiej odpowiedzi (kod QR) dla określonego ciągu w formacie binarnym.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-158">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="ce8a6-159">Tekst</span><span class="sxs-lookup"><span data-stu-id="ce8a6-159">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="ce8a6-160">Ta funkcja zwraca określoną wartość typu *Ciąg*, która reprezentuje określoną liczbę po przekształceniu na ciąg tekstowy, który jest sformatowany zgodnie z ustawieniami regionalnymi serwera bieżącego wystąpienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ce8a6-160">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="ce8a6-161">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ce8a6-161">Additional resources</span></span>

[<span data-ttu-id="ce8a6-162">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="ce8a6-162">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="ce8a6-163">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="ce8a6-163">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="ce8a6-164">Język formuł raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="ce8a6-164">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]