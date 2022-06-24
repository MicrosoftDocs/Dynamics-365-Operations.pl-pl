---
title: LISTOFFIRSTITEM, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji LISTOFFIRSTITEM w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: f4715becfb158826a2b5678aac6a58c987433192
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881167"
---
# <a name="listoffirstitem-er-function"></a>LISTOFFIRSTITEM, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `LISTOFFIRSTITEM` zwraca wartość typu *Lista rekordów*, która składa się tylko z pierwszego rekordu określonej listy.

## <a name="syntax"></a>Składnia

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="example"></a>Przykład

Wyrażenie `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` zwraca wartość tekstową **"A"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]