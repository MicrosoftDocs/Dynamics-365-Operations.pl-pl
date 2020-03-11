---
title: FA_BALANCE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji FA_BALANCE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 76a087157ae53e2c571654ade7383d7bd7a005c3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041453"
---
# <span data-ttu-id="cbde9-103"><a name="FA_BALANCE">FA_BALANCE, funkcja ER</a></span><span class="sxs-lookup"><span data-stu-id="cbde9-103"><a name="FA_BALANCE">FA_BALANCE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbde9-104">Funkcja `FA_BALANCE` zwraca wartość *Kontener (rekord)*, która składa się z danych dla salda składnika majątku dla określonego elementu składnika majątku, kodu modelu ewidencji, roku sprawozdawczego i daty raportowania.</span><span class="sxs-lookup"><span data-stu-id="cbde9-104">The `FA_BALANCE` function returns a *Container (record)* value that consists of data for the fixed asset balance for the specified fixed asset item, value model code, reporting year, and reporting date.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbde9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="cbde9-105">Syntax</span></span>

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a><span data-ttu-id="cbde9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="cbde9-106">Arguments</span></span>

<span data-ttu-id="cbde9-107">`fixed asset code`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="cbde9-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="cbde9-108">Wartość typu *Ciąg* reprezentująca kod elementu składnika majątku, dla którego jest obliczane saldo.</span><span class="sxs-lookup"><span data-stu-id="cbde9-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="cbde9-109">`value model code`: *Ciąg*</span><span class="sxs-lookup"><span data-stu-id="cbde9-109">`value model code`: *String*</span></span>

<span data-ttu-id="cbde9-110">Wartość typu *Ciąg* reprezentująca kod modelu wartości, dla którego jest obliczane saldo.</span><span class="sxs-lookup"><span data-stu-id="cbde9-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="cbde9-111">`reporting year`: *Wartość wyliczenia*</span><span class="sxs-lookup"><span data-stu-id="cbde9-111">`reporting year`: *Enumeration value*</span></span>

<span data-ttu-id="cbde9-112">Wartość wyliczenia aplikacji **AssetYear** definiujący okres na potrzeby obliczania salda.</span><span class="sxs-lookup"><span data-stu-id="cbde9-112">An enumeration value of the **AssetYear** application enumeration that defines a period for the balance calculation.</span></span>

<span data-ttu-id="cbde9-113">`reporting date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="cbde9-113">`reporting date`: *Date*</span></span>

<span data-ttu-id="cbde9-114">Wartość typu *Data* definiująca datę obliczenia salda.</span><span class="sxs-lookup"><span data-stu-id="cbde9-114">A *Date* value that defines a date for the balance calculation.</span></span>

## <a name="return-values"></a><span data-ttu-id="cbde9-115">Wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="cbde9-115">Return values</span></span>

<span data-ttu-id="cbde9-116">*Kontener (rekord)*</span><span class="sxs-lookup"><span data-stu-id="cbde9-116">*Container (record)*</span></span>

<span data-ttu-id="cbde9-117">Wynik wartości rekordu.</span><span class="sxs-lookup"><span data-stu-id="cbde9-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="cbde9-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="cbde9-118">Example</span></span>

<span data-ttu-id="cbde9-119">Funkcja `FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` zwraca przygotowany kontener sald dla środka trwałego **COMP-000001**, który ma model ewidencji **Bieżący** na dzień bieżącej sesji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="cbde9-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returns the data container of balances for fixed asset **COMP-000001** that has been prepared for the **Current** value model on the current application session date.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cbde9-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cbde9-120">Additional resources</span></span>

[<span data-ttu-id="cbde9-121">Inne funkcje (specyficzne dla domeny biznesowej)</span><span class="sxs-lookup"><span data-stu-id="cbde9-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
