---
title: NULLDATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NULLDATE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 79d37247653aa297fdee2c770180916b9a9a5fc5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563469"
---
# <a name="nulldate-er-function"></a><span data-ttu-id="8f8c5-103">NULLDATE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="8f8c5-103">NULLDATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f8c5-104">Funkcja `NULLDATE` zwraca wartość *Data*, która reprezentuje datę **null** (1 stycznia 1900).</span><span class="sxs-lookup"><span data-stu-id="8f8c5-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="8f8c5-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="8f8c5-105">Syntax</span></span>

```vb
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="8f8c5-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="8f8c5-106">Return values</span></span>

<span data-ttu-id="8f8c5-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="8f8c5-107">*Date*</span></span>

<span data-ttu-id="8f8c5-108">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="8f8c5-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="8f8c5-109">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="8f8c5-109">Example 1</span></span>

<span data-ttu-id="8f8c5-110">Funkcja `DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` zwraca wartość daty **null**, 1 stycznia 1900, jako **„1900-01-01”**, na podstawie określonego formatu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="8f8c5-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="8f8c5-111">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="8f8c5-111">Example 2</span></span>

<span data-ttu-id="8f8c5-112">Wyrażenie `IF( Invoice.DocumentDate = NULLDATE(), true, false)` zwraca wartość **True**, gdy wartość pola **DocumentDate** jest równa dacie **null**.</span><span class="sxs-lookup"><span data-stu-id="8f8c5-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="8f8c5-113">W tym przykładzie **Invoice** jest źródłem danych raportowania elektronicznego (ER) typu **Finance/Tabela — rekordy** i odwołuje się do tabeli CustInvoiceJour.</span><span class="sxs-lookup"><span data-stu-id="8f8c5-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f8c5-114">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8f8c5-114">Additional resources</span></span>

[<span data-ttu-id="8f8c5-115">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="8f8c5-115">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]