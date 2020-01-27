---
title: PADLEFT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji PADLEFT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 28306b2e5fb1febce49ab55240c6d84ff240282a
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916782"
---
# <a name="PADLEFT">PADLEFT, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `PADLEFT` zwracanie wartość typu *Ciąg* o określonej długości, w którym początek ciągu jest dopełniany określonymi znakami.

## <a name="syntax"></a>Składnia

```
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Wartość *ciągu* reprezentująca oryginalny tekst.

`length`: *Liczba całkowita*

Wartość *całkowita*, która reprezentuje ostatnią liczbę znaków w dopełnianym ciągu.

`padding chars`: *Ciąg*

Znaki używane do dopełnienia.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Funkcja `PADLEFT ("1234", 10, "`&nbsp;`")` zwraca ciąg tekstowy **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)
