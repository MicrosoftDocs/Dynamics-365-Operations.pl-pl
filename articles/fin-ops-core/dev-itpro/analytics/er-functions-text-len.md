---
title: LEN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LEN w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 3e0ba19e762574dde4f9038b87ce352d13f714f4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041062"
---
# <span data-ttu-id="88dd3-103"><a name="LEN">LEN, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="88dd3-103"><a name="LEN">LEN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88dd3-104">Funkcja `LEN` zwraca określoną liczbę znaków w określonym ciągu jako wartość *Liczba całkowita*.</span><span class="sxs-lookup"><span data-stu-id="88dd3-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="88dd3-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="88dd3-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="88dd3-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="88dd3-106">Arguments</span></span>

<span data-ttu-id="88dd3-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="88dd3-107">`text`: *String*</span></span>

<span data-ttu-id="88dd3-108">Wartość typu *Ciąg* określająca tekst.</span><span class="sxs-lookup"><span data-stu-id="88dd3-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="88dd3-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="88dd3-109">Return values</span></span>

<span data-ttu-id="88dd3-110">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="88dd3-110">*Integer*</span></span>

<span data-ttu-id="88dd3-111">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="88dd3-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="88dd3-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="88dd3-112">Example</span></span>

<span data-ttu-id="88dd3-113">Funkcja `LEN ("Sample")` zwraca wartość **6**.</span><span class="sxs-lookup"><span data-stu-id="88dd3-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88dd3-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="88dd3-114">Additional resources</span></span>

[<span data-ttu-id="88dd3-115">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="88dd3-115">Text functions</span></span>](er-functions-category-text.md)
