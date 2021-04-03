---
title: MID, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji MID w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: e0520bc54465f00d36e88787933b291847dee852
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562740"
---
# <a name="mid-er-function"></a><span data-ttu-id="64fcd-103">MID, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="64fcd-103">MID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64fcd-104">Funkcja `MID` zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków określonego ciągu od określonego położenia.</span><span class="sxs-lookup"><span data-stu-id="64fcd-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="64fcd-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="64fcd-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="64fcd-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="64fcd-106">Arguments</span></span>

<span data-ttu-id="64fcd-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="64fcd-107">`text`: *String*</span></span>

<span data-ttu-id="64fcd-108">Wartość typu *Ciąg*, która określa tekst do zwracania znaków.</span><span class="sxs-lookup"><span data-stu-id="64fcd-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="64fcd-109">`starting position`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="64fcd-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="64fcd-110">Wartość typu *Liczba całkowita*, która określa położenie pierwszego znaku, który musi zostać zwrócony z określonego tekstu.</span><span class="sxs-lookup"><span data-stu-id="64fcd-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="64fcd-111">`number of characters`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="64fcd-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="64fcd-112">Wartość typu *Liczba całkowita*, która określa liczbę znaków, które muszą zostać zwrócone, rozpoczynając od określonej pozycji początkowej.</span><span class="sxs-lookup"><span data-stu-id="64fcd-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="64fcd-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="64fcd-113">Return values</span></span>

<span data-ttu-id="64fcd-114">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="64fcd-114">*String*</span></span>

<span data-ttu-id="64fcd-115">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="64fcd-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="64fcd-116">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="64fcd-116">Usage notes</span></span>

<span data-ttu-id="64fcd-117">Jeśli wartość argumentu `starting position` jest mniejsza niż 0 (zero), zwracane znaki są liczone od pierwszej pozycji w określonym ciągu.</span><span class="sxs-lookup"><span data-stu-id="64fcd-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="64fcd-118">Jeśli wartość argumentu `starting position` przekracza długość określonego ciągu, zwracany jest pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="64fcd-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="64fcd-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="64fcd-119">Example</span></span>

<span data-ttu-id="64fcd-120">Funkcja `MID ("Sample", 2, 3)` zwraca wartość **„amp”**.</span><span class="sxs-lookup"><span data-stu-id="64fcd-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64fcd-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="64fcd-121">Additional resources</span></span>

[<span data-ttu-id="64fcd-122">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="64fcd-122">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]