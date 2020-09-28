---
title: ORDERBY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ORDERBY w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ff280d66fd2c418984f2d7fd31a32609932e89c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745016"
---
# <a name="orderby-er-function"></a>ORDERBY, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ORDERBY` zwraca określoną listę jako wartość typu *Lista rekordów* po jej posortowaniu zgodnie z określonymi argumentami. Te argumenty można zdefiniować jako wyrażenia.

## <a name="syntax"></a>Składnia

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`expression 1`: *Pole*

Prawidłowa ścieżka pola źródła danych, do której odwołuje się argument `list` wywoływanej funkcji. Przywoływane pole musi być polem typu danych pierwotnych. Ten argument jest wymagany.

`expression N`: *Pole*

Prawidłowa ścieżka pola źródła danych, do której odwołuje się argument `list` wywoływanej funkcji. Przywoływane pole musi być polem typu danych pierwotnych. Te dodatkowe argumenty są opcjonalne.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="example-1"></a>Przykład 1

Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("C|B|A", "|")`, wyrażenie `FIRST( ORDERBY( DS, DS. Value)).Value` zwraca wartość tekstową **"A"**.

## <a name="example-2"></a>Przykład 2

Jeśli opcja **Vendor** jest skonfigurowana jako źródło danych raportowania elektronicznego (ER) odwołujące się do tabeli VendTable, wyrażenie `ORDERBY (Vendors, Vendors.'name()')` zwraca listę dostawców posortowaną według nazw w porządku rosnącym.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
