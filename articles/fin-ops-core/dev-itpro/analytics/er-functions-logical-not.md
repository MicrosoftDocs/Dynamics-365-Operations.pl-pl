---
title: NOT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NOT w module Raportowanie elektroniczne (ER).
author: NickSelin
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
ms.openlocfilehash: 7c10ed61b97dcd4d4a66a530bb3d08c539659233
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751730"
---
# <a name="not-er-function"></a>NOT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NOT` zwraca odwróconą wartość logiczną określonego warunku jako wartość *logiczną*.

## <a name="syntax"></a>Składnia

```vb
NOT (condition)
```

## <a name="arguments"></a>Argumenty

`condition`: *Wartość logiczna*

Prawidłowe wyrażenie warunkowe, które musi zostać odwrócone.

## <a name="return-values"></a>Wartości zwracane

*Wartość logiczna*

Wyjściowa *wartość logiczna*.

## <a name="example"></a>Przykład

Funkcja `NOT (TRUE)` zwraca wartość **FALSE**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje logiczne](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]