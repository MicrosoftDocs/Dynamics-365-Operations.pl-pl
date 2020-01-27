---
title: ROUNDDOWN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUNDDOWN w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: ef7d81852a0bbb84fd8f37cd89555766cc47f5f8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915862"
---
# <a name="ROUNDDOWN">ROUNDDOWN, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `ROUNDDOWN` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej w dół do określonej liczby miejsc dziesiętnych.

## <a name="syntax"></a>Składnia

```
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba rzeczywista*

Wartość numeryczna do zaokrąglenia w dół.

`decimals`: *Liczba całkowita*

Wartość numeryczna, która reprezentuje liczbę miejsc dziesiętnych.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ta funkcja zachowuje się jak funkcja [ROUND](er-functions-mathematical-round.md), ale zawsze zaokrągla podaną liczbę do dołu (w stronę zera).

## <a name="example-1"></a>Przykład 1

Funkcja `ROUNDDOWN (1200.767, 2)` zaokrągla w dół do dwóch miejsc po przecinku i zwraca wartość **1200.76**. 

## <a name="example-2"></a>Przykład 2

Funkcja `ROUNDDOWN (1700.767, -3)` zaokrągla w dół do najbliższej wielokrotności 1000 i zwraca wartość **1000**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje matematyczne](er-functions-category-mathematical.md)
