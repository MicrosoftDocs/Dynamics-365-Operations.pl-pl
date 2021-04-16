---
title: Lista funkcji modułu ER w kategorii Data i godzina
description: Ten temat zawiera ogólne informacje o funkcjach daty i godziny obsługiwanych w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 2dd8524c9cd368f0fe64347e3212b419bb0902b4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744568"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>Lista funkcji modułu ER w kategorii Data i godzina

[!include [banner](../includes/banner.md)]

Funkcje daty i godziny w module raportowania elektronicznego (ER) mogą być używane do wyodrębniania informacji z wartości daty i godziny oraz do wykonywania operacji na nich. Ten temat zawiera podsumowanie tych funkcji.

## <a name="list-of-supported-functions"></a>Lista obsługiwanych funkcji

| Funkcja | Opis |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Ta funkcja zwraca wartość *DateTime*, która jest określoną liczbą dni przed wybraną datą rozpoczęcia lub po niej. |
| [DateFormat](er-functions-datetime-dateformat.md) | Ta funkcja zwraca wartość *Ciąg*, która przedstawia daną wartość daty jako tekst w określonym formacie i opcjonalnie określonej kulturze. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Ta funkcja zwraca wartość *Ciąg*, która przedstawia daną wartość daty/godziny jako tekst w określonym formacie i opcjonalnie określonej kulturze. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości tekstowej w określonym formacie i opcjonalnie określonej kulturze na wartość daty/godziny. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości daty na wartość daty/godziny w uniwersalnym czasie koordynowanym (czas uniwersalny Greenwich \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md) | Ta funkcja zwraca wartość *Data*, która jest konwertowana z wartości danego tekstu w określonym formacie i opcjonalnie określonej kulturze na wartość daty. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między 1 stycznia a określoną datą. |
| [Dni](er-functions-datetime-days.md) | Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między dwiema określonymi datami. |
| [Now](er-functions-datetime-now.md) | Ta funkcja zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę serwera aplikacji. |
| [NullDate](er-functions-datetime-nulldate.md) | Ta funkcja zwraca wartość *Data*, która reprezentuje datę **null** (1 stycznia 1900). |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Ta funkcja zwraca wartość *Data/godzina*, która reprezentuje wartość **null** daty/godziny (1 stycznia 1900) w uniwersalnym czasie koordynowanym. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Ta funkcja zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę sesji aplikacji. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Ta funkcja zwraca wartość *Data*, która reprezentuje bieżącą datę sesji aplikacji. |
| [Dzisiaj](er-functions-datetime-today.md) | Ta funkcja zwraca wartość *Data*, która reprezentuje bieżącą datę serwera aplikacji. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]