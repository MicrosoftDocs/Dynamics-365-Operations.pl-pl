---
title: UPPER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji UPPER w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 77854d645ba5b65a2819437af510fcd67be6d99d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040947"
---
# <span data-ttu-id="e06f2-103"><a name="UPPER">UPPER, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="e06f2-103"><a name="UPPER">UPPER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e06f2-104">Funkcja `UPPER` zwraca określony ciąg tekstowy jako wartość *Ciąg* po przekonwertowaniu go na duże litery.</span><span class="sxs-lookup"><span data-stu-id="e06f2-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="e06f2-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="e06f2-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="e06f2-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="e06f2-106">Arguments</span></span>

<span data-ttu-id="e06f2-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e06f2-107">`text`: *String*</span></span>

<span data-ttu-id="e06f2-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="e06f2-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="e06f2-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="e06f2-109">Return values</span></span>

<span data-ttu-id="e06f2-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="e06f2-110">*String*</span></span>

<span data-ttu-id="e06f2-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="e06f2-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="e06f2-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="e06f2-112">Example</span></span>

<span data-ttu-id="e06f2-113">Funkcja `UPPER ("Sample")` zwraca **"SAMPLE"**.</span><span class="sxs-lookup"><span data-stu-id="e06f2-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e06f2-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e06f2-114">Additional resources</span></span>

[<span data-ttu-id="e06f2-115">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="e06f2-115">Text functions</span></span>](er-functions-category-text.md)
