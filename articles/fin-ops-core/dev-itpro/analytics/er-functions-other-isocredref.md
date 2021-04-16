---
title: ISOCREDREF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISOCREDREF w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 51adc6392b07ba4061a475f3072fb35452f15ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748324"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="afaa0-103">ISOCREDREF, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="afaa0-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="afaa0-104">Funkcja `ISOCREDREF` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela w formacie Międzynarodowej Organizacji Normalizacyjnej (ISO) w oparciu o cyfry i znaki alfabetyczne określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="afaa0-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="afaa0-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="afaa0-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="afaa0-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="afaa0-106">Arguments</span></span>

<span data-ttu-id="afaa0-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="afaa0-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="afaa0-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="afaa0-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="afaa0-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="afaa0-109">Return values</span></span>

<span data-ttu-id="afaa0-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="afaa0-110">*String*</span></span>

<span data-ttu-id="afaa0-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="afaa0-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="afaa0-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="afaa0-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="afaa0-113">Aby wyeliminować symbole z alfabetów niezgodnych z systemem ISO, argument `invoice number digits` musi zostać przetłumaczony przed przekazaniem go do tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="afaa0-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="afaa0-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="afaa0-114">Example</span></span>

<span data-ttu-id="afaa0-115">Funkcja `ISOCredRef ("VEND-200002")` zwraca wartość **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="afaa0-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="afaa0-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="afaa0-116">Additional resources</span></span>

[<span data-ttu-id="afaa0-117">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="afaa0-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]