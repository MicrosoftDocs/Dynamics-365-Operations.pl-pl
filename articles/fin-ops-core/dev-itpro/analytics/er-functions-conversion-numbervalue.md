---
title: NUMBERVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMBERVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 13346c4810d6c93d4ef47ce525831332562c7f51
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743406"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="c12a8-103">NUMBERVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c12a8-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c12a8-104">Funkcja `NUMBERVALUE` zwraca wartość *rzeczywistą*, która jest konwertowana z określonej wartości typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="c12a8-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="c12a8-105">Podczas konwersji są uwzględniane wybrane separatory dziesiętne i separatory grupowania cyfr.</span><span class="sxs-lookup"><span data-stu-id="c12a8-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="c12a8-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="c12a8-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="c12a8-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c12a8-107">Arguments</span></span>

<span data-ttu-id="c12a8-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c12a8-108">`text`: *String*</span></span>

<span data-ttu-id="c12a8-109">Wartość tekstowa, która musi zostać przekonwertowana na liczbę *rzeczywistą*.</span><span class="sxs-lookup"><span data-stu-id="c12a8-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="c12a8-110">`decimal separator`: Ciąg</span><span class="sxs-lookup"><span data-stu-id="c12a8-110">`decimal separator`: String</span></span>

<span data-ttu-id="c12a8-111">Separator dziesiętny.</span><span class="sxs-lookup"><span data-stu-id="c12a8-111">A decimal separator.</span></span> <span data-ttu-id="c12a8-112">Służy do oddzielania całkowitych i ułamkowych części liczby dziesiętnej.</span><span class="sxs-lookup"><span data-stu-id="c12a8-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="c12a8-113">`digit grouping separator`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c12a8-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="c12a8-114">Separator grupowania cyfr.</span><span class="sxs-lookup"><span data-stu-id="c12a8-114">A digit grouping separator.</span></span> <span data-ttu-id="c12a8-115">Jest używany jako separator tysięcy.</span><span class="sxs-lookup"><span data-stu-id="c12a8-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="c12a8-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c12a8-116">Return values</span></span>

<span data-ttu-id="c12a8-117">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="c12a8-117">*Real*</span></span>

<span data-ttu-id="c12a8-118">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="c12a8-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="c12a8-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="c12a8-119">Example</span></span>

<span data-ttu-id="c12a8-120">Funkcja `NUMBERVALUE( "1 234,56", ",", " ")` zwraca wartość **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="c12a8-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c12a8-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c12a8-121">Additional resources</span></span>

[<span data-ttu-id="c12a8-122">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="c12a8-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
