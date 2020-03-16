---
title: OR, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji OR w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 2a850b1cbe7224ab1a7b2bd39ac4667304781cbb
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041683"
---
# <a name="OR">OR, funkcja ER</a>

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
