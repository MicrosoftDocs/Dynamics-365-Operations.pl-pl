---
title: COUNTIF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji COUNTIF w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: ca7c0f449aff75527e5052ba01e6fc0e29bb0fd7
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917702"
---
# <span data-ttu-id="da098-103"><a name="COUNTIF">COUNTIF, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="da098-103"><a name="COUNTIF">COUNTIF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da098-104">Funkcja `COUNTIF` zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, oraz spełniającą określony warunek.</span><span class="sxs-lookup"><span data-stu-id="da098-104">The `COUNTIF` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="da098-105">Warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="da098-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="da098-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="da098-106">Syntax</span></span>

```
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="da098-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="da098-107">Arguments</span></span>

<span data-ttu-id="da098-108">`condition range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="da098-108">`condition range`: *String*</span></span>

<span data-ttu-id="da098-109">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="da098-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span>

<span data-ttu-id="da098-110">`condition value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="da098-110">`condition value`: *String*</span></span>

<span data-ttu-id="da098-111">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="da098-111">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span>

## <a name="return-values"></a><span data-ttu-id="da098-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="da098-112">Return values</span></span>

<span data-ttu-id="da098-113">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="da098-113">*Integer*</span></span>

<span data-ttu-id="da098-114">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="da098-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="da098-115">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="da098-115">Usage notes</span></span>

<span data-ttu-id="da098-116">Właściwości **Nazwa pobranego klucza danych** i **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="da098-116">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="da098-117">Ta funkcja zwraca wartość **0** (zero), gdy opcja **Pobierz szczegóły rezultatu** dla bieżącego składnika **Common\\File** jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="da098-117">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="da098-118">W argumencie `condition range` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="da098-118">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="da098-119">W argumencie `condition value` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="da098-119">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="da098-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="da098-120">Example</span></span>

<span data-ttu-id="da098-121">Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.</span><span class="sxs-lookup"><span data-stu-id="da098-121">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da098-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="da098-122">Additional resources</span></span>

[<span data-ttu-id="da098-123">Funkcje gromadzenia danych</span><span class="sxs-lookup"><span data-stu-id="da098-123">Data collection functions</span></span>](er-functions-category-data-collection.md)
