---
title: FILTER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FILTER w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/12/2019
ms.prod: ''
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
ms.openlocfilehash: c601babd3ea7122bc9ddf7bf101751d4c032016fb33c3d4101f588789491e817
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760033"
---
# <a name="filter-er-function"></a>FILTER, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `FILTER` zwraca określoną listę jako wartość typu *Lista rekordów* po zmianie zapytania tak, aby filtrowała ona dane pod kątem określonego warunku.

## <a name="syntax"></a>Składnia

```vb
FILTER (list, condition)
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

Ta funkcja różni się od funkcji [WHERE](er-functions-list-where.md), ponieważ podany warunek jest stosowany do każdego źródła danych modułu Raportowanie elektroniczne (ER) o typie *Rekordy tabeli* na poziomie bazy danych. Listę i warunek można zdefiniować przy użyciu tabel i relacji.

Jeśli jeden lub oba argumenty skonfigurowane dla tej funkcji (`list` i `condition`) nie zezwalają na przetłumaczenie tego żądania na bezpośrednie wywołanie SQL, w czasie projektowania jest generowany wyjątek. Ten wyjątek informuje użytkownika, że elementu `list` lub `condition` nie można użyć do tworzenia zapytania dotyczącego bazy danych.

## <a name="example-1"></a>Przykład 1

Jeśli element **Vendor** został skonfigurowany jako źródło danych ER odwołujące się do tabeli VendTable, wyrażenie `FILTER (Vendors, Vendors.VendGroup = "40")` zwraca listę wyłącznie dostawców należących do grupy dostawców 40.

## <a name="example-2"></a>Przykład 2

Jeśli element **Vendor** został skonfigurowany jako źródło danych ER odwołujące się do tabeli VendTable, a element **parmVendorBankGroup** został skonfigurowany jako źródło danych ER zwracające wartość o typie danych *Ciąg*, wyrażenie `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` zwraca listę tylko kont dostawców należących do określonej grupy bankowej.

## <a name="example-3"></a>Przykład 3

Wprowadzasz źródło danych **DS** typu *Pole obliczeniowe*, które zawiera wyrażenie `SPLIT ("A,B,C", ",")`. Następnie wprowadzasz inne wyrażenie `FILTER( DS, DS.Value = "B")`. Podczas próby zapisania tego wyrażenia w projektancie formuł ER, jest zgłaszany następujący wyjątek: „Błąd weryfikacji: wyrażenie listy funkcji FILTER nie pozwala na tworzenie zapytań”.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]