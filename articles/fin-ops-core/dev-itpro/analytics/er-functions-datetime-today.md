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
ms.openlocfilehash: c7e9917dcdc45a52e0ad490f5fa194d5390cc437
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917426"
---
# <span data-ttu-id="07781-103"><a name="TODAY">TODAY, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="07781-103"><a name="TODAY">TODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07781-104">Funkcja `TODAY` zwraca wartość *Data*, która reprezentuje bieżącą datę serwera aplikacji.</span><span class="sxs-lookup"><span data-stu-id="07781-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="07781-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="07781-105">Syntax</span></span>

```
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="07781-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="07781-106">Return values</span></span>

<span data-ttu-id="07781-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="07781-107">*Date*</span></span>

<span data-ttu-id="07781-108">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="07781-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="07781-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="07781-109">Example</span></span>

<span data-ttu-id="07781-110">Funkcja `DATEFORMAT (TODAY (), "dd-MM-yyyy")` zwraca datę bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako ciąg **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="07781-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="07781-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="07781-111">Additional resources</span></span>

[<span data-ttu-id="07781-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="07781-112">Date and time functions</span></span>](er-functions-category-datetime.md)
