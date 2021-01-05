---
title: JSONVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji JSONVALUE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 11f9ac680ea00622367ea56106fd22508628d85d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685914"
---
# <a name="jsonvalue-er-function"></a><span data-ttu-id="c4a30-103">JSONVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="c4a30-103">JSONVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4a30-104">Funkcja `JSONVALUE` analizuje dane w formacie JSON (JavaScript Object Notation), do których dostęp jest uzyskiwany za pośrednictwem wskazanej ścieżki oraz wyodrębnia wartość skalarną opartą na podanym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="c4a30-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="c4a30-105">Następnie zwraca wartość skalarną wyodrębnioną jako wartość typu *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="c4a30-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="c4a30-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="c4a30-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="c4a30-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c4a30-107">Arguments</span></span>

<span data-ttu-id="c4a30-108">`input`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c4a30-108">`input`: *String*</span></span>

<span data-ttu-id="c4a30-109">Prawidłowa ścieżka elementu źródła danych typu *Ciąg*, który zawiera dane JSON.</span><span class="sxs-lookup"><span data-stu-id="c4a30-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="c4a30-110">`path`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c4a30-110">`path`: *String*</span></span>

<span data-ttu-id="c4a30-111">Identyfikator wartości skalarnej danych JSON.</span><span class="sxs-lookup"><span data-stu-id="c4a30-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="c4a30-112">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="c4a30-112">Return values</span></span>

<span data-ttu-id="c4a30-113">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="c4a30-113">*String*</span></span>

<span data-ttu-id="c4a30-114">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="c4a30-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c4a30-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="c4a30-115">Example</span></span>

<span data-ttu-id="c4a30-116">Źródło danych **JsonField** zawiera następujące dane w formacie JSON: **{"Numer_kompilacji":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="c4a30-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="c4a30-117">W tym przypadku wyrażenie `JSONVALUE (JsonField, "BuildNumber")` zwraca następującą wartość typu danych *String*: **"7.3.1234.1".**</span><span class="sxs-lookup"><span data-stu-id="c4a30-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4a30-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c4a30-118">Additional resources</span></span>

[<span data-ttu-id="c4a30-119">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="c4a30-119">Text functions</span></span>](er-functions-category-text.md)
