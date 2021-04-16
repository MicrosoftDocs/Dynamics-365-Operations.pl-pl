---
title: STRINGJOIN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji STRINGJOIN w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: ac21651e0f5b5a1579b9335bb7f3217370c4d5a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745528"
---
# <a name="stringjoin-er-function"></a><span data-ttu-id="c5d24-103">STRINGJOIN, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c5d24-103">STRINGJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c5d24-104">Funkcja `STRINGJOIN` zwraca wartość typu *Ciąg* zawierającą połączone wartości z określonego pola na wybranej liście.</span><span class="sxs-lookup"><span data-stu-id="c5d24-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="c5d24-105">Wartości mogą być rozdzielone wybranym separatorem.</span><span class="sxs-lookup"><span data-stu-id="c5d24-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="c5d24-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="c5d24-106">Syntax</span></span>

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="c5d24-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c5d24-107">Arguments</span></span>

<span data-ttu-id="c5d24-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="c5d24-108">`list`: *Record list*</span></span>

<span data-ttu-id="c5d24-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="c5d24-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="c5d24-110">`field`: *Pole*</span><span class="sxs-lookup"><span data-stu-id="c5d24-110">`field`: *Field*</span></span>

<span data-ttu-id="c5d24-111">Prawidłowa ścieżka pola typu *Ciąg* na określonej liście.</span><span class="sxs-lookup"><span data-stu-id="c5d24-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="c5d24-112">`delimiter`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c5d24-112">`delimiter`: *String*</span></span>

<span data-ttu-id="c5d24-113">Ogranicznik, który jest używany do dzielenia podciągów.</span><span class="sxs-lookup"><span data-stu-id="c5d24-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="c5d24-114">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c5d24-114">Return values</span></span>

<span data-ttu-id="c5d24-115">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c5d24-115">*String*</span></span>

<span data-ttu-id="c5d24-116">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="c5d24-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c5d24-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="c5d24-117">Example</span></span>

<span data-ttu-id="c5d24-118">Jeśli wprowadzisz `SPLIT("abc" , 1)` jako źródło danych **DS**, wyrażenie `STRINGJOIN (DS, DS.Value, "-")` zwraca wartość **"a-b-c"**.</span><span class="sxs-lookup"><span data-stu-id="c5d24-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c5d24-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c5d24-119">Additional resources</span></span>

[<span data-ttu-id="c5d24-120">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="c5d24-120">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]