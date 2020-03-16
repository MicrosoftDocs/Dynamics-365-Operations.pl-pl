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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 951de1d1505508ebb6abeff5b80ecef10573e117
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041278"
---
# <a name="TABLENAME2ID">TABLENAME2ID, funkcja ER</a>

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
