---
title: IF, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji IF w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 3674618acae79170daf94413895d17d86a491996
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753175"
---
# <a name="if-er-function"></a><span data-ttu-id="b10ee-103">IF, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="b10ee-103">IF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b10ee-104">Funkcja `IF` zwraca pierwszą określoną wartość, jeśli jest spełniony podany warunek.</span><span class="sxs-lookup"><span data-stu-id="b10ee-104">The `IF` function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="b10ee-105">W przeciwnym razie zwraca ona drugą określoną wartość.</span><span class="sxs-lookup"><span data-stu-id="b10ee-105">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="b10ee-106">Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych.</span><span class="sxs-lookup"><span data-stu-id="b10ee-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="b10ee-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="b10ee-107">Syntax</span></span>

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a><span data-ttu-id="b10ee-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b10ee-108">Arguments</span></span>

<span data-ttu-id="b10ee-109">`condition`: *Wartość logiczna*</span><span class="sxs-lookup"><span data-stu-id="b10ee-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="b10ee-110">Prawidłowe wyrażenie warunkowe, które musi zostać przetestowane.</span><span class="sxs-lookup"><span data-stu-id="b10ee-110">A valid conditional expression that must be tested.</span></span>

<span data-ttu-id="b10ee-111">`first value`: *Dowolny z obsługiwanych typów danych*</span><span class="sxs-lookup"><span data-stu-id="b10ee-111">`first value`: *Any of the supported data types*</span></span>

<span data-ttu-id="b10ee-112">Wynik, który jest zwracany, jeśli warunek zostanie spełniony.</span><span class="sxs-lookup"><span data-stu-id="b10ee-112">The result that is returned if the condition is met.</span></span>

<span data-ttu-id="b10ee-113">`second value`: *Dowolny z obsługiwanych typów danych*</span><span class="sxs-lookup"><span data-stu-id="b10ee-113">`second value`: *Any of the supported data types*</span></span>

<span data-ttu-id="b10ee-114">Wynik, który jest zwracany, jeśli warunek nie zostanie spełniony.</span><span class="sxs-lookup"><span data-stu-id="b10ee-114">The result that is returned if the condition isn't met.</span></span>

## <a name="return-values"></a><span data-ttu-id="b10ee-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="b10ee-115">Return values</span></span>

<span data-ttu-id="b10ee-116">*Dowolny z obsługiwanych typów danych*</span><span class="sxs-lookup"><span data-stu-id="b10ee-116">*Any of the supported data types*</span></span>

<span data-ttu-id="b10ee-117">Wynikowa wartość dowolnego z obsługiwanych typów danych.</span><span class="sxs-lookup"><span data-stu-id="b10ee-117">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b10ee-118">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="b10ee-118">Usage notes</span></span>

<span data-ttu-id="b10ee-119">Argumenty `first value` i `second value` muszą być określone przy użyciu tego samego typu danych.</span><span class="sxs-lookup"><span data-stu-id="b10ee-119">The `first value` and `second value` arguments must be specified by using the same data type.</span></span> <span data-ttu-id="b10ee-120">Wyjątek jest zgłaszany w czasie projektowania, jeśli typy danych skonfigurowanych wartości nie są zgodne.</span><span class="sxs-lookup"><span data-stu-id="b10ee-120">An exception is thrown at design time if the data types of the configured values don't match.</span></span>

<span data-ttu-id="b10ee-121">Jeśli pierwsza wartość wyniku i druga wartość wyniku są wartościami o typie danych *Kontener (rekord)* lub *Lista rekordów*, wynik ma tylko pola, które istnieją w obu wartościach.</span><span class="sxs-lookup"><span data-stu-id="b10ee-121">If the first value and the second value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="b10ee-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="b10ee-122">Example</span></span>

<span data-ttu-id="b10ee-123">Funkcja `IF (1=2, "condition is met", "condition is not met")` zwraca ciąg **"condition is not met"**.</span><span class="sxs-lookup"><span data-stu-id="b10ee-123">`IF (1=2, "condition is met", "condition is not met")` returns the string **"condition is not met"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b10ee-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b10ee-124">Additional resources</span></span>

[<span data-ttu-id="b10ee-125">Funkcje logiczne</span><span class="sxs-lookup"><span data-stu-id="b10ee-125">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]