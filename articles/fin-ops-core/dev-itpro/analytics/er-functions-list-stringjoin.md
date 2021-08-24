---
title: STRINGJOIN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji STRINGJOIN w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 651cc261e6a33b1a824feb94afa767e439196e249bb13b0fc4886dc72bfdd184
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776105"
---
# <a name="stringjoin-er-function"></a>STRINGJOIN, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `STRINGJOIN` zwraca wartość typu *Ciąg* zawierającą połączone wartości z określonego pola na wybranej liście. Wartości mogą być rozdzielone wybranym separatorem.

## <a name="syntax"></a>Składnia

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`field`: *Pole*

Prawidłowa ścieżka pola typu *Ciąg* na określonej liście.

`delimiter`: *Ciąg*

Ogranicznik, który jest używany do dzielenia podciągów.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Jeśli wprowadzisz `SPLIT("abc" , 1)` jako źródło danych **DS**, wyrażenie `STRINGJOIN (DS, DS.Value, "-")` zwraca wartość **"a-b-c"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]