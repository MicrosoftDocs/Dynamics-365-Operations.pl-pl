---
title: FIRST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FIRST w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 3ed0e0aaf29e2a67a4842d71121f1adc24f524f7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745232"
---
# <a name="first-er-function"></a><span data-ttu-id="da43d-103">FIRST, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="da43d-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da43d-104">Funkcja `FIRST` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ta lista nie jest pusta.</span><span class="sxs-lookup"><span data-stu-id="da43d-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="da43d-105">Jeśli lista jest pusta, ta funkcja zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="da43d-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="da43d-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="da43d-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="da43d-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="da43d-107">Arguments</span></span>

<span data-ttu-id="da43d-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="da43d-108">`list`: *Record list*</span></span>

<span data-ttu-id="da43d-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="da43d-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="da43d-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="da43d-110">Return values</span></span>

<span data-ttu-id="da43d-111">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="da43d-111">*Container (record)*</span></span>

<span data-ttu-id="da43d-112">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="da43d-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="da43d-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="da43d-113">Example 1</span></span>

<span data-ttu-id="da43d-114">Wyrażenie `FIRST(SPLIT("ABC",1)).Value` zwraca wartość tekstową **"A"**.</span><span class="sxs-lookup"><span data-stu-id="da43d-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="da43d-115">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="da43d-115">Example 2</span></span>

<span data-ttu-id="da43d-116">Wyrażenie `FIRST(SPLIT("",1)).Value` zgłasza wyjątek w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="da43d-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da43d-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="da43d-117">Additional resources</span></span>

[<span data-ttu-id="da43d-118">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="da43d-118">List functions</span></span>](er-functions-category-list.md)
