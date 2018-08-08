---
title: "Opcje Cała kwota i Obliczanie interwału dla kodów podatku"
description: "W tym artykule opisano opcje dostępne w polu Metoda obliczania w ustawieniach kodów podatków oraz wyjaśniono sposób obliczania podatku dla interwałów kwot i całych kwot."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Retail
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: d16ea19a6d3cfea325281f301e0502bb051381d9
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="9b368-103">Opcje Cała kwota i Obliczanie interwału dla kodów podatku</span><span class="sxs-lookup"><span data-stu-id="9b368-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

<span data-ttu-id="9b368-104">W tym artykule opisano opcje dostępne w polu Metoda obliczania w ustawieniach kodów podatków oraz wyjaśniono sposób obliczania podatku dla interwałów kwot i całych kwot.</span><span class="sxs-lookup"><span data-stu-id="9b368-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="9b368-105">można skonfigurować kod podatku, który ma być obliczany na podstawie jednej całej kwoty lub kwoty interwału.</span><span class="sxs-lookup"><span data-stu-id="9b368-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="9b368-106">Na stronie Kody podatków użyj pola Metoda obliczania na karcie skróconej Obliczanie, aby wybrać, jak ma być obliczany kod podatku.</span><span class="sxs-lookup"><span data-stu-id="9b368-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
- <span data-ttu-id="9b368-107">Cała kwota — stawka podatku jest stosowana do całej kwoty opodatkowanej.</span><span class="sxs-lookup"><span data-stu-id="9b368-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
- <span data-ttu-id="9b368-108">Interwał — kwota opodatkowana jest dzielona na części, z których każda mieści się w zakresie o określonej stawce podatku.</span><span class="sxs-lookup"><span data-stu-id="9b368-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="9b368-109">Część tej kwoty należąca do danego interwału jest opodatkowana według stawki podatku określonej dla tego interwału.</span><span class="sxs-lookup"><span data-stu-id="9b368-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="9b368-110">Podatek jest sumą kwot podatku obliczonych dla poszczególnych interwałów kwoty.</span><span class="sxs-lookup"><span data-stu-id="9b368-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
  > [!NOTE]                                                                                                                              
  > <span data-ttu-id="9b368-111">Opcja Interwał jest dostępna tylko po wybraniu opcji Wiersz w polu Obliczanie w obszarze Podatek na stronie Parametry księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="9b368-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="9b368-112">Interwały są konfigurowane na stronie Wartości kodu podatku poprzez wprowadzanie kwot Minimalna i Maksymalna dla stawki podatkowej.</span><span class="sxs-lookup"><span data-stu-id="9b368-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="9b368-113">Aby podatki były obliczane dla wszystkich kwot opodatkowanych — niezależnie od wyboru metody obliczania — interwały muszą podlegać następującym regułom:</span><span class="sxs-lookup"><span data-stu-id="9b368-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="9b368-114">Pierwszy interwał musi mieć Minimalny limit zero.</span><span class="sxs-lookup"><span data-stu-id="9b368-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="9b368-115">Ostatni interwał musi mieć Maksymalny limit zero, który oznacza nieskończoność.</span><span class="sxs-lookup"><span data-stu-id="9b368-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="9b368-116">Maksymalny limit interwału musi być Minimalnym limitem następnego interwału.</span><span class="sxs-lookup"><span data-stu-id="9b368-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="9b368-117">Jeśli kwota jest równa Maksymalnemu limitowi poprzedniego interwału i Minimalnemu limitowi następnego interwału, stosowany jest do niej podatek pierwszego interwału.</span><span class="sxs-lookup"><span data-stu-id="9b368-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="9b368-118">Jeśli kwota nie należy do żadnego z interwałów określonych przez górne i dolne limity, stosowana jest stawka podatku równa 0.</span><span class="sxs-lookup"><span data-stu-id="9b368-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="9b368-119">Przykład: Metoda obliczania wg całej kwoty</span><span class="sxs-lookup"><span data-stu-id="9b368-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="9b368-120">Na stronie Wartości kodu podatku stawki podatku są skonfigurowane przy użyciu następujących interwałów:</span><span class="sxs-lookup"><span data-stu-id="9b368-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="9b368-121">**Dolny limit**</span><span class="sxs-lookup"><span data-stu-id="9b368-121">**Minimum limit**</span></span> | <span data-ttu-id="9b368-122">**Maksymalny limit**</span><span class="sxs-lookup"><span data-stu-id="9b368-122">**Maximum limit**</span></span> | <span data-ttu-id="9b368-123">**Stawka podatku**</span><span class="sxs-lookup"><span data-stu-id="9b368-123">**Tax rate**</span></span> |
| <span data-ttu-id="9b368-124">0,00</span><span class="sxs-lookup"><span data-stu-id="9b368-124">0.00</span></span>              | <span data-ttu-id="9b368-125">50,00</span><span class="sxs-lookup"><span data-stu-id="9b368-125">50.00</span></span>             | <span data-ttu-id="9b368-126">30%</span><span class="sxs-lookup"><span data-stu-id="9b368-126">30%</span></span>          |
| <span data-ttu-id="9b368-127">50,00</span><span class="sxs-lookup"><span data-stu-id="9b368-127">50.00</span></span>             | <span data-ttu-id="9b368-128">100,00</span><span class="sxs-lookup"><span data-stu-id="9b368-128">100.00</span></span>            | <span data-ttu-id="9b368-129">20%</span><span class="sxs-lookup"><span data-stu-id="9b368-129">20%</span></span>          |
| <span data-ttu-id="9b368-130">100,00</span><span class="sxs-lookup"><span data-stu-id="9b368-130">100.00</span></span>            | <span data-ttu-id="9b368-131">0,00</span><span class="sxs-lookup"><span data-stu-id="9b368-131">0.00</span></span>              | <span data-ttu-id="9b368-132">10%</span><span class="sxs-lookup"><span data-stu-id="9b368-132">10%</span></span>          |

<span data-ttu-id="9b368-133">Podatek jest obliczany według pełnej stawki opodatkowania.</span><span class="sxs-lookup"><span data-stu-id="9b368-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="9b368-134">Kwota opodatkowana (cena)</span><span class="sxs-lookup"><span data-stu-id="9b368-134">Taxable amount (price)</span></span> | <span data-ttu-id="9b368-135">Obliczenie</span><span class="sxs-lookup"><span data-stu-id="9b368-135">Calculation</span></span>    | <span data-ttu-id="9b368-136">Podatek</span><span class="sxs-lookup"><span data-stu-id="9b368-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="9b368-137">35,00</span><span class="sxs-lookup"><span data-stu-id="9b368-137">35.00</span></span>                  | <span data-ttu-id="9b368-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="9b368-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="9b368-139">10,50 zł</span><span class="sxs-lookup"><span data-stu-id="9b368-139">10.50</span></span>     |
| <span data-ttu-id="9b368-140">50,00</span><span class="sxs-lookup"><span data-stu-id="9b368-140">50.00</span></span>                  | <span data-ttu-id="9b368-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="9b368-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="9b368-142">15,00</span><span class="sxs-lookup"><span data-stu-id="9b368-142">15.00</span></span>     |
| <span data-ttu-id="9b368-143">85,00</span><span class="sxs-lookup"><span data-stu-id="9b368-143">85.00</span></span>                  | <span data-ttu-id="9b368-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="9b368-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="9b368-145">17,00</span><span class="sxs-lookup"><span data-stu-id="9b368-145">17.00</span></span>     |
| <span data-ttu-id="9b368-146">305,00</span><span class="sxs-lookup"><span data-stu-id="9b368-146">305.00</span></span>                 | <span data-ttu-id="9b368-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="9b368-147">305.00 \* 0.10</span></span> | <span data-ttu-id="9b368-148">30,50</span><span class="sxs-lookup"><span data-stu-id="9b368-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="9b368-149"> Przykład: Metoda obliczania wg interwału</span><span class="sxs-lookup"><span data-stu-id="9b368-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="9b368-150">Na stronie Wartości stawki podatku są skonfigurowane przy użyciu następujących interwałów:</span><span class="sxs-lookup"><span data-stu-id="9b368-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="9b368-151">**Dolny limit**</span><span class="sxs-lookup"><span data-stu-id="9b368-151">**Minimum limit**</span></span> | <span data-ttu-id="9b368-152">**Maksymalny limit**</span><span class="sxs-lookup"><span data-stu-id="9b368-152">**Maximum limit**</span></span> | <span data-ttu-id="9b368-153">**Stawka podatku**</span><span class="sxs-lookup"><span data-stu-id="9b368-153">**Tax rate**</span></span> |
| <span data-ttu-id="9b368-154">0,00</span><span class="sxs-lookup"><span data-stu-id="9b368-154">0.00</span></span>              | <span data-ttu-id="9b368-155">50,00</span><span class="sxs-lookup"><span data-stu-id="9b368-155">50.00</span></span>             | <span data-ttu-id="9b368-156">30%</span><span class="sxs-lookup"><span data-stu-id="9b368-156">30%</span></span>          |
| <span data-ttu-id="9b368-157">50,00</span><span class="sxs-lookup"><span data-stu-id="9b368-157">50.00</span></span>             | <span data-ttu-id="9b368-158">100,00</span><span class="sxs-lookup"><span data-stu-id="9b368-158">100.00</span></span>            | <span data-ttu-id="9b368-159">20%</span><span class="sxs-lookup"><span data-stu-id="9b368-159">20%</span></span>          |
| <span data-ttu-id="9b368-160">100,00</span><span class="sxs-lookup"><span data-stu-id="9b368-160">100.00</span></span>            | <span data-ttu-id="9b368-161">0,00</span><span class="sxs-lookup"><span data-stu-id="9b368-161">0.00</span></span>              | <span data-ttu-id="9b368-162">10%</span><span class="sxs-lookup"><span data-stu-id="9b368-162">10%</span></span>          |

<span data-ttu-id="9b368-163">Podatek jest sumą kwot podatku obliczonych dla poszczególnych interwałów kwoty.</span><span class="sxs-lookup"><span data-stu-id="9b368-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="9b368-164">Kwota opodatkowana (cena)</span><span class="sxs-lookup"><span data-stu-id="9b368-164">Taxable amount (price)</span></span> | <span data-ttu-id="9b368-165">Obliczenie</span><span class="sxs-lookup"><span data-stu-id="9b368-165">Calculation</span></span>                                                               | <span data-ttu-id="9b368-166">Podatek</span><span class="sxs-lookup"><span data-stu-id="9b368-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="9b368-167">35,00</span><span class="sxs-lookup"><span data-stu-id="9b368-167">35.00</span></span>                  | <span data-ttu-id="9b368-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="9b368-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="9b368-169">10,50 zł</span><span class="sxs-lookup"><span data-stu-id="9b368-169">10.50</span></span>     |
| <span data-ttu-id="9b368-170">50,00</span><span class="sxs-lookup"><span data-stu-id="9b368-170">50.00</span></span>                  | <span data-ttu-id="9b368-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="9b368-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="9b368-172">15,00</span><span class="sxs-lookup"><span data-stu-id="9b368-172">15.00</span></span>     |
| <span data-ttu-id="9b368-173">85,00</span><span class="sxs-lookup"><span data-stu-id="9b368-173">85.00</span></span>                  | <span data-ttu-id="9b368-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="9b368-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="9b368-175">22,00</span><span class="sxs-lookup"><span data-stu-id="9b368-175">22.00</span></span>     |
| <span data-ttu-id="9b368-176">305,00</span><span class="sxs-lookup"><span data-stu-id="9b368-176">305.00</span></span>                 | <span data-ttu-id="9b368-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="9b368-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="9b368-178">45,50</span><span class="sxs-lookup"><span data-stu-id="9b368-178">45.50</span></span>     |



<span data-ttu-id="9b368-179">Aby uzyskać więcej informacji, zobacz [Ustalanie stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania](marginal-base-field.md).</span><span class="sxs-lookup"><span data-stu-id="9b368-179">For more information, see [Determining sale tax rates based on the Marginal base and Calculation method fields](marginal-base-field.md).</span></span>






