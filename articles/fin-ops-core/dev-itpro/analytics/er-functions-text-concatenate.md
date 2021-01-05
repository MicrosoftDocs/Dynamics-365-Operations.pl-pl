---
title: CONCATENATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CONCATENATE w module Raportowanie elektroniczne (ER)
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 903429994ae5618b597aa0ab0991e9f6783a96ed
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687945"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="9ae8a-103">CONCATENATE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="9ae8a-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ae8a-104">Funkcja `CONCATENATE` zwraca wszystkie ciągi tekstowe określone jako wartość typu *Ciąg* po ich połączeniu w jeden ciąg.</span><span class="sxs-lookup"><span data-stu-id="9ae8a-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="9ae8a-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9ae8a-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="9ae8a-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="9ae8a-106">Arguments</span></span>

<span data-ttu-id="9ae8a-107">`text 1`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="9ae8a-107">`text 1`: *String*</span></span>

<span data-ttu-id="9ae8a-108">Odwołanie do źródła danych o typie danych *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="9ae8a-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="9ae8a-109">Ten argument jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="9ae8a-109">This argument is required.</span></span>

<span data-ttu-id="9ae8a-110">`text N`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="9ae8a-110">`text N`: *String*</span></span>

<span data-ttu-id="9ae8a-111">Odwołanie do źródła danych o typie danych *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="9ae8a-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="9ae8a-112">Te dodatkowe argumenty są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="9ae8a-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="9ae8a-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="9ae8a-113">Return values</span></span>

<span data-ttu-id="9ae8a-114">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="9ae8a-114">*String*</span></span>

<span data-ttu-id="9ae8a-115">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="9ae8a-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9ae8a-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="9ae8a-116">Example</span></span>

<span data-ttu-id="9ae8a-117">Funkcja `CONCATENATE ("abc", "def")` zwraca wartość **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="9ae8a-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9ae8a-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="9ae8a-118">Usage notes</span></span>

<span data-ttu-id="9ae8a-119">Wyrażenie `"abc" & "def"` również zwraca wartość **abcdef**.</span><span class="sxs-lookup"><span data-stu-id="9ae8a-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9ae8a-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9ae8a-120">Additional resources</span></span>

[<span data-ttu-id="9ae8a-121">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="9ae8a-121">Text functions</span></span>](er-functions-category-text.md)
