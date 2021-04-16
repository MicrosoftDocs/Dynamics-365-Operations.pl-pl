---
title: Lista funkcji modułu ER w kategorii kontenerów
description: Ten temat zawiera ogólne informacje o funkcjach kontenerów obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 95f207538ea4f0f7df775bf28d0dcf6529d1a91c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753247"
---
# <a name="list-of-er-functions-in-the-container-category"></a><span data-ttu-id="0d8d9-103">Lista funkcji modułu ER w kategorii kontenerów</span><span class="sxs-lookup"><span data-stu-id="0d8d9-103">List of ER functions in the container category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d8d9-104">[Funkcje](er-formula-language.md#functions) kontenerów [raportowania elektronicznego (ER)](general-electronic-reporting.md) mogą służyć do wykonywania operacji na źródłach danych o typie danych *Kontener*.</span><span class="sxs-lookup"><span data-stu-id="0d8d9-104">[Electronic reporting (ER)](general-electronic-reporting.md) container [functions](er-formula-language.md#functions) can be used to perform operations that involve data sources of the *Container* data type.</span></span> <span data-ttu-id="0d8d9-105">Te operacje są wykonywane, gdy dane przetwarzania reprezentują kolekcję danych binarnych w formacie binarnego dużego obiektu (BLOB).</span><span class="sxs-lookup"><span data-stu-id="0d8d9-105">These operations occur when the processing data represents a collection of binary data in binary large object (BLOB) format.</span></span> <span data-ttu-id="0d8d9-106">Ten temat zawiera podsumowanie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="0d8d9-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="0d8d9-107">Lista obsługiwanych funkcji</span><span class="sxs-lookup"><span data-stu-id="0d8d9-107">List of supported functions</span></span>

| <span data-ttu-id="0d8d9-108">Funkcja</span><span class="sxs-lookup"><span data-stu-id="0d8d9-108">Function</span></span> | <span data-ttu-id="0d8d9-109">opis</span><span class="sxs-lookup"><span data-stu-id="0d8d9-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="0d8d9-110">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="0d8d9-110">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="0d8d9-111">Ta funkcja zwraca wartość *kontenera*, która zawiera zawartość binarną, która jest dekodowana z określonego ciągu ASCII, reprezentującego grupę Base64 schematów kodowania binarnego do tekstu.</span><span class="sxs-lookup"><span data-stu-id="0d8d9-111">This function returns a *Container* value that consists of binary content that is decoded from the specified ASCII string that represents a Base64 group of binary-to-text encoding schemes.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="0d8d9-112">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0d8d9-112">Additional resources</span></span>

[<span data-ttu-id="0d8d9-113">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="0d8d9-113">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="0d8d9-114">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="0d8d9-114">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="0d8d9-115">Język formuł raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="0d8d9-115">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]