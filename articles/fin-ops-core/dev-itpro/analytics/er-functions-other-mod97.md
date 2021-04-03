---
title: MOD_97, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji MOD_97 w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 618cb2b101dd0b1c91b3b1538ef3f87c21e4a70a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563349"
---
# <a name="mod_97-er-function"></a><span data-ttu-id="0d65f-103">MOD_97, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="0d65f-103">MOD_97 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d65f-104">Funkcja `MOD_97` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela jako wyrażenie MOD97, na podstawie cyfr określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="0d65f-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="0d65f-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0d65f-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="0d65f-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="0d65f-106">Arguments</span></span>

<span data-ttu-id="0d65f-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="0d65f-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="0d65f-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="0d65f-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="0d65f-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="0d65f-109">Return values</span></span>

<span data-ttu-id="0d65f-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="0d65f-110">*String*</span></span>

<span data-ttu-id="0d65f-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="0d65f-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="0d65f-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="0d65f-112">Example</span></span>

<span data-ttu-id="0d65f-113">Funkcja `MOD_97 ("VEND-200002")` zwraca wartość **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="0d65f-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d65f-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0d65f-114">Additional resources</span></span>

[<span data-ttu-id="0d65f-115">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="0d65f-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]