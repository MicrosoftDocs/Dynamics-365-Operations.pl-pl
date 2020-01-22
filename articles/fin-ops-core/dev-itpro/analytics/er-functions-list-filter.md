---
title: FILTER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FILTER w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 2783fbfa0ba45c8d3772cf9ca16d110549d227b4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917380"
---
# <span data-ttu-id="ff536-103"><a name="FILTER">FILTER, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="ff536-103"><a name="FILTER">FILTER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ff536-104">Funkcja `FILTER` zwraca określoną listę jako wartość typu *Lista rekordów* po zmianie zapytania tak, aby filtrowała ona dane pod kątem określonego warunku.</span><span class="sxs-lookup"><span data-stu-id="ff536-104">The `FILTER` function returns the specified list as a *Record list* value after the query has been changed so that it filters for the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="ff536-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ff536-105">Syntax</span></span>

```
FILTER (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="ff536-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ff536-106">Arguments</span></span>

<span data-ttu-id="ff536-107">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="ff536-107">`list`: *Record list*</span></span>

<span data-ttu-id="ff536-108">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="ff536-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="ff536-109">`condition`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="ff536-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="ff536-110">Prawidłowe wyrażenie warunkowe, które jest używane do filtrowania rekordów z określonej listy.</span><span class="sxs-lookup"><span data-stu-id="ff536-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="ff536-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="ff536-111">Return values</span></span>

<span data-ttu-id="ff536-112">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="ff536-112">*Record list*</span></span>

<span data-ttu-id="ff536-113">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="ff536-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ff536-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="ff536-114">Usage notes</span></span>

<span data-ttu-id="ff536-115">Ta funkcja różni się od funkcji [WHERE](er-functions-list-where.md), ponieważ podany warunek jest stosowany do każdego źródła danych modułu Raportowanie elektroniczne (ER) o typie *Rekordy tabeli* na poziomie bazy danych.</span><span class="sxs-lookup"><span data-stu-id="ff536-115">This function differs from the [WHERE](er-functions-list-where.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Table records* type at the database level.</span></span> <span data-ttu-id="ff536-116">Listę i warunek można zdefiniować przy użyciu tabel i relacji.</span><span class="sxs-lookup"><span data-stu-id="ff536-116">The list and condition can be defined by using tables and relations.</span></span>

<span data-ttu-id="ff536-117">Jeśli jeden lub oba argumenty skonfigurowane dla tej funkcji (`list` i `condition`) nie zezwalają na przetłumaczenie tego żądania na bezpośrednie wywołanie SQL, w czasie projektowania jest generowany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ff536-117">If one or both arguments that are configured for this function (`list` and `condition`) don't allow this request to be translated to the direct SQL call, an exception is thrown at design time.</span></span> <span data-ttu-id="ff536-118">Ten wyjątek informuje użytkownika, że elementu `list` lub `condition` nie można użyć do tworzenia zapytania dotyczącego bazy danych.</span><span class="sxs-lookup"><span data-stu-id="ff536-118">This exception informs the user that either `list` or `condition` can't be used to query the database.</span></span>

## <a name="example-1"></a><span data-ttu-id="ff536-119">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="ff536-119">Example 1</span></span>

<span data-ttu-id="ff536-120">Jeśli element **Vendor** został skonfigurowany jako źródło danych ER odwołujące się do tabeli VendTable, wyrażenie `FILTER (Vendors, Vendors.VendGroup = "40")` zwraca listę wyłącznie dostawców należących do grupy dostawców 40.</span><span class="sxs-lookup"><span data-stu-id="ff536-120">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `FILTER (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="ff536-121">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="ff536-121">Example 2</span></span>

<span data-ttu-id="ff536-122">Jeśli element **Vendor** został skonfigurowany jako źródło danych ER odwołujące się do tabeli VendTable, a element **parmVendorBankGroup** został skonfigurowany jako źródło danych ER zwracające wartość o typie danych *Ciąg*, wyrażenie `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` zwraca listę tylko kont dostawców należących do określonej grupy bankowej.</span><span class="sxs-lookup"><span data-stu-id="ff536-122">If **Vendor** is configured as an ER data source that refers to the VendTable table, and if **parmVendorBankGroup** is configured as an ER data source that returns a value of the *String* data type, the expression `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returns a list of only vendor accounts that belong to a specific bank group.</span></span>

## <a name="example-3"></a><span data-ttu-id="ff536-123">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="ff536-123">Example 3</span></span>

<span data-ttu-id="ff536-124">Wprowadzasz źródło danych **DS** typu *Pole obliczeniowe*, które zawiera wyrażenie `SPLIT ("A,B,C", ",")`.</span><span class="sxs-lookup"><span data-stu-id="ff536-124">You enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A,B,C", ",")`.</span></span> <span data-ttu-id="ff536-125">Następnie wprowadzasz inne wyrażenie `FILTER( DS, DS.Value = "B")`.</span><span class="sxs-lookup"><span data-stu-id="ff536-125">You then enter another expression, `FILTER( DS, DS.Value = "B")`.</span></span> <span data-ttu-id="ff536-126">Podczas próby zapisania tego wyrażenia w projektancie formuł ER, jest zgłaszany następujący wyjątek: „Błąd weryfikacji: wyrażenie listy funkcji FILTER nie pozwala na tworzenie zapytań”.</span><span class="sxs-lookup"><span data-stu-id="ff536-126">When you try to save this expression in the ER formula designer, the following exception is thrown: "Validation error: The list expression of FILTER function is not queryable."</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff536-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ff536-127">Additional resources</span></span>

[<span data-ttu-id="ff536-128">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="ff536-128">List functions</span></span>](er-functions-category-list.md)
