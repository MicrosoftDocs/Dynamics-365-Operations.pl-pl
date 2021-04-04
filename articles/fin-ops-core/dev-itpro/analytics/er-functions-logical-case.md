---
title: CASE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CASE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: f466e3ffe368bf30236060d820621e723106fc1d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562476"
---
# <a name="case-er-function"></a><span data-ttu-id="4b9ff-103">CASE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="4b9ff-103">CASE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b9ff-104">Funkcja `CASE` oblicza wartość określonego wyrażenia względem określonych alternatywnych opcji i zwraca wynik pierwszej opcji, która jest równa wartości określonego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-104">The `CASE` function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="4b9ff-105">W przeciwnym razie zwraca ona domyślny wynik opcjonalny, jeśli domyślny wynik jest określony jako ostatni argument wywołanej funkcji, który nie jest poprzedzony opcją.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-105">Otherwise, it returns the optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="4b9ff-106">Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b9ff-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="4b9ff-107">Syntax</span></span>

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a><span data-ttu-id="4b9ff-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="4b9ff-108">Arguments</span></span>

<span data-ttu-id="4b9ff-109">`expression`: *Typ danych pierwotnych* (wartość logiczna, numeryczna lub tekst)</span><span class="sxs-lookup"><span data-stu-id="4b9ff-109">`expression`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="4b9ff-110">Prawidłowe wyrażenie, które zwraca wartość typu danych pierwotnych.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-110">A valid expression that returns a value of the primitive data type.</span></span>

<span data-ttu-id="4b9ff-111">`option 1`: *Typ danych pierwotnych* (wartość logiczna, numeryczna lub tekst)</span><span class="sxs-lookup"><span data-stu-id="4b9ff-111">`option 1`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="4b9ff-112">Prawidłowe wyrażenie, które zwraca wartość tego samego typu danych pierwotnych jako argument `expression` wywołanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-112">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="4b9ff-113">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-113">This argument is required.</span></span>

<span data-ttu-id="4b9ff-114">`result 1`: *Dowolny z obsługiwanych typów danych*</span><span class="sxs-lookup"><span data-stu-id="4b9ff-114">`result 1`: *Any of the supported data types*</span></span>

<span data-ttu-id="4b9ff-115">Zwrócony wynik, który odpowiada poprzedniej opcji.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-115">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="4b9ff-116">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-116">This argument is required.</span></span>

<span data-ttu-id="4b9ff-117">`option N`: *Typ danych pierwotnych* (wartość logiczna, numeryczna lub tekst)</span><span class="sxs-lookup"><span data-stu-id="4b9ff-117">`option N`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="4b9ff-118">Prawidłowe wyrażenie, które zwraca wartość tego samego typu danych pierwotnych jako argument `expression` wywołanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-118">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="4b9ff-119">Ten argument jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-119">This argument is optional.</span></span>

<span data-ttu-id="4b9ff-120">`result N`: *Dowolny z obsługiwanych typów danych*</span><span class="sxs-lookup"><span data-stu-id="4b9ff-120">`result N`: *Any of the supported data types*</span></span>

<span data-ttu-id="4b9ff-121">Zwrócony wynik, który odpowiada poprzedniej opcji.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-121">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="4b9ff-122">Ten argument jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-122">This argument is optional.</span></span>

<span data-ttu-id="4b9ff-123">`default result`: *Dowolny z obsługiwanych typów danych*</span><span class="sxs-lookup"><span data-stu-id="4b9ff-123">`default result`: *Any of the supported data types*</span></span>

<span data-ttu-id="4b9ff-124">Wynik, który powinien zostać zwrócony, jeśli nie ma dopasowania.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-124">The result that should be returned if there is no match.</span></span> <span data-ttu-id="4b9ff-125">Ten argument jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-125">This argument is optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="4b9ff-126">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="4b9ff-126">Return values</span></span>

<span data-ttu-id="4b9ff-127">*Dowolny z obsługiwanych typów danych*</span><span class="sxs-lookup"><span data-stu-id="4b9ff-127">*Any of the supported data types*</span></span>

<span data-ttu-id="4b9ff-128">Wynikowa wartość dowolnego z obsługiwanych typów danych.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-128">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4b9ff-129">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="4b9ff-129">Usage notes</span></span>

<span data-ttu-id="4b9ff-130">Wyjątek jest generowany w czasie wykonywania, jeśli nie ma dopasowania i opcjonalny domyślny wynik nie został zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-130">An exception is thrown at runtime if there is no match and an optional default result isn't defined.</span></span>

<span data-ttu-id="4b9ff-131">Wszystkie wyniki muszą być określone przy użyciu tego samego typu danych.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-131">All results must be specified by using the same data type.</span></span> <span data-ttu-id="4b9ff-132">Wyjątek jest zgłaszany w czasie projektowania, jeśli typy danych skonfigurowanych wyników nie są zgodne.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-132">An exception is thrown at design time if the data types of the configured results don't match.</span></span>

<span data-ttu-id="4b9ff-133">Jeśli pierwsza wartość wyniku i *N*-ta wartość wyniku są wartościami o typie danych *Kontener (rekord)* lub *Lista rekordów*, wynik ma tylko pola, które istnieją w obu wartościach.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-133">If the first result value and the *N* th result value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="4b9ff-134">Przykład</span><span class="sxs-lookup"><span data-stu-id="4b9ff-134">Example</span></span>

<span data-ttu-id="4b9ff-135">Funkcja `CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` zwraca ciąg **„WINTER”**, jeśli bieżąca data sesji aplikacji przypada w miesiącach od października do grudnia.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` returns the string **"WINTER"** if the current application session date is between October and December.</span></span> <span data-ttu-id="4b9ff-136">W przeciwnym razie zwraca ciąg pusty.</span><span class="sxs-lookup"><span data-stu-id="4b9ff-136">Otherwise, it returns a blank string.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b9ff-137">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4b9ff-137">Additional resources</span></span>

[<span data-ttu-id="4b9ff-138">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="4b9ff-138">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]