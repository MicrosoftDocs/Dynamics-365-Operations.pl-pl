---
title: CHAR, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CHAR w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: a621328817171be7df0622507c84f5c6f6fe90a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746442"
---
# <a name="char-er-function"></a><span data-ttu-id="cf3c3-103">CHAR, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="cf3c3-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cf3c3-104">Funkcja `CHAR` zwraca wartość typu *Ciąg*, która przedstawia pojedynczy znak, do którego odwołuje się określony numer Unicode.</span><span class="sxs-lookup"><span data-stu-id="cf3c3-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf3c3-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="cf3c3-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="cf3c3-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="cf3c3-106">Arguments</span></span>

<span data-ttu-id="cf3c3-107">`number`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="cf3c3-107">`number`: *Integer*</span></span>

<span data-ttu-id="cf3c3-108">Liczba odpowiadająca oczekiwanemu pojedynczemu znakowi.</span><span class="sxs-lookup"><span data-stu-id="cf3c3-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="cf3c3-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="cf3c3-109">Return values</span></span>

<span data-ttu-id="cf3c3-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="cf3c3-110">*String*</span></span>

<span data-ttu-id="cf3c3-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="cf3c3-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cf3c3-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="cf3c3-112">Usage notes</span></span>

<span data-ttu-id="cf3c3-113">Ciąg zwrócony przez funkcję zależy od kodowania wybranego w nadrzędnym elemencie formatu **PLIK**.</span><span class="sxs-lookup"><span data-stu-id="cf3c3-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="cf3c3-114">Lista obsługiwanych kodowań znajduje się w temacie [Klasa Encoding](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="cf3c3-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="cf3c3-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="cf3c3-115">Example</span></span>

<span data-ttu-id="cf3c3-116">Funkcja `CHAR (255)` zwraca **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="cf3c3-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cf3c3-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cf3c3-117">Additional resources</span></span>

[<span data-ttu-id="cf3c3-118">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="cf3c3-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]