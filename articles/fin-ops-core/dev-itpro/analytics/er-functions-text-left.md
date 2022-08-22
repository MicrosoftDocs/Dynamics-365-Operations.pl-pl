---
title: LEFT, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji LEFT w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 866c1b59fee9aa58afafbd82a83cff57e4cadeeb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268005"
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
