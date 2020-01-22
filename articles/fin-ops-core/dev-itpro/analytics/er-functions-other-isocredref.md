---
title: ISOCREDREF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISOCREDREF w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: ea72d824d3a98d7685a965e981d057991f012a0e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916966"
---
# <span data-ttu-id="13fe9-103"><a name="ISOCREDREF">ISOCREDREF, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="13fe9-103"><a name="ISOCREDREF">ISOCREDREF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="13fe9-104">Funkcja `ISOCREDREF` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela w formacie Międzynarodowej Organizacji Normalizacyjnej (ISO) w oparciu o cyfry i znaki alfabetyczne określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="13fe9-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="13fe9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="13fe9-105">Syntax</span></span>

```
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="13fe9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="13fe9-106">Arguments</span></span>

<span data-ttu-id="13fe9-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="13fe9-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="13fe9-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="13fe9-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="13fe9-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="13fe9-109">Return values</span></span>

<span data-ttu-id="13fe9-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="13fe9-110">*String*</span></span>

<span data-ttu-id="13fe9-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="13fe9-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="13fe9-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="13fe9-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="13fe9-113">Aby wyeliminować symbole z alfabetów niezgodnych z systemem ISO, argument `invoice number digits` musi zostać przetłumaczony przed przekazaniem go do tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="13fe9-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="13fe9-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="13fe9-114">Example</span></span>

<span data-ttu-id="13fe9-115">Funkcja `ISOCredRef ("VEND-200002")` zwraca wartość **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="13fe9-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13fe9-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="13fe9-116">Additional resources</span></span>

[<span data-ttu-id="13fe9-117">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="13fe9-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
