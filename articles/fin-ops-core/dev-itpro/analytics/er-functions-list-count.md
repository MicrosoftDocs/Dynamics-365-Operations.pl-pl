---
title: COUNT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji COUNT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 2d29b82a8c3b108f7651e6d593cb17e7ec8ca872
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916253"
---
# <a name="COUNT">COUNT, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `COUNT` zwraca wartość typu *Liczba całkowita* reprezentującą liczbę rekordów na określonej liście, jeśli lista nie jest pusta. Jeśli lista jest pusta, ta funkcja zwraca wartość **0** (zero).

## <a name="syntax"></a>Składnia

```
COUNT (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Wartość całkowita*

Wynikowa wartość numeryczna.

## <a name="example"></a>Przykład

Funkcja `COUNT (SPLIT("abcd" , 3))` zwraca wartość **2**, ponieważ funkcja `SPLIT` używana w tym przykładzie tworzy listę, która składa się z dwóch rekordów.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
