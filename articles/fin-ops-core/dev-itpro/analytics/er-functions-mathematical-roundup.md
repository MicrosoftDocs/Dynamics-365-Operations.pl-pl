---
title: ROUNDUP, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUNDUP w module Raportowanie elektroniczne (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ed86e2a848248dd8f2fc99401d12e0a162bf20a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686841"
---
# <a name="roundup-er-function"></a>ROUNDUP, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ROUNDUP` zwraca podaną liczbę jako wartość *rzeczywistą* po zaokrągleniu jej w górę do określonej liczby miejsc dziesiętnych.

## <a name="syntax"></a>Składnia

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba rzeczywista*

Wartość numeryczna do zaokrąglenia w górę.

`decimals`: *Liczba całkowita*

Wartość numeryczna, która reprezentuje liczbę miejsc dziesiętnych.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ta funkcja zachowuje się jak funkcja [ROUND](er-functions-mathematical-round.md), ale zawsze zaokrągla podaną liczbę do góry (od zera).

## <a name="example-1"></a>Przykład 1

Funkcja `ROUNDUP (1200.763, 2)` zaokrągla w górę do dwóch miejsc po przecinku i zwraca wartość **1200.77**.

## <a name="example-2"></a>Przykład 2

Funkcja `ROUNDUP (1200.767, -3)` zaokrągla w górę do najbliższej wielokrotności 1,000 i zwraca wartość **2000**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje matematyczne](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]