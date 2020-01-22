---
title: SPLITLIST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SPLITLIST w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: b324d42a53b35074ba62ccf3df7b77cb4db70450
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917219"
---
# <span data-ttu-id="c39fb-103"><a name="SPLITLIST">SPLITLIST, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="c39fb-103"><a name="SPLITLIST">SPLITLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c39fb-104">Funkcja `SPLITLIST` dzieli określoną listę na listy podrzędne (lub partie), z których każda zawiera określoną liczbę rekordów.</span><span class="sxs-lookup"><span data-stu-id="c39fb-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="c39fb-105">Zwraca ona wynik jako nową wartość typu *Lista rekordów*, która składa się z partii.</span><span class="sxs-lookup"><span data-stu-id="c39fb-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="c39fb-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="c39fb-106">Syntax</span></span>

```
SPLITLIST (list, number)
```

## <a name="arguments"></a><span data-ttu-id="c39fb-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c39fb-107">Arguments</span></span>

<span data-ttu-id="c39fb-108">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="c39fb-108">`list`: *Record list*</span></span>

<span data-ttu-id="c39fb-109">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="c39fb-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="c39fb-110">`number`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="c39fb-110">`number`: *Integer*</span></span>

<span data-ttu-id="c39fb-111">Maksymalna liczba rekordów na partię.</span><span class="sxs-lookup"><span data-stu-id="c39fb-111">The maximum number of records per batch.</span></span>

## <a name="return-values"></a><span data-ttu-id="c39fb-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c39fb-112">Return values</span></span>

<span data-ttu-id="c39fb-113">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="c39fb-113">*Record list*</span></span>

<span data-ttu-id="c39fb-114">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="c39fb-114">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c39fb-115">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="c39fb-115">Usage notes</span></span>

<span data-ttu-id="c39fb-116">Zwracana jest lista partii zawierająca następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="c39fb-116">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="c39fb-117">**Value:** *Lista*</span><span class="sxs-lookup"><span data-stu-id="c39fb-117">**Value:** *List*</span></span>

    <span data-ttu-id="c39fb-118">Lista rekordów należących do bieżącej partii.</span><span class="sxs-lookup"><span data-stu-id="c39fb-118">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="c39fb-119">**BatchNumber:** *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="c39fb-119">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="c39fb-120">Numer bieżącej partii na zwróconej liście.</span><span class="sxs-lookup"><span data-stu-id="c39fb-120">The number of the current batch in the returned list.</span></span>

## <a name="example"></a><span data-ttu-id="c39fb-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="c39fb-121">Example</span></span>

<span data-ttu-id="c39fb-122">Na poniższej ilustracji źródło danych **Lines** jest tworzone jako lista z trzema rekordami.</span><span class="sxs-lookup"><span data-stu-id="c39fb-122">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="c39fb-123">Lista jest podzielona na partie, z których każdy zawiera maksymalnie dwa rekordy.</span><span class="sxs-lookup"><span data-stu-id="c39fb-123">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="c39fb-124">Na ilustracji poniżej widać zaprojektowany układ formatu.</span><span class="sxs-lookup"><span data-stu-id="c39fb-124">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="c39fb-125">W tym układzie formatu są tworzone wiązania ze źródłem danych **Lines** w celu wygenerowania danych wyjściowych w formacie XML</span><span class="sxs-lookup"><span data-stu-id="c39fb-125">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="c39fb-126">Te dane wyjściowe reprezentują poszczególne węzły każdej partii i zawartych w niej rekordów.</span><span class="sxs-lookup"><span data-stu-id="c39fb-126">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="c39fb-127">Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.</span><span class="sxs-lookup"><span data-stu-id="c39fb-127">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="c39fb-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c39fb-128">Additional resources</span></span>

[<span data-ttu-id="c39fb-129">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="c39fb-129">List functions</span></span>](er-functions-category-list.md)
