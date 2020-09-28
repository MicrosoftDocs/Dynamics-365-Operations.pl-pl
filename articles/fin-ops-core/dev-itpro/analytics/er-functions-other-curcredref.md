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
ms.openlocfilehash: 95e90289f43896b83ba98a6edefe0cd6028f4043
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744198"
---
# <a name="curcredref-er-function"></a><span data-ttu-id="102c9-103">CURCREDREF, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="102c9-103">CURCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="102c9-104">Funkcja `CURCREDREF` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela na podstawie cyfr określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="102c9-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="102c9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="102c9-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="102c9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="102c9-106">Arguments</span></span>

<span data-ttu-id="102c9-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="102c9-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="102c9-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="102c9-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="102c9-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="102c9-109">Return values</span></span>

<span data-ttu-id="102c9-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="102c9-110">*String*</span></span>

<span data-ttu-id="102c9-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="102c9-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="102c9-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="102c9-112">Example</span></span>

<span data-ttu-id="102c9-113">Funkcja `CURCredRef ("VEND-200002")` zwraca wartość **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="102c9-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="102c9-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="102c9-114">Additional resources</span></span>

[<span data-ttu-id="102c9-115">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="102c9-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
