---
title: TRANSLATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TRANSLATE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: c5d192b8679d6df2c44a0038fe4ffc181a6a54df
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685310"
---
# <a name="translate-er-function"></a><span data-ttu-id="6a72c-103">TRANSLATE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="6a72c-103">TRANSLATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6a72c-104">Funkcja `TRANSLATE` zwraca wartość typu *Ciąg*, która zawiera wynik zastąpienia znaków określonego tekstu w znakach dla innego dostarczonego zbioru.</span><span class="sxs-lookup"><span data-stu-id="6a72c-104">The `TRANSLATE` function returns a *String* value that contains the result of the character replacement of specified text in characters of another provided set.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a72c-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="6a72c-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="6a72c-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="6a72c-106">Arguments</span></span>

<span data-ttu-id="6a72c-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6a72c-107">`text`: *String*</span></span>

<span data-ttu-id="6a72c-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="6a72c-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="6a72c-109">`pattern`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6a72c-109">`pattern`: *String*</span></span>

<span data-ttu-id="6a72c-110">Tekst, który musi zostać zastąpiony.</span><span class="sxs-lookup"><span data-stu-id="6a72c-110">The text that must be replaced.</span></span>

<span data-ttu-id="6a72c-111">`replacement`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6a72c-111">`replacement`: *String*</span></span>

<span data-ttu-id="6a72c-112">Tekst używany jako zastępczy.</span><span class="sxs-lookup"><span data-stu-id="6a72c-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="6a72c-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="6a72c-113">Return values</span></span>

<span data-ttu-id="6a72c-114">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6a72c-114">*String*</span></span>

<span data-ttu-id="6a72c-115">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="6a72c-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6a72c-116">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="6a72c-116">Usage notes</span></span>

<span data-ttu-id="6a72c-117">Funkcja `TRANSLATE` zastępuje jeden znak na raz.</span><span class="sxs-lookup"><span data-stu-id="6a72c-117">The `TRANSLATE` function replaces one character at a time.</span></span> <span data-ttu-id="6a72c-118">Funkcja zastępuje pierwszy znak argumentu `text` wartością pierwszego znaku argumentu `pattern`, a następnie drugi znak i podąża za tym samym przepływem do zakończenia operacji.</span><span class="sxs-lookup"><span data-stu-id="6a72c-118">The function replaces the first character of the `text` argument with the first character of the `pattern` argument and then the second character and follows the same flow until finished.</span></span> <span data-ttu-id="6a72c-119">Jeśli znak z argumentów `text` i `pattern` jest zgodny, jest on zastępowany znakiem z argumentu `replacement` znajdującego się w tym samym położeniu, co znak z argumentu `pattern`.</span><span class="sxs-lookup"><span data-stu-id="6a72c-119">When a character from the `text` and `pattern` arguments match, it is replaced by a character from the `replacement` argument that is located in the same position as the character from the `pattern` argument.</span></span> <span data-ttu-id="6a72c-120">Jeśli w argumencie `pattern` występuje wiele razy znak, zostanie użyte mapowanie argumentu `replacement` odpowiadające pierwszemu wystąpieniu tego znaku.</span><span class="sxs-lookup"><span data-stu-id="6a72c-120">If a character appears multiple times in the `pattern` argument, the `replacement` argument mapping that corresponds to the first occurrence of this character is used.</span></span>

## <a name="example-1"></a><span data-ttu-id="6a72c-121">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="6a72c-121">Example 1</span></span>

<span data-ttu-id="6a72c-122">`TRANSLATE ("abcdef", "cd", "GH")` zastępuje znak **„c”** określonego tekstu **„abcdef** „ znakiem **„G”** tekstu `replacement`, ze względu na nastepujące:</span><span class="sxs-lookup"><span data-stu-id="6a72c-122">`TRANSLATE ("abcdef", "cd", "GH")` replaces the **"c"** character of the specified  **“abcdef”** text with the **"G"** character of the `replacement` text due to the following:</span></span>
-   <span data-ttu-id="6a72c-123">Znak **„c”** jest przedstawiony w tekście `pattern` na pierwszym miejscu.</span><span class="sxs-lookup"><span data-stu-id="6a72c-123">The **"c"** character is presented in the `pattern` text in the first position.</span></span>
-   <span data-ttu-id="6a72c-124">Pierwsza pozycja tekstu `replacement` zawiera znak **„G”**.</span><span class="sxs-lookup"><span data-stu-id="6a72c-124">The first position of the `replacement` text contains the **"G"** character.</span></span>

## <a name="example-2"></a><span data-ttu-id="6a72c-125">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="6a72c-125">Example 2</span></span>

<span data-ttu-id="6a72c-126">Funkcja `TRANSLATE ("abcdef", "ccd", "GH")` zwraca wartość **"abGdef"**.</span><span class="sxs-lookup"><span data-stu-id="6a72c-126">`TRANSLATE ("abcdef", "ccd", "GH")` returns **"abGdef"**.</span></span>

## <a name="example-3"></a><span data-ttu-id="6a72c-127">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="6a72c-127">Example 3</span></span>

<span data-ttu-id="6a72c-128">Funkcja `TRANSLATE ("abccba", "abc", "123")` zwraca wartość **"123321"**.</span><span class="sxs-lookup"><span data-stu-id="6a72c-128">`TRANSLATE ("abccba", "abc", "123")` returns **"123321"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a72c-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6a72c-129">Additional resources</span></span>

[<span data-ttu-id="6a72c-130">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="6a72c-130">Text functions</span></span>](er-functions-category-text.md)
