---
title: NUMBERVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMBERVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
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
ms.openlocfilehash: 84d7f17f37a83547522cf09047b72100f6f5b859
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755355"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="f62a2-103">NUMBERVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="f62a2-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f62a2-104">Funkcja `NUMBERVALUE` zwraca wartość *rzeczywistą*, która jest konwertowana z określonej wartości typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="f62a2-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="f62a2-105">Podczas konwersji są uwzględniane wybrane separatory dziesiętne i separatory grupowania cyfr.</span><span class="sxs-lookup"><span data-stu-id="f62a2-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="f62a2-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="f62a2-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="f62a2-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f62a2-107">Arguments</span></span>

<span data-ttu-id="f62a2-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f62a2-108">`text`: *String*</span></span>

<span data-ttu-id="f62a2-109">Wartość tekstowa, która musi zostać przekonwertowana na liczbę *rzeczywistą*.</span><span class="sxs-lookup"><span data-stu-id="f62a2-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="f62a2-110">`decimal separator`: Ciąg</span><span class="sxs-lookup"><span data-stu-id="f62a2-110">`decimal separator`: String</span></span>

<span data-ttu-id="f62a2-111">Separator dziesiętny.</span><span class="sxs-lookup"><span data-stu-id="f62a2-111">A decimal separator.</span></span> <span data-ttu-id="f62a2-112">Służy do oddzielania całkowitych i ułamkowych części liczby dziesiętnej.</span><span class="sxs-lookup"><span data-stu-id="f62a2-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="f62a2-113">`digit grouping separator`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f62a2-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="f62a2-114">Separator grupowania cyfr.</span><span class="sxs-lookup"><span data-stu-id="f62a2-114">A digit grouping separator.</span></span> <span data-ttu-id="f62a2-115">Jest używany jako separator tysięcy.</span><span class="sxs-lookup"><span data-stu-id="f62a2-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="f62a2-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="f62a2-116">Return values</span></span>

<span data-ttu-id="f62a2-117">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="f62a2-117">*Real*</span></span>

<span data-ttu-id="f62a2-118">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="f62a2-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="f62a2-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="f62a2-119">Example</span></span>

<span data-ttu-id="f62a2-120">Funkcja `NUMBERVALUE( "1 234,56", ",", " ")` zwraca wartość **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="f62a2-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f62a2-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f62a2-121">Additional resources</span></span>

[<span data-ttu-id="f62a2-122">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="f62a2-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]