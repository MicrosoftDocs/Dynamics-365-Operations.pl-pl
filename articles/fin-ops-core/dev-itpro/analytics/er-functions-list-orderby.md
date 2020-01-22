---
title: ORDERBY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ORDERBY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: a6aed53dcad6d402fc2ca61ae0687016cdb3af5b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916207"
---
# <span data-ttu-id="c8222-103"><a name="ORDERBY">ORDERBY, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="c8222-103"><a name="ORDERBY">ORDERBY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8222-104">Funkcja `ORDERBY` zwraca określoną listę jako wartość typu *Lista rekordów* po jej posortowaniu zgodnie z określonymi argumentami.</span><span class="sxs-lookup"><span data-stu-id="c8222-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="c8222-105">Te argumenty można zdefiniować jako wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="c8222-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8222-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="c8222-106">Syntax</span></span>

```
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="c8222-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c8222-107">Arguments</span></span>

<span data-ttu-id="c8222-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="c8222-108">`list`: *Record list*</span></span>

<span data-ttu-id="c8222-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="c8222-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="c8222-110">`expression 1`: *Pole*</span><span class="sxs-lookup"><span data-stu-id="c8222-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="c8222-111">Prawidłowa ścieżka pola źródła danych, do której odwołuje się argument `list` wywoływanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c8222-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="c8222-112">Przywoływane pole musi być polem typu danych pierwotnych.</span><span class="sxs-lookup"><span data-stu-id="c8222-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="c8222-113">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="c8222-113">This argument is required.</span></span>

<span data-ttu-id="c8222-114">`expression N`: *Pole*</span><span class="sxs-lookup"><span data-stu-id="c8222-114">`expression N`: *Field*</span></span>

<span data-ttu-id="c8222-115">Prawidłowa ścieżka pola źródła danych, do której odwołuje się argument `list` wywoływanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c8222-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="c8222-116">Przywoływane pole musi być polem typu danych pierwotnych.</span><span class="sxs-lookup"><span data-stu-id="c8222-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="c8222-117">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="c8222-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="c8222-118">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c8222-118">Return values</span></span>

<span data-ttu-id="c8222-119">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="c8222-119">*Record list*</span></span>

<span data-ttu-id="c8222-120">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="c8222-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="c8222-121">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="c8222-121">Example 1</span></span>

<span data-ttu-id="c8222-122">Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("C|B|A", "|")`, wyrażenie `FIRST( ORDERBY( DS, DS. Value)).Value` zwraca wartość tekstową **"A"**.</span><span class="sxs-lookup"><span data-stu-id="c8222-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c8222-123">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="c8222-123">Example 2</span></span>

<span data-ttu-id="c8222-124">Jeśli opcja **Vendor** jest skonfigurowana jako źródło danych raportowania elektronicznego (ER) odwołujące się do tabeli VendTable, wyrażenie `ORDERBY (Vendors, Vendors.'name()')` zwraca listę dostawców posortowaną według nazw w porządku rosnącym.</span><span class="sxs-lookup"><span data-stu-id="c8222-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8222-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c8222-125">Additional resources</span></span>

[<span data-ttu-id="c8222-126">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="c8222-126">List functions</span></span>](er-functions-category-list.md)
