---
title: MOD_97, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji MOD_97 w module Raportowanie elektroniczne (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2e4e40fbd953b31225ccc0f54912b26933ccc48
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680645"
---
# <a name="mod_97-er-function"></a>MOD_97, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `MOD_97` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela jako wyrażenie MOD97, na podstawie cyfr określonego numeru faktury.

## <a name="syntax"></a>Składnia

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a>Argumenty

`invoice number digits`: *Ciąg*

Wartość tekstowa reprezentująca cyfry numeru faktury.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `MOD_97 ("VEND-200002")` zwraca wartość **"20000285"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)
