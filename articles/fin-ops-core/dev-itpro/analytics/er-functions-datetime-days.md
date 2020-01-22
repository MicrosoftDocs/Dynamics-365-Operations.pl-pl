---
title: DAYS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DAYS w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 4f8c12a22f7654285d5598064473bf86689ed207
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916299"
---
# <a name="DAYS">DAYS, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `DAYS` zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między dwiema określonymi datami.

## <a name="syntax"></a>Składnia

```
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>Argumenty

`date 1`: *Data*

Wartość daty, która reprezentuje datę początkową na potrzeby obliczania liczby dni.

`date 2`: *Data*

Wartość daty, która reprezentuje datę końcową na potrzeby obliczania liczby dni.

## <a name="return-values"></a>Wartości zwracane

*Wartość całkowita*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Funkcja `DAYS` zwraca wartość dodatnią, gdy pierwsza data jest późniejsza niż druga data, wartość **0** (zero), gdy pierwsza data jest równa drugiej dacie, lub wartość ujemną, gdy pierwsza data jest wcześniejsza niż druga data.

## <a name="example"></a>Przykład

Funkcja `DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` zwraca wartość **-1**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)
