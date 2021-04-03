---
title: POWER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji POWER w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9c45e7f9b47a3f0ff4445b1dd160def0ada3a56e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570429"
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