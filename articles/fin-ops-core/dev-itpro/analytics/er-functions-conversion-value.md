---
title: VALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji VALUE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 7cdaa302e757b54858e36c3716167593383d7071
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561453"
---
# <a name="value-er-function"></a>VALUE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `VALUE` zwraca wartość *rzeczywistą*, która jest konwertowana z określonego ciągu.

## <a name="syntax"></a>Składnia

```vb
VALUE (text)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość ciągu, która musi zostać przekonwertowana na wartość numeryczną.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Przecinki i kropki (.) są traktowane jako separatory dziesiętne, a wiodący łącznik (-) jako znak minusa. W czasie wykonywania wyjątek jest zgłaszany, jeśli podany ciąg zawiera inne znaki nieliczbowe.

## <a name="example-1"></a>Przykład 1

Funkcja `VALUE ("1 234,56")` zgłasza wyjątek.

## <a name="example-2"></a>Przykład 2

Funkcja `VALUE ("1234,56")` zwraca wartość **1234,56**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje konwersji typu](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]