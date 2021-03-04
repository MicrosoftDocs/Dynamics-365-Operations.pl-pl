---
title: TABLENAME2ID, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TABLENAME2ID w module Raportowanie elektroniczne (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a68a8e1f4afa378ab446eae12bc90cdb3aba8b19
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681165"
---
# <a name="tablename2id-er-function"></a>TABLENAME2ID, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `TABLENAME2ID` zwraca numeryczną reprezentację identyfikatora tabeli dla określonej nazwy tabeli jako wartość typu *Liczba całkowita*.

## <a name="syntax"></a>Składnia

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość tekstowa, która reprezentuje prawidłową nazwę tabeli.

## <a name="return-values"></a>Wartości zwracane

*Wartość całkowita*

Wynikowa wartość numeryczna.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wykonanie tej funkcji może mieć różne wyniki w różnych wystąpieniach aplikacji Microsoft Dynamics 365 Finance, nawet jeśli jest używana ta sama nazwa firmy.

## <a name="example"></a>Przykład

Funkcja `TABLENAME2ID ("Intrastat")` zwraca wartość **1510**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]