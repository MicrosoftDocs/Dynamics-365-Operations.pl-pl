---
title: FIRSTORNULL, funkcja ER
description: Ten temat zawiera objaśnienie sposobu używania funkcji FIRSTORNULL w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 075b2e064641061adf5404591a784311b6d28697
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917334"
---
# <span data-ttu-id="a4818-103"><a name="FIRSTORNULL">FIRSTORNULL, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="a4818-103"><a name="FIRSTORNULL">FIRSTORNULL ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a4818-104">Funkcja `FIRSTORNULL` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ten rekord nie jest pusty.</span><span class="sxs-lookup"><span data-stu-id="a4818-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="a4818-105">Jeśli rekord jest pusty, ta funkcja zwraca wartość null typu *Kontener (rekord)*.</span><span class="sxs-lookup"><span data-stu-id="a4818-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4818-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="a4818-106">Syntax</span></span>

```
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="a4818-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="a4818-107">Arguments</span></span>

<span data-ttu-id="a4818-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="a4818-108">`list`: *Record list*</span></span>

<span data-ttu-id="a4818-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="a4818-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a4818-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="a4818-110">Return values</span></span>

<span data-ttu-id="a4818-111">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="a4818-111">*Container (record)*</span></span>

<span data-ttu-id="a4818-112">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="a4818-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="a4818-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="a4818-113">Example</span></span>

<span data-ttu-id="a4818-114">Wyrażenie `FIRSTORNULL(SPLIT("",1)).Value` zwraca pusty ciąg (**""**).</span><span class="sxs-lookup"><span data-stu-id="a4818-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a4818-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a4818-115">Additional resources</span></span>

[<span data-ttu-id="a4818-116">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="a4818-116">List functions</span></span>](er-functions-category-list.md)
