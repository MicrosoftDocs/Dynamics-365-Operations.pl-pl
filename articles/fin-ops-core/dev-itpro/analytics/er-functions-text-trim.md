---
title: TRIM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TRIM w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: c95663f1aacaf93c1c4bfc8d36d9515f495bf61e
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040832"
---
# <span data-ttu-id="83666-103"><a name="TRIM">TRIM, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="83666-103"><a name="TRIM">TRIM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83666-104">Funkcja `TRIM` zwraca określony ciąg tekstowy jako wartość typu *Ciąg* po obcięciu spacji wiodących i końcowych oraz usunięciu spacji wielokrotnych spomiędzy wyrazów.</span><span class="sxs-lookup"><span data-stu-id="83666-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="83666-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="83666-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="83666-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="83666-106">Arguments</span></span>

<span data-ttu-id="83666-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="83666-107">`text`: *String*</span></span>

<span data-ttu-id="83666-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="83666-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="83666-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="83666-109">Return values</span></span>

<span data-ttu-id="83666-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="83666-110">*String*</span></span>

<span data-ttu-id="83666-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="83666-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="83666-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="83666-112">Example</span></span>

<span data-ttu-id="83666-113">Funkcja `TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` zwraca **"Sample text"**.</span><span class="sxs-lookup"><span data-stu-id="83666-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="83666-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="83666-114">Additional resources</span></span>

[<span data-ttu-id="83666-115">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="83666-115">Text functions</span></span>](er-functions-category-text.md)
