---
title: TODAY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TODAY w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 94ef15d1971287e8bf13944bc8f693b567950031
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411444"
---
# <a name=""></a><span data-ttu-id="59d3d-103"><a name="TODAY">TODAY, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="59d3d-103"><a name="TODAY">TODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59d3d-104">Funkcja `TODAY` zwraca wartość *Data*, która reprezentuje bieżącą datę serwera aplikacji.</span><span class="sxs-lookup"><span data-stu-id="59d3d-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="59d3d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="59d3d-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="59d3d-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="59d3d-106">Return values</span></span>

<span data-ttu-id="59d3d-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="59d3d-107">*Date*</span></span>

<span data-ttu-id="59d3d-108">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="59d3d-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="59d3d-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="59d3d-109">Example</span></span>

<span data-ttu-id="59d3d-110">Funkcja `DATEFORMAT (TODAY (), "dd-MM-yyyy")` zwraca datę bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako ciąg **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="59d3d-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59d3d-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="59d3d-111">Additional resources</span></span>

[<span data-ttu-id="59d3d-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="59d3d-112">Date and time functions</span></span>](er-functions-category-datetime.md)
