---
title: ISVALIDCHARACTERISO7064, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ISVALIDCHARACTERISO7064 w module Raportowanie elektroniczne (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3bceb15bbe1dc65abc88c1229459707a6166482
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680669"
---
# <a name="isvalidcharacteriso7064-er-function"></a><span data-ttu-id="98442-103">ISVALIDCHARACTERISO7064, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="98442-103">ISVALIDCHARACTERISO7064 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98442-104">Funkcja `ISVALIDCHARACTERISO7064` zwraca wartość *logiczną* **TRUE**, jeśli podany ciąg tekstowy reprezentuje prawidłowy międzynarodowy numer konta bankowego (IBAN).</span><span class="sxs-lookup"><span data-stu-id="98442-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="98442-105">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="98442-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="98442-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="98442-106">Syntax</span></span>

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="98442-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="98442-107">Arguments</span></span>

<span data-ttu-id="98442-108">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="98442-108">`text`: *String*</span></span>

<span data-ttu-id="98442-109">Wartość tekstowa, która reprezentuje numer IBAN.</span><span class="sxs-lookup"><span data-stu-id="98442-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="98442-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="98442-110">Return values</span></span>

<span data-ttu-id="98442-111">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="98442-111">*String*</span></span>

<span data-ttu-id="98442-112">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="98442-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="98442-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="98442-113">Example</span></span>

<span data-ttu-id="98442-114">Funkcja `ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` zwraca wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="98442-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="98442-115">Funkcja `ISVALIDCHARACTERISO7064 ("AT61")` zwraca wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="98442-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98442-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="98442-116">Additional resources</span></span>

[<span data-ttu-id="98442-117">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="98442-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
