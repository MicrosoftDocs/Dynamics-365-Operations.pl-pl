---
title: ENUMERATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji ENUMERATE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 0827fe33a548970c7673ac2ab830bb22d367c8cc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567875"
---
# <a name="enumerate-er-function"></a><span data-ttu-id="ce3a9-103">ENUMERATE, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="ce3a9-103">ENUMERATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce3a9-104">Funkcja `ENUMERATE` zwraca nową wartość typu *Lista rekordów*, która składa się z wyliczonych rekordów określonej listy.</span><span class="sxs-lookup"><span data-stu-id="ce3a9-104">The `ENUMERATE` function returns a new *Record list* value that consists of enumerated records of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce3a9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ce3a9-105">Syntax</span></span>

```vb
ENUMERATE (list)
```

## <a name="arguments"></a><span data-ttu-id="ce3a9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ce3a9-106">Arguments</span></span>

<span data-ttu-id="ce3a9-107">`list`: *Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="ce3a9-107">`list`: *Record list*</span></span>

<span data-ttu-id="ce3a9-108">Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.</span><span class="sxs-lookup"><span data-stu-id="ce3a9-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ce3a9-109">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="ce3a9-109">Return values</span></span>

<span data-ttu-id="ce3a9-110">*Lista rekordów*</span><span class="sxs-lookup"><span data-stu-id="ce3a9-110">*Record list*</span></span>

<span data-ttu-id="ce3a9-111">Wynikowa lista rekordów.</span><span class="sxs-lookup"><span data-stu-id="ce3a9-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ce3a9-112">Uwagi dotyczące użytkowania</span><span class="sxs-lookup"><span data-stu-id="ce3a9-112">Usage notes</span></span>

<span data-ttu-id="ce3a9-113">Zwracana lista wyliczonych rekordów zawiera następujące elementy dodatkowe:</span><span class="sxs-lookup"><span data-stu-id="ce3a9-113">The list of enumerated records that is returned exposes the following additional elements:</span></span>

- <span data-ttu-id="ce3a9-114">Rekord pól (składnik **Wartość**)</span><span class="sxs-lookup"><span data-stu-id="ce3a9-114">The record of fields (**Value** component)</span></span>
- <span data-ttu-id="ce3a9-115">Indeks bieżącego rekordu (składnik **Number**)</span><span class="sxs-lookup"><span data-stu-id="ce3a9-115">The current record index (**Number** component)</span></span>

## <a name="example"></a><span data-ttu-id="ce3a9-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="ce3a9-116">Example</span></span>

<span data-ttu-id="ce3a9-117">Na poniższej ilustracji źródło danych **Enumerated** jest tworzone jako stałotekstowa lista rekordów dostawców ze źródła danych **Vendors**, które odwołuje się do tabeli VendTable.</span><span class="sxs-lookup"><span data-stu-id="ce3a9-117">In the following illustration, an **Enumerated** data source is created as an enumerated list of vendor records from the **Vendors** data source that refers to the VendTable table.</span></span>

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

<span data-ttu-id="ce3a9-118">Na poniższej ilustracji przedstawiono format raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="ce3a9-118">The following illustration shows the Electronic reporting (ER) format.</span></span> <span data-ttu-id="ce3a9-119">W tym formacie są tworzone powiązania danych w celu wygenerowania danych wyjściowych w formacie XML</span><span class="sxs-lookup"><span data-stu-id="ce3a9-119">In this format, data bindings are created to generate output in XML format.</span></span> <span data-ttu-id="ce3a9-120">Te dane wyjściowe prezentują poszczególnych dostawców jako stałotekstowe węzły.</span><span class="sxs-lookup"><span data-stu-id="ce3a9-120">This output presents individual vendors as enumerated nodes.</span></span>

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

<span data-ttu-id="ce3a9-121">Na ilustracji poniżej widać wynik uruchomienia zaprojektowanego formatu.</span><span class="sxs-lookup"><span data-stu-id="ce3a9-121">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a><span data-ttu-id="ce3a9-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ce3a9-122">Additional resources</span></span>

[<span data-ttu-id="ce3a9-123">Lista funkcji</span><span class="sxs-lookup"><span data-stu-id="ce3a9-123">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]