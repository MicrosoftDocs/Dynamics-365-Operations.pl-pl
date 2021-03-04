---
title: IF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji IF w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: b8733022b44f3460e34a610140fd6d584ab990c2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687009"
---
# <a name="if-er-function"></a>IF, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `IF` zwraca pierwszą określoną wartość, jeśli jest spełniony podany warunek. W przeciwnym razie zwraca ona drugą określoną wartość. Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych.

## <a name="syntax"></a>Składnia

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a>Argumenty

`condition`: *Wartość logiczna*

Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane.

`first value`: *Dowolny z obsługiwanych typów danych*

Wynik, który jest zwracany, jeśli warunek zostanie spełniony.

`second value`: *Dowolny z obsługiwanych typów danych*

Wynik, który jest zwracany, jeśli warunek nie zostanie spełniony.

## <a name="return-values"></a>Wartości zwracane

*Dowolny z obsługiwanych typów danych*

Wynikowa wartość dowolnego z obsługiwanych typów danych.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Argumenty `first value` i `second value` muszą być określone przy użyciu tego samego typu danych. Wyjątek jest zgłaszany w czasie projektowania, jeśli typy danych skonfigurowanych wartości nie są zgodne.

Jeśli pierwsza wartość wyniku i druga wartość wyniku są wartościami o typie danych *Kontener (rekord)* lub *Lista rekordów*, wynik ma tylko pola, które istnieją w obu wartościach.

## <a name="example"></a>Przykład

Funkcja `IF (1=2, "condition is met", "condition is not met")` zwraca ciąg **"condition is not met"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje logiczne](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]