---
title: TRIM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TRIM w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: b671ef72a3558c17fb16db939770394b225656da
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560044"
---
# <a name="trim-er-function"></a><span data-ttu-id="3c9cb-103">TRIM, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="3c9cb-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3c9cb-104">Funkcja `TRIM` zwraca określony ciąg tekstowy jako wartość typu *Ciąg* po obcięciu spacji wiodących i końcowych oraz usunięciu spacji wielokrotnych spomiędzy wyrazów.</span><span class="sxs-lookup"><span data-stu-id="3c9cb-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c9cb-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="3c9cb-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="3c9cb-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="3c9cb-106">Arguments</span></span>

<span data-ttu-id="3c9cb-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="3c9cb-107">`text`: *String*</span></span>

<span data-ttu-id="3c9cb-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="3c9cb-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="3c9cb-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="3c9cb-109">Return values</span></span>

<span data-ttu-id="3c9cb-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="3c9cb-110">*String*</span></span>

<span data-ttu-id="3c9cb-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="3c9cb-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="3c9cb-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="3c9cb-112">Example</span></span>

<span data-ttu-id="3c9cb-113">Funkcja `TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` zwraca **"Sample text"**.</span><span class="sxs-lookup"><span data-stu-id="3c9cb-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3c9cb-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3c9cb-114">Additional resources</span></span>

[<span data-ttu-id="3c9cb-115">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="3c9cb-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]