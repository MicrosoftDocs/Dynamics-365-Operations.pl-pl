---
title: Funkcja ER REPLACE
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji REPLACE w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: e7a27b5015615d9b0f26e8fcddd812b3f51fb945
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278480"
---
# <a name="replace-er-function"></a>Funkcja ER REPLACE

[!include [banner](../includes/banner.md)]

Funkcja `REPLACE` zwraca określony ciąg tekstowy jako wartość *ciągu* po zastąpieniu go w całości lub częściowo innym ciągiem.

## <a name="syntax"></a>Składnia

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.

`pattern`: *Ciąg*

Jeśli argument `regular expression flag` ma wartość **FALSE**, ten argument zawiera tekst, który musi zostać zastąpiony.

Jeśli argument `regular expression flag` ma wartość **TRUE**, ten argument zawiera wyrażenie regularne definiujące zarówno wzorzec wyszukiwania, jak i tekst zastępczy.

`replacement`: *Ciąg*

Jeśli argument `regular expression flag` ma wartość **FALSE**, ten argument zawiera tekst do użycia jako zastępczy

Jeśli argument `regular expression flag` ma wartość **TRUE**, ten argument nie jest używany.

`regular expression flag`: *Wartość logiczna*

*Wartość logiczna* wskazująca, czy wyrażenie regularne jest używane do zastępowania.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Jeśli argument `regular expression flag` ma wartość **TRUE**, ta funkcja zwraca określony ciąg po zmianie przez zastosowanie wyrażenia regularnego, które zostało określone przez argument `pattern`. Wyrażenie regularne służy do znajdowania znaków, które należy zastąpić.

Jeśli argument `regular expression flag` ma wartość **FAŁSZ**, ta funkcja zwraca określony ciąg po zestawie znaków zdefiniowanych w argumencie `pattern` , który został zastąpiony znakami argumentu `replacement`. 

## <a name="example-1"></a>Przykład 1

Funkcja `REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` stosuje wyrażenie regularne, które usuwa wszystkie symbole nieliczbowe i zwraca **"19234564971"**. 

## <a name="example-2"></a>Przykład 2

Funkcja `REPLACE ("abcdef", "cd", "GH", false)` zastępuje wzorzec **"cd"** ciągiem **"GH"** i zwraca wartość **"abGHef"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
