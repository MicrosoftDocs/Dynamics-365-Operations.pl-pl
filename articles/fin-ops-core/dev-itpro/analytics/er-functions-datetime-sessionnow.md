---
title: SESSIONNOW, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SESSIONNOW w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4dff6daa8fbd60ef1fc84d783e428d69477aac6d
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916276"
---
# <a name="">SESSIONNOW, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `SESSIONNOW` zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę sesji aplikacji.

## <a name="syntax"></a>Składnia

```
SESSIONNOW ()
```

## <a name="return-values"></a>Wartości zwracane

*Data/godzina*

Wyjściowa wartość daty/godziny.

## <a name="example"></a>Przykład

Funkcja `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` zwraca bieżącą datę/godzinę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24.12.2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)
