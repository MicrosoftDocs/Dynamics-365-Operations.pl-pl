---
title: ROUND, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUND w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 6751c1321fc71419fa8b153145a057371e0f7af5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041614"
---
# <a name="ROUND">ROUND, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `ROUND` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej do określonej liczby miejsc dziesiętnych.

## <a name="syntax"></a>Składnia

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba rzeczywista*

Wartość numeryczna do zaokrąglenia.

`decimals`: *Liczba całkowita*

Wartość numeryczna, która reprezentuje liczbę miejsc dziesiętnych.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Jeśli wartość argumentu `decimals` jest większa niż 0 (zero), podana liczba jest zaokrąglana do tej liczby miejsc po przecinku.

Jeśli wartość argumentu `decimals` wynosi **0** (zero), podana liczba jest zaokrąglana do najbliższej liczby całkowitej.

Jeśli wartość argumentu `decimals` jest mniejsza niż 0 (zero), podana liczba jest zaokrąglana do liczby na lewo od separatora dziesiętnego.

## <a name="example-1"></a>Przykład 1

Funkcja `ROUND (1200.767, 2)` zaokrągla do dwóch miejsc po przecinku i zwraca wartość **1200.77**.

## <a name="example-2"></a>Przykład 2

Funkcja `ROUND (1200.767, -3)` zaokrągla do najbliższej wielokrotności 1000 i zwraca wartość **1000**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje matematyczne](er-functions-category-mathematical.md)
