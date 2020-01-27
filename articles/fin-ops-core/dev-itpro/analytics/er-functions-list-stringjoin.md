---
title: STRINGJOIN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji STRINGJOIN w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 99d50313f8097d43b820ffc1c36eef0097e7ec55
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917196"
---
# <a name="STRINGJOIN">STRINGJOIN, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `STRINGJOIN` zwraca wartość typu *Ciąg* zawierającą połączone wartości z określonego pola na wybranej liście. Wartości mogą być rozdzielone wybranym separatorem.

## <a name="syntax"></a>Składnia

```
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
