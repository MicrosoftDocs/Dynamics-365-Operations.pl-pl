---
title: ISOCREDREF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISOCREDREF w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 51adc6392b07ba4061a475f3072fb35452f15ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748324"
---
# <a name="isocredref-er-function"></a>ISOCREDREF, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ISOCREDREF` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela w formacie Międzynarodowej Organizacji Normalizacyjnej (ISO) w oparciu o cyfry i znaki alfabetyczne określonego numeru faktury.

## <a name="syntax"></a>Składnia

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argumenty

`invoice number digits`: *Ciąg*

Wartość tekstowa reprezentująca cyfry numeru faktury.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

> [!NOTE] 
> Aby wyeliminować symbole z alfabetów niezgodnych z systemem ISO, argument `invoice number digits` musi zostać przetłumaczony przed przekazaniem go do tej funkcji.

## <a name="example"></a>Przykład

Funkcja `ISOCredRef ("VEND-200002")` zwraca wartość **"RF23VEND-200002"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]