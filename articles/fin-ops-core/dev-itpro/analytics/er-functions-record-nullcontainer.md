---
title: NULLCONTAINER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NULLCONTAINER w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: ea71bfc4b30164fd32e804bf83a46c49cd18d155
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041476"
---
# <span data-ttu-id="fd665-103"><a name="NULLCONTAINER">NULLCONTAINER, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="fd665-103"><a name="NULLCONTAINER">NULLCONTAINER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd665-104">Funkcja `NULLCONTAINER` zwraca pustą wartość *Kontener (rekord)*, która ma tę samą strukturę, co wybrana lista rekordów lub rekord.</span><span class="sxs-lookup"><span data-stu-id="fd665-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd665-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="fd665-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="fd665-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="fd665-106">Arguments</span></span>

<span data-ttu-id="fd665-107">`list`: *Lista rekordów* lub *Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="fd665-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="fd665-108">Prawidłowa ścieżka elementu źródła danych typu *Lista rekordów* lub *Kontener (rekord)*.</span><span class="sxs-lookup"><span data-stu-id="fd665-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="fd665-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="fd665-109">Return values</span></span>

<span data-ttu-id="fd665-110">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="fd665-110">*Container (record)*</span></span>

<span data-ttu-id="fd665-111">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="fd665-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fd665-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="fd665-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="fd665-113">Ta funkcja jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="fd665-113">This function is obsolete.</span></span> <span data-ttu-id="fd665-114">W zamian użyj funkcji `EMPTYRECORD`.</span><span class="sxs-lookup"><span data-stu-id="fd665-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="fd665-115">Aby uzyskać więcej informacji, zobacz [EMPTYCORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="fd665-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="fd665-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="fd665-116">Example</span></span>

<span data-ttu-id="fd665-117">Funkcja `NULLCONTAINER (SPLIT ("abc", 1))` zwraca nowy pusty rekord, który ma taką samą strukturę jak lista zwracana przez używaną funkcję `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="fd665-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="fd665-118">Aby uzyskać więcej informacji, zobacz [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="fd665-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fd665-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fd665-119">Additional resources</span></span>

[<span data-ttu-id="fd665-120">Funkcje zapisu</span><span class="sxs-lookup"><span data-stu-id="fd665-120">Record functions</span></span>](er-functions-category-record.md)
