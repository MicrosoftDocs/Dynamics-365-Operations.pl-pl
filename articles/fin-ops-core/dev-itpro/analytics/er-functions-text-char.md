---
title: CHAR, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CHAR w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: f83dfe19e442b9e81d63a2b1dd3dd44aa2f594bc
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891190"
---
# <a name="char-er-function"></a>CHAR, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `CHAR` zwraca wartość typu *Ciąg*, która przedstawia pojedynczy znak, do którego odwołuje się określony numer Unicode.

## <a name="syntax"></a>Składnia

```vb
CHAR (number)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba całkowita*

Liczba odpowiadająca oczekiwanemu pojedynczemu znakowi.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ciąg zwrócony przez funkcję zależy od kodowania wybranego w nadrzędnym elemencie formatu **PLIK**. Lista obsługiwanych kodowań znajduje się w temacie [Klasa Encoding](/dotnet/api/system.text.encoding).

## <a name="example"></a>Przykład

Funkcja `CHAR (255)` zwraca **"ÿ"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]