---
title: DAYOFYEAR, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DAYOFYEAR w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: b9b937e7fae3e90d1a87196fab653dfac8e94179
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682396"
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