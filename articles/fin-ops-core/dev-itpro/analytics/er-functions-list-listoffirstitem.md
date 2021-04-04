---
title: LISTOFFIRSTITEM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LISTOFFIRSTITEM w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: f2e1f7e55c61f883aebb9d5a522a883a9a9de694
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569847"
---
# <a name="listoffirstitem-er-function"></a><span data-ttu-id="91511-103">LISTOFFIRSTITEM, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="91511-103">LISTOFFIRSTITEM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91511-104">Funkcja `LISTOFFIRSTITEM` zwraca wartość typu *Lista rekordów*, która składa się tylko z pierwszego rekordu określonej listy.</span><span class="sxs-lookup"><span data-stu-id="91511-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="91511-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="91511-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="91511-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="91511-106">Arguments</span></span>

<span data-ttu-id="91511-107">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="91511-107">`list`: *Record list*</span></span>

<span data-ttu-id="91511-108">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="91511-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="91511-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="91511-109">Return values</span></span>

<span data-ttu-id="91511-110">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="91511-110">*Record list*</span></span>

<span data-ttu-id="91511-111">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="91511-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="91511-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="91511-112">Example</span></span>

<span data-ttu-id="91511-113">Wyrażenie `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` zwraca wartość tekstową **"A"**.</span><span class="sxs-lookup"><span data-stu-id="91511-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="91511-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="91511-114">Additional resources</span></span>

[<span data-ttu-id="91511-115">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="91511-115">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]