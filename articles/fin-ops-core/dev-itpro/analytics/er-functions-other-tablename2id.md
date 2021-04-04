---
title: TABLENAME2ID, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TABLENAME2ID w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 49370af4ebb7552dd3aff4512890fd93fa67c72d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563277"
---
# <a name="tablename2id-er-function"></a><span data-ttu-id="f7080-103">TABLENAME2ID, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="f7080-103">TABLENAME2ID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f7080-104">Funkcja `TABLENAME2ID` zwraca numeryczną reprezentację identyfikatora tabeli dla określonej nazwy tabeli jako wartość typu *Liczba całkowita*.</span><span class="sxs-lookup"><span data-stu-id="f7080-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="f7080-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f7080-105">Syntax</span></span>

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="f7080-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f7080-106">Arguments</span></span>

<span data-ttu-id="f7080-107">`text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f7080-107">`text`: *String*</span></span>

<span data-ttu-id="f7080-108">Wartość tekstowa, która reprezentuje prawidłową nazwę tabeli.</span><span class="sxs-lookup"><span data-stu-id="f7080-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="f7080-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="f7080-109">Return values</span></span>

<span data-ttu-id="f7080-110">*Wartość całkowita*</span><span class="sxs-lookup"><span data-stu-id="f7080-110">*Integer*</span></span>

<span data-ttu-id="f7080-111">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="f7080-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f7080-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="f7080-112">Usage notes</span></span>

<span data-ttu-id="f7080-113">Wykonanie tej funkcji może mieć różne wyniki w różnych wystąpieniach aplikacji Microsoft Dynamics 365 Finance, nawet jeśli jest używana ta sama nazwa firmy.</span><span class="sxs-lookup"><span data-stu-id="f7080-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="f7080-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="f7080-114">Example</span></span>

<span data-ttu-id="f7080-115">Funkcja `TABLENAME2ID ("Intrastat")` zwraca wartość **1510**.</span><span class="sxs-lookup"><span data-stu-id="f7080-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f7080-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f7080-116">Additional resources</span></span>

[<span data-ttu-id="f7080-117">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="f7080-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]