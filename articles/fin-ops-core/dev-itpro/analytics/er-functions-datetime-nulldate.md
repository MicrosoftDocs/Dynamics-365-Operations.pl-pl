---
title: NULLDATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NULLDATE w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 6ac8da3f18c7793512685d52dd64a9bd55bfb8fc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746850"
---
# <a name="nulldate-er-function"></a><span data-ttu-id="856a7-103">NULLDATE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="856a7-103">NULLDATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="856a7-104">Funkcja `NULLDATE` zwraca wartość *Data*, która reprezentuje datę **null** (1 stycznia 1900).</span><span class="sxs-lookup"><span data-stu-id="856a7-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="856a7-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="856a7-105">Syntax</span></span>

```vb
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="856a7-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="856a7-106">Return values</span></span>

<span data-ttu-id="856a7-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="856a7-107">*Date*</span></span>

<span data-ttu-id="856a7-108">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="856a7-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="856a7-109">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="856a7-109">Example 1</span></span>

<span data-ttu-id="856a7-110">Funkcja `DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` zwraca wartość daty **null**, 1 stycznia 1900, jako **„1900-01-01”**, na podstawie określonego formatu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="856a7-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="856a7-111">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="856a7-111">Example 2</span></span>

<span data-ttu-id="856a7-112">Wyrażenie `IF( Invoice.DocumentDate = NULLDATE(), true, false)` zwraca wartość **True**, gdy wartość pola **DocumentDate** jest równa dacie **null**.</span><span class="sxs-lookup"><span data-stu-id="856a7-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="856a7-113">W tym przykładzie **Invoice** jest źródłem danych raportowania elektronicznego (ER) typu **Finance/Tabela — rekordy** i odwołuje się do tabeli CustInvoiceJour.</span><span class="sxs-lookup"><span data-stu-id="856a7-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="856a7-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="856a7-114">Additional resources</span></span>

[<span data-ttu-id="856a7-115">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="856a7-115">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]