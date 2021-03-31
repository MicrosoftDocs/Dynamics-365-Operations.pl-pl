---
title: Amortyzacja degresywna po podzieleniu
description: W tym temacie opisano metodę używaną w module Środki trwałe do obliczania amortyzacji po podzieleniu składnika majątku przy użyciu metody amortyzacji degresywnej.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f276f49e5b1bc2814dc851f1ad4204a151d86c43
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222390"
---
# <a name="reduce-balance-depreciation-after-a-split"></a><span data-ttu-id="ef9a3-103">Amortyzacja degresywna po podzieleniu</span><span class="sxs-lookup"><span data-stu-id="ef9a3-103">Reduce balance depreciation after a split</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef9a3-104">W tym temacie opisano metodę używaną w module Środki trwałe do obliczania amortyzacji po podzieleniu składnika majątku na inny składnik majątku przy użyciu metody amortyzacji degresywnej.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-104">This topic describes the method that is used in Fixed assets to calculate depreciation after an asset is split to another asset by using the reduce balance method.</span></span> <span data-ttu-id="ef9a3-105">Rok amortyzacji skonfigurowany w księdze składników majątku jest rokiem obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-105">The depreciation year that is configured in the asset book is the fiscal year.</span></span> <span data-ttu-id="ef9a3-106">Aby uzyskać więcej informacji, zobacz [Amortyzacja degresywna](reduce-balance-depreciation.md) i [Rozbicie środka trwałego](tasks/split-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="ef9a3-106">For more information, see [Reduce balance depreciation](reduce-balance-depreciation.md) and [Split a fixed asset](tasks/split-fixed-asset.md).</span></span>

<span data-ttu-id="ef9a3-107">Jeśli środek trwały zostanie podzielony w okresie obrachunkowym późniejszym niż okres, w którym składnik majątku został nabyty, amortyzacja degresywna uwzględni wartość księgową netto (NBV) składnika majątku za poprzedni rok.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-107">If you split a fixed asset during a fiscal period that is later than the period when the asset was acquired, the reduced balance depreciation will account for the asset's net book value (NBV) for the previous year.</span></span> <span data-ttu-id="ef9a3-108">Ponadto uwzględni transakcje korekty wartości początkowej i amortyzacji wygenerowane przez transakcję, która podzieliła składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-108">It will also account for the acquisition and depreciation adjustment transactions that were generated from the transaction that split the asset.</span></span> <span data-ttu-id="ef9a3-109">To zachowanie zakłada, że składnik majątku został nabyty w jednym roku obrachunkowym i podzielony w późniejszym roku obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-109">This behavior assumes that the asset was acquired in one fiscal year and split in a later fiscal year.</span></span> <span data-ttu-id="ef9a3-110">Kwota, o którą należy zamortyzować pierwotny składnik majątku po podzieleniu, odzwierciedla NBV składnika sprzed podziału oraz transakcję korekty wartości początkowej i amortyzacji zaksięgowaną wskutek podziału.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-110">The amount that must be depreciated for the original asset after the split reflects the asset's NBV before the asset was split, and the acquisition and depreciation adjustment transaction that was posted for the split.</span></span>

<span data-ttu-id="ef9a3-111">Na przykład istnieją następujące okoliczności:</span><span class="sxs-lookup"><span data-stu-id="ef9a3-111">For example, the following conditions are in effect:</span></span>

- <span data-ttu-id="ef9a3-112">Okres obrachunkowy wypada od 30 czerwca do 1 lipca.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-112">The fiscal period is from June 30 to July 1.</span></span>
- <span data-ttu-id="ef9a3-113">Wartość procentowa amortyzacji degresywnej wynosi 18 procent, a składnik majątku został kupiony w czerwcu 2019 roku w cenie nabycia 10 000 zł.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-113">The reducing balance percentage is 18 percent, and an asset is acquired in June 2019 at an acquisition price of $10,000.</span></span>
- <span data-ttu-id="ef9a3-114">Amortyzacja w pierwszym roku obrachunkowym wynosi 18 000 zł, amortyzacja miesięczna wynosi 150 zł, a składnik majątku jest następnie amortyzowany do listopada 2019 r. na kwotę 738,75 zł.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-114">The depreciation of the first fiscal year equals $18,000, the monthly depreciation equals $150, and the asset is then depreciated until November 2019, in the amount of $738.75.</span></span>
- <span data-ttu-id="ef9a3-115">W listopadzie 2019 r. 80 procent składnika majątku zostało podzielone na inny składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-115">In November 2019, 80 percent of the asset is split to another fixed asset.</span></span>

<span data-ttu-id="ef9a3-116">[![Amortyzacja degresywna po podzieleniu](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span><span class="sxs-lookup"><span data-stu-id="ef9a3-116">[![Reduce balance depreciation after a split](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span></span>

<span data-ttu-id="ef9a3-117">Kwota amortyzacji pierwotnego składnika majątku wynosi 1822,25 zł.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-117">The amount to depreciate for the original asset is $1,822.25.</span></span> <span data-ttu-id="ef9a3-118">Ta kwota jest równa NBV przed zaksięgowaniem transakcji podziału (9111,25 zł) powiększonej o korektę wartości początkowej wygenerowaną podczas księgowania transakcji podziału (-8000 zł) oraz korektę amortyzacji wygenerowaną w trakcie transakcji podziału (711 zł).</span><span class="sxs-lookup"><span data-stu-id="ef9a3-118">This amount equals the NBV before the split transaction is posted ($9,111.25), plus the acquisition adjustment that is generated during posting of the split transaction (-$8,000), plus the depreciation adjustment that is generated during the split transaction ($711).</span></span> <span data-ttu-id="ef9a3-119">W efekcie amortyzacja za drugi rok wynosi (1822,25 × 18 procent) ÷ 12 = 27,33 zł.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-119">Therefore, the depreciation for the second year is (1,822.25 × 18 percent) ÷ 12 = $27.33.</span></span>

<span data-ttu-id="ef9a3-120">Kwota amortyzacji dla nowego środka trwałego w pierwszym roku wynosi (8000 × 18 procent) ÷ 12 = 120 zł.</span><span class="sxs-lookup"><span data-stu-id="ef9a3-120">The amount to depreciate for the new fixed asset in the first year is (8,000 × 18 percent) ÷ 12 = $120.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]