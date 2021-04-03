---
title: CN_GBT_ADDITIONALDIMENSIONID, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CN_GBT_ADDITIONALDIMENSIONID w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 5774bb6928ae321af923819d6b2cc609dbf35b99
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564149"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="5b11b-103">CN_GBT_ADDITIONALDIMENSIONID, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="5b11b-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b11b-104">Funkcja `CN_GBT_ADDITIONALDIMENSIONID` zwraca wartość typu *Ciąg*, która reprezentuje identyfikator pojedynczego wymiaru finansowego pobrany z określonego ciągu.</span><span class="sxs-lookup"><span data-stu-id="5b11b-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="5b11b-105">Określony ciąg przedstawia wszystkie wymiary jako rozdzielaną przecinkami listę identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="5b11b-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="5b11b-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="5b11b-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="5b11b-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="5b11b-107">Arguments</span></span>

<span data-ttu-id="5b11b-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="5b11b-108">`text`: *String*</span></span>

<span data-ttu-id="5b11b-109">Wartość typu *Ciąg* przedstawiająca wszystkie wymiary jako rozdzielaną przecinkami listę identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="5b11b-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="5b11b-110">`number`: Liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="5b11b-110">`number`: Integer</span></span>

<span data-ttu-id="5b11b-111">Wartość typu *Liczba całkowita* określa numer kolejny żądanego wymiaru w określonym ciągu.</span><span class="sxs-lookup"><span data-stu-id="5b11b-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="5b11b-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="5b11b-112">Return values</span></span>

<span data-ttu-id="5b11b-113">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="5b11b-113">*String*</span></span>

<span data-ttu-id="5b11b-114">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="5b11b-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="5b11b-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="5b11b-115">Example</span></span>

<span data-ttu-id="5b11b-116">Funkcja `CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` zwraca wartość **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="5b11b-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b11b-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5b11b-117">Additional resources</span></span>

[<span data-ttu-id="5b11b-118">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="5b11b-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]