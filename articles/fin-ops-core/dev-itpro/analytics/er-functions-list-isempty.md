---
title: ISEMPTY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISEMPTY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 9c33e8b613bf5bf5bc17a42a7668d4cc4ee58e53
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750443"
---
# <a name="isempty-er-function"></a>ISEMPTY, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ISEMPTY` zwraca wartość *logiczną* **TRUE**, jeśli określona lista nie zawiera żadnych rekordów. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.

## <a name="syntax"></a>Składnia

```vb
ISEMPTY (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Wartość logiczna*

Wyjściowa *wartość logiczna*.

## <a name="example-1"></a>Przykład 1

Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `ISEMPTY(DS)` zwraca wartość **FALSE**.

## <a name="example-2"></a>Przykład 2

Wyrażenie `ISEMPTY (SPLIT ("",1))` zwraca wartość **TRUE**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]