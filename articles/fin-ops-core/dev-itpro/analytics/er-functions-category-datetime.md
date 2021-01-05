---
title: Lista funkcji modułu ER w kategorii Data i godzina
description: Ten temat zawiera ogólne informacje o funkcjach daty i godziny obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 2745298ae1f6787c3de5a4aaf6a2a6350f5f3e85
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686226"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a><span data-ttu-id="1c924-103">Lista funkcji modułu ER w kategorii Data i godzina</span><span class="sxs-lookup"><span data-stu-id="1c924-103">List of ER functions in the Date and time category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1c924-104">Funkcje daty i godziny w module raportowania elektronicznego (ER) mogą być używane do wyodrębniania informacji z wartości daty i godziny oraz do wykonywania operacji na nich.</span><span class="sxs-lookup"><span data-stu-id="1c924-104">Electronic reporting (ER) date and time functions can be used to extract information from date and time values, and to perform operations on them.</span></span> <span data-ttu-id="1c924-105">Ten temat zawiera podsumowanie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="1c924-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="1c924-106">Lista obsługiwanych funkcji</span><span class="sxs-lookup"><span data-stu-id="1c924-106">List of supported functions</span></span>

| <span data-ttu-id="1c924-107">Funkcja</span><span class="sxs-lookup"><span data-stu-id="1c924-107">Function</span></span> | <span data-ttu-id="1c924-108">Opis</span><span class="sxs-lookup"><span data-stu-id="1c924-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="1c924-109">AddDays</span><span class="sxs-lookup"><span data-stu-id="1c924-109">AddDays</span></span>](er-functions-datetime-adddays.md) | <span data-ttu-id="1c924-110">Ta funkcja zwraca wartość *DateTime*, która jest określoną liczbą dni przed wybraną datą rozpoczęcia lub po niej.</span><span class="sxs-lookup"><span data-stu-id="1c924-110">This function returns a *DateTime* value that is the specified number of days before or after a specified start date.</span></span> |
| [<span data-ttu-id="1c924-111">DateFormat</span><span class="sxs-lookup"><span data-stu-id="1c924-111">DateFormat</span></span>](er-functions-datetime-dateformat.md) | <span data-ttu-id="1c924-112">Ta funkcja zwraca wartość *Ciąg*, która przedstawia daną wartość daty jako tekst w określonym formacie i opcjonalnie określonej kulturze.</span><span class="sxs-lookup"><span data-stu-id="1c924-112">This function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="1c924-113">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="1c924-113">DateTimeFormat</span></span>](er-functions-datetime-datetimeformat.md) | <span data-ttu-id="1c924-114">Ta funkcja zwraca wartość *Ciąg*, która przedstawia daną wartość daty/godziny jako tekst w określonym formacie i opcjonalnie określonej kulturze.</span><span class="sxs-lookup"><span data-stu-id="1c924-114">This function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="1c924-115">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="1c924-115">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md) | <span data-ttu-id="1c924-116">Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości tekstowej w określonym formacie i opcjonalnie określonej kulturze na wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="1c924-116">This function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="1c924-117">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="1c924-117">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="1c924-118">Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości daty na wartość daty/godziny w uniwersalnym czasie koordynowanym (czas uniwersalny Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="1c924-118">This function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="1c924-119">DateValue</span><span class="sxs-lookup"><span data-stu-id="1c924-119">DateValue</span></span>](er-functions-datetime-datevalue.md) | <span data-ttu-id="1c924-120">Ta funkcja zwraca wartość *Data*, która jest konwertowana z wartości danego tekstu w określonym formacie i opcjonalnie określonej kulturze na wartość daty.</span><span class="sxs-lookup"><span data-stu-id="1c924-120">This function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified culture to a date value.</span></span> |
| [<span data-ttu-id="1c924-121">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="1c924-121">DayOfYear</span></span>](er-functions-datetime-dayofyear.md) | <span data-ttu-id="1c924-122">Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między 1 stycznia a określoną datą.</span><span class="sxs-lookup"><span data-stu-id="1c924-122">This function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span> |
| [<span data-ttu-id="1c924-123">Dni</span><span class="sxs-lookup"><span data-stu-id="1c924-123">Days</span></span>](er-functions-datetime-days.md) | <span data-ttu-id="1c924-124">Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między dwiema określonymi datami.</span><span class="sxs-lookup"><span data-stu-id="1c924-124">This function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span> |
| [<span data-ttu-id="1c924-125">Now</span><span class="sxs-lookup"><span data-stu-id="1c924-125">Now</span></span>](er-functions-datetime-now.md) | <span data-ttu-id="1c924-126">Ta funkcja zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę serwera aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1c924-126">This function returns a *DateTime* value that represents the current application server date and time.</span></span> |
| [<span data-ttu-id="1c924-127">NullDate</span><span class="sxs-lookup"><span data-stu-id="1c924-127">NullDate</span></span>](er-functions-datetime-nulldate.md) | <span data-ttu-id="1c924-128">Ta funkcja zwraca wartość *Data*, która reprezentuje datę **null** (1 stycznia 1900).</span><span class="sxs-lookup"><span data-stu-id="1c924-128">This function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span> |
| [<span data-ttu-id="1c924-129">NullDateTime</span><span class="sxs-lookup"><span data-stu-id="1c924-129">NullDateTime</span></span>](er-functions-datetime-nulldatetime.md) | <span data-ttu-id="1c924-130">Ta funkcja zwraca wartość *Data/godzina*, która reprezentuje wartość **null** daty/godziny (1 stycznia 1900) w uniwersalnym czasie koordynowanym.</span><span class="sxs-lookup"><span data-stu-id="1c924-130">This function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time.</span></span> |
| [<span data-ttu-id="1c924-131">SessionNow</span><span class="sxs-lookup"><span data-stu-id="1c924-131">SessionNow</span></span>](er-functions-datetime-sessionnow.md) | <span data-ttu-id="1c924-132">Ta funkcja zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę sesji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1c924-132">This function returns a *DateTime* value that represents the current application session date and time.</span></span> |
| [<span data-ttu-id="1c924-133">SessionToday</span><span class="sxs-lookup"><span data-stu-id="1c924-133">SessionToday</span></span>](er-functions-datetime-sessiontoday.md) | <span data-ttu-id="1c924-134">Ta funkcja zwraca wartość *Data*, która reprezentuje bieżącą datę sesji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1c924-134">This function returns a *Date* value that represents the current application session date.</span></span> |
| [<span data-ttu-id="1c924-135">Dzisiaj</span><span class="sxs-lookup"><span data-stu-id="1c924-135">Today</span></span>](er-functions-datetime-today.md) | <span data-ttu-id="1c924-136">Ta funkcja zwraca wartość *Data*, która reprezentuje bieżącą datę serwera aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1c924-136">This function returns a *Date* value that represents the current application server date.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="1c924-137">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1c924-137">Additional resources</span></span>

[<span data-ttu-id="1c924-138">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="1c924-138">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="1c924-139">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="1c924-139">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="1c924-140">Język formuł raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="1c924-140">Electronic reporting formula language</span></span>](er-formula-language.md)
