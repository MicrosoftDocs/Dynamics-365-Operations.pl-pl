---
title: SUMIFS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SUMIFS w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: a3adfe62d9fd7bdc23784cf7311f65a4d2e88960
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747090"
---
# <a name="sumifs-er-function"></a><span data-ttu-id="efbee-103">SUMIFS, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="efbee-103">SUMIFS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efbee-104">Funkcja `SUMIFS` zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="efbee-104">The `SUMIFS` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="efbee-105">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="efbee-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="efbee-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="efbee-106">Syntax</span></span>

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="efbee-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="efbee-107">Arguments</span></span>

<span data-ttu-id="efbee-108">`key name for summing`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="efbee-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="efbee-109">Wartość, która jest zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu modułu Raportowanie elektroniczne (ER), dla którego wartość powiązania musi być używana do celów sumowania.</span><span class="sxs-lookup"><span data-stu-id="efbee-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="efbee-110">Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Liczba** lub **Ciąg** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="efbee-110">The **Collected data key name** property can be configured for either a **Numeric** component or a **String** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="efbee-111">`condition 1 range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="efbee-111">`condition 1 range`: *String*</span></span>

<span data-ttu-id="efbee-112">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="efbee-112">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="efbee-113">Ten argument jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="efbee-113">This argument is mandatory.</span></span>

<span data-ttu-id="efbee-114">Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="efbee-114">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="efbee-115">`condition 1 value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="efbee-115">`condition 1 value`: *String*</span></span>

<span data-ttu-id="efbee-116">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="efbee-116">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="efbee-117">Ten argument jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="efbee-117">This argument is mandatory.</span></span>

<span data-ttu-id="efbee-118">Właściwość **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="efbee-118">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="efbee-119">`condition N range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="efbee-119">`condition N range`: *String*</span></span>

<span data-ttu-id="efbee-120">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="efbee-120">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="efbee-121">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="efbee-121">These additional arguments are optional.</span></span>

<span data-ttu-id="efbee-122">Właściwość **Nazwa pobranego klucza danych** i można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="efbee-122">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="efbee-123">`condition N value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="efbee-123">`condition N value`: *String*</span></span>

<span data-ttu-id="efbee-124">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="efbee-124">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="efbee-125">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="efbee-125">These additional arguments are optional.</span></span>

<span data-ttu-id="efbee-126">Właściwość **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="efbee-126">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="efbee-127">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="efbee-127">Return values</span></span>

<span data-ttu-id="efbee-128">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="efbee-128">*Real*</span></span>

<span data-ttu-id="efbee-129">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="efbee-129">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="efbee-130">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="efbee-130">Usage notes</span></span>

<span data-ttu-id="efbee-131">Ta funkcja zwraca wartość **0** (zero), gdy opcja **Pobierz szczegóły rezultatu** dla bieżącego składnika **Common\\File** jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="efbee-131">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="efbee-132">W argumentach `condition range` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="efbee-132">In the `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="efbee-133">W argumentach `condition value` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="efbee-133">In the `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="efbee-134">Przykład</span><span class="sxs-lookup"><span data-stu-id="efbee-134">Example</span></span>

<span data-ttu-id="efbee-135">Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.</span><span class="sxs-lookup"><span data-stu-id="efbee-135">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="efbee-136">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="efbee-136">Additional resources</span></span>

[<span data-ttu-id="efbee-137">Funkcje gromadzenia danych</span><span class="sxs-lookup"><span data-stu-id="efbee-137">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]