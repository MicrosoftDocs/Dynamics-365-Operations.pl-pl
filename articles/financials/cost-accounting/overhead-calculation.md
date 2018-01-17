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
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 936e54c0ef1de449afda2392cd1fbb304eed631b
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="c55fd-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="c55fd-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c55fd-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="c55fd-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="c55fd-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="c55fd-105">Term definition</span></span>
---------------

<span data-ttu-id="c55fd-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="c55fd-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="c55fd-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="c55fd-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="c55fd-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="c55fd-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="c55fd-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="c55fd-109">Rent</span></span>
-   <span data-ttu-id="c55fd-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-110">Electricity</span></span>
-   <span data-ttu-id="c55fd-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="c55fd-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="c55fd-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="c55fd-112">Overhead calculation overview</span></span>
<span data-ttu-id="c55fd-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="c55fd-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="c55fd-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="c55fd-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="c55fd-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="c55fd-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="c55fd-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="c55fd-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="c55fd-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="c55fd-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="c55fd-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="c55fd-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="c55fd-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="c55fd-119">Version type</span></span>
-   <span data-ttu-id="c55fd-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="c55fd-120">Date and time</span></span>
-   <span data-ttu-id="c55fd-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="c55fd-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="c55fd-122">Fiscal year</span></span>
-   <span data-ttu-id="c55fd-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="c55fd-123">Fiscal period</span></span>

<span data-ttu-id="c55fd-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="c55fd-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="c55fd-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="c55fd-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="c55fd-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="c55fd-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="c55fd-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="c55fd-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="c55fd-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="c55fd-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="c55fd-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="c55fd-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="c55fd-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="c55fd-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="c55fd-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="c55fd-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="c55fd-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="c55fd-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="c55fd-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="c55fd-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="c55fd-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="c55fd-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c55fd-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c55fd-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="c55fd-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="c55fd-140">Main account</span></span></th>
<th><span data-ttu-id="c55fd-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="c55fd-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="c55fd-143">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-143">CC099</span></span></td>
<td><span data-ttu-id="c55fd-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-144">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-145">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-145">10001</span></span></td>
<td><span data-ttu-id="c55fd-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-146">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="c55fd-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="c55fd-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="c55fd-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="c55fd-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="c55fd-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-151">Define the cost behavior rule</span></span>

<span data-ttu-id="c55fd-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="c55fd-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="c55fd-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="c55fd-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="c55fd-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="c55fd-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="c55fd-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="c55fd-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="c55fd-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="c55fd-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="c55fd-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="c55fd-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c55fd-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="c55fd-160">Journal</span></span></th>
<th><span data-ttu-id="c55fd-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="c55fd-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c55fd-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="c55fd-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c55fd-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="c55fd-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-164">00001</span><span class="sxs-lookup"><span data-stu-id="c55fd-164">00001</span></span></td>
<td><span data-ttu-id="c55fd-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="c55fd-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="c55fd-166">Fiscal</span></span></td>
<td><span data-ttu-id="c55fd-167">2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-167">2017</span></span></td>
<td><span data-ttu-id="c55fd-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-168">Period 1</span></span></td>
<td><span data-ttu-id="c55fd-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c55fd-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="c55fd-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c55fd-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="c55fd-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-173">Cost element</span></span></th>
<th><span data-ttu-id="c55fd-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-174">Cost behavior</span></span></th>
<th><span data-ttu-id="c55fd-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="c55fd-177">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-177">CC099</span></span></td>
<td><span data-ttu-id="c55fd-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-178">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-179">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-179">10001</span></span></td>
<td><span data-ttu-id="c55fd-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-180">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="c55fd-181">Unclassified</span></span></td>
<td><span data-ttu-id="c55fd-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c55fd-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-185">Cost element</span></span></th>
<th><span data-ttu-id="c55fd-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-186">Cost behavior</span></span></th>
<th><span data-ttu-id="c55fd-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-187">Amount</span></span></th>
<th><span data-ttu-id="c55fd-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="c55fd-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-189">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-189">CC099</span></span></td>
<td><span data-ttu-id="c55fd-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-190">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-191">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-191">10001</span></span></td>
<td><span data-ttu-id="c55fd-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-192">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="c55fd-193">Unclassified</span></span></td>
<td><span data-ttu-id="c55fd-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-194">10,000.00</span></span></td>
<td><span data-ttu-id="c55fd-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-196">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-196">CC099</span></span></td>
<td><span data-ttu-id="c55fd-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-197">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-198">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-198">10001</span></span></td>
<td><span data-ttu-id="c55fd-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-199">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="c55fd-200">Unclassified</span></span></td>
<td><span data-ttu-id="c55fd-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-201">-10,000.00</span></span></td>
<td><span data-ttu-id="c55fd-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-203">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-203">CC099</span></span></td>
<td><span data-ttu-id="c55fd-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-204">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-205">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-205">10001</span></span></td>
<td><span data-ttu-id="c55fd-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-206">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-207">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-208">1,000.00</span></span></td>
<td><span data-ttu-id="c55fd-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-210">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-210">CC099</span></span></td>
<td><span data-ttu-id="c55fd-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-211">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-212">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-212">10001</span></span></td>
<td><span data-ttu-id="c55fd-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-213">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-214">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-215">9,000.00</span></span></td>
<td><span data-ttu-id="c55fd-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-217">Aby uzyskać szczegółowe informacje o zachowaniu kosztów, zobacz temat Zasada zachowania kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="c55fd-218">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="c55fd-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="c55fd-219">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="c55fd-220">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="c55fd-221">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="c55fd-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="c55fd-222">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-222">Define the cost distribution rule</span></span>

<span data-ttu-id="c55fd-223">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="c55fd-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="c55fd-224">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="c55fd-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="c55fd-225">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="c55fd-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="c55fd-226">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="c55fd-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="c55fd-227">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="c55fd-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="c55fd-228">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-229">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-229">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-230">kWh</span><span class="sxs-lookup"><span data-stu-id="c55fd-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-231">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-231">CC001</span></span></td>
<td><span data-ttu-id="c55fd-232">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-232">HR</span></span></td>
<td><span data-ttu-id="c55fd-233">1 000</span><span class="sxs-lookup"><span data-stu-id="c55fd-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-234">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-234">CC002</span></span></td>
<td><span data-ttu-id="c55fd-235">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-235">Finance</span></span></td>
<td><span data-ttu-id="c55fd-236">6,000</span><span class="sxs-lookup"><span data-stu-id="c55fd-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-237">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-237">CC003</span></span></td>
<td><span data-ttu-id="c55fd-238">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-238">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-239">0</span><span class="sxs-lookup"><span data-stu-id="c55fd-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-240">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="c55fd-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-241">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-241">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-242">Wartość</span><span class="sxs-lookup"><span data-stu-id="c55fd-242">Magnitude</span></span></th>
<th><span data-ttu-id="c55fd-243">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="c55fd-243">Allocation factor</span></span></th>
<th><span data-ttu-id="c55fd-244">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-245">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-245">CC001</span></span></td>
<td><span data-ttu-id="c55fd-246">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-246">HR</span></span></td>
<td><span data-ttu-id="c55fd-247">1 000</span><span class="sxs-lookup"><span data-stu-id="c55fd-247">1,000</span></span></td>
<td><span data-ttu-id="c55fd-248">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c55fd-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c55fd-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-250">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-250">CC002</span></span></td>
<td><span data-ttu-id="c55fd-251">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-251">Finance</span></span></td>
<td><span data-ttu-id="c55fd-252">6,000</span><span class="sxs-lookup"><span data-stu-id="c55fd-252">6,000</span></span></td>
<td><span data-ttu-id="c55fd-253">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c55fd-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c55fd-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-255">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-255">CC003</span></span></td>
<td><span data-ttu-id="c55fd-256">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-256">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-257">0</span><span class="sxs-lookup"><span data-stu-id="c55fd-257">0</span></span></td>
<td><span data-ttu-id="c55fd-258">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c55fd-259">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-260">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="c55fd-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="c55fd-261">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="c55fd-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-262">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-262">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-263">Wzór</span><span class="sxs-lookup"><span data-stu-id="c55fd-263">Formula</span></span></th>
<th><span data-ttu-id="c55fd-264">Wartość</span><span class="sxs-lookup"><span data-stu-id="c55fd-264">Magnitude</span></span></th>
<th><span data-ttu-id="c55fd-265">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="c55fd-265">Allocation factor</span></span></th>
<th><span data-ttu-id="c55fd-266">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-267">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-267">CC001</span></span></td>
<td><span data-ttu-id="c55fd-268">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-268">HR</span></span></td>
<td><span data-ttu-id="c55fd-269">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c55fd-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c55fd-270">1</span><span class="sxs-lookup"><span data-stu-id="c55fd-270">1</span></span></td>
<td><span data-ttu-id="c55fd-271">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c55fd-272">500.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-273">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-273">CC002</span></span></td>
<td><span data-ttu-id="c55fd-274">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-274">Finance</span></span></td>
<td><span data-ttu-id="c55fd-275">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c55fd-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c55fd-276">1</span><span class="sxs-lookup"><span data-stu-id="c55fd-276">1</span></span></td>
<td><span data-ttu-id="c55fd-277">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c55fd-278">500.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-279">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-279">CC003</span></span></td>
<td><span data-ttu-id="c55fd-280">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-280">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c55fd-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c55fd-282">0</span><span class="sxs-lookup"><span data-stu-id="c55fd-282">0</span></span></td>
<td><span data-ttu-id="c55fd-283">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c55fd-284">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c55fd-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="c55fd-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c55fd-286">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="c55fd-286">Journal</span></span></th>
<th><span data-ttu-id="c55fd-287">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="c55fd-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c55fd-288">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="c55fd-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c55fd-289">Wersja</span><span class="sxs-lookup"><span data-stu-id="c55fd-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-290">00002</span><span class="sxs-lookup"><span data-stu-id="c55fd-290">00002</span></span></td>
<td><span data-ttu-id="c55fd-291">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="c55fd-292">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="c55fd-292">Fiscal</span></span></td>
<td><span data-ttu-id="c55fd-293">2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-293">2017</span></span></td>
<td><span data-ttu-id="c55fd-294">Okres 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-294">Period 1</span></span></td>
<td><span data-ttu-id="c55fd-295">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c55fd-296">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="c55fd-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c55fd-297">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="c55fd-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-298">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-299">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-299">Cost element</span></span></th>
<th><span data-ttu-id="c55fd-300">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-300">Cost behavior</span></span></th>
<th><span data-ttu-id="c55fd-301">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-302">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-303">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-303">CC099</span></span></td>
<td><span data-ttu-id="c55fd-304">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-304">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-305">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-305">10001</span></span></td>
<td><span data-ttu-id="c55fd-306">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-306">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-307">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-307">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-308">1000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-309">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-310">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-310">CC099</span></span></td>
<td><span data-ttu-id="c55fd-311">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-311">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-312">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-312">10001</span></span></td>
<td><span data-ttu-id="c55fd-313">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-313">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-314">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-314">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c55fd-316">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-317">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-318">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-318">Cost element</span></span></th>
<th><span data-ttu-id="c55fd-319">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-319">Cost behavior</span></span></th>
<th><span data-ttu-id="c55fd-320">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-320">Amount</span></span></th>
<th><span data-ttu-id="c55fd-321">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="c55fd-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-322">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-322">CC099</span></span></td>
<td><span data-ttu-id="c55fd-323">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-323">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-324">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-324">10001</span></span></td>
<td><span data-ttu-id="c55fd-325">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-325">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-326">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-326">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-327">-1000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-327">-1,000.00</span></span></td>
<td><span data-ttu-id="c55fd-328">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-329">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-329">CC001</span></span></td>
<td><span data-ttu-id="c55fd-330">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-330">HR</span></span></td>
<td><span data-ttu-id="c55fd-331">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-331">10001</span></span></td>
<td><span data-ttu-id="c55fd-332">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-332">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-333">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-333">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-334">500.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-334">500.00</span></span></td>
<td><span data-ttu-id="c55fd-335">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-336">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-336">CC002</span></span></td>
<td><span data-ttu-id="c55fd-337">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-337">Finance</span></span></td>
<td><span data-ttu-id="c55fd-338">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-338">10001</span></span></td>
<td><span data-ttu-id="c55fd-339">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-339">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-340">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-340">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-341">500.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-341">500.00</span></span></td>
<td><span data-ttu-id="c55fd-342">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-343">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-343">CC099</span></span></td>
<td><span data-ttu-id="c55fd-344">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-344">Default cost center</span></span></td>
<td><span data-ttu-id="c55fd-345">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-345">10001</span></span></td>
<td><span data-ttu-id="c55fd-346">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-346">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-347">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-347">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-348">-9000,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-348">-9,000.00</span></span></td>
<td><span data-ttu-id="c55fd-349">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-350">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-350">CC001</span></span></td>
<td><span data-ttu-id="c55fd-351">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-351">HR</span></span></td>
<td><span data-ttu-id="c55fd-352">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-352">10001</span></span></td>
<td><span data-ttu-id="c55fd-353">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-353">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-354">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-354">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c55fd-355">1,285.71</span></span></td>
<td><span data-ttu-id="c55fd-356">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-357">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-357">CC002</span></span></td>
<td><span data-ttu-id="c55fd-358">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-358">Finance</span></span></td>
<td><span data-ttu-id="c55fd-359">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-359">10001</span></span></td>
<td><span data-ttu-id="c55fd-360">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-360">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-361">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-361">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c55fd-362">7,714.29</span></span></td>
<td><span data-ttu-id="c55fd-363">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-364">Aby uzyskać szczegółowe informacje na temat dystrybucji kosztów i podstaw alokacji, zobacz tematy Zasada dystrybucji kosztów i Podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="c55fd-365">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="c55fd-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="c55fd-366">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="c55fd-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="c55fd-367">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="c55fd-368">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="c55fd-369">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="c55fd-369">Define the overhead rate</span></span>

<span data-ttu-id="c55fd-370">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="c55fd-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="c55fd-371">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="c55fd-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-372">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-372">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-373">Godziny</span><span class="sxs-lookup"><span data-stu-id="c55fd-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-374">Proj 1</span></span></td>
<td><span data-ttu-id="c55fd-375">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-375">Project 1</span></span></td>
<td><span data-ttu-id="c55fd-376">3</span><span class="sxs-lookup"><span data-stu-id="c55fd-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-377">Proj 2</span></span></td>
<td><span data-ttu-id="c55fd-378">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-378">Project 2</span></span></td>
<td><span data-ttu-id="c55fd-379">1</span><span class="sxs-lookup"><span data-stu-id="c55fd-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-380">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="c55fd-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-381">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-381">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-382">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-382">Cost element</span></span></th>
<th><span data-ttu-id="c55fd-383">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-383">Cost behavior</span></span></th>
<th><span data-ttu-id="c55fd-384">Jednostki</span><span class="sxs-lookup"><span data-stu-id="c55fd-384">Units</span></span></th>
<th><span data-ttu-id="c55fd-385">Kurs</span><span class="sxs-lookup"><span data-stu-id="c55fd-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-386">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-386">CC001</span></span></td>
<td><span data-ttu-id="c55fd-387">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-387">HR</span></span></td>
<td><span data-ttu-id="c55fd-388">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-388">10001</span></span></td>
<td><span data-ttu-id="c55fd-389">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-389">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-390">1</span><span class="sxs-lookup"><span data-stu-id="c55fd-390">1</span></span></td>
<td><span data-ttu-id="c55fd-391">10</span><span class="sxs-lookup"><span data-stu-id="c55fd-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-392">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-393">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-393">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-394">Wartość</span><span class="sxs-lookup"><span data-stu-id="c55fd-394">Magnitude</span></span></th>
<th><span data-ttu-id="c55fd-395">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-395">Cost element</span></span></th>
<th><span data-ttu-id="c55fd-396">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="c55fd-396">Allocation factor</span></span></th>
<th><span data-ttu-id="c55fd-397">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-398">Proj 1</span></span></td>
<td><span data-ttu-id="c55fd-399">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-399">Project 1</span></span></td>
<td><span data-ttu-id="c55fd-400">3</span><span class="sxs-lookup"><span data-stu-id="c55fd-400">3</span></span></td>
<td><span data-ttu-id="c55fd-401">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-401">10001</span></span></td>
<td><span data-ttu-id="c55fd-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c55fd-403">30.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-404">Proj 2</span></span></td>
<td><span data-ttu-id="c55fd-405">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-405">Project 2</span></span></td>
<td><span data-ttu-id="c55fd-406">1</span><span class="sxs-lookup"><span data-stu-id="c55fd-406">1</span></span></td>
<td><span data-ttu-id="c55fd-407">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-407">10001</span></span></td>
<td><span data-ttu-id="c55fd-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c55fd-409">10,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c55fd-410">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="c55fd-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c55fd-411">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="c55fd-411">Journal</span></span></th>
<th><span data-ttu-id="c55fd-412">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="c55fd-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c55fd-413">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="c55fd-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c55fd-414">Wersja</span><span class="sxs-lookup"><span data-stu-id="c55fd-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-415">00003</span><span class="sxs-lookup"><span data-stu-id="c55fd-415">00003</span></span></td>
<td><span data-ttu-id="c55fd-416">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="c55fd-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="c55fd-417">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="c55fd-417">Fiscal</span></span></td>
<td><span data-ttu-id="c55fd-418">2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-418">2017</span></span></td>
<td><span data-ttu-id="c55fd-419">Okres 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-419">Period 1</span></span></td>
<td><span data-ttu-id="c55fd-420">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="c55fd-421">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="c55fd-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c55fd-422">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="c55fd-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-423">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-423">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-424">Wartość</span><span class="sxs-lookup"><span data-stu-id="c55fd-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-425">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-426">Proj 1</span></span></td>
<td><span data-ttu-id="c55fd-427">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c55fd-428">3,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-429">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-430">Proj 2</span></span></td>
<td><span data-ttu-id="c55fd-431">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c55fd-432">1.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c55fd-433">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-434">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-435">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-435">Cost element</span></span></th>
<th><span data-ttu-id="c55fd-436">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-436">Cost behavior</span></span></th>
<th><span data-ttu-id="c55fd-437">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-437">Amount</span></span></th>
<th><span data-ttu-id="c55fd-438">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="c55fd-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="c55fd-439">CC0001</span></span></td>
<td><span data-ttu-id="c55fd-440">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-440">HR</span></span></td>
<td><span data-ttu-id="c55fd-441">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-441">10001</span></span></td>
<td><span data-ttu-id="c55fd-442">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-442">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-443">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-443">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-444">-30.00</span></span></td>
<td><span data-ttu-id="c55fd-445">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-446">Proj 1</span></span></td>
<td><span data-ttu-id="c55fd-447">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c55fd-448">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-448">10001</span></span></td>
<td><span data-ttu-id="c55fd-449">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-449">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-450">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-450">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-451">30.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-451">30.00</span></span></td>
<td><span data-ttu-id="c55fd-452">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-453">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-453">CC001</span></span></td>
<td><span data-ttu-id="c55fd-454">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-454">HR</span></span></td>
<td><span data-ttu-id="c55fd-455">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-455">10001</span></span></td>
<td><span data-ttu-id="c55fd-456">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-456">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-457">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-457">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-458">-10.00</span></span></td>
<td><span data-ttu-id="c55fd-459">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-460">Proj 2</span></span></td>
<td><span data-ttu-id="c55fd-461">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c55fd-462">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-462">10001</span></span></td>
<td><span data-ttu-id="c55fd-463">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-463">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-464">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-464">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-465">10,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-465">10.00</span></span></td>
<td><span data-ttu-id="c55fd-466">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-467">Aby uzyskać szczegółowe informacje o zasadach stawek kosztów ogólnych, zobacz tematy Zasada stawki kosztu ogólnego i Podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="c55fd-468">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="c55fd-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="c55fd-469">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="c55fd-470">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="c55fd-471">Program Finance and Operations obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="c55fd-472">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="c55fd-473">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="c55fd-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="c55fd-474">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="c55fd-475">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="c55fd-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="c55fd-476">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="c55fd-477">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="c55fd-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="c55fd-478">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-478">Define the cost allocation</span></span>

<span data-ttu-id="c55fd-479">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="c55fd-480">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="c55fd-481">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="c55fd-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-482">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-482">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-483">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="c55fd-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-484">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-484">CC002</span></span></td>
<td><span data-ttu-id="c55fd-485">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-485">Finance</span></span></td>
<td><span data-ttu-id="c55fd-486">35</span><span class="sxs-lookup"><span data-stu-id="c55fd-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-487">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-487">CC003</span></span></td>
<td><span data-ttu-id="c55fd-488">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-488">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-489">55</span><span class="sxs-lookup"><span data-stu-id="c55fd-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-490">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-490">CC004</span></span></td>
<td><span data-ttu-id="c55fd-491">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-491">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-492">10</span><span class="sxs-lookup"><span data-stu-id="c55fd-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-493">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="c55fd-494">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="c55fd-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-495">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-495">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-496">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="c55fd-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-497">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-497">CC003</span></span></td>
<td><span data-ttu-id="c55fd-498">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-498">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-499">65</span><span class="sxs-lookup"><span data-stu-id="c55fd-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-500">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-500">CC004</span></span></td>
<td><span data-ttu-id="c55fd-501">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-501">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-502">35</span><span class="sxs-lookup"><span data-stu-id="c55fd-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-503">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="c55fd-504">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="c55fd-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-505">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-505">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-506">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="c55fd-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-507">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-508">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-508">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-509">60</span><span class="sxs-lookup"><span data-stu-id="c55fd-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-510">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-511">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-511">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-512">20</span><span class="sxs-lookup"><span data-stu-id="c55fd-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-513">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="c55fd-514">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="c55fd-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-515">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-515">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-516">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="c55fd-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-517">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-518">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-518">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-519">80</span><span class="sxs-lookup"><span data-stu-id="c55fd-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-520">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-521">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-521">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-522">15</span><span class="sxs-lookup"><span data-stu-id="c55fd-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-523">**Uwaga:** W programie Finance and Operations miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="c55fd-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="c55fd-524">Aby uzyskać bardziej szczegółowe informacje o dostawcach miar statystycznych, zobacz temat Szablon dostawcy miar statystycznych</span><span class="sxs-lookup"><span data-stu-id="c55fd-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="c55fd-525">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy). W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="c55fd-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-526">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-526">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-527">Wartość</span><span class="sxs-lookup"><span data-stu-id="c55fd-527">Magnitude</span></span></th>
<th><span data-ttu-id="c55fd-528">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="c55fd-528">Allocation factor</span></span></th>
<th><span data-ttu-id="c55fd-529">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-529">Amount</span></span></th>
<th><span data-ttu-id="c55fd-530">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-531">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-531">CC002</span></span></td>
<td><span data-ttu-id="c55fd-532">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-532">Finance</span></span></td>
<td><span data-ttu-id="c55fd-533">35</span><span class="sxs-lookup"><span data-stu-id="c55fd-533">35</span></span></td>
<td><span data-ttu-id="c55fd-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c55fd-535">175.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-535">175.00</span></span></td>
<td><span data-ttu-id="c55fd-536">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-537">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-537">CC003</span></span></td>
<td><span data-ttu-id="c55fd-538">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-538">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-539">55</span><span class="sxs-lookup"><span data-stu-id="c55fd-539">55</span></span></td>
<td><span data-ttu-id="c55fd-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c55fd-541">275.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-541">275.00</span></span></td>
<td><span data-ttu-id="c55fd-542">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-543">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-543">CC004</span></span></td>
<td><span data-ttu-id="c55fd-544">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-544">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-545">10</span><span class="sxs-lookup"><span data-stu-id="c55fd-545">10</span></span></td>
<td><span data-ttu-id="c55fd-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c55fd-547">50,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-547">50.00</span></span></td>
<td><span data-ttu-id="c55fd-548">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-549">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-549">CC002</span></span></td>
<td><span data-ttu-id="c55fd-550">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-550">Finance</span></span></td>
<td><span data-ttu-id="c55fd-551">35</span><span class="sxs-lookup"><span data-stu-id="c55fd-551">35</span></span></td>
<td><span data-ttu-id="c55fd-552">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="c55fd-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c55fd-553">436.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-553">436.00</span></span></td>
<td><span data-ttu-id="c55fd-554">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-555">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-555">CC003</span></span></td>
<td><span data-ttu-id="c55fd-556">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-556">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-557">55</span><span class="sxs-lookup"><span data-stu-id="c55fd-557">55</span></span></td>
<td><span data-ttu-id="c55fd-558">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="c55fd-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c55fd-559">685.14</span><span class="sxs-lookup"><span data-stu-id="c55fd-559">685.14</span></span></td>
<td><span data-ttu-id="c55fd-560">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-561">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-561">CC004</span></span></td>
<td><span data-ttu-id="c55fd-562">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-562">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-563">10</span><span class="sxs-lookup"><span data-stu-id="c55fd-563">10</span></span></td>
<td><span data-ttu-id="c55fd-564">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="c55fd-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c55fd-565">124.57</span><span class="sxs-lookup"><span data-stu-id="c55fd-565">124.57</span></span></td>
<td><span data-ttu-id="c55fd-566">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-567">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="c55fd-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-568">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-568">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-569">Wartość</span><span class="sxs-lookup"><span data-stu-id="c55fd-569">Magnitude</span></span></th>
<th><span data-ttu-id="c55fd-570">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="c55fd-570">Allocation factor</span></span></th>
<th><span data-ttu-id="c55fd-571">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-571">Amount</span></span></th>
<th><span data-ttu-id="c55fd-572">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-573">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-573">CC003</span></span></td>
<td><span data-ttu-id="c55fd-574">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-574">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-575">65</span><span class="sxs-lookup"><span data-stu-id="c55fd-575">65</span></span></td>
<td><span data-ttu-id="c55fd-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="c55fd-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c55fd-577">438.75</span><span class="sxs-lookup"><span data-stu-id="c55fd-577">438.75</span></span></td>
<td><span data-ttu-id="c55fd-578">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-579">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-579">CC004</span></span></td>
<td><span data-ttu-id="c55fd-580">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-580">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-581">35</span><span class="sxs-lookup"><span data-stu-id="c55fd-581">35</span></span></td>
<td><span data-ttu-id="c55fd-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="c55fd-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c55fd-583">236.25</span><span class="sxs-lookup"><span data-stu-id="c55fd-583">236.25</span></span></td>
<td><span data-ttu-id="c55fd-584">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-585">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-585">CC003</span></span></td>
<td><span data-ttu-id="c55fd-586">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-586">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-587">65</span><span class="sxs-lookup"><span data-stu-id="c55fd-587">65</span></span></td>
<td><span data-ttu-id="c55fd-588">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="c55fd-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c55fd-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c55fd-589">5,297.69</span></span></td>
<td><span data-ttu-id="c55fd-590">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-591">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-591">CC004</span></span></td>
<td><span data-ttu-id="c55fd-592">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-592">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-593">35</span><span class="sxs-lookup"><span data-stu-id="c55fd-593">35</span></span></td>
<td><span data-ttu-id="c55fd-594">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="c55fd-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c55fd-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c55fd-595">2,852.60</span></span></td>
<td><span data-ttu-id="c55fd-596">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-597">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="c55fd-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-598">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-598">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-599">Wartość</span><span class="sxs-lookup"><span data-stu-id="c55fd-599">Magnitude</span></span></th>
<th><span data-ttu-id="c55fd-600">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="c55fd-600">Allocation factor</span></span></th>
<th><span data-ttu-id="c55fd-601">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-601">Amount</span></span></th>
<th><span data-ttu-id="c55fd-602">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-603">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-604">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-604">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-605">60</span><span class="sxs-lookup"><span data-stu-id="c55fd-605">60</span></span></td>
<td><span data-ttu-id="c55fd-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="c55fd-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c55fd-607">535.31</span><span class="sxs-lookup"><span data-stu-id="c55fd-607">535.31</span></span></td>
<td><span data-ttu-id="c55fd-608">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-609">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-610">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-610">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-611">20</span><span class="sxs-lookup"><span data-stu-id="c55fd-611">20</span></span></td>
<td><span data-ttu-id="c55fd-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="c55fd-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c55fd-613">178.44</span><span class="sxs-lookup"><span data-stu-id="c55fd-613">178.44</span></span></td>
<td><span data-ttu-id="c55fd-614">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-615">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-616">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-616">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-617">60</span><span class="sxs-lookup"><span data-stu-id="c55fd-617">60</span></span></td>
<td><span data-ttu-id="c55fd-618">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="c55fd-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c55fd-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c55fd-619">4,487.12</span></span></td>
<td><span data-ttu-id="c55fd-620">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-621">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-622">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-622">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-623">20</span><span class="sxs-lookup"><span data-stu-id="c55fd-623">20</span></span></td>
<td><span data-ttu-id="c55fd-624">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="c55fd-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c55fd-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c55fd-625">1,495.71</span></span></td>
<td><span data-ttu-id="c55fd-626">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c55fd-627">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="c55fd-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-628">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-628">Cost object</span></span></th>
<th><span data-ttu-id="c55fd-629">Wartość</span><span class="sxs-lookup"><span data-stu-id="c55fd-629">Magnitude</span></span></th>
<th><span data-ttu-id="c55fd-630">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="c55fd-630">Allocation factor</span></span></th>
<th><span data-ttu-id="c55fd-631">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-631">Amount</span></span></th>
<th><span data-ttu-id="c55fd-632">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-633">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-634">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-634">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-635">80</span><span class="sxs-lookup"><span data-stu-id="c55fd-635">80</span></span></td>
<td><span data-ttu-id="c55fd-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="c55fd-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c55fd-637">241.05</span><span class="sxs-lookup"><span data-stu-id="c55fd-637">241.05</span></span></td>
<td><span data-ttu-id="c55fd-638">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-639">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-640">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-640">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-641">15</span><span class="sxs-lookup"><span data-stu-id="c55fd-641">15</span></span></td>
<td><span data-ttu-id="c55fd-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="c55fd-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c55fd-643">45.20</span><span class="sxs-lookup"><span data-stu-id="c55fd-643">45.20</span></span></td>
<td><span data-ttu-id="c55fd-644">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-645">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-646">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-646">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-647">80</span><span class="sxs-lookup"><span data-stu-id="c55fd-647">80</span></span></td>
<td><span data-ttu-id="c55fd-648">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="c55fd-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c55fd-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c55fd-649">2,507.09</span></span></td>
<td><span data-ttu-id="c55fd-650">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-651">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-652">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-652">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-653">15</span><span class="sxs-lookup"><span data-stu-id="c55fd-653">15</span></span></td>
<td><span data-ttu-id="c55fd-654">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="c55fd-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c55fd-655">470.08</span><span class="sxs-lookup"><span data-stu-id="c55fd-655">470.08</span></span></td>
<td><span data-ttu-id="c55fd-656">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c55fd-657">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="c55fd-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c55fd-658">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="c55fd-658">Journal</span></span></th>
<th><span data-ttu-id="c55fd-659">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="c55fd-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c55fd-660">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="c55fd-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c55fd-661">Wersja</span><span class="sxs-lookup"><span data-stu-id="c55fd-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-662">00004</span><span class="sxs-lookup"><span data-stu-id="c55fd-662">00004</span></span></td>
<td><span data-ttu-id="c55fd-663">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="c55fd-664">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="c55fd-664">Fiscal</span></span></td>
<td><span data-ttu-id="c55fd-665">2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-665">2017</span></span></td>
<td><span data-ttu-id="c55fd-666">Okres 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-666">Period 1</span></span></td>
<td><span data-ttu-id="c55fd-667">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="c55fd-668">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="c55fd-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c55fd-669">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="c55fd-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-670">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-671">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-671">Cost element</span></span></th>
<th><span data-ttu-id="c55fd-672">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-672">Cost behavior</span></span></th>
<th><span data-ttu-id="c55fd-673">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-674">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-675">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-675">CC001</span></span></td>
<td><span data-ttu-id="c55fd-676">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-676">HR</span></span></td>
<td><span data-ttu-id="c55fd-677">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-677">10001</span></span></td>
<td><span data-ttu-id="c55fd-678">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-678">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-679">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-679">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-680">500.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-681">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-682">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-682">CC001</span></span></td>
<td><span data-ttu-id="c55fd-683">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-683">HR</span></span></td>
<td><span data-ttu-id="c55fd-684">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-684">10001</span></span></td>
<td><span data-ttu-id="c55fd-685">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-685">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-686">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-686">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="c55fd-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-688">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-689">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-689">CC002</span></span></td>
<td><span data-ttu-id="c55fd-690">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-690">Finance</span></span></td>
<td><span data-ttu-id="c55fd-691">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-691">10001</span></span></td>
<td><span data-ttu-id="c55fd-692">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-692">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-693">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-693">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-694">675.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-695">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-696">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-696">CC002</span></span></td>
<td><span data-ttu-id="c55fd-697">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-697">Finance</span></span></td>
<td><span data-ttu-id="c55fd-698">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-698">10001</span></span></td>
<td><span data-ttu-id="c55fd-699">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-699">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-700">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-700">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="c55fd-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-702">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-703">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-703">CC003</span></span></td>
<td><span data-ttu-id="c55fd-704">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-704">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-705">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-705">10001</span></span></td>
<td><span data-ttu-id="c55fd-706">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-706">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-707">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-707">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-708">713.75</span><span class="sxs-lookup"><span data-stu-id="c55fd-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-709">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-710">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-710">CC003</span></span></td>
<td><span data-ttu-id="c55fd-711">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-711">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-712">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-712">10001</span></span></td>
<td><span data-ttu-id="c55fd-713">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-713">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-714">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-714">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="c55fd-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-716">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-717">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-717">CC003</span></span></td>
<td><span data-ttu-id="c55fd-718">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-718">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-719">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-719">10001</span></span></td>
<td><span data-ttu-id="c55fd-720">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-720">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-721">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-721">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-722">286.25</span><span class="sxs-lookup"><span data-stu-id="c55fd-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-723">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-724">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-724">CC003</span></span></td>
<td><span data-ttu-id="c55fd-725">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-725">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-726">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-726">10001</span></span></td>
<td><span data-ttu-id="c55fd-727">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-727">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-728">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-728">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="c55fd-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-730">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-731">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-732">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-732">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-733">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-733">10001</span></span></td>
<td><span data-ttu-id="c55fd-734">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-734">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-735">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-735">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-736">776.36</span><span class="sxs-lookup"><span data-stu-id="c55fd-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-737">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-738">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-739">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-739">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-740">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-740">10001</span></span></td>
<td><span data-ttu-id="c55fd-741">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-741">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-742">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-742">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c55fd-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-744">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-745">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-746">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-746">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-747">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-747">10001</span></span></td>
<td><span data-ttu-id="c55fd-748">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-748">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-749">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-749">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-750">223.64</span><span class="sxs-lookup"><span data-stu-id="c55fd-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-751">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="c55fd-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-752">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-753">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-753">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-754">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-754">10001</span></span></td>
<td><span data-ttu-id="c55fd-755">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-755">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-756">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-756">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c55fd-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c55fd-758">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c55fd-759">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c55fd-760">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-760">Cost element</span></span></th>
<th><span data-ttu-id="c55fd-761">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-761">Cost behavior</span></span></th>
<th><span data-ttu-id="c55fd-762">Ilość</span><span class="sxs-lookup"><span data-stu-id="c55fd-762">Amount</span></span></th>
<th><span data-ttu-id="c55fd-763">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="c55fd-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c55fd-764">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-764">CC001</span></span></td>
<td><span data-ttu-id="c55fd-765">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-765">HR</span></span></td>
<td><span data-ttu-id="c55fd-766">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-766">10001</span></span></td>
<td><span data-ttu-id="c55fd-767">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-767">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-768">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-768">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-769">-500.00</span></span></td>
<td><span data-ttu-id="c55fd-770">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-771">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-771">CC002</span></span></td>
<td><span data-ttu-id="c55fd-772">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-772">Finance</span></span></td>
<td><span data-ttu-id="c55fd-773">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-773">10001</span></span></td>
<td><span data-ttu-id="c55fd-774">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-774">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-775">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-775">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-776">175.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-776">175.00</span></span></td>
<td><span data-ttu-id="c55fd-777">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-778">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-778">CC003</span></span></td>
<td><span data-ttu-id="c55fd-779">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-779">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-780">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-780">10001</span></span></td>
<td><span data-ttu-id="c55fd-781">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-781">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-782">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-782">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-783">275.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-783">275.00</span></span></td>
<td><span data-ttu-id="c55fd-784">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-785">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-785">CC004</span></span></td>
<td><span data-ttu-id="c55fd-786">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-786">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-787">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-787">10001</span></span></td>
<td><span data-ttu-id="c55fd-788">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-788">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-789">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-789">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-790">50,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-790">50,00</span></span></td>
<td><span data-ttu-id="c55fd-791">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-792">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-792">CC001</span></span></td>
<td><span data-ttu-id="c55fd-793">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="c55fd-793">HR</span></span></td>
<td><span data-ttu-id="c55fd-794">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-794">10001</span></span></td>
<td><span data-ttu-id="c55fd-795">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-795">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-796">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-796">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-797">-1245,71</span><span class="sxs-lookup"><span data-stu-id="c55fd-797">-1,245.71</span></span></td>
<td><span data-ttu-id="c55fd-798">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-799">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-799">CC002</span></span></td>
<td><span data-ttu-id="c55fd-800">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-800">Finance</span></span></td>
<td><span data-ttu-id="c55fd-801">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-801">10001</span></span></td>
<td><span data-ttu-id="c55fd-802">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-802">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-803">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-803">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-804">436.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-804">436.00</span></span></td>
<td><span data-ttu-id="c55fd-805">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-806">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-806">CC003</span></span></td>
<td><span data-ttu-id="c55fd-807">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-807">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-808">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-808">10001</span></span></td>
<td><span data-ttu-id="c55fd-809">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-809">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-810">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-810">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-811">685.14</span><span class="sxs-lookup"><span data-stu-id="c55fd-811">685.14</span></span></td>
<td><span data-ttu-id="c55fd-812">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-813">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-813">CC004</span></span></td>
<td><span data-ttu-id="c55fd-814">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-814">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-815">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-815">10001</span></span></td>
<td><span data-ttu-id="c55fd-816">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-816">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-817">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-817">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-818">124.57</span><span class="sxs-lookup"><span data-stu-id="c55fd-818">124.57</span></span></td>
<td><span data-ttu-id="c55fd-819">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-820">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-820">CC002</span></span></td>
<td><span data-ttu-id="c55fd-821">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-821">Finance</span></span></td>
<td><span data-ttu-id="c55fd-822">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-822">10001</span></span></td>
<td><span data-ttu-id="c55fd-823">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-823">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-824">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-824">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-825">-675.00</span></span></td>
<td><span data-ttu-id="c55fd-826">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-827">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-827">CC003</span></span></td>
<td><span data-ttu-id="c55fd-828">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-828">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-829">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-829">10001</span></span></td>
<td><span data-ttu-id="c55fd-830">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-830">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-831">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-831">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-832">438.75</span><span class="sxs-lookup"><span data-stu-id="c55fd-832">438.75</span></span></td>
<td><span data-ttu-id="c55fd-833">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-834">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-834">CC004</span></span></td>
<td><span data-ttu-id="c55fd-835">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-835">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-836">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-836">10001</span></span></td>
<td><span data-ttu-id="c55fd-837">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-837">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-838">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-838">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-839">236.25</span><span class="sxs-lookup"><span data-stu-id="c55fd-839">236.25</span></span></td>
<td><span data-ttu-id="c55fd-840">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-841">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-841">CC002</span></span></td>
<td><span data-ttu-id="c55fd-842">Finanse</span><span class="sxs-lookup"><span data-stu-id="c55fd-842">Finance</span></span></td>
<td><span data-ttu-id="c55fd-843">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-843">10001</span></span></td>
<td><span data-ttu-id="c55fd-844">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-844">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-845">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-845">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-846">-8150,29</span><span class="sxs-lookup"><span data-stu-id="c55fd-846">-8,150.29</span></span></td>
<td><span data-ttu-id="c55fd-847">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-848">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-848">CC003</span></span></td>
<td><span data-ttu-id="c55fd-849">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-849">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-850">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-850">10001</span></span></td>
<td><span data-ttu-id="c55fd-851">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-851">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-852">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-852">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c55fd-853">5,297.69</span></span></td>
<td><span data-ttu-id="c55fd-854">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-855">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-855">CC004</span></span></td>
<td><span data-ttu-id="c55fd-856">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="c55fd-856">Packaging</span></span></td>
<td><span data-ttu-id="c55fd-857">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-857">10001</span></span></td>
<td><span data-ttu-id="c55fd-858">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-858">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-859">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-859">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c55fd-860">2,852.60</span></span></td>
<td><span data-ttu-id="c55fd-861">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-862">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-862">CC003</span></span></td>
<td><span data-ttu-id="c55fd-863">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-863">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-864">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-864">10001</span></span></td>
<td><span data-ttu-id="c55fd-865">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-865">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-866">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-866">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="c55fd-867">-713.75</span></span></td>
<td><span data-ttu-id="c55fd-868">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-869">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-870">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-870">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-871">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-871">10001</span></span></td>
<td><span data-ttu-id="c55fd-872">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-872">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-873">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-873">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-874">535.31</span><span class="sxs-lookup"><span data-stu-id="c55fd-874">535.31</span></span></td>
<td><span data-ttu-id="c55fd-875">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-876">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-877">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-877">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-878">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-878">10001</span></span></td>
<td><span data-ttu-id="c55fd-879">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-879">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-880">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-880">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-881">178.44</span><span class="sxs-lookup"><span data-stu-id="c55fd-881">178.44</span></span></td>
<td><span data-ttu-id="c55fd-882">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-883">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-883">CC003</span></span></td>
<td><span data-ttu-id="c55fd-884">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-884">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-885">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-885">10001</span></span></td>
<td><span data-ttu-id="c55fd-886">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-886">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-887">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-887">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-888">-5982,83</span><span class="sxs-lookup"><span data-stu-id="c55fd-888">-5,982.83</span></span></td>
<td><span data-ttu-id="c55fd-889">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-890">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-891">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-891">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-892">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-892">10001</span></span></td>
<td><span data-ttu-id="c55fd-893">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-893">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-894">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-894">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c55fd-895">4,487.12</span></span></td>
<td><span data-ttu-id="c55fd-896">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-897">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-898">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-898">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-899">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-899">10001</span></span></td>
<td><span data-ttu-id="c55fd-900">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-900">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-901">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-901">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c55fd-902">1,495.71</span></span></td>
<td><span data-ttu-id="c55fd-903">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-904">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-904">CC003</span></span></td>
<td><span data-ttu-id="c55fd-905">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-905">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-906">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-906">10001</span></span></td>
<td><span data-ttu-id="c55fd-907">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-907">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-908">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-908">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="c55fd-909">-286.25</span></span></td>
<td><span data-ttu-id="c55fd-910">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-911">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-912">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-912">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-913">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-913">10001</span></span></td>
<td><span data-ttu-id="c55fd-914">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-914">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-915">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-915">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-916">241.05</span><span class="sxs-lookup"><span data-stu-id="c55fd-916">241.05</span></span></td>
<td><span data-ttu-id="c55fd-917">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-918">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-919">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-919">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-920">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-920">10001</span></span></td>
<td><span data-ttu-id="c55fd-921">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-921">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-922">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-922">Fixed cost</span></span></td>
<td><span data-ttu-id="c55fd-923">45.20</span><span class="sxs-lookup"><span data-stu-id="c55fd-923">45.20</span></span></td>
<td><span data-ttu-id="c55fd-924">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-925">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-925">CC003</span></span></td>
<td><span data-ttu-id="c55fd-926">Zestaw</span><span class="sxs-lookup"><span data-stu-id="c55fd-926">Assembly</span></span></td>
<td><span data-ttu-id="c55fd-927">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-927">10001</span></span></td>
<td><span data-ttu-id="c55fd-928">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-928">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-929">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-929">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-930">-2977,17</span><span class="sxs-lookup"><span data-stu-id="c55fd-930">-2,977.17</span></span></td>
<td><span data-ttu-id="c55fd-931">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-932">Prod 1</span></span></td>
<td><span data-ttu-id="c55fd-933">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-933">Product 1</span></span></td>
<td><span data-ttu-id="c55fd-934">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-934">10001</span></span></td>
<td><span data-ttu-id="c55fd-935">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-935">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-936">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-936">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c55fd-937">2,507.09</span></span></td>
<td><span data-ttu-id="c55fd-938">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c55fd-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-939">Prod 2</span></span></td>
<td><span data-ttu-id="c55fd-940">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-940">Product 2</span></span></td>
<td><span data-ttu-id="c55fd-941">10001</span><span class="sxs-lookup"><span data-stu-id="c55fd-941">10001</span></span></td>
<td><span data-ttu-id="c55fd-942">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="c55fd-942">Electricity</span></span></td>
<td><span data-ttu-id="c55fd-943">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-943">Variable cost</span></span></td>
<td><span data-ttu-id="c55fd-944">470.08</span><span class="sxs-lookup"><span data-stu-id="c55fd-944">470.08</span></span></td>
<td><span data-ttu-id="c55fd-945">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="c55fd-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="c55fd-946">Wniosek</span><span class="sxs-lookup"><span data-stu-id="c55fd-946">Conclusion</span></span>
<span data-ttu-id="c55fd-947">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="c55fd-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="c55fd-948">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="c55fd-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="c55fd-949">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="c55fd-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="c55fd-950">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="c55fd-951">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="c55fd-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="c55fd-952">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="c55fd-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="c55fd-953">Razem</span><span class="sxs-lookup"><span data-stu-id="c55fd-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c55fd-954">CC099</span><span class="sxs-lookup"><span data-stu-id="c55fd-954">CC099</span></span></th>
<th><span data-ttu-id="c55fd-955">CC001</span><span class="sxs-lookup"><span data-stu-id="c55fd-955">CC001</span></span></th>
<th><span data-ttu-id="c55fd-956">CC002</span><span class="sxs-lookup"><span data-stu-id="c55fd-956">CC002</span></span></th>
<th><span data-ttu-id="c55fd-957">CC003</span><span class="sxs-lookup"><span data-stu-id="c55fd-957">CC003</span></span></th>
<th><span data-ttu-id="c55fd-958">CC004</span><span class="sxs-lookup"><span data-stu-id="c55fd-958">CC004</span></span></th>
<th><span data-ttu-id="c55fd-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-959">Proj 1</span></span></th>
<th><span data-ttu-id="c55fd-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-960">Proj 2</span></span></th>
<th><span data-ttu-id="c55fd-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c55fd-961">Prod 1</span></span></th>
<th><span data-ttu-id="c55fd-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c55fd-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="c55fd-963">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="c55fd-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-965"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-966"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-967"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-968"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-969"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-970"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-971"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-972"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="c55fd-973">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="c55fd-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-974">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="c55fd-975">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="c55fd-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-976">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-977">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-978">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-979">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-980">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-981">776.36</span><span class="sxs-lookup"><span data-stu-id="c55fd-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-982">223.64</span><span class="sxs-lookup"><span data-stu-id="c55fd-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-983"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="c55fd-984">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="c55fd-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-985">000</span><span class="sxs-lookup"><span data-stu-id="c55fd-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-986">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-987">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-988">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-989">0,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-990">30.00</span><span class="sxs-lookup"><span data-stu-id="c55fd-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-991">10,00</span><span class="sxs-lookup"><span data-stu-id="c55fd-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c55fd-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c55fd-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c55fd-994"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="c55fd-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c55fd-995">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="c55fd-996">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="c55fd-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="c55fd-997">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="c55fd-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="c55fd-998">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="c55fd-999">Aby uzyskać szczegółowe informacje, zobacz temat Zasada akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="c55fd-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="c55fd-1000">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="c55fd-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




