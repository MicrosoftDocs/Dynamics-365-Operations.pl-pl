---
title: NULLDATE, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji NULLDATE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 7d1f0535796da096253dbd3ed55e9407cc9150f4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870414"
---
# <a name="nulldate-er-function"></a>NULLDATE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NULLDATE` zwraca wartość *Data*, która reprezentuje datę **null** (1 stycznia 1900).

## <a name="syntax"></a>Składnia

```vb
NULLDATE () as 
```

## <a name="return-values"></a>Wartości zwracane

*Data*

Wyjściowa wartość daty.

## <a name="example-1"></a>Przykład 1

Funkcja `DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` zwraca wartość daty **null**, 1 stycznia 1900, jako **„1900-01-01”**, na podstawie określonego formatu niestandardowego.

## <a name="example-2"></a>Przykład 2

Wyrażenie `IF( Invoice.DocumentDate = NULLDATE(), true, false)` zwraca wartość **True**, gdy wartość pola **DocumentDate** jest równa dacie **null**. W tym przykładzie **Invoice** jest źródłem danych raportowania elektronicznego (ER) typu **Finance/Tabela — rekordy** i odwołuje się do tabeli CustInvoiceJour.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]