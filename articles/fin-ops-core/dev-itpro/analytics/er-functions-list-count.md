---
title: COUNT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji COUNT w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a0b780051684ef52d06a9baf78d9b513d9ac1f0e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746634"
---
# <a name="count-er-function"></a><span data-ttu-id="9e253-103">COUNT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="9e253-103">COUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e253-104">Funkcja `COUNT` zwraca wartość typu *Liczba całkowita* reprezentującą liczbę rekordów na określonej liście, jeśli lista nie jest pusta.</span><span class="sxs-lookup"><span data-stu-id="9e253-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="9e253-105">Jeśli lista jest pusta, ta funkcja zwraca wartość **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="9e253-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="9e253-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="9e253-106">Syntax</span></span>

```vb
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="9e253-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="9e253-107">Arguments</span></span>

<span data-ttu-id="9e253-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="9e253-108">`list`: *Record list*</span></span>

<span data-ttu-id="9e253-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="9e253-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="9e253-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="9e253-110">Return values</span></span>

<span data-ttu-id="9e253-111">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="9e253-111">*Integer*</span></span>

<span data-ttu-id="9e253-112">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="9e253-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="9e253-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="9e253-113">Example</span></span>

<span data-ttu-id="9e253-114">Funkcja `COUNT (SPLIT("abcd" , 3))` zwraca wartość **2**, ponieważ funkcja `SPLIT` używana w tym przykładzie tworzy listę, która składa się z dwóch rekordów.</span><span class="sxs-lookup"><span data-stu-id="9e253-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e253-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9e253-115">Additional resources</span></span>

[<span data-ttu-id="9e253-116">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="9e253-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]