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
ms.openlocfilehash: 672abf4938df7d96c0190bfd5325689b381e2764
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744342"
---
# <a name="upper-er-function"></a><span data-ttu-id="1f0d0-103">UPPER, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="1f0d0-103">UPPER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f0d0-104">Funkcja `UPPER` zwraca określony ciąg tekstowy jako wartość *Ciąg* po przekonwertowaniu go na duże litery.</span><span class="sxs-lookup"><span data-stu-id="1f0d0-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="1f0d0-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="1f0d0-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="1f0d0-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="1f0d0-106">Arguments</span></span>

<span data-ttu-id="1f0d0-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="1f0d0-107">`text`: *String*</span></span>

<span data-ttu-id="1f0d0-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="1f0d0-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="1f0d0-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="1f0d0-109">Return values</span></span>

<span data-ttu-id="1f0d0-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="1f0d0-110">*String*</span></span>

<span data-ttu-id="1f0d0-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="1f0d0-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="1f0d0-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="1f0d0-112">Example</span></span>

<span data-ttu-id="1f0d0-113">Funkcja `UPPER ("Sample")` zwraca **"SAMPLE"**.</span><span class="sxs-lookup"><span data-stu-id="1f0d0-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1f0d0-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1f0d0-114">Additional resources</span></span>

[<span data-ttu-id="1f0d0-115">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="1f0d0-115">Text functions</span></span>](er-functions-category-text.md)
