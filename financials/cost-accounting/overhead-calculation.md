---
title: Obliczenie narzutu
description: "W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 9e13fc9fa7e51a1299ca8698f581de979b680a7b
ms.openlocfilehash: a8c867ba49b95af2816fe8294059307e974c0a81
ms.contentlocale: pl-pl
ms.lasthandoff: 09/18/2017

---

# <a name="overhead-calculation"></a><span data-ttu-id="27da8-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="27da8-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="27da8-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="27da8-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="27da8-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="27da8-105">Term definition</span></span>
---------------

<span data-ttu-id="27da8-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="27da8-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="27da8-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="27da8-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="27da8-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="27da8-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="27da8-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="27da8-109">Rent</span></span>
-   <span data-ttu-id="27da8-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-110">Electricity</span></span>
-   <span data-ttu-id="27da8-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="27da8-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="27da8-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="27da8-112">Overhead calculation overview</span></span>
<span data-ttu-id="27da8-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="27da8-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="27da8-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="27da8-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="27da8-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="27da8-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="27da8-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="27da8-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="27da8-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="27da8-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="27da8-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="27da8-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="27da8-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="27da8-119">Version type</span></span>
-   <span data-ttu-id="27da8-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="27da8-120">Date and time</span></span>
-   <span data-ttu-id="27da8-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="27da8-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="27da8-122">Fiscal year</span></span>
-   <span data-ttu-id="27da8-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="27da8-123">Fiscal period</span></span>

<span data-ttu-id="27da8-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="27da8-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="27da8-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="27da8-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="27da8-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="27da8-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="27da8-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="27da8-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="27da8-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="27da8-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="27da8-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="27da8-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-130">Therefore, you always have full traceability.</span></span> 
<span data-ttu-id="27da8-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="27da8-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="27da8-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="27da8-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="27da8-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="27da8-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="27da8-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="27da8-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="27da8-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="27da8-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="27da8-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="27da8-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="27da8-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="27da8-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="27da8-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="27da8-140">Main account</span></span></th>
<th><span data-ttu-id="27da8-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="27da8-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="27da8-143">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-143">CC099</span></span></td>
<td><span data-ttu-id="27da8-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-144">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-145">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-145">10001</span></span></td>
<td><span data-ttu-id="27da8-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-146">Electricity</span></span></td>
<td><span data-ttu-id="27da8-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="27da8-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="27da8-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="27da8-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="27da8-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="27da8-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="27da8-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-151">Define the cost behavior rule</span></span>

<span data-ttu-id="27da8-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="27da8-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="27da8-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="27da8-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="27da8-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="27da8-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="27da8-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="27da8-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="27da8-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="27da8-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="27da8-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="27da8-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="27da8-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="27da8-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="27da8-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="27da8-160">Journal</span></span></th>
<th><span data-ttu-id="27da8-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="27da8-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="27da8-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="27da8-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="27da8-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="27da8-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-164">00001</span><span class="sxs-lookup"><span data-stu-id="27da8-164">00001</span></span></td>
<td><span data-ttu-id="27da8-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="27da8-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="27da8-166">Fiscal</span></span></td>
<td><span data-ttu-id="27da8-167">2017</span><span class="sxs-lookup"><span data-stu-id="27da8-167">2017</span></span></td>
<td><span data-ttu-id="27da8-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="27da8-168">Period 1</span></span></td>
<td><span data-ttu-id="27da8-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="27da8-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="27da8-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="27da8-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="27da8-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="27da8-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-173">Cost element</span></span></th>
<th><span data-ttu-id="27da8-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-174">Cost behavior</span></span></th>
<th><span data-ttu-id="27da8-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="27da8-177">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-177">CC099</span></span></td>
<td><span data-ttu-id="27da8-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-178">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-179">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-179">10001</span></span></td>
<td><span data-ttu-id="27da8-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-180">Electricity</span></span></td>
<td><span data-ttu-id="27da8-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="27da8-181">Unclassified</span></span></td>
<td><span data-ttu-id="27da8-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="27da8-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="27da8-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-185">Cost element</span></span></th>
<th><span data-ttu-id="27da8-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-186">Cost behavior</span></span></th>
<th><span data-ttu-id="27da8-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-187">Amount</span></span></th>
<th><span data-ttu-id="27da8-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="27da8-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-189">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-189">CC099</span></span></td>
<td><span data-ttu-id="27da8-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-190">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-191">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-191">10001</span></span></td>
<td><span data-ttu-id="27da8-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-192">Electricity</span></span></td>
<td><span data-ttu-id="27da8-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="27da8-193">Unclassified</span></span></td>
<td><span data-ttu-id="27da8-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="27da8-194">10,000.00</span></span></td>
<td><span data-ttu-id="27da8-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-196">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-196">CC099</span></span></td>
<td><span data-ttu-id="27da8-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-197">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-198">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-198">10001</span></span></td>
<td><span data-ttu-id="27da8-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-199">Electricity</span></span></td>
<td><span data-ttu-id="27da8-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="27da8-200">Unclassified</span></span></td>
<td><span data-ttu-id="27da8-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-201">-10,000.00</span></span></td>
<td><span data-ttu-id="27da8-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-203">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-203">CC099</span></span></td>
<td><span data-ttu-id="27da8-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-204">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-205">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-205">10001</span></span></td>
<td><span data-ttu-id="27da8-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-206">Electricity</span></span></td>
<td><span data-ttu-id="27da8-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-207">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-208">1,000.00</span></span></td>
<td><span data-ttu-id="27da8-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-210">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-210">CC099</span></span></td>
<td><span data-ttu-id="27da8-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-211">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-212">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-212">10001</span></span></td>
<td><span data-ttu-id="27da8-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-213">Electricity</span></span></td>
<td><span data-ttu-id="27da8-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-214">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="27da8-215">9,000.00</span></span></td>
<td><span data-ttu-id="27da8-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-217">Aby uzyskać szczegółowe informacje o zachowaniu kosztów, zobacz temat Zasada zachowania kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="27da8-218">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="27da8-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="27da8-219">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="27da8-220">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="27da8-221">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="27da8-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="27da8-222">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-222">Define the cost distribution rule</span></span>

<span data-ttu-id="27da8-223">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="27da8-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="27da8-224">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="27da8-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="27da8-225">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="27da8-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="27da8-226">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="27da8-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="27da8-227">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="27da8-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="27da8-228">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-229">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-229">Cost object</span></span></th>
<th><span data-ttu-id="27da8-230">kWh</span><span class="sxs-lookup"><span data-stu-id="27da8-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-231">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-231">CC001</span></span></td>
<td><span data-ttu-id="27da8-232">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-232">HR</span></span></td>
<td><span data-ttu-id="27da8-233">1 000</span><span class="sxs-lookup"><span data-stu-id="27da8-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-234">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-234">CC002</span></span></td>
<td><span data-ttu-id="27da8-235">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-235">Finance</span></span></td>
<td><span data-ttu-id="27da8-236">6,000</span><span class="sxs-lookup"><span data-stu-id="27da8-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-237">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-237">CC003</span></span></td>
<td><span data-ttu-id="27da8-238">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-238">Assembly</span></span></td>
<td><span data-ttu-id="27da8-239">0</span><span class="sxs-lookup"><span data-stu-id="27da8-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-240">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="27da8-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-241">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-241">Cost object</span></span></th>
<th><span data-ttu-id="27da8-242">Wartość</span><span class="sxs-lookup"><span data-stu-id="27da8-242">Magnitude</span></span></th>
<th><span data-ttu-id="27da8-243">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="27da8-243">Allocation factor</span></span></th>
<th><span data-ttu-id="27da8-244">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-245">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-245">CC001</span></span></td>
<td><span data-ttu-id="27da8-246">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-246">HR</span></span></td>
<td><span data-ttu-id="27da8-247">1 000</span><span class="sxs-lookup"><span data-stu-id="27da8-247">1,000</span></span></td>
<td><span data-ttu-id="27da8-248">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="27da8-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="27da8-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-250">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-250">CC002</span></span></td>
<td><span data-ttu-id="27da8-251">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-251">Finance</span></span></td>
<td><span data-ttu-id="27da8-252">6,000</span><span class="sxs-lookup"><span data-stu-id="27da8-252">6,000</span></span></td>
<td><span data-ttu-id="27da8-253">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="27da8-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="27da8-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-255">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-255">CC003</span></span></td>
<td><span data-ttu-id="27da8-256">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-256">Assembly</span></span></td>
<td><span data-ttu-id="27da8-257">0</span><span class="sxs-lookup"><span data-stu-id="27da8-257">0</span></span></td>
<td><span data-ttu-id="27da8-258">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="27da8-259">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-260">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="27da8-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="27da8-261">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="27da8-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-262">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-262">Cost object</span></span></th>
<th><span data-ttu-id="27da8-263">Wzór</span><span class="sxs-lookup"><span data-stu-id="27da8-263">Formula</span></span></th>
<th><span data-ttu-id="27da8-264">Wartość</span><span class="sxs-lookup"><span data-stu-id="27da8-264">Magnitude</span></span></th>
<th><span data-ttu-id="27da8-265">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="27da8-265">Allocation factor</span></span></th>
<th><span data-ttu-id="27da8-266">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-267">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-267">CC001</span></span></td>
<td><span data-ttu-id="27da8-268">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-268">HR</span></span></td>
<td><span data-ttu-id="27da8-269">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="27da8-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="27da8-270">1</span><span class="sxs-lookup"><span data-stu-id="27da8-270">1</span></span></td>
<td><span data-ttu-id="27da8-271">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="27da8-272">500.00</span><span class="sxs-lookup"><span data-stu-id="27da8-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-273">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-273">CC002</span></span></td>
<td><span data-ttu-id="27da8-274">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-274">Finance</span></span></td>
<td><span data-ttu-id="27da8-275">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="27da8-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="27da8-276">1</span><span class="sxs-lookup"><span data-stu-id="27da8-276">1</span></span></td>
<td><span data-ttu-id="27da8-277">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="27da8-278">500.00</span><span class="sxs-lookup"><span data-stu-id="27da8-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-279">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-279">CC003</span></span></td>
<td><span data-ttu-id="27da8-280">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-280">Assembly</span></span></td>
<td><span data-ttu-id="27da8-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="27da8-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="27da8-282">0</span><span class="sxs-lookup"><span data-stu-id="27da8-282">0</span></span></td>
<td><span data-ttu-id="27da8-283">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="27da8-284">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="27da8-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="27da8-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="27da8-286">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="27da8-286">Journal</span></span></th>
<th><span data-ttu-id="27da8-287">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="27da8-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="27da8-288">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="27da8-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="27da8-289">Wersja</span><span class="sxs-lookup"><span data-stu-id="27da8-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-290">00002</span><span class="sxs-lookup"><span data-stu-id="27da8-290">00002</span></span></td>
<td><span data-ttu-id="27da8-291">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="27da8-292">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="27da8-292">Fiscal</span></span></td>
<td><span data-ttu-id="27da8-293">2017</span><span class="sxs-lookup"><span data-stu-id="27da8-293">2017</span></span></td>
<td><span data-ttu-id="27da8-294">Okres 1</span><span class="sxs-lookup"><span data-stu-id="27da8-294">Period 1</span></span></td>
<td><span data-ttu-id="27da8-295">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="27da8-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="27da8-296">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="27da8-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="27da8-297">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="27da8-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-298">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-299">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-299">Cost element</span></span></th>
<th><span data-ttu-id="27da8-300">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-300">Cost behavior</span></span></th>
<th><span data-ttu-id="27da8-301">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-302">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-303">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-303">CC099</span></span></td>
<td><span data-ttu-id="27da8-304">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-304">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-305">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-305">10001</span></span></td>
<td><span data-ttu-id="27da8-306">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-306">Electricity</span></span></td>
<td><span data-ttu-id="27da8-307">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-307">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-308">1000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-309">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-310">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-310">CC099</span></span></td>
<td><span data-ttu-id="27da8-311">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-311">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-312">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-312">10001</span></span></td>
<td><span data-ttu-id="27da8-313">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-313">Electricity</span></span></td>
<td><span data-ttu-id="27da8-314">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-314">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="27da8-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="27da8-316">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-317">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-318">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-318">Cost element</span></span></th>
<th><span data-ttu-id="27da8-319">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-319">Cost behavior</span></span></th>
<th><span data-ttu-id="27da8-320">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-320">Amount</span></span></th>
<th><span data-ttu-id="27da8-321">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="27da8-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-322">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-322">CC099</span></span></td>
<td><span data-ttu-id="27da8-323">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-323">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-324">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-324">10001</span></span></td>
<td><span data-ttu-id="27da8-325">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-325">Electricity</span></span></td>
<td><span data-ttu-id="27da8-326">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-326">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-327">-1000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-327">-1,000.00</span></span></td>
<td><span data-ttu-id="27da8-328">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-329">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-329">CC001</span></span></td>
<td><span data-ttu-id="27da8-330">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-330">HR</span></span></td>
<td><span data-ttu-id="27da8-331">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-331">10001</span></span></td>
<td><span data-ttu-id="27da8-332">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-332">Electricity</span></span></td>
<td><span data-ttu-id="27da8-333">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-333">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-334">500.00</span><span class="sxs-lookup"><span data-stu-id="27da8-334">500.00</span></span></td>
<td><span data-ttu-id="27da8-335">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-336">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-336">CC002</span></span></td>
<td><span data-ttu-id="27da8-337">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-337">Finance</span></span></td>
<td><span data-ttu-id="27da8-338">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-338">10001</span></span></td>
<td><span data-ttu-id="27da8-339">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-339">Electricity</span></span></td>
<td><span data-ttu-id="27da8-340">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-340">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-341">500.00</span><span class="sxs-lookup"><span data-stu-id="27da8-341">500.00</span></span></td>
<td><span data-ttu-id="27da8-342">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-343">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-343">CC099</span></span></td>
<td><span data-ttu-id="27da8-344">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-344">Default cost center</span></span></td>
<td><span data-ttu-id="27da8-345">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-345">10001</span></span></td>
<td><span data-ttu-id="27da8-346">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-346">Electricity</span></span></td>
<td><span data-ttu-id="27da8-347">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-347">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-348">-9000,00</span><span class="sxs-lookup"><span data-stu-id="27da8-348">-9,000.00</span></span></td>
<td><span data-ttu-id="27da8-349">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-350">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-350">CC001</span></span></td>
<td><span data-ttu-id="27da8-351">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-351">HR</span></span></td>
<td><span data-ttu-id="27da8-352">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-352">10001</span></span></td>
<td><span data-ttu-id="27da8-353">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-353">Electricity</span></span></td>
<td><span data-ttu-id="27da8-354">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-354">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="27da8-355">1,285.71</span></span></td>
<td><span data-ttu-id="27da8-356">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-357">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-357">CC002</span></span></td>
<td><span data-ttu-id="27da8-358">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-358">Finance</span></span></td>
<td><span data-ttu-id="27da8-359">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-359">10001</span></span></td>
<td><span data-ttu-id="27da8-360">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-360">Electricity</span></span></td>
<td><span data-ttu-id="27da8-361">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-361">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="27da8-362">7,714.29</span></span></td>
<td><span data-ttu-id="27da8-363">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-364">Aby uzyskać szczegółowe informacje na temat dystrybucji kosztów i podstaw alokacji, zobacz tematy Zasada dystrybucji kosztów i Podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="27da8-365">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="27da8-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="27da8-366">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="27da8-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="27da8-367">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="27da8-368">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="27da8-369">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="27da8-369">Define the overhead rate</span></span>

<span data-ttu-id="27da8-370">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="27da8-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="27da8-371">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="27da8-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-372">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-372">Cost object</span></span></th>
<th><span data-ttu-id="27da8-373">Godziny</span><span class="sxs-lookup"><span data-stu-id="27da8-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="27da8-374">Proj 1</span></span></td>
<td><span data-ttu-id="27da8-375">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-375">Project 1</span></span></td>
<td><span data-ttu-id="27da8-376">3</span><span class="sxs-lookup"><span data-stu-id="27da8-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="27da8-377">Proj 2</span></span></td>
<td><span data-ttu-id="27da8-378">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-378">Project 2</span></span></td>
<td><span data-ttu-id="27da8-379">1</span><span class="sxs-lookup"><span data-stu-id="27da8-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-380">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="27da8-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-381">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-381">Cost object</span></span></th>
<th><span data-ttu-id="27da8-382">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-382">Cost element</span></span></th>
<th><span data-ttu-id="27da8-383">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-383">Cost behavior</span></span></th>
<th><span data-ttu-id="27da8-384">Jednostki</span><span class="sxs-lookup"><span data-stu-id="27da8-384">Units</span></span></th>
<th><span data-ttu-id="27da8-385">Kurs</span><span class="sxs-lookup"><span data-stu-id="27da8-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-386">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-386">CC001</span></span></td>
<td><span data-ttu-id="27da8-387">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-387">HR</span></span></td>
<td><span data-ttu-id="27da8-388">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-388">10001</span></span></td>
<td><span data-ttu-id="27da8-389">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-389">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-390">1</span><span class="sxs-lookup"><span data-stu-id="27da8-390">1</span></span></td>
<td><span data-ttu-id="27da8-391">10</span><span class="sxs-lookup"><span data-stu-id="27da8-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-392">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-393">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-393">Cost object</span></span></th>
<th><span data-ttu-id="27da8-394">Wartość</span><span class="sxs-lookup"><span data-stu-id="27da8-394">Magnitude</span></span></th>
<th><span data-ttu-id="27da8-395">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-395">Cost element</span></span></th>
<th><span data-ttu-id="27da8-396">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="27da8-396">Allocation factor</span></span></th>
<th><span data-ttu-id="27da8-397">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="27da8-398">Proj 1</span></span></td>
<td><span data-ttu-id="27da8-399">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-399">Project 1</span></span></td>
<td><span data-ttu-id="27da8-400">3</span><span class="sxs-lookup"><span data-stu-id="27da8-400">3</span></span></td>
<td><span data-ttu-id="27da8-401">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-401">10001</span></span></td>
<td><span data-ttu-id="27da8-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="27da8-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="27da8-403">30.00</span><span class="sxs-lookup"><span data-stu-id="27da8-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="27da8-404">Proj 2</span></span></td>
<td><span data-ttu-id="27da8-405">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-405">Project 2</span></span></td>
<td><span data-ttu-id="27da8-406">1</span><span class="sxs-lookup"><span data-stu-id="27da8-406">1</span></span></td>
<td><span data-ttu-id="27da8-407">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-407">10001</span></span></td>
<td><span data-ttu-id="27da8-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="27da8-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="27da8-409">10,00</span><span class="sxs-lookup"><span data-stu-id="27da8-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="27da8-410">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="27da8-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="27da8-411">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="27da8-411">Journal</span></span></th>
<th><span data-ttu-id="27da8-412">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="27da8-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="27da8-413">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="27da8-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="27da8-414">Wersja</span><span class="sxs-lookup"><span data-stu-id="27da8-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-415">00003</span><span class="sxs-lookup"><span data-stu-id="27da8-415">00003</span></span></td>
<td><span data-ttu-id="27da8-416">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="27da8-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="27da8-417">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="27da8-417">Fiscal</span></span></td>
<td><span data-ttu-id="27da8-418">2017</span><span class="sxs-lookup"><span data-stu-id="27da8-418">2017</span></span></td>
<td><span data-ttu-id="27da8-419">Okres 1</span><span class="sxs-lookup"><span data-stu-id="27da8-419">Period 1</span></span></td>
<td><span data-ttu-id="27da8-420">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="27da8-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="27da8-421">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="27da8-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="27da8-422">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="27da8-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-423">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-423">Cost object</span></span></th>
<th><span data-ttu-id="27da8-424">Wartość</span><span class="sxs-lookup"><span data-stu-id="27da8-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-425">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="27da8-426">Proj 1</span></span></td>
<td><span data-ttu-id="27da8-427">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="27da8-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="27da8-428">3,00</span><span class="sxs-lookup"><span data-stu-id="27da8-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-429">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="27da8-430">Proj 2</span></span></td>
<td><span data-ttu-id="27da8-431">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="27da8-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="27da8-432">1.00</span><span class="sxs-lookup"><span data-stu-id="27da8-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="27da8-433">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-434">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-435">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-435">Cost element</span></span></th>
<th><span data-ttu-id="27da8-436">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-436">Cost behavior</span></span></th>
<th><span data-ttu-id="27da8-437">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-437">Amount</span></span></th>
<th><span data-ttu-id="27da8-438">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="27da8-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="27da8-439">CC0001</span></span></td>
<td><span data-ttu-id="27da8-440">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-440">HR</span></span></td>
<td><span data-ttu-id="27da8-441">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-441">10001</span></span></td>
<td><span data-ttu-id="27da8-442">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-442">Electricity</span></span></td>
<td><span data-ttu-id="27da8-443">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-443">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="27da8-444">-30.00</span></span></td>
<td><span data-ttu-id="27da8-445">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="27da8-446">Proj 1</span></span></td>
<td><span data-ttu-id="27da8-447">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="27da8-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="27da8-448">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-448">10001</span></span></td>
<td><span data-ttu-id="27da8-449">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-449">Electricity</span></span></td>
<td><span data-ttu-id="27da8-450">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-450">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-451">30.00</span><span class="sxs-lookup"><span data-stu-id="27da8-451">30.00</span></span></td>
<td><span data-ttu-id="27da8-452">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-453">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-453">CC001</span></span></td>
<td><span data-ttu-id="27da8-454">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-454">HR</span></span></td>
<td><span data-ttu-id="27da8-455">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-455">10001</span></span></td>
<td><span data-ttu-id="27da8-456">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-456">Electricity</span></span></td>
<td><span data-ttu-id="27da8-457">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-457">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="27da8-458">-10.00</span></span></td>
<td><span data-ttu-id="27da8-459">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="27da8-460">Proj 2</span></span></td>
<td><span data-ttu-id="27da8-461">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="27da8-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="27da8-462">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-462">10001</span></span></td>
<td><span data-ttu-id="27da8-463">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-463">Electricity</span></span></td>
<td><span data-ttu-id="27da8-464">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-464">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-465">10,00</span><span class="sxs-lookup"><span data-stu-id="27da8-465">10.00</span></span></td>
<td><span data-ttu-id="27da8-466">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-467">Aby uzyskać szczegółowe informacje o zasadach stawek kosztów ogólnych, zobacz tematy Zasada stawki kosztu ogólnego i Podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="27da8-468">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="27da8-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="27da8-469">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="27da8-470">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="27da8-471">Program Finance and Operations obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="27da8-472">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="27da8-473">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="27da8-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="27da8-474">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="27da8-475">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="27da8-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="27da8-476">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-476">The allocation order is controlled by the cost control unit.</span></span> <span data-ttu-id="27da8-477">[![Metoda wzajemna](./media/reciprocal-method.png)]</span><span class="sxs-lookup"><span data-stu-id="27da8-477">[![Reciprocal method](./media/reciprocal-method.png)]</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="27da8-478">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-478">Define the cost allocation</span></span>

<span data-ttu-id="27da8-479">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="27da8-480">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="27da8-481">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="27da8-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-482">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-482">Cost object</span></span></th>
<th><span data-ttu-id="27da8-483">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="27da8-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-484">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-484">CC002</span></span></td>
<td><span data-ttu-id="27da8-485">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-485">Finance</span></span></td>
<td><span data-ttu-id="27da8-486">35</span><span class="sxs-lookup"><span data-stu-id="27da8-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-487">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-487">CC003</span></span></td>
<td><span data-ttu-id="27da8-488">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-488">Assembly</span></span></td>
<td><span data-ttu-id="27da8-489">55</span><span class="sxs-lookup"><span data-stu-id="27da8-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-490">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-490">CC004</span></span></td>
<td><span data-ttu-id="27da8-491">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-491">Packaging</span></span></td>
<td><span data-ttu-id="27da8-492">10</span><span class="sxs-lookup"><span data-stu-id="27da8-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-493">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="27da8-494">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="27da8-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-495">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-495">Cost object</span></span></th>
<th><span data-ttu-id="27da8-496">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="27da8-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-497">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-497">CC003</span></span></td>
<td><span data-ttu-id="27da8-498">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-498">Assembly</span></span></td>
<td><span data-ttu-id="27da8-499">65</span><span class="sxs-lookup"><span data-stu-id="27da8-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-500">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-500">CC004</span></span></td>
<td><span data-ttu-id="27da8-501">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-501">Packaging</span></span></td>
<td><span data-ttu-id="27da8-502">35</span><span class="sxs-lookup"><span data-stu-id="27da8-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-503">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="27da8-504">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="27da8-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-505">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-505">Cost object</span></span></th>
<th><span data-ttu-id="27da8-506">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="27da8-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-507">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-508">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-508">Product 1</span></span></td>
<td><span data-ttu-id="27da8-509">60</span><span class="sxs-lookup"><span data-stu-id="27da8-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-510">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-511">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-511">Product 2</span></span></td>
<td><span data-ttu-id="27da8-512">20</span><span class="sxs-lookup"><span data-stu-id="27da8-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-513">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="27da8-514">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="27da8-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-515">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-515">Cost object</span></span></th>
<th><span data-ttu-id="27da8-516">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="27da8-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-517">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-518">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-518">Product 1</span></span></td>
<td><span data-ttu-id="27da8-519">80</span><span class="sxs-lookup"><span data-stu-id="27da8-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-520">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-521">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-521">Product 2</span></span></td>
<td><span data-ttu-id="27da8-522">15</span><span class="sxs-lookup"><span data-stu-id="27da8-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-523">**Uwaga:** W programie Finance and Operations miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="27da8-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="27da8-524">Aby uzyskać bardziej szczegółowe informacje o dostawcach miar statystycznych, zobacz temat Szablon dostawcy miar statystycznych</span><span class="sxs-lookup"><span data-stu-id="27da8-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="27da8-525">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy). W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="27da8-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-526">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-526">Cost object</span></span></th>
<th><span data-ttu-id="27da8-527">Wartość</span><span class="sxs-lookup"><span data-stu-id="27da8-527">Magnitude</span></span></th>
<th><span data-ttu-id="27da8-528">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="27da8-528">Allocation factor</span></span></th>
<th><span data-ttu-id="27da8-529">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-529">Amount</span></span></th>
<th><span data-ttu-id="27da8-530">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-531">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-531">CC002</span></span></td>
<td><span data-ttu-id="27da8-532">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-532">Finance</span></span></td>
<td><span data-ttu-id="27da8-533">35</span><span class="sxs-lookup"><span data-stu-id="27da8-533">35</span></span></td>
<td><span data-ttu-id="27da8-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="27da8-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="27da8-535">175.00</span><span class="sxs-lookup"><span data-stu-id="27da8-535">175.00</span></span></td>
<td><span data-ttu-id="27da8-536">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-537">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-537">CC003</span></span></td>
<td><span data-ttu-id="27da8-538">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-538">Assembly</span></span></td>
<td><span data-ttu-id="27da8-539">55</span><span class="sxs-lookup"><span data-stu-id="27da8-539">55</span></span></td>
<td><span data-ttu-id="27da8-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="27da8-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="27da8-541">275.00</span><span class="sxs-lookup"><span data-stu-id="27da8-541">275.00</span></span></td>
<td><span data-ttu-id="27da8-542">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-543">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-543">CC004</span></span></td>
<td><span data-ttu-id="27da8-544">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-544">Packaging</span></span></td>
<td><span data-ttu-id="27da8-545">10</span><span class="sxs-lookup"><span data-stu-id="27da8-545">10</span></span></td>
<td><span data-ttu-id="27da8-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="27da8-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="27da8-547">50,00</span><span class="sxs-lookup"><span data-stu-id="27da8-547">50.00</span></span></td>
<td><span data-ttu-id="27da8-548">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-549">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-549">CC002</span></span></td>
<td><span data-ttu-id="27da8-550">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-550">Finance</span></span></td>
<td><span data-ttu-id="27da8-551">35</span><span class="sxs-lookup"><span data-stu-id="27da8-551">35</span></span></td>
<td><span data-ttu-id="27da8-552">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="27da8-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="27da8-553">436.00</span><span class="sxs-lookup"><span data-stu-id="27da8-553">436.00</span></span></td>
<td><span data-ttu-id="27da8-554">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-555">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-555">CC003</span></span></td>
<td><span data-ttu-id="27da8-556">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-556">Assembly</span></span></td>
<td><span data-ttu-id="27da8-557">55</span><span class="sxs-lookup"><span data-stu-id="27da8-557">55</span></span></td>
<td><span data-ttu-id="27da8-558">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="27da8-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="27da8-559">685.14</span><span class="sxs-lookup"><span data-stu-id="27da8-559">685.14</span></span></td>
<td><span data-ttu-id="27da8-560">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-561">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-561">CC004</span></span></td>
<td><span data-ttu-id="27da8-562">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-562">Packaging</span></span></td>
<td><span data-ttu-id="27da8-563">10</span><span class="sxs-lookup"><span data-stu-id="27da8-563">10</span></span></td>
<td><span data-ttu-id="27da8-564">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="27da8-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="27da8-565">124.57</span><span class="sxs-lookup"><span data-stu-id="27da8-565">124.57</span></span></td>
<td><span data-ttu-id="27da8-566">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-567">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="27da8-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-568">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-568">Cost object</span></span></th>
<th><span data-ttu-id="27da8-569">Wartość</span><span class="sxs-lookup"><span data-stu-id="27da8-569">Magnitude</span></span></th>
<th><span data-ttu-id="27da8-570">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="27da8-570">Allocation factor</span></span></th>
<th><span data-ttu-id="27da8-571">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-571">Amount</span></span></th>
<th><span data-ttu-id="27da8-572">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-573">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-573">CC003</span></span></td>
<td><span data-ttu-id="27da8-574">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-574">Assembly</span></span></td>
<td><span data-ttu-id="27da8-575">65</span><span class="sxs-lookup"><span data-stu-id="27da8-575">65</span></span></td>
<td><span data-ttu-id="27da8-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="27da8-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="27da8-577">438.75</span><span class="sxs-lookup"><span data-stu-id="27da8-577">438.75</span></span></td>
<td><span data-ttu-id="27da8-578">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-579">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-579">CC004</span></span></td>
<td><span data-ttu-id="27da8-580">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-580">Packaging</span></span></td>
<td><span data-ttu-id="27da8-581">35</span><span class="sxs-lookup"><span data-stu-id="27da8-581">35</span></span></td>
<td><span data-ttu-id="27da8-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="27da8-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="27da8-583">236.25</span><span class="sxs-lookup"><span data-stu-id="27da8-583">236.25</span></span></td>
<td><span data-ttu-id="27da8-584">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-585">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-585">CC003</span></span></td>
<td><span data-ttu-id="27da8-586">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-586">Assembly</span></span></td>
<td><span data-ttu-id="27da8-587">65</span><span class="sxs-lookup"><span data-stu-id="27da8-587">65</span></span></td>
<td><span data-ttu-id="27da8-588">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="27da8-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="27da8-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="27da8-589">5,297.69</span></span></td>
<td><span data-ttu-id="27da8-590">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-591">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-591">CC004</span></span></td>
<td><span data-ttu-id="27da8-592">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-592">Packaging</span></span></td>
<td><span data-ttu-id="27da8-593">35</span><span class="sxs-lookup"><span data-stu-id="27da8-593">35</span></span></td>
<td><span data-ttu-id="27da8-594">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="27da8-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="27da8-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="27da8-595">2,852.60</span></span></td>
<td><span data-ttu-id="27da8-596">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-597">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="27da8-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-598">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-598">Cost object</span></span></th>
<th><span data-ttu-id="27da8-599">Wartość</span><span class="sxs-lookup"><span data-stu-id="27da8-599">Magnitude</span></span></th>
<th><span data-ttu-id="27da8-600">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="27da8-600">Allocation factor</span></span></th>
<th><span data-ttu-id="27da8-601">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-601">Amount</span></span></th>
<th><span data-ttu-id="27da8-602">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-603">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-604">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-604">Product 1</span></span></td>
<td><span data-ttu-id="27da8-605">60</span><span class="sxs-lookup"><span data-stu-id="27da8-605">60</span></span></td>
<td><span data-ttu-id="27da8-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="27da8-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="27da8-607">535.31</span><span class="sxs-lookup"><span data-stu-id="27da8-607">535.31</span></span></td>
<td><span data-ttu-id="27da8-608">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-609">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-610">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-610">Product 2</span></span></td>
<td><span data-ttu-id="27da8-611">20</span><span class="sxs-lookup"><span data-stu-id="27da8-611">20</span></span></td>
<td><span data-ttu-id="27da8-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="27da8-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="27da8-613">178.44</span><span class="sxs-lookup"><span data-stu-id="27da8-613">178.44</span></span></td>
<td><span data-ttu-id="27da8-614">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-615">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-616">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-616">Product 1</span></span></td>
<td><span data-ttu-id="27da8-617">60</span><span class="sxs-lookup"><span data-stu-id="27da8-617">60</span></span></td>
<td><span data-ttu-id="27da8-618">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="27da8-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="27da8-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="27da8-619">4,487.12</span></span></td>
<td><span data-ttu-id="27da8-620">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-621">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-622">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-622">Product 2</span></span></td>
<td><span data-ttu-id="27da8-623">20</span><span class="sxs-lookup"><span data-stu-id="27da8-623">20</span></span></td>
<td><span data-ttu-id="27da8-624">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="27da8-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="27da8-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="27da8-625">1,495.71</span></span></td>
<td><span data-ttu-id="27da8-626">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="27da8-627">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="27da8-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-628">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-628">Cost object</span></span></th>
<th><span data-ttu-id="27da8-629">Wartość</span><span class="sxs-lookup"><span data-stu-id="27da8-629">Magnitude</span></span></th>
<th><span data-ttu-id="27da8-630">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="27da8-630">Allocation factor</span></span></th>
<th><span data-ttu-id="27da8-631">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-631">Amount</span></span></th>
<th><span data-ttu-id="27da8-632">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-633">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-634">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-634">Product 1</span></span></td>
<td><span data-ttu-id="27da8-635">80</span><span class="sxs-lookup"><span data-stu-id="27da8-635">80</span></span></td>
<td><span data-ttu-id="27da8-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="27da8-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="27da8-637">241.05</span><span class="sxs-lookup"><span data-stu-id="27da8-637">241.05</span></span></td>
<td><span data-ttu-id="27da8-638">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-639">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-640">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-640">Product 2</span></span></td>
<td><span data-ttu-id="27da8-641">15</span><span class="sxs-lookup"><span data-stu-id="27da8-641">15</span></span></td>
<td><span data-ttu-id="27da8-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="27da8-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="27da8-643">45.20</span><span class="sxs-lookup"><span data-stu-id="27da8-643">45.20</span></span></td>
<td><span data-ttu-id="27da8-644">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-645">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-646">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-646">Product 1</span></span></td>
<td><span data-ttu-id="27da8-647">80</span><span class="sxs-lookup"><span data-stu-id="27da8-647">80</span></span></td>
<td><span data-ttu-id="27da8-648">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="27da8-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="27da8-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="27da8-649">2,507.09</span></span></td>
<td><span data-ttu-id="27da8-650">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-651">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-652">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-652">Product 2</span></span></td>
<td><span data-ttu-id="27da8-653">15</span><span class="sxs-lookup"><span data-stu-id="27da8-653">15</span></span></td>
<td><span data-ttu-id="27da8-654">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="27da8-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="27da8-655">470.08</span><span class="sxs-lookup"><span data-stu-id="27da8-655">470.08</span></span></td>
<td><span data-ttu-id="27da8-656">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="27da8-657">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="27da8-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="27da8-658">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="27da8-658">Journal</span></span></th>
<th><span data-ttu-id="27da8-659">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="27da8-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="27da8-660">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="27da8-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="27da8-661">Wersja</span><span class="sxs-lookup"><span data-stu-id="27da8-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-662">00004</span><span class="sxs-lookup"><span data-stu-id="27da8-662">00004</span></span></td>
<td><span data-ttu-id="27da8-663">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="27da8-664">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="27da8-664">Fiscal</span></span></td>
<td><span data-ttu-id="27da8-665">2017</span><span class="sxs-lookup"><span data-stu-id="27da8-665">2017</span></span></td>
<td><span data-ttu-id="27da8-666">Okres 1</span><span class="sxs-lookup"><span data-stu-id="27da8-666">Period 1</span></span></td>
<td><span data-ttu-id="27da8-667">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="27da8-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="27da8-668">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="27da8-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="27da8-669">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="27da8-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-670">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-671">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-671">Cost element</span></span></th>
<th><span data-ttu-id="27da8-672">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-672">Cost behavior</span></span></th>
<th><span data-ttu-id="27da8-673">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-674">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-675">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-675">CC001</span></span></td>
<td><span data-ttu-id="27da8-676">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-676">HR</span></span></td>
<td><span data-ttu-id="27da8-677">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-677">10001</span></span></td>
<td><span data-ttu-id="27da8-678">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-678">Electricity</span></span></td>
<td><span data-ttu-id="27da8-679">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-679">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-680">500.00</span><span class="sxs-lookup"><span data-stu-id="27da8-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-681">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-682">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-682">CC001</span></span></td>
<td><span data-ttu-id="27da8-683">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-683">HR</span></span></td>
<td><span data-ttu-id="27da8-684">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-684">10001</span></span></td>
<td><span data-ttu-id="27da8-685">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-685">Electricity</span></span></td>
<td><span data-ttu-id="27da8-686">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-686">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="27da8-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-688">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-689">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-689">CC002</span></span></td>
<td><span data-ttu-id="27da8-690">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-690">Finance</span></span></td>
<td><span data-ttu-id="27da8-691">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-691">10001</span></span></td>
<td><span data-ttu-id="27da8-692">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-692">Electricity</span></span></td>
<td><span data-ttu-id="27da8-693">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-693">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-694">675.00</span><span class="sxs-lookup"><span data-stu-id="27da8-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-695">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-696">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-696">CC002</span></span></td>
<td><span data-ttu-id="27da8-697">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-697">Finance</span></span></td>
<td><span data-ttu-id="27da8-698">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-698">10001</span></span></td>
<td><span data-ttu-id="27da8-699">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-699">Electricity</span></span></td>
<td><span data-ttu-id="27da8-700">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-700">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="27da8-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-702">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-703">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-703">CC003</span></span></td>
<td><span data-ttu-id="27da8-704">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-704">Assembly</span></span></td>
<td><span data-ttu-id="27da8-705">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-705">10001</span></span></td>
<td><span data-ttu-id="27da8-706">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-706">Electricity</span></span></td>
<td><span data-ttu-id="27da8-707">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-707">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-708">713.75</span><span class="sxs-lookup"><span data-stu-id="27da8-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-709">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-710">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-710">CC003</span></span></td>
<td><span data-ttu-id="27da8-711">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-711">Assembly</span></span></td>
<td><span data-ttu-id="27da8-712">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-712">10001</span></span></td>
<td><span data-ttu-id="27da8-713">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-713">Electricity</span></span></td>
<td><span data-ttu-id="27da8-714">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-714">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="27da8-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-716">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-717">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-717">CC003</span></span></td>
<td><span data-ttu-id="27da8-718">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-718">Packaging</span></span></td>
<td><span data-ttu-id="27da8-719">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-719">10001</span></span></td>
<td><span data-ttu-id="27da8-720">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-720">Electricity</span></span></td>
<td><span data-ttu-id="27da8-721">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-721">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-722">286.25</span><span class="sxs-lookup"><span data-stu-id="27da8-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-723">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-724">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-724">CC003</span></span></td>
<td><span data-ttu-id="27da8-725">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-725">Packaging</span></span></td>
<td><span data-ttu-id="27da8-726">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-726">10001</span></span></td>
<td><span data-ttu-id="27da8-727">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-727">Electricity</span></span></td>
<td><span data-ttu-id="27da8-728">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-728">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="27da8-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-730">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-731">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-732">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-732">Product 1</span></span></td>
<td><span data-ttu-id="27da8-733">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-733">10001</span></span></td>
<td><span data-ttu-id="27da8-734">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-734">Electricity</span></span></td>
<td><span data-ttu-id="27da8-735">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-735">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-736">776.36</span><span class="sxs-lookup"><span data-stu-id="27da8-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-737">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-738">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-739">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-739">Product 1</span></span></td>
<td><span data-ttu-id="27da8-740">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-740">10001</span></span></td>
<td><span data-ttu-id="27da8-741">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-741">Electricity</span></span></td>
<td><span data-ttu-id="27da8-742">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-742">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="27da8-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-744">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-745">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-746">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-746">Product 1</span></span></td>
<td><span data-ttu-id="27da8-747">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-747">10001</span></span></td>
<td><span data-ttu-id="27da8-748">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-748">Electricity</span></span></td>
<td><span data-ttu-id="27da8-749">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-749">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-750">223.64</span><span class="sxs-lookup"><span data-stu-id="27da8-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-751">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="27da8-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-752">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-753">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-753">Product 1</span></span></td>
<td><span data-ttu-id="27da8-754">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-754">10001</span></span></td>
<td><span data-ttu-id="27da8-755">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-755">Electricity</span></span></td>
<td><span data-ttu-id="27da8-756">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-756">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="27da8-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="27da8-758">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="27da8-759">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="27da8-760">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-760">Cost element</span></span></th>
<th><span data-ttu-id="27da8-761">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-761">Cost behavior</span></span></th>
<th><span data-ttu-id="27da8-762">Ilość</span><span class="sxs-lookup"><span data-stu-id="27da8-762">Amount</span></span></th>
<th><span data-ttu-id="27da8-763">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="27da8-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="27da8-764">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-764">CC001</span></span></td>
<td><span data-ttu-id="27da8-765">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-765">HR</span></span></td>
<td><span data-ttu-id="27da8-766">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-766">10001</span></span></td>
<td><span data-ttu-id="27da8-767">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-767">Electricity</span></span></td>
<td><span data-ttu-id="27da8-768">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-768">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="27da8-769">-500.00</span></span></td>
<td><span data-ttu-id="27da8-770">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-771">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-771">CC002</span></span></td>
<td><span data-ttu-id="27da8-772">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-772">Finance</span></span></td>
<td><span data-ttu-id="27da8-773">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-773">10001</span></span></td>
<td><span data-ttu-id="27da8-774">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-774">Electricity</span></span></td>
<td><span data-ttu-id="27da8-775">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-775">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-776">175.00</span><span class="sxs-lookup"><span data-stu-id="27da8-776">175.00</span></span></td>
<td><span data-ttu-id="27da8-777">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-778">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-778">CC003</span></span></td>
<td><span data-ttu-id="27da8-779">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-779">Assembly</span></span></td>
<td><span data-ttu-id="27da8-780">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-780">10001</span></span></td>
<td><span data-ttu-id="27da8-781">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-781">Electricity</span></span></td>
<td><span data-ttu-id="27da8-782">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-782">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-783">275.00</span><span class="sxs-lookup"><span data-stu-id="27da8-783">275.00</span></span></td>
<td><span data-ttu-id="27da8-784">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-785">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-785">CC004</span></span></td>
<td><span data-ttu-id="27da8-786">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-786">Packaging</span></span></td>
<td><span data-ttu-id="27da8-787">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-787">10001</span></span></td>
<td><span data-ttu-id="27da8-788">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-788">Electricity</span></span></td>
<td><span data-ttu-id="27da8-789">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-789">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-790">50,00</span><span class="sxs-lookup"><span data-stu-id="27da8-790">50,00</span></span></td>
<td><span data-ttu-id="27da8-791">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-792">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-792">CC001</span></span></td>
<td><span data-ttu-id="27da8-793">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="27da8-793">HR</span></span></td>
<td><span data-ttu-id="27da8-794">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-794">10001</span></span></td>
<td><span data-ttu-id="27da8-795">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-795">Electricity</span></span></td>
<td><span data-ttu-id="27da8-796">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-796">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-797">-1245,71</span><span class="sxs-lookup"><span data-stu-id="27da8-797">-1,245.71</span></span></td>
<td><span data-ttu-id="27da8-798">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-799">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-799">CC002</span></span></td>
<td><span data-ttu-id="27da8-800">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-800">Finance</span></span></td>
<td><span data-ttu-id="27da8-801">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-801">10001</span></span></td>
<td><span data-ttu-id="27da8-802">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-802">Electricity</span></span></td>
<td><span data-ttu-id="27da8-803">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-803">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-804">436.00</span><span class="sxs-lookup"><span data-stu-id="27da8-804">436.00</span></span></td>
<td><span data-ttu-id="27da8-805">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-806">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-806">CC003</span></span></td>
<td><span data-ttu-id="27da8-807">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-807">Assembly</span></span></td>
<td><span data-ttu-id="27da8-808">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-808">10001</span></span></td>
<td><span data-ttu-id="27da8-809">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-809">Electricity</span></span></td>
<td><span data-ttu-id="27da8-810">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-810">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-811">685.14</span><span class="sxs-lookup"><span data-stu-id="27da8-811">685.14</span></span></td>
<td><span data-ttu-id="27da8-812">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-813">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-813">CC004</span></span></td>
<td><span data-ttu-id="27da8-814">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-814">Packaging</span></span></td>
<td><span data-ttu-id="27da8-815">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-815">10001</span></span></td>
<td><span data-ttu-id="27da8-816">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-816">Electricity</span></span></td>
<td><span data-ttu-id="27da8-817">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-817">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-818">124.57</span><span class="sxs-lookup"><span data-stu-id="27da8-818">124.57</span></span></td>
<td><span data-ttu-id="27da8-819">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-820">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-820">CC002</span></span></td>
<td><span data-ttu-id="27da8-821">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-821">Finance</span></span></td>
<td><span data-ttu-id="27da8-822">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-822">10001</span></span></td>
<td><span data-ttu-id="27da8-823">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-823">Electricity</span></span></td>
<td><span data-ttu-id="27da8-824">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-824">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="27da8-825">-675.00</span></span></td>
<td><span data-ttu-id="27da8-826">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-827">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-827">CC003</span></span></td>
<td><span data-ttu-id="27da8-828">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-828">Assembly</span></span></td>
<td><span data-ttu-id="27da8-829">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-829">10001</span></span></td>
<td><span data-ttu-id="27da8-830">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-830">Electricity</span></span></td>
<td><span data-ttu-id="27da8-831">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-831">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-832">438.75</span><span class="sxs-lookup"><span data-stu-id="27da8-832">438.75</span></span></td>
<td><span data-ttu-id="27da8-833">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-834">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-834">CC004</span></span></td>
<td><span data-ttu-id="27da8-835">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-835">Packaging</span></span></td>
<td><span data-ttu-id="27da8-836">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-836">10001</span></span></td>
<td><span data-ttu-id="27da8-837">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-837">Electricity</span></span></td>
<td><span data-ttu-id="27da8-838">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-838">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-839">236.25</span><span class="sxs-lookup"><span data-stu-id="27da8-839">236.25</span></span></td>
<td><span data-ttu-id="27da8-840">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-841">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-841">CC002</span></span></td>
<td><span data-ttu-id="27da8-842">Finanse</span><span class="sxs-lookup"><span data-stu-id="27da8-842">Finance</span></span></td>
<td><span data-ttu-id="27da8-843">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-843">10001</span></span></td>
<td><span data-ttu-id="27da8-844">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-844">Electricity</span></span></td>
<td><span data-ttu-id="27da8-845">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-845">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-846">-8150,29</span><span class="sxs-lookup"><span data-stu-id="27da8-846">-8,150.29</span></span></td>
<td><span data-ttu-id="27da8-847">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-848">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-848">CC003</span></span></td>
<td><span data-ttu-id="27da8-849">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-849">Assembly</span></span></td>
<td><span data-ttu-id="27da8-850">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-850">10001</span></span></td>
<td><span data-ttu-id="27da8-851">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-851">Electricity</span></span></td>
<td><span data-ttu-id="27da8-852">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-852">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="27da8-853">5,297.69</span></span></td>
<td><span data-ttu-id="27da8-854">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-855">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-855">CC004</span></span></td>
<td><span data-ttu-id="27da8-856">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="27da8-856">Packaging</span></span></td>
<td><span data-ttu-id="27da8-857">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-857">10001</span></span></td>
<td><span data-ttu-id="27da8-858">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-858">Electricity</span></span></td>
<td><span data-ttu-id="27da8-859">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-859">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="27da8-860">2,852.60</span></span></td>
<td><span data-ttu-id="27da8-861">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-862">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-862">CC003</span></span></td>
<td><span data-ttu-id="27da8-863">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-863">Assembly</span></span></td>
<td><span data-ttu-id="27da8-864">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-864">10001</span></span></td>
<td><span data-ttu-id="27da8-865">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-865">Electricity</span></span></td>
<td><span data-ttu-id="27da8-866">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-866">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="27da8-867">-713.75</span></span></td>
<td><span data-ttu-id="27da8-868">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-869">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-870">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-870">Product 1</span></span></td>
<td><span data-ttu-id="27da8-871">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-871">10001</span></span></td>
<td><span data-ttu-id="27da8-872">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-872">Electricity</span></span></td>
<td><span data-ttu-id="27da8-873">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-873">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-874">535.31</span><span class="sxs-lookup"><span data-stu-id="27da8-874">535.31</span></span></td>
<td><span data-ttu-id="27da8-875">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-876">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-877">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-877">Product 2</span></span></td>
<td><span data-ttu-id="27da8-878">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-878">10001</span></span></td>
<td><span data-ttu-id="27da8-879">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-879">Electricity</span></span></td>
<td><span data-ttu-id="27da8-880">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-880">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-881">178.44</span><span class="sxs-lookup"><span data-stu-id="27da8-881">178.44</span></span></td>
<td><span data-ttu-id="27da8-882">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-883">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-883">CC003</span></span></td>
<td><span data-ttu-id="27da8-884">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-884">Assembly</span></span></td>
<td><span data-ttu-id="27da8-885">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-885">10001</span></span></td>
<td><span data-ttu-id="27da8-886">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-886">Electricity</span></span></td>
<td><span data-ttu-id="27da8-887">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-887">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-888">-5982,83</span><span class="sxs-lookup"><span data-stu-id="27da8-888">-5,982.83</span></span></td>
<td><span data-ttu-id="27da8-889">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-890">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-891">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-891">Product 1</span></span></td>
<td><span data-ttu-id="27da8-892">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-892">10001</span></span></td>
<td><span data-ttu-id="27da8-893">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-893">Electricity</span></span></td>
<td><span data-ttu-id="27da8-894">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-894">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="27da8-895">4,487.12</span></span></td>
<td><span data-ttu-id="27da8-896">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-897">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-898">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-898">Product 2</span></span></td>
<td><span data-ttu-id="27da8-899">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-899">10001</span></span></td>
<td><span data-ttu-id="27da8-900">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-900">Electricity</span></span></td>
<td><span data-ttu-id="27da8-901">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-901">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="27da8-902">1,495.71</span></span></td>
<td><span data-ttu-id="27da8-903">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-904">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-904">CC003</span></span></td>
<td><span data-ttu-id="27da8-905">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-905">Assembly</span></span></td>
<td><span data-ttu-id="27da8-906">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-906">10001</span></span></td>
<td><span data-ttu-id="27da8-907">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-907">Electricity</span></span></td>
<td><span data-ttu-id="27da8-908">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-908">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="27da8-909">-286.25</span></span></td>
<td><span data-ttu-id="27da8-910">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-911">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-912">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-912">Product 1</span></span></td>
<td><span data-ttu-id="27da8-913">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-913">10001</span></span></td>
<td><span data-ttu-id="27da8-914">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-914">Electricity</span></span></td>
<td><span data-ttu-id="27da8-915">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-915">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-916">241.05</span><span class="sxs-lookup"><span data-stu-id="27da8-916">241.05</span></span></td>
<td><span data-ttu-id="27da8-917">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-918">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-919">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-919">Product 2</span></span></td>
<td><span data-ttu-id="27da8-920">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-920">10001</span></span></td>
<td><span data-ttu-id="27da8-921">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-921">Electricity</span></span></td>
<td><span data-ttu-id="27da8-922">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-922">Fixed cost</span></span></td>
<td><span data-ttu-id="27da8-923">45.20</span><span class="sxs-lookup"><span data-stu-id="27da8-923">45.20</span></span></td>
<td><span data-ttu-id="27da8-924">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-925">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-925">CC003</span></span></td>
<td><span data-ttu-id="27da8-926">Zestaw</span><span class="sxs-lookup"><span data-stu-id="27da8-926">Assembly</span></span></td>
<td><span data-ttu-id="27da8-927">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-927">10001</span></span></td>
<td><span data-ttu-id="27da8-928">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-928">Electricity</span></span></td>
<td><span data-ttu-id="27da8-929">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-929">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-930">-2977,17</span><span class="sxs-lookup"><span data-stu-id="27da8-930">-2,977.17</span></span></td>
<td><span data-ttu-id="27da8-931">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-932">Prod 1</span></span></td>
<td><span data-ttu-id="27da8-933">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="27da8-933">Product 1</span></span></td>
<td><span data-ttu-id="27da8-934">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-934">10001</span></span></td>
<td><span data-ttu-id="27da8-935">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-935">Electricity</span></span></td>
<td><span data-ttu-id="27da8-936">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-936">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="27da8-937">2,507.09</span></span></td>
<td><span data-ttu-id="27da8-938">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="27da8-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-939">Prod 2</span></span></td>
<td><span data-ttu-id="27da8-940">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="27da8-940">Product 2</span></span></td>
<td><span data-ttu-id="27da8-941">10001</span><span class="sxs-lookup"><span data-stu-id="27da8-941">10001</span></span></td>
<td><span data-ttu-id="27da8-942">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="27da8-942">Electricity</span></span></td>
<td><span data-ttu-id="27da8-943">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-943">Variable cost</span></span></td>
<td><span data-ttu-id="27da8-944">470.08</span><span class="sxs-lookup"><span data-stu-id="27da8-944">470.08</span></span></td>
<td><span data-ttu-id="27da8-945">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="27da8-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="27da8-946">Wniosek</span><span class="sxs-lookup"><span data-stu-id="27da8-946">Conclusion</span></span>
<span data-ttu-id="27da8-947">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="27da8-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="27da8-948">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="27da8-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="27da8-949">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="27da8-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="27da8-950">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="27da8-951">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="27da8-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="27da8-952">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="27da8-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="27da8-953">Razem</span><span class="sxs-lookup"><span data-stu-id="27da8-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="27da8-954">CC099</span><span class="sxs-lookup"><span data-stu-id="27da8-954">CC099</span></span></th>
<th><span data-ttu-id="27da8-955">CC001</span><span class="sxs-lookup"><span data-stu-id="27da8-955">CC001</span></span></th>
<th><span data-ttu-id="27da8-956">CC002</span><span class="sxs-lookup"><span data-stu-id="27da8-956">CC002</span></span></th>
<th><span data-ttu-id="27da8-957">CC003</span><span class="sxs-lookup"><span data-stu-id="27da8-957">CC003</span></span></th>
<th><span data-ttu-id="27da8-958">CC004</span><span class="sxs-lookup"><span data-stu-id="27da8-958">CC004</span></span></th>
<th><span data-ttu-id="27da8-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="27da8-959">Proj 1</span></span></th>
<th><span data-ttu-id="27da8-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="27da8-960">Proj 2</span></span></th>
<th><span data-ttu-id="27da8-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="27da8-961">Prod 1</span></span></th>
<th><span data-ttu-id="27da8-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="27da8-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="27da8-963">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="27da8-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-965"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-966"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-967"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="27da8-968"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-969"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-970"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-971"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-972"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="27da8-973">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="27da8-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-974">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-974">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="27da8-975">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="27da8-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-976">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-977">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-978">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-979">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-980">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="27da8-981">776.36</span><span class="sxs-lookup"><span data-stu-id="27da8-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-982">223.64</span><span class="sxs-lookup"><span data-stu-id="27da8-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-983"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="27da8-984">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="27da8-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-985">000</span><span class="sxs-lookup"><span data-stu-id="27da8-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-986">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-987">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-988">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-989">0,00</span><span class="sxs-lookup"><span data-stu-id="27da8-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-990">30.00</span><span class="sxs-lookup"><span data-stu-id="27da8-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-991">10,00</span><span class="sxs-lookup"><span data-stu-id="27da8-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="27da8-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="27da8-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="27da8-994"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="27da8-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="27da8-995">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="27da8-996">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="27da8-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="27da8-997">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="27da8-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="27da8-998">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="27da8-999">Aby uzyskać szczegółowe informacje, zobacz temat Zasada akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="27da8-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="27da8-1000">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="27da8-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




