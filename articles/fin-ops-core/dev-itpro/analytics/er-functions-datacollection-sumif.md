---
title: SUMIF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SUMIF w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 04/27/2020
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
ms.openlocfilehash: 9df7be0825203f91434d348385c1ee358ae555ea
ms.sourcegitcommit: ef6fd78c817f93610771cfb2477f52f16b882164
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2020
ms.locfileid: "3290207"
---
# <a name=""></a><span data-ttu-id="38729-103"><a name="SUMIF">SUMIF, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="38729-103"><a name="SUMIF">SUMIF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38729-104">Funkcja `SUMIF` zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="38729-104">The `SUMIF` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="38729-105">Warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="38729-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="38729-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="38729-106">Syntax</span></span>

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="38729-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="38729-107">Arguments</span></span>

<span data-ttu-id="38729-108">`key name for summing`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="38729-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="38729-109">Wartość, która jest zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu modułu Raportowanie elektroniczne (ER), dla którego wartość powiązania musi być używana do celów sumowania.</span><span class="sxs-lookup"><span data-stu-id="38729-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="38729-110">Właściwość **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="38729-110">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="38729-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="38729-111">Return values</span></span>

<span data-ttu-id="38729-112">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="38729-112">*Real*</span></span>

<span data-ttu-id="38729-113">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="38729-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="38729-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="38729-114">Usage notes</span></span>

<span data-ttu-id="38729-115">Ta funkcja zwraca wartość **0** (zero), gdy opcja **Pobierz szczegóły rezultatu** dla bieżącego składnika **Common\\File** jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="38729-115">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="38729-116">W argumencie `condition range` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="38729-116">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="38729-117">W argumencie `condition value` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="38729-117">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="38729-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="38729-118">Example</span></span>

<span data-ttu-id="38729-119">Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.</span><span class="sxs-lookup"><span data-stu-id="38729-119">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

<span data-ttu-id="38729-120">Aby uzyskać więcej informacji i przykładów dotyczących korzystania z tej funkcji, zobacz tematy [Odkładanie wykonania elementów sekwencji w formatach ER](er-defer-sequence-element.md#Example) i [Odkładanie wykonania elementów XML w formatach ER](er-defer-xml-element.md#Example).</span><span class="sxs-lookup"><span data-stu-id="38729-120">For more information and examples about using this function, see [Defer the execution of sequence elements in ER formats](er-defer-sequence-element.md#Example) and [Defer the execution of XML elements in ER formats](er-defer-xml-element.md#Example).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="38729-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="38729-121">Additional resources</span></span>

[<span data-ttu-id="38729-122">Funkcje gromadzenia danych</span><span class="sxs-lookup"><span data-stu-id="38729-122">Data collection functions</span></span>](er-functions-category-data-collection.md)
