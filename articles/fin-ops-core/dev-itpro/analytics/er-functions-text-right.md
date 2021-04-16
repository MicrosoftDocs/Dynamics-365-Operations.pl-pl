---
title: RIGHT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji RIGHT w module Raportowanie elektroniczne (ER).
author: NickSelin
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
ms.openlocfilehash: f59b12f0b3f7b100b953b2072677c83c836746ff
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746130"
---
# <a name="right-er-function"></a><span data-ttu-id="d35a2-103">RIGHT, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="d35a2-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d35a2-104">Funkcja `RIGHT` zwraca wartość *Ciąg*, która reprezentuje określoną liczbę znaków od końca określonego ciągu.</span><span class="sxs-lookup"><span data-stu-id="d35a2-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="d35a2-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="d35a2-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="d35a2-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d35a2-106">Arguments</span></span>

<span data-ttu-id="d35a2-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d35a2-107">`text`: *String*</span></span>

<span data-ttu-id="d35a2-108">Wartość *ciągu* reprezentująca oryginalny tekst.</span><span class="sxs-lookup"><span data-stu-id="d35a2-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="d35a2-109">`number`: *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="d35a2-109">`number`: *Integer*</span></span>

<span data-ttu-id="d35a2-110">Liczba znaków, które muszą zostać zwrócone, od końca oryginalnego tekstu.</span><span class="sxs-lookup"><span data-stu-id="d35a2-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="d35a2-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="d35a2-111">Return values</span></span>

<span data-ttu-id="d35a2-112">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="d35a2-112">*String*</span></span>

<span data-ttu-id="d35a2-113">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="d35a2-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d35a2-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="d35a2-114">Example</span></span>

<span data-ttu-id="d35a2-115">Funkcja `RIGHT ("Sample", 3)` zwraca wartość **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="d35a2-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d35a2-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d35a2-116">Additional resources</span></span>

[<span data-ttu-id="d35a2-117">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="d35a2-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]