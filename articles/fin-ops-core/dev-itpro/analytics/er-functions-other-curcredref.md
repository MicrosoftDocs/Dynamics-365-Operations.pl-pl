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
ms.openlocfilehash: 6e684a8e063cb3c049d13005cbcf6ebbe688af00
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041499"
---
# <span data-ttu-id="2c6b9-103"><a name="CURCREDREF">CURCREDREF, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="2c6b9-103"><a name="CURCREDREF">CURCREDREF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c6b9-104">Funkcja `CURCREDREF` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela na podstawie cyfr określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="2c6b9-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c6b9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2c6b9-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="2c6b9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="2c6b9-106">Arguments</span></span>

<span data-ttu-id="2c6b9-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="2c6b9-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="2c6b9-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="2c6b9-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="2c6b9-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="2c6b9-109">Return values</span></span>

<span data-ttu-id="2c6b9-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="2c6b9-110">*String*</span></span>

<span data-ttu-id="2c6b9-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="2c6b9-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="2c6b9-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="2c6b9-112">Example</span></span>

<span data-ttu-id="2c6b9-113">Funkcja `CURCredRef ("VEND-200002")` zwraca wartość **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="2c6b9-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2c6b9-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2c6b9-114">Additional resources</span></span>

[<span data-ttu-id="2c6b9-115">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="2c6b9-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
