---
title: REVERSE, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji REVERSE w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 360878319bfa29395ae5deabec2e25e52d9e0fdc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284157"
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
