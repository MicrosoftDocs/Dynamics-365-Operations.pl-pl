---
title: CH_BANK_MOD_10, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CH_BANK_MOD_10 w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 21942fa47b968fa10bfc9b07f269d44e495139fe
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564847"
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