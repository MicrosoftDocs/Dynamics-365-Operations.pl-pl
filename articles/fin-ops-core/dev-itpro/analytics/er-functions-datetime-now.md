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
ms.openlocfilehash: e8c411e1ce9656ffa35986f1ceef712c9def1e6b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743526"
---
# <a name="now-er-function"></a><span data-ttu-id="ac7bd-103">NOW, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="ac7bd-103">NOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac7bd-104">Funkcja `NOW` zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę serwera aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ac7bd-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac7bd-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ac7bd-105">Syntax</span></span>

```vb
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="ac7bd-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="ac7bd-106">Return values</span></span>

<span data-ttu-id="ac7bd-107">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="ac7bd-107">*DateTime*</span></span>

<span data-ttu-id="ac7bd-108">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="ac7bd-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="ac7bd-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="ac7bd-109">Example</span></span>

<span data-ttu-id="ac7bd-110">Funkcja `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` zwraca wartość daty/godziny bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="ac7bd-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac7bd-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ac7bd-111">Additional resources</span></span>

[<span data-ttu-id="ac7bd-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="ac7bd-112">Date and time functions</span></span>](er-functions-category-datetime.md)
