---
title: ADDDAYS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ADDDAYS w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 08b9727fb34210fecff31826cc1f2b8da022156b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042465"
---
# <a name="ADDDAYS">ADDDAYS, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `ADDDAYS` oblicza wartość *Data/godzina*, która jest określoną liczbą dni przed wybraną datą rozpoczęcia lub po niej.

## <a name="syntax"></a>Składnia

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>Argumenty

`datetime`: *Data/godzina*

Wartość daty/godziny, która reprezentuje datę początkową.

`days`: *Liczba całkowita*

Liczba dni przed lub po `datetime`.

## <a name="return-values"></a>Wartości zwracane

*Data/godzina*

Wyjściowa wartość daty/godziny.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wartość dodatnia elementu `days` generuje przyszłą datę. Wartość ujemna generuje datę przeszłą.

## <a name="example-1"></a>Przykład 1

Funkcja `ADDDAYS (NOW(), 7)` zwraca datę i godzinę siedem dni w przyszłości.

## <a name="example-2"></a>Przykład 2

Funkcja `ADDDAYS (NOW(), -3)` zwraca datę i godzinę trzy dni w przeszłości.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje daty i godziny](er-functions-category-datetime.md)
