---
title: COUNT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji COUNT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 2d29b82a8c3b108f7651e6d593cb17e7ec8ca872
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916253"
---
# <span data-ttu-id="64f73-103"><a name="COUNT">COUNT, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="64f73-103"><a name="COUNT">COUNT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64f73-104">Funkcja `COUNT` zwraca wartość typu *Liczba całkowita* reprezentującą liczbę rekordów na określonej liście, jeśli lista nie jest pusta.</span><span class="sxs-lookup"><span data-stu-id="64f73-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="64f73-105">Jeśli lista jest pusta, ta funkcja zwraca wartość **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="64f73-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="64f73-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="64f73-106">Syntax</span></span>

```
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="64f73-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="64f73-107">Arguments</span></span>

<span data-ttu-id="64f73-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="64f73-108">`list`: *Record list*</span></span>

<span data-ttu-id="64f73-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="64f73-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="64f73-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="64f73-110">Return values</span></span>

<span data-ttu-id="64f73-111">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="64f73-111">*Integer*</span></span>

<span data-ttu-id="64f73-112">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="64f73-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="64f73-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="64f73-113">Example</span></span>

<span data-ttu-id="64f73-114">Funkcja `COUNT (SPLIT("abcd" , 3))` zwraca wartość **2**, ponieważ funkcja `SPLIT` używana w tym przykładzie tworzy listę, która składa się z dwóch rekordów.</span><span class="sxs-lookup"><span data-stu-id="64f73-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64f73-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="64f73-115">Additional resources</span></span>

[<span data-ttu-id="64f73-116">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="64f73-116">List functions</span></span>](er-functions-category-list.md)
