---
title: DAYOFYEAR, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji DAYOFYEAR w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: fc4d1d3293c31b1b89a7390c8ac313e1407d433e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848788"
---
# <a name="dayofyear-er-function"></a>DAYOFYEAR, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `DAYOFYEAR` zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między 1 stycznia a określoną datą.

## <a name="syntax"></a>Składnia

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a>Argumenty

`date`: *Data*

Wartość daty, która reprezentuje datę do użycia do obliczania liczby dni.

## <a name="return-values"></a>Wartości zwracane

*Wartość całkowita*

Wynikowa wartość numeryczna.

## <a name="example-1"></a>Przykład 1

Funkcja `DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` zwraca wartość **61**.

## <a name="example-2"></a>Przykład 2

Funkcja `DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` zwraca wartość **1**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]