---
title: TRIM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TRIM w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: 816f6d6623bb778c9186d294c9b67db7edddd671
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/01/2022
ms.locfileid: "8367799"
---
# <a name="trim-er-function"></a>TRIM, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `TRIM` zwraca określony ciąg tekstowy jako wartość *Ciąg* po zastąpieniu znaków tabulacji, powrotu karetki, wysuwu wiersza i wysuwu formularza pojedynczym znakiem spacji, po obcięciu spacji wiodących i końcowych oraz po wielu spacjach między słowa zostały usunięte.

## <a name="syntax"></a>Składnia

```vb
TRIM (text)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

W niektórych przypadkach możesz chcieć obciąć początkowe i końcowe spacje, ale wolisz zachować formatowanie dla określonego tekstu. Na przykład, gdy ten tekst reprezentuje adres, który można wprowadzić w wielowierszowym polu tekstowym i może zawierać znak nowego wiersza i formatowanie powrotu karetki. W takim przypadku użyj następującego wyrażenia: `REPLACE(text,"^[ \t]+|[ \t]+$","", true)` gdzie `text` jest argumentem odnoszącym się do określonego Ciąg tekstowy.

## <a name="example-1"></a>Przykład 1

Funkcja `TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` zwraca **"Sample text"**.

## <a name="example-2"></a>Przykład 2

`TRIM (CONCATENATE (CHAR(10), "`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(9),"`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(13)))` zwraca "**Sample text"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)

[Funkcja ER REPLACE](er-functions-text-replace.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
