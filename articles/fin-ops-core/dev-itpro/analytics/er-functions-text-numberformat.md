---
title: NUMBERFORMAT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMBERFORMAT w module Raportowanie elektroniczne (ER).
author: NickSelin
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
ms.openlocfilehash: 8de57d8b0a45b8b58849a24f2d8f0cde41e0ea3a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746225"
---
# <a name="numberformat-er-function"></a>NUMBERFORMAT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NUMBERFORMAT` zwraca wartość *Ciąg*, który przedstawia określoną liczbę w określonym formacie i opcjonalnie określonej [kulturze](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). Aby uzyskać informacje na temat obsługiwanych formatów, zobacz formaty [standardowe](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) i [niestandardowe](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).

## <a name="syntax-1"></a>Składnia 1

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>Składnia 2

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba całkowita* lub *Liczba rzeczywista*

Wartość liczbowa, która określa liczbę do sformatowania.

`format`: *Ciąg*

Wartość typu *Ciąg* reprezentująca format.

`culture`: *Ciąg*

Wartość typu *Ciąg* reprezentująca kulturę do użycia podczas formatowania.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Jeśli kultura nie została zdefiniowana jako argument wywołanej funkcji, kontekst, w którym ta funkcja jest uruchamiana, określa kulturę używaną do formatowania liczb.

## <a name="example-1"></a>Przykład 1

W kulturze **EN-US** funkcja `NUMBERFORMAT (0.45, "p")` zwraca **"45.00 %"**, a funkcja `NUMBERFORMAT (10.45, "#")` zwraca **"10"**.

## <a name="example-2"></a>Przykład 2

Funkcja `NUMBERFORMAT (10/3, "F2", "de")` zwraca **3,33**, a funkcja `NUMBERFORMAT (10/3, "F2", "en-us")` zwraca **3.33**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]