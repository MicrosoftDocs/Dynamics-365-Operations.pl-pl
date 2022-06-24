---
title: OR, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji OR w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: d2783b5aff34e6ab4b5bde5dfe39e92d20892634
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892959"
---
# <a name="or-er-function"></a>OR, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `OR` zwraca wartość *logiczną* **FALSE**, jeśli żadne wybrane warunki nie zostały spełnione. Jeśli dowolny wybrany warunek został spełniony, ta funkcja zwraca wartość *logiczną* **TRUE**.

## <a name="syntax"></a>Składnia

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argumenty

`condition 1`: *Wartość logiczna*

Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane. Ten argument jest wymagany.

`condition N`: *Wartość logiczna*

Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane. Te dodatkowe argumenty są opcjonalne.

## <a name="return-values"></a>Wartości zwracane

*Wartość logiczna*

Wyjściowa *wartość logiczna*.

## <a name="example"></a>Przykład

Funkcja `OR (1=2, "a"="a")` zwraca wartość **TRUE**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje logiczne](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]