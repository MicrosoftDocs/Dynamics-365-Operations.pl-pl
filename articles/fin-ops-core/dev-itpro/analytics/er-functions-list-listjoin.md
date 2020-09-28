---
title: Funkcja LISTJOIN ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LISTJOIN w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 035bf720a892e987ff9fc073ab8ed6f6cc6ea18e
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745112"
---
# <a name="listjoin-er-function"></a><span data-ttu-id="81cde-103">Funkcja LISTJOIN ER</span><span class="sxs-lookup"><span data-stu-id="81cde-103">LISTJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81cde-104">Funkcja `LISTJOIN` zwraca wartość typu *Lista rekordów*, która reprezentuje nową połączoną listę rekordów utworzoną na podstawie określonych argumentów.</span><span class="sxs-lookup"><span data-stu-id="81cde-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="81cde-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="81cde-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="81cde-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="81cde-106">Arguments</span></span>

<span data-ttu-id="81cde-107">`list 1`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="81cde-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="81cde-108">Odwołanie do źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="81cde-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="81cde-109">Ten argument jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="81cde-109">This argument is mandatory.</span></span>

<span data-ttu-id="81cde-110">`list N`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="81cde-110">`list N`: *Record list*</span></span>

<span data-ttu-id="81cde-111">Odwołanie do źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="81cde-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="81cde-112">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="81cde-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="81cde-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="81cde-113">Return values</span></span>

<span data-ttu-id="81cde-114">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="81cde-114">*Record list*</span></span>

<span data-ttu-id="81cde-115">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="81cde-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="81cde-116">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="81cde-116">Usage notes</span></span>

<span data-ttu-id="81cde-117">Tworzona struktura listy zawiera tylko pola, które są prezentowane w strukturze każdej listy rekordów, wymienionej w argumentach.</span><span class="sxs-lookup"><span data-stu-id="81cde-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="81cde-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="81cde-118">Example</span></span>

<span data-ttu-id="81cde-119">Wprowadź źródło danych **Rekord 1** typu `Container`.</span><span class="sxs-lookup"><span data-stu-id="81cde-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="81cde-120">To źródło danych zawiera następujące pola zagnieżdżone typu `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="81cde-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="81cde-121">**Kod**: to pole zawiera wyrażenie, które zwraca wartość typu `String`.</span><span class="sxs-lookup"><span data-stu-id="81cde-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="81cde-122">**Ilość**: to pole zawiera wyrażenie, które zwraca wartość typu `Real`.</span><span class="sxs-lookup"><span data-stu-id="81cde-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="81cde-123">Wprowadź następnie źródło danych **Rekord 2** typu `Container`.</span><span class="sxs-lookup"><span data-stu-id="81cde-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="81cde-124">To źródło danych zawiera następujące pola zagnieżdżone typu `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="81cde-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="81cde-125">**Ilość**: to pole zawiera wyrażenie, które zwraca wartość typu `Real`.</span><span class="sxs-lookup"><span data-stu-id="81cde-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="81cde-126">**IsValid**: to pole zawiera wyrażenie, które zwraca wartość typu `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="81cde-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

![Strona projektanta mapowania modelu ER](./media/er-functions-list-listjoin-image1.gif)

<span data-ttu-id="81cde-128">W takim przypadku wyrażenie `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` zwraca nową listę zawierającą dwa rekordy.</span><span class="sxs-lookup"><span data-stu-id="81cde-128">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span>

![Strona projektanta mapowania modelu ER z dwoma rekordami](./media/er-functions-list-listjoin-image2.gif)

<span data-ttu-id="81cde-130">Struktura tej listy składa się z pojedynczego pola **Ilość** typu `Real`, ponieważ jest ono jedynym polem, które jest prezentowane w każdym argumencie wywołanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="81cde-130">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

![Strona projektanta mapowania modelu ER — pole ilości/liczby](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a><span data-ttu-id="81cde-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="81cde-132">Additional resources</span></span>

[<span data-ttu-id="81cde-133">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="81cde-133">List functions</span></span>](er-functions-category-list.md)

[<span data-ttu-id="81cde-134">Debugowanie źródeł danych dla wykonanego formatu ER w celu analizowania przekształcenia i przepływu danych</span><span class="sxs-lookup"><span data-stu-id="81cde-134">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>](er-debug-data-sources.md)
