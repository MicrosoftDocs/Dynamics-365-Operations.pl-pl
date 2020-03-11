---
title: WHERE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji WHERE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 392cf7acebd7ad95bcc0f5d4b7a67500a412a795
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041844"
---
# <span data-ttu-id="77577-103"><a name="WHERE">WHERE, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="77577-103"><a name="WHERE">WHERE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="77577-104">Funkcja `WHERE` zwraca określoną listę jako wartość typu *Lista rekordów* po jej odfiltrowaniu zgodnie z określonym warunkiem.</span><span class="sxs-lookup"><span data-stu-id="77577-104">The `WHERE` function returns the specified list as a *Record list* value after it has been filtered according to the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="77577-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="77577-105">Syntax</span></span>

```vb
WHERE (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="77577-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="77577-106">Arguments</span></span>

<span data-ttu-id="77577-107">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="77577-107">`list`: *Record list*</span></span>

<span data-ttu-id="77577-108">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="77577-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="77577-109">`condition`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="77577-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="77577-110">Prawidłowe wyrażenie warunkowe, które jest używane do filtrowania rekordów z określonej listy.</span><span class="sxs-lookup"><span data-stu-id="77577-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="77577-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="77577-111">Return values</span></span>

<span data-ttu-id="77577-112">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="77577-112">*Record list*</span></span>

<span data-ttu-id="77577-113">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="77577-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="77577-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="77577-114">Usage notes</span></span>

<span data-ttu-id="77577-115">Ta funkcja różni się od funkcji [FILTER](er-functions-list-filter.md), ponieważ podany warunek jest stosowany do każdego źródła danych modułu Raportowanie elektroniczne (ER) o typie *Lista rekordów* obecnym w pamięci.</span><span class="sxs-lookup"><span data-stu-id="77577-115">This function differs from the [FILTER](er-functions-list-filter.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="77577-116">Jeśli argumenty skonfigurowane dla tej funkcji (`list` i `condition`) zezwalają na przetłumaczenie tego żądania na bezpośrednie wywołanie SQL, w czasie projektowania jest wyświetlany komunikat ostrzegawczy.</span><span class="sxs-lookup"><span data-stu-id="77577-116">If the arguments that are configured for this function (`list` and `condition`) allow this request to be translated to the direct SQL call, a warning message is thrown at design time.</span></span> <span data-ttu-id="77577-117">Ten komunikat informuje użytkownika, że wydajność może się zwiększyć, jeśli funkcja [FILTER](er-functions-list-filter.md) będzie używana zamiast funkcji `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="77577-117">This message informs the user that performance might be improved if the [FILTER](er-functions-list-filter.md) function is used instead of `WHERE`.</span></span>

## <a name="example-1"></a><span data-ttu-id="77577-118">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="77577-118">Example 1</span></span>

<span data-ttu-id="77577-119">Jeśli element **Vendor** został skonfigurowany jako źródło danych ER odwołujące się do tabeli VendTable, wyrażenie `WHERE (Vendors, Vendors.VendGroup = "40")` zwraca listę wyłącznie dostawców należących do grupy dostawców 40.</span><span class="sxs-lookup"><span data-stu-id="77577-119">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `WHERE (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="77577-120">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="77577-120">Example 2</span></span>

<span data-ttu-id="77577-121">Po wprowadzeniu źródła danych **DS** typu *Pole obliczeniowe* zawierającego wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `WHERE( DS, DS.Value = "B")` zwraca listę z tylko jednym rekordem, który zawiera tekst **„B”** w polu **Wartość**.</span><span class="sxs-lookup"><span data-stu-id="77577-121">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `WHERE( DS, DS.Value = "B")` returns a list of only one record that contains the text **"B"** in the **Value** field.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="77577-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="77577-122">Additional resources</span></span>

[<span data-ttu-id="77577-123">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="77577-123">List functions</span></span>](er-functions-category-list.md)
