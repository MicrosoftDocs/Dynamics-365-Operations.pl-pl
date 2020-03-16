---
title: FIRSTORNULL, funkcja ER
description: Ten temat zawiera objaśnienie sposobu używania funkcji FIRSTORNULL w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 86c8a0ae21ffeb6268efbbd198f7c709c2ad54f6
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042120"
---
# <a name="FIRSTORNULL">FIRSTORNULL, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `FIRSTORNULL` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ten rekord nie jest pusty. Jeśli rekord jest pusty, ta funkcja zwraca wartość null typu *Kontener (rekord)*.

## <a name="syntax"></a>Składnia

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Kontener (rekord)*

Wynik wartości rekordu.

## <a name="example"></a>Przykład

Wyrażenie `FIRSTORNULL(SPLIT("",1)).Value` zwraca pusty ciąg (**""**).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
