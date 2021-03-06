---
title: COUNT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji COUNT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: a0b780051684ef52d06a9baf78d9b513d9ac1f0e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746634"
---
# <a name="count-er-function"></a>COUNT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `COUNT` zwraca wartość typu *Liczba całkowita* reprezentującą liczbę rekordów na określonej liście, jeśli lista nie jest pusta. Jeśli lista jest pusta, ta funkcja zwraca wartość **0** (zero).

## <a name="syntax"></a>Składnia

```vb
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]