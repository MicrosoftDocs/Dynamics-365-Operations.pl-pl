---
title: CN_GBT_ADDITIONALDIMENSIONID, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CN_GBT_ADDITIONALDIMENSIONID w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 7fdc4527bc6115bdb3fca9d6a92d3d77a7c264c2
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744438"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="b8aed-103">CN_GBT_ADDITIONALDIMENSIONID, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="b8aed-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8aed-104">Funkcja `CN_GBT_ADDITIONALDIMENSIONID` zwraca wartość typu *Ciąg*, która reprezentuje identyfikator pojedynczego wymiaru finansowego pobrany z określonego ciągu.</span><span class="sxs-lookup"><span data-stu-id="b8aed-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="b8aed-105">Określony ciąg przedstawia wszystkie wymiary jako rozdzielaną przecinkami listę identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="b8aed-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8aed-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="b8aed-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="b8aed-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b8aed-107">Arguments</span></span>

<span data-ttu-id="b8aed-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b8aed-108">`text`: *String*</span></span>

<span data-ttu-id="b8aed-109">Wartość typu *Ciąg* przedstawiająca wszystkie wymiary jako rozdzielaną przecinkami listę identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="b8aed-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="b8aed-110">`number`: Liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="b8aed-110">`number`: Integer</span></span>

<span data-ttu-id="b8aed-111">Wartość typu *Liczba całkowita* określa numer kolejny żądanego wymiaru w określonym ciągu.</span><span class="sxs-lookup"><span data-stu-id="b8aed-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="b8aed-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="b8aed-112">Return values</span></span>

<span data-ttu-id="b8aed-113">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="b8aed-113">*String*</span></span>

<span data-ttu-id="b8aed-114">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="b8aed-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="b8aed-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="b8aed-115">Example</span></span>

<span data-ttu-id="b8aed-116">Funkcja `CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` zwraca wartość **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="b8aed-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8aed-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b8aed-117">Additional resources</span></span>

[<span data-ttu-id="b8aed-118">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="b8aed-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
