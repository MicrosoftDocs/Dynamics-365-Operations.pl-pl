---
title: FORMATELEMENTNAME, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FORMATELEMENTNAME w module Raportowanie elektroniczne (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef59bb44a7096f4c095ce37a89558a717748f02e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685334"
---
# <a name="formatelementname-er-function"></a><span data-ttu-id="a9a97-103">FORMATELEMENTNAME, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="a9a97-103">FORMATELEMENTNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9a97-104">Funkcja `FORMATELEMENTNAME` zwraca wartość typu *Ciąg* reprezentującą nazwę bieżącego elementu formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="a9a97-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9a97-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a9a97-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="a9a97-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="a9a97-106">Return values</span></span>

<span data-ttu-id="a9a97-107">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="a9a97-107">*String*</span></span>

<span data-ttu-id="a9a97-108">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="a9a97-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a9a97-109">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="a9a97-109">Usage notes</span></span>

<span data-ttu-id="a9a97-110">Tę funkcję można wywoływać w wyrażeniach ER skonfigurowanych dla właściwości **Nazwa pobranego klucza danych** i **Wartość pobranego klucza danych** składnika formatu ER z grupy **Tekst** znajdującej się w składniku **Common\\File**, dla którego włączono opcję **Pobierz szczegóły rezultatu**.</span><span class="sxs-lookup"><span data-stu-id="a9a97-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="a9a97-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="a9a97-111">Example</span></span>

<span data-ttu-id="a9a97-112">Aby dowiedzieć się więcej o korzystaniu z tej funkcji, zobacz przewodnik zadania [ER Używanie danych wyjściowych formatu do inwentaryzacji i sumowania](tasks/er-format-counting-summing-1.md), który jest częścią procesu biznesowego **Nabywanie/opracowywanie składników usług/rozwiązań informatycznych**.</span><span class="sxs-lookup"><span data-stu-id="a9a97-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9a97-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a9a97-113">Additional resources</span></span>

[<span data-ttu-id="a9a97-114">Funkcje gromadzenia danych</span><span class="sxs-lookup"><span data-stu-id="a9a97-114">Data collection functions</span></span>](er-functions-category-data-collection.md)
