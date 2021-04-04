---
title: ROUNDDOWN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUNDDOWN w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: f199d662eb31f184b6f978b3d251e64907254584
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567147"
---
# <a name="rounddown-er-function"></a>ROUNDDOWN, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ROUNDDOWN` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej w dół do określonej liczby miejsc dziesiętnych.

## <a name="syntax"></a>Składnia

```vb
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]