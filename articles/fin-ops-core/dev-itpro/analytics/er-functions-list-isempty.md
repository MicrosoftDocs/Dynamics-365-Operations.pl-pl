---
title: ISEMPTY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISEMPTY w module Raportowanie elektroniczne (ER).
author: NickSelin
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
ms.openlocfilehash: 9c33e8b613bf5bf5bc17a42a7668d4cc4ee58e53
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750443"
---
# <a name="isempty-er-function"></a><span data-ttu-id="a3c2e-103">ISEMPTY, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="a3c2e-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3c2e-104">Funkcja `ISEMPTY` zwraca wartość *logiczną* **TRUE**, jeśli określona lista nie zawiera żadnych rekordów.</span><span class="sxs-lookup"><span data-stu-id="a3c2e-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="a3c2e-105">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a3c2e-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="a3c2e-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="a3c2e-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="a3c2e-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="a3c2e-107">Arguments</span></span>

<span data-ttu-id="a3c2e-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="a3c2e-108">`list`: *Record list*</span></span>

<span data-ttu-id="a3c2e-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="a3c2e-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a3c2e-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="a3c2e-110">Return values</span></span>

<span data-ttu-id="a3c2e-111">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="a3c2e-111">*Boolean*</span></span>

<span data-ttu-id="a3c2e-112">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="a3c2e-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="a3c2e-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="a3c2e-113">Example 1</span></span>

<span data-ttu-id="a3c2e-114">Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `ISEMPTY(DS)` zwraca wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a3c2e-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="a3c2e-115">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="a3c2e-115">Example 2</span></span>

<span data-ttu-id="a3c2e-116">Wyrażenie `ISEMPTY (SPLIT ("",1))` zwraca wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="a3c2e-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3c2e-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a3c2e-117">Additional resources</span></span>

[<span data-ttu-id="a3c2e-118">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="a3c2e-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]