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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5c52d3f999b4c6fbdea0685977ab13fca1e8ffb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679421"
---
# <a name="first-er-function"></a><span data-ttu-id="98782-103">FIRST, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="98782-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98782-104">Funkcja `FIRST` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ta lista nie jest pusta.</span><span class="sxs-lookup"><span data-stu-id="98782-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="98782-105">Jeśli lista jest pusta, ta funkcja zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="98782-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="98782-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="98782-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="98782-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="98782-107">Arguments</span></span>

<span data-ttu-id="98782-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="98782-108">`list`: *Record list*</span></span>

<span data-ttu-id="98782-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="98782-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="98782-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="98782-110">Return values</span></span>

<span data-ttu-id="98782-111">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="98782-111">*Container (record)*</span></span>

<span data-ttu-id="98782-112">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="98782-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="98782-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="98782-113">Example 1</span></span>

<span data-ttu-id="98782-114">Wyrażenie `FIRST(SPLIT("ABC",1)).Value` zwraca wartość tekstową **"A"**.</span><span class="sxs-lookup"><span data-stu-id="98782-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="98782-115">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="98782-115">Example 2</span></span>

<span data-ttu-id="98782-116">Wyrażenie `FIRST(SPLIT("",1)).Value` zgłasza wyjątek w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="98782-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98782-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="98782-117">Additional resources</span></span>

[<span data-ttu-id="98782-118">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="98782-118">List functions</span></span>](er-functions-category-list.md)
