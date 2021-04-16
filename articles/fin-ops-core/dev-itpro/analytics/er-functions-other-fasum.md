---
title: FA_SUM, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FA_SUM w module Raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: d6f380e384e591e7417cfa40c73f9be6575fb0f6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744302"
---
# <a name="fa_sum-er-function"></a><span data-ttu-id="224dc-103">FA_SUM, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="224dc-103">FA_SUM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="224dc-104">Funkcja `FA_SUM` zwraca wartość *Kontener (rekord)*, która składa się z danych dla kwot składnika majątku dla określonego elementu składnika majątku, kodu modelu ewidencji i zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="224dc-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="224dc-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="224dc-105">Syntax</span></span>

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="224dc-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="224dc-106">Arguments</span></span>

<span data-ttu-id="224dc-107">`fixed asset code`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="224dc-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="224dc-108">Wartość typu *Ciąg* reprezentująca kod elementu składnika majątku, dla którego jest obliczane saldo.</span><span class="sxs-lookup"><span data-stu-id="224dc-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="224dc-109">`value model code`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="224dc-109">`value model code`: *String*</span></span>

<span data-ttu-id="224dc-110">Wartość typu *Ciąg* reprezentująca kod modelu wartości, dla którego jest obliczane saldo.</span><span class="sxs-lookup"><span data-stu-id="224dc-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="224dc-111">`start date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="224dc-111">`start date`: *Date*</span></span>

<span data-ttu-id="224dc-112">Wartość typu *Data* reprezentująca datę początkową okresu, dla którego są obliczane kwoty składników majątku.</span><span class="sxs-lookup"><span data-stu-id="224dc-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="224dc-113">`end date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="224dc-113">`end date`: *Date*</span></span>

<span data-ttu-id="224dc-114">Wartość typu *Data* reprezentująca datę końcową okresu, dla którego są obliczane kwoty składników majątku.</span><span class="sxs-lookup"><span data-stu-id="224dc-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="224dc-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="224dc-115">Return values</span></span>

<span data-ttu-id="224dc-116">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="224dc-116">*Container (record)*</span></span>

<span data-ttu-id="224dc-117">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="224dc-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="224dc-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="224dc-118">Example</span></span>

<span data-ttu-id="224dc-119">Funkcja `FA_SUM ("COMP-000001", "Current", Date1, Date2)` zwraca kontener danych dla składnika majątku **COMP-000001** przygotowanego dla modelu ewidencji **Bieżące** i przez okres od **Data1** do **Data2**.</span><span class="sxs-lookup"><span data-stu-id="224dc-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="224dc-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="224dc-120">Additional resources</span></span>

[<span data-ttu-id="224dc-121">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="224dc-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]