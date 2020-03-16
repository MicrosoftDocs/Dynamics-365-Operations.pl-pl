---
title: VALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji VALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: c90772ca1e93500ac45cc52ba92d4169c4d29bad
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042626"
---
# <a name="VALUE">VALUE, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `VALUE` zwraca wartość *rzeczywistą*, która jest konwertowana z określonego ciągu.

## <a name="syntax"></a>Składnia

```vb
VALUE (text)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość ciągu, która musi zostać przekonwertowana na wartość numeryczną.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Przecinki i kropki (.) są traktowane jako separatory dziesiętne, a wiodący łącznik (-) jako znak minusa. W czasie wykonywania wyjątek jest zgłaszany, jeśli podany ciąg zawiera inne znaki nieliczbowe.

## <a name="example-1"></a>Przykład 1

Funkcja `VALUE ("1 234,56")` zgłasza wyjątek.

## <a name="example-2"></a>Przykład 2

Funkcja `VALUE ("1234,56")` zwraca wartość **1234,56**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje konwersji typu](er-functions-category-type-conversion.md)
