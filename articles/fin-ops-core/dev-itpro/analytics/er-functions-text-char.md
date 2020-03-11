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
ms.openlocfilehash: 7813b0c6002e47aef6a8c119c72728a49584401b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041242"
---
# <span data-ttu-id="57340-103"><a name="CHAR">CHAR, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="57340-103"><a name="CHAR">CHAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57340-104">Funkcja `CHAR` zwraca wartość typu *Ciąg*, która przedstawia pojedynczy znak, do którego odwołuje się określony numer Unicode.</span><span class="sxs-lookup"><span data-stu-id="57340-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="57340-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="57340-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="57340-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="57340-106">Arguments</span></span>

<span data-ttu-id="57340-107">`number`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="57340-107">`number`: *Integer*</span></span>

<span data-ttu-id="57340-108">Liczba odpowiadająca oczekiwanemu pojedynczemu znakowi.</span><span class="sxs-lookup"><span data-stu-id="57340-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="57340-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="57340-109">Return values</span></span>

<span data-ttu-id="57340-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="57340-110">*String*</span></span>

<span data-ttu-id="57340-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="57340-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="57340-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="57340-112">Usage notes</span></span>

<span data-ttu-id="57340-113">Ciąg zwrócony przez funkcję zależy od kodowania wybranego w nadrzędnym elemencie formatu **PLIK**.</span><span class="sxs-lookup"><span data-stu-id="57340-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="57340-114">Lista obsługiwanych kodowań znajduje się w temacie [Klasa Encoding](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="57340-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="57340-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="57340-115">Example</span></span>

<span data-ttu-id="57340-116">Funkcja `CHAR (255)` zwraca **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="57340-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="57340-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="57340-117">Additional resources</span></span>

[<span data-ttu-id="57340-118">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="57340-118">Text functions</span></span>](er-functions-category-text.md)
