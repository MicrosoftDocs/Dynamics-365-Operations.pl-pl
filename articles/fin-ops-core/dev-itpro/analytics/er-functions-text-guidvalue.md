---
title: GUIDVALUE, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji GUIDVALUE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: f3899d983f7c790ff2e3dc74dd91c44fc54e44d3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898748"
---
# <a name="guidvalue-er-function"></a>GUIDVALUE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `GUIDVALUE` przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *Identyfikator GUID*.

## <a name="syntax"></a>Składnia

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a>Argumenty

`input`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.

## <a name="return-values"></a>Wartości zwracane

*GUID*

Wynikowa wartość globalnie unikatowego identyfikatora (GUID).

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Aby wykonać przekształcenie w przeciwnym kierunku (tzn. aby przekonwertować podane dane wejściowe o typie danych *GUID* na element danych o typie danych *String*), można użyć funkcji [TEXT](er-functions-text-text.md).

## <a name="example"></a>Przykład

Definiuje się następujące źródła danych w mapowaniu modelu:

- Źródło danych **myID** typu *Pole obliczeniowe*, które zawiera wyrażenie `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`
- Źródło danych **Users** typu *Rekordy tabeli*, które odwołuje się do tabeli UserInfo

Następnie użyj wyrażenia, takiego jak `FILTER (Users, Users.objectId = myID)`, do odfiltrowania tabeli UserInfo według pola **objectid** typu danych *GUID*.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]