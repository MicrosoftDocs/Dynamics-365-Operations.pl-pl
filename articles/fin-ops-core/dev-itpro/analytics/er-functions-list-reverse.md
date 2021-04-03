---
title: REVERSE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji REVERSE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: f76582bc8b752fe0322bee8917d8649ed1c024ba
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567373"
---
# <a name="reverse-er-function"></a>REVERSE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `REVERSE` zwraca określoną listę jako wartość *Lista rekordów* w odwróconej kolejności sortowania.

## <a name="syntax"></a>Składnia

```vb
REVERSE (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="example-1"></a>Przykład 1

Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("C|B|A", "|")`, wyrażenie `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` zwraca wartość tekstową **„C”**.

## <a name="example-2"></a>Przykład 2

Jeśli opcja **Vendor** jest skonfigurowana jako źródło danych raportowania elektronicznego odwołujące się do tabeli VendTable, wyrażenie `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` zwraca listę dostawców posortowaną według nazw w porządku malejącym.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]