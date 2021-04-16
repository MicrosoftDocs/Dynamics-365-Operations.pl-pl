---
title: ALLITEMS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ALLITEMS w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 5ddcf989bdfd1d1f5d0a412a2ffefe0e3037ca79
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746730"
---
# <a name="allitems-er-function"></a>ALLITEMS, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ALLITEMS` jest uruchamiana jako wybór w pamięci i zwraca nową spłaszczoną wartość *Lista rekordów* jako listę rekordów, który reprezentuje wszystkie elementy, które odpowiadają określonej ścieżce.

## <a name="syntax"></a>Składnia

```vb
ALLITEMS (path)
```

## <a name="arguments"></a>Argumenty

`path`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ścieżka musi być zdefiniowana jako prawidłowa ścieżka źródła danych do elementu źródła danych o typie danych *Lista rekordów*. Elementy danych, takie jak ciąg i data ścieżki, powinny powodować zgłaszanie błędu w konstruktorze wyrażeń modułu Raportowanie elektroniczne (ER) w czasie projektowania.

Nie zaleca się używania tej funkcji dla źródeł danych transakcyjnych, które mogą zawierać dużą ilość danych. Zamiast tego należy rozważyć użycie funkcji [ALLTEMSQUERY](er-functions-list-allitemsquery.md).

## <a name="example-1"></a>Przykład 1

Jeśli wprowadzisz `SPLIT("abcdef" , 2)` jako źródło danych **DS**, wyrażenie `COUNT( ALLITEMS (DS))` zwraca wartość **3**.

## <a name="example-2"></a>Przykład 2

Jeśli wprowadzisz **Vend** jako źródło danych z typem danych *Lista rekordów*, które odwołuje się do tabeli aplikacji VendTable, wyrażenie `ALLITEMS (Vend.'<Relations'.ContactPerson)` zwraca spłaszczoną listę rekordów, które ma strukturę tabeli **ContactPerson** i zawiera wszystkie osoby kontaktowe dostępne za pośrednictwem relacji **ContactPerson.ContactForParty == VendTable.Party**. Lista ta jest dostępna dla wszystkich dostawców z poziomu przywołanej tablicy dostawców.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]