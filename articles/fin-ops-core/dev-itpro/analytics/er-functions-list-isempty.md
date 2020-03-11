---
title: ISEMPTY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISEMPTY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 6adca3c95c10e7d4b3287561925a9d9fe8a74121
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042051"
---
# <span data-ttu-id="944a7-103"><a name="ISEMPTY">ISEMPTY, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="944a7-103"><a name="ISEMPTY">ISEMPTY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="944a7-104">Funkcja `ISEMPTY` zwraca wartość *logiczną* **TRUE**, jeśli określona lista nie zawiera żadnych rekordów.</span><span class="sxs-lookup"><span data-stu-id="944a7-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="944a7-105">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="944a7-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="944a7-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="944a7-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="944a7-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="944a7-107">Arguments</span></span>

<span data-ttu-id="944a7-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="944a7-108">`list`: *Record list*</span></span>

<span data-ttu-id="944a7-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="944a7-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="944a7-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="944a7-110">Return values</span></span>

<span data-ttu-id="944a7-111">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="944a7-111">*Boolean*</span></span>

<span data-ttu-id="944a7-112">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="944a7-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="944a7-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="944a7-113">Example 1</span></span>

<span data-ttu-id="944a7-114">Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `ISEMPTY(DS)` zwraca wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="944a7-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="944a7-115">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="944a7-115">Example 2</span></span>

<span data-ttu-id="944a7-116">Wyrażenie `ISEMPTY (SPLIT ("",1))` zwraca wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="944a7-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="944a7-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="944a7-117">Additional resources</span></span>

[<span data-ttu-id="944a7-118">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="944a7-118">List functions</span></span>](er-functions-category-list.md)
