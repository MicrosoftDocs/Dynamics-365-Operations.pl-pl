---
title: LEFT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LEFT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 9e9cdff9bb5c22c74803cf17c056c0ff1af5ef43
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685890"
---
# <a name="left-er-function"></a>LEFT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `LEFT` zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków od początku określonego ciągu.

## <a name="syntax"></a>Składnia

```vb
LEFT (text, number)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość *ciągu* reprezentująca oryginalny tekst.

`number`: *Liczba całkowita*

Liczba znaków, które muszą zostać zwrócone, od początku oryginalnego tekstu.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `LEFT ("Sample", 3)` zwraca **"Sam"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]