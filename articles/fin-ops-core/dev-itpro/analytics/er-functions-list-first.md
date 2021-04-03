---
title: FIRST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FIRST w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: ec94a27776cf1069b50b5437f4d167019fdef120
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564742"
---
# <a name="first-er-function"></a><span data-ttu-id="31072-103">FIRST, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="31072-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31072-104">Funkcja `FIRST` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ta lista nie jest pusta.</span><span class="sxs-lookup"><span data-stu-id="31072-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="31072-105">Jeśli lista jest pusta, ta funkcja zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="31072-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="31072-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="31072-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="31072-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="31072-107">Arguments</span></span>

<span data-ttu-id="31072-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="31072-108">`list`: *Record list*</span></span>

<span data-ttu-id="31072-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="31072-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="31072-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="31072-110">Return values</span></span>

<span data-ttu-id="31072-111">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="31072-111">*Container (record)*</span></span>

<span data-ttu-id="31072-112">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="31072-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="31072-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="31072-113">Example 1</span></span>

<span data-ttu-id="31072-114">Wyrażenie `FIRST(SPLIT("ABC",1)).Value` zwraca wartość tekstową **"A"**.</span><span class="sxs-lookup"><span data-stu-id="31072-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="31072-115">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="31072-115">Example 2</span></span>

<span data-ttu-id="31072-116">Wyrażenie `FIRST(SPLIT("",1)).Value` zgłasza wyjątek w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="31072-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31072-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="31072-117">Additional resources</span></span>

[<span data-ttu-id="31072-118">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="31072-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]