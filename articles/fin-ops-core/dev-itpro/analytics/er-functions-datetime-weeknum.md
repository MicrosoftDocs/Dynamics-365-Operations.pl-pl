---
title: WEEKNUM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji WEEKNUM w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 37e62b32896e2030b3322a89ac4acdd6c18d5e3c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982184"
---
# <a name="weeknum-er-function"></a>WEEKNUM, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `WEEKNUM` zwraca wartość *[Liczba całkowita](er-formula-supported-data-types-primitive.md#integer)* reprezentującą tydzień w roku, zawierający wybraną *[datę](er-formula-supported-data-types-primitive.md#date)*. Obliczenia są oparte na regułach zależnych od kultury, które definiują tydzień kalendarzowy i pierwszy dzień tygodnia.

## <a name="syntax"></a>Składnia

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">Argumenty</a>

`date`: *Data*

Wartość daty, która reprezentuje datę do użycia do obliczania tygodnia w roku.

`culture`: *[ciąg](er-formula-supported-data-types-primitive.md#string)*

Kultura do użycia na potrzeby obliczania. Można używać kodów kultury, które są obsługiwane zgodnie ze [standardami](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0) środowiska .NET.

## <a name="return-values"></a>Wartości zwracane

*Wartość całkowita*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Tydzień roku jest obliczany na podstawie normy [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), jeśli ta norma została przyjęta przez kraj lub region, dla których podane są ustawienia lokalne w czasie wykonywania. W przeciwnym razie obliczenia są oparte na normach krajowych specyficznych dla danego kraju/regionu.

Jeśli nieobsługiwany kod [kultury](#arguments) jest dostarczany jako argument funkcji `WEEKNUM` w czasie wykonywania, generowany jest wyjątek. Jeśli jako kod kultury jest podany pusty ciąg, do obliczania numeru tygodnia używany jest angielski kalendarz z neutralnego kraju.

## <a name="examples"></a>Przykłady

Funkcja `WEEKNUM (DATEVALUE ("01-01-2020", "de"))` zwraca wartość **1**.

Funkcja `WEEKNUM (DATEVALUE ("01-01-2021", "de"))` zwraca wartość **53**.

Funkcja `WEEKNUM (DATEVALUE ("01-01-2022", "de"))` zwraca wartość **52**.

Funkcja `WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` zwraca wartość **21**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
