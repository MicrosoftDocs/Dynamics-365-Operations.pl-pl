---
title: Funkcja LISTDISTINCT ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LISTDISTINCT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f20565d73cea8d0cc1361bd03cda86a79a97955e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563831"
---
# <a name="listdistinct-er-function"></a><span data-ttu-id="c6ce0-103">Funkcja LISTDISTINCT ER</span><span class="sxs-lookup"><span data-stu-id="c6ce0-103">LISTDISTINCT ER Function</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="c6ce0-104">Funkcja `LISTDISTINCT` oblicza określone wyrażenie jako selektor dla każdego rekordu określonej listy.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-104">The `LISTDISTINCT` function calculates the specified expression as a selector for every record of the specified list.</span></span> <span data-ttu-id="c6ce0-105">Zwraca nową wartość *Lista rekordów* zawierającą jeden rekord dla każdej unikatowej wartości selektora.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-105">It returns a new *Record list* value that contains a single record for each unique selector value.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6ce0-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="c6ce0-106">Syntax</span></span>

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a><span data-ttu-id="c6ce0-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c6ce0-107">Arguments</span></span>

<span data-ttu-id="c6ce0-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="c6ce0-108">`list`: *Record list*</span></span>

<span data-ttu-id="c6ce0-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="c6ce0-110">`selector`: *Pierwotny typ danych*</span><span class="sxs-lookup"><span data-stu-id="c6ce0-110">`selector`: *Primitive data type*</span></span>

<span data-ttu-id="c6ce0-111">Prawidłowe wyrażenie używane do obliczenia wartości selektora dla każdego rekordu na określonej liście.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-111">A valid expression that is used to calculate a selector value for every record in the specified list.</span></span>

<span data-ttu-id="c6ce0-112">Dla tego parametru są obsługiwane następujące typy danych:</span><span class="sxs-lookup"><span data-stu-id="c6ce0-112">The following data types are supported for this parameter:</span></span>

- <span data-ttu-id="c6ce0-113">Wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="c6ce0-113">Boolean</span></span>
- <span data-ttu-id="c6ce0-114">Data</span><span class="sxs-lookup"><span data-stu-id="c6ce0-114">Date</span></span>
- <span data-ttu-id="c6ce0-115">Data/godzina</span><span class="sxs-lookup"><span data-stu-id="c6ce0-115">DateTime</span></span>
- <span data-ttu-id="c6ce0-116">Identyfikator Guid</span><span class="sxs-lookup"><span data-stu-id="c6ce0-116">GUID</span></span>
- <span data-ttu-id="c6ce0-117">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="c6ce0-117">Integer</span></span>
- <span data-ttu-id="c6ce0-118">Int64</span><span class="sxs-lookup"><span data-stu-id="c6ce0-118">Int64</span></span>
- <span data-ttu-id="c6ce0-119">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="c6ce0-119">Real</span></span>
- <span data-ttu-id="c6ce0-120">Ciąg</span><span class="sxs-lookup"><span data-stu-id="c6ce0-120">String</span></span>

## <a name="return-values"></a><span data-ttu-id="c6ce0-121">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c6ce0-121">Return values</span></span>

<span data-ttu-id="c6ce0-122">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="c6ce0-122">*Record list*</span></span>

<span data-ttu-id="c6ce0-123">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-123">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c6ce0-124">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="c6ce0-124">Usage notes</span></span>

<span data-ttu-id="c6ce0-125">Struktura tworzonej listy pasuje do struktury określonej listy.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-125">The structure of the list that is created matches the structure of the specified list.</span></span>

<span data-ttu-id="c6ce0-126">Ta sama wartość selektora może zostać obliczona dla wielu rekordów na określonej liście.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-126">The same selector value might be calculated for multiple records in the specified list.</span></span> <span data-ttu-id="c6ce0-127">W tym przypadku wartości pól odpowiadające danemu rekordowi z utworzonej listy są równe wartościom pierwszego rekordu z określonej listy, dla którego obliczana jest wartość selektora.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-127">In this case, field values of the corresponding record in the created list equal the values of the first record from the specified list that the selector value is calculated for.</span></span>

<span data-ttu-id="c6ce0-128">Wykonywanie tej funkcji jest wykonywane na dowolnym źródle danych [raportowania elektronicznego (ER)](general-electronic-reporting.md) typu *Lista rekordów*, które znajduje się w pamięci.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-128">The execution of this function is done on any [Electronic reporting (ER)](general-electronic-reporting.md) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="c6ce0-129">Źródło danych **GROUPBY** może być również używane do generowania listy rekordów, dla których jest obliczane selektor zawierający różne wartości.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-129">The **GROUPBY** data source can also be used to generate the list of records that the selector that has distinct values is calculated for.</span></span> <span data-ttu-id="c6ce0-130">Jednak z perspektywy wykorzystania wydajności i pamięci lepiej jest stosować funkcję `LISTDISTINCT` niż źródło danych **GROUPBY**, ponieważ wykonywanie funkcji jest wykonywane w pamięci.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-130">However, from a performance and memory consumption perspective, it's better to use the `LISTDISTINCT` function than the **GROUPBY** data source, because the execution of the function is done in memory.</span></span>

## <a name="example"></a><span data-ttu-id="c6ce0-131">Przykład</span><span class="sxs-lookup"><span data-stu-id="c6ce0-131">Example</span></span>

<span data-ttu-id="c6ce0-132">W poniższym przykładzie pokazano, jak można uzyskać listę unikatowych numerów kont odbiorców, dla których wystawiono co najmniej jedną fakturę sprzedaży lub fakturę projektu w określonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-132">The following example shows how you can get the list of unique customer account numbers that at least one sales invoice or project invoice has been issued to during a specific period.</span></span>

1. <span data-ttu-id="c6ce0-133">Wprowadź źródło danych **SalesInvoice** typu `Record list`, które odwołuje się do tabeli aplikacji **CustInvoiceJour** i filtruje faktury sprzedaży dla wybranych okresów.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-133">Enter the **SalesInvoice** data source of the `Record list` type that refers to the **CustInvoiceJour** application table and filters sales invoices for specific periods.</span></span>

    <span data-ttu-id="c6ce0-134">Pole `InvoiceAccount` tego źródła danych zwraca numer konta zafakturowanego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-134">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

2. <span data-ttu-id="c6ce0-135">Wprowadź źródło danych **ProjectInvoice** typu `Record list`, które odwołuje się do tabeli aplikacji **ProjInvoiceJour** i filtruje faktury projektu dla wybranych okresów.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-135">Enter the **ProjectInvoice** data source of the `Record list` type that refers to the **ProjInvoiceJour** application table and filters project invoices for specific periods.</span></span>

    <span data-ttu-id="c6ce0-136">Pole `InvoiceAccount` tego źródła danych zwraca numer konta zafakturowanego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-136">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

3. <span data-ttu-id="c6ce0-137">Skonfiguruj źródło danych **AllInvoices** typu `Calculated field`, które zawiera wyrażenie `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-137">Configure the **AllInvoices** data source of the `Calculated field` type that contains the expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span></span>

    <span data-ttu-id="c6ce0-138">To źródło danych zwraca listę sprzężonych faktur sprzedaży i faktur projektu.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-138">This data source returns the joined list of sales invoices and project invoices.</span></span>

4. <span data-ttu-id="c6ce0-139">Skonfiguruj źródło danych **InvoicedCustomer** typu `Record list`, które zawiera wyrażenie `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-139">Configure the **InvoicedCustomer** data source of the `Record list` type that contains the expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span></span>

    <span data-ttu-id="c6ce0-140">To źródło danych zwraca nową listę zawierającą jeden rekord dla każdego unikatowego odbiorcy, który został zafakturowany w określonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-140">This data source returns a new list that contains a single record for every unique customer that has been invoiced during the defined period.</span></span> <span data-ttu-id="c6ce0-141">Pole `InvoiceAccount` tej listy zawiera numer konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="c6ce0-141">The `InvoiceAccount` field of this list contains a customer account number.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c6ce0-142">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c6ce0-142">Additional resources</span></span>

[<span data-ttu-id="c6ce0-143">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="c6ce0-143">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]