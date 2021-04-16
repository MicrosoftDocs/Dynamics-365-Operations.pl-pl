---
title: IF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji IF w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 3674618acae79170daf94413895d17d86a491996
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753175"
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