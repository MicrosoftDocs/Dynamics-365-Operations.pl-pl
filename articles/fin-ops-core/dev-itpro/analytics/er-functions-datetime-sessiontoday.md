---
title: SESSIONTODAY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SESSIONTODAY w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: bcfb36d6e3fb8475546f7cfb420c4aca848ac896
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917472"
---
# <span data-ttu-id="d1e8e-103"><a name="SESSIONTODAY">SESSIONTODAY, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="d1e8e-103"><a name="SESSIONTODAY">SESSIONTODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1e8e-104">Funkcja `SESSIONTODAY` zwraca wartość *Data*, która reprezentuje bieżącą datę sesji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d1e8e-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1e8e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="d1e8e-105">Syntax</span></span>

```
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="d1e8e-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="d1e8e-106">Return values</span></span>

<span data-ttu-id="d1e8e-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="d1e8e-107">*Date*</span></span>

<span data-ttu-id="d1e8e-108">Wyjściowa wartość daty.</span><span class="sxs-lookup"><span data-stu-id="d1e8e-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="d1e8e-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="d1e8e-109">Example</span></span>

<span data-ttu-id="d1e8e-110">Funkcja `DATEFORMAT (SESSIONTODAY (), "d", "DE")` zwraca bieżącą datę sesji aplikacji, 24 grudnia 2015, jako ciąg **„24-12-2015”**, na podstawie wybranej kultury niemieckiej i określonego formatu.</span><span class="sxs-lookup"><span data-stu-id="d1e8e-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d1e8e-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d1e8e-111">Additional resources</span></span>

[<span data-ttu-id="d1e8e-112">Funkcje daty i godziny</span><span class="sxs-lookup"><span data-stu-id="d1e8e-112">Date and time functions</span></span>](er-functions-category-datetime.md)
