---
title: FA_SUM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FA_SUM w module Raportowanie elektroniczne (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32eb07689598a3b6c852f272b480106670b88cd0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916989"
---
# <span data-ttu-id="0c4ad-103"><a name="FA_SUM">FA_SUM, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="0c4ad-103"><a name="FA_SUM">FA_SUM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c4ad-104">Funkcja `FA_SUM` zwraca wartość *Kontener (rekord)*, która składa się z danych dla kwot składnika majątku dla określonego elementu składnika majątku, kodu modelu ewidencji i zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="0c4ad-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c4ad-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0c4ad-105">Syntax</span></span>

```
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="0c4ad-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="0c4ad-106">Arguments</span></span>

<span data-ttu-id="0c4ad-107">`fixed asset code`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="0c4ad-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="0c4ad-108">Wartość typu *Ciąg* reprezentująca kod elementu składnika majątku, dla którego jest obliczane saldo.</span><span class="sxs-lookup"><span data-stu-id="0c4ad-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="0c4ad-109">`value model code`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="0c4ad-109">`value model code`: *String*</span></span>

<span data-ttu-id="0c4ad-110">Wartość typu *Ciąg* reprezentująca kod modelu wartości, dla którego jest obliczane saldo.</span><span class="sxs-lookup"><span data-stu-id="0c4ad-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="0c4ad-111">`start date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="0c4ad-111">`start date`: *Date*</span></span>

<span data-ttu-id="0c4ad-112">Wartość typu *Data* reprezentująca datę początkową okresu, dla którego są obliczane kwoty składników majątku.</span><span class="sxs-lookup"><span data-stu-id="0c4ad-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="0c4ad-113">`end date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="0c4ad-113">`end date`: *Date*</span></span>

<span data-ttu-id="0c4ad-114">Wartość typu *Data* reprezentująca datę końcową okresu, dla którego są obliczane kwoty składników majątku.</span><span class="sxs-lookup"><span data-stu-id="0c4ad-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="0c4ad-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="0c4ad-115">Return values</span></span>

<span data-ttu-id="0c4ad-116">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="0c4ad-116">*Container (record)*</span></span>

<span data-ttu-id="0c4ad-117">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="0c4ad-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="0c4ad-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="0c4ad-118">Example</span></span>

<span data-ttu-id="0c4ad-119">Funkcja `FA_SUM ("COMP-000001", "Current", Date1, Date2)` zwraca kontener danych dla składnika majątku **COMP-000001** przygotowanego dla modelu ewidencji **Bieżące** i przez okres od **Data1** do **Data2**.</span><span class="sxs-lookup"><span data-stu-id="0c4ad-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c4ad-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0c4ad-120">Additional resources</span></span>

[<span data-ttu-id="0c4ad-121">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="0c4ad-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
