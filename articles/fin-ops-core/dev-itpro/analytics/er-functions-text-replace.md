---
title: Funkcja ER REPLACE
description: Ten temat zawiera ogólne informacje o używaniu funkcji REPLACE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 3c9d3b6748ecb1680586a2d47a425b5ef98551f1
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682927"
---
# <a name="replace-er-function"></a><span data-ttu-id="64e1a-103">Funkcja ER REPLACE</span><span class="sxs-lookup"><span data-stu-id="64e1a-103">REPLACE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64e1a-104">Funkcja `REPLACE` zwraca określony ciąg tekstowy jako wartość *ciągu* po zastąpieniu go w całości lub częściowo innym ciągiem.</span><span class="sxs-lookup"><span data-stu-id="64e1a-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="64e1a-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="64e1a-105">Syntax</span></span>

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="64e1a-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="64e1a-106">Arguments</span></span>

<span data-ttu-id="64e1a-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="64e1a-107">`text`: *String*</span></span>

<span data-ttu-id="64e1a-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="64e1a-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="64e1a-109">`pattern`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="64e1a-109">`pattern`: *String*</span></span>

<span data-ttu-id="64e1a-110">Jeśli argument `regular expression flag` ma wartość **FALSE**, ten argument zawiera tekst, który musi zostać zastąpiony.</span><span class="sxs-lookup"><span data-stu-id="64e1a-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="64e1a-111">Jeśli argument `regular expression flag` ma wartość **TRUE**, ten argument zawiera wyrażenie regularne definiujące zarówno wzorzec wyszukiwania, jak i tekst zastępczy.</span><span class="sxs-lookup"><span data-stu-id="64e1a-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="64e1a-112">`replacement`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="64e1a-112">`replacement`: *String*</span></span>

<span data-ttu-id="64e1a-113">Jeśli argument `regular expression flag` ma wartość **FALSE**, ten argument zawiera tekst do użycia jako zastępczy</span><span class="sxs-lookup"><span data-stu-id="64e1a-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="64e1a-114">Jeśli argument `regular expression flag` ma wartość **TRUE**, ten argument nie jest używany.</span><span class="sxs-lookup"><span data-stu-id="64e1a-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="64e1a-115">`regular expression flag`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="64e1a-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="64e1a-116">*Wartość logiczna* wskazująca, czy wyrażenie regularne jest używane do zastępowania.</span><span class="sxs-lookup"><span data-stu-id="64e1a-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="64e1a-117">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="64e1a-117">Return values</span></span>

<span data-ttu-id="64e1a-118">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="64e1a-118">*String*</span></span>

<span data-ttu-id="64e1a-119">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="64e1a-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="64e1a-120">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="64e1a-120">Usage notes</span></span>

<span data-ttu-id="64e1a-121">Jeśli argument `regular expression flag` ma wartość **TRUE**, ta funkcja zwraca określony ciąg po zmianie przez zastosowanie wyrażenia regularnego, które zostało określone przez argument `pattern`.</span><span class="sxs-lookup"><span data-stu-id="64e1a-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="64e1a-122">Wyrażenie regularne służy do znajdowania znaków, które należy zastąpić.</span><span class="sxs-lookup"><span data-stu-id="64e1a-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="64e1a-123">Jeśli argument `regular expression flag` ma wartość **FAŁSZ**, ta funkcja zwraca określony ciąg po zestawie znaków zdefiniowanych w argumencie `pattern` , który został zastąpiony znakami argumentu `replacement`.</span><span class="sxs-lookup"><span data-stu-id="64e1a-123">If the `regular expression flag` argument is **FALSE**, this function returns the specified string after the set of characters that are defined in the `pattern` argument have been replaced by characters of the `replacement` argument.</span></span> 

## <a name="example-1"></a><span data-ttu-id="64e1a-124">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="64e1a-124">Example 1</span></span>

<span data-ttu-id="64e1a-125">Funkcja `REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` stosuje wyrażenie regularne, które usuwa wszystkie symbole nieliczbowe i zwraca **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="64e1a-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="64e1a-126">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="64e1a-126">Example 2</span></span>

<span data-ttu-id="64e1a-127">Funkcja `REPLACE ("abcdef", "cd", "GH", false)` zastępuje wzorzec **"cd"** ciągiem **"GH"** i zwraca wartość **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="64e1a-127">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64e1a-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="64e1a-128">Additional resources</span></span>

[<span data-ttu-id="64e1a-129">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="64e1a-129">Text functions</span></span>](er-functions-category-text.md)
