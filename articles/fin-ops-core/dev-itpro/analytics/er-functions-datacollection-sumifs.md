---
title: SUMIFS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SUMIFS w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: d9d9ef51f3c8cb090f940670c4c3afae104268ed
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687969"
---
# <a name="sumifs-er-function"></a><span data-ttu-id="fcfa0-103">SUMIFS, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="fcfa0-103">SUMIFS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fcfa0-104">Funkcja `SUMIFS` zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-104">The `SUMIFS` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="fcfa0-105">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="fcfa0-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="fcfa0-106">Syntax</span></span>

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="fcfa0-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="fcfa0-107">Arguments</span></span>

<span data-ttu-id="fcfa0-108">`key name for summing`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fcfa0-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="fcfa0-109">Wartość, która jest zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu modułu Raportowanie elektroniczne (ER), dla którego wartość powiązania musi być używana do celów sumowania.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="fcfa0-110">Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Liczba** lub **Ciąg** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-110">The **Collected data key name** property can be configured for either a **Numeric** component or a **String** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="fcfa0-111">`condition 1 range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fcfa0-111">`condition 1 range`: *String*</span></span>

<span data-ttu-id="fcfa0-112">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="fcfa0-112">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="fcfa0-113">Ten argument jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-113">This argument is mandatory.</span></span>

<span data-ttu-id="fcfa0-114">Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-114">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="fcfa0-115">`condition 1 value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fcfa0-115">`condition 1 value`: *String*</span></span>

<span data-ttu-id="fcfa0-116">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="fcfa0-116">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="fcfa0-117">Ten argument jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-117">This argument is mandatory.</span></span>

<span data-ttu-id="fcfa0-118">Właściwość **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-118">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="fcfa0-119">`condition N range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fcfa0-119">`condition N range`: *String*</span></span>

<span data-ttu-id="fcfa0-120">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="fcfa0-120">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="fcfa0-121">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-121">These additional arguments are optional.</span></span>

<span data-ttu-id="fcfa0-122">Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-122">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="fcfa0-123">`condition N value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fcfa0-123">`condition N value`: *String*</span></span>

<span data-ttu-id="fcfa0-124">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="fcfa0-124">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="fcfa0-125">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-125">These additional arguments are optional.</span></span>

<span data-ttu-id="fcfa0-126">Właściwość **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-126">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="fcfa0-127">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="fcfa0-127">Return values</span></span>

<span data-ttu-id="fcfa0-128">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="fcfa0-128">*Real*</span></span>

<span data-ttu-id="fcfa0-129">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-129">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fcfa0-130">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="fcfa0-130">Usage notes</span></span>

<span data-ttu-id="fcfa0-131">Ta funkcja zwraca wartość **0** (zero), gdy opcja **Pobierz szczegóły rezultatu** dla bieżącego składnika **Common\\File** jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-131">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="fcfa0-132">W argumentach `condition range` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-132">In the `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="fcfa0-133">W argumentach `condition value` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-133">In the `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="fcfa0-134">Przykład</span><span class="sxs-lookup"><span data-stu-id="fcfa0-134">Example</span></span>

<span data-ttu-id="fcfa0-135">Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-135">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fcfa0-136">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fcfa0-136">Additional resources</span></span>

[<span data-ttu-id="fcfa0-137">Funkcje gromadzenia danych</span><span class="sxs-lookup"><span data-stu-id="fcfa0-137">Data collection functions</span></span>](er-functions-category-data-collection.md)
