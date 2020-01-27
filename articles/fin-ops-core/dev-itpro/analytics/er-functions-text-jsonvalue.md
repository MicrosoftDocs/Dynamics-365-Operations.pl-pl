---
title: JSONVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji JSONVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: d8209f8ce9d244ab7c82f897e4f59283e94e0522
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915678"
---
# <a name="JSONVALUE">JSONVALUE, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `JSONVALUE` analizuje dane w formacie JSON (JavaScript Object Notation), do których dostęp jest uzyskiwany za pośrednictwem wskazanej ścieżki oraz wyodrębnia wartość skalarną opartą na podanym identyfikatorze. Następnie zwraca wartość skalarną wyodrębnioną jako wartość typu *Ciąg*.

## <a name="syntax"></a>Składnia

```
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argumenty

`input`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych typu *Ciąg*, który zawiera dane JSON.

`path`: *Ciąg*

Identyfikator wartości skalarnej danych JSON.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="example"></a>Przykład

Źródło danych **JsonField** zawiera następujące dane w formacie JSON: **{"Numer_kompilacji":"7.3.1234.1", "KeyThumbprint":"7366E"}**. W tym przypadku wyrażenie `JSONVALUE (JsonField, "BuildNumber")` zwraca następującą wartość typu danych *String*: **"7.3.1234.1".**

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)
