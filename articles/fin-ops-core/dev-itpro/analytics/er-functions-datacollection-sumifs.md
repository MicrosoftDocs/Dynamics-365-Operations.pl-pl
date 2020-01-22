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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6820be1976e722f7b108b3e9303c8ed4d822ae9b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917610"
---
# <span data-ttu-id="fb71e-103"><a name="SUMIFS">SUMIFS, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="fb71e-103"><a name="SUMIFS">SUMIFS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb71e-104">Funkcja `SUMIFS` zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="fb71e-104">The `SUMIFS` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="fb71e-105">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="fb71e-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb71e-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="fb71e-106">Syntax</span></span>

```
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="fb71e-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="fb71e-107">Arguments</span></span>

<span data-ttu-id="fb71e-108">`key name for summing`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fb71e-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="fb71e-109">Wartość, która jest zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu modułu Raportowanie elektroniczne (ER), dla którego wartość powiązania musi być używana do celów sumowania.</span><span class="sxs-lookup"><span data-stu-id="fb71e-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="fb71e-110">Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Liczba** lub **Ciąg** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fb71e-110">The **Collected data key name** property can be configured for either a **Numeric** component or a **String** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="fb71e-111">`condition 1 range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fb71e-111">`condition 1 range`: *String*</span></span>

<span data-ttu-id="fb71e-112">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="fb71e-112">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="fb71e-113">Ten argument jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="fb71e-113">This argument is mandatory.</span></span>

<span data-ttu-id="fb71e-114">Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fb71e-114">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="fb71e-115">`condition 1 value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fb71e-115">`condition 1 value`: *String*</span></span>

<span data-ttu-id="fb71e-116">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="fb71e-116">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="fb71e-117">Ten argument jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="fb71e-117">This argument is mandatory.</span></span>

<span data-ttu-id="fb71e-118">Właściwość **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fb71e-118">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="fb71e-119">`condition N range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fb71e-119">`condition N range`: *String*</span></span>

<span data-ttu-id="fb71e-120">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="fb71e-120">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="fb71e-121">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="fb71e-121">These additional arguments are optional.</span></span>

<span data-ttu-id="fb71e-122">Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fb71e-122">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="fb71e-123">`condition N value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="fb71e-123">`condition N value`: *String*</span></span>

<span data-ttu-id="fb71e-124">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="fb71e-124">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="fb71e-125">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="fb71e-125">These additional arguments are optional.</span></span>

<span data-ttu-id="fb71e-126">Właściwość **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="fb71e-126">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="fb71e-127">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="fb71e-127">Return values</span></span>

<span data-ttu-id="fb71e-128">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="fb71e-128">*Real*</span></span>

<span data-ttu-id="fb71e-129">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="fb71e-129">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fb71e-130">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="fb71e-130">Usage notes</span></span>

<span data-ttu-id="fb71e-131">Ta funkcja zwraca wartość **0** (zero), gdy opcja **Pobierz szczegóły rezultatu** dla bieżącego składnika **Common\\File** jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="fb71e-131">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="fb71e-132">W argumentach `condition range` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="fb71e-132">In the `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="fb71e-133">W argumentach `condition value` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="fb71e-133">In the `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="fb71e-134">Przykład</span><span class="sxs-lookup"><span data-stu-id="fb71e-134">Example</span></span>

<span data-ttu-id="fb71e-135">Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.</span><span class="sxs-lookup"><span data-stu-id="fb71e-135">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb71e-136">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fb71e-136">Additional resources</span></span>

[<span data-ttu-id="fb71e-137">Funkcje gromadzenia danych</span><span class="sxs-lookup"><span data-stu-id="fb71e-137">Data collection functions</span></span>](er-functions-category-data-collection.md)
