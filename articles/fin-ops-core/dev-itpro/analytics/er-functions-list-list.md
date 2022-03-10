---
title: LIST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LIST w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: ac8d3971a5502ce567069e0c97247d75a25ae3d38e2cd91e875d4c0d2681d01d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747328"
---
# <a name="list-er-function"></a>LIST, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `LIST` zwraca wartość typu *Lista rekordów*, która składa się z nowej listy rekordów utworzonej na podstawie określonych argumentów.

## <a name="syntax"></a>Składnia

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a>Argumenty

`record 1`: *Kontener (rekord)*

Odwołanie do źródła danych o typie danych *Rekord*. Ten argument jest wymagany.

`record N`: *Kontener (rekord)*

Odwołanie do źródła danych o typie danych *Rekord*. Te dodatkowe argumenty są opcjonalne.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Tworzona struktura listy zawiera tylko pola, które są prezentowane w strukturze każdego rekordu, wymienionego w argumentach.

## <a name="example"></a>Przykład

Wprowadź źródło danych **Rekord 1** typu *Kontener*. To źródło danych zawiera następujące pola zagnieżdżone typu *Pole obliczeniowe*:

- **Code:** to pole zawiera wyrażenie, które zwraca wartość typu *Ciąg*.
- **Amount:** to pole zawiera wyrażenie, które zwraca wartość typu *Liczba rzeczywista*.

Następnie wprowadź źródło danych **Rekord 2** typu *Kontener*. To źródło danych zawiera następujące pola zagnieżdżone typu *Pole obliczeniowe*:

- **Amount:** to pole zawiera wyrażenie, które zwraca wartość typu *Liczba rzeczywista*.
- **IsValid:** to pole zawiera wyrażenie, które zwraca wartość *logiczną*.

W takim przypadku wyrażenie `LIST('Record 1', 'Record 2')` zwraca nową listę zawierającą dwa rekordy. Struktura tej listy składa się z pojedynczego pola **Ilość** typu *Liczba rzeczywista*, ponieważ jest ono jedynym polem, które jest prezentowane w każdym argumencie wywołanej funkcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]