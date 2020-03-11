---
title: NULLDATETIME, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NULLDATETIME w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 3cd4c152d4e220a2f6315265ed5e44d148134279
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042271"
---
# <span data-ttu-id="c3801-103"><a name="NULLDATETIME">NULLDATETIME, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="c3801-103"><a name="NULLDATETIME">NULLDATETIME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3801-104">Funkcja `NULLDATETIME` zwraca wartość *Data/godzina*, która reprezentuje wartość **null** daty/godziny (1 stycznia 1900) w uniwersalnym czasie koordynowanym (Czas uniwersalny Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="c3801-104">The `NULLDATETIME` function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="c3801-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c3801-105">Syntax</span></span>

```vb
NULLDATETIME ()
```

## <a name="return-values"></a><span data-ttu-id="c3801-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c3801-106">Return values</span></span>

<span data-ttu-id="c3801-107">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="c3801-107">*DateTime*</span></span>

<span data-ttu-id="c3801-108">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="c3801-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="c3801-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="c3801-109">Example</span></span>

<span data-ttu-id="c3801-110">Funkcja `DATETIMEFORMAT( NULLDATETIME(), "O")` zwraca wartość ciągu **1900-01-01T00:00:00.0000000+00:00**, gdy jest wywoływana podczas procesu, który został zainicjowany przez użytkownika aplikacji z wartością strefy czasowej **(GMT) Uniwersalny czas koordynowany** w sekcji **Preferencje dotyczące języka i kraju/regionu**.</span><span class="sxs-lookup"><span data-stu-id="c3801-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` returns the string value **1900-01-01T00:00:00.0000000+00:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT) Coordinated Universal Time** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3801-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c3801-111">Additional resources</span></span>

[<span data-ttu-id="c3801-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="c3801-112">Date and time functions</span></span>](er-functions-category-datetime.md)
