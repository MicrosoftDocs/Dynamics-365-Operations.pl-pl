---
title: FIRSTORNULL, funkcja ER
description: Ten temat zawiera objaśnienie sposobu używania funkcji FIRSTORNULL w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: 1ccc094fc468470ffc857c729b6d8402796785d7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753223"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="3c414-103">FIRSTORNULL, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="3c414-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3c414-104">Funkcja `FIRSTORNULL` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ten rekord nie jest pusty.</span><span class="sxs-lookup"><span data-stu-id="3c414-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="3c414-105">Jeśli rekord jest pusty, ta funkcja zwraca wartość null typu *Kontener (rekord)*.</span><span class="sxs-lookup"><span data-stu-id="3c414-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c414-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="3c414-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="3c414-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="3c414-107">Arguments</span></span>

<span data-ttu-id="3c414-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="3c414-108">`list`: *Record list*</span></span>

<span data-ttu-id="3c414-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="3c414-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="3c414-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="3c414-110">Return values</span></span>

<span data-ttu-id="3c414-111">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="3c414-111">*Container (record)*</span></span>

<span data-ttu-id="3c414-112">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="3c414-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="3c414-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="3c414-113">Example</span></span>

<span data-ttu-id="3c414-114">Wyrażenie `FIRSTORNULL(SPLIT("",1)).Value` zwraca pusty ciąg (**""**).</span><span class="sxs-lookup"><span data-stu-id="3c414-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3c414-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3c414-115">Additional resources</span></span>

[<span data-ttu-id="3c414-116">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="3c414-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]