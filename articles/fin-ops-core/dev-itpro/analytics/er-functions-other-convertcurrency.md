---
title: CONVERTCURRENCY, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CONVERTCURRENCY w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: a27fd30236a61576ab9063010ea6bc38d9cf7a1e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686793"
---
# <a name="convertcurrency-er-function"></a><span data-ttu-id="70ecd-103">CONVERTCURRENCY, funkcja ER</span><span class="sxs-lookup"><span data-stu-id="70ecd-103">CONVERTCURRENCY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70ecd-104">Funkcja `CONVERTCURRENCY` zwraca wartość *rzeczywistą*, która reprezentuje wynik konwertowania określonej kwoty pieniężnej ze wskazanej waluty źródłowej na określoną walutę docelową przy użyciu ustawień określonej firmy na określony dzień.</span><span class="sxs-lookup"><span data-stu-id="70ecd-104">The `CONVERTCURRENCY` function returns a *Real* value that represents the result of converting the specified monetary amount from the specified source currency to the specified target currency by using the settings of the specified company on the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="70ecd-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="70ecd-105">Syntax</span></span>

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a><span data-ttu-id="70ecd-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="70ecd-106">Arguments</span></span>

<span data-ttu-id="70ecd-107">`amount`: *Liczba całkowita* lub *Liczba rzeczywista*</span><span class="sxs-lookup"><span data-stu-id="70ecd-107">`amount`: *Integer* or *Real*</span></span>

<span data-ttu-id="70ecd-108">Wartość liczbowa, która reprezentuje kwotę pieniężną do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="70ecd-108">A numeric value that represents the monetary amount that must be converted.</span></span>

<span data-ttu-id="70ecd-109">`source currency`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="70ecd-109">`source currency`: *String*</span></span>

<span data-ttu-id="70ecd-110">Kod waluty źródłowej.</span><span class="sxs-lookup"><span data-stu-id="70ecd-110">The code of the source currency.</span></span>

<span data-ttu-id="70ecd-111">`target currency`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="70ecd-111">`target currency`: *String*</span></span>

<span data-ttu-id="70ecd-112">Kod waluty docelowej.</span><span class="sxs-lookup"><span data-stu-id="70ecd-112">The code of the target currency.</span></span>

<span data-ttu-id="70ecd-113">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="70ecd-113">`date`: *Date*</span></span>

<span data-ttu-id="70ecd-114">Wartość typu *Data* reprezentująca datę, która jest używana do określania kursu wymiany na potrzeby konwersji.</span><span class="sxs-lookup"><span data-stu-id="70ecd-114">A *Date* value that represents the date that is used to determine the exchange rate for the conversion.</span></span>

<span data-ttu-id="70ecd-115">`company`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="70ecd-115">`company`: *String*</span></span>

<span data-ttu-id="70ecd-116">Wartość typu *Ciąg*, która reprezentuje kod firmy dostarczającej ustawienia używane do konwersji.</span><span class="sxs-lookup"><span data-stu-id="70ecd-116">A *String* value that represents the code of a company that supplies the settings that are used for the conversion.</span></span>

## <a name="return-values"></a><span data-ttu-id="70ecd-117">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="70ecd-117">Return values</span></span>

<span data-ttu-id="70ecd-118">*Rzeczywisty*</span><span class="sxs-lookup"><span data-stu-id="70ecd-118">*Real*</span></span>

<span data-ttu-id="70ecd-119">Wynikowa wartość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="70ecd-119">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="70ecd-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="70ecd-120">Example</span></span>

<span data-ttu-id="70ecd-121">Funkcja `CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` zwraca równoważność jednego euro w dolarach amerykańskich w dniu bieżącej sesji na podstawie ustawień dla firmy **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="70ecd-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returns the equivalent of one euro in US dollars on the current session date, based on settings for the **DEMF** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="70ecd-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="70ecd-122">Additional resources</span></span>

[<span data-ttu-id="70ecd-123">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="70ecd-123">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
