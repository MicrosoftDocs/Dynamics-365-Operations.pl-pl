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