---
title: ALLITEMSQUERY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ALLITEMSQUERY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 37546fccf804a4522638147d39206997e8c0c24c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745376"
---
# <a name="allitemsquery-er-function"></a>ALLITEMSQUERY, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `ALLITEMSQUERY` jest wykonywana jako sprzężone zapytanie SQL. Zwraca nową spłaszczoną wartość *Lista rekordów*, która składa się z listy rekordów reprezentującej wszystkie elementy, które odpowiadają określonej ścieżce.

## <a name="syntax"></a>Składnia

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a>Argumenty

`path`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*. Musi zawierać co najmniej jeden zbiór.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Określona ścieżka musi być zdefiniowana jako prawidłowa ścieżka źródła danych do elementu źródła danych o typie danych *Lista rekordów*. Musi również zawierać co najmniej jeden zbiór. Elementy danych, takie jak *ciąg* i *data*, powinny powodować zgłaszanie błędu w konstruktorze wyrażeń modułu Raportowanie elektroniczne (ER) w czasie projektowania.

Gdy ta funkcja jest stosowana do źródeł danych o typie danych *Lista rekordów*, które odwołują się do obiektu aplikacji, który można bezpośrednio wywołać za pomocą instrukcji SQL (na przykład tabeli, jednostki lub zapytania), działa jako sprzężone zapytanie SQL. W przeciwnym razie działa w pamięci jako funkcja [ALLITEMS](er-functions-list-allitems.md).

## <a name="example"></a>Przykład

Definiuje się następujące źródła danych w mapowaniu modelu:

- Źródło danych **CustInv** typu *Rekordy tabeli*, które odwołuje się do tabeli CustInvoiceTable
- Źródło danych **FilteredInv** typu *Pole obliczeniowe*, które zawiera wyrażenie `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`
- Źródło danych **JourLines** typu *Pole obliczeniowe*, które zawiera wyrażenie `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`

Po uruchomieniu mapowania modelu do wywoływania źródła danych **JourLines** uruchamiana jest następująca instrukcja SQL:

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
