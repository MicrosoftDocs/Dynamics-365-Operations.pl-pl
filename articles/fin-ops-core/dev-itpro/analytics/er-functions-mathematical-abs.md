---
title: ABS, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji ABS w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 90fbff223be5c195feb66b9ea72ee0688e60697b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886886"
---
# <a name="abs-er-function"></a>ABS, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ABS` zwraca wartość bezwzględną (moduł) określonej liczby jako wartość *rzeczywistą*. Innymi słowy zwraca liczbę bez znaku.

## <a name="syntax"></a>Składnia

```vb
ABS (number)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba rzeczywista*

Wartość liczbowa, dla której chcesz obliczyć moduł.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="example"></a>Przykład

Funkcja `ABS (-1)` zwraca wartość **1**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje matematyczne](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]