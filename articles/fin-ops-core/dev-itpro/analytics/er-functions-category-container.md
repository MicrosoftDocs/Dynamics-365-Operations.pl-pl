---
title: Lista funkcji modułu ER w kategorii kontenerów
description: Ten temat zawiera ogólne informacje o funkcjach kontenerów obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 46d1af85773f6c3d07865658c554dee74fae625f
ms.sourcegitcommit: e8a46e127d70986539c138b27a641bff6f6874d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2020
ms.locfileid: "4739103"
---
# <a name="list-of-er-functions-in-the-container-category"></a><span data-ttu-id="446d8-103">Lista funkcji modułu ER w kategorii kontenerów</span><span class="sxs-lookup"><span data-stu-id="446d8-103">List of ER functions in the container category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="446d8-104">[Funkcje](er-formula-language.md#functions) kontenerów [raportowania elektronicznego (ER)](general-electronic-reporting.md) mogą służyć do wykonywania operacji na źródłach danych o typie danych *Kontener*.</span><span class="sxs-lookup"><span data-stu-id="446d8-104">[Electronic reporting (ER)](general-electronic-reporting.md) container [functions](er-formula-language.md#functions) can be used to perform operations that involve data sources of the *Container* data type.</span></span> <span data-ttu-id="446d8-105">Te operacje są wykonywane, gdy dane przetwarzania reprezentują kolekcję danych binarnych w formacie binarnego dużego obiektu (BLOB).</span><span class="sxs-lookup"><span data-stu-id="446d8-105">These operations occur when the processing data represents a collection of binary data in binary large object (BLOB) format.</span></span> <span data-ttu-id="446d8-106">Ten temat zawiera podsumowanie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="446d8-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="446d8-107">Lista obsługiwanych funkcji</span><span class="sxs-lookup"><span data-stu-id="446d8-107">List of supported functions</span></span>

| <span data-ttu-id="446d8-108">Funkcja</span><span class="sxs-lookup"><span data-stu-id="446d8-108">Function</span></span> | <span data-ttu-id="446d8-109">opis</span><span class="sxs-lookup"><span data-stu-id="446d8-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="446d8-110">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="446d8-110">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="446d8-111">Ta funkcja zwraca wartość *kontenera*, która zawiera zawartość binarną, która jest dekodowana z określonego ciągu ASCII, reprezentującego grupę Base64 schematów kodowania binarnego do tekstu.</span><span class="sxs-lookup"><span data-stu-id="446d8-111">This function returns a *Container* value that consists of binary content that is decoded from the specified ASCII string that represents a Base64 group of binary-to-text encoding schemes.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="446d8-112">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="446d8-112">Additional resources</span></span>

[<span data-ttu-id="446d8-113">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="446d8-113">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="446d8-114">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="446d8-114">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="446d8-115">Język formuł raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="446d8-115">Electronic reporting formula language</span></span>](er-formula-language.md)
