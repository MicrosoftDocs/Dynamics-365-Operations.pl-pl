---
title: Funkcja LISTDISTINCT ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LISTDISTINCT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 2333cfc21a16a5905acadd590982020fdf878330
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682274"
---
# <a name="listdistinct-er-function"></a>Funkcja LISTDISTINCT ER

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Funkcja `LISTDISTINCT` oblicza określone wyrażenie jako selektor dla każdego rekordu określonej listy. Zwraca nową wartość *Lista rekordów* zawierającą jeden rekord dla każdej unikatowej wartości selektora.

## <a name="syntax"></a>Składnia

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`selector`: *Pierwotny typ danych*

Prawidłowe wyrażenie używane do obliczenia wartości selektora dla każdego rekordu na określonej liście.

Dla tego parametru są obsługiwane następujące typy danych:

- Wartość logiczna
- Data
- Data/godzina
- Identyfikator Guid
- Wartość całkowita
- Int64
- Rzeczywisty
- Ciąg

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Struktura tworzonej listy pasuje do struktury określonej listy.

Ta sama wartość selektora może zostać obliczona dla wielu rekordów na określonej liście. W tym przypadku wartości pól odpowiadające danemu rekordowi z utworzonej listy są równe wartościom pierwszego rekordu z określonej listy, dla którego obliczana jest wartość selektora.

Wykonywanie tej funkcji jest wykonywane na dowolnym źródle danych [raportowania elektronicznego (ER)](general-electronic-reporting.md) typu *Lista rekordów*, które znajduje się w pamięci.

Źródło danych **GROUPBY** może być również używane do generowania listy rekordów, dla których jest obliczane selektor zawierający różne wartości. Jednak z perspektywy wykorzystania wydajności i pamięci lepiej jest stosować funkcję `LISTDISTINCT` niż źródło danych **GROUPBY**, ponieważ wykonywanie funkcji jest wykonywane w pamięci.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak można uzyskać listę unikatowych numerów kont odbiorców, dla których wystawiono co najmniej jedną fakturę sprzedaży lub fakturę projektu w określonym okresie.

1. Wprowadź źródło danych **SalesInvoice** typu `Record list`, które odwołuje się do tabeli aplikacji **CustInvoiceJour** i filtruje faktury sprzedaży dla wybranych okresów.

    Pole `InvoiceAccount` tego źródła danych zwraca numer konta zafakturowanego odbiorcy.

2. Wprowadź źródło danych **ProjectInvoice** typu `Record list`, które odwołuje się do tabeli aplikacji **ProjInvoiceJour** i filtruje faktury projektu dla wybranych okresów.

    Pole `InvoiceAccount` tego źródła danych zwraca numer konta zafakturowanego odbiorcy.

3. Skonfiguruj źródło danych **AllInvoices** typu `Calculated field`, które zawiera wyrażenie `LISTJOIN(SalesInvoice, ProjectInvoice)`.

    To źródło danych zwraca listę sprzężonych faktur sprzedaży i faktur projektu.

4. Skonfiguruj źródło danych **InvoicedCustomer** typu `Record list`, które zawiera wyrażenie `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.

    To źródło danych zwraca nową listę zawierającą jeden rekord dla każdego unikatowego odbiorcy, który został zafakturowany w określonym okresie. Pole `InvoiceAccount` tej listy zawiera numer konta odbiorcy.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
