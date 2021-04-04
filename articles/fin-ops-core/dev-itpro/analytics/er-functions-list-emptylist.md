---
title: EMPTYLIST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji EMPTYLIST w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f6c2777065656affc992a427194286008c1df42f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559207"
---
# <a name="emptylist-er-function"></a><span data-ttu-id="be3da-103">EMPTYLIST, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="be3da-103">EMPTYLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="be3da-104">Funkcja `EMPTYLIST` zwraca pustą wartość typu *Lista rekordów* przez użycie określonej listy jako źródła dla struktury listy.</span><span class="sxs-lookup"><span data-stu-id="be3da-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="be3da-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="be3da-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="be3da-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="be3da-106">Arguments</span></span>

<span data-ttu-id="be3da-107">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="be3da-107">`list`: *Record list*</span></span>

<span data-ttu-id="be3da-108">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="be3da-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="be3da-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="be3da-109">Return values</span></span>

<span data-ttu-id="be3da-110">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="be3da-110">*Record list*</span></span>

<span data-ttu-id="be3da-111">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="be3da-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="be3da-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="be3da-112">Example</span></span>

<span data-ttu-id="be3da-113">Funkcja `EMPTYLIST (SPLIT ("abc", 1))` zwraca nową pustą listę, która ma taką samą strukturę jak lista zwracana przez używaną funkcję `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="be3da-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be3da-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="be3da-114">Additional resources</span></span>

[<span data-ttu-id="be3da-115">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="be3da-115">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]