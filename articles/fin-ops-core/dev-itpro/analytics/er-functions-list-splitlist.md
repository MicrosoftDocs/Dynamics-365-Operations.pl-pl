---
title: SPLITLIST, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji SPLITLIST w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 03/15/2021
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
ms.openlocfilehash: 30226b50f5705d5a43fa48ce5c6f92e150871b3a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845491"
---
# <a name="splitlist-er-function"></a>SPLITLIST, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `SPLITLIST` dzieli określoną listę na listy podrzędne (lub partie), z których każda zawiera określoną liczbę rekordów. Zwraca ona wynik jako nową wartość typu *Lista rekordów*, która składa się z partii.

## <a name="syntax-1"></a>Składnia 1

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a>Składnia 2

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`number`: *Liczba całkowita*

Maksymalna liczba rekordów na partię.

`on-demand reading flag`: *Wartość logiczna*

Wartość *logiczna* określająca, czy elementy podlist powinny być generowane na żądanie.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Zwracana jest lista partii zawierająca następujące elementy:

 - **Value:** *Lista*

    Lista rekordów należących do bieżącej partii.

- **BatchNumber:** *Liczba całkowita*

    Numer bieżącej partii na zwróconej liście.

Gdy flaga odczytu na żądanie ma wartość **Prawda**, podlisty są generowane na żądanie, co pozwala na zmniejszenie zużycia pamięci, ale może spowodować uszkodzenie wydajności, jeśli elementy nie są używane sekwencyjnie.

## <a name="example"></a>Przykład

Na poniższej ilustracji źródło danych **Lines** jest tworzone jako lista z trzema rekordami. Lista jest podzielona na partie, z których każdy zawiera maksymalnie dwa rekordy.

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

Na ilustracji poniżej widać zaprojektowany układ formatu. W tym układzie formatu są tworzone wiązania ze źródłem danych **Lines** w celu wygenerowania danych wyjściowych w formacie XML Te dane wyjściowe reprezentują poszczególne węzły każdej partii i zawartych w niej rekordów.

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
