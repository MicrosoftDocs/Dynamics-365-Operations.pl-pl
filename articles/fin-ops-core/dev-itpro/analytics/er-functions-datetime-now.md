---
title: NOW, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NOW w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 0c3cfefd36db44608f05225746704aa3fbe4fc2c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682372"
---
# <a name="now-er-function"></a><span data-ttu-id="2361b-103">NOW, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="2361b-103">NOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2361b-104">Funkcja `NOW` zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę serwera aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2361b-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="2361b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2361b-105">Syntax</span></span>

```vb
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="2361b-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="2361b-106">Return values</span></span>

<span data-ttu-id="2361b-107">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="2361b-107">*DateTime*</span></span>

<span data-ttu-id="2361b-108">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="2361b-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="2361b-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="2361b-109">Example</span></span>

<span data-ttu-id="2361b-110">Funkcja `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` zwraca wartość daty/godziny bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="2361b-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2361b-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2361b-111">Additional resources</span></span>

[<span data-ttu-id="2361b-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="2361b-112">Date and time functions</span></span>](er-functions-category-datetime.md)
