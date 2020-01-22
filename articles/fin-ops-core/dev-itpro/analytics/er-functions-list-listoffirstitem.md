---
title: LISTOFFIRSTITEM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LISTOFFIRSTITEM w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 4d985ef5015bc104a83260b64418821cc715e8cb
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917265"
---
# <a name="LISTOFFIRSTITEM">LISTOFFIRSTITEM, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `LISTOFFIRSTITEM` zwraca wartość typu *Lista rekordów*, która składa się tylko z pierwszego rekordu określonej listy.

## <a name="syntax"></a>Składnia

```
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
