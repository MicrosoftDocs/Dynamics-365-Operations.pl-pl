---
title: SESSIONTODAY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SESSIONTODAY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 6d0fcbbf1a1fb0809e3f76161314f38bcd8a74aa
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746779"
---
# <a name="sessiontoday-er-function"></a><span data-ttu-id="9da3a-103">SESSIONTODAY, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="9da3a-103">SESSIONTODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9da3a-104">Funkcja `SESSIONTODAY` zwraca wartość *Data*, która reprezentuje bieżącą datę sesji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9da3a-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="9da3a-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9da3a-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="9da3a-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="9da3a-106">Return values</span></span>

<span data-ttu-id="9da3a-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="9da3a-107">*Date*</span></span>

<span data-ttu-id="9da3a-108">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="9da3a-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="9da3a-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="9da3a-109">Example</span></span>

<span data-ttu-id="9da3a-110">Funkcja `DATEFORMAT (SESSIONTODAY (), "d", "DE")` zwraca bieżącą datę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24-12-2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.</span><span class="sxs-lookup"><span data-stu-id="9da3a-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9da3a-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9da3a-111">Additional resources</span></span>

[<span data-ttu-id="9da3a-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="9da3a-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]