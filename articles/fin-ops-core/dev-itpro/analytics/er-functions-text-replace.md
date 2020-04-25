---
title: Funkcja ER REPLACE
description: Ten temat zawiera ogólne informacje o używaniu funkcji REPLACE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 83d5095620a938f1ac4b8428fff9209fda7a7831
ms.sourcegitcommit: fb8ad8e2b142441a6530b364f3258bbcc0c724d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201073"
---
# <a name=""></a><a name="REPLACE">Funkcja ER REPLACE</a>

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
