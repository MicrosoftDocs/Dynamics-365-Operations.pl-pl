---
title: EMPTYRECORD, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji EMPTYRECORD w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 2d3c34cbff8551b84121201b9489250c07c7799e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563253"
---
# <a name="emptyrecord-er-function"></a>EMPTYRECORD, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `EMPTYRECORD` zwraca pustą wartość *Kontener (rekord)*, która ma tę samą strukturę, co wybrana lista rekordów lub rekord.

## <a name="syntax"></a>Składnia

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów* lub *Kontener (rekord)*

Prawidłowa ścieżka elementu źródła danych typu *Lista rekordów* lub *Kontener (rekord)*.

## <a name="return-values"></a>Wartości zwracane

*Kontener (rekord)*

Wynik wartości rekordu.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

> [!NOTE] 
> Rekord null jest rekordem, w którym wszystkie pola mają wartość pustą. Wartość pusta to **0** (zero) w przypadku liczb, pusty ciąg w przypadku ciągów tekstowych, itd.

## <a name="example"></a>Przykład

Funkcja `EMPTYRECORD (SPLIT ("abc", 1))` zwraca nowy pusty rekord, która ma taką samą strukturę jak lista zwracana przez używaną funkcję `SPLIT`. Aby uzyskać więcej informacji, zobacz [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje zapisu](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]