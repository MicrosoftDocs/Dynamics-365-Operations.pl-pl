---
title: FIRST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FIRST w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 4d10abcf15b93961bd2ba4aec22914825d9ac38c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042097"
---
# <a name="FIRST">FIRST, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `FIRST` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ta lista nie jest pusta. Jeśli lista jest pusta, ta funkcja zgłasza wyjątek.

## <a name="syntax"></a>Składnia

```vb
FIRST (list)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

## <a name="return-values"></a>Wartości zwracane

*Kontener (rekord)*

Wynik wartości rekordu.

## <a name="example-1"></a>Przykład 1

Wyrażenie `FIRST(SPLIT("ABC",1)).Value` zwraca wartość tekstową **"A"**.

## <a name="example-2"></a>Przykład 2

Wyrażenie `FIRST(SPLIT("",1)).Value` zgłasza wyjątek w czasie wykonywania.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
