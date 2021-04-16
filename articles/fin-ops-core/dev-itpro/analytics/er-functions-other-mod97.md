---
title: MOD_97, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji MOD_97 w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 1054407addaf6f7c2a7d2f72bf1479e9dc374389
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749172"
---
# <a name="mod_97-er-function"></a><span data-ttu-id="9f90b-103">MOD_97, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="9f90b-103">MOD_97 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f90b-104">Funkcja `MOD_97` zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela jako wyrażenie MOD97, na podstawie cyfr określonego numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="9f90b-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f90b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9f90b-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="9f90b-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="9f90b-106">Arguments</span></span>

<span data-ttu-id="9f90b-107">`invoice number digits`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="9f90b-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="9f90b-108">Wartość tekstowa reprezentująca cyfry numeru faktury.</span><span class="sxs-lookup"><span data-stu-id="9f90b-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="9f90b-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="9f90b-109">Return values</span></span>

<span data-ttu-id="9f90b-110">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="9f90b-110">*String*</span></span>

<span data-ttu-id="9f90b-111">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="9f90b-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9f90b-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="9f90b-112">Example</span></span>

<span data-ttu-id="9f90b-113">Funkcja `MOD_97 ("VEND-200002")` zwraca wartość **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="9f90b-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f90b-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9f90b-114">Additional resources</span></span>

[<span data-ttu-id="9f90b-115">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="9f90b-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]