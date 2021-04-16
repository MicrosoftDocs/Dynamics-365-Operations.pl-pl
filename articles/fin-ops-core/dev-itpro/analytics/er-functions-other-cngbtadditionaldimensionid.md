---
title: CN_GBT_ADDITIONALDIMENSIONID, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CN_GBT_ADDITIONALDIMENSIONID w module Raportowanie elektroniczne (ER).
author: NickSelin
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
ms.openlocfilehash: ac0b54476265171b3826e43600f99097701231e1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744398"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="5bd73-103">CN_GBT_ADDITIONALDIMENSIONID, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="5bd73-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5bd73-104">Funkcja `CN_GBT_ADDITIONALDIMENSIONID` zwraca wartość typu *Ciąg*, która reprezentuje identyfikator pojedynczego wymiaru finansowego pobrany z określonego ciągu.</span><span class="sxs-lookup"><span data-stu-id="5bd73-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="5bd73-105">Określony ciąg przedstawia wszystkie wymiary jako rozdzielaną przecinkami listę identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="5bd73-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="5bd73-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="5bd73-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="5bd73-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="5bd73-107">Arguments</span></span>

<span data-ttu-id="5bd73-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="5bd73-108">`text`: *String*</span></span>

<span data-ttu-id="5bd73-109">Wartość typu *Ciąg* przedstawiająca wszystkie wymiary jako rozdzielaną przecinkami listę identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="5bd73-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="5bd73-110">`number`: Liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="5bd73-110">`number`: Integer</span></span>

<span data-ttu-id="5bd73-111">Wartość typu *Liczba całkowita* określa numer kolejny żądanego wymiaru w określonym ciągu.</span><span class="sxs-lookup"><span data-stu-id="5bd73-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="5bd73-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="5bd73-112">Return values</span></span>

<span data-ttu-id="5bd73-113">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="5bd73-113">*String*</span></span>

<span data-ttu-id="5bd73-114">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="5bd73-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="5bd73-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="5bd73-115">Example</span></span>

<span data-ttu-id="5bd73-116">Funkcja `CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` zwraca wartość **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="5bd73-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5bd73-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5bd73-117">Additional resources</span></span>

[<span data-ttu-id="5bd73-118">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="5bd73-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]