---
title: GUIDVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GUIDVALUE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: be5e8e7625d0226c9eb59efd3217fce7b8eba086
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915701"
---
# <a name="GUIDVALUE">GUIDVALUE, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `GUIDVALUE` przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *Identyfikator GUID*.

## <a name="syntax"></a>Składnia

```
GUIDVALUE (input)
```

## <a name="arguments"></a>Argumenty

`input`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.

## <a name="return-values"></a>Wartości zwracane

*GUID*

Wynikowa wartość globalnie unikatowego identyfikatora (GUID).

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Aby wykonać przekształcenie w przeciwnym kierunku (tzn. aby przekonwertować podane dane wejściowe o typie danych *GUID* na element danych o typie danych *String*), można użyć funkcji [TEXT](er-functions-text-text.md).

## <a name="example"></a>Przykład

Definiuje się następujące źródła danych w mapowaniu modelu:

- Źródło danych **myID** typu *Pole obliczeniowe*, które zawiera wyrażenie `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`
- Źródło danych **Users** typu *Rekordy tabeli*, które odwołuje się do tabeli UserInfo

Następnie użyj wyrażenia, takiego jak `FILTER (Users, Users.objectId = myID)`, do odfiltrowania tabeli UserInfo według pola **objectid** typu danych *GUID*.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)
