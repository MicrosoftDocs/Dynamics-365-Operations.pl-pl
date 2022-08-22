---
title: NUMBERVALUE, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji NUMBERVALUE w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2e39cf59cabd44583e78ff2c35a7ae4d6edbd7ee
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282600"
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
