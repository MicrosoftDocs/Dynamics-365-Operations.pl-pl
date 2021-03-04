---
title: CH_BANK_MOD_10, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CH_BANK_MOD_10 w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: bca82cd596ba1e3ec42b3dba91ee6c4871ff8601
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686865"
---
# <a name="ch_bank_mod_10-er-function"></a>CH_BANK_MOD_10, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `CH_BANK_MOD_10` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela jako wyrażenie MOD10, na podstawie cyfr określonego numeru faktury.

## <a name="syntax"></a>Składnia

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a>Argumenty

`invoice number digits`: *Ciąg*

Wartość tekstowa reprezentująca cyfry numeru faktury.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `CH_BANK_MOD_10 ("VEND-200002")` zwraca wartość **3**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]