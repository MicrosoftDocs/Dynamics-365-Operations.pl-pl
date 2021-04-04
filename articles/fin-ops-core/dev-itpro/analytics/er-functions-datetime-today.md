---
title: TODAY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TODAY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 9288baf4e6123a7c03152f524a852eae9b671dde
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567923"
---
# <a name="today-er-function"></a>TODAY, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `TODAY` zwraca wartość *Data*, która reprezentuje bieżącą datę serwera aplikacji.

## <a name="syntax"></a>Składnia

```xpp
TODAY ()
```

## <a name="return-values"></a>Wartości zwracane

*Data*

Wyjściowa wartość daty.

## <a name="example"></a>Przykład

Funkcja `DATEFORMAT (TODAY (), "dd-MM-yyyy")` zwraca datę bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako ciąg **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]