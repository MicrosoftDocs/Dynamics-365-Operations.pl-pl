---
title: Funkcja LISTJOIN ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LISTJOIN w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249042"
---
# <a name=""></a><a name="LISTJOIN">Funkcja LISTJOIN ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `LISTJOIN` zwraca wartość typu *Lista rekordów*, która reprezentuje nową połączoną listę rekordów utworzoną na podstawie określonych argumentów.

## <a name="syntax"></a>Składnia

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>Argumenty

`list 1`: *Lista rekordów*

Odwołanie do źródła danych o typie danych *Lista rekordów*. Ten argument jest obowiązkowy.

`list N`: *Lista rekordów*

Odwołanie do źródła danych o typie danych *Lista rekordów*. Te dodatkowe argumenty są opcjonalne.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Tworzona struktura listy zawiera tylko pola, które są prezentowane w strukturze każdej listy rekordów, wymienionej w argumentach.

## <a name="example"></a>Przykład

Wprowadź źródło danych **Rekord 1** typu `Container`. To źródło danych zawiera następujące pola zagnieżdżone typu `Calculated field`:

- **Kod**: to pole zawiera wyrażenie, które zwraca wartość typu `String`.
- **Ilość**: to pole zawiera wyrażenie, które zwraca wartość typu `Real`.

Wprowadź następnie źródło danych **Rekord 2** typu `Container`. To źródło danych zawiera następujące pola zagnieżdżone typu `Calculated field`:

- **Ilość**: to pole zawiera wyrażenie, które zwraca wartość typu `Real`.
- **IsValid**: to pole zawiera wyrażenie, które zwraca wartość typu `Boolean`.

W takim przypadku wyrażenie `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` zwraca nową listę zawierającą dwa rekordy. Struktura tej listy składa się z pojedynczego pola **Ilość** typu `Real`, ponieważ jest ono jedynym polem, które jest prezentowane w każdym argumencie wywołanej funkcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)