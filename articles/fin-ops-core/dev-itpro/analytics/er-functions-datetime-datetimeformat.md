---
title: DATETIMEFORMAT, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji DATETIMEFORMAT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 09/08/2021
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
ms.openlocfilehash: 693ec465b56a1c7fbd9828c9e972da8a3e3fc6d4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896800"
---
# <a name="datetimeformat-er-function"></a>DATETIMEFORMAT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `DATETIMEFORMAT` zwraca wartość *[Ciąg](er-formula-supported-data-types-primitive.md#string)*, która przedstawia daną wartość daty/godziny jako tekst w określonym formacie i opcjonalnie określonej [kulturze](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](/dotnet/standard/base-types/standard-date-and-time-format-strings) i [niestandardowe](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Składnia 1

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a>Składnia 2

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a>Argumenty

`datetime`: *[Data/godzina](er-formula-supported-data-types-primitive.md#datetime)*

Wartość daty i godziny, która reprezentuje datę i godzinę do sformatowania.

`format`: *Ciąg*

Format ciągu wyjściowego. Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](/dotnet/standard/base-types/standard-date-and-time-format-strings) i [niestandardowe](/dotnet/standard/base-types/custom-date-and-time-format-strings).

> [!NOTE]
> W przypadku używania formatu standardowego lub niestandardowego w ciągu formatu jest uwzględniana wielkość liter. Na przykład [standardowy](/dotnet/standard/base-types/standard-date-and-time-format-strings) format „d” zwraca datę przy użyciu wzorca daty krótkiej, a standardowy modyfikator formatu „D” zwraca datę przy użyciu wzorca daty długiej. Ponadto [niestandardowy](/dotnet/standard/base-types/custom-date-and-time-format-strings) modyfikator formatu „M” zwraca miesiąc z okresu od 1 do 12, podczas gdy niestandardowy modyfikator formatu „m” zwraca minuty od 0 do 59.

`culture`: *Ciąg*

Kultura do użycia na potrzeby formatowania. Aby uzyskać informacje o obsługiwanych kulturach, zobacz temat [Kultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wyjściowa wartość ciągu.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący. Jeśli na przykład funkcja `DATETIMEFORMAT` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej. Domyślna wartość `culture` to **EN-US**.

Gdy funkcja `DATETIMEFORMAT` konwertuje wartość danej daty/godziny, bierze pod uwagę ustawienia strefy czasowej użytkownika aplikacji, który uruchamia format ER, w którego kontekście jest wywoływana funkcja.

## <a name="example-1"></a>Przykład 1

Funkcja `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` zwraca wartość daty/godziny bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.

## <a name="example-2"></a>Przykład 2

Funkcja `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` zwraca bieżącą datę/godzinę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24.12.2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.

## <a name="example-3"></a>Przykład 3

Funkcja `DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` zwraca wartość ciągu **2019-11-12T08:00:00.0000000-08:00**, gdy funkcja jest wywoływana podczas procesu, który został zainicjowany przez użytkownika aplikacji z wartością strefy czasowej **(GMT-08:00) Czas pacyficzny (USA i Kanada)** w sekcji **Preferencje dotyczące języka i kraju/regionu**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
