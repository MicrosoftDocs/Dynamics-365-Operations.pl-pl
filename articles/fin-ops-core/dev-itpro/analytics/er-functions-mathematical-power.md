---
title: POWER, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji POWER w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9b6693d7c1afebcf9c30d1bf8d72950053c305bd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274005"
---
# <a name="power-er-function"></a>POWER, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `POWER` zwraca wartość *rzeczywistą* reprezentującą wynik podniesienia określonej liczby dodatniej do określonej potęgi.

## <a name="syntax"></a>Składnia

```vb
POWER (number, power)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba rzeczywista* lub *Liczba całkowita*

Wartość numeryczna, którą należy podnieść do określonej potęgi.

`power`: *Liczba rzeczywista* lub *Liczba całkowita*

Wartość numeryczna reprezentują określoną potęgę.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="example-1"></a>Przykład 1

Funkcja `POWER (10, 2)` zwraca wartość **100**.

## <a name="example-2"></a>Przykład 2

Funkcja `POWER (4, 0.5)` zwraca wartość **2**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje matematyczne](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
