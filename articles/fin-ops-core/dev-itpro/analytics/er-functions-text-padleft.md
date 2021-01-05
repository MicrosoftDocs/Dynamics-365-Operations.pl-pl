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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 268941d8bc0bd4dc6de6d2597c05a11c1f530f15
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680153"
---
# <a name="padleft-er-function"></a><span data-ttu-id="679b3-103">PADLEFT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="679b3-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="679b3-104">Funkcja `PADLEFT` zwracanie wartość typu *Ciąg* o określonej długości, w którym początek ciągu jest dopełniany określonymi znakami.</span><span class="sxs-lookup"><span data-stu-id="679b3-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="679b3-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="679b3-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="679b3-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="679b3-106">Arguments</span></span>

<span data-ttu-id="679b3-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="679b3-107">`text`: *String*</span></span>

<span data-ttu-id="679b3-108">Wartość *ciągu* reprezentująca oryginalny tekst.</span><span class="sxs-lookup"><span data-stu-id="679b3-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="679b3-109">`length`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="679b3-109">`length`: *Integer*</span></span>

<span data-ttu-id="679b3-110">Wartość *całkowita*, która reprezentuje ostatnią liczbę znaków w dopełnianym ciągu.</span><span class="sxs-lookup"><span data-stu-id="679b3-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="679b3-111">`padding chars`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="679b3-111">`padding chars`: *String*</span></span>

<span data-ttu-id="679b3-112">Znaki używane do dopełnienia.</span><span class="sxs-lookup"><span data-stu-id="679b3-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="679b3-113">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="679b3-113">Return values</span></span>

<span data-ttu-id="679b3-114">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="679b3-114">*String*</span></span>

<span data-ttu-id="679b3-115">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="679b3-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="679b3-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="679b3-116">Example</span></span>

<span data-ttu-id="679b3-117">Funkcja `PADLEFT ("1234", 10, "`&nbsp;`")` zwraca ciąg tekstowy **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="679b3-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="679b3-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="679b3-118">Additional resources</span></span>

[<span data-ttu-id="679b3-119">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="679b3-119">Text functions</span></span>](er-functions-category-text.md)
