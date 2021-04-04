---
title: NUMBERVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMBERVALUE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: f542621c4bcc29e03d8c92b0c700e2c80c9846f6
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561429"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="5eb61-103">NUMBERVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="5eb61-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5eb61-104">Funkcja `NUMBERVALUE` zwraca wartość *rzeczywistą*, która jest konwertowana z określonej wartości typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="5eb61-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="5eb61-105">Podczas konwersji są uwzględniane wybrane separatory dziesiętne i separatory grupowania cyfr.</span><span class="sxs-lookup"><span data-stu-id="5eb61-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="5eb61-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="5eb61-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="5eb61-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="5eb61-107">Arguments</span></span>

<span data-ttu-id="5eb61-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="5eb61-108">`text`: *String*</span></span>

<span data-ttu-id="5eb61-109">Wartość tekstowa, która musi zostać przekonwertowana na liczbę *rzeczywistą*.</span><span class="sxs-lookup"><span data-stu-id="5eb61-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="5eb61-110">`decimal separator`: Ciąg</span><span class="sxs-lookup"><span data-stu-id="5eb61-110">`decimal separator`: String</span></span>

<span data-ttu-id="5eb61-111">Separator dziesiętny.</span><span class="sxs-lookup"><span data-stu-id="5eb61-111">A decimal separator.</span></span> <span data-ttu-id="5eb61-112">Służy do oddzielania całkowitych i ułamkowych części liczby dziesiętnej.</span><span class="sxs-lookup"><span data-stu-id="5eb61-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="5eb61-113">`digit grouping separator`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="5eb61-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="5eb61-114">Separator grupowania cyfr.</span><span class="sxs-lookup"><span data-stu-id="5eb61-114">A digit grouping separator.</span></span> <span data-ttu-id="5eb61-115">Jest używany jako separator tysięcy.</span><span class="sxs-lookup"><span data-stu-id="5eb61-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="5eb61-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="5eb61-116">Return values</span></span>

<span data-ttu-id="5eb61-117">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="5eb61-117">*Real*</span></span>

<span data-ttu-id="5eb61-118">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="5eb61-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="5eb61-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="5eb61-119">Example</span></span>

<span data-ttu-id="5eb61-120">Funkcja `NUMBERVALUE( "1 234,56", ",", " ")` zwraca wartość **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5eb61-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5eb61-121">Additional resources</span></span>

[<span data-ttu-id="5eb61-122">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="5eb61-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]