---
title: AND, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji AND w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: dd9c0ed0238009f70ad7a9bf5a5e19ebfb95cccc
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917173"
---
# <a name="AND">AND, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `AND` zwraca wartość *logiczną* **TRUE**, jeśli wszystkie wybrane warunki zostaną spełnione. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.

## <a name="syntax"></a>Składnia

```
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argumenty

`condition 1`: *Wartość logiczna*

Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane. Ten argument jest wymagany.

`condition N`: *Wartość logiczna*

Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane. Te dodatkowe argumenty są opcjonalne.

## <a name="return-values"></a>Wartości zwracane

*Wartość logiczna*

Wyjściowa *wartość logiczna*.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

W argumentach funkcji logicznych można używać odwołań do źródeł danych, wartości liczbowych i tekstowych, wartości logicznych, operatorów porównania i innych funkcji raportowania elektronicznego (ER). Jednak wartość wszystkich argumentów musi być obliczana jako wartość *logiczna* **TRUE** lub **FALSE**.

## <a name="example"></a>Przykład

Funkcja `AND (1=1, "a"="a")` zwraca wartość **TRUE**.

Funkcja `AND (1=2, "a"="a")` zwraca wartość **FALSE**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje logiczne](er-functions-category-logical.md)
