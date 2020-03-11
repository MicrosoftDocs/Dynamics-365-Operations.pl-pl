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
ms.openlocfilehash: 4d10abcf15b93961bd2ba4aec22914825d9ac38c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042097"
---
# <span data-ttu-id="02200-103"><a name="FIRST">FIRST, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="02200-103"><a name="FIRST">FIRST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02200-104">Funkcja `FIRST` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ta lista nie jest pusta.</span><span class="sxs-lookup"><span data-stu-id="02200-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="02200-105">Jeśli lista jest pusta, ta funkcja zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="02200-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="02200-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="02200-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="02200-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="02200-107">Arguments</span></span>

<span data-ttu-id="02200-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="02200-108">`list`: *Record list*</span></span>

<span data-ttu-id="02200-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="02200-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="02200-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="02200-110">Return values</span></span>

<span data-ttu-id="02200-111">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="02200-111">*Container (record)*</span></span>

<span data-ttu-id="02200-112">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="02200-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="02200-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="02200-113">Example 1</span></span>

<span data-ttu-id="02200-114">Wyrażenie `FIRST(SPLIT("ABC",1)).Value` zwraca wartość tekstową **"A"**.</span><span class="sxs-lookup"><span data-stu-id="02200-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="02200-115">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="02200-115">Example 2</span></span>

<span data-ttu-id="02200-116">Wyrażenie `FIRST(SPLIT("",1)).Value` zgłasza wyjątek w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="02200-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02200-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="02200-117">Additional resources</span></span>

[<span data-ttu-id="02200-118">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="02200-118">List functions</span></span>](er-functions-category-list.md)
