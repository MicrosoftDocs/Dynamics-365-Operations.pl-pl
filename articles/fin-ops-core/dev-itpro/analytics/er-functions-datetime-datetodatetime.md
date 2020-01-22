---
title: DATETODATETIME, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DATETODATETIME w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: f9ce977b36cd96a27a228dba1bc8c8445bafd879
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916391"
---
# <span data-ttu-id="e53b8-103"><a name="DATETODATETIME">DATETODATETIME, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="e53b8-103"><a name="DATETODATETIME">DATETODATETIME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e53b8-104">Funkcja `DATETODATETIME` zwraca wartość *Data/godzina*, która jest konwertowana z danej wartości daty na wartość daty/godziny w uniwersalnym czasie koordynowanym (czas uniwersalny Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="e53b8-104">The `DATETODATETIME` function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="e53b8-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="e53b8-105">Syntax</span></span>

```
DATETODATETIME (date)
```

## <a name="arguments"></a><span data-ttu-id="e53b8-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="e53b8-106">Arguments</span></span>

<span data-ttu-id="e53b8-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="e53b8-107">`date`: *Date*</span></span>

<span data-ttu-id="e53b8-108">Wartość daty, która reprezentuje datę do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="e53b8-108">A date value that represents the date to convert.</span></span>

## <a name="return-values"></a><span data-ttu-id="e53b8-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="e53b8-109">Return values</span></span>

<span data-ttu-id="e53b8-110">*Data/godzina*</span><span class="sxs-lookup"><span data-stu-id="e53b8-110">*DateTime*</span></span>

<span data-ttu-id="e53b8-111">Wyjściowa wartość daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="e53b8-111">The resulting date/time value.</span></span>

## <a name="example-1"></a><span data-ttu-id="e53b8-112">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="e53b8-112">Example 1</span></span>

<span data-ttu-id="e53b8-113">Funkcja `DATETODATETIME (CompInfo. 'getCurrentDate()')` zwraca datę bieżącej sesji aplikacji Microsoft Dynamics 365 Finance, 24 grudnia 2015 r. jako **12/24/2015 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="e53b8-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` returns the date of the current Microsoft Dynamics 365 Finance session, December 24, 2015, as **12/24/2015 12:00:00 AM**.</span></span> <span data-ttu-id="e53b8-114">W tym przykładzie **CompInfo** jest źródłem danych modułu Raportowanie elektroniczne (ER) typu **Finance and Operations/Tabela** i odwołuje się do tabeli CompanyInfo.</span><span class="sxs-lookup"><span data-stu-id="e53b8-114">In this example, **CompInfo** is an Electronic reporting (ER) data source of the **Finance and Operations/Table** type, and it refers to the CompanyInfo table.</span></span>

## <a name="example-2"></a><span data-ttu-id="e53b8-115">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="e53b8-115">Example 2</span></span>

<span data-ttu-id="e53b8-116">Funkcja `DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` zwraca wartość daty/godziny **11/12/2019 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="e53b8-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` returns the date/time value **11/12/2019 12:00:00 AM**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e53b8-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e53b8-117">Additional resources</span></span>

[<span data-ttu-id="e53b8-118">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="e53b8-118">Date and time functions</span></span>](er-functions-category-datetime.md)
