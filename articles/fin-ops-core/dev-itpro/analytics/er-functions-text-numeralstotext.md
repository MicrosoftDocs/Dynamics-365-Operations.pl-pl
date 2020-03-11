---
title: NUMERALSTOTEXT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMERALSTOTEXT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 31fd4076d04ce7d849555bc8301c4d23ad8e1a7e
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041021"
---
# <span data-ttu-id="a12dc-103"><a name="NUMERALSTOTEXT">NUMERALSTOTEXT, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="a12dc-103"><a name="NUMERALSTOTEXT">NUMERALSTOTEXT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a12dc-104">Funkcja `NUMERALSTOTEXT` zwraca określoną liczbę jako wartość *Ciąg* po jej zapisaniu (czyli przekonwertowaniu na ciągi tekstowe) w określonym języku.</span><span class="sxs-lookup"><span data-stu-id="a12dc-104">The `NUMERALSTOTEXT` function returns the specified number as a *String* value after it has been spelled out (that is, converted to text strings) in the specified language.</span></span>

## <a name="syntax"></a><span data-ttu-id="a12dc-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a12dc-105">Syntax</span></span>

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a><span data-ttu-id="a12dc-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="a12dc-106">Arguments</span></span>

<span data-ttu-id="a12dc-107">`number`: *Liczba całkowita* lub *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="a12dc-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="a12dc-108">Wartość liczbowa, która określa liczbę do zapisania.</span><span class="sxs-lookup"><span data-stu-id="a12dc-108">A numeric value that specifies the number that must be spelled out.</span></span>

<span data-ttu-id="a12dc-109">`language`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="a12dc-109">`language`: *String*</span></span>

<span data-ttu-id="a12dc-110">Wartość typu *Ciąg* reprezentująca kod języka.</span><span class="sxs-lookup"><span data-stu-id="a12dc-110">A *String* value that represents the language code.</span></span>

<span data-ttu-id="a12dc-111">`currency`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="a12dc-111">`currency`: *String*</span></span>

<span data-ttu-id="a12dc-112">Wartość typu *Ciąg* reprezentująca kod waluty.</span><span class="sxs-lookup"><span data-stu-id="a12dc-112">A *String* value that represents the currency code.</span></span>

<span data-ttu-id="a12dc-113">`print currency name flag`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="a12dc-113">`print currency name flag`: *Boolean*</span></span>

<span data-ttu-id="a12dc-114">Wartość *logiczna* wskazująca, czy nazwa waluty musi zostać dodana do napisanego tekstu.</span><span class="sxs-lookup"><span data-stu-id="a12dc-114">A *Boolean* value that indicates whether a currency name must be added to the spelled-out text.</span></span>

<span data-ttu-id="a12dc-115">`decimal points`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="a12dc-115">`decimal points`: *Integer*</span></span>

<span data-ttu-id="a12dc-116">Wartość *całkowita*, która wskazuje liczbę miejsc dziesiętnych na potrzeby zapisanego tekstu.</span><span class="sxs-lookup"><span data-stu-id="a12dc-116">An *Integer* value that indicates the number of decimal places that the spelled-out text should have.</span></span>

## <a name="return-values"></a><span data-ttu-id="a12dc-117">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="a12dc-117">Return values</span></span>

<span data-ttu-id="a12dc-118">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="a12dc-118">*String*</span></span>

<span data-ttu-id="a12dc-119">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="a12dc-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a12dc-120">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="a12dc-120">Usage notes</span></span>

<span data-ttu-id="a12dc-121">Kod języka jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="a12dc-121">The language code is optional.</span></span> <span data-ttu-id="a12dc-122">Jeśli jest zdefiniowany jako pusty ciąg znaków, będzie używany kod języka aktualnie uruchomionego kontekstu.</span><span class="sxs-lookup"><span data-stu-id="a12dc-122">If it's defined as an empty string, the language code for the running context is used.</span></span> <span data-ttu-id="a12dc-123">Domyślny kod języka to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="a12dc-123">The default language code is **EN-US**.</span></span> <span data-ttu-id="a12dc-124">Kod języka dla uruchomionego kontekstu jest zdefiniowany w elemencie **Folder** lub **Plik** w uruchomionym formacie raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="a12dc-124">The language code for the running context is defined in a **Folder** or **File** element of the Electronic reporting (ER) format that is running.</span></span>

<span data-ttu-id="a12dc-125">Kod waluty jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="a12dc-125">The currency code is optional.</span></span> <span data-ttu-id="a12dc-126">Jeśli jest zdefiniowany jako pusty ciąg znaków, będzie używana waluta firmy aktualnie uruchomionego kontekstu.</span><span class="sxs-lookup"><span data-stu-id="a12dc-126">If it's defined as an empty string, the company currency for the running context is used.</span></span>

> [!NOTE] 
> <span data-ttu-id="a12dc-127">Argumenty `print currency name flag` i `decimal points` są analizowane tylko dla następujących kodów języków: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** i **RU**.</span><span class="sxs-lookup"><span data-stu-id="a12dc-127">The `print currency name flag` and `decimal points` arguments are analyzed only for the following language codes: **CS**, **ET**, **HU**, **LT**, **LV**, **PL**, and **RU**.</span></span> <span data-ttu-id="a12dc-128">Ponadto argument `print currency name flag` jest analizowany tylko dla firm, których kontekst kraju lub regionu obsługuje deklinację nazw walut.</span><span class="sxs-lookup"><span data-stu-id="a12dc-128">Additionally, the `print currency name flag` argument is analyzed only for companies where the country's or region's context supports declension of currency names.</span></span>

## <a name="example-1"></a><span data-ttu-id="a12dc-129">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="a12dc-129">Example 1</span></span>

<span data-ttu-id="a12dc-130">Funkcja `NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` zwraca wartość **"One Thousand Two Hundred Thirty Four and 56"**.</span><span class="sxs-lookup"><span data-stu-id="a12dc-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returns **"One Thousand Two Hundred Thirty Four and 56"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="a12dc-131">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="a12dc-131">Example 2</span></span>

<span data-ttu-id="a12dc-132">Funkcja `NUMERALSTOTEXT (120, "PL", "", false, 0)` zwraca wartość **„Sto dwadzieścia”**.</span><span class="sxs-lookup"><span data-stu-id="a12dc-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returns **"Sto dwadzieścia"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="a12dc-133">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="a12dc-133">Example 3</span></span>

<span data-ttu-id="a12dc-134">Funkcja `NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` zwraca wartość **„сто двадцать евро 21 евроцент”**.</span><span class="sxs-lookup"><span data-stu-id="a12dc-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returns **"Сто двадцать евро 21 евроцент"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a12dc-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a12dc-135">Additional resources</span></span>

[<span data-ttu-id="a12dc-136">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="a12dc-136">Text functions</span></span>](er-functions-category-text.md)
