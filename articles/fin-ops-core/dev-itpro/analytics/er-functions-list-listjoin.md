---
title: Funkcja LISTJOIN ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LISTJOIN w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b300cef0a508f7cc37397480738091158efdead
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027922"
---
# <a name="listjoin-er-function"></a>Funkcja LISTJOIN ER

[!include [banner](../includes/banner.md)]

Funkcja `LISTJOIN` zwraca wartość typu *Lista rekordów*, która reprezentuje nową połączoną listę rekordów utworzoną na podstawie określonych argumentów.

## <a name="syntax"></a>Składnia

```vb
LISTJOIN (list 1 [, list 2, …, list N])
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

![Strona projektanta mapowania modelu ER](./media/er-functions-list-listjoin-image1.gif)

W takim przypadku wyrażenie `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` zwraca nową listę zawierającą dwa rekordy.

![Strona projektanta mapowania modelu ER z dwoma rekordami](./media/er-functions-list-listjoin-image2.gif)

Struktura tej listy składa się z pojedynczego pola **Ilość** typu `Real`, ponieważ jest ono jedynym polem, które jest prezentowane w każdym argumencie wywołanej funkcji.

![Strona projektanta mapowania modelu ER — pole ilości/liczby](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)

[Debugowanie źródeł danych dla wykonanego formatu ER w celu analizowania przekształcenia i przepływu danych](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
