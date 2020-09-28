---
title: SESSIONNOW, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SESSIONNOW w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 00c41564b18eed477e1cefb0bc3bb2bca3fa6fdd
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745472"
---
# <a name="sessionnow-er-function"></a><span data-ttu-id="1e5ba-103">SESSIONNOW, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="1e5ba-103">SESSIONNOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1e5ba-104">Funkcja `SESSIONNOW` zwraca wartość *Data/godzina*, która reprezentuje bieżącą datę i godzinę sesji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1e5ba-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e5ba-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="1e5ba-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="1e5ba-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="1e5ba-106">Return values</span></span>

<span data-ttu-id="1e5ba-107">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="1e5ba-107">*DateTime*</span></span>

<span data-ttu-id="1e5ba-108">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="1e5ba-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="1e5ba-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="1e5ba-109">Example</span></span>

<span data-ttu-id="1e5ba-110">Funkcja `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` zwraca bieżącą datę/godzinę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24.12.2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.</span><span class="sxs-lookup"><span data-stu-id="1e5ba-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1e5ba-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1e5ba-111">Additional resources</span></span>

[<span data-ttu-id="1e5ba-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="1e5ba-112">Date and time functions</span></span>](er-functions-category-datetime.md)
