---
title: INTVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji INTVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
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
ms.openlocfilehash: 71eedde5a22f36a8a827824087633de32c00cc7d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755379"
---
# <a name="intvalue-er-function"></a>INTVALUE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `INTVALUE` zwraca wartość *Int*, która reprezentuje określony ciąg.

## <a name="syntax-1"></a>Składnia 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>Składnia 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość tekstowa, która musi zostać przekonwertowana na liczbę typu *Int*.

`number`: *Liczba rzeczywista* lub *Liczba całkowita*

Liczbowa wartość *rzeczywista* lub *całkowita*, która musi zostać przekonwertowana na liczbę typu *Int*.

## <a name="return-values"></a>Wartości zwracane

*Int*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wszystkie miejsca dziesiętne są obcinane.

## <a name="example-1"></a>Przykład 1

Funkcja `INTVALUE ("100.77")` zwraca wartość *Int* wynoszącą **100**.

## <a name="example-2"></a>Przykład 2

Funkcja `INTVALUE (-100.77)` zwraca wartość *Int* wynoszącą **-100**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje konwersji typu](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]