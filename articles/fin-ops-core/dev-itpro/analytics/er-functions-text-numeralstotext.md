---
title: NUMERALSTOTEXT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMERALSTOTEXT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 0dfb36e21259eada97b158cb38b22ae19e0afa07
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562764"
---
# <a name="numeralstotext-er-function"></a><span data-ttu-id="3e200-103">NUMERALSTOTEXT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="3e200-103">NUMERALSTOTEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3e200-104">Funkcja `NUMERALSTOTEXT` zwraca określoną liczbę jako wartość *Ciąg* po jej zapisaniu (czyli przekonwertowaniu na ciągi tekstowe) w określonym języku.</span><span class="sxs-lookup"><span data-stu-id="3e200-104">The `NUMERALSTOTEXT` function returns the specified number as a *String* value after it has been spelled out (that is, converted to text strings) in the specified language.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e200-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="3e200-105">Syntax</span></span>

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a><span data-ttu-id="3e200-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="3e200-106">Arguments</span></span>

<span data-ttu-id="3e200-107">`number`: *Liczba całkowita* lub *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="3e200-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="3e200-108">Wartość liczbowa, która określa liczbę do zapisania.</span><span class="sxs-lookup"><span data-stu-id="3e200-108">A numeric value that specifies the number that must be spelled out.</span></span>

<span data-ttu-id="3e200-109">`language`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="3e200-109">`language`: *String*</span></span>

<span data-ttu-id="3e200-110">Wartość typu *Ciąg* reprezentująca kod języka.</span><span class="sxs-lookup"><span data-stu-id="3e200-110">A *String* value that represents the language code.</span></span>

<span data-ttu-id="3e200-111">`currency`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="3e200-111">`currency`: *String*</span></span>

<span data-ttu-id="3e200-112">Wartość typu *Ciąg* reprezentująca kod waluty.</span><span class="sxs-lookup"><span data-stu-id="3e200-112">A *String* value that represents the currency code.</span></span>

<span data-ttu-id="3e200-113">`print currency name flag`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="3e200-113">`print currency name flag`: *Boolean*</span></span>

<span data-ttu-id="3e200-114">Wartość *logiczna* wskazująca, czy nazwa waluty musi zostać dodana do napisanego tekstu.</span><span class="sxs-lookup"><span data-stu-id="3e200-114">A *Boolean* value that indicates whether a currency name must be added to the spelled-out text.</span></span>

<span data-ttu-id="3e200-115">`decimal points`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="3e200-115">`decimal points`: *Integer*</span></span>

<span data-ttu-id="3e200-116">Wartość *całkowita*, która wskazuje liczbę miejsc dziesiętnych na potrzeby zapisanego tekstu.</span><span class="sxs-lookup"><span data-stu-id="3e200-116">An *Integer* value that indicates the number of decimal places that the spelled-out text should have.</span></span>

## <a name="return-values"></a><span data-ttu-id="3e200-117">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="3e200-117">Return values</span></span>

<span data-ttu-id="3e200-118">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="3e200-118">*String*</span></span>

<span data-ttu-id="3e200-119">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="3e200-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3e200-120">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="3e200-120">Usage notes</span></span>

<span data-ttu-id="3e200-121">Kod języka jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="3e200-121">The language code is optional.</span></span> <span data-ttu-id="3e200-122">Jeśli jest zdefiniowany jako pusty ciąg znaków, będzie używany kod języka aktualnie uruchomionego kontekstu.</span><span class="sxs-lookup"><span data-stu-id="3e200-122">If it's defined as an empty string, the language code for the running context is used.</span></span> <span data-ttu-id="3e200-123">Domyślny kod języka to **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="3e200-123">The default language code is **EN-US**.</span></span> <span data-ttu-id="3e200-124">Kod języka dla uruchomionego kontekstu jest zdefiniowany w elemencie **Folder** lub **Plik** w uruchomionym formacie raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="3e200-124">The language code for the running context is defined in a **Folder** or **File** element of the Electronic reporting (ER) format that is running.</span></span>

<span data-ttu-id="3e200-125">Kod waluty jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="3e200-125">The currency code is optional.</span></span> <span data-ttu-id="3e200-126">Jeśli jest zdefiniowany jako pusty ciąg znaków, będzie używana waluta firmy aktualnie uruchomionego kontekstu.</span><span class="sxs-lookup"><span data-stu-id="3e200-126">If it's defined as an empty string, the company currency for the running context is used.</span></span>

> [!NOTE] 
> <span data-ttu-id="3e200-127">Argumenty `print currency name flag` i `decimal points` są analizowane tylko dla następujących kodów języków: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** i **RU**.</span><span class="sxs-lookup"><span data-stu-id="3e200-127">The `print currency name flag` and `decimal points` arguments are analyzed only for the following language codes: **CS**, **ET**, **HU**, **LT**, **LV**, **PL**, and **RU**.</span></span> <span data-ttu-id="3e200-128">Ponadto argument `print currency name flag` jest analizowany tylko dla firm, których kontekst kraju lub regionu obsługuje deklinację nazw walut.</span><span class="sxs-lookup"><span data-stu-id="3e200-128">Additionally, the `print currency name flag` argument is analyzed only for companies where the country's or region's context supports declension of currency names.</span></span>

## <a name="example-1"></a><span data-ttu-id="3e200-129">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="3e200-129">Example 1</span></span>

<span data-ttu-id="3e200-130">Funkcja `NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` zwraca wartość **"One Thousand Two Hundred Thirty Four and 56"**.</span><span class="sxs-lookup"><span data-stu-id="3e200-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returns **"One Thousand Two Hundred Thirty Four and 56"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="3e200-131">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="3e200-131">Example 2</span></span>

<span data-ttu-id="3e200-132">Funkcja `NUMERALSTOTEXT (120, "PL", "", false, 0)` zwraca wartość **„Sto dwadzieścia”**.</span><span class="sxs-lookup"><span data-stu-id="3e200-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returns **"Sto dwadzieścia"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="3e200-133">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="3e200-133">Example 3</span></span>

<span data-ttu-id="3e200-134">Funkcja `NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` zwraca wartość **„сто двадцать евро 21 евроцент”**.</span><span class="sxs-lookup"><span data-stu-id="3e200-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returns **"Сто двадцать евро 21 евроцент"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e200-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3e200-135">Additional resources</span></span>

[<span data-ttu-id="3e200-136">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="3e200-136">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]