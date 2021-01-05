---
title: POWER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji POWER w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 858f59cf0bc6387b09cbb6f0c59f58ba8107582c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683336"
---
# <a name="power-er-function"></a><span data-ttu-id="04878-103">POWER, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="04878-103">POWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04878-104">Funkcja `POWER` zwraca wartość *rzeczywistą* reprezentującą wynik podniesienia określonej liczby dodatniej do określonej potęgi.</span><span class="sxs-lookup"><span data-stu-id="04878-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="04878-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="04878-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="04878-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="04878-106">Arguments</span></span>

<span data-ttu-id="04878-107">`number`: *Liczba rzeczywista* lub *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="04878-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="04878-108">Wartość numeryczna, którą należy podnieść do określonej potęgi.</span><span class="sxs-lookup"><span data-stu-id="04878-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="04878-109">`power`: *Liczba rzeczywista* lub *Liczba całkowita*</span><span class="sxs-lookup"><span data-stu-id="04878-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="04878-110">Wartość numeryczna reprezentują określoną potęgę.</span><span class="sxs-lookup"><span data-stu-id="04878-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="04878-111">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="04878-111">Return values</span></span>

<span data-ttu-id="04878-112">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="04878-112">*Real*</span></span>

<span data-ttu-id="04878-113">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="04878-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="04878-114">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="04878-114">Example 1</span></span>

<span data-ttu-id="04878-115">Funkcja `POWER (10, 2)` zwraca wartość **100**.</span><span class="sxs-lookup"><span data-stu-id="04878-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="04878-116">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="04878-116">Example 2</span></span>

<span data-ttu-id="04878-117">Funkcja `POWER (4, 0.5)` zwraca wartość **2**.</span><span class="sxs-lookup"><span data-stu-id="04878-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04878-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="04878-118">Additional resources</span></span>

[<span data-ttu-id="04878-119">Funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="04878-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)
