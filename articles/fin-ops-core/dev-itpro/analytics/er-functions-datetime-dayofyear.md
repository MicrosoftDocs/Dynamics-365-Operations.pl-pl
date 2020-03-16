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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d24aabb582151b0b357b64a988cc932a9c9f3cea
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070674"
---
# <a name="DAYOFYEAR">DAYOFYEAR, funkcja ER</a>

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
