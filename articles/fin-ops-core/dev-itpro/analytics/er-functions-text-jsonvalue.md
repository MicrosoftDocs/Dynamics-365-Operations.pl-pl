---
title: JSONVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji JSONVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: b034755602a2f999892d2b976c80550b7a3d7f3cd179816dd7aa1edefe6a0270
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733780"
---
# <a name="jsonvalue-er-function"></a>JSONVALUE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `JSONVALUE` analizuje dane w formacie JSON (JavaScript Object Notation), do których dostęp jest uzyskiwany za pośrednictwem wskazanej ścieżki oraz wyodrębnia wartość skalarną opartą na podanym identyfikatorze. Następnie zwraca wartość skalarną wyodrębnioną jako wartość typu *Ciąg*.

## <a name="syntax"></a>Składnia

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argumenty

`input`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych typu *Ciąg*, który zawiera dane JSON.

`path`: *Ciąg*

Identyfikator wartości skalarnej danych JSON.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Źródło danych **JsonField** zawiera następujące dane w formacie JSON: **{"Numer_kompilacji":"7.3.1234.1", "KeyThumbprint":"7366E"}**. W tym przypadku wyrażenie `JSONVALUE (JsonField, "BuildNumber")` zwraca następującą wartość typu danych *String*: **"7.3.1234.1".**

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]