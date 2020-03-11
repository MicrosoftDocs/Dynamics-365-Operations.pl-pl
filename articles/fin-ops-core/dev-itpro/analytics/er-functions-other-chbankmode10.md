---
title: CH_BANK_MOD_10, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CH_BANK_MOD_10 w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 808e328bfcc35c96091da9a69850429b82a71070
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070582"
---
# <span data-ttu-id="bea89-103"><a name="CH_BANK_MOD_10">CH_BANK_MOD_10, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="bea89-103"><a name="CH_BANK_MOD_10">CH_BANK_MOD_10 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bea89-104">Funkcja `CH_BANK_MOD_10` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela jako wyrażenie MOD10, na podstawie cyfr określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="bea89-104">The `CH_BANK_MOD_10` function returns a *String* value that represents a creditor reference as an MOD10 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="bea89-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="bea89-105">Syntax</span></span>

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="bea89-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="bea89-106">Arguments</span></span>

<span data-ttu-id="bea89-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="bea89-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="bea89-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="bea89-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="bea89-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="bea89-109">Return values</span></span>

<span data-ttu-id="bea89-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="bea89-110">*String*</span></span>

<span data-ttu-id="bea89-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="bea89-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="bea89-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="bea89-112">Example</span></span>

<span data-ttu-id="bea89-113">Funkcja `CH_BANK_MOD_10 ("VEND-200002")` zwraca wartość **3**.</span><span class="sxs-lookup"><span data-stu-id="bea89-113">`CH_BANK_MOD_10 ("VEND-200002")` returns **3**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bea89-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="bea89-114">Additional resources</span></span>

[<span data-ttu-id="bea89-115">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="bea89-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
