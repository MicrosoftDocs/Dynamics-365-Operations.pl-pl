---
title: GETCURRENTCOMPANY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji GETCURRENTCOMPANY w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 3e14c6a8aaff0a32a115117938d0e853bb34bb14
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684866"
---
# <a name="getcurrentcompany-er-function"></a><span data-ttu-id="97214-103">GETCURRENTCOMPANY, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="97214-103">GETCURRENTCOMPANY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97214-104">Funkcja `GETCURRENTCOMPANY` zwraca wartość *Ciąg* reprezentującą kod firmy (jednostki prawnej), do której użytkownik jest aktualnie zalogowany.</span><span class="sxs-lookup"><span data-stu-id="97214-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="97214-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="97214-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="97214-106">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="97214-106">Return values</span></span>

<span data-ttu-id="97214-107">*Ciąg*</span><span class="sxs-lookup"><span data-stu-id="97214-107">*String*</span></span>

<span data-ttu-id="97214-108">Wynikowa wartość tekstowa.</span><span class="sxs-lookup"><span data-stu-id="97214-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="97214-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="97214-109">Example</span></span>

<span data-ttu-id="97214-110">Funkcja `GETCURRENTCOMPANY ()` zwraca wartość **USMF** dla użytkownika zalogowanego do firmy **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="97214-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="97214-111">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="97214-111">Additional resources</span></span>

[<span data-ttu-id="97214-112">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="97214-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
