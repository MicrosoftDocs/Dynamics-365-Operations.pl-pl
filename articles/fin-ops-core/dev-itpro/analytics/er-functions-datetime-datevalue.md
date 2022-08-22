---
title: DATEVALUE, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji DATEVALUE w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 09/08/2021
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
ms.openlocfilehash: 290a4665d3527c0f0954c46cb0a0a14677b93218
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268707"
---
# <a name="datevalue-er-function"></a>DATEVALUE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `DATEVALUE` zwraca wartość *[daty](er-formula-supported-data-types-primitive.md#date)*, która jest konwertowana z wartości danego tekstu w określonym formacie i opcjonalnie określonej [kulturze](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) na wartość daty. Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](/dotnet/standard/base-types/standard-date-and-time-format-strings) i [niestandardowe](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Składnia 1

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Składnia 2

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argumenty

`text`: *[Ciąg](er-formula-supported-data-types-primitive.md#string)*

Tekst reprezentujący wartość do sformatowania.

`format`: *Ciąg*

Format danego tekstu. Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](/dotnet/standard/base-types/standard-date-and-time-format-strings) i [niestandardowe](/dotnet/standard/base-types/custom-date-and-time-format-strings).

`culture`: *Ciąg*

Kultura używana do formatowania danego tekstu. Aby uzyskać informacje o obsługiwanych kulturach, zobacz temat [Kultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Wartości zwracane

*Data*

Wyjściowa wartość daty.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Gdy kultura nie jest zdefiniowana jako argument wywołanej funkcji, wartość `culture` jest definiowana przez kontekst wywołujący. Jeśli na przykład funkcja `DATEVALUE` jest wywoływana przy użyciu składni 1 w formacie raportowania elektronicznego (ER) dla elementu **PLIK**, który jest skonfigurowany do używania kultury niemieckiej, konwersja zostanie wykonana przy użyciu kultury niemieckiej. Domyślna wartość `culture` to **EN-US**.

## <a name="example-1"></a>Przykład 1

Funkcja `DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` zwraca datę **21 grudnia 2016 roku** zgodnie z określonym formatem niestandardowym i domyślną kulturą **EN-US** aplikacji.

## <a name="example-2"></a>Przykład 2

Funkcja `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` zwraca wartość daty **21 stycznia 2016** na podstawie określonego formatu niestandardowego i kultury.

Natomiast funkcja `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` zgłasza wyjątek w celu poinformowania użytkownika, że podany ciąg nie został rozpoznany jako prawidłowa data.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
