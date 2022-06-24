---
title: NULLDATETIME, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji NULLDATETIME w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 3e8447d4f05ee8394842b9b07d14d1c054834bb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867680"
---
# <a name="nulldatetime-er-function"></a>NULLDATETIME, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NULLDATETIME` zwraca wartość *Data/godzina*, która reprezentuje wartość **null** daty/godziny (1 stycznia 1900) w uniwersalnym czasie koordynowanym (Czas uniwersalny Greenwich \[GMT\]).

## <a name="syntax"></a>Składnia

```vb
NULLDATETIME ()
```

## <a name="return-values"></a>Wartości zwracane

*Data/godzina*

Wyjściowa wartość daty/godziny.

## <a name="example"></a>Przykład

Funkcja `DATETIMEFORMAT( NULLDATETIME(), "O")` zwraca wartość ciągu **1900-01-01T00:00:00.0000000+00:00**, gdy jest wywoływana podczas procesu, który został zainicjowany przez użytkownika aplikacji z wartością strefy czasowej **(GMT) Uniwersalny czas koordynowany** w sekcji **Preferencje dotyczące języka i kraju/regionu**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]