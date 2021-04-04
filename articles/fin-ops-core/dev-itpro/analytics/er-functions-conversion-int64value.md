---
title: INT64VALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji INT64VALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 9db2e9abcac36a8331a494c886218bbfc82e93aa
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561501"
---
# <a name="int64value-er-function"></a>INT64VALUE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `INT64VALUE` zwraca wartość *Int64*, która reprezentuje określony ciąg.

## <a name="syntax-1"></a>Składnia 1

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a>Składnia 2

```vb
INT64VALUE (number)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość tekstowa, która musi zostać przekonwertowana na liczbę typu *Int64*.

`number`: *Liczba rzeczywista* lub *Liczba całkowita*

Liczbowa wartość *rzeczywista* lub *całkowita*, która musi zostać przekonwertowana na liczbę typu *Int64*.

## <a name="return-values"></a>Wartości zwracane

*Int64*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wszystkie miejsca dziesiętne są obcinane.

## <a name="example-1"></a>Przykład 1

Funkcja `INT64VALUE ("22565422744")` zwraca wartość *Int64* wynoszącą **22565422744**.

## <a name="example-2"></a>Przykład 2

Funkcja `INT64VALUE ( VALUE("22565422744.77"))` zwraca wartość *Int64* wynoszącą **22565422744**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje konwersji typu](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]