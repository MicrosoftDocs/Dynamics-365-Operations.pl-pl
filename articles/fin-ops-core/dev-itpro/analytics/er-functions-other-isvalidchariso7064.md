---
title: ISVALIDCHARACTERISO7064, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISVALIDCHARACTERISO7064 w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 6f6f3326c9ca5cdcb3cef52f243d6d3da34251ce
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915931"
---
# <a name="ISVALIDCHARACTERISO7064">ISVALIDCHARACTERISO7064, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `ISVALIDCHARACTERISO7064` zwraca wartość *logiczną* **TRUE**, jeśli podany ciąg tekstowy reprezentuje prawidłowy międzynarodowy numer konta bankowego (IBAN). W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.

## <a name="syntax"></a>Składnia

```
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość tekstowa, która reprezentuje numer IBAN.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` zwraca wartość **TRUE**. 

Funkcja `ISVALIDCHARACTERISO7064 ("AT61")` zwraca wartość **FALSE**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)
