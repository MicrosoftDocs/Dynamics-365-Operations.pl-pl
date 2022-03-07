---
title: NUMBERVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMBERVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: bcb76310a53c86b68f18085e203d11f405b16946a25fe1be67e649f83335d1f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733804"
---
# <a name="numbervalue-er-function"></a>NUMBERVALUE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NUMBERVALUE` zwraca wartość *rzeczywistą*, która jest konwertowana z określonej wartości typu *Ciąg*. Podczas konwersji są uwzględniane wybrane separatory dziesiętne i separatory grupowania cyfr.

## <a name="syntax"></a>Składnia

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość tekstowa, która musi zostać przekonwertowana na liczbę *rzeczywistą*.

`decimal separator`: Ciąg

Separator dziesiętny. Służy do oddzielania całkowitych i ułamkowych części liczby dziesiętnej.

`digit grouping separator`: *Ciąg*

Separator grupowania cyfr. Jest używany jako separator tysięcy.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="example"></a>Przykład

Funkcja `NUMBERVALUE( "1 234,56", ",", " ")` zwraca wartość **1234,56**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje konwersji typu](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]