---
title: RIGHT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji RIGHT w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 13884182cb986564e81f310993747997341ffc07
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682949"
---
# <a name="right-er-function"></a><span data-ttu-id="f3f8e-103">RIGHT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="f3f8e-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3f8e-104">Funkcja `RIGHT` zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków od końca określonego ciągu.</span><span class="sxs-lookup"><span data-stu-id="f3f8e-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="f3f8e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f3f8e-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="f3f8e-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f3f8e-106">Arguments</span></span>

<span data-ttu-id="f3f8e-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f3f8e-107">`text`: *String*</span></span>

<span data-ttu-id="f3f8e-108">Wartość *ciągu* reprezentująca oryginalny tekst.</span><span class="sxs-lookup"><span data-stu-id="f3f8e-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="f3f8e-109">`number`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="f3f8e-109">`number`: *Integer*</span></span>

<span data-ttu-id="f3f8e-110">Liczba znaków, które muszą zostać zwrócone, od końca oryginalnego tekstu.</span><span class="sxs-lookup"><span data-stu-id="f3f8e-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="f3f8e-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="f3f8e-111">Return values</span></span>

<span data-ttu-id="f3f8e-112">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f3f8e-112">*String*</span></span>

<span data-ttu-id="f3f8e-113">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="f3f8e-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="f3f8e-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="f3f8e-114">Example</span></span>

<span data-ttu-id="f3f8e-115">Funkcja `RIGHT ("Sample", 3)` zwraca wartość **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="f3f8e-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f3f8e-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f3f8e-116">Additional resources</span></span>

[<span data-ttu-id="f3f8e-117">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="f3f8e-117">Text functions</span></span>](er-functions-category-text.md)
