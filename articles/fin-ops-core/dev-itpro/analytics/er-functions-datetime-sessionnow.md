---
title: SESSIONNOW, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SESSIONNOW w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: a79e8055a4b5025e1b1c4ab91875cf165fa8b354
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563405"
---
# <a name="sessionnow-er-function"></a><span data-ttu-id="b2382-103">SESSIONNOW, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="b2382-103">SESSIONNOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2382-104">Funkcja `SESSIONNOW` zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę sesji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b2382-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2382-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b2382-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="b2382-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="b2382-106">Return values</span></span>

<span data-ttu-id="b2382-107">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="b2382-107">*DateTime*</span></span>

<span data-ttu-id="b2382-108">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="b2382-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="b2382-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="b2382-109">Example</span></span>

<span data-ttu-id="b2382-110">Funkcja `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` zwraca bieżącą datę/godzinę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24.12.2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.</span><span class="sxs-lookup"><span data-stu-id="b2382-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2382-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b2382-111">Additional resources</span></span>

[<span data-ttu-id="b2382-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="b2382-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]