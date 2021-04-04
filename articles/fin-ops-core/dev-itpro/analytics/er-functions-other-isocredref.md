---
title: ISOCREDREF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISOCREDREF w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: a9378028a4b308aae7796b861b37a5f89ddfe49c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563420"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="cf3f0-103">ISOCREDREF, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="cf3f0-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cf3f0-104">Funkcja `ISOCREDREF` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela w formacie Międzynarodowej Organizacji Normalizacyjnej (ISO) w oparciu o cyfry i znaki alfabetyczne określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf3f0-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="cf3f0-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="cf3f0-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="cf3f0-106">Arguments</span></span>

<span data-ttu-id="cf3f0-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="cf3f0-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="cf3f0-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="cf3f0-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="cf3f0-109">Return values</span></span>

<span data-ttu-id="cf3f0-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="cf3f0-110">*String*</span></span>

<span data-ttu-id="cf3f0-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cf3f0-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="cf3f0-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="cf3f0-113">Aby wyeliminować symbole z alfabetów niezgodnych z systemem ISO, argument `invoice number digits` musi zostać przetłumaczony przed przekazaniem go do tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="cf3f0-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="cf3f0-114">Example</span></span>

<span data-ttu-id="cf3f0-115">Funkcja `ISOCredRef ("VEND-200002")` zwraca wartość **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cf3f0-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cf3f0-116">Additional resources</span></span>

[<span data-ttu-id="cf3f0-117">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="cf3f0-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]