---
title: MID, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji MID w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: e0520bc54465f00d36e88787933b291847dee852
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562740"
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