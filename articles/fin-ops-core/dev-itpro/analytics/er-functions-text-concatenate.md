---
title: CONCATENATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CONCATENATE w module Raportowanie elektroniczne (ER)
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 04c7b32e2a9578f8864570a552817ec3ce28fa43
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041190"
---
# <a name="CONCATENATE">CONCATENATE, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `CONCATENATE` zwraca wszystkie ciągi tekstowe określone jako wartość typu *Ciąg* po ich połączeniu w jeden ciąg.

## <a name="syntax"></a>Składnia

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argumenty

`text 1`: *Ciąg*

Odwołanie do źródła danych o typie danych *Ciąg*. Ten argument jest wymagany.

`text N`: *Ciąg*

Odwołanie do źródła danych o typie danych *Ciąg*. Te dodatkowe argumenty są opcjonalne.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `CONCATENATE ("abc", "def")` zwraca wartość **"abcdef"**.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wyrażenie `"abc" & "def"` również zwraca wartość **abcdef**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)
