---
title: EMPTYLIST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji EMPTYLIST w module Raportowanie elektroniczne (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fb991eb9ee08aeb418313eb782dbde7fa22b763
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042189"
---
# <a name="EMPTYLIST">EMPTYLIST, funkcja ER</a>

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
