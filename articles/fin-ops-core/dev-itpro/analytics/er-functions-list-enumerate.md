---
title: ENUMERATE, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji ENUMERATE w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 2ba0ab6ed3c1625904665d87f56745d9810ac782
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891851"
---
# <a name="enumerate-er-function"></a>ENUMERATE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ENUMERATE` zwraca nową wartość typu *Lista rekordów*, która składa się z wyliczonych rekordów określonej listy.

## <a name="syntax"></a>Składnia

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Zwracana lista wyliczonych rekordów zawiera następujące elementy dodatkowe:

- Rekord pól (składnik **Wartość**)
- Indeks bieżącego rekordu (składnik **Number**)

## <a name="example"></a>Przykład

Na poniższej ilustracji źródło danych **Enumerated** jest tworzone jako stałotekstowa lista rekordów dostawców ze źródła danych **Vendors**, które odwołuje się do tabeli VendTable.

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

Na poniższej ilustracji przedstawiono format raportowania elektronicznego (ER). W tym formacie są tworzone powiązania danych w celu wygenerowania danych wyjściowych w formacie XML Te dane wyjściowe prezentują poszczególnych dostawców jako stałotekstowe węzły.

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]