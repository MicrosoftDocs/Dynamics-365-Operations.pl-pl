---
title: CURCREDREF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CURCREDREF w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 5633541b1c7e25a0cfb837c4679691506806421b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917012"
---
# <span data-ttu-id="6e269-103"><a name="CURCREDREF">CURCREDREF, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="6e269-103"><a name="CURCREDREF">CURCREDREF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e269-104">Funkcja `CURCREDREF` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela na podstawie cyfr określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="6e269-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e269-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="6e269-105">Syntax</span></span>

```
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="6e269-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="6e269-106">Arguments</span></span>

<span data-ttu-id="6e269-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6e269-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="6e269-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="6e269-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="6e269-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="6e269-109">Return values</span></span>

<span data-ttu-id="6e269-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="6e269-110">*String*</span></span>

<span data-ttu-id="6e269-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="6e269-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="6e269-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="6e269-112">Example</span></span>

<span data-ttu-id="6e269-113">Funkcja `CURCredRef ("VEND-200002")` zwraca wartość **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="6e269-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6e269-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6e269-114">Additional resources</span></span>

[<span data-ttu-id="6e269-115">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="6e269-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
