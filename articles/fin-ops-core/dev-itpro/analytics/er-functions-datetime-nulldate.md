---
title: NULLDATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NULLDATE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 7761342c6759c11591e06fc7c32f0ddd8bef407a
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916322"
---
# <span data-ttu-id="6c7c5-103"><a name="NULLDATE">NULLDATE, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="6c7c5-103"><a name="NULLDATE">NULLDATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c7c5-104">Funkcja `NULLDATE` zwraca wartość *Data*, która reprezentuje datę **null** (1 stycznia 1900).</span><span class="sxs-lookup"><span data-stu-id="6c7c5-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="6c7c5-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="6c7c5-105">Syntax</span></span>

```
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="6c7c5-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="6c7c5-106">Return values</span></span>

<span data-ttu-id="6c7c5-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="6c7c5-107">*Date*</span></span>

<span data-ttu-id="6c7c5-108">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="6c7c5-109">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="6c7c5-109">Example 1</span></span>

<span data-ttu-id="6c7c5-110">Funkcja `DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` zwraca wartość daty **null**, 1 stycznia 1900, jako **„1900-01-01”**, na podstawie określonego formatu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="6c7c5-111">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="6c7c5-111">Example 2</span></span>

<span data-ttu-id="6c7c5-112">Wyrażenie `IF( Invoice.DocumentDate = NULLDATE(), true, false)` zwraca wartość **True**, gdy wartość pola **DocumentDate** jest równa dacie **null**.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="6c7c5-113">W tym przykładzie **Invoice** jest źródłem danych raportowania elektronicznego (ER) typu **Finance/Tabela — rekordy** i odwołuje się do tabeli CustInvoiceJour.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6c7c5-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6c7c5-114">Additional resources</span></span>

[<span data-ttu-id="6c7c5-115">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="6c7c5-115">Date and time functions</span></span>](er-functions-category-datetime.md)
