---
title: LEFT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LEFT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 6f1ec7a21a16c3a34bed9779b05f20f21815ab9d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569999"
---
# <a name="left-er-function"></a><span data-ttu-id="2011d-103">LEFT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="2011d-103">LEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2011d-104">Funkcja `LEFT` zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków od początku określonego ciągu.</span><span class="sxs-lookup"><span data-stu-id="2011d-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="2011d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2011d-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="2011d-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="2011d-106">Arguments</span></span>

<span data-ttu-id="2011d-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="2011d-107">`text`: *String*</span></span>

<span data-ttu-id="2011d-108">Wartość *ciągu* reprezentująca oryginalny tekst.</span><span class="sxs-lookup"><span data-stu-id="2011d-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="2011d-109">`number`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="2011d-109">`number`: *Integer*</span></span>

<span data-ttu-id="2011d-110">Liczba znaków, które muszą zostać zwrócone, od początku oryginalnego tekstu.</span><span class="sxs-lookup"><span data-stu-id="2011d-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="2011d-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="2011d-111">Return values</span></span>

<span data-ttu-id="2011d-112">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="2011d-112">*String*</span></span>

<span data-ttu-id="2011d-113">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="2011d-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="2011d-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="2011d-114">Example</span></span>

<span data-ttu-id="2011d-115">Funkcja `LEFT ("Sample", 3)` zwraca **"Sam"**.</span><span class="sxs-lookup"><span data-stu-id="2011d-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2011d-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2011d-116">Additional resources</span></span>

[<span data-ttu-id="2011d-117">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="2011d-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]