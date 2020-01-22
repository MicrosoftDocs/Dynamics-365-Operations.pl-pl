---
title: COUNTIFS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji COUNTIFS w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 02e401254cdfebd4b549f63dbd6a5f925e7bf544
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916483"
---
# <span data-ttu-id="b71be-103"><a name="COUNTIFS">COUNTIFS, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="b71be-103"><a name="COUNTIFS">COUNTIFS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b71be-104">Funkcja `COUNTIFS` zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, oraz spełniającą określone warunki.</span><span class="sxs-lookup"><span data-stu-id="b71be-104">The `COUNTIFS` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="b71be-105">Każdy warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="b71be-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="b71be-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="b71be-106">Syntax</span></span>

```
COUNTIFS (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="b71be-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b71be-107">Arguments</span></span>

<span data-ttu-id="b71be-108">`condition 1 range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b71be-108">`condition 1 range`: *String*</span></span>

<span data-ttu-id="b71be-109">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="b71be-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span> <span data-ttu-id="b71be-110">Ten argument jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="b71be-110">This argument is mandatory.</span></span>

<span data-ttu-id="b71be-111">`condition 1 value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b71be-111">`condition 1 value`: *String*</span></span>

<span data-ttu-id="b71be-112">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="b71be-112">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="b71be-113">Ten argument jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="b71be-113">This argument is mandatory.</span></span>

<span data-ttu-id="b71be-114">`condition N range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b71be-114">`condition N range`: *String*</span></span>

<span data-ttu-id="b71be-115">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="b71be-115">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="b71be-116">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="b71be-116">These additional arguments are optional.</span></span>

<span data-ttu-id="b71be-117">`condition N value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b71be-117">`condition N value`: *String*</span></span>

<span data-ttu-id="b71be-118">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="b71be-118">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="b71be-119">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="b71be-119">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="b71be-120">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="b71be-120">Return values</span></span>

<span data-ttu-id="b71be-121">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="b71be-121">*Integer*</span></span>

<span data-ttu-id="b71be-122">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="b71be-122">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b71be-123">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="b71be-123">Usage notes</span></span>

<span data-ttu-id="b71be-124">Właściwości **Nazwa pobranego klucza danych** i **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="b71be-124">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="b71be-125">Ta funkcja zwraca wartość **0** (zero), gdy opcja **Pobierz szczegóły rezultatu** dla bieżącego składnika **Common\\File** jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="b71be-125">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="b71be-126">W argumentach `condition range` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="b71be-126">In `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="b71be-127">W argumentach `condition value` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="b71be-127">In `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="b71be-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="b71be-128">Example</span></span>

<span data-ttu-id="b71be-129">Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.</span><span class="sxs-lookup"><span data-stu-id="b71be-129">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b71be-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b71be-130">Additional resources</span></span>

[<span data-ttu-id="b71be-131">Funkcje gromadzenia danych</span><span class="sxs-lookup"><span data-stu-id="b71be-131">Data collection functions</span></span>](er-functions-category-data-collection.md)
