---
title: Opcje Cała kwota i Obliczanie interwału dla kodów podatku
description: W tym artykule opisano opcje dostępne w polu Metoda obliczania w ustawieniach kodów podatków oraz wyjaśniono sposób obliczania podatku dla interwałów kwot i całych kwot.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d452ccc94324a695f0d203486fc5fa8fe9db79f6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770558"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="74516-103">Opcje Cała kwota i Obliczanie interwału dla kodów podatku</span><span class="sxs-lookup"><span data-stu-id="74516-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74516-104">W tym artykule opisano opcje dostępne w polu Metoda obliczania w ustawieniach kodów podatków oraz wyjaśniono sposób obliczania podatku dla interwałów kwot i całych kwot.</span><span class="sxs-lookup"><span data-stu-id="74516-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="74516-105">można skonfigurować kod podatku, który ma być obliczany na podstawie jednej całej kwoty lub kwoty interwału.</span><span class="sxs-lookup"><span data-stu-id="74516-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="74516-106">Na stronie Kody podatków użyj pola Metoda obliczania na karcie skróconej Obliczanie, aby wybrać, jak ma być obliczany kod podatku.</span><span class="sxs-lookup"><span data-stu-id="74516-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
- <span data-ttu-id="74516-107">Cała kwota — stawka podatku jest stosowana do całej kwoty opodatkowanej.</span><span class="sxs-lookup"><span data-stu-id="74516-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
- <span data-ttu-id="74516-108">Interwał — kwota opodatkowana jest dzielona na części, z których każda mieści się w zakresie o określonej stawce podatku.</span><span class="sxs-lookup"><span data-stu-id="74516-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="74516-109">Część tej kwoty należąca do danego interwału jest opodatkowana według stawki podatku określonej dla tego interwału.</span><span class="sxs-lookup"><span data-stu-id="74516-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="74516-110">Podatek jest sumą kwot podatku obliczonych dla poszczególnych interwałów kwoty.</span><span class="sxs-lookup"><span data-stu-id="74516-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
  > [!NOTE]                                                                                                                              
  > <span data-ttu-id="74516-111">Opcja Interwał jest dostępna tylko po wybraniu opcji Wiersz w polu Obliczanie w obszarze Podatek na stronie Parametry księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="74516-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="74516-112">Interwały są konfigurowane na stronie Wartości kodu podatku poprzez wprowadzanie kwot Minimalna i Maksymalna dla stawki podatkowej.</span><span class="sxs-lookup"><span data-stu-id="74516-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="74516-113">Aby podatki były obliczane dla wszystkich kwot opodatkowanych — niezależnie od wyboru metody obliczania — interwały muszą podlegać następującym regułom:</span><span class="sxs-lookup"><span data-stu-id="74516-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="74516-114">Pierwszy interwał musi mieć Minimalny limit zero.</span><span class="sxs-lookup"><span data-stu-id="74516-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="74516-115">Ostatni interwał musi mieć Maksymalny limit zero, który oznacza nieskończoność.</span><span class="sxs-lookup"><span data-stu-id="74516-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="74516-116">Maksymalny limit interwału musi być Minimalnym limitem następnego interwału.</span><span class="sxs-lookup"><span data-stu-id="74516-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="74516-117">Jeśli kwota jest równa Maksymalnemu limitowi poprzedniego interwału i Minimalnemu limitowi następnego interwału, stosowany jest do niej podatek pierwszego interwału.</span><span class="sxs-lookup"><span data-stu-id="74516-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="74516-118">Jeśli kwota nie należy do żadnego z interwałów określonych przez górne i dolne limity, stosowana jest stawka podatku równa 0.</span><span class="sxs-lookup"><span data-stu-id="74516-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="74516-119">Przykład: Metoda obliczania wg całej kwoty</span><span class="sxs-lookup"><span data-stu-id="74516-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="74516-120">Na stronie Wartości kodu podatku stawki podatku są skonfigurowane przy użyciu następujących interwałów:</span><span class="sxs-lookup"><span data-stu-id="74516-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="74516-121">**Dolny limit**</span><span class="sxs-lookup"><span data-stu-id="74516-121">**Minimum limit**</span></span> | <span data-ttu-id="74516-122">**Maksymalny limit**</span><span class="sxs-lookup"><span data-stu-id="74516-122">**Maximum limit**</span></span> | <span data-ttu-id="74516-123">**Stawka podatku**</span><span class="sxs-lookup"><span data-stu-id="74516-123">**Tax rate**</span></span> |
| <span data-ttu-id="74516-124">0,00</span><span class="sxs-lookup"><span data-stu-id="74516-124">0.00</span></span>              | <span data-ttu-id="74516-125">50,00</span><span class="sxs-lookup"><span data-stu-id="74516-125">50.00</span></span>             | <span data-ttu-id="74516-126">30%</span><span class="sxs-lookup"><span data-stu-id="74516-126">30%</span></span>          |
| <span data-ttu-id="74516-127">50,00</span><span class="sxs-lookup"><span data-stu-id="74516-127">50.00</span></span>             | <span data-ttu-id="74516-128">100,00</span><span class="sxs-lookup"><span data-stu-id="74516-128">100.00</span></span>            | <span data-ttu-id="74516-129">20%</span><span class="sxs-lookup"><span data-stu-id="74516-129">20%</span></span>          |
| <span data-ttu-id="74516-130">100,00</span><span class="sxs-lookup"><span data-stu-id="74516-130">100.00</span></span>            | <span data-ttu-id="74516-131">0,00</span><span class="sxs-lookup"><span data-stu-id="74516-131">0.00</span></span>              | <span data-ttu-id="74516-132">10%</span><span class="sxs-lookup"><span data-stu-id="74516-132">10%</span></span>          |

<span data-ttu-id="74516-133">Podatek jest obliczany według pełnej stawki opodatkowania.</span><span class="sxs-lookup"><span data-stu-id="74516-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="74516-134">Kwota opodatkowana (cena)</span><span class="sxs-lookup"><span data-stu-id="74516-134">Taxable amount (price)</span></span> | <span data-ttu-id="74516-135">Obliczenie</span><span class="sxs-lookup"><span data-stu-id="74516-135">Calculation</span></span>    | <span data-ttu-id="74516-136">Podatek</span><span class="sxs-lookup"><span data-stu-id="74516-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="74516-137">35,00</span><span class="sxs-lookup"><span data-stu-id="74516-137">35.00</span></span>                  | <span data-ttu-id="74516-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="74516-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="74516-139">10,50 zł</span><span class="sxs-lookup"><span data-stu-id="74516-139">10.50</span></span>     |
| <span data-ttu-id="74516-140">50,00</span><span class="sxs-lookup"><span data-stu-id="74516-140">50.00</span></span>                  | <span data-ttu-id="74516-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="74516-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="74516-142">15,00</span><span class="sxs-lookup"><span data-stu-id="74516-142">15.00</span></span>     |
| <span data-ttu-id="74516-143">85,00</span><span class="sxs-lookup"><span data-stu-id="74516-143">85.00</span></span>                  | <span data-ttu-id="74516-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="74516-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="74516-145">17,00</span><span class="sxs-lookup"><span data-stu-id="74516-145">17.00</span></span>     |
| <span data-ttu-id="74516-146">305,00</span><span class="sxs-lookup"><span data-stu-id="74516-146">305.00</span></span>                 | <span data-ttu-id="74516-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="74516-147">305.00 \* 0.10</span></span> | <span data-ttu-id="74516-148">30,50</span><span class="sxs-lookup"><span data-stu-id="74516-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="74516-149"> Przykład: Metoda obliczania wg interwału</span><span class="sxs-lookup"><span data-stu-id="74516-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="74516-150">Na stronie Wartości stawki podatku są skonfigurowane przy użyciu następujących interwałów:</span><span class="sxs-lookup"><span data-stu-id="74516-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="74516-151">**Dolny limit**</span><span class="sxs-lookup"><span data-stu-id="74516-151">**Minimum limit**</span></span> | <span data-ttu-id="74516-152">**Maksymalny limit**</span><span class="sxs-lookup"><span data-stu-id="74516-152">**Maximum limit**</span></span> | <span data-ttu-id="74516-153">**Stawka podatku**</span><span class="sxs-lookup"><span data-stu-id="74516-153">**Tax rate**</span></span> |
| <span data-ttu-id="74516-154">0,00</span><span class="sxs-lookup"><span data-stu-id="74516-154">0.00</span></span>              | <span data-ttu-id="74516-155">50,00</span><span class="sxs-lookup"><span data-stu-id="74516-155">50.00</span></span>             | <span data-ttu-id="74516-156">30%</span><span class="sxs-lookup"><span data-stu-id="74516-156">30%</span></span>          |
| <span data-ttu-id="74516-157">50,00</span><span class="sxs-lookup"><span data-stu-id="74516-157">50.00</span></span>             | <span data-ttu-id="74516-158">100,00</span><span class="sxs-lookup"><span data-stu-id="74516-158">100.00</span></span>            | <span data-ttu-id="74516-159">20%</span><span class="sxs-lookup"><span data-stu-id="74516-159">20%</span></span>          |
| <span data-ttu-id="74516-160">100,00</span><span class="sxs-lookup"><span data-stu-id="74516-160">100.00</span></span>            | <span data-ttu-id="74516-161">0,00</span><span class="sxs-lookup"><span data-stu-id="74516-161">0.00</span></span>              | <span data-ttu-id="74516-162">10%</span><span class="sxs-lookup"><span data-stu-id="74516-162">10%</span></span>          |

<span data-ttu-id="74516-163">Podatek jest sumą kwot podatku obliczonych dla poszczególnych interwałów kwoty.</span><span class="sxs-lookup"><span data-stu-id="74516-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="74516-164">Kwota opodatkowana (cena)</span><span class="sxs-lookup"><span data-stu-id="74516-164">Taxable amount (price)</span></span> | <span data-ttu-id="74516-165">Obliczenie</span><span class="sxs-lookup"><span data-stu-id="74516-165">Calculation</span></span>                                                               | <span data-ttu-id="74516-166">Podatek</span><span class="sxs-lookup"><span data-stu-id="74516-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="74516-167">35,00</span><span class="sxs-lookup"><span data-stu-id="74516-167">35.00</span></span>                  | <span data-ttu-id="74516-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="74516-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="74516-169">10,50 zł</span><span class="sxs-lookup"><span data-stu-id="74516-169">10.50</span></span>     |
| <span data-ttu-id="74516-170">50,00</span><span class="sxs-lookup"><span data-stu-id="74516-170">50.00</span></span>                  | <span data-ttu-id="74516-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="74516-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="74516-172">15,00</span><span class="sxs-lookup"><span data-stu-id="74516-172">15.00</span></span>     |
| <span data-ttu-id="74516-173">85,00</span><span class="sxs-lookup"><span data-stu-id="74516-173">85.00</span></span>                  | <span data-ttu-id="74516-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="74516-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="74516-175">22,00</span><span class="sxs-lookup"><span data-stu-id="74516-175">22.00</span></span>     |
| <span data-ttu-id="74516-176">305,00</span><span class="sxs-lookup"><span data-stu-id="74516-176">305.00</span></span>                 | <span data-ttu-id="74516-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="74516-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="74516-178">45.50</span><span class="sxs-lookup"><span data-stu-id="74516-178">45.50</span></span>     |



<span data-ttu-id="74516-179">Aby uzyskać więcej informacji, zobacz [Stawki podatku na podstawie pól Podstawa limitu i Metody obliczania](marginal-base-field.md).</span><span class="sxs-lookup"><span data-stu-id="74516-179">For more information, see [Sales tax rates based on the Marginal base and Calculation methods](marginal-base-field.md).</span></span>





