---
title: Lista funkcji modułu ER w kategorii funkcji tekstowych
description: Ten temat zawiera ogólne informacje o funkcjach tekstowych obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 228620afc81e154eced572f3b6024d6836d00d66
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686034"
---
# <a name="list-of-er-functions-of-the-text-category"></a>Lista funkcji modułu ER w kategorii funkcji tekstowych

[!include [banner](../includes/banner.md)]

Funkcje tekstowe raportowania elektronicznego (ER) mogą służyć do wykonywania operacji na źródłach danych o typie danych *Ciąg*. Ten temat zawiera podsumowanie tych funkcji.

## <a name="list-of-supported-functions"></a>Lista obsługiwanych funkcji

| Funkcja | Opis |
|----------|-------------|
| [Char](er-functions-text-char.md) | Ta funkcja zwraca wartość typu *Ciąg*, która przedstawia pojedynczy znak, do którego odwołuje się określony numer Unicode. |
| [Złącz](er-functions-text-concatenate.md) | Ta funkcja zwraca wszystkie ciągi tekstowe określone jako wartość typu *Ciąg* po ich połączeniu w jeden ciąg. |
| [Format](er-functions-text-format.md) | Ta funkcja zwraca określoną wartość typu *Ciąg* po jej sformatowaniu przez zastąpienie wszystkich wystąpień elementu **%N** *N*-tym argumentem. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | Ta funkcja wyszukuje określoną wartość *wyliczenia* w źródle danych określonego wyliczenia przy użyciu nazwy wyliczenia, która jest określona jako wartość typu *Ciąg*. W przypadku znalezienia wartości typu *Wyliczenie* funkcja zwraca tę wartość. |
| [GuidValue](er-functions-text-guidvalue.md) | Ta funkcja przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *Identyfikator GUID*. |
| [JsonValue](er-functions-text-jsonvalue.md) | Ta funkcja analizuje dane w formacie JSON (JavaScript Object Notation), do których dostęp jest uzyskiwany za pośrednictwem wskazanej ścieżki oraz wyodrębnia wartość skalarną opartą na podanym identyfikatorze. Następnie zwraca wartość skalarną wyodrębnioną jako wartość typu *Ciąg*. |
| [Lewa](er-functions-text-left.md) | Ta funkcja zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków od początku określonego ciągu. |
| [Len](er-functions-text-len.md) | Ta funkcja zwraca wartość *Liczba całkowita*, która reprezentuje określoną liczbę znaków w określonym ciągu. |
| [Lower](er-functions-text-lower.md) | Ta funkcja zwraca określony ciąg tekstowy jako wartość *Ciąg* po przekonwertowaniu go na małe litery. |
| [Mid](er-functions-text-mid.md) | Ta funkcja zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków określonego ciągu od określonego położenia. |
| [NumberFormat](er-functions-text-numberformat.md) | Ta funkcja zwraca wartość *Ciąg*, który przedstawia określoną liczbę w określonym formacie i opcjonalnie określonej kulturze. |
| [NumeralsToText](er-functions-text-numeralstotext.md) | Ta funkcja zwraca określoną liczbę jako wartość *Ciąg* po jej zapisaniu (czyli przekonwertowaniu na ciągi tekstowe) w określonym języku. |
| [PadLeft](er-functions-text-padleft.md) | Ta funkcja zwraca wartość typu *Ciąg* o określonej długości, w której początek ciągu jest dopełniany co najmniej jednym wystąpieniem określonego znaku. |
| [QrCode](er-functions-text-qrcode.md) | Ta funkcja zwraca wartość typu *Kontener*, która przedstawia obraz kodu szybkiej odpowiedzi (kod QR) dla określonego ciągu w formacie binarnym. |
| [Zastąp](er-functions-text-replace.md) | Ta funkcja zwraca określony ciąg tekstowy jako wartość typu *Ciąg* po zastąpieniu go w całości lub częściowo innym ciągiem. |
| [Prawa](er-functions-text-right.md) | Ta funkcja zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków od końca określonego ciągu. |
| [Tekst](er-functions-text-text.md) | Ta funkcja zwraca określoną liczbę jako wartość typu *Ciąg* po przekształceniu na ciąg tekstowy, który jest sformatowany zgodnie z ustawieniami regionalnymi serwera bieżącego wystąpienia aplikacji. |
| [Przetłumacz](er-functions-text-translate.md) | Ta funkcja zwraca wartość typu *Ciąg*, która zawiera wynik zastąpienia określonego tekstu w znakach dla innego dostarczonego zbioru znaków. |
| [Trim](er-functions-text-trim.md) | Ta funkcja zwraca określony ciąg tekstowy jako wartość typu *Ciąg* po obcięciu spacji wiodących i końcowych oraz usunięciu spacji wielokrotnych spomiędzy wyrazów. |
| [Upper](er-functions-text-upper.md) | Ta funkcja zwraca określony ciąg tekstowy jako wartość *Ciąg* po przekonwertowaniu go na duże litery. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)
