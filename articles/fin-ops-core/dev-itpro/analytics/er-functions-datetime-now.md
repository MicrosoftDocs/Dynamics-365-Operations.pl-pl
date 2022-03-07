---
title: NOW, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NOW w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: cbbc3623249338c8af943974717a077f68945acfeea2b5e8c4d33c544c58734b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772015"
---
# <a name="now-er-function"></a>NOW, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NOW` zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę serwera aplikacji.

## <a name="syntax"></a>Składnia

```vb
NOW ()
```

## <a name="return-values"></a>Wartości zwracane

*Data/godzina*

Wyjściowa wartość daty/godziny.

## <a name="example"></a>Przykład

Funkcja `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` zwraca wartość daty/godziny bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]