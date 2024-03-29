---
title: MID, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji MID w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/10/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: c53963876db92bb07ed5ac49f009ed4f9bc5e8c4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285918"
---
# <a name="mid-er-function"></a>MID, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `MID` zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków określonego ciągu od określonego położenia.

## <a name="syntax"></a>Składnia

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość typu *Ciąg*, która określa tekst do zwracania znaków.

`starting position`: *Liczba całkowita*

Wartość typu *Liczba całkowita*, która określa położenie pierwszego znaku, który musi zostać zwrócony z określonego tekstu.

`number of characters`: *Liczba całkowita*

Wartość typu *Liczba całkowita*, która określa liczbę znaków, które muszą zostać zwrócone, rozpoczynając od określonej pozycji początkowej.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Jeśli wartość argumentu `starting position` jest mniejsza niż 0 (zero), zwracane znaki są liczone od pierwszej pozycji w określonym ciągu.

Jeśli wartość argumentu `starting position` przekracza długość określonego ciągu, zwracany jest pusty ciąg.

## <a name="example"></a>Przykład

Funkcja `MID ("Sample", 2, 3)` zwraca wartość **„amp”**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
