---
title: SPLIT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SPLIT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: c171509353fed92b14ca0d7473742e4a9a54bad1
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745280"
---
# <a name="split-er-function"></a><span data-ttu-id="d02f2-103">SPLIT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="d02f2-103">SPLIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d02f2-104">Funkcja `SPLIT` dzieli określony ciąg wejściowy na podciągi i zwraca wynik jako nową wartość *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="d02f2-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="d02f2-105">Składnia 1</span><span class="sxs-lookup"><span data-stu-id="d02f2-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="d02f2-106">Ta składnia jest używana do dzielenia podanego ciągu wejściowego na podciągi, z których każdy ma określoną długość.</span><span class="sxs-lookup"><span data-stu-id="d02f2-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="d02f2-107">Składnia 2</span><span class="sxs-lookup"><span data-stu-id="d02f2-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="d02f2-108">Ta składnia jest używana do dzielenia podanego ciągu wejściowego na podciągi przy użyciu podanego separatora.</span><span class="sxs-lookup"><span data-stu-id="d02f2-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="d02f2-109">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d02f2-109">Arguments</span></span>

<span data-ttu-id="d02f2-110">`input`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d02f2-110">`input`: *String*</span></span>

<span data-ttu-id="d02f2-111">Tekst do podzielenia.</span><span class="sxs-lookup"><span data-stu-id="d02f2-111">The text to split.</span></span>

<span data-ttu-id="d02f2-112">`length`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="d02f2-112">`length`: *Integer*</span></span>

<span data-ttu-id="d02f2-113">Maksymalna długość jednego podciągu.</span><span class="sxs-lookup"><span data-stu-id="d02f2-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="d02f2-114">`delimiter`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d02f2-114">`delimiter`: *String*</span></span>

<span data-ttu-id="d02f2-115">Ogranicznik, który jest używany do dzielenia podciągów.</span><span class="sxs-lookup"><span data-stu-id="d02f2-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="d02f2-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="d02f2-116">Return values</span></span>

<span data-ttu-id="d02f2-117">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="d02f2-117">*Record list*</span></span>

<span data-ttu-id="d02f2-118">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="d02f2-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d02f2-119">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="d02f2-119">Usage notes</span></span>

<span data-ttu-id="d02f2-120">Struktura rekordów listy, która jest zwracana, składa się z pola **Wartość** typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="d02f2-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="d02f2-121">Każdy zwracany rekord listy zawiera wygenerowane podciągi w tym polu.</span><span class="sxs-lookup"><span data-stu-id="d02f2-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="d02f2-122">Jeśli argument `delimiter` jest pusty, zostanie zwrócona nowa lista składająca się z jednego rekordu mającego pole **Wartość** typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="d02f2-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="d02f2-123">To pole zawiera tekst wejściowy.</span><span class="sxs-lookup"><span data-stu-id="d02f2-123">This field contains the input text.</span></span>

<span data-ttu-id="d02f2-124">Jeśli argument `input` jest pusty, zostanie zwrócona nowa pusta lista.</span><span class="sxs-lookup"><span data-stu-id="d02f2-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="d02f2-125">Jeśli argument `input` lub `delimiter` jest nieokreślony (ma wartość null), aplikacja zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="d02f2-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="d02f2-126">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="d02f2-126">Example 1</span></span>

<span data-ttu-id="d02f2-127">Funkcja `SPLIT ("abcd", 3)` zwraca nową listę zawierającą dwa rekordy, które mają pole **Wartość** typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="d02f2-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="d02f2-128">Pole **Wartość** w pierwszym rekordzie zawiera tekst **"abc"**, a pole **Wartość** w drugim rekordzie zawiera tekst **"d"**.</span><span class="sxs-lookup"><span data-stu-id="d02f2-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d02f2-129">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="d02f2-129">Example 2</span></span>

<span data-ttu-id="d02f2-130">Funkcja `SPLIT ("XAb aBy", "aB")` zwraca nową listę zawierającą trzy rekordy, które mają pole **Wartość** typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="d02f2-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="d02f2-131">Pole **Wartość** w pierwszym rekordzie zawiera tekst **"X"**, pole **Wartość** w drugim rekordzie zawiera tekst **"&nbsp;"**, a pole **Wartość** w trzecim rekordzie zawiera tekst **"y"**.</span><span class="sxs-lookup"><span data-stu-id="d02f2-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="d02f2-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d02f2-132">Additional resources</span></span>

[<span data-ttu-id="d02f2-133">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="d02f2-133">List functions</span></span>](er-functions-category-list.md)
