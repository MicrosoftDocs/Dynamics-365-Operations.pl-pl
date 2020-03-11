---
title: GUIDVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GUIDVALUE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: a7b8c782aff488a433c40a49ab7f4fe2d0e944e4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041191"
---
# <span data-ttu-id="ee43a-103"><a name="GUIDVALUE">GUIDVALUE, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="ee43a-103"><a name="GUIDVALUE">GUIDVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee43a-104">Funkcja `GUIDVALUE` przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *Identyfikator GUID*.</span><span class="sxs-lookup"><span data-stu-id="ee43a-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee43a-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ee43a-105">Syntax</span></span>

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="ee43a-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ee43a-106">Arguments</span></span>

<span data-ttu-id="ee43a-107">`input`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="ee43a-107">`input`: *String*</span></span>

<span data-ttu-id="ee43a-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="ee43a-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ee43a-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="ee43a-109">Return values</span></span>

<span data-ttu-id="ee43a-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="ee43a-110">*GUID*</span></span>

<span data-ttu-id="ee43a-111">Wynikowa wartość globalnie unikatowego identyfikatora (GUID).</span><span class="sxs-lookup"><span data-stu-id="ee43a-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ee43a-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="ee43a-112">Usage notes</span></span>

<span data-ttu-id="ee43a-113">Aby wykonać przekształcenie w przeciwnym kierunku (tzn. aby przekonwertować podane dane wejściowe o typie danych *GUID* na element danych o typie danych *String*), można użyć funkcji [TEXT](er-functions-text-text.md).</span><span class="sxs-lookup"><span data-stu-id="ee43a-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="ee43a-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="ee43a-114">Example</span></span>

<span data-ttu-id="ee43a-115">Definiuje się następujące źródła danych w mapowaniu modelu:</span><span class="sxs-lookup"><span data-stu-id="ee43a-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="ee43a-116">Źródło danych **myID** typu *Pole obliczeniowe*, które zawiera wyrażenie `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span><span class="sxs-lookup"><span data-stu-id="ee43a-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="ee43a-117">Źródło danych **Users** typu *Rekordy tabeli*, które odwołuje się do tabeli UserInfo</span><span class="sxs-lookup"><span data-stu-id="ee43a-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="ee43a-118">Następnie użyj wyrażenia, takiego jak `FILTER (Users, Users.objectId = myID)`, do odfiltrowania tabeli UserInfo według pola **objectid** typu danych *GUID*.</span><span class="sxs-lookup"><span data-stu-id="ee43a-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ee43a-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ee43a-119">Additional resources</span></span>

[<span data-ttu-id="ee43a-120">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="ee43a-120">Text functions</span></span>](er-functions-category-text.md)
