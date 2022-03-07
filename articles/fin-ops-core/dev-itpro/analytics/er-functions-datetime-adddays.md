---
title: ADDDAYS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ADDDAYS w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/03/2019
ms.topic: article
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
ms.openlocfilehash: 0c420daa04b8e22504d25d317c75826f1d1914b7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747066"
---
# <a name="adddays-er-function"></a>ADDDAYS, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ADDDAYS` oblicza wartość *Data/godzina*, która jest określoną liczbą dni przed wybraną datą rozpoczęcia lub po niej.

## <a name="syntax"></a>Składnia

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>Argumenty

`datetime`: *Data/godzina*

Wartość daty/godziny, która reprezentuje datę początkową.

`days`: *Liczba całkowita*

Liczba dni przed lub po `datetime`.

## <a name="return-values"></a>Wartości zwracane

*Data/godzina*

Wyjściowa wartość daty/godziny.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wartość dodatnia elementu `days` generuje przyszłą datę. Wartość ujemna generuje datę przeszłą.

## <a name="example-1"></a>Przykład 1

Funkcja `ADDDAYS (NOW(), 7)` zwraca datę i godzinę siedem dni w przyszłości.

## <a name="example-2"></a>Przykład 2

Funkcja `ADDDAYS (NOW(), -3)` zwraca datę i godzinę trzy dni w przeszłości.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]