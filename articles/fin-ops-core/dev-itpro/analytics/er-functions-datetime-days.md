---
title: DAYS, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji DAYS w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 47d992d061f8664a55332024ee5c6cd41e4bc495
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743574"
---
# <a name="days-er-function"></a><span data-ttu-id="8bea1-103">DAYS, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="8bea1-103">DAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8bea1-104">Funkcja `DAYS` zwraca wartość *Liczba całkowita* reprezentującą liczbę dni między dwiema określonymi datami.</span><span class="sxs-lookup"><span data-stu-id="8bea1-104">The `DAYS` function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="8bea1-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="8bea1-105">Syntax</span></span>

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a><span data-ttu-id="8bea1-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="8bea1-106">Arguments</span></span>

<span data-ttu-id="8bea1-107">`date 1`: *Data*</span><span class="sxs-lookup"><span data-stu-id="8bea1-107">`date 1`: *Date*</span></span>

<span data-ttu-id="8bea1-108">Wartość daty, która reprezentuje datę początkową na potrzeby obliczania liczby dni.</span><span class="sxs-lookup"><span data-stu-id="8bea1-108">A date value that represents the start date for the calculation of the number of days.</span></span>

<span data-ttu-id="8bea1-109">`date 2`: *Data*</span><span class="sxs-lookup"><span data-stu-id="8bea1-109">`date 2`: *Date*</span></span>

<span data-ttu-id="8bea1-110">Wartość daty, która reprezentuje datę końcową na potrzeby obliczania liczby dni.</span><span class="sxs-lookup"><span data-stu-id="8bea1-110">A date value that represents the end date for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="8bea1-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="8bea1-111">Return values</span></span>

<span data-ttu-id="8bea1-112">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="8bea1-112">*Integer*</span></span>

<span data-ttu-id="8bea1-113">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="8bea1-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8bea1-114">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="8bea1-114">Usage notes</span></span>

<span data-ttu-id="8bea1-115">Funkcja `DAYS` zwraca wartość dodatnią, gdy pierwsza data jest późniejsza niż druga data, wartość **0** (zero), gdy pierwsza data jest równa drugiej dacie, lub wartość ujemną, gdy pierwsza data jest wcześniejsza niż druga data.</span><span class="sxs-lookup"><span data-stu-id="8bea1-115">The `DAYS` function returns a positive value when the first date is later than the second date, it returns **0** (zero) when the first date equals the second date, and it returns a negative value when the first date is earlier than the second date.</span></span>

## <a name="example"></a><span data-ttu-id="8bea1-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="8bea1-116">Example</span></span>

<span data-ttu-id="8bea1-117">Funkcja `DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` zwraca wartość **-1**.</span><span class="sxs-lookup"><span data-stu-id="8bea1-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returns **-1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8bea1-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8bea1-118">Additional resources</span></span>

[<span data-ttu-id="8bea1-119">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="8bea1-119">Date and time functions</span></span>](er-functions-category-datetime.md)
