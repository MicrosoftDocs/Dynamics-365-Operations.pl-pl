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
ms.openlocfilehash: 647019a103006c8b74bc26885c51f5372dcf0c42
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917518"
---
# <span data-ttu-id="6189b-103"><a name="ALLITEMSQUERY">ALLITEMSQUERY, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="6189b-103"><a name="ALLITEMSQUERY">ALLITEMSQUERY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6189b-104">Funkcja `ALLITEMSQUERY` jest wykonywana jako sprzężone zapytanie SQL.</span><span class="sxs-lookup"><span data-stu-id="6189b-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="6189b-105">Zwraca nową spłaszczoną wartość *Lista rekordów*, która składa się z listy rekordów reprezentującej wszystkie elementy, które odpowiadają określonej ścieżce.</span><span class="sxs-lookup"><span data-stu-id="6189b-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="6189b-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="6189b-106">Syntax</span></span>

```
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="6189b-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="6189b-107">Arguments</span></span>

<span data-ttu-id="6189b-108">`path`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="6189b-108">`path`: *Record list*</span></span>

<span data-ttu-id="6189b-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="6189b-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="6189b-110">Musi zawierać co najmniej jeden zbiór.</span><span class="sxs-lookup"><span data-stu-id="6189b-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="6189b-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="6189b-111">Return values</span></span>

<span data-ttu-id="6189b-112">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="6189b-112">*Record list*</span></span>

<span data-ttu-id="6189b-113">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="6189b-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6189b-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="6189b-114">Usage notes</span></span>

<span data-ttu-id="6189b-115">Określona ścieżka musi być zdefiniowana jako prawidłowa ścieżka źródła danych do elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="6189b-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="6189b-116">Musi również zawierać co najmniej jeden zbiór.</span><span class="sxs-lookup"><span data-stu-id="6189b-116">It must also contain at least one relation.</span></span> <span data-ttu-id="6189b-117">Elementy danych, takie jak *ciąg* i *data*, powinny powodować zgłaszanie błędu w konstruktorze wyrażeń modułu Raportowanie elektroniczne (ER) w czasie projektowania.</span><span class="sxs-lookup"><span data-stu-id="6189b-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="6189b-118">Gdy ta funkcja jest stosowana do źródeł danych o typie danych *Lista rekordów*, które odwołują się do obiektu aplikacji, który można bezpośrednio wywołać za pomocą instrukcji SQL (na przykład tabeli, jednostki lub zapytania), działa jako sprzężone zapytanie SQL.</span><span class="sxs-lookup"><span data-stu-id="6189b-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="6189b-119">W przeciwnym razie działa w pamięci jako funkcja [ALLITEMS](er-functions-list-allitems.md).</span><span class="sxs-lookup"><span data-stu-id="6189b-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="6189b-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="6189b-120">Example</span></span>

<span data-ttu-id="6189b-121">Definiuje się następujące źródła danych w mapowaniu modelu:</span><span class="sxs-lookup"><span data-stu-id="6189b-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="6189b-122">Źródło danych **CustInv** typu *Rekordy tabeli*, które odwołuje się do tabeli CustInvoiceTable</span><span class="sxs-lookup"><span data-stu-id="6189b-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="6189b-123">Źródło danych **FilteredInv** typu *Pole obliczeniowe*, które zawiera wyrażenie `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span><span class="sxs-lookup"><span data-stu-id="6189b-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="6189b-124">Źródło danych **JourLines** typu *Pole obliczeniowe*, które zawiera wyrażenie `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span><span class="sxs-lookup"><span data-stu-id="6189b-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="6189b-125">Po uruchomieniu mapowania modelu do wywoływania źródła danych **JourLines** uruchamiana jest następująca instrukcja SQL:</span><span class="sxs-lookup"><span data-stu-id="6189b-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="6189b-126">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6189b-126">Additional resources</span></span>

[<span data-ttu-id="6189b-127">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="6189b-127">List functions</span></span>](er-functions-category-list.md)
