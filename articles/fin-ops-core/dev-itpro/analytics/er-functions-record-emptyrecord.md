---
title: EMPTYRECORD, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji EMPTYRECORD w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 1cf23f11fa92adfb7a050efd9c68e80e1bee621f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916897"
---
# <span data-ttu-id="41659-103"><a name="EMPTYRECORD">EMPTYRECORD, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="41659-103"><a name="EMPTYRECORD">EMPTYRECORD ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="41659-104">Funkcja `EMPTYRECORD` zwraca pustą wartość *Kontener (rekord)*, która ma tę samą strukturę, co wybrana lista rekordów lub rekord.</span><span class="sxs-lookup"><span data-stu-id="41659-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="41659-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="41659-105">Syntax</span></span>

```
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="41659-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="41659-106">Arguments</span></span>

<span data-ttu-id="41659-107">`list`: *Lista rekordów* lub *Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="41659-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="41659-108">Prawidłowa ścieżka elementu źródła danych typu *Lista rekordów* lub *Kontener (rekord)*.</span><span class="sxs-lookup"><span data-stu-id="41659-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="41659-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="41659-109">Return values</span></span>

<span data-ttu-id="41659-110">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="41659-110">*Container (record)*</span></span>

<span data-ttu-id="41659-111">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="41659-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="41659-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="41659-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="41659-113">Rekord null jest rekordem, w którym wszystkie pola mają wartość pustą.</span><span class="sxs-lookup"><span data-stu-id="41659-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="41659-114">Wartość pusta to **0** (zero) w przypadku liczb, pusty ciąg w przypadku ciągów tekstowych, itd.</span><span class="sxs-lookup"><span data-stu-id="41659-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="41659-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="41659-115">Example</span></span>

<span data-ttu-id="41659-116">Funkcja `EMPTYRECORD (SPLIT ("abc", 1))` zwraca nowy pusty rekord, która ma taką samą strukturę jak lista zwracana przez używaną funkcję `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="41659-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="41659-117">Aby uzyskać więcej informacji, zobacz [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="41659-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="41659-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="41659-118">Additional resources</span></span>

[<span data-ttu-id="41659-119">Funkcje zapisu</span><span class="sxs-lookup"><span data-stu-id="41659-119">Record functions</span></span>](er-functions-category-record.md)
