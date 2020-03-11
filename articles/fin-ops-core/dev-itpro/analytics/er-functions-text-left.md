---
title: LEFT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LEFT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 4293db244d04debf3679cf2bde0b892bd74e8ead
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041131"
---
# <span data-ttu-id="ffb09-103"><a name="LEFT">LEFT, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="ffb09-103"><a name="LEFT">LEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ffb09-104">Funkcja `LEFT` zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków od początku określonego ciągu.</span><span class="sxs-lookup"><span data-stu-id="ffb09-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="ffb09-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ffb09-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="ffb09-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ffb09-106">Arguments</span></span>

<span data-ttu-id="ffb09-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ffb09-107">`text`: *String*</span></span>

<span data-ttu-id="ffb09-108">Wartość *ciągu* reprezentująca oryginalny tekst.</span><span class="sxs-lookup"><span data-stu-id="ffb09-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="ffb09-109">`number`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="ffb09-109">`number`: *Integer*</span></span>

<span data-ttu-id="ffb09-110">Liczba znaków, które muszą zostać zwrócone, od początku oryginalnego tekstu.</span><span class="sxs-lookup"><span data-stu-id="ffb09-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="ffb09-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="ffb09-111">Return values</span></span>

<span data-ttu-id="ffb09-112">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ffb09-112">*String*</span></span>

<span data-ttu-id="ffb09-113">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="ffb09-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ffb09-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="ffb09-114">Example</span></span>

<span data-ttu-id="ffb09-115">Funkcja `LEFT ("Sample", 3)` zwraca **"Sam"**.</span><span class="sxs-lookup"><span data-stu-id="ffb09-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ffb09-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ffb09-116">Additional resources</span></span>

[<span data-ttu-id="ffb09-117">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="ffb09-117">Text functions</span></span>](er-functions-category-text.md)
