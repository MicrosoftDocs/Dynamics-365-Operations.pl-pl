---
title: LEN, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji LEN w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: fce4b5311d84364310b76545a775f1cc8db2fd70
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569975"
---
# <a name="len-er-function"></a><span data-ttu-id="4df80-103">LEN, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="4df80-103">LEN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4df80-104">Funkcja `LEN` zwraca określoną liczbę znaków w określonym ciągu jako wartość *Liczba całkowita*.</span><span class="sxs-lookup"><span data-stu-id="4df80-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="4df80-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="4df80-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="4df80-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="4df80-106">Arguments</span></span>

<span data-ttu-id="4df80-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="4df80-107">`text`: *String*</span></span>

<span data-ttu-id="4df80-108">Wartość typu *Ciąg* określająca tekst.</span><span class="sxs-lookup"><span data-stu-id="4df80-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="4df80-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="4df80-109">Return values</span></span>

<span data-ttu-id="4df80-110">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="4df80-110">*Integer*</span></span>

<span data-ttu-id="4df80-111">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="4df80-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="4df80-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="4df80-112">Example</span></span>

<span data-ttu-id="4df80-113">Funkcja `LEN ("Sample")` zwraca wartość **6**.</span><span class="sxs-lookup"><span data-stu-id="4df80-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4df80-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4df80-114">Additional resources</span></span>

[<span data-ttu-id="4df80-115">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="4df80-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]