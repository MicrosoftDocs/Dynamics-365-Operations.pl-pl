---
title: CHAR, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CHAR w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 63df7b1ac847e12cf429467dd444450552a59162
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744968"
---
# <a name="char-er-function"></a><span data-ttu-id="5b62b-103">CHAR, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="5b62b-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b62b-104">Funkcja `CHAR` zwraca wartość typu *Ciąg*, która przedstawia pojedynczy znak, do którego odwołuje się określony numer Unicode.</span><span class="sxs-lookup"><span data-stu-id="5b62b-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="5b62b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="5b62b-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="5b62b-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="5b62b-106">Arguments</span></span>

<span data-ttu-id="5b62b-107">`number`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="5b62b-107">`number`: *Integer*</span></span>

<span data-ttu-id="5b62b-108">Liczba odpowiadająca oczekiwanemu pojedynczemu znakowi.</span><span class="sxs-lookup"><span data-stu-id="5b62b-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="5b62b-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="5b62b-109">Return values</span></span>

<span data-ttu-id="5b62b-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="5b62b-110">*String*</span></span>

<span data-ttu-id="5b62b-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="5b62b-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5b62b-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="5b62b-112">Usage notes</span></span>

<span data-ttu-id="5b62b-113">Ciąg zwrócony przez funkcję zależy od kodowania wybranego w nadrzędnym elemencie formatu **PLIK**.</span><span class="sxs-lookup"><span data-stu-id="5b62b-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="5b62b-114">Lista obsługiwanych kodowań znajduje się w temacie [Klasa Encoding](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="5b62b-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="5b62b-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="5b62b-115">Example</span></span>

<span data-ttu-id="5b62b-116">Funkcja `CHAR (255)` zwraca **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="5b62b-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b62b-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5b62b-117">Additional resources</span></span>

[<span data-ttu-id="5b62b-118">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="5b62b-118">Text functions</span></span>](er-functions-category-text.md)
