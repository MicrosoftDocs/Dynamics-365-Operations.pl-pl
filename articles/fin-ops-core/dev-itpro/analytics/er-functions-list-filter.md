---
title: FILTER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FILTER w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/14/2021
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
ms.openlocfilehash: e857306574dda7bad5dd25fc7708514997d8e86f
ms.sourcegitcommit: b1c758ec4abfcf3bf9e50f18c1102d4a9c1316d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2021
ms.locfileid: "7922430"
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

## <a name="usage-notes"></a><a name="usage-notes"></a>Uwagi dotyczące użytkowania

Ta funkcja różni się od funkcji [WHERE](er-functions-list-where.md), ponieważ podany warunek jest stosowany do każdego źródła danych modułu Raportowanie elektroniczne (ER) o typie *Rekordy tabeli* na poziomie bazy danych. Listę i warunek można zdefiniować przy użyciu tabel i relacji.

Jeśli jeden lub oba argumenty skonfigurowane dla tej funkcji (`list` i `condition`) nie zezwalają na przetłumaczenie tego żądania na bezpośrednie wywołanie SQL, w czasie projektowania jest generowany wyjątek. Ten wyjątek informuje użytkownika, że elementu `list` lub `condition` nie można użyć do tworzenia zapytania dotyczącego bazy danych.

> [!NOTE]
> Funkcja `FILTER` różni się od funkcji `WHERE` w przypadku korzystania z funkcji [`VALUEIN`](er-functions-logical-valuein.md) do określania kryteriów wyboru.
> 
> - Jeśli funkcja `VALUEIN` jest używana w zakresie funkcji `WHERE`, a drugi argument `VALUEIN` odwołuje się do źródła danych, które nie zwraca rekordów, jest uznawana wartość logiczna *[Fałsz](er-formula-supported-data-types-primitive.md#boolean)*, która zwraca `VALUEIN`. W związku z tym wyrażenie `WHERE(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` nie zwróci rekordów dostawcy, jeśli źródło danych **VendGroups** nie zwróci rekordów grupy dostawców.
> - Jeśli funkcja `VALUEIN` jest używana w zakresie funkcji `FILTER`, a drugi argument `VALUEIN` odwołuje się do źródła danych, które nie zwraca rekordów, wartość logiczna *[Fałsz](er-formula-supported-data-types-primitive.md#boolean)*, która zwraca `VALUEIN`, jest ignorowana. W związku z tym wyrażenie `FILTER(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` zwraca wszystkie rekordy źródła danych **Dostawcy**, nawet jeśli źródło danych **VendGroups** nie zwróci żadnych rekordów grupy dostawców.

## <a name="example-1"></a>Przykład 1

Jeśli element **Vendor** został skonfigurowany jako źródło danych ER odwołujące się do tabeli VendTable, wyrażenie `FILTER (Vendors, Vendors.VendGroup = "40")` zwraca listę wyłącznie dostawców należących do grupy dostawców 40.

## <a name="example-2"></a>Przykład 2

Jeśli element **Vendor** został skonfigurowany jako źródło danych ER odwołujące się do tabeli VendTable, a element **parmVendorBankGroup** został skonfigurowany jako źródło danych ER zwracające wartość o typie danych *Ciąg*, wyrażenie `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` zwraca listę tylko kont dostawców należących do określonej grupy bankowej.

## <a name="example-3"></a>Przykład 3

Wprowadzasz źródło danych **DS** typu *Pole obliczeniowe*, które zawiera wyrażenie `SPLIT ("A,B,C", ",")`. Następnie wprowadzasz inne wyrażenie `FILTER( DS, DS.Value = "B")`. Podczas próby zapisania tego wyrażenia w projektancie formuł ER, jest zgłaszany następujący wyjątek: „Błąd weryfikacji: wyrażenie listy funkcji FILTER nie pozwala na tworzenie zapytań”.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
