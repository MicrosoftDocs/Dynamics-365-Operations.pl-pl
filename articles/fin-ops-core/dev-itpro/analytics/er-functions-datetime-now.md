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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cffb23afa4cb347d2840b099b0b49a71150d87d8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917564"
---
# <span data-ttu-id="ecc70-103"><a name="NOW">NOW, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="ecc70-103"><a name="NOW">NOW ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ecc70-104">Funkcja `NOW` zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę serwera aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ecc70-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="ecc70-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ecc70-105">Syntax</span></span>

```
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="ecc70-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="ecc70-106">Return values</span></span>

<span data-ttu-id="ecc70-107">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="ecc70-107">*DateTime*</span></span>

<span data-ttu-id="ecc70-108">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="ecc70-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="ecc70-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="ecc70-109">Example</span></span>

<span data-ttu-id="ecc70-110">Funkcja `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` zwraca wartość daty/godziny bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="ecc70-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ecc70-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ecc70-111">Additional resources</span></span>

[<span data-ttu-id="ecc70-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="ecc70-112">Date and time functions</span></span>](er-functions-category-datetime.md)
