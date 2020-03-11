---
title: VALUEIN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji VALUEIN w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: d0df97234df41d11897473dea4e85354e82d36ec
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041706"
---
# <span data-ttu-id="622a7-103"><a name="VALUEIN">VALUEIN, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="622a7-103"><a name="VALUEIN">VALUEIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="622a7-104">Funkcja `VALUEIN` określa, czy podane dane wejściowe pasują do którejkolwiek wartości określonego elementu na podanej liście.</span><span class="sxs-lookup"><span data-stu-id="622a7-104">The `VALUEIN` function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="622a7-105">Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy.</span><span class="sxs-lookup"><span data-stu-id="622a7-105">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="622a7-106">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="622a7-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="622a7-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="622a7-107">Syntax</span></span>

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="622a7-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="622a7-108">Arguments</span></span>

<span data-ttu-id="622a7-109">`input`: *Pole*</span><span class="sxs-lookup"><span data-stu-id="622a7-109">`input`: *Field*</span></span>

<span data-ttu-id="622a7-110">Prawidłowa ścieżka elementu źródła danych typu *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="622a7-110">The valid path of an item of a data source of the *Record list* type.</span></span> <span data-ttu-id="622a7-111">To z wartością tego elementu będzie dokonywane porównanie.</span><span class="sxs-lookup"><span data-stu-id="622a7-111">The value of this item will be matched.</span></span>

<span data-ttu-id="622a7-112">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="622a7-112">`list`: *Record list*</span></span>

<span data-ttu-id="622a7-113">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="622a7-113">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="622a7-114">`list item expression`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="622a7-114">`list item expression`: *Boolean*</span></span>

<span data-ttu-id="622a7-115">Prawidłowe wyrażenie warunkowe, które wskazuje na albo zawiera pojedyncze pole określonej listy, która ma być używana do porównania.</span><span class="sxs-lookup"><span data-stu-id="622a7-115">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="622a7-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="622a7-116">Return values</span></span>

<span data-ttu-id="622a7-117">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="622a7-117">*Boolean*</span></span>

<span data-ttu-id="622a7-118">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="622a7-118">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="622a7-119">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="622a7-119">Usage notes</span></span>

<span data-ttu-id="622a7-120">Zasadniczo funkcja `VALUEIN` jest przekształcana na zbiór warunków **OR**.</span><span class="sxs-lookup"><span data-stu-id="622a7-120">In general, the `VALUEIN` function is translated to a set of **OR** conditions.</span></span>

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

<span data-ttu-id="622a7-121">W niektórych przypadkach można ją przekształcić na instrukcję SQL bazy danych za pomocą operatora `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="622a7-121">In some cases, it can be translated to a database SQL statement by using the `EXISTS JOIN` operator.</span></span>

## <a name="example-1"></a><span data-ttu-id="622a7-122">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="622a7-122">Example 1</span></span>

<span data-ttu-id="622a7-123">W mapowaniu modelu definiujesz źródło danych **Lista** typu *Pole obliczeniowe*.</span><span class="sxs-lookup"><span data-stu-id="622a7-123">In your model mapping, you define the **List** data source of the *Calculated field* type.</span></span> <span data-ttu-id="622a7-124">To źródło danych zawiera wyrażenie `SPLIT ("a,b,c", ",")`.</span><span class="sxs-lookup"><span data-stu-id="622a7-124">This data source contains the expression `SPLIT ("a,b,c", ",")`.</span></span>

<span data-ttu-id="622a7-125">Gdy źródło danych jest wywoływane, jeśli zostało skonfigurowane jako wyrażenie `VALUEIN ("B", List, List.Value)`, zwraca wartość **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="622a7-125">When a data source is called, if it has been configured as the `VALUEIN ("B", List, List.Value)` expression, it returns **TRUE**.</span></span> <span data-ttu-id="622a7-126">W tym przypadku funkcja `VALUEIN` jest przekształcana na następujący zbiór warunków: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, gdzie `("B" = "b")` równa się **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="622a7-126">In this case, the `VALUEIN` function is translated to the following set of conditions: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, where `("B" = "b")` equals **TRUE**.</span></span>

<span data-ttu-id="622a7-127">Gdy źródło danych jest wywoływane, jeśli zostało skonfigurowane jako wyrażenie `VALUEIN ("B", List, LEFT(List.Value, 0))`, zwraca wartość **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="622a7-127">When a data source is called, if it has been configured as the `VALUEIN ("B", List, LEFT(List.Value, 0))` expression, it returns **FALSE**.</span></span> <span data-ttu-id="622a7-128">W tym przypadku funkcja `VALUEIN` jest przekształcana na następujący warunek: , gdzie `("B" = "")` nie równa się **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="622a7-128">In this case, the `VALUEIN` function is translated to the following condition: `("B" = "")`, which doesn't equal **TRUE**.</span></span>

<span data-ttu-id="622a7-129">Górny limit liczby znaków w treści takiego warunku to 32 768 znaków.</span><span class="sxs-lookup"><span data-stu-id="622a7-129">The upper limit for the number of characters in the text of such a condition is 32,768 characters.</span></span> <span data-ttu-id="622a7-130">Z tego względu nie należy tworzyć źródeł danych, które w czasie wykonywania mogą spowodować przekroczenie tego limitu.</span><span class="sxs-lookup"><span data-stu-id="622a7-130">Therefore, you should not create data sources that might exceed this limit at runtime.</span></span> <span data-ttu-id="622a7-131">W przypadku przekroczenia limitu aplikacja przestaje działać i zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="622a7-131">If the limit is exceeded, the application stops running, and an exception is thrown.</span></span> <span data-ttu-id="622a7-132">Na przykład taka sytuacja może wystąpić, jeśli źródło danych jest skonfigurowane za pomocą wyrażenia `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, a listy **List1** i **List2** zawierają bardzo dużo rekordów.</span><span class="sxs-lookup"><span data-stu-id="622a7-132">For example, this situation can occur if the data source is configured as `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, and the **List1** and **List2** lists contain a large volume of records.</span></span>

<span data-ttu-id="622a7-133">W niektórych przypadkach funkcja `VALUEIN` jest przekształcana na instrukcję bazy danych za pomocą operatora `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="622a7-133">In some cases, the `VALUEIN` function is translated to a database statement by using the `EXISTS JOIN` operator.</span></span> <span data-ttu-id="622a7-134">Takie zachowanie występuje, gdy jest używana funkcja [FILTER](er-functions-list-filter.md) i są spełnione następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="622a7-134">This behavior occurs when the [FILTER](er-functions-list-filter.md) function is used and the following conditions are met:</span></span>

- <span data-ttu-id="622a7-135">Opcja **MONITUJ O ZAPYTANIE** jest wyłączona w źródle danych funkcji `VALUEIN` odwołującej się do listy rekordów.</span><span class="sxs-lookup"><span data-stu-id="622a7-135">The **ASK FOR QUERY** option is turned off for the data source of the `VALUEIN` function that refers to the list of records.</span></span> <span data-ttu-id="622a7-136">W czasie wykonywania do tego źródła danych nie będą stosowane żadne dodatkowe warunki.</span><span class="sxs-lookup"><span data-stu-id="622a7-136">No additional conditions will be applied to this data source at runtime.</span></span>
- <span data-ttu-id="622a7-137">Nie skonfigurowano żadnych warunków zagnieżdżonych w źródle danych funkcji `VALUEIN` odwołującej się do listy rekordów.</span><span class="sxs-lookup"><span data-stu-id="622a7-137">No nested expressions are configured for the data source of the `VALUEIN` function that refers to the list of records.</span></span>
- <span data-ttu-id="622a7-138">Element listy w funkcji `VALUEIN` odwołuje się do pola podanego źródła danych, a nie do wyrażenia lub metody tego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="622a7-138">A list item of the `VALUEIN` function refers to a field of the specified data source, not to an expression or method of that data source.</span></span>

<span data-ttu-id="622a7-139">Warto rozważyć używanie tej opcji zamiast funkcji [WHERE](er-functions-list-where.md), którą opisano wcześniej w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="622a7-139">Consider using this option instead of the [WHERE](er-functions-list-where.md) function that is described earlier in this example.</span></span>

## <a name="example-2"></a><span data-ttu-id="622a7-140">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="622a7-140">Example 2</span></span>

<span data-ttu-id="622a7-141">Definiuje się następujące źródła danych w mapowaniu modelu:</span><span class="sxs-lookup"><span data-stu-id="622a7-141">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="622a7-142">Źródło danych **In** typu *Rekordy tabeli*.</span><span class="sxs-lookup"><span data-stu-id="622a7-142">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="622a7-143">To źródło danych odnosi się do tabeli Intrastat.</span><span class="sxs-lookup"><span data-stu-id="622a7-143">This data source refers to the Intrastat table.</span></span>
- <span data-ttu-id="622a7-144">Źródło danych **Port** typu *Rekordy tabeli*.</span><span class="sxs-lookup"><span data-stu-id="622a7-144">The **Port** data source of the *Table records* type.</span></span> <span data-ttu-id="622a7-145">To źródło danych odnosi się do tabeli IntrastatPort.</span><span class="sxs-lookup"><span data-stu-id="622a7-145">This data source refers to the IntrastatPort table.</span></span>

<span data-ttu-id="622a7-146">Gdy zostanie wywołane źródło danych skonfigurowane za pomocą wyrażenia `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)`, zostanie wygenerowana poniższa instrukcja SQL w celu zwrócenia odfiltrowanych rekordów tabeli Intrastat.</span><span class="sxs-lookup"><span data-stu-id="622a7-146">When a data source is called that has been configured as the `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` expression, the following SQL statement is generated to return filtered records of the Intrastat table.</span></span>

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

<span data-ttu-id="622a7-147">Dla pól **dataAreaId** zostanie wygenerowana końcowa instrukcja SQL przy użyciu operatora `IN`.</span><span class="sxs-lookup"><span data-stu-id="622a7-147">For **dataAreaId** fields, the final SQL statement is generated by the using `IN` operator.</span></span>

## <a name="example-3"></a><span data-ttu-id="622a7-148">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="622a7-148">Example 3</span></span>

<span data-ttu-id="622a7-149">Definiuje się następujące źródła danych w mapowaniu modelu:</span><span class="sxs-lookup"><span data-stu-id="622a7-149">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="622a7-150">Źródło danych **Le** typu *Pole obliczeniowe*.</span><span class="sxs-lookup"><span data-stu-id="622a7-150">The **Le** data source of the *Calculated field* type.</span></span> <span data-ttu-id="622a7-151">To źródło danych zawiera wyrażenie `SPLIT ("DEMF,GBSI,USMF", ",")`.</span><span class="sxs-lookup"><span data-stu-id="622a7-151">This data source contains the expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span></span>
- <span data-ttu-id="622a7-152">Źródło danych **In** typu *Rekordy tabeli*.</span><span class="sxs-lookup"><span data-stu-id="622a7-152">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="622a7-153">To źródło danych odnosi się do tabeli Intrastat z włączoną opcją **Między firmami**.</span><span class="sxs-lookup"><span data-stu-id="622a7-153">This data source refers to the Intrastat table, and the **Cross-company** option is turned on for it.</span></span>

<span data-ttu-id="622a7-154">Gdy zostanie wywołane źródło danych skonfigurowane za pomocą wyrażenia `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, końcowa instrukcja SQL zawiera następujący warunek.</span><span class="sxs-lookup"><span data-stu-id="622a7-154">When a data source is called that has been configured as the `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` expression, the final SQL statement contains the following condition.</span></span>

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a><span data-ttu-id="622a7-155">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="622a7-155">Additional resources</span></span>

[<span data-ttu-id="622a7-156">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="622a7-156">Logical functions</span></span>](er-functions-category-logical.md)
