---
title: VALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji VALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 2252823d98b63d36d9bb195696abef34ac9c98b6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752587"
---
# <a name="value-er-function"></a><span data-ttu-id="9f693-103">VALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="9f693-103">VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f693-104">Funkcja `VALUE` zwraca wartość *rzeczywistą*, która jest konwertowana z określonego ciągu.</span><span class="sxs-lookup"><span data-stu-id="9f693-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f693-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9f693-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="9f693-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="9f693-106">Arguments</span></span>

<span data-ttu-id="9f693-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="9f693-107">`text`: *String*</span></span>

<span data-ttu-id="9f693-108">Wartość ciągu, która musi zostać przekonwertowana na wartość numeryczną.</span><span class="sxs-lookup"><span data-stu-id="9f693-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="9f693-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="9f693-109">Return values</span></span>

<span data-ttu-id="9f693-110">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="9f693-110">*Real*</span></span>

<span data-ttu-id="9f693-111">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="9f693-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9f693-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="9f693-112">Usage notes</span></span>

<span data-ttu-id="9f693-113">Przecinki i kropki (.) są traktowane jako separatory dziesiętne, a wiodący łącznik (-) jako znak minusa.</span><span class="sxs-lookup"><span data-stu-id="9f693-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="9f693-114">W czasie wykonywania wyjątek jest zgłaszany, jeśli podany ciąg zawiera inne znaki nieliczbowe.</span><span class="sxs-lookup"><span data-stu-id="9f693-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="9f693-115">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="9f693-115">Example 1</span></span>

<span data-ttu-id="9f693-116">Funkcja `VALUE ("1 234,56")` zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9f693-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="9f693-117">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="9f693-117">Example 2</span></span>

<span data-ttu-id="9f693-118">Funkcja `VALUE ("1234,56")` zwraca wartość **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="9f693-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f693-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9f693-119">Additional resources</span></span>

[<span data-ttu-id="9f693-120">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="9f693-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]