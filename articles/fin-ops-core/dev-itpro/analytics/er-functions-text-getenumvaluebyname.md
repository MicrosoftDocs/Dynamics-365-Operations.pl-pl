---
title: GETENUMVALUEBYNAME, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GETENUMVALUEBYNAME w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 87613978c149b5d41aefc58f9896424229819626
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041195"
---
# <span data-ttu-id="f2e7c-103"><a name="GETENUMVALUEBYNAME">GETENUMVALUEBYNAME, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="f2e7c-103"><a name="GETENUMVALUEBYNAME">GETENUMVALUEBYNAME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2e7c-104">Funkcja `GETENUMVALUEBYNAME` wyszukuje określoną wartość *wyliczenia* w źródle danych określonego wyliczenia przy użyciu nazwy wyliczenia, która jest określona jako wartość typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="f2e7c-105">W przypadku znalezienia wartości typu *Wyliczenie* funkcja zwraca tę wartość.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="f2e7c-106">W przeciwnym razie funkcja zwraca wartość **null** wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="f2e7c-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="f2e7c-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="f2e7c-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f2e7c-108">Arguments</span></span>

<span data-ttu-id="f2e7c-109">`enumeration data source path`: *Wyliczenie*</span><span class="sxs-lookup"><span data-stu-id="f2e7c-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="f2e7c-110">Prawidłowa ścieżka źródła danych jednego z następujących typów wyliczenia:</span><span class="sxs-lookup"><span data-stu-id="f2e7c-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="f2e7c-111">Wyliczanie modelu raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="f2e7c-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="f2e7c-112">Wyliczenie formatu ER</span><span class="sxs-lookup"><span data-stu-id="f2e7c-112">ER format enumeration</span></span>
- <span data-ttu-id="f2e7c-113">Wyliczenie aplikacji Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="f2e7c-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="f2e7c-114">`enumeration value text`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="f2e7c-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="f2e7c-115">Wartość ciągu, która reprezentuje nazwę pojedynczej wartości wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="f2e7c-116">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="f2e7c-116">Return values</span></span>

<span data-ttu-id="f2e7c-117">*Wyliczenie* z dopuszczalną wartością null</span><span class="sxs-lookup"><span data-stu-id="f2e7c-117">Nullable *Enum*</span></span>

<span data-ttu-id="f2e7c-118">Wyjściowa wartość wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f2e7c-119">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="f2e7c-119">Usage notes</span></span>

<span data-ttu-id="f2e7c-120">Wyjątek nie jest zgłaszany, jeśli wartość *wyliczenia* nie zostanie znaleziona przy użyciu nazwy wartości wyliczenia określonej jako wartość typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="f2e7c-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="f2e7c-121">Example</span></span>

<span data-ttu-id="f2e7c-122">Na poniższej ilustracji wartość stałotekstowa **ReportDirection** została wprowadzona do modelu danych.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="f2e7c-123">Zauważ, że etykiety są zdefiniowane dla wartości wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="f2e7c-124">Na ilustracji przedstawiono następujące szczegóły:</span><span class="sxs-lookup"><span data-stu-id="f2e7c-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="f2e7c-125">Źródło danych **$Direction** jest skonfigurowane w raporcie ER.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="f2e7c-126">To źródło danych jest skonfigurowane na podstawie wyliczenia modelu **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="f2e7c-127">Wyrażenie `$IsArrivals` jest zaprojektowane tak, aby używało źródła danych **$Direction** opartego na wyliczeniu modelu jako parametru tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="f2e7c-128">Wartością tego wyrażenia porównania jest **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="f2e7c-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="f2e7c-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f2e7c-129">Additional resources</span></span>

[<span data-ttu-id="f2e7c-130">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="f2e7c-130">Text functions</span></span>](er-functions-category-text.md)
