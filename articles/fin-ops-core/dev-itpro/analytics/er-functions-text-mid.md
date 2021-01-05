---
title: MID, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji MID w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 1d8a7d2e9beb0fc8724d26de0acaf1d61e3834c6
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680297"
---
# <a name="mid-er-function"></a><span data-ttu-id="bb676-103">MID, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="bb676-103">MID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bb676-104">Funkcja `MID` zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków określonego ciągu od określonego położenia.</span><span class="sxs-lookup"><span data-stu-id="bb676-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb676-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="bb676-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="bb676-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="bb676-106">Arguments</span></span>

<span data-ttu-id="bb676-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="bb676-107">`text`: *String*</span></span>

<span data-ttu-id="bb676-108">Wartość typu *Ciąg*, która określa tekst do zwracania znaków.</span><span class="sxs-lookup"><span data-stu-id="bb676-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="bb676-109">`starting position`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="bb676-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="bb676-110">Wartość typu *Liczba całkowita*, która określa położenie pierwszego znaku, który musi zostać zwrócony z określonego tekstu.</span><span class="sxs-lookup"><span data-stu-id="bb676-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="bb676-111">`number of characters`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="bb676-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="bb676-112">Wartość typu *Liczba całkowita*, która określa liczbę znaków, które muszą zostać zwrócone, rozpoczynając od określonej pozycji początkowej.</span><span class="sxs-lookup"><span data-stu-id="bb676-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="bb676-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="bb676-113">Return values</span></span>

<span data-ttu-id="bb676-114">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="bb676-114">*String*</span></span>

<span data-ttu-id="bb676-115">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="bb676-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bb676-116">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="bb676-116">Usage notes</span></span>

<span data-ttu-id="bb676-117">Jeśli wartość argumentu `starting position` jest mniejsza niż 0 (zero), zwracane znaki są liczone od pierwszej pozycji w określonym ciągu.</span><span class="sxs-lookup"><span data-stu-id="bb676-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="bb676-118">Jeśli wartość argumentu `starting position` przekracza długość określonego ciągu, zwracany jest pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="bb676-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="bb676-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="bb676-119">Example</span></span>

<span data-ttu-id="bb676-120">Funkcja `MID ("Sample", 2, 3)` zwraca wartość **„amp”**.</span><span class="sxs-lookup"><span data-stu-id="bb676-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bb676-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="bb676-121">Additional resources</span></span>

[<span data-ttu-id="bb676-122">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="bb676-122">Text functions</span></span>](er-functions-category-text.md)
