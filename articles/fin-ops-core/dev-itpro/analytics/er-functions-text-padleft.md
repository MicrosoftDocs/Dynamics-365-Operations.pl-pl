---
title: PADLEFT, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji PADLEFT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 551b508bc6a17b1c6a08e25d5db0094713d9634f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892574"
---
# <a name="padleft-er-function"></a>PADLEFT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `PADLEFT` zwracanie wartość typu *Ciąg* o określonej długości, w którym początek ciągu jest dopełniany określonymi znakami.

## <a name="syntax"></a>Składnia

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość *ciągu* reprezentująca oryginalny tekst.

`length`: *Liczba całkowita*

Wartość *całkowita*, która reprezentuje ostatnią liczbę znaków w dopełnianym ciągu.

`padding chars`: *Ciąg*

Znaki używane do dopełnienia.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `PADLEFT ("1234", 10, "`&nbsp;`")` zwraca ciąg tekstowy **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]