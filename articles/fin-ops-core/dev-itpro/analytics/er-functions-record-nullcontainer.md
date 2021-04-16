---
title: NULLCONTAINER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NULLCONTAINER w module Raportowanie elektroniczne (ER).
author: NickSelin
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
ms.openlocfilehash: af6651ef3c62bd8d1285fa8179ac923d3c333ce7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746514"
---
# <a name="nullcontainer-er-function"></a>NULLCONTAINER, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NULLCONTAINER` zwraca pustą wartość *Kontener (rekord)*, która ma tę samą strukturę, co wybrana lista rekordów lub rekord.

## <a name="syntax"></a>Składnia

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów* lub *Kontener (rekord)*

Prawidłowa ścieżka elementu źródła danych typu *Lista rekordów* lub *Kontener (rekord)*.

## <a name="return-values"></a>Wartości zwracane

*Kontener (rekord)*

Wynik wartości rekordu.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

> [!NOTE] 
> Ta funkcja jest przestarzała. W zamian użyj funkcji `EMPTYRECORD`. Aby uzyskać więcej informacji, zobacz [EMPTYCORD](er-functions-record-emptyrecord.md).

## <a name="example"></a>Przykład

Funkcja `NULLCONTAINER (SPLIT ("abc", 1))` zwraca nowy pusty rekord, który ma taką samą strukturę jak lista zwracana przez używaną funkcję `SPLIT`. Aby uzyskać więcej informacji, zobacz [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje zapisu](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]