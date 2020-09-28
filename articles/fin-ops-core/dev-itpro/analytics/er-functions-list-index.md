---
title: INDEX, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji INDEX w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 051e22daa3fe2d6c328e36403201d940f724bd29
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745186"
---
# <a name="index-er-function"></a>INDEX, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `INDEX` zwraca wartość typu *Kontener (rekord)*, która jest wybierana przy użyciu określonego indeksu liczbowego na określonej liście. Jeśli indeks jest poza zakresem dla rekordów na określonej liście, zostanie zgłoszony wyjątek.

## <a name="syntax"></a>Składnia

```vb
INDEX (list, index)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`index`: *Liczba całkowita*

Indeks liczbowy, który wskazuje pozycję żądanego rekordu na określonej liście.

## <a name="return-values"></a>Wartości zwracane

*Kontener (rekord)*

Wynik wartości rekordu.

## <a name="example-1"></a>Przykład 1

Po wprowadzeniu źródła danych **DS** typu *Pole obliczeniowe* zawierającego wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `DS.Value` zwraca listę z tylko jednym rekordem, który zawiera wartość tekstową **"B"** dla drugiego rekordu n liście rekordów. Wyrażenie `INDEX (SPLIT ("A|B|C", "|"), 2).Value` również zwraca wartość tekstową **"B"**.

## <a name="example-2"></a>Przykład 2

Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `INDEX (SPLIT ("A|B|C", "|"), 4).Value` zgłasza wyjątek w czasie wykonywania.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
