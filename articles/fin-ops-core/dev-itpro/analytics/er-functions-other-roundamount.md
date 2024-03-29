---
title: ROUNDAMOUNT, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji ROUNDAMOUNT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 0e4de43f865ca21822ab2c0c345026d2e9113ca2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286038"
---
# <a name="roundamount-er-function"></a>ROUNDAMOUNT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ROUNDAMOUNT` zwraca wartość *rzeczywistą* jako wynik zaokrąglania określonej liczby do najbliższej wielokrotności określonej liczby zgodnie z określoną regułą zaokrąglania.

## <a name="syntax"></a>Składnia

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>Argumenty

`number`: *Int* lub *Real*

Wartość numeryczna do zaokrąglenia.

`decimals`: *Int* lub *Real*

Liczba, do której wielokrotności musi być zaokrąglona wartość parametru `number`.

`round rule`: *Wartość wyliczenia*

Wartość wyliczenia **RoundOffType**, która definiuje regułę zaokrąglania. To wyliczenie oferuje następujące wartości:

- Normalne (Ordinary)
- W dół (RoundDown)
- Zaokrąglanie w górę (RoundUp)

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość liczbowa jest wielokrotnością wartości określonej przez parametr `decimals` i jest najbliższa wartości określonej przez parametr `number`.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Gdy parametr `number` ma wartość zero, ta funkcja zawsze zwraca wartość zero.

Gdy parametr `decimals` ma wartość zero, ta funkcja zaokrągla do domyślnej wartości zaokrąglenia. Gdy parametr `round rule` jest ustawiony na **RoundOffType.Ordinary**, domyślna wartość zaokrąglenia to **0,01**. W przeciwnym razie wartość domyślna zaokrąglenia to **1,0**.

Gdy parametr `round rule` jest ustawiony na **RoundOffType.Ordinary**, ta funkcja zaokrągla do najbliższej ilości zaokrąglenia.

Gdy parametr `round rule` jest ustawiony na **RoundOffType.RoundDown**, ta funkcja zaokrągla do zera dla najbliższej ilości zaokrąglenia.

Gdy parametr `round rule` jest ustawiony na **RoundOffType.RoundUp**, ta funkcja zaokrągla od zera dla najbliższej ilości zaokrąglenia.

Gdy parametr `round rule` jest ustawiony na **RoundOffType.Ordinary**, ta funkcja zachowuje się jak funkcja [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) programu Excel i funkcja [ROUND](../dev-ref/xpp-math-run-time-functions.md#round) języka X++.

## <a name="remarks"></a>Uwagi

Aby zaokrąglić wartość liczbową do określonej liczby miejsc dziesiętnych, należy użyć funkcji [ROUND](er-functions-mathematical-round.md).

## <a name="example"></a>Przykład

Jeśli parametr **model.RoundOff** został ustawiony na **RoundOffType.Ordinary**, funkcja `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` zwraca wartość 7,35. 

Jeśli parametr **model.RoundOff** został ustawiony na **RoundOffType.RoundDown**, funkcja `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` zwraca wartość 7,35. 

Jeśli parametr **model.RoundOff** został ustawiony na **RoundOffType.RoundUp**, funkcja `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` zwraca wartość 8,4.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)

[Funkcje matematyczne](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
