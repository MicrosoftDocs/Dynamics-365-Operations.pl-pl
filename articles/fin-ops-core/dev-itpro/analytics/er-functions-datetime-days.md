---
title: DAYS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DAYS w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 19e363e7bc8b8ad898244702ad6ba14bcf490f5ca2381b006a35dc0ed9309d49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750607"
---
# <a name="days-er-function"></a>DAYS, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `DAYS` zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między dwiema określonymi datami.

## <a name="syntax"></a>Składnia

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>Argumenty

`date 1`: *Data*

Wartość daty, która reprezentuje datę początkową na potrzeby obliczania liczby dni.

`date 2`: *Data*

Wartość daty, która reprezentuje datę końcową na potrzeby obliczania liczby dni.

## <a name="return-values"></a>Wartości zwracane

*Wartość całkowita*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Funkcja `DAYS` zwraca wartość dodatnią, gdy pierwsza data jest późniejsza niż druga data, wartość **0** (zero), gdy pierwsza data jest równa drugiej dacie, lub wartość ujemną, gdy pierwsza data jest wcześniejsza niż druga data.

## <a name="example"></a>Przykład

Funkcja `DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` zwraca wartość **-1**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]