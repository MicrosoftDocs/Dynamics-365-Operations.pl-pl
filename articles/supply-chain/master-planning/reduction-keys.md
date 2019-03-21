---
title: Klucze redukcji
description: Ten artykuł zawiera przykłady pokazujące konfigurowanie klucza redukcji. Zawiera informacje o różnych ustawieniach kluczy redukcji i wynikach ich zastosowania. Za pomocą klucza redukcji można określić sposób zmniejszania prognozowanych zapotrzebowań.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7457aca4ca4d5188bafb497d3052276cfc154ad1
ms.sourcegitcommit: 704d273485dcdc25c97a222bc0ef0695aad334d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2019
ms.locfileid: "770923"
---
# <a name="reduction-keys"></a><span data-ttu-id="c1860-105">Klucze redukcji</span><span class="sxs-lookup"><span data-stu-id="c1860-105">Reduction keys</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1860-106">Ten artykuł zawiera przykłady pokazujące konfigurowanie klucza redukcji.</span><span class="sxs-lookup"><span data-stu-id="c1860-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="c1860-107">Zawiera informacje o różnych ustawieniach kluczy redukcji i wynikach ich zastosowania.</span><span class="sxs-lookup"><span data-stu-id="c1860-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="c1860-108">Za pomocą klucza redukcji można określić sposób zmniejszania prognozowanych zapotrzebowań.</span><span class="sxs-lookup"><span data-stu-id="c1860-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="c1860-109">Przykład 1: Procent — zasada redukcji prognozy klucza redukcji</span><span class="sxs-lookup"><span data-stu-id="c1860-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="c1860-110">W tym przykładzie pokazano, jak klucz redukcji zmniejsza wymagania dotyczące prognozy popytu według wartości procentowych i okresów, które są definiowane według klucza redukcji.</span><span class="sxs-lookup"><span data-stu-id="c1860-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1. <span data-ttu-id="c1860-111">Na stronie **Klucz redukcji** ustaw następujące wiersze.</span><span class="sxs-lookup"><span data-stu-id="c1860-111">On the **Reduction keys** page, set up the following lines.</span></span>

   | <span data-ttu-id="c1860-112">Reszta</span><span class="sxs-lookup"><span data-stu-id="c1860-112">Change</span></span> | <span data-ttu-id="c1860-113">Jednostka</span><span class="sxs-lookup"><span data-stu-id="c1860-113">Unit</span></span>  | <span data-ttu-id="c1860-114">Procent</span><span class="sxs-lookup"><span data-stu-id="c1860-114">Percent</span></span> |
   |--------|-------|---------|
   |   <span data-ttu-id="c1860-115">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="c1860-115">1</span></span>    | <span data-ttu-id="c1860-116">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="c1860-116">Month</span></span> |   <span data-ttu-id="c1860-117">100</span><span class="sxs-lookup"><span data-stu-id="c1860-117">100</span></span>   |
   |   <span data-ttu-id="c1860-118">2</span><span class="sxs-lookup"><span data-stu-id="c1860-118">2</span></span>    | <span data-ttu-id="c1860-119">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="c1860-119">Month</span></span> |   <span data-ttu-id="c1860-120">75</span><span class="sxs-lookup"><span data-stu-id="c1860-120">75</span></span>    |
   |   <span data-ttu-id="c1860-121">3</span><span class="sxs-lookup"><span data-stu-id="c1860-121">3</span></span>    | <span data-ttu-id="c1860-122">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="c1860-122">Month</span></span> |   <span data-ttu-id="c1860-123">50</span><span class="sxs-lookup"><span data-stu-id="c1860-123">50</span></span>    |
   |   <span data-ttu-id="c1860-124">4</span><span class="sxs-lookup"><span data-stu-id="c1860-124">4</span></span>    | <span data-ttu-id="c1860-125">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="c1860-125">Month</span></span> |   <span data-ttu-id="c1860-126">25</span><span class="sxs-lookup"><span data-stu-id="c1860-126">25</span></span>    |


2. <span data-ttu-id="c1860-127">Połącz klucz redukcji z grupą zapotrzebowania dla towaru.</span><span class="sxs-lookup"><span data-stu-id="c1860-127">Link the reduction key to the item's coverage group.</span></span>
3. <span data-ttu-id="c1860-128">Na stronie **Plany główne** w polu **Reguła redukcji** zaznacz **Procent — klucz redukcji**.</span><span class="sxs-lookup"><span data-stu-id="c1860-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4. <span data-ttu-id="c1860-129">Utwórz prognozę redukcji dla 1000 szt. na miesiąc.</span><span class="sxs-lookup"><span data-stu-id="c1860-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="c1860-130">Uruchomienie planowania w dniu 1 stycznia spowoduje, że wymagania prognozy popytu zostaną zużyte według wartości procentowych ustawionych na stronie **Klucze redukcji**.</span><span class="sxs-lookup"><span data-stu-id="c1860-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="c1860-131">Następujące ilości wymagania są przenoszone do planu głównego.</span><span class="sxs-lookup"><span data-stu-id="c1860-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="c1860-132">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="c1860-132">Month</span></span>                | <span data-ttu-id="c1860-133">Wymagana liczba sztuk</span><span class="sxs-lookup"><span data-stu-id="c1860-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="c1860-134">Styczeń</span><span class="sxs-lookup"><span data-stu-id="c1860-134">January</span></span>              | <span data-ttu-id="c1860-135">0</span><span class="sxs-lookup"><span data-stu-id="c1860-135">0</span></span>                         |
| <span data-ttu-id="c1860-136">Luty</span><span class="sxs-lookup"><span data-stu-id="c1860-136">February</span></span>             | <span data-ttu-id="c1860-137">250</span><span class="sxs-lookup"><span data-stu-id="c1860-137">250</span></span>                       |
| <span data-ttu-id="c1860-138">Marzec</span><span class="sxs-lookup"><span data-stu-id="c1860-138">March</span></span>                | <span data-ttu-id="c1860-139">500</span><span class="sxs-lookup"><span data-stu-id="c1860-139">500</span></span>                       |
| <span data-ttu-id="c1860-140">kwiecień</span><span class="sxs-lookup"><span data-stu-id="c1860-140">April</span></span>                | <span data-ttu-id="c1860-141">750</span><span class="sxs-lookup"><span data-stu-id="c1860-141">750</span></span>                       |
| <span data-ttu-id="c1860-142">Od maja do grudnia</span><span class="sxs-lookup"><span data-stu-id="c1860-142">May through December</span></span> | <span data-ttu-id="c1860-143">1 000</span><span class="sxs-lookup"><span data-stu-id="c1860-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="c1860-144">Przykład 2: Transakcja — zasada redukcji prognozy klucza redukcji</span><span class="sxs-lookup"><span data-stu-id="c1860-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="c1860-145">W tym przykładzie pokazano, jak rzeczywiste zamówienia występujące w okresach zdefiniowanych przez klucz redukują wymagania prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="c1860-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="c1860-146">Na stronie **Plany główne** w polu **Reguła redukcji** zaznacz **Transakcje — klucz redukcji**.</span><span class="sxs-lookup"><span data-stu-id="c1860-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="c1860-147">1 stycznia istnieją następujące zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c1860-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="c1860-148">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="c1860-148">Month</span></span>    | <span data-ttu-id="c1860-149">Zamówiona liczba sztuk</span><span class="sxs-lookup"><span data-stu-id="c1860-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="c1860-150">Styczeń</span><span class="sxs-lookup"><span data-stu-id="c1860-150">January</span></span>  | <span data-ttu-id="c1860-151">956</span><span class="sxs-lookup"><span data-stu-id="c1860-151">956</span></span>                      |
| <span data-ttu-id="c1860-152">Luty</span><span class="sxs-lookup"><span data-stu-id="c1860-152">February</span></span> | <span data-ttu-id="c1860-153">1,176</span><span class="sxs-lookup"><span data-stu-id="c1860-153">1,176</span></span>                    |
| <span data-ttu-id="c1860-154">Marzec</span><span class="sxs-lookup"><span data-stu-id="c1860-154">March</span></span>    | <span data-ttu-id="c1860-155">451</span><span class="sxs-lookup"><span data-stu-id="c1860-155">451</span></span>                      |
| <span data-ttu-id="c1860-156">Kwiecień</span><span class="sxs-lookup"><span data-stu-id="c1860-156">April</span></span>    | <span data-ttu-id="c1860-157">119</span><span class="sxs-lookup"><span data-stu-id="c1860-157">119</span></span>                      |

<span data-ttu-id="c1860-158">Przy tej samej prognozie popytu dla 1000 sztuk na miesiąc do planu głównego przesyłane są następujące ilości wymagania.</span><span class="sxs-lookup"><span data-stu-id="c1860-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="c1860-159">Miesiąc</span><span class="sxs-lookup"><span data-stu-id="c1860-159">Month</span></span>                | <span data-ttu-id="c1860-160">Wymagana liczba sztuk</span><span class="sxs-lookup"><span data-stu-id="c1860-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="c1860-161">Styczeń</span><span class="sxs-lookup"><span data-stu-id="c1860-161">January</span></span>              | <span data-ttu-id="c1860-162">44</span><span class="sxs-lookup"><span data-stu-id="c1860-162">44</span></span>                        |
| <span data-ttu-id="c1860-163">Luty</span><span class="sxs-lookup"><span data-stu-id="c1860-163">February</span></span>             | <span data-ttu-id="c1860-164">0</span><span class="sxs-lookup"><span data-stu-id="c1860-164">0</span></span>                         |
| <span data-ttu-id="c1860-165">Marzec</span><span class="sxs-lookup"><span data-stu-id="c1860-165">March</span></span>                | <span data-ttu-id="c1860-166">549</span><span class="sxs-lookup"><span data-stu-id="c1860-166">549</span></span>                       |
| <span data-ttu-id="c1860-167">kwiecień</span><span class="sxs-lookup"><span data-stu-id="c1860-167">April</span></span>                | <span data-ttu-id="c1860-168">881</span><span class="sxs-lookup"><span data-stu-id="c1860-168">881</span></span>                       |
| <span data-ttu-id="c1860-169">Od maja do grudnia</span><span class="sxs-lookup"><span data-stu-id="c1860-169">May through December</span></span> | <span data-ttu-id="c1860-170">1 000</span><span class="sxs-lookup"><span data-stu-id="c1860-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="c1860-171">Przykład 3: Transakcja — zasada redukcji prognozy okresu dynamicznego</span><span class="sxs-lookup"><span data-stu-id="c1860-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="c1860-172">W większości przypadków systemy są skonfigurowane tak, aby transakcje zmniejszały prognozy popytu w określonych okresach prognozy: tygodnie, miesiąca itd.</span><span class="sxs-lookup"><span data-stu-id="c1860-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="c1860-173">Te okresy są definiowane w kluczu redukcji.</span><span class="sxs-lookup"><span data-stu-id="c1860-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="c1860-174">Jednak czas między dwoma wierszami popytu mogą również *implikować* okresu.</span><span class="sxs-lookup"><span data-stu-id="c1860-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1. <span data-ttu-id="c1860-175">Utwórz prognozę popytu dla następujących dat i ilości.</span><span class="sxs-lookup"><span data-stu-id="c1860-175">Create a demand forecast for the following dates and quantities.</span></span>

   | <span data-ttu-id="c1860-176">Data</span><span class="sxs-lookup"><span data-stu-id="c1860-176">Date</span></span>       | <span data-ttu-id="c1860-177">Prognoza popytu</span><span class="sxs-lookup"><span data-stu-id="c1860-177">Demand forecast</span></span> |
   |------------|-----------------|
   | <span data-ttu-id="c1860-178">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="c1860-178">January 1</span></span>  | <span data-ttu-id="c1860-179">1 000</span><span class="sxs-lookup"><span data-stu-id="c1860-179">1,000</span></span>           |
   | <span data-ttu-id="c1860-180">5 stycznia</span><span class="sxs-lookup"><span data-stu-id="c1860-180">January 5</span></span>  | <span data-ttu-id="c1860-181">500</span><span class="sxs-lookup"><span data-stu-id="c1860-181">500</span></span>             |
   | <span data-ttu-id="c1860-182">12 stycznia</span><span class="sxs-lookup"><span data-stu-id="c1860-182">January 12</span></span> | <span data-ttu-id="c1860-183">1 000</span><span class="sxs-lookup"><span data-stu-id="c1860-183">1,000</span></span>           |

   <span data-ttu-id="c1860-184">W tej prognozie wyraźnie widać okres między datami prognozy: między pierwszą i drugą datą są 4 dni, a między drugą i trzecią jest 7 dni.</span><span class="sxs-lookup"><span data-stu-id="c1860-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="c1860-185">Te różne zakresy to są okresy dynamiczne.</span><span class="sxs-lookup"><span data-stu-id="c1860-185">These various spans are the dynamic periods.</span></span>
2. <span data-ttu-id="c1860-186">Utwórz wiersze zamówienia sprzedaży w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="c1860-186">Create sales order lines as follows.</span></span>

   | <span data-ttu-id="c1860-187">Data</span><span class="sxs-lookup"><span data-stu-id="c1860-187">Date</span></span>                             | <span data-ttu-id="c1860-188">Ilość dla zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c1860-188">Sales order quantity</span></span> |
   |----------------------------------|----------------------|
   | <span data-ttu-id="c1860-189">15 grudnia w poprzednim roku</span><span class="sxs-lookup"><span data-stu-id="c1860-189">December 15 in the previous year</span></span> | <span data-ttu-id="c1860-190">500</span><span class="sxs-lookup"><span data-stu-id="c1860-190">500</span></span>                  |
   | <span data-ttu-id="c1860-191">3 stycznia</span><span class="sxs-lookup"><span data-stu-id="c1860-191">January 3</span></span>                        | <span data-ttu-id="c1860-192">100</span><span class="sxs-lookup"><span data-stu-id="c1860-192">100</span></span>                  |
   | <span data-ttu-id="c1860-193">10 stycznia</span><span class="sxs-lookup"><span data-stu-id="c1860-193">January 10</span></span>                       | <span data-ttu-id="c1860-194">200</span><span class="sxs-lookup"><span data-stu-id="c1860-194">200</span></span>                  |

<span data-ttu-id="c1860-195">Prognoza będzie ograniczona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c1860-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="c1860-196">Pierwsze zamówienie sprzedaży nie mieści się w żadnym okresie, więc nie będzie ograniczona przez żadną prognozę.</span><span class="sxs-lookup"><span data-stu-id="c1860-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="c1860-197">Drugie zamówienie sprzedaży mieści się w dniach 1-5 stycznia, więc ograniczy prognozę dla 1 stycznia o 100.</span><span class="sxs-lookup"><span data-stu-id="c1860-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="c1860-198">Trzecie zamówienie sprzedaży mieści się w dniach 5-12 stycznia, więc ograniczy prognozę dla 5 stycznia o 200.</span><span class="sxs-lookup"><span data-stu-id="c1860-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="c1860-199">Zostanie utworzone następujące planowane zamówienie w celu wypełnienia prognozy.</span><span class="sxs-lookup"><span data-stu-id="c1860-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="c1860-200">Data prognozy popytu</span><span class="sxs-lookup"><span data-stu-id="c1860-200">Demand forecast date</span></span> | <span data-ttu-id="c1860-201">Zmniejszona ilość</span><span class="sxs-lookup"><span data-stu-id="c1860-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="c1860-202">1 stycznia</span><span class="sxs-lookup"><span data-stu-id="c1860-202">January 1</span></span>            | <span data-ttu-id="c1860-203">900</span><span class="sxs-lookup"><span data-stu-id="c1860-203">900</span></span>              |
| <span data-ttu-id="c1860-204">5 stycznia</span><span class="sxs-lookup"><span data-stu-id="c1860-204">January 5</span></span>            | <span data-ttu-id="c1860-205">300</span><span class="sxs-lookup"><span data-stu-id="c1860-205">300</span></span>              |
| <span data-ttu-id="c1860-206">12 stycznia</span><span class="sxs-lookup"><span data-stu-id="c1860-206">January 12</span></span>           | <span data-ttu-id="c1860-207">1 000</span><span class="sxs-lookup"><span data-stu-id="c1860-207">1,000</span></span>            |

<span data-ttu-id="c1860-208">Poniżej przedstawiono podsumowanie redukcji **transakcji — okres dynamiczny**:</span><span class="sxs-lookup"><span data-stu-id="c1860-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="c1860-209">Wymagania prognozy są ograniczone przez rzeczywiste transakcje zamówienia występujące w okresie dynamicznym.</span><span class="sxs-lookup"><span data-stu-id="c1860-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="c1860-210">Okres dynamiczny obejmuje aktualne daty prognozy i kończy się na początku kolejnej prognozy.</span><span class="sxs-lookup"><span data-stu-id="c1860-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="c1860-211">Ta metoda nie używa ani nie wymaga klucza redukcji.</span><span class="sxs-lookup"><span data-stu-id="c1860-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="c1860-212">Ta opcja jest używana, występują następujące zachowania:</span><span class="sxs-lookup"><span data-stu-id="c1860-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="c1860-213">Jeśli prognoza zostanie zmniejszona do zera, wymagania prognozy dla bieżącej prognozy przybierają wartość 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c1860-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="c1860-214">Jeśli nie ma żadnej przyszłej prognozy, wymagania prognozy z ostatnio wprowadzonej prognozy są redukowane.</span><span class="sxs-lookup"><span data-stu-id="c1860-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="c1860-215">Horyzonty czasowe są uwzględniane w obliczeniach redukcji prognozy.</span><span class="sxs-lookup"><span data-stu-id="c1860-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="c1860-216">Dni pasywne są uwzględniane w obliczeniach redukcji prognozy.</span><span class="sxs-lookup"><span data-stu-id="c1860-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="c1860-217">Jeśli transakcje rzeczywistego zamówienia przekraczają prognozowane zapotrzebowanie, pozostałe transakcje nie są przekazywane do następnego okresu prognozy.</span><span class="sxs-lookup"><span data-stu-id="c1860-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="additional-resources"></a><span data-ttu-id="c1860-218">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c1860-218">Additional resources</span></span>
--------

[<span data-ttu-id="c1860-219">Plany główne</span><span class="sxs-lookup"><span data-stu-id="c1860-219">Master plans</span></span>](master-plans.md)



