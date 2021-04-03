---
title: CH_BANK_MOD_10, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CH_BANK_MOD_10 w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 21942fa47b968fa10bfc9b07f269d44e495139fe
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564847"
---
# <a name="ch_bank_mod_10-er-function"></a><span data-ttu-id="89cb9-103">CH_BANK_MOD_10, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="89cb9-103">CH_BANK_MOD_10 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89cb9-104">Funkcja `CH_BANK_MOD_10` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela jako wyrażenie MOD10, na podstawie cyfr określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="89cb9-104">The `CH_BANK_MOD_10` function returns a *String* value that represents a creditor reference as an MOD10 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="89cb9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="89cb9-105">Syntax</span></span>

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="89cb9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="89cb9-106">Arguments</span></span>

<span data-ttu-id="89cb9-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="89cb9-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="89cb9-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="89cb9-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="89cb9-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="89cb9-109">Return values</span></span>

<span data-ttu-id="89cb9-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="89cb9-110">*String*</span></span>

<span data-ttu-id="89cb9-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="89cb9-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="89cb9-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="89cb9-112">Example</span></span>

<span data-ttu-id="89cb9-113">Funkcja `CH_BANK_MOD_10 ("VEND-200002")` zwraca wartość **3**.</span><span class="sxs-lookup"><span data-stu-id="89cb9-113">`CH_BANK_MOD_10 ("VEND-200002")` returns **3**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89cb9-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="89cb9-114">Additional resources</span></span>

[<span data-ttu-id="89cb9-115">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="89cb9-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]