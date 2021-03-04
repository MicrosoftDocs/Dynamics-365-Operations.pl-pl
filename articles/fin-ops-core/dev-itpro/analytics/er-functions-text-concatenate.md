---
title: CONCATENATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CONCATENATE w module Raportowanie elektroniczne (ER)
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 903429994ae5618b597aa0ab0991e9f6783a96ed
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687945"
---
# <a name="concatenate-er-function"></a>CONCATENATE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `CONCATENATE` zwraca wszystkie ciągi tekstowe określone jako wartość typu *Ciąg* po ich połączeniu w jeden ciąg.

## <a name="syntax"></a>Składnia

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argumenty

`text 1`: *Ciąg*

Odwołanie do źródła danych o typie danych *Ciąg*. Ten argument jest wymagany.

`text N`: *Ciąg*

Odwołanie do źródła danych o typie danych *Ciąg*. Te dodatkowe argumenty są opcjonalne.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `CONCATENATE ("abc", "def")` zwraca wartość **"abcdef"**.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wyrażenie `"abc" & "def"` również zwraca wartość **abcdef**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]