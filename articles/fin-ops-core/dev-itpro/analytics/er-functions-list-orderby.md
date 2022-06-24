---
title: ORDERBY, funkcja ER
description: Ten artykuł zawiera ogólne informacje o używaniu funkcji ORDERBY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 1a922405ea23d2b1ff5ac062785e68626edbc8f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883767"
---
# <a name="orderby-er-function"></a>ORDERBY, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ORDERBY` zwraca określoną listę jako wartość typu *Lista rekordów* po jej posortowaniu zgodnie z określonymi argumentami. Te argumenty można zdefiniować jako wyrażenia.

## <a name="syntax-1"></a><a name="syntax-1"></a>Składnia 1

```vb
ORDERBY (list, expression 1[, expression 2, …, expression N])
```

## <a name="syntax-2"></a><a name="syntax-2"></a>Składnia 2

```vb
ORDERBY (location, list, expression 1[, expression 2, …, expression N])
```

> [!NOTE]
> Ta składnia jest obsługiwana przez Microsoft Dynamics 365 Finance w wersji 10.0.25 i nowszych.

## <a name="arguments"></a>Argumenty

`location`: *[String](er-formula-supported-data-types-primitive.md#string)*

Lokalizacja, w której ma być uruchamiane sortowanie. Poprawne są następujące opcje:

- "Query"
- "InMemory"

`list`: *[Record list](er-formula-supported-data-types-composite.md#record-list)*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`expression 1`: *Pole*

Prawidłowa ścieżka pola źródła danych, do której odwołuje się argument `list` wywoływanej funkcji. Przywoływane pole musi być polem typu danych pierwotnych. Ten argument jest wymagany.

`expression N`: *Pole*

Prawidłowa ścieżka pola źródła danych, do której odwołuje się argument `list` wywoływanej funkcji. Przywoływane pole musi być polem typu danych pierwotnych. Te dodatkowe argumenty są opcjonalne.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

### <a name="syntax-1"></a>Składnia 1

Sortowanie danych jest zawsze wykonywane w pamięci serwera aplikacji. Aby uzyskać więcej szczegółów, zobacz [przykład 1](#example-1).

### <a name="syntax-2"></a>Składnia 2

### <a name="sorting-in-memory"></a>Sortowanie w pamięci

Jeśli argument `location` jest określony jako **InMemory**, sortowanie danych jest wykonywane w pamięci serwera aplikacji. Aby uzyskać więcej szczegółów, zobacz [przykład 2](#example-2).

### <a name="sorting-in-database"></a>Sortowanie w bazie danych

Jeśli argument `location` zostanie określony jako **Zapytanie**, sortowanie danych jest wykonywane na poziomie bazy danych. W tym przypadku argument `list` musi wskazać jedno z następujących źródeł danych [raportowania elektronicznego (ER)](general-electronic-reporting.md), które określa źródło aplikacji, dla których może zostać utworzone bezpośrednie zapytanie bazy danych:

- Źródło danych typu *Rekordy tabeli*
- Relacja źródła danych typu *Rekordy tabeli*
- Typ źródła danych typu *Pole obliczeniowe*

Argumenty `expression 1` i `expression N` muszą wskazywać na pola źródła danych ER, które określają odpowiednie pola źródła aplikacji, dla których można również utworzyć bezpośrednie zapytanie do bazy danych.

Jeśli nie można utworzyć bezpośredniego zapytania do bazy danych, w projektancie odwzorowania modelu ER pojawia się [błąd](er-components-inspections.md#i18) walidacji. Odebrany komunikat stwierdza, że wyrażenie ER zawierające funkcję `ORDERBY` nie może zostać uruchomione w czasie wykonywania.

Dla lepszej wydajności zalecamy użycie opcji **Query**, gdy sortowanie jest skonfigurowane dla źródeł danych aplikacji, które mogą zawierać dużą liczbę rekordów (na przykład dla tabel aplikacji transakcyjnych).

> [!NOTE]
> Sama funkcja `ORDEBY` nie może być przetłumaczona na bezpośrednie zapytanie do bazy danych. Dlatego źródło danych ER, które zawiera tę funkcję, nie może być przedmiotem zapytań. Nie może być również użyty w zakresie funkcji ER takich jak [FILTER](er-functions-list-filter.md) i [ALLITEMSQUERY](er-functions-list-allitemsquery.md), gdzie mogą być użyte tylko źródła danych, które można odpytywać.

Aby uzyskać więcej informacji, zobacz [przykład 3](#example-3) i [przykład 4](#example-4).

### <a name="comparability"></a>Porównywalność

Ponieważ silnik bazy danych SQL i serwer aplikacji Finanse mogą używać różnych wartości rankingu dla pojedynczego znaku, wynik sortowania tej samej listy rekordów może się różnić, gdy do sortowania używane jest pole [String](er-formula-supported-data-types-primitive.md#string). Aby uzyskać więcej szczegółów, zobacz [przykład 5](#example-5).

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a>Przykład 1: Domyślne wykonywanie w pamięci

Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("C|B|A", "|")`, wyrażenie `FIRST( ORDERBY( DS, DS. Value)).Value` zwraca wartość tekstową **"A"**.

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a>Przykład 2: Wyraźne wykonywanie w pamięci

Jeśli opcja **Vendor** jest skonfigurowana jako źródło danych raportowania elektronicznego (ER) typu *Rekordy tabeli*, odwołujące się do tabeli **VendTable**, zarówno wyrażenie `ORDERBY (Vendor, Vendor.'name()')`, jak i `ORDERBY ("InMemory", Vendor, Vendor.'name()')` zwracają listę dostawców posortowaną według nazw w porządku rosnącym.

Kiedy konfigurujesz wyrażenie `ORDERBY ("Query", Vendor, Vendor.'name()')` w projektancie odwzorowania modelu ER, pojawia się błąd [walidacji](er-components-inspections.md#i8) w czasie projektowania, ponieważ ścieżka `Vendor.'name()'` odnosi się do metody aplikacji, która posiada logikę, która nie może być przetłumaczona na bezpośrednie zapytanie do bazy danych.

## <a name="example-3-database-query"></a><a name="example-3"></a>Przykład 3: Kwerenda bazy danych

Jeśli **TaxTransaction** jest skonfigurowane jako źródło danych ER typu *Rekordy tabeli*, które odwołuje się do tabeli **TaxTrans**, wyrażenie `ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` rekordy na poziomie aplikacji bazy danych i zwraca listę transakcji podatkowych posortowanych rosnąco według kodu podatkowego.

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a>Przykład 4: Źródła danych, które można przeszukiwać

Jeśli **TaxTransaction** jest skonfigurowane jako źródło danych ER typu *Rekordy tabeli*, które odwołuje się do tabeli **TaxTrans**, źródło danych ER **TaxTransactionFiltered** może być skonfigurowane tak, aby zawierało wyrażenie `FILTER(TaxTransaction, TaxCode="VAT19")`, które będzie pobierać transakcje dla określonego kodu podatkowego. Ponieważ skonfigurowane źródło danych **TaxTransactionFiltered** ER jest możliwe do przeszukania, wyrażenie `ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` może być skonfigurowane tak, aby zwrócić listę przefiltrowanych transakcji podatkowych posortowanych według daty transakcji w porządku rosnącym.

Jeśli skonfigurujesz **TaxTransactionOrdered** jako źródło danych ER typu *Pole kalkulowane* zawierające wyrażenie `ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` oraz źródło danych ER typu *Pole kalkulowane* zawierające wyrażenie `FILTER(TaxTransactionOrdered, TaxCode="VAT19")`, pojawia się błąd [błąd](er-components-inspections.md#i18) w czasie projektowania w projektancie odwzorowania modelu ER. Ten błąd pojawia się, ponieważ pierwszy argument funkcji [FILTER](er-functions-list-filter.md#usage-notes) musi odwoływać się do źródła danych ER, ale źródło danych **TaxTransactionOrdered**, które zawiera funkcję `ORDERBY`, nie jest dostępne dla zapytań.

## <a name="example-5-comparability"></a><a name="example-5"></a>Przykład 5: Porównywaność

### <a name="prerequisites"></a>Wymagania wstępne

1. Wprowadź źródło danych **DS1** typu *Pole obliczeniowe*, które zawiera wyrażenie `SPLIT ("D1|_D2|D3", "|")`.
2. Otwórz stronę **[Wartości wymiaru finansowego](../../../finance/general-ledger/financial-dimensions.md)** i wybierz wymiar **CostCenter**.
3. Wprowadź następujące wartości rozmiaru: **D1**, **\_D2** i **D3**.

### <a name="sorting-in-memory"></a>Sortowanie w pamięci

1. Skonfiguruj źródło danych **DS2** o typie *Pole kalkulowane*, które zawiera wyrażenie `ORDERBY("InMemory", DS1, DS1.Value)`.
2. Zauważmy, że wyrażenie `FIRST(DS2).Value` zwraca wartość tekstową **"D1"**, wyrażenie `INDEX(DS2, COUNT(DS2)).Value` zwraca wartość tekstową **"\_D2"**, a wyrażenie `STRINGJOIN(DS2, DS2.Value, "|")` zwraca wartość tekstową **"D1\|D3\|\_D2"**.

### <a name="sorting-in-database"></a>Sortowanie w bazie danych

1. Podaj źródło danych **DS3** typu *Rekordy tabeli*, które odnosi się do encji **FinancialDimensionValueEntity**.
2. Skonfiguruj źródło danych **DS4** o typie *Pole kalkulowane*, które zawiera wyrażenie `FILTER(DS3, DS3.FinancialDimension="CostCenter")`.
3. Skonfiguruj źródło danych **DS5** o typie *Pole kalkulowane*, które zawiera wyrażenie `ORDERBY(DS4, DS4.DimensionValue)`.
4. Zauważmy, że wyrażenie `FIRST(DS5).Value` zwraca wartość tekstową **"\_D2"**, wyrażenie `INDEX(DS5, COUNT(DS5)).Value` zwraca wartość tekstową **"D3"**, a wyrażenie `STRINGJOIN(DS5, DS5.Value, "|")` zwraca wartość tekstową **"\_D2\|D1\|D3"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
