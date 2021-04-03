---
title: ROUNDAMOUNT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ROUNDAMOUNT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 2a80587236d17160a996d701ca4ae38be21c818c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563301"
---
# <a name="roundamount-er-function"></a><span data-ttu-id="ebf4b-103">ROUNDAMOUNT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="ebf4b-103">ROUNDAMOUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ebf4b-104">Funkcja `ROUNDAMOUNT` zwraca wartość *rzeczywistą* jako wynik zaokrąglania określonej liczby do najbliższej wielokrotności określonej liczby zgodnie z określoną regułą zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-104">The `ROUNDAMOUNT` function returns a *Real* value as the result of the rounding of the specified number to the nearest multiple of another number according to the specified rounding rule.</span></span>

## <a name="syntax"></a><span data-ttu-id="ebf4b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ebf4b-105">Syntax</span></span>

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a><span data-ttu-id="ebf4b-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ebf4b-106">Arguments</span></span>

<span data-ttu-id="ebf4b-107">`number`: *Int* lub *Real*</span><span class="sxs-lookup"><span data-stu-id="ebf4b-107">`number`: *Int* or *Real*</span></span>

<span data-ttu-id="ebf4b-108">Wartość numeryczna do zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="ebf4b-109">`decimals`: *Int* lub *Real*</span><span class="sxs-lookup"><span data-stu-id="ebf4b-109">`decimals`: *Int* or *Real*</span></span>

<span data-ttu-id="ebf4b-110">Liczba, do której wielokrotności musi być zaokrąglona wartość parametru `number`.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-110">The number that the value of the `number` parameter must be rounded to a multiple of.</span></span>

<span data-ttu-id="ebf4b-111">`round rule`: *Wartość wyliczenia*</span><span class="sxs-lookup"><span data-stu-id="ebf4b-111">`round rule`: *Enum value*</span></span>

<span data-ttu-id="ebf4b-112">Wartość wyliczenia **RoundOffType**, która definiuje regułę zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-112">An enumeration value of the **RoundOffType** enumeration that defines the rounding rule.</span></span> <span data-ttu-id="ebf4b-113">To wyliczenie oferuje następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="ebf4b-113">This enumeration offers the following values:</span></span>

- <span data-ttu-id="ebf4b-114">Normalne (Ordinary)</span><span class="sxs-lookup"><span data-stu-id="ebf4b-114">Normal (Ordinary)</span></span>
- <span data-ttu-id="ebf4b-115">W dół (RoundDown)</span><span class="sxs-lookup"><span data-stu-id="ebf4b-115">Downward (RoundDown)</span></span>
- <span data-ttu-id="ebf4b-116">Zaokrąglanie w górę (RoundUp)</span><span class="sxs-lookup"><span data-stu-id="ebf4b-116">Rounding-up (RoundUp)</span></span>

## <a name="return-values"></a><span data-ttu-id="ebf4b-117">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="ebf4b-117">Return values</span></span>

<span data-ttu-id="ebf4b-118">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="ebf4b-118">*Real*</span></span>

<span data-ttu-id="ebf4b-119">Wynikowa wartość liczbowa jest wielokrotnością wartości określonej przez parametr `decimals` i jest najbliższa wartości określonej przez parametr `number`.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-119">The resulting numeric value is a multiple of the value specified by the `decimals` parameter and is closest to the value specified by the `number` parameter.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ebf4b-120">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="ebf4b-120">Usage notes</span></span>

<span data-ttu-id="ebf4b-121">Gdy parametr `number` ma wartość zero, ta funkcja zawsze zwraca wartość zero.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-121">When the `number` parameter is zero, this function always returns zero.</span></span>

<span data-ttu-id="ebf4b-122">Gdy parametr `decimals` ma wartość zero, ta funkcja zaokrągla do domyślnej wartości zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-122">When the `decimals` parameter is zero, this function rounds to the default round-off value.</span></span> <span data-ttu-id="ebf4b-123">Gdy parametr `round rule` jest ustawiony na **RoundOffType.Ordinary**, domyślna wartość zaokrąglenia to **0,01**.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-123">When the `round rule` parameter is set to **RoundOffType.Ordinary**, the default round-off value is **0.01**.</span></span> <span data-ttu-id="ebf4b-124">W przeciwnym razie wartość domyślna zaokrąglenia to **1,0**.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-124">Otherwise, the default round-off value is **1.0**.</span></span>

<span data-ttu-id="ebf4b-125">Gdy parametr `round rule` jest ustawiony na **RoundOffType.Ordinary**, ta funkcja zaokrągla do najbliższej ilości zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-125">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function rounds to the nearest round-off amount.</span></span>

<span data-ttu-id="ebf4b-126">Gdy parametr `round rule` jest ustawiony na **RoundOffType.RoundDown**, ta funkcja zaokrągla do zera dla najbliższej ilości zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-126">When the `round rule` parameter is set to **RoundOffType.RoundDown**, this function rounds towards zero to the nearest round-off amount.</span></span>

<span data-ttu-id="ebf4b-127">Gdy parametr `round rule` jest ustawiony na **RoundOffType.RoundUp**, ta funkcja zaokrągla od zera dla najbliższej ilości zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-127">When the `round rule` parameter is set to **RoundOffType.RoundUp**, this function rounds away from zero to the nearest round-off amount.</span></span>

<span data-ttu-id="ebf4b-128">Gdy parametr `round rule` jest ustawiony na **RoundOffType.Ordinary**, ta funkcja zachowuje się jak funkcja [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) programu Excel i funkcja [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) języka X++.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-128">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function behaves like the [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel function and the [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) X++ function.</span></span>

## <a name="remarks"></a><span data-ttu-id="ebf4b-129">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ebf4b-129">Remarks</span></span>

<span data-ttu-id="ebf4b-130">Aby zaokrąglić wartość liczbową do określonej liczby miejsc dziesiętnych, należy użyć funkcji [ROUND](er-functions-mathematical-round.md).</span><span class="sxs-lookup"><span data-stu-id="ebf4b-130">To round a numeric value to a specified number of decimal places, use the [ROUND](er-functions-mathematical-round.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="ebf4b-131">Przykład</span><span class="sxs-lookup"><span data-stu-id="ebf4b-131">Example</span></span>

<span data-ttu-id="ebf4b-132">Jeśli parametr **model.RoundOff** został ustawiony na **RoundOffType.Ordinary**, funkcja `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` zwraca wartość 7,35.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-132">If the **model.RoundOff** parameter is set to **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="ebf4b-133">Jeśli parametr **model.RoundOff** został ustawiony na **RoundOffType.RoundDown**, funkcja `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` zwraca wartość 7,35.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-133">If the **model.RoundOff** parameter is set to **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="ebf4b-134">Jeśli parametr **model.RoundOff** został ustawiony na **RoundOffType.RoundUp**, funkcja `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` zwraca wartość 8,4.</span><span class="sxs-lookup"><span data-stu-id="ebf4b-134">If the **model.RoundOff** parameter is set to **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 8.4.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ebf4b-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ebf4b-135">Additional resources</span></span>

[<span data-ttu-id="ebf4b-136">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="ebf4b-136">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)

[<span data-ttu-id="ebf4b-137">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="ebf4b-137">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]