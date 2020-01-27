---
title: NULLDATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NULLDATE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 7761342c6759c11591e06fc7c32f0ddd8bef407a
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916322"
---
# <a name="NULLDATE">NULLDATE, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `NULLDATE` zwraca wartość *Data*, która reprezentuje datę **null** (1 stycznia 1900).

## <a name="syntax"></a>Składnia

```
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
