---
title: SPLITLIST, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SPLITLIST w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 03/15/2021
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
ms.openlocfilehash: 99e199e238b3132622a8b305895637b430e8f6d2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745576"
---
# <a name="splitlist-er-function"></a><span data-ttu-id="dcb72-103">SPLITLIST, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="dcb72-103">SPLITLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dcb72-104">Funkcja `SPLITLIST` dzieli określoną listę na listy podrzędne (lub partie), z których każda zawiera określoną liczbę rekordów.</span><span class="sxs-lookup"><span data-stu-id="dcb72-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="dcb72-105">Zwraca ona wynik jako nową wartość typu *Lista rekordów*, która składa się z partii.</span><span class="sxs-lookup"><span data-stu-id="dcb72-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="dcb72-106">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="dcb72-106">Syntax 1</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a><span data-ttu-id="dcb72-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="dcb72-107">Syntax 2</span></span>

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a><span data-ttu-id="dcb72-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="dcb72-108">Arguments</span></span>

<span data-ttu-id="dcb72-109">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="dcb72-109">`list`: *Record list*</span></span>

<span data-ttu-id="dcb72-110">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="dcb72-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="dcb72-111">`number`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="dcb72-111">`number`: *Integer*</span></span>

<span data-ttu-id="dcb72-112">Maksymalna liczba rekordów na partię.</span><span class="sxs-lookup"><span data-stu-id="dcb72-112">The maximum number of records per batch.</span></span>

<span data-ttu-id="dcb72-113">`on-demand reading flag`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="dcb72-113">`on-demand reading flag`: *Boolean*</span></span>

<span data-ttu-id="dcb72-114">Wartość *logiczna* określająca, czy elementy podlist powinny być generowane na żądanie.</span><span class="sxs-lookup"><span data-stu-id="dcb72-114">A *Boolean* value that specifies whether elements of sublists should be generated on demand.</span></span>

## <a name="return-values"></a><span data-ttu-id="dcb72-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="dcb72-115">Return values</span></span>

<span data-ttu-id="dcb72-116">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="dcb72-116">*Record list*</span></span>

<span data-ttu-id="dcb72-117">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="dcb72-117">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="dcb72-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="dcb72-118">Usage notes</span></span>

<span data-ttu-id="dcb72-119">Zwracana jest lista partii zawierająca następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="dcb72-119">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="dcb72-120">**Value:** *Lista*</span><span class="sxs-lookup"><span data-stu-id="dcb72-120">**Value:** *List*</span></span>

    <span data-ttu-id="dcb72-121">Lista rekordów należących do bieżącej partii.</span><span class="sxs-lookup"><span data-stu-id="dcb72-121">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="dcb72-122">**BatchNumber:** *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="dcb72-122">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="dcb72-123">Numer bieżącej partii na zwróconej liście.</span><span class="sxs-lookup"><span data-stu-id="dcb72-123">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="dcb72-124">Gdy flaga odczytu na żądanie ma wartość **Prawda**, podlisty są generowane na żądanie, co pozwala na zmniejszenie zużycia pamięci, ale może spowodować uszkodzenie wydajności, jeśli elementy nie są używane sekwencyjnie.</span><span class="sxs-lookup"><span data-stu-id="dcb72-124">When the on-demand reading flag is set to **True**, sublists are generated upon request which allows for a reduction in memory consumption but may cause performance degradation if elements aren't used sequentially.</span></span>

## <a name="example"></a><span data-ttu-id="dcb72-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="dcb72-125">Example</span></span>

<span data-ttu-id="dcb72-126">Na poniższej ilustracji źródło danych **Lines** jest tworzone jako lista z trzema rekordami.</span><span class="sxs-lookup"><span data-stu-id="dcb72-126">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="dcb72-127">Lista jest podzielona na partie, z których każdy zawiera maksymalnie dwa rekordy.</span><span class="sxs-lookup"><span data-stu-id="dcb72-127">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="dcb72-128">Na ilustracji poniżej widać zaprojektowany układ formatu.</span><span class="sxs-lookup"><span data-stu-id="dcb72-128">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="dcb72-129">W tym układzie formatu są tworzone wiązania ze źródłem danych **Lines** w celu wygenerowania danych wyjściowych w formacie XML</span><span class="sxs-lookup"><span data-stu-id="dcb72-129">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="dcb72-130">Te dane wyjściowe reprezentują poszczególne węzły każdej partii i zawartych w niej rekordów.</span><span class="sxs-lookup"><span data-stu-id="dcb72-130">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="dcb72-131">Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.</span><span class="sxs-lookup"><span data-stu-id="dcb72-131">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="dcb72-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="dcb72-132">Additional resources</span></span>

[<span data-ttu-id="dcb72-133">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="dcb72-133">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
