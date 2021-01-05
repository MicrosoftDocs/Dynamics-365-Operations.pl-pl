---
title: Kwota zaokrąglenia do obliczenia amortyzacji
description: W tym artykule omówiono pole Zaokrąglenie amortyzacji, które znajduje się na stronach konfiguracji ksiąg.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40fd019b1b5900fbd15866d9d3c32ed6d88147b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446855"
---
# <a name="round-off-amount-for-depreciation-calculations"></a><span data-ttu-id="3bfb1-103">Kwota zaokrąglenia do obliczenia amortyzacji</span><span class="sxs-lookup"><span data-stu-id="3bfb1-103">Round-off amount for depreciation calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3bfb1-104">W tym artykule omówiono pole Zaokrąglenie amortyzacji, które znajduje się na stronach konfiguracji ksiąg.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-104">This article discusses the Round-off depreciation field that is found on the Book setup pages.</span></span>

<span data-ttu-id="3bfb1-105">Kwoty zaokrąglenia amortyzacji są ustawiane dla każdej księgi.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-105">Round-off depreciation amounts are set for each book.</span></span> <span data-ttu-id="3bfb1-106">Kwoty zaokrąglenia amortyzacji są używane w profilu amortyzacji środka trwałego, który pokazuje przyszłą amortyzację i wartość środka trwałego, a także w propozycjach amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-106">Round-off depreciation amounts are used in the fixed asset depreciation profile that shows the future depreciation and value of the fixed asset, and also in depreciation proposals.</span></span> <span data-ttu-id="3bfb1-107">Wprowadź najniższą kwotę amortyzacji dozwoloną dla danej księgi.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-107">Enter the lowest depreciation amount that is allowed for the book.</span></span> 

<span data-ttu-id="3bfb1-108">Niezależnie od ustawionego zaokrąglenia kwota amortyzacji w ostatnim okresie amortyzacji nie jest zaokrąglana.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-108">Regardless of the rounding that is set up, the depreciation amount in the last depreciation period isn't rounded.</span></span> <span data-ttu-id="3bfb1-109">Na końcu ostatniego okresu amortyzacji wartość środków trwałych musi wynosić 0 (zero) lub być równa wartości likwidacji, jeśli likwidacja jest stosowana.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-109">At the end of the last depreciation period, the value of the fixed asset must be 0 (zero) or the scrap value, if scrap value is used.</span></span>

### <a name="example"></a><span data-ttu-id="3bfb1-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="3bfb1-110">Example</span></span>

<span data-ttu-id="3bfb1-111">Amortyzacja bez żadnego zaokrąglania została obliczona jako 2444,44.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-111">Depreciation without rounding is calculated as 2,444.44.</span></span> <span data-ttu-id="3bfb1-112">Jak pokazano w poniższej tabeli sugerowane kwoty różnią się w zależności od ustawienia zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-112">As the following table shows, the amounts that are suggested vary, depending on how rounding is set up.</span></span>

| <span data-ttu-id="3bfb1-113">Metoda zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="3bfb1-113">Rounding method</span></span> | <span data-ttu-id="3bfb1-114">Kwota amortyzacji</span><span class="sxs-lookup"><span data-stu-id="3bfb1-114">Depreciation amount</span></span> |
|-----------------|---------------------|
| <span data-ttu-id="3bfb1-115">Zaokrąglanie 0,1</span><span class="sxs-lookup"><span data-stu-id="3bfb1-115">Rounding 0.1</span></span>    | <span data-ttu-id="3bfb1-116">2444,40</span><span class="sxs-lookup"><span data-stu-id="3bfb1-116">2,444.40</span></span>            |
| <span data-ttu-id="3bfb1-117">Zaokrąglanie 1,00</span><span class="sxs-lookup"><span data-stu-id="3bfb1-117">Rounding 1.00</span></span>   | <span data-ttu-id="3bfb1-118">2,444.00</span><span class="sxs-lookup"><span data-stu-id="3bfb1-118">2,444.00</span></span>            |
| <span data-ttu-id="3bfb1-119">Zaokrąglanie 10,00</span><span class="sxs-lookup"><span data-stu-id="3bfb1-119">Rounding 10.00</span></span>  | <span data-ttu-id="3bfb1-120">2,440.00</span><span class="sxs-lookup"><span data-stu-id="3bfb1-120">2,440.00</span></span>            |
| <span data-ttu-id="3bfb1-121">Zaokrąglanie 100,00</span><span class="sxs-lookup"><span data-stu-id="3bfb1-121">Rounding 100.00</span></span> | <span data-ttu-id="3bfb1-122">2,400.00</span><span class="sxs-lookup"><span data-stu-id="3bfb1-122">2,400.00</span></span>            |





