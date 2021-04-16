---
title: PADLEFT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji PADLEFT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 806b1d318f18b0ade01f7b03909c90b1e4fd29b1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746250"
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