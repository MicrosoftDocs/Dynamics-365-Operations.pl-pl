---
title: STRINGJOIN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji STRINGJOIN w module Raportowanie elektroniczne (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 586dbcb98d237325188f4b0384580613ab7a9347
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683749"
---
# <a name="stringjoin-er-function"></a><span data-ttu-id="cf407-103">STRINGJOIN, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="cf407-103">STRINGJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cf407-104">Funkcja `STRINGJOIN` zwraca wartość typu *Ciąg* zawierającą połączone wartości z określonego pola na wybranej liście.</span><span class="sxs-lookup"><span data-stu-id="cf407-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="cf407-105">Wartości mogą być rozdzielone wybranym separatorem.</span><span class="sxs-lookup"><span data-stu-id="cf407-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf407-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="cf407-106">Syntax</span></span>

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="cf407-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="cf407-107">Arguments</span></span>

<span data-ttu-id="cf407-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="cf407-108">`list`: *Record list*</span></span>

<span data-ttu-id="cf407-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="cf407-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="cf407-110">`field`: *Pole*</span><span class="sxs-lookup"><span data-stu-id="cf407-110">`field`: *Field*</span></span>

<span data-ttu-id="cf407-111">Prawidłowa ścieżka pola typu *Ciąg* na określonej liście.</span><span class="sxs-lookup"><span data-stu-id="cf407-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="cf407-112">`delimiter`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="cf407-112">`delimiter`: *String*</span></span>

<span data-ttu-id="cf407-113">Ogranicznik, który jest używany do dzielenia podciągów.</span><span class="sxs-lookup"><span data-stu-id="cf407-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="cf407-114">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="cf407-114">Return values</span></span>

<span data-ttu-id="cf407-115">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="cf407-115">*String*</span></span>

<span data-ttu-id="cf407-116">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="cf407-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="cf407-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="cf407-117">Example</span></span>

<span data-ttu-id="cf407-118">Jeśli wprowadzisz `SPLIT("abc" , 1)` jako źródło danych **DS**, wyrażenie `STRINGJOIN (DS, DS.Value, "-")` zwraca wartość **"a-b-c"**.</span><span class="sxs-lookup"><span data-stu-id="cf407-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cf407-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cf407-119">Additional resources</span></span>

[<span data-ttu-id="cf407-120">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="cf407-120">List functions</span></span>](er-functions-category-list.md)
