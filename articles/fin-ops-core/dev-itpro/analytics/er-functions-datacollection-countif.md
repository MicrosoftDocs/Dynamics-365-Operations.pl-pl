---
title: COUNTIF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji COUNTIF w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: bebb3d3b810e68fa6a0d3f4deb92b750b7c9a9f3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755307"
---
# <a name="countif-er-function"></a><span data-ttu-id="d2eb2-103">COUNTIF, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="d2eb2-103">COUNTIF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2eb2-104">Funkcja `COUNTIF` zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, oraz spełniającą określony warunek.</span><span class="sxs-lookup"><span data-stu-id="d2eb2-104">The `COUNTIF` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="d2eb2-105">Warunek składa się z zakresu kluczy i wartości klucza.</span><span class="sxs-lookup"><span data-stu-id="d2eb2-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2eb2-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="d2eb2-106">Syntax</span></span>

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="d2eb2-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d2eb2-107">Arguments</span></span>

<span data-ttu-id="d2eb2-108">`condition range`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d2eb2-108">`condition range`: *String*</span></span>

<span data-ttu-id="d2eb2-109">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Nazwa pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="d2eb2-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span>

<span data-ttu-id="d2eb2-110">`condition value`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d2eb2-110">`condition value`: *String*</span></span>

<span data-ttu-id="d2eb2-111">Wartość zwracana przez wyrażenie skonfigurowane we właściwości **Wartość pobranego klucza danych** składnika formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="d2eb2-111">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span>

## <a name="return-values"></a><span data-ttu-id="d2eb2-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="d2eb2-112">Return values</span></span>

<span data-ttu-id="d2eb2-113">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="d2eb2-113">*Integer*</span></span>

<span data-ttu-id="d2eb2-114">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="d2eb2-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d2eb2-115">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="d2eb2-115">Usage notes</span></span>

<span data-ttu-id="d2eb2-116">Właściwości **Nazwa pobranego klucza danych** i **Wartość pobranego klucza danych** można konfigurować dla składnika **Sekwencja** lub **Element XML** formatu ER znajdującego się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="d2eb2-116">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="d2eb2-117">Ta funkcja zwraca wartość **0** (zero), gdy opcja **Pobierz szczegóły rezultatu** dla bieżącego składnika **Common\\File** jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="d2eb2-117">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="d2eb2-118">W argumencie `condition range` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="d2eb2-118">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="d2eb2-119">W argumencie `condition value` symbol wieloznaczny **"\*"** może służyć do reprezentowania wielu znaków.</span><span class="sxs-lookup"><span data-stu-id="d2eb2-119">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="d2eb2-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="d2eb2-120">Example</span></span>

<span data-ttu-id="d2eb2-121">Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.</span><span class="sxs-lookup"><span data-stu-id="d2eb2-121">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d2eb2-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d2eb2-122">Additional resources</span></span>

[<span data-ttu-id="d2eb2-123">Funkcje gromadzenia danych</span><span class="sxs-lookup"><span data-stu-id="d2eb2-123">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]