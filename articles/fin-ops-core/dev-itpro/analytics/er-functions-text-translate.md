---
title: TRANSLATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TRANSLATE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 07fe19c5f66c33e336f76f3a72d3bbda0c7e8d86
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040924"
---
# <span data-ttu-id="6a3c6-103"><a name="TRANSLATE">TRANSLATE, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="6a3c6-103"><a name="TRANSLATE">TRANSLATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6a3c6-104">Funkcja `TRANSLATE` zwraca określony ciąg tekstowy jako wartość *ciągu* po zastąpieniu go w całości lub częściowo innym ciągiem.</span><span class="sxs-lookup"><span data-stu-id="6a3c6-104">The `TRANSLATE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a3c6-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="6a3c6-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="6a3c6-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="6a3c6-106">Arguments</span></span>

<span data-ttu-id="6a3c6-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6a3c6-107">`text`: *String*</span></span>

<span data-ttu-id="6a3c6-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="6a3c6-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="6a3c6-109">`pattern`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6a3c6-109">`pattern`: *String*</span></span>

<span data-ttu-id="6a3c6-110">Tekst, który musi zostać zastąpiony.</span><span class="sxs-lookup"><span data-stu-id="6a3c6-110">The text that must be replaced.</span></span>

<span data-ttu-id="6a3c6-111">`replacement`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6a3c6-111">`replacement`: *String*</span></span>

<span data-ttu-id="6a3c6-112">Tekst używany jako zastępczy.</span><span class="sxs-lookup"><span data-stu-id="6a3c6-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="6a3c6-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="6a3c6-113">Return values</span></span>

<span data-ttu-id="6a3c6-114">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6a3c6-114">*String*</span></span>

<span data-ttu-id="6a3c6-115">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="6a3c6-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="6a3c6-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="6a3c6-116">Example</span></span>

<span data-ttu-id="6a3c6-117">Funkcja `TRANSLATE ("abcdef", "cd", "GH")` zastępuje wzorzec **"cd"** ciągiem **"GH"** i zwraca wartość **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="6a3c6-117">`TRANSLATE ("abcdef", "cd", "GH")` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a3c6-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6a3c6-118">Additional resources</span></span>

[<span data-ttu-id="6a3c6-119">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="6a3c6-119">Text functions</span></span>](er-functions-category-text.md)
