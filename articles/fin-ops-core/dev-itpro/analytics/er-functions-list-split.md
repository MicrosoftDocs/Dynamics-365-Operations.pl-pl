---
title: SPLIT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SPLIT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 4a42b0c7cfa2a8d3dcb7448224c9e88a48276f7d8cdbcce484383a778b8275a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757328"
---
# <a name="split-er-function"></a>SPLIT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `SPLIT` dzieli określony ciąg wejściowy na podciągi i zwraca wynik jako nową wartość *Lista rekordów*.

## <a name="syntax-1"></a>Składnia 1

```vb
SPLIT (input, length)
```

Ta składnia jest używana do dzielenia podanego ciągu wejściowego na podciągi, z których każdy ma określoną długość.

## <a name="syntax-2"></a>Składnia 2

```vb
SPLIT (input, delimiter)
```

Ta składnia jest używana do dzielenia podanego ciągu wejściowego na podciągi przy użyciu podanego separatora.

## <a name="arguments"></a>Argumenty

`input`: *Ciąg*

Tekst do podzielenia.

`length`: *Liczba całkowita*

Maksymalna długość jednego podciągu.

`delimiter`: *Ciąg*

Ogranicznik, który jest używany do dzielenia podciągów.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Struktura rekordów listy, która jest zwracana, składa się z pola **Wartość** typu *Ciąg*. Każdy zwracany rekord listy zawiera wygenerowane podciągi w tym polu.

Jeśli argument `delimiter` jest pusty, zostanie zwrócona nowa lista składająca się z jednego rekordu mającego pole **Wartość** typu *Ciąg*. To pole zawiera tekst wejściowy.

Jeśli argument `input` jest pusty, zostanie zwrócona nowa pusta lista. Jeśli argument `input` lub `delimiter` jest nieokreślony (ma wartość null), aplikacja zgłasza wyjątek.

## <a name="example-1"></a>Przykład 1

Funkcja `SPLIT ("abcd", 3)` zwraca nową listę zawierającą dwa rekordy, które mają pole **Wartość** typu *Ciąg*. Pole **Wartość** w pierwszym rekordzie zawiera tekst **"abc"**, a pole **Wartość** w drugim rekordzie zawiera tekst **"d"**.

## <a name="example-2"></a>Przykład 2

Funkcja `SPLIT ("XAb aBy", "aB")` zwraca nową listę zawierającą trzy rekordy, które mają pole **Wartość** typu *Ciąg*. Pole **Wartość** w pierwszym rekordzie zawiera tekst **"X"**, pole **Wartość** w drugim rekordzie zawiera tekst **"&nbsp;"**, a pole **Wartość** w trzecim rekordzie zawiera tekst **"y"**. 

## <a name="example-3"></a>Przykład 3

Za pomocą funkcji [INDEX](er-functions-list-index.md) można uzyskać dostęp do poszczególnych elementów określonego ciągu wejściowego. Jeśli wprowadzisz źródło danych **MojaLista** typu **Pole obliczeniowe** i skonfigurujesz je na wyrażenie `SPLIT("abc", 1)`, wyrażenie `INDEX(MyList,2).Value` zwraca wartość tekstową **„b”**.

## <a name="example-4"></a>Przykład 4

Za pomocą funkcji [INDEX](er-functions-list-enumerate.md) można również uzyskać dostęp do poszczególnych elementów określonego ciągu wejściowego. Po wprowadzeniu źródła danych **MyList** dla typu **Pole obliczeniowe** i skonfigurowaniu dla niego wyrażenia `SPLIT("abc", 1)`, a następnie wprowadzeniu źródła danych **EnumeratedList** dla typu **Pole obliczeniowe** i skonfigurowaniu dla niego wyrażenia `ENUMERATE(MyList)` wyrażenie `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` zwraca tekst **„b”**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
