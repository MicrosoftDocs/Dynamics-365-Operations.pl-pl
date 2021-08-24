---
title: ISEMPTY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISEMPTY w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 41d1f773e3fc2f076dbe3d826d14a364548d6656c95c03e54eb36345c004fecd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740973"
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