---
title: PADLEFT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji PADLEFT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 3f8a8e2006fe279b25bbf154c6e1802babf51117
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744366"
---
# <a name="padleft-er-function"></a><span data-ttu-id="c2f8b-103">PADLEFT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c2f8b-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2f8b-104">Funkcja `PADLEFT` zwracanie wartość typu *Ciąg* o określonej długości, w którym początek ciągu jest dopełniany określonymi znakami.</span><span class="sxs-lookup"><span data-stu-id="c2f8b-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="c2f8b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c2f8b-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="c2f8b-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c2f8b-106">Arguments</span></span>

<span data-ttu-id="c2f8b-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c2f8b-107">`text`: *String*</span></span>

<span data-ttu-id="c2f8b-108">Wartość *ciągu* reprezentująca oryginalny tekst.</span><span class="sxs-lookup"><span data-stu-id="c2f8b-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="c2f8b-109">`length`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="c2f8b-109">`length`: *Integer*</span></span>

<span data-ttu-id="c2f8b-110">Wartość *całkowita*, która reprezentuje ostatnią liczbę znaków w dopełnianym ciągu.</span><span class="sxs-lookup"><span data-stu-id="c2f8b-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="c2f8b-111">`padding chars`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c2f8b-111">`padding chars`: *String*</span></span>

<span data-ttu-id="c2f8b-112">Znaki używane do dopełnienia.</span><span class="sxs-lookup"><span data-stu-id="c2f8b-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="c2f8b-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c2f8b-113">Return values</span></span>

<span data-ttu-id="c2f8b-114">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c2f8b-114">*String*</span></span>

<span data-ttu-id="c2f8b-115">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="c2f8b-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c2f8b-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="c2f8b-116">Example</span></span>

<span data-ttu-id="c2f8b-117">Funkcja `PADLEFT ("1234", 10, "`&nbsp;`")` zwraca ciąg tekstowy **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="c2f8b-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2f8b-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c2f8b-118">Additional resources</span></span>

[<span data-ttu-id="c2f8b-119">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="c2f8b-119">Text functions</span></span>](er-functions-category-text.md)
