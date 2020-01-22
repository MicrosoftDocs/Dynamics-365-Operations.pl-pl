---
title: Lista funkcji modułu ER w kategorii konwersji typu
description: Ten temat zawiera ogólne informacje o funkcjach konwersji obsługiwanych w module Raportowanie elektroniczne (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cfa5deb3b2c00565759e4334a002bf112f888ac
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917656"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a>Lista funkcji modułu ER w kategorii konwersji typu

[!include [banner](../includes/banner.md)]

Funkcje konwersji typu w module raportowania elektronicznego (ER) mogą być używane do konwertowania wartości między typami. Ten temat zawiera podsumowanie tych funkcji.

## <a name="type-conversion-functions"></a>Funkcje konwersji typu

| Funkcja | Opis |
|----------|-------------|
| [Int64Value](er-functions-conversion-int64value.md)   | Ta funkcja zwraca wartość *Int64*, która reprezentuje określony ciąg. |
| [IntValue](er-functions-conversion-intvalue.md)       | Ta funkcja zwraca wartość *Int*, która reprezentuje określony ciąg. |
| [NumberValue](er-functions-conversion-numbervalue.md) | Ta funkcja zwraca wartość *rzeczywistą*, która jest konwertowana z określonej wartości typu *Ciąg*. Podczas konwersji są uwzględniane wybrane separatory dziesiętne i separatory grupowania cyfr. |
| [Wartość](er-functions-conversion-value.md)             | Ta funkcja zwraca wartość *rzeczywistą*, która jest konwertowana z określonej wartości typu *Ciąg*. |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a>Funkcje konwersji typu w kategorii daty i godziny

W poniższej tabeli opisano funkcje konwersji typu w [kategorii daty i godziny](er-functions-category-datetime.md).

| Funkcja | Opis |
|----------|-------------|
| [DateTimeValue](er-functions-datetime-datetimevalue.md)   | Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości *Ciąg* w określonym formacie i opcjonalnie określonej kulturze na wartość daty/godziny. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Ta funkcja zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości *Data* na wartość daty/godziny w uniwersalnym czasie koordynowanym (czas uniwersalny Greenwich \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md)           | Ta funkcja zwraca wartość *Data*, która jest konwertowana z danej wartości *Ciąg* w określonym formacie i opcjonalnie określonej kulturze na wartość daty/godziny. |

## <a name="type-conversion-functions-in-the-list-category"></a>Funkcje konwersji typu w kategorii listy

W poniższej tabeli opisano funkcje konwersji typu w [kategorii listy](er-functions-category-list.md).

| Funkcja | Opis |
|----------|-------------|
| [Lista](er-functions-list-list.md)                 | Ta funkcja zwraca wartość typu *Lista rekordów* jako nową listę utworzoną na podstawie określonych argumentów typu *Kontener (rekord)*. |
| [ListOfFields](er-functions-list-listoffields.md) | Ta funkcja zwraca wartość typu *Lista rekordów*, która jest tworzona na podstawie struktury danego argumentu typu *Wyliczenie* lub *Kontener (rekord)*. |
| [Podział](er-functions-list-split.md)               | Ta funkcja dzieli określoną wartość *Ciąg* na podciągi i zwraca wynik jako nową wartość *Lista rekordów*. |
| [StringJoin](er-functions-list-stringjoin.md)     | Ta funkcja zwraca wartość typu *Ciąg* zawierającą połączone wartości z określonego pola wybranej wartości *Lista rekordów*. Wartości mogą być rozdzielone wybranym separatorem. |

## <a name="type-conversion-functions-in-the-text-category"></a>Funkcje konwersji typu w kategorii tekstu

W poniższej tabeli opisano funkcje konwersji typu w [kategorii tekstu](er-functions-category-text.md).

| Funkcja | Opis |
|----------|-------------|
| [Char](er-functions-text-char.md)                 | Ta funkcja zwraca wartość typu *Ciąg*, która reprezentuje pojedynczy znak, do którego odwołuje się określony numer Unicode. |
| [GuidValue](er-functions-text-guidvalue.md)       | Ta funkcja przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *Identyfikator GUID*. |
| [NumberFormat](er-functions-text-numberformat.md) | Ta funkcja zwraca wartość *Ciąg*, która reprezentuje określoną liczbę w określonym formacie i opcjonalnie określonej kulturze. |
| [QrCode](er-functions-text-qrcode.md)             | Ta funkcja zwraca wartość typu *Kontener*, która przedstawia obraz kodu szybkiej odpowiedzi (kod QR) dla określonego ciągu w formacie binarnym. |
| [Tekst](er-functions-text-text.md)                 | Ta funkcja zwraca określoną wartość typu *Ciąg*, która reprezentuje określoną liczbę po przekształceniu na ciąg tekstowy, który jest sformatowany zgodnie z ustawieniami regionalnymi serwera bieżącego wystąpienia aplikacji. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)
