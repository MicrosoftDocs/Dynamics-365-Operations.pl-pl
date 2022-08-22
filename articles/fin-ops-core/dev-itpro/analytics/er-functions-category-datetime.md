---
title: Lista funkcji modułu ER w kategorii Data i godzina
description: Ten artykuł zawiera ogólne informacje o funkcjach daty i godziny obsługiwanych w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: d77f41e10d927a9aae06b9ba0fc58ca237c071cd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291333"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>Lista funkcji modułu ER w kategorii Data i godzina

[!include [banner](../includes/banner.md)]

Funkcje daty i godziny w module raportowania elektronicznego (ER) mogą być używane do wyodrębniania informacji z wartości daty i godziny oraz do wykonywania operacji na nich. Ten artykuł zawiera podsumowanie tych funkcji.

## <a name="list-of-supported-functions"></a>Lista obsługiwanych funkcji

| Funkcja | Opis |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Ta funkcja zwraca wartość typu *[data/godzina](er-formula-supported-data-types-primitive.md#datetime)*, która jest określoną liczbą dni przed wybraną datą rozpoczęcia lub po niej. |
| [ChangeTimeZone](er-functions-datetime-changetimezone.md) | Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości daty/godziny w jednej strefie czasowej na wartość daty/godziny w innej strefie czasowej. |
| [DateFormat](er-functions-datetime-dateformat.md) | Ta funkcja zwraca wartość *[Ciąg](er-formula-supported-data-types-primitive.md#string)*, która przedstawia daną wartość daty jako tekst w określonym formacie i opcjonalnie określonej kulturze. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Ta funkcja zwraca wartość *Ciąg*, która przedstawia daną wartość daty/godziny jako tekst w określonym formacie i opcjonalnie określonej kulturze. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości tekstowej w określonym formacie i opcjonalnie określonej kulturze na wartość daty/godziny. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości daty na wartość daty/godziny w uniwersalnym czasie koordynowanym (czas uniwersalny Greenwich \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md) | Ta funkcja zwraca wartość *[Data](er-formula-supported-data-types-primitive.md#date)*, która jest konwertowana z wartości danego tekstu w określonym formacie i opcjonalnie określonej kulturze na wartość daty. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Ta funkcja zwraca wartość *[Liczba całkowita](er-formula-supported-data-types-primitive.md#integer)* reprezentującą liczbę dni między 1 stycznia a określoną datą. |
| [Dni](er-functions-datetime-days.md) | Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między dwiema określonymi datami. |
| [Now](er-functions-datetime-now.md) | Ta funkcja zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę serwera aplikacji. |
| [NullDate](er-functions-datetime-nulldate.md) | Ta funkcja zwraca wartość *Data*, która reprezentuje datę **null** (1 stycznia 1900). |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Ta funkcja zwraca wartość *Data/godzina*, która reprezentuje wartość **null** daty/godziny (1 stycznia 1900) w uniwersalnym czasie koordynowanym. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Ta funkcja zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę sesji aplikacji. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Ta funkcja zwraca wartość *Data*, która reprezentuje bieżącą datę sesji aplikacji. |
| [Dzisiaj](er-functions-datetime-today.md) | Ta funkcja zwraca wartość *Data*, która reprezentuje bieżącą datę serwera aplikacji. |
| [WeekNum](er-functions-datetime-weeknum.md) | Ta funkcja zwraca wartość *Liczba całkowita*, która reprezentuje tydzień w roku. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
