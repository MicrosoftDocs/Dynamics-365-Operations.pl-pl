---
title: FIRST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FIRST w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: d30c8481866ccf3f7080197b37586a0460a4ad2c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746586"
---
# <a name="first-er-function"></a><span data-ttu-id="7622d-103">FIRST, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="7622d-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7622d-104">Funkcja `FIRST` zwraca pierwszy rekord określonej listy jako wartość *Kontener (rekord)*, jeśli ta lista nie jest pusta.</span><span class="sxs-lookup"><span data-stu-id="7622d-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="7622d-105">Jeśli lista jest pusta, ta funkcja zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="7622d-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="7622d-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="7622d-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="7622d-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="7622d-107">Arguments</span></span>

<span data-ttu-id="7622d-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="7622d-108">`list`: *Record list*</span></span>

<span data-ttu-id="7622d-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="7622d-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="7622d-110">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="7622d-110">Return values</span></span>

<span data-ttu-id="7622d-111">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="7622d-111">*Container (record)*</span></span>

<span data-ttu-id="7622d-112">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="7622d-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="7622d-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="7622d-113">Example 1</span></span>

<span data-ttu-id="7622d-114">Wyrażenie `FIRST(SPLIT("ABC",1)).Value` zwraca wartość tekstową **"A"**.</span><span class="sxs-lookup"><span data-stu-id="7622d-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="7622d-115">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="7622d-115">Example 2</span></span>

<span data-ttu-id="7622d-116">Wyrażenie `FIRST(SPLIT("",1)).Value` zgłasza wyjątek w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="7622d-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7622d-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7622d-117">Additional resources</span></span>

[<span data-ttu-id="7622d-118">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="7622d-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]