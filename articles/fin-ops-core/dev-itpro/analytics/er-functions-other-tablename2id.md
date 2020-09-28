---
title: TABLENAME2ID, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TABLENAME2ID w module Raportowanie elektroniczne (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9f9e38f46df8a93b5cb16b8d0d5e5afbff8558a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744006"
---
# <a name="tablename2id-er-function"></a><span data-ttu-id="c2a34-103">TABLENAME2ID, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c2a34-103">TABLENAME2ID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2a34-104">Funkcja `TABLENAME2ID` zwraca numeryczną reprezentację identyfikatora tabeli dla określonej nazwy tabeli jako wartość typu *Liczba całkowita*.</span><span class="sxs-lookup"><span data-stu-id="c2a34-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="c2a34-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c2a34-105">Syntax</span></span>

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="c2a34-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c2a34-106">Arguments</span></span>

<span data-ttu-id="c2a34-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c2a34-107">`text`: *String*</span></span>

<span data-ttu-id="c2a34-108">Wartość tekstowa, która reprezentuje prawidłową nazwę tabeli.</span><span class="sxs-lookup"><span data-stu-id="c2a34-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="c2a34-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c2a34-109">Return values</span></span>

<span data-ttu-id="c2a34-110">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="c2a34-110">*Integer*</span></span>

<span data-ttu-id="c2a34-111">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="c2a34-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c2a34-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="c2a34-112">Usage notes</span></span>

<span data-ttu-id="c2a34-113">Wykonanie tej funkcji może mieć różne wyniki w różnych wystąpieniach aplikacji Microsoft Dynamics 365 Finance, nawet jeśli jest używana ta sama nazwa firmy.</span><span class="sxs-lookup"><span data-stu-id="c2a34-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="c2a34-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="c2a34-114">Example</span></span>

<span data-ttu-id="c2a34-115">Funkcja `TABLENAME2ID ("Intrastat")` zwraca wartość **1510**.</span><span class="sxs-lookup"><span data-stu-id="c2a34-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2a34-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c2a34-116">Additional resources</span></span>

[<span data-ttu-id="c2a34-117">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="c2a34-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
