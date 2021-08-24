---
title: EMPTYLIST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji EMPTYLIST w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: fe2c72eddbb7f9227691ba29b19743c03aedfeb0d841e1a2466a159fa3afdf56
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734799"
---
# <a name="emptylist-er-function"></a>EMPTYLIST, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `EMPTYLIST` zwraca pustą wartość typu *Lista rekordów* przez użycie określonej listy jako źródła dla struktury listy.

## <a name="syntax"></a>Składnia

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="example"></a>Przykład

Funkcja `EMPTYLIST (SPLIT ("abc", 1))` zwraca nową pustą listę, która ma taką samą strukturę jak lista zwracana przez używaną funkcję `SPLIT`.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]