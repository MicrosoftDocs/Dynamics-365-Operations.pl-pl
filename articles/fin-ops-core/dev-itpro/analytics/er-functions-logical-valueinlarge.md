---
title: Funkcja VALUEINLARGE ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji VALUEIN ER w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 08/17/2020
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
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 4630ec20e7cbca97c5e43093e6a888a5e09f41a3
ms.sourcegitcommit: 38ad6f791c3d5688a5dc201a234ba89f155f7f03
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "3705150"
---
# <a name="valueinlarge-er-function"></a><span data-ttu-id="a145d-103">Funkcja VALUEINLARGE ER</span><span class="sxs-lookup"><span data-stu-id="a145d-103">VALUEINLARGE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a145d-104">Funkcja `VALUEINLARGE` określa, czy podane dane wejściowe typu *Int64* lub *Integer* pasują do którejkolwiek wartości określonego elementu na podanej liście.</span><span class="sxs-lookup"><span data-stu-id="a145d-104">The `VALUEINLARGE` function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="a145d-105">Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy.</span><span class="sxs-lookup"><span data-stu-id="a145d-105">The function returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="a145d-106">W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a145d-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> <span data-ttu-id="a145d-107">Aby zrozumieć różnicę związaną z funkcją `VALUEIN`, zapoznaj się z sekcją [Wskazówki użycia](#usage_note), znajdującą się w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="a145d-107">To understand the difference with the `VALUEIN` function, see the [Usage note](#usage_note) section later in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="a145d-108">Składnia</span><span class="sxs-lookup"><span data-stu-id="a145d-108">Syntax</span></span>

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="a145d-109">Argumenty</span><span class="sxs-lookup"><span data-stu-id="a145d-109">Arguments</span></span>

<span data-ttu-id="a145d-110">`input`: *Pole*</span><span class="sxs-lookup"><span data-stu-id="a145d-110">`input`: *Field*</span></span>

<span data-ttu-id="a145d-111">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="a145d-111">The valid path of a data source item of the *Record list* type.</span></span> <span data-ttu-id="a145d-112">To z wartością tego elementu będzie dokonywane porównanie.</span><span class="sxs-lookup"><span data-stu-id="a145d-112">The value of this item will be matched.</span></span>

<span data-ttu-id="a145d-113">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="a145d-113">`list`: *Record list*</span></span>

<span data-ttu-id="a145d-114">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="a145d-114">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="a145d-115">`list item expression`: *Wyrażenie*</span><span class="sxs-lookup"><span data-stu-id="a145d-115">`list item expression`: *Expression*</span></span>

<span data-ttu-id="a145d-116">Prawidłowe wyrażenie warunkowe, które wskazuje na albo zawiera pojedyncze pole określonej listy, która ma być używana do porównania.</span><span class="sxs-lookup"><span data-stu-id="a145d-116">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="a145d-117">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="a145d-117">Return values</span></span>

<span data-ttu-id="a145d-118">*Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="a145d-118">*Boolean*</span></span>

<span data-ttu-id="a145d-119">Wyjściowa *wartość logiczna*.</span><span class="sxs-lookup"><span data-stu-id="a145d-119">The resulting *Boolean* value.</span></span>

## <a name=""></a><span data-ttu-id="a145d-120"><a name="usage_note">Uwagi dotyczące użytkowania</a></span><span class="sxs-lookup"><span data-stu-id="a145d-120"><a name="usage_note">Usage notes</a></span></span>

<span data-ttu-id="a145d-121">Jeśli określone dane reprezentują typ elementu źródła danych taki jak *Int64* lub *Integer*, do którego wywołanie jest możliwe do przetłumaczenia na bezpośrednią instrukcję SQL, określona lista jest konwertowana na tabelę tymczasową SQL, a w bazie danych dokonywane jest dopasowanie przez wykonanie pojedynczej kwerendy `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="a145d-121">When the specified input represents an *Int64* or *Integer* type of a data source item, the call to which is translatable to a direct SQL statement, the specified list is converted to a temporary SQL table and matching is performed in the database by executing a single `EXISTS JOIN` query.</span></span> <span data-ttu-id="a145d-122">W przeciwnym razie funkcja działa jako funkcja [`VALUEIN`](er-functions-logical-valuein.md).</span><span class="sxs-lookup"><span data-stu-id="a145d-122">Otherwise, this function works as the [`VALUEIN`](er-functions-logical-valuein.md) function.</span></span>

<span data-ttu-id="a145d-123">Gdy określone dane wejściowe reprezentują element źródła danych zaprojektowany jako element inny niż *Int64* i *Integer*, błąd występuje w czasie projektowania, informując o tym, że funkcja `VALUEINLARGE` nie ma zastosowania dla skonfigurowanego wyrażenia encji.</span><span class="sxs-lookup"><span data-stu-id="a145d-123">When the specified input represents a data source item that is designed as an item other than *Int64* and *Integer* type, an error occurs at design time informing you that the `VALUEINLARGE` function is not applicable for the configured ER expression.</span></span>

<span data-ttu-id="a145d-124">Gdy jest wykonywane wyrażenie funkcyjne `VALUEINLARGE` i w zakresie tej operacji jest używana więcej niż jedna tabela tymczasowa, wystąpi błąd środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="a145d-124">When the `VALUEINLARGE` function expression is executed and more than one temporary table is used in scope of this execution, a runtime error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="a145d-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="a145d-125">Example</span></span>

<span data-ttu-id="a145d-126">Definiuje się następujące źródła danych w mapowaniu modelu:</span><span class="sxs-lookup"><span data-stu-id="a145d-126">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="a145d-127">Źródło danych **In** typu *Rekordy tabeli*.</span><span class="sxs-lookup"><span data-stu-id="a145d-127">The **In** data source of the *Table records* type.</span></span>
    - <span data-ttu-id="a145d-128">To źródło danych odnosi się do tabeli **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="a145d-128">This data source refers to the **Intrastat** table.</span></span>
    - <span data-ttu-id="a145d-129">Opcja **Międzyfirmowe** jest ustawiona na wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="a145d-129">The **Cross-company** option is set to **No**.</span></span>
- <span data-ttu-id="a145d-130">Źródło danych **InMemory** typu *Pole obliczeniowe*.</span><span class="sxs-lookup"><span data-stu-id="a145d-130">The **InMemory** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="a145d-131">To źródło danych zawiera wyrażenie `WHERE (In, In.Port <> "")`.</span><span class="sxs-lookup"><span data-stu-id="a145d-131">This data source contains the expression `WHERE (In, In.Port <> "")`.</span></span>
- <span data-ttu-id="a145d-132">Źródło danych **InFiltered** typu *Pole obliczeniowe*.</span><span class="sxs-lookup"><span data-stu-id="a145d-132">The **InFiltered** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="a145d-133">To źródło danych zawiera wyrażenie `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span><span class="sxs-lookup"><span data-stu-id="a145d-133">This data source contains the expression `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span></span>

<span data-ttu-id="a145d-134">Jeśli źródło danych **InFiltered** jest wywoływane w kontekście firmy **DEMF**, w bazie danych aplikacji zostanie utworzona nowa tabela tymczasowa, a w tabeli zostanie wstawiona lista kodów identyfikacyjnych rekordów z kodami identyfikującymi rekordy, a w celu zwrócenia filtrowanych rekordów generowana jest instrukcja SQL tabeli **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="a145d-134">When the data source **InFiltered** is called under the context of the company **DEMF**, a new temporary table is created in the application database, the collected in memory list of record identification codes are inserted to this table, and the following SQL statement is generated to return filtered records of the **Intrastat** table.</span></span>

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a><span data-ttu-id="a145d-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a145d-135">Additional resources</span></span>

[<span data-ttu-id="a145d-136">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="a145d-136">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="a145d-137">funkcje VALUEIN</span><span class="sxs-lookup"><span data-stu-id="a145d-137">VALUEIN functions</span></span>](er-functions-logical-valuein.md)
