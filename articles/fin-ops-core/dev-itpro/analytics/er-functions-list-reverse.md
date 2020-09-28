---
title: REVERSE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji REVERSE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: ab953136b7500665bdb13e6ff585e3b76896c9ee
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744992"
---
# <a name="reverse-er-function"></a><span data-ttu-id="27867-103">REVERSE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="27867-103">REVERSE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27867-104">Funkcja `REVERSE` zwraca określoną listę jako wartość *Lista rekordów* w odwróconej kolejności sortowania.</span><span class="sxs-lookup"><span data-stu-id="27867-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="27867-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="27867-105">Syntax</span></span>

```vb
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="27867-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="27867-106">Arguments</span></span>

<span data-ttu-id="27867-107">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="27867-107">`list`: *Record list*</span></span>

<span data-ttu-id="27867-108">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="27867-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="27867-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="27867-109">Return values</span></span>

<span data-ttu-id="27867-110">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="27867-110">*Record list*</span></span>

<span data-ttu-id="27867-111">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="27867-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="27867-112">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="27867-112">Example 1</span></span>

<span data-ttu-id="27867-113">Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("C|B|A", "|")`, wyrażenie `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` zwraca wartość tekstową **„C”**.</span><span class="sxs-lookup"><span data-stu-id="27867-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="27867-114">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="27867-114">Example 2</span></span>

<span data-ttu-id="27867-115">Jeśli opcja **Vendor** jest skonfigurowana jako źródło danych raportowania elektronicznego odwołujące się do tabeli VendTable, wyrażenie `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` zwraca listę dostawców posortowaną według nazw w porządku malejącym.</span><span class="sxs-lookup"><span data-stu-id="27867-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="27867-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="27867-116">Additional resources</span></span>

[<span data-ttu-id="27867-117">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="27867-117">List functions</span></span>](er-functions-category-list.md)
