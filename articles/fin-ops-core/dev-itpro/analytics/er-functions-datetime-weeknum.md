---
title: WEEKNUM, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji WEEKNUM w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 4658f88b7e353e651177fad0c8636c5403be1256
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268155"
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
