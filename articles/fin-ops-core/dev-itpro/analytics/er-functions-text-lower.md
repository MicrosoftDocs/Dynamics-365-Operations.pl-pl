---
title: LOWER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LOWER w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: e507a17f5125a3cba0d2434a1aaec0f04f0cd388
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562790"
---
# <a name="lower-er-function"></a><span data-ttu-id="99a96-103">LOWER, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="99a96-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99a96-104">Funkcja `LOWER` zwraca określony ciąg tekstowy jako wartość *Ciąg* po przekonwertowaniu go na małe litery.</span><span class="sxs-lookup"><span data-stu-id="99a96-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="99a96-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="99a96-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="99a96-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="99a96-106">Arguments</span></span>

<span data-ttu-id="99a96-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="99a96-107">`text`: *String*</span></span>

<span data-ttu-id="99a96-108">Wartość typu *Ciąg* określająca tekst.</span><span class="sxs-lookup"><span data-stu-id="99a96-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="99a96-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="99a96-109">Return values</span></span>

<span data-ttu-id="99a96-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="99a96-110">*String*</span></span>

<span data-ttu-id="99a96-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="99a96-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="99a96-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="99a96-112">Example</span></span>

<span data-ttu-id="99a96-113">Funkcja `LOWER ("Sample")` zwraca **"sample"**.</span><span class="sxs-lookup"><span data-stu-id="99a96-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99a96-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="99a96-114">Additional resources</span></span>

[<span data-ttu-id="99a96-115">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="99a96-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]