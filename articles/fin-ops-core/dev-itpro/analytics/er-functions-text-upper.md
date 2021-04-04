---
title: UPPER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji UPPER w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 8fb89ca48c0035e672b2de6820d6ef08d36c02af
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559996"
---
# <a name="upper-er-function"></a><span data-ttu-id="c8582-103">UPPER, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c8582-103">UPPER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8582-104">Funkcja `UPPER` zwraca określony ciąg tekstowy jako wartość *Ciąg* po przekonwertowaniu go na duże litery.</span><span class="sxs-lookup"><span data-stu-id="c8582-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8582-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c8582-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="c8582-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c8582-106">Arguments</span></span>

<span data-ttu-id="c8582-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c8582-107">`text`: *String*</span></span>

<span data-ttu-id="c8582-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="c8582-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c8582-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c8582-109">Return values</span></span>

<span data-ttu-id="c8582-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c8582-110">*String*</span></span>

<span data-ttu-id="c8582-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="c8582-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c8582-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="c8582-112">Example</span></span>

<span data-ttu-id="c8582-113">Funkcja `UPPER ("Sample")` zwraca **"SAMPLE"**.</span><span class="sxs-lookup"><span data-stu-id="c8582-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8582-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c8582-114">Additional resources</span></span>

[<span data-ttu-id="c8582-115">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="c8582-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]