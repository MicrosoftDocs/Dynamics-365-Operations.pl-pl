---
title: EMPTYLIST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji EMPTYLIST w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 5fb991eb9ee08aeb418313eb782dbde7fa22b763
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042189"
---
# <span data-ttu-id="aebd1-103"><a name="EMPTYLIST">EMPTYLIST, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="aebd1-103"><a name="EMPTYLIST">EMPTYLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aebd1-104">Funkcja `EMPTYLIST` zwraca pustą wartość typu *Lista rekordów* przez użycie określonej listy jako źródła dla struktury listy.</span><span class="sxs-lookup"><span data-stu-id="aebd1-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="aebd1-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="aebd1-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="aebd1-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="aebd1-106">Arguments</span></span>

<span data-ttu-id="aebd1-107">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="aebd1-107">`list`: *Record list*</span></span>

<span data-ttu-id="aebd1-108">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="aebd1-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="aebd1-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="aebd1-109">Return values</span></span>

<span data-ttu-id="aebd1-110">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="aebd1-110">*Record list*</span></span>

<span data-ttu-id="aebd1-111">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="aebd1-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="aebd1-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="aebd1-112">Example</span></span>

<span data-ttu-id="aebd1-113">Funkcja `EMPTYLIST (SPLIT ("abc", 1))` zwraca nową pustą listę, która ma taką samą strukturę jak lista zwracana przez używaną funkcję `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="aebd1-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aebd1-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="aebd1-114">Additional resources</span></span>

[<span data-ttu-id="aebd1-115">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="aebd1-115">List functions</span></span>](er-functions-category-list.md)
