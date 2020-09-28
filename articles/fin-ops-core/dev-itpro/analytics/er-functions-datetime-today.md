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
ms.openlocfilehash: e2ee153c1dde99810a78ed15c7505fa705088797
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745448"
---
# <a name="today-er-function"></a><span data-ttu-id="090a1-103">TODAY, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="090a1-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="090a1-104">Funkcja `TODAY` zwraca wartość *Data*, która reprezentuje bieżącą datę serwera aplikacji.</span><span class="sxs-lookup"><span data-stu-id="090a1-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="090a1-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="090a1-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="090a1-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="090a1-106">Return values</span></span>

<span data-ttu-id="090a1-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="090a1-107">*Date*</span></span>

<span data-ttu-id="090a1-108">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="090a1-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="090a1-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="090a1-109">Example</span></span>

<span data-ttu-id="090a1-110">Funkcja `DATEFORMAT (TODAY (), "dd-MM-yyyy")` zwraca datę bieżącego serwera aplikacji, 24 grudnia 2015 roku, jako ciąg **"24-12-2015"**, zgodnie z określonym formatem niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="090a1-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="090a1-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="090a1-111">Additional resources</span></span>

[<span data-ttu-id="090a1-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="090a1-112">Date and time functions</span></span>](er-functions-category-datetime.md)
