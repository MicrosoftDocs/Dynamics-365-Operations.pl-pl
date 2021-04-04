---
title: ISEMPTY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISEMPTY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: b689e6d4bb849f07db5d00cf8a9dc5c16646a927
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563879"
---
# <a name="isempty-er-function"></a><span data-ttu-id="625d0-103">ISEMPTY, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="625d0-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="625d0-104">Funkcja `ISEMPTY` zwraca wartość *logiczną* **TRUE**, jeśli określona lista nie zawiera żadnych rekordów.</span><span class="sxs-lookup"><span data-stu-id="625d0-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="625d0-105">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="625d0-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="625d0-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="625d0-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="625d0-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="625d0-107">Arguments</span></span>

<span data-ttu-id="625d0-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="625d0-108">`list`: *Record list*</span></span>

<span data-ttu-id="625d0-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="625d0-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="625d0-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="625d0-110">Return values</span></span>

<span data-ttu-id="625d0-111">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="625d0-111">*Boolean*</span></span>

<span data-ttu-id="625d0-112">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="625d0-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="625d0-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="625d0-113">Example 1</span></span>

<span data-ttu-id="625d0-114">Jeśli wprowadzisz źródło danych **DS** typu *Pole obliczeniowe* i zawiera ono wyrażenie `SPLIT ("A|B|C", "|")`, wyrażenie `ISEMPTY(DS)` zwraca wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="625d0-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="625d0-115">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="625d0-115">Example 2</span></span>

<span data-ttu-id="625d0-116">Wyrażenie `ISEMPTY (SPLIT ("",1))` zwraca wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="625d0-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="625d0-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="625d0-117">Additional resources</span></span>

[<span data-ttu-id="625d0-118">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="625d0-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]