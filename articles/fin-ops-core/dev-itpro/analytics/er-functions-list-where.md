---
title: WHERE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji WHERE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 392cf7acebd7ad95bcc0f5d4b7a67500a412a795
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041844"
---
# <a name="WHERE">WHERE, funkcja ER</a>

[!include [banner](../includes/banner.md)]

Funkcja `WHERE` zwraca określoną listę jako wartość typu *Lista rekordów* po jej odfiltrowaniu zgodnie z określonym warunkiem.

## <a name="syntax"></a>Składnia

```vb
WHERE (list, condition)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`condition`: *Wartość logiczna*

Prawidłowe wyrażenie warunkowe, które jest używane do filtrowania rekordów z określonej listy.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ta funkcja różni się od funkcji [FILTER](er-functions-list-filter.md), ponieważ podany warunek jest stosowany do każdego źródła danych modułu Raportowanie elektroniczne (ER) o typie *Lista rekordów* obecnym w pamięci.

Jeśli argumenty skonfigurowane dla tej funkcji (`list` i `condition`) zezwalają na przetłumaczenie tego żądania na bezpośrednie wywołanie SQL, w czasie projektowania jest wyświetlany komunikat ostrzegawczy. Ten komunikat informuje użytkownika, że wydajność może się zwiększyć, jeśli funkcja [FILTER](er-functions-list-filter.md) będzie używana zamiast funkcji `WHERE`.

## <a name="example-1"></a>Przykład 1

Jeśli element **Vendor** został skonfigurowany jako źródło danych ER odwołujące się do tabeli VendTable, wyrażenie `WHERE (Vendors, Vendors.VendGroup = "40")` zwraca listę wyłącznie dostawców należących do grupy dostawców 40.

## <a name="example-2"></a>Przykład 2

Po wprowadzeniu źródła danych **DS** typu *Pole obliczeniowe* zawierającego wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `WHERE( DS, DS.Value = "B")` zwraca listę z tylko jednym rekordem, który zawiera tekst **„B”** w polu **Wartość**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
