---
title: GUIDVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GUIDVALUE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 552c6a42dd0e189f2f8404ce5d7f7a68fec1b216
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564345"
---
# <a name="guidvalue-er-function"></a><span data-ttu-id="40aa6-103">GUIDVALUE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="40aa6-103">GUIDVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40aa6-104">Funkcja `GUIDVALUE` przekształca określone dane wejściowe typu *Ciąg* na element danych o typie danych *Identyfikator GUID*.</span><span class="sxs-lookup"><span data-stu-id="40aa6-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="40aa6-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="40aa6-105">Syntax</span></span>

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="40aa6-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="40aa6-106">Arguments</span></span>

<span data-ttu-id="40aa6-107">`input`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="40aa6-107">`input`: *String*</span></span>

<span data-ttu-id="40aa6-108">Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.</span><span class="sxs-lookup"><span data-stu-id="40aa6-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="40aa6-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="40aa6-109">Return values</span></span>

<span data-ttu-id="40aa6-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="40aa6-110">*GUID*</span></span>

<span data-ttu-id="40aa6-111">Wynikowa wartość globalnie unikatowego identyfikatora (GUID).</span><span class="sxs-lookup"><span data-stu-id="40aa6-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="40aa6-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="40aa6-112">Usage notes</span></span>

<span data-ttu-id="40aa6-113">Aby wykonać przekształcenie w przeciwnym kierunku (tzn. aby przekonwertować podane dane wejściowe o typie danych *GUID* na element danych o typie danych *String*), można użyć funkcji [TEXT](er-functions-text-text.md).</span><span class="sxs-lookup"><span data-stu-id="40aa6-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="40aa6-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="40aa6-114">Example</span></span>

<span data-ttu-id="40aa6-115">Definiuje się następujące źródła danych w mapowaniu modelu:</span><span class="sxs-lookup"><span data-stu-id="40aa6-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="40aa6-116">Źródło danych **myID** typu *Pole obliczeniowe*, które zawiera wyrażenie `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span><span class="sxs-lookup"><span data-stu-id="40aa6-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="40aa6-117">Źródło danych **Users** typu *Rekordy tabeli*, które odwołuje się do tabeli UserInfo</span><span class="sxs-lookup"><span data-stu-id="40aa6-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="40aa6-118">Następnie użyj wyrażenia, takiego jak `FILTER (Users, Users.objectId = myID)`, do odfiltrowania tabeli UserInfo według pola **objectid** typu danych *GUID*.</span><span class="sxs-lookup"><span data-stu-id="40aa6-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40aa6-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="40aa6-119">Additional resources</span></span>

[<span data-ttu-id="40aa6-120">Funkcje tekstowe</span><span class="sxs-lookup"><span data-stu-id="40aa6-120">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]