---
title: FIRSTORNULL, funkcja ER
description: Ten artykuł zawiera objaśnienie sposobu używania funkcji FIRSTORNULL w module Raportowanie elektroniczne (ER)
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: bae2916371cd00810f559ff2006b2b238c8ad918
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900259"
---
# <a name="firstornull-er-function"></a>FIRSTORNULL, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `FIRSTORNULL` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ten rekord nie jest pusty. Jeśli rekord jest pusty, ta funkcja zwraca wartość null typu *Kontener (rekord)*.

## <a name="syntax"></a>Składnia

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Kontener (rekord)*

Wynik wartości rekordu.

## <a name="example"></a>Przykład

Wyrażenie `FIRSTORNULL(SPLIT("",1)).Value` zwraca pusty ciąg (**""**).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]