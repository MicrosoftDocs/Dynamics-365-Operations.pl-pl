---
title: TRIM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TRIM w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: b671ef72a3558c17fb16db939770394b225656da
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560044"
---
# <a name="trim-er-function"></a>TRIM, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `TRIM` zwraca określony ciąg tekstowy jako wartość typu *Ciąg* po obcięciu spacji wiodących i końcowych oraz usunięciu spacji wielokrotnych spomiędzy wyrazów.

## <a name="syntax"></a>Składnia

```vb
TRIM (text )
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` zwraca **"Sample text"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]