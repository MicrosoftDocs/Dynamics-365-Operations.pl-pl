---
title: Obliczenie narzutu
description: W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 2dddc22128621dc148a253cd568430587f294544
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822910"
---
# <a name="overhead-calculation"></a><span data-ttu-id="fe854-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="fe854-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fe854-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="fe854-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="fe854-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="fe854-105">Term definition</span></span>
---------------

<span data-ttu-id="fe854-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="fe854-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="fe854-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="fe854-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="fe854-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="fe854-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="fe854-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="fe854-109">Rent</span></span>
-   <span data-ttu-id="fe854-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-110">Electricity</span></span>
-   <span data-ttu-id="fe854-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="fe854-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="fe854-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="fe854-112">Overhead calculation overview</span></span>
<span data-ttu-id="fe854-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="fe854-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="fe854-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="fe854-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="fe854-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="fe854-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="fe854-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="fe854-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="fe854-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="fe854-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="fe854-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="fe854-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="fe854-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="fe854-119">Version type</span></span>
-   <span data-ttu-id="fe854-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="fe854-120">Date and time</span></span>
-   <span data-ttu-id="fe854-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="fe854-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="fe854-122">Fiscal year</span></span>
-   <span data-ttu-id="fe854-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="fe854-123">Fiscal period</span></span>

<span data-ttu-id="fe854-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="fe854-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="fe854-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="fe854-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="fe854-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="fe854-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="fe854-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="fe854-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="fe854-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="fe854-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="fe854-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="fe854-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="fe854-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="fe854-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="fe854-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="fe854-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="fe854-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="fe854-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="fe854-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="fe854-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="fe854-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="fe854-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="fe854-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="fe854-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="fe854-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fe854-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="fe854-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="fe854-140">Main account</span></span></th>
<th><span data-ttu-id="fe854-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="fe854-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="fe854-143">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-143">CC099</span></span></td>
<td><span data-ttu-id="fe854-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-144">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-145">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-145">10001</span></span></td>
<td><span data-ttu-id="fe854-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-146">Electricity</span></span></td>
<td><span data-ttu-id="fe854-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="fe854-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="fe854-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="fe854-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="fe854-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="fe854-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="fe854-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-151">Define the cost behavior rule</span></span>

<span data-ttu-id="fe854-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="fe854-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="fe854-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="fe854-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="fe854-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="fe854-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="fe854-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="fe854-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="fe854-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="fe854-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="fe854-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="fe854-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="fe854-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="fe854-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fe854-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="fe854-160">Journal</span></span></th>
<th><span data-ttu-id="fe854-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="fe854-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fe854-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="fe854-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fe854-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="fe854-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-164">00001</span><span class="sxs-lookup"><span data-stu-id="fe854-164">00001</span></span></td>
<td><span data-ttu-id="fe854-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="fe854-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="fe854-166">Fiscal</span></span></td>
<td><span data-ttu-id="fe854-167">2017</span><span class="sxs-lookup"><span data-stu-id="fe854-167">2017</span></span></td>
<td><span data-ttu-id="fe854-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="fe854-168">Period 1</span></span></td>
<td><span data-ttu-id="fe854-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="fe854-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="fe854-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="fe854-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fe854-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="fe854-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-173">Cost element</span></span></th>
<th><span data-ttu-id="fe854-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-174">Cost behavior</span></span></th>
<th><span data-ttu-id="fe854-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="fe854-177">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-177">CC099</span></span></td>
<td><span data-ttu-id="fe854-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-178">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-179">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-179">10001</span></span></td>
<td><span data-ttu-id="fe854-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-180">Electricity</span></span></td>
<td><span data-ttu-id="fe854-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="fe854-181">Unclassified</span></span></td>
<td><span data-ttu-id="fe854-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="fe854-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fe854-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-185">Cost element</span></span></th>
<th><span data-ttu-id="fe854-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-186">Cost behavior</span></span></th>
<th><span data-ttu-id="fe854-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-187">Amount</span></span></th>
<th><span data-ttu-id="fe854-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="fe854-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-189">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-189">CC099</span></span></td>
<td><span data-ttu-id="fe854-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-190">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-191">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-191">10001</span></span></td>
<td><span data-ttu-id="fe854-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-192">Electricity</span></span></td>
<td><span data-ttu-id="fe854-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="fe854-193">Unclassified</span></span></td>
<td><span data-ttu-id="fe854-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="fe854-194">10,000.00</span></span></td>
<td><span data-ttu-id="fe854-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-196">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-196">CC099</span></span></td>
<td><span data-ttu-id="fe854-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-197">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-198">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-198">10001</span></span></td>
<td><span data-ttu-id="fe854-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-199">Electricity</span></span></td>
<td><span data-ttu-id="fe854-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="fe854-200">Unclassified</span></span></td>
<td><span data-ttu-id="fe854-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-201">-10,000.00</span></span></td>
<td><span data-ttu-id="fe854-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-203">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-203">CC099</span></span></td>
<td><span data-ttu-id="fe854-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-204">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-205">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-205">10001</span></span></td>
<td><span data-ttu-id="fe854-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-206">Electricity</span></span></td>
<td><span data-ttu-id="fe854-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-207">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-208">1,000.00</span></span></td>
<td><span data-ttu-id="fe854-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-210">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-210">CC099</span></span></td>
<td><span data-ttu-id="fe854-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-211">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-212">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-212">10001</span></span></td>
<td><span data-ttu-id="fe854-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-213">Electricity</span></span></td>
<td><span data-ttu-id="fe854-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-214">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="fe854-215">9,000.00</span></span></td>
<td><span data-ttu-id="fe854-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="fe854-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="fe854-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="fe854-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="fe854-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="fe854-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="fe854-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="fe854-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-221">Define the cost distribution rule</span></span>

<span data-ttu-id="fe854-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="fe854-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="fe854-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="fe854-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="fe854-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="fe854-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="fe854-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="fe854-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="fe854-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="fe854-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="fe854-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="fe854-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-228">Cost object</span></span></th>
<th><span data-ttu-id="fe854-229">kWh</span><span class="sxs-lookup"><span data-stu-id="fe854-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-230">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-230">CC001</span></span></td>
<td><span data-ttu-id="fe854-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-231">HR</span></span></td>
<td><span data-ttu-id="fe854-232">1 000</span><span class="sxs-lookup"><span data-stu-id="fe854-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-233">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-233">CC002</span></span></td>
<td><span data-ttu-id="fe854-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-234">Finance</span></span></td>
<td><span data-ttu-id="fe854-235">6,000</span><span class="sxs-lookup"><span data-stu-id="fe854-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-236">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-236">CC003</span></span></td>
<td><span data-ttu-id="fe854-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-237">Assembly</span></span></td>
<td><span data-ttu-id="fe854-238">0</span><span class="sxs-lookup"><span data-stu-id="fe854-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="fe854-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-240">Cost object</span></span></th>
<th><span data-ttu-id="fe854-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe854-241">Magnitude</span></span></th>
<th><span data-ttu-id="fe854-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="fe854-242">Allocation factor</span></span></th>
<th><span data-ttu-id="fe854-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-244">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-244">CC001</span></span></td>
<td><span data-ttu-id="fe854-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-245">HR</span></span></td>
<td><span data-ttu-id="fe854-246">1 000</span><span class="sxs-lookup"><span data-stu-id="fe854-246">1,000</span></span></td>
<td><span data-ttu-id="fe854-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="fe854-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="fe854-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-249">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-249">CC002</span></span></td>
<td><span data-ttu-id="fe854-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-250">Finance</span></span></td>
<td><span data-ttu-id="fe854-251">6,000</span><span class="sxs-lookup"><span data-stu-id="fe854-251">6,000</span></span></td>
<td><span data-ttu-id="fe854-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="fe854-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="fe854-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-254">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-254">CC003</span></span></td>
<td><span data-ttu-id="fe854-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-255">Assembly</span></span></td>
<td><span data-ttu-id="fe854-256">0</span><span class="sxs-lookup"><span data-stu-id="fe854-256">0</span></span></td>
<td><span data-ttu-id="fe854-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="fe854-258">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="fe854-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="fe854-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="fe854-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-261">Cost object</span></span></th>
<th><span data-ttu-id="fe854-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="fe854-262">Formula</span></span></th>
<th><span data-ttu-id="fe854-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe854-263">Magnitude</span></span></th>
<th><span data-ttu-id="fe854-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="fe854-264">Allocation factor</span></span></th>
<th><span data-ttu-id="fe854-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-266">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-266">CC001</span></span></td>
<td><span data-ttu-id="fe854-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-267">HR</span></span></td>
<td><span data-ttu-id="fe854-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="fe854-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="fe854-269">1</span><span class="sxs-lookup"><span data-stu-id="fe854-269">1</span></span></td>
<td><span data-ttu-id="fe854-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="fe854-271">500.00</span><span class="sxs-lookup"><span data-stu-id="fe854-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-272">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-272">CC002</span></span></td>
<td><span data-ttu-id="fe854-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-273">Finance</span></span></td>
<td><span data-ttu-id="fe854-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="fe854-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="fe854-275">1</span><span class="sxs-lookup"><span data-stu-id="fe854-275">1</span></span></td>
<td><span data-ttu-id="fe854-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="fe854-277">500.00</span><span class="sxs-lookup"><span data-stu-id="fe854-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-278">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-278">CC003</span></span></td>
<td><span data-ttu-id="fe854-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-279">Assembly</span></span></td>
<td><span data-ttu-id="fe854-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="fe854-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="fe854-281">0</span><span class="sxs-lookup"><span data-stu-id="fe854-281">0</span></span></td>
<td><span data-ttu-id="fe854-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="fe854-283">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="fe854-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="fe854-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fe854-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="fe854-285">Journal</span></span></th>
<th><span data-ttu-id="fe854-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="fe854-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fe854-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="fe854-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fe854-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="fe854-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-289">00002</span><span class="sxs-lookup"><span data-stu-id="fe854-289">00002</span></span></td>
<td><span data-ttu-id="fe854-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="fe854-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="fe854-291">Fiscal</span></span></td>
<td><span data-ttu-id="fe854-292">2017</span><span class="sxs-lookup"><span data-stu-id="fe854-292">2017</span></span></td>
<td><span data-ttu-id="fe854-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="fe854-293">Period 1</span></span></td>
<td><span data-ttu-id="fe854-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="fe854-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="fe854-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="fe854-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fe854-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="fe854-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-298">Cost element</span></span></th>
<th><span data-ttu-id="fe854-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-299">Cost behavior</span></span></th>
<th><span data-ttu-id="fe854-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-302">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-302">CC099</span></span></td>
<td><span data-ttu-id="fe854-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-303">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-304">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-304">10001</span></span></td>
<td><span data-ttu-id="fe854-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-305">Electricity</span></span></td>
<td><span data-ttu-id="fe854-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-306">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-309">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-309">CC099</span></span></td>
<td><span data-ttu-id="fe854-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-310">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-311">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-311">10001</span></span></td>
<td><span data-ttu-id="fe854-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-312">Electricity</span></span></td>
<td><span data-ttu-id="fe854-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-313">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="fe854-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fe854-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-317">Cost element</span></span></th>
<th><span data-ttu-id="fe854-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-318">Cost behavior</span></span></th>
<th><span data-ttu-id="fe854-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-319">Amount</span></span></th>
<th><span data-ttu-id="fe854-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="fe854-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-321">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-321">CC099</span></span></td>
<td><span data-ttu-id="fe854-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-322">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-323">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-323">10001</span></span></td>
<td><span data-ttu-id="fe854-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-324">Electricity</span></span></td>
<td><span data-ttu-id="fe854-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-325">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-326">-1,000.00</span></span></td>
<td><span data-ttu-id="fe854-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-328">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-328">CC001</span></span></td>
<td><span data-ttu-id="fe854-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-329">HR</span></span></td>
<td><span data-ttu-id="fe854-330">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-330">10001</span></span></td>
<td><span data-ttu-id="fe854-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-331">Electricity</span></span></td>
<td><span data-ttu-id="fe854-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-332">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-333">500.00</span><span class="sxs-lookup"><span data-stu-id="fe854-333">500.00</span></span></td>
<td><span data-ttu-id="fe854-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-335">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-335">CC002</span></span></td>
<td><span data-ttu-id="fe854-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-336">Finance</span></span></td>
<td><span data-ttu-id="fe854-337">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-337">10001</span></span></td>
<td><span data-ttu-id="fe854-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-338">Electricity</span></span></td>
<td><span data-ttu-id="fe854-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-339">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-340">500.00</span><span class="sxs-lookup"><span data-stu-id="fe854-340">500.00</span></span></td>
<td><span data-ttu-id="fe854-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-342">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-342">CC099</span></span></td>
<td><span data-ttu-id="fe854-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-343">Default cost center</span></span></td>
<td><span data-ttu-id="fe854-344">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-344">10001</span></span></td>
<td><span data-ttu-id="fe854-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-345">Electricity</span></span></td>
<td><span data-ttu-id="fe854-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-346">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="fe854-347">-9,000.00</span></span></td>
<td><span data-ttu-id="fe854-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-349">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-349">CC001</span></span></td>
<td><span data-ttu-id="fe854-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-350">HR</span></span></td>
<td><span data-ttu-id="fe854-351">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-351">10001</span></span></td>
<td><span data-ttu-id="fe854-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-352">Electricity</span></span></td>
<td><span data-ttu-id="fe854-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-353">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="fe854-354">1,285.71</span></span></td>
<td><span data-ttu-id="fe854-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-356">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-356">CC002</span></span></td>
<td><span data-ttu-id="fe854-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-357">Finance</span></span></td>
<td><span data-ttu-id="fe854-358">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-358">10001</span></span></td>
<td><span data-ttu-id="fe854-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-359">Electricity</span></span></td>
<td><span data-ttu-id="fe854-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-360">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="fe854-361">7,714.29</span></span></td>
<td><span data-ttu-id="fe854-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="fe854-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="fe854-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="fe854-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="fe854-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="fe854-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="fe854-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="fe854-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="fe854-367">Define the overhead rate</span></span>

<span data-ttu-id="fe854-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="fe854-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="fe854-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="fe854-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-370">Cost object</span></span></th>
<th><span data-ttu-id="fe854-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="fe854-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fe854-372">Proj 1</span></span></td>
<td><span data-ttu-id="fe854-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-373">Project 1</span></span></td>
<td><span data-ttu-id="fe854-374">3</span><span class="sxs-lookup"><span data-stu-id="fe854-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fe854-375">Proj 2</span></span></td>
<td><span data-ttu-id="fe854-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-376">Project 2</span></span></td>
<td><span data-ttu-id="fe854-377">1</span><span class="sxs-lookup"><span data-stu-id="fe854-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="fe854-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-379">Cost object</span></span></th>
<th><span data-ttu-id="fe854-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-380">Cost element</span></span></th>
<th><span data-ttu-id="fe854-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-381">Cost behavior</span></span></th>
<th><span data-ttu-id="fe854-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="fe854-382">Units</span></span></th>
<th><span data-ttu-id="fe854-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="fe854-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-384">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-384">CC001</span></span></td>
<td><span data-ttu-id="fe854-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-385">HR</span></span></td>
<td><span data-ttu-id="fe854-386">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-386">10001</span></span></td>
<td><span data-ttu-id="fe854-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-387">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-388">1</span><span class="sxs-lookup"><span data-stu-id="fe854-388">1</span></span></td>
<td><span data-ttu-id="fe854-389">10</span><span class="sxs-lookup"><span data-stu-id="fe854-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="fe854-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-391">Cost object</span></span></th>
<th><span data-ttu-id="fe854-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe854-392">Magnitude</span></span></th>
<th><span data-ttu-id="fe854-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-393">Cost element</span></span></th>
<th><span data-ttu-id="fe854-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="fe854-394">Allocation factor</span></span></th>
<th><span data-ttu-id="fe854-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fe854-396">Proj 1</span></span></td>
<td><span data-ttu-id="fe854-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-397">Project 1</span></span></td>
<td><span data-ttu-id="fe854-398">3</span><span class="sxs-lookup"><span data-stu-id="fe854-398">3</span></span></td>
<td><span data-ttu-id="fe854-399">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-399">10001</span></span></td>
<td><span data-ttu-id="fe854-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="fe854-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="fe854-401">30.00</span><span class="sxs-lookup"><span data-stu-id="fe854-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fe854-402">Proj 2</span></span></td>
<td><span data-ttu-id="fe854-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-403">Project 2</span></span></td>
<td><span data-ttu-id="fe854-404">1</span><span class="sxs-lookup"><span data-stu-id="fe854-404">1</span></span></td>
<td><span data-ttu-id="fe854-405">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-405">10001</span></span></td>
<td><span data-ttu-id="fe854-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="fe854-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="fe854-407">10,00</span><span class="sxs-lookup"><span data-stu-id="fe854-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="fe854-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="fe854-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fe854-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="fe854-409">Journal</span></span></th>
<th><span data-ttu-id="fe854-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="fe854-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fe854-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="fe854-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fe854-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="fe854-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-413">00003</span><span class="sxs-lookup"><span data-stu-id="fe854-413">00003</span></span></td>
<td><span data-ttu-id="fe854-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="fe854-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="fe854-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="fe854-415">Fiscal</span></span></td>
<td><span data-ttu-id="fe854-416">2017</span><span class="sxs-lookup"><span data-stu-id="fe854-416">2017</span></span></td>
<td><span data-ttu-id="fe854-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="fe854-417">Period 1</span></span></td>
<td><span data-ttu-id="fe854-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="fe854-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="fe854-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="fe854-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fe854-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="fe854-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-421">Cost object</span></span></th>
<th><span data-ttu-id="fe854-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe854-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fe854-424">Proj 1</span></span></td>
<td><span data-ttu-id="fe854-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="fe854-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="fe854-426">3,00</span><span class="sxs-lookup"><span data-stu-id="fe854-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fe854-428">Proj 2</span></span></td>
<td><span data-ttu-id="fe854-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="fe854-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="fe854-430">1.00</span><span class="sxs-lookup"><span data-stu-id="fe854-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fe854-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-433">Cost element</span></span></th>
<th><span data-ttu-id="fe854-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-434">Cost behavior</span></span></th>
<th><span data-ttu-id="fe854-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-435">Amount</span></span></th>
<th><span data-ttu-id="fe854-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="fe854-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="fe854-437">CC0001</span></span></td>
<td><span data-ttu-id="fe854-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-438">HR</span></span></td>
<td><span data-ttu-id="fe854-439">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-439">10001</span></span></td>
<td><span data-ttu-id="fe854-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-440">Electricity</span></span></td>
<td><span data-ttu-id="fe854-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-441">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="fe854-442">-30.00</span></span></td>
<td><span data-ttu-id="fe854-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fe854-444">Proj 1</span></span></td>
<td><span data-ttu-id="fe854-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="fe854-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="fe854-446">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-446">10001</span></span></td>
<td><span data-ttu-id="fe854-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-447">Electricity</span></span></td>
<td><span data-ttu-id="fe854-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-448">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-449">30.00</span><span class="sxs-lookup"><span data-stu-id="fe854-449">30.00</span></span></td>
<td><span data-ttu-id="fe854-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-451">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-451">CC001</span></span></td>
<td><span data-ttu-id="fe854-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-452">HR</span></span></td>
<td><span data-ttu-id="fe854-453">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-453">10001</span></span></td>
<td><span data-ttu-id="fe854-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-454">Electricity</span></span></td>
<td><span data-ttu-id="fe854-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-455">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="fe854-456">-10.00</span></span></td>
<td><span data-ttu-id="fe854-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fe854-458">Proj 2</span></span></td>
<td><span data-ttu-id="fe854-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="fe854-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="fe854-460">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-460">10001</span></span></td>
<td><span data-ttu-id="fe854-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-461">Electricity</span></span></td>
<td><span data-ttu-id="fe854-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-462">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-463">10,00</span><span class="sxs-lookup"><span data-stu-id="fe854-463">10.00</span></span></td>
<td><span data-ttu-id="fe854-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="fe854-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="fe854-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="fe854-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="fe854-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="fe854-468">Aplikacja Finance obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="fe854-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="fe854-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="fe854-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="fe854-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="fe854-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="fe854-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="fe854-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="fe854-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="fe854-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="fe854-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="fe854-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="fe854-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-475">Define the cost allocation</span></span>

<span data-ttu-id="fe854-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="fe854-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="fe854-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="fe854-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-479">Cost object</span></span></th>
<th><span data-ttu-id="fe854-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="fe854-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-481">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-481">CC002</span></span></td>
<td><span data-ttu-id="fe854-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-482">Finance</span></span></td>
<td><span data-ttu-id="fe854-483">35</span><span class="sxs-lookup"><span data-stu-id="fe854-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-484">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-484">CC003</span></span></td>
<td><span data-ttu-id="fe854-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-485">Assembly</span></span></td>
<td><span data-ttu-id="fe854-486">55</span><span class="sxs-lookup"><span data-stu-id="fe854-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-487">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-487">CC004</span></span></td>
<td><span data-ttu-id="fe854-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-488">Packaging</span></span></td>
<td><span data-ttu-id="fe854-489">10</span><span class="sxs-lookup"><span data-stu-id="fe854-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="fe854-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="fe854-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-492">Cost object</span></span></th>
<th><span data-ttu-id="fe854-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="fe854-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-494">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-494">CC003</span></span></td>
<td><span data-ttu-id="fe854-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-495">Assembly</span></span></td>
<td><span data-ttu-id="fe854-496">65</span><span class="sxs-lookup"><span data-stu-id="fe854-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-497">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-497">CC004</span></span></td>
<td><span data-ttu-id="fe854-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-498">Packaging</span></span></td>
<td><span data-ttu-id="fe854-499">35</span><span class="sxs-lookup"><span data-stu-id="fe854-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="fe854-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="fe854-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-502">Cost object</span></span></th>
<th><span data-ttu-id="fe854-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="fe854-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-504">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-505">Product 1</span></span></td>
<td><span data-ttu-id="fe854-506">60</span><span class="sxs-lookup"><span data-stu-id="fe854-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-507">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-508">Product 2</span></span></td>
<td><span data-ttu-id="fe854-509">20</span><span class="sxs-lookup"><span data-stu-id="fe854-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="fe854-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="fe854-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-512">Cost object</span></span></th>
<th><span data-ttu-id="fe854-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="fe854-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-514">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-515">Product 1</span></span></td>
<td><span data-ttu-id="fe854-516">80</span><span class="sxs-lookup"><span data-stu-id="fe854-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-517">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-518">Product 2</span></span></td>
<td><span data-ttu-id="fe854-519">15</span><span class="sxs-lookup"><span data-stu-id="fe854-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="fe854-520">Miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="fe854-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="fe854-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="fe854-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="fe854-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="fe854-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-523">Cost object</span></span></th>
<th><span data-ttu-id="fe854-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe854-524">Magnitude</span></span></th>
<th><span data-ttu-id="fe854-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="fe854-525">Allocation factor</span></span></th>
<th><span data-ttu-id="fe854-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-526">Amount</span></span></th>
<th><span data-ttu-id="fe854-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-528">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-528">CC002</span></span></td>
<td><span data-ttu-id="fe854-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-529">Finance</span></span></td>
<td><span data-ttu-id="fe854-530">35</span><span class="sxs-lookup"><span data-stu-id="fe854-530">35</span></span></td>
<td><span data-ttu-id="fe854-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="fe854-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="fe854-532">175.00</span><span class="sxs-lookup"><span data-stu-id="fe854-532">175.00</span></span></td>
<td><span data-ttu-id="fe854-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-534">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-534">CC003</span></span></td>
<td><span data-ttu-id="fe854-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-535">Assembly</span></span></td>
<td><span data-ttu-id="fe854-536">55</span><span class="sxs-lookup"><span data-stu-id="fe854-536">55</span></span></td>
<td><span data-ttu-id="fe854-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="fe854-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="fe854-538">275.00</span><span class="sxs-lookup"><span data-stu-id="fe854-538">275.00</span></span></td>
<td><span data-ttu-id="fe854-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-540">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-540">CC004</span></span></td>
<td><span data-ttu-id="fe854-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-541">Packaging</span></span></td>
<td><span data-ttu-id="fe854-542">10</span><span class="sxs-lookup"><span data-stu-id="fe854-542">10</span></span></td>
<td><span data-ttu-id="fe854-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="fe854-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="fe854-544">50,00</span><span class="sxs-lookup"><span data-stu-id="fe854-544">50.00</span></span></td>
<td><span data-ttu-id="fe854-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-546">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-546">CC002</span></span></td>
<td><span data-ttu-id="fe854-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-547">Finance</span></span></td>
<td><span data-ttu-id="fe854-548">35</span><span class="sxs-lookup"><span data-stu-id="fe854-548">35</span></span></td>
<td><span data-ttu-id="fe854-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="fe854-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="fe854-550">436.00</span><span class="sxs-lookup"><span data-stu-id="fe854-550">436.00</span></span></td>
<td><span data-ttu-id="fe854-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-552">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-552">CC003</span></span></td>
<td><span data-ttu-id="fe854-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-553">Assembly</span></span></td>
<td><span data-ttu-id="fe854-554">55</span><span class="sxs-lookup"><span data-stu-id="fe854-554">55</span></span></td>
<td><span data-ttu-id="fe854-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="fe854-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="fe854-556">685.14</span><span class="sxs-lookup"><span data-stu-id="fe854-556">685.14</span></span></td>
<td><span data-ttu-id="fe854-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-558">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-558">CC004</span></span></td>
<td><span data-ttu-id="fe854-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-559">Packaging</span></span></td>
<td><span data-ttu-id="fe854-560">10</span><span class="sxs-lookup"><span data-stu-id="fe854-560">10</span></span></td>
<td><span data-ttu-id="fe854-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="fe854-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="fe854-562">124.57</span><span class="sxs-lookup"><span data-stu-id="fe854-562">124.57</span></span></td>
<td><span data-ttu-id="fe854-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="fe854-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-565">Cost object</span></span></th>
<th><span data-ttu-id="fe854-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe854-566">Magnitude</span></span></th>
<th><span data-ttu-id="fe854-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="fe854-567">Allocation factor</span></span></th>
<th><span data-ttu-id="fe854-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-568">Amount</span></span></th>
<th><span data-ttu-id="fe854-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-570">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-570">CC003</span></span></td>
<td><span data-ttu-id="fe854-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-571">Assembly</span></span></td>
<td><span data-ttu-id="fe854-572">65</span><span class="sxs-lookup"><span data-stu-id="fe854-572">65</span></span></td>
<td><span data-ttu-id="fe854-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="fe854-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="fe854-574">438.75</span><span class="sxs-lookup"><span data-stu-id="fe854-574">438.75</span></span></td>
<td><span data-ttu-id="fe854-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-576">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-576">CC004</span></span></td>
<td><span data-ttu-id="fe854-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-577">Packaging</span></span></td>
<td><span data-ttu-id="fe854-578">35</span><span class="sxs-lookup"><span data-stu-id="fe854-578">35</span></span></td>
<td><span data-ttu-id="fe854-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="fe854-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="fe854-580">236.25</span><span class="sxs-lookup"><span data-stu-id="fe854-580">236.25</span></span></td>
<td><span data-ttu-id="fe854-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-582">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-582">CC003</span></span></td>
<td><span data-ttu-id="fe854-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-583">Assembly</span></span></td>
<td><span data-ttu-id="fe854-584">65</span><span class="sxs-lookup"><span data-stu-id="fe854-584">65</span></span></td>
<td><span data-ttu-id="fe854-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="fe854-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="fe854-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="fe854-586">5,297.69</span></span></td>
<td><span data-ttu-id="fe854-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-588">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-588">CC004</span></span></td>
<td><span data-ttu-id="fe854-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-589">Packaging</span></span></td>
<td><span data-ttu-id="fe854-590">35</span><span class="sxs-lookup"><span data-stu-id="fe854-590">35</span></span></td>
<td><span data-ttu-id="fe854-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="fe854-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="fe854-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="fe854-592">2,852.60</span></span></td>
<td><span data-ttu-id="fe854-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="fe854-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-595">Cost object</span></span></th>
<th><span data-ttu-id="fe854-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe854-596">Magnitude</span></span></th>
<th><span data-ttu-id="fe854-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="fe854-597">Allocation factor</span></span></th>
<th><span data-ttu-id="fe854-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-598">Amount</span></span></th>
<th><span data-ttu-id="fe854-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-600">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-601">Product 1</span></span></td>
<td><span data-ttu-id="fe854-602">60</span><span class="sxs-lookup"><span data-stu-id="fe854-602">60</span></span></td>
<td><span data-ttu-id="fe854-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="fe854-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="fe854-604">535.31</span><span class="sxs-lookup"><span data-stu-id="fe854-604">535.31</span></span></td>
<td><span data-ttu-id="fe854-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-606">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-607">Product 2</span></span></td>
<td><span data-ttu-id="fe854-608">20</span><span class="sxs-lookup"><span data-stu-id="fe854-608">20</span></span></td>
<td><span data-ttu-id="fe854-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="fe854-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="fe854-610">178.44</span><span class="sxs-lookup"><span data-stu-id="fe854-610">178.44</span></span></td>
<td><span data-ttu-id="fe854-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-612">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-613">Product 1</span></span></td>
<td><span data-ttu-id="fe854-614">60</span><span class="sxs-lookup"><span data-stu-id="fe854-614">60</span></span></td>
<td><span data-ttu-id="fe854-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="fe854-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="fe854-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="fe854-616">4,487.12</span></span></td>
<td><span data-ttu-id="fe854-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-618">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-619">Product 2</span></span></td>
<td><span data-ttu-id="fe854-620">20</span><span class="sxs-lookup"><span data-stu-id="fe854-620">20</span></span></td>
<td><span data-ttu-id="fe854-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="fe854-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="fe854-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="fe854-622">1,495.71</span></span></td>
<td><span data-ttu-id="fe854-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fe854-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="fe854-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-625">Cost object</span></span></th>
<th><span data-ttu-id="fe854-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe854-626">Magnitude</span></span></th>
<th><span data-ttu-id="fe854-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="fe854-627">Allocation factor</span></span></th>
<th><span data-ttu-id="fe854-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-628">Amount</span></span></th>
<th><span data-ttu-id="fe854-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-630">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-631">Product 1</span></span></td>
<td><span data-ttu-id="fe854-632">80</span><span class="sxs-lookup"><span data-stu-id="fe854-632">80</span></span></td>
<td><span data-ttu-id="fe854-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="fe854-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="fe854-634">241.05</span><span class="sxs-lookup"><span data-stu-id="fe854-634">241.05</span></span></td>
<td><span data-ttu-id="fe854-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-636">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-637">Product 2</span></span></td>
<td><span data-ttu-id="fe854-638">15</span><span class="sxs-lookup"><span data-stu-id="fe854-638">15</span></span></td>
<td><span data-ttu-id="fe854-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="fe854-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="fe854-640">45.20</span><span class="sxs-lookup"><span data-stu-id="fe854-640">45.20</span></span></td>
<td><span data-ttu-id="fe854-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-642">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-643">Product 1</span></span></td>
<td><span data-ttu-id="fe854-644">80</span><span class="sxs-lookup"><span data-stu-id="fe854-644">80</span></span></td>
<td><span data-ttu-id="fe854-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="fe854-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="fe854-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="fe854-646">2,507.09</span></span></td>
<td><span data-ttu-id="fe854-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-648">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-649">Product 2</span></span></td>
<td><span data-ttu-id="fe854-650">15</span><span class="sxs-lookup"><span data-stu-id="fe854-650">15</span></span></td>
<td><span data-ttu-id="fe854-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="fe854-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="fe854-652">470.08</span><span class="sxs-lookup"><span data-stu-id="fe854-652">470.08</span></span></td>
<td><span data-ttu-id="fe854-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="fe854-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="fe854-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fe854-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="fe854-655">Journal</span></span></th>
<th><span data-ttu-id="fe854-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="fe854-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fe854-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="fe854-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fe854-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="fe854-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-659">00004</span><span class="sxs-lookup"><span data-stu-id="fe854-659">00004</span></span></td>
<td><span data-ttu-id="fe854-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="fe854-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="fe854-661">Fiscal</span></span></td>
<td><span data-ttu-id="fe854-662">2017</span><span class="sxs-lookup"><span data-stu-id="fe854-662">2017</span></span></td>
<td><span data-ttu-id="fe854-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="fe854-663">Period 1</span></span></td>
<td><span data-ttu-id="fe854-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="fe854-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="fe854-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="fe854-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fe854-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="fe854-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-668">Cost element</span></span></th>
<th><span data-ttu-id="fe854-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-669">Cost behavior</span></span></th>
<th><span data-ttu-id="fe854-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-672">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-672">CC001</span></span></td>
<td><span data-ttu-id="fe854-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-673">HR</span></span></td>
<td><span data-ttu-id="fe854-674">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-674">10001</span></span></td>
<td><span data-ttu-id="fe854-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-675">Electricity</span></span></td>
<td><span data-ttu-id="fe854-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-676">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-677">500.00</span><span class="sxs-lookup"><span data-stu-id="fe854-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-679">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-679">CC001</span></span></td>
<td><span data-ttu-id="fe854-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-680">HR</span></span></td>
<td><span data-ttu-id="fe854-681">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-681">10001</span></span></td>
<td><span data-ttu-id="fe854-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-682">Electricity</span></span></td>
<td><span data-ttu-id="fe854-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-683">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="fe854-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-686">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-686">CC002</span></span></td>
<td><span data-ttu-id="fe854-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-687">Finance</span></span></td>
<td><span data-ttu-id="fe854-688">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-688">10001</span></span></td>
<td><span data-ttu-id="fe854-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-689">Electricity</span></span></td>
<td><span data-ttu-id="fe854-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-690">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-691">675.00</span><span class="sxs-lookup"><span data-stu-id="fe854-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-693">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-693">CC002</span></span></td>
<td><span data-ttu-id="fe854-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-694">Finance</span></span></td>
<td><span data-ttu-id="fe854-695">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-695">10001</span></span></td>
<td><span data-ttu-id="fe854-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-696">Electricity</span></span></td>
<td><span data-ttu-id="fe854-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-697">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="fe854-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-700">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-700">CC003</span></span></td>
<td><span data-ttu-id="fe854-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-701">Assembly</span></span></td>
<td><span data-ttu-id="fe854-702">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-702">10001</span></span></td>
<td><span data-ttu-id="fe854-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-703">Electricity</span></span></td>
<td><span data-ttu-id="fe854-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-704">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-705">713.75</span><span class="sxs-lookup"><span data-stu-id="fe854-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-707">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-707">CC003</span></span></td>
<td><span data-ttu-id="fe854-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-708">Assembly</span></span></td>
<td><span data-ttu-id="fe854-709">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-709">10001</span></span></td>
<td><span data-ttu-id="fe854-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-710">Electricity</span></span></td>
<td><span data-ttu-id="fe854-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-711">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="fe854-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-714">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-714">CC003</span></span></td>
<td><span data-ttu-id="fe854-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-715">Packaging</span></span></td>
<td><span data-ttu-id="fe854-716">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-716">10001</span></span></td>
<td><span data-ttu-id="fe854-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-717">Electricity</span></span></td>
<td><span data-ttu-id="fe854-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-718">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-719">286.25</span><span class="sxs-lookup"><span data-stu-id="fe854-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-721">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-721">CC003</span></span></td>
<td><span data-ttu-id="fe854-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-722">Packaging</span></span></td>
<td><span data-ttu-id="fe854-723">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-723">10001</span></span></td>
<td><span data-ttu-id="fe854-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-724">Electricity</span></span></td>
<td><span data-ttu-id="fe854-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-725">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="fe854-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-728">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-729">Product 1</span></span></td>
<td><span data-ttu-id="fe854-730">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-730">10001</span></span></td>
<td><span data-ttu-id="fe854-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-731">Electricity</span></span></td>
<td><span data-ttu-id="fe854-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-732">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-733">776.36</span><span class="sxs-lookup"><span data-stu-id="fe854-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-735">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-736">Product 1</span></span></td>
<td><span data-ttu-id="fe854-737">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-737">10001</span></span></td>
<td><span data-ttu-id="fe854-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-738">Electricity</span></span></td>
<td><span data-ttu-id="fe854-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-739">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="fe854-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-742">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-743">Product 1</span></span></td>
<td><span data-ttu-id="fe854-744">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-744">10001</span></span></td>
<td><span data-ttu-id="fe854-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-745">Electricity</span></span></td>
<td><span data-ttu-id="fe854-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-746">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-747">223.64</span><span class="sxs-lookup"><span data-stu-id="fe854-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="fe854-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-749">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-750">Product 1</span></span></td>
<td><span data-ttu-id="fe854-751">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-751">10001</span></span></td>
<td><span data-ttu-id="fe854-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-752">Electricity</span></span></td>
<td><span data-ttu-id="fe854-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-753">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="fe854-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fe854-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fe854-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fe854-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-757">Cost element</span></span></th>
<th><span data-ttu-id="fe854-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-758">Cost behavior</span></span></th>
<th><span data-ttu-id="fe854-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="fe854-759">Amount</span></span></th>
<th><span data-ttu-id="fe854-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="fe854-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fe854-761">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-761">CC001</span></span></td>
<td><span data-ttu-id="fe854-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-762">HR</span></span></td>
<td><span data-ttu-id="fe854-763">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-763">10001</span></span></td>
<td><span data-ttu-id="fe854-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-764">Electricity</span></span></td>
<td><span data-ttu-id="fe854-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-765">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="fe854-766">-500.00</span></span></td>
<td><span data-ttu-id="fe854-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-768">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-768">CC002</span></span></td>
<td><span data-ttu-id="fe854-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-769">Finance</span></span></td>
<td><span data-ttu-id="fe854-770">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-770">10001</span></span></td>
<td><span data-ttu-id="fe854-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-771">Electricity</span></span></td>
<td><span data-ttu-id="fe854-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-772">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-773">175.00</span><span class="sxs-lookup"><span data-stu-id="fe854-773">175.00</span></span></td>
<td><span data-ttu-id="fe854-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-775">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-775">CC003</span></span></td>
<td><span data-ttu-id="fe854-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-776">Assembly</span></span></td>
<td><span data-ttu-id="fe854-777">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-777">10001</span></span></td>
<td><span data-ttu-id="fe854-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-778">Electricity</span></span></td>
<td><span data-ttu-id="fe854-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-779">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-780">275.00</span><span class="sxs-lookup"><span data-stu-id="fe854-780">275.00</span></span></td>
<td><span data-ttu-id="fe854-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-782">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-782">CC004</span></span></td>
<td><span data-ttu-id="fe854-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-783">Packaging</span></span></td>
<td><span data-ttu-id="fe854-784">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-784">10001</span></span></td>
<td><span data-ttu-id="fe854-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-785">Electricity</span></span></td>
<td><span data-ttu-id="fe854-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-786">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-787">50,00</span><span class="sxs-lookup"><span data-stu-id="fe854-787">50,00</span></span></td>
<td><span data-ttu-id="fe854-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-789">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-789">CC001</span></span></td>
<td><span data-ttu-id="fe854-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="fe854-790">HR</span></span></td>
<td><span data-ttu-id="fe854-791">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-791">10001</span></span></td>
<td><span data-ttu-id="fe854-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-792">Electricity</span></span></td>
<td><span data-ttu-id="fe854-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-793">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="fe854-794">-1,245.71</span></span></td>
<td><span data-ttu-id="fe854-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-796">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-796">CC002</span></span></td>
<td><span data-ttu-id="fe854-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-797">Finance</span></span></td>
<td><span data-ttu-id="fe854-798">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-798">10001</span></span></td>
<td><span data-ttu-id="fe854-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-799">Electricity</span></span></td>
<td><span data-ttu-id="fe854-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-800">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-801">436.00</span><span class="sxs-lookup"><span data-stu-id="fe854-801">436.00</span></span></td>
<td><span data-ttu-id="fe854-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-803">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-803">CC003</span></span></td>
<td><span data-ttu-id="fe854-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-804">Assembly</span></span></td>
<td><span data-ttu-id="fe854-805">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-805">10001</span></span></td>
<td><span data-ttu-id="fe854-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-806">Electricity</span></span></td>
<td><span data-ttu-id="fe854-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-807">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-808">685.14</span><span class="sxs-lookup"><span data-stu-id="fe854-808">685.14</span></span></td>
<td><span data-ttu-id="fe854-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-810">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-810">CC004</span></span></td>
<td><span data-ttu-id="fe854-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-811">Packaging</span></span></td>
<td><span data-ttu-id="fe854-812">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-812">10001</span></span></td>
<td><span data-ttu-id="fe854-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-813">Electricity</span></span></td>
<td><span data-ttu-id="fe854-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-814">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-815">124.57</span><span class="sxs-lookup"><span data-stu-id="fe854-815">124.57</span></span></td>
<td><span data-ttu-id="fe854-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-817">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-817">CC002</span></span></td>
<td><span data-ttu-id="fe854-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-818">Finance</span></span></td>
<td><span data-ttu-id="fe854-819">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-819">10001</span></span></td>
<td><span data-ttu-id="fe854-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-820">Electricity</span></span></td>
<td><span data-ttu-id="fe854-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-821">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="fe854-822">-675.00</span></span></td>
<td><span data-ttu-id="fe854-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-824">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-824">CC003</span></span></td>
<td><span data-ttu-id="fe854-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-825">Assembly</span></span></td>
<td><span data-ttu-id="fe854-826">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-826">10001</span></span></td>
<td><span data-ttu-id="fe854-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-827">Electricity</span></span></td>
<td><span data-ttu-id="fe854-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-828">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-829">438.75</span><span class="sxs-lookup"><span data-stu-id="fe854-829">438.75</span></span></td>
<td><span data-ttu-id="fe854-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-831">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-831">CC004</span></span></td>
<td><span data-ttu-id="fe854-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-832">Packaging</span></span></td>
<td><span data-ttu-id="fe854-833">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-833">10001</span></span></td>
<td><span data-ttu-id="fe854-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-834">Electricity</span></span></td>
<td><span data-ttu-id="fe854-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-835">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-836">236.25</span><span class="sxs-lookup"><span data-stu-id="fe854-836">236.25</span></span></td>
<td><span data-ttu-id="fe854-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-838">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-838">CC002</span></span></td>
<td><span data-ttu-id="fe854-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="fe854-839">Finance</span></span></td>
<td><span data-ttu-id="fe854-840">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-840">10001</span></span></td>
<td><span data-ttu-id="fe854-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-841">Electricity</span></span></td>
<td><span data-ttu-id="fe854-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-842">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="fe854-843">-8,150.29</span></span></td>
<td><span data-ttu-id="fe854-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-845">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-845">CC003</span></span></td>
<td><span data-ttu-id="fe854-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-846">Assembly</span></span></td>
<td><span data-ttu-id="fe854-847">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-847">10001</span></span></td>
<td><span data-ttu-id="fe854-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-848">Electricity</span></span></td>
<td><span data-ttu-id="fe854-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-849">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="fe854-850">5,297.69</span></span></td>
<td><span data-ttu-id="fe854-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-852">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-852">CC004</span></span></td>
<td><span data-ttu-id="fe854-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="fe854-853">Packaging</span></span></td>
<td><span data-ttu-id="fe854-854">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-854">10001</span></span></td>
<td><span data-ttu-id="fe854-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-855">Electricity</span></span></td>
<td><span data-ttu-id="fe854-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-856">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="fe854-857">2,852.60</span></span></td>
<td><span data-ttu-id="fe854-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-859">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-859">CC003</span></span></td>
<td><span data-ttu-id="fe854-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-860">Assembly</span></span></td>
<td><span data-ttu-id="fe854-861">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-861">10001</span></span></td>
<td><span data-ttu-id="fe854-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-862">Electricity</span></span></td>
<td><span data-ttu-id="fe854-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-863">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="fe854-864">-713.75</span></span></td>
<td><span data-ttu-id="fe854-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-866">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-867">Product 1</span></span></td>
<td><span data-ttu-id="fe854-868">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-868">10001</span></span></td>
<td><span data-ttu-id="fe854-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-869">Electricity</span></span></td>
<td><span data-ttu-id="fe854-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-870">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-871">535.31</span><span class="sxs-lookup"><span data-stu-id="fe854-871">535.31</span></span></td>
<td><span data-ttu-id="fe854-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-873">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-874">Product 2</span></span></td>
<td><span data-ttu-id="fe854-875">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-875">10001</span></span></td>
<td><span data-ttu-id="fe854-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-876">Electricity</span></span></td>
<td><span data-ttu-id="fe854-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-877">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-878">178.44</span><span class="sxs-lookup"><span data-stu-id="fe854-878">178.44</span></span></td>
<td><span data-ttu-id="fe854-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-880">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-880">CC003</span></span></td>
<td><span data-ttu-id="fe854-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-881">Assembly</span></span></td>
<td><span data-ttu-id="fe854-882">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-882">10001</span></span></td>
<td><span data-ttu-id="fe854-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-883">Electricity</span></span></td>
<td><span data-ttu-id="fe854-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-884">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="fe854-885">-5,982.83</span></span></td>
<td><span data-ttu-id="fe854-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-887">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-888">Product 1</span></span></td>
<td><span data-ttu-id="fe854-889">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-889">10001</span></span></td>
<td><span data-ttu-id="fe854-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-890">Electricity</span></span></td>
<td><span data-ttu-id="fe854-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-891">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="fe854-892">4,487.12</span></span></td>
<td><span data-ttu-id="fe854-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-894">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-895">Product 2</span></span></td>
<td><span data-ttu-id="fe854-896">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-896">10001</span></span></td>
<td><span data-ttu-id="fe854-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-897">Electricity</span></span></td>
<td><span data-ttu-id="fe854-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-898">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="fe854-899">1,495.71</span></span></td>
<td><span data-ttu-id="fe854-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-901">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-901">CC003</span></span></td>
<td><span data-ttu-id="fe854-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-902">Assembly</span></span></td>
<td><span data-ttu-id="fe854-903">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-903">10001</span></span></td>
<td><span data-ttu-id="fe854-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-904">Electricity</span></span></td>
<td><span data-ttu-id="fe854-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-905">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="fe854-906">-286.25</span></span></td>
<td><span data-ttu-id="fe854-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-908">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-909">Product 1</span></span></td>
<td><span data-ttu-id="fe854-910">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-910">10001</span></span></td>
<td><span data-ttu-id="fe854-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-911">Electricity</span></span></td>
<td><span data-ttu-id="fe854-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-912">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-913">241.05</span><span class="sxs-lookup"><span data-stu-id="fe854-913">241.05</span></span></td>
<td><span data-ttu-id="fe854-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-915">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-916">Product 2</span></span></td>
<td><span data-ttu-id="fe854-917">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-917">10001</span></span></td>
<td><span data-ttu-id="fe854-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-918">Electricity</span></span></td>
<td><span data-ttu-id="fe854-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-919">Fixed cost</span></span></td>
<td><span data-ttu-id="fe854-920">45.20</span><span class="sxs-lookup"><span data-stu-id="fe854-920">45.20</span></span></td>
<td><span data-ttu-id="fe854-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-922">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-922">CC003</span></span></td>
<td><span data-ttu-id="fe854-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="fe854-923">Assembly</span></span></td>
<td><span data-ttu-id="fe854-924">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-924">10001</span></span></td>
<td><span data-ttu-id="fe854-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-925">Electricity</span></span></td>
<td><span data-ttu-id="fe854-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-926">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="fe854-927">-2,977.17</span></span></td>
<td><span data-ttu-id="fe854-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-929">Prod 1</span></span></td>
<td><span data-ttu-id="fe854-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="fe854-930">Product 1</span></span></td>
<td><span data-ttu-id="fe854-931">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-931">10001</span></span></td>
<td><span data-ttu-id="fe854-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-932">Electricity</span></span></td>
<td><span data-ttu-id="fe854-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-933">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="fe854-934">2,507.09</span></span></td>
<td><span data-ttu-id="fe854-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fe854-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-936">Prod 2</span></span></td>
<td><span data-ttu-id="fe854-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="fe854-937">Product 2</span></span></td>
<td><span data-ttu-id="fe854-938">10001</span><span class="sxs-lookup"><span data-stu-id="fe854-938">10001</span></span></td>
<td><span data-ttu-id="fe854-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="fe854-939">Electricity</span></span></td>
<td><span data-ttu-id="fe854-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-940">Variable cost</span></span></td>
<td><span data-ttu-id="fe854-941">470.08</span><span class="sxs-lookup"><span data-stu-id="fe854-941">470.08</span></span></td>
<td><span data-ttu-id="fe854-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="fe854-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="fe854-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="fe854-943">Conclusion</span></span>
<span data-ttu-id="fe854-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="fe854-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="fe854-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="fe854-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="fe854-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="fe854-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="fe854-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="fe854-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="fe854-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="fe854-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="fe854-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="fe854-950">Razem</span><span class="sxs-lookup"><span data-stu-id="fe854-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="fe854-951">CC099</span><span class="sxs-lookup"><span data-stu-id="fe854-951">CC099</span></span></th>
<th><span data-ttu-id="fe854-952">CC001</span><span class="sxs-lookup"><span data-stu-id="fe854-952">CC001</span></span></th>
<th><span data-ttu-id="fe854-953">CC002</span><span class="sxs-lookup"><span data-stu-id="fe854-953">CC002</span></span></th>
<th><span data-ttu-id="fe854-954">CC003</span><span class="sxs-lookup"><span data-stu-id="fe854-954">CC003</span></span></th>
<th><span data-ttu-id="fe854-955">CC004</span><span class="sxs-lookup"><span data-stu-id="fe854-955">CC004</span></span></th>
<th><span data-ttu-id="fe854-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fe854-956">Proj 1</span></span></th>
<th><span data-ttu-id="fe854-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fe854-957">Proj 2</span></span></th>
<th><span data-ttu-id="fe854-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fe854-958">Prod 1</span></span></th>
<th><span data-ttu-id="fe854-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fe854-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="fe854-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="fe854-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="fe854-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="fe854-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="fe854-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-971">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="fe854-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="fe854-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-973">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-974">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-975">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-976">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-977">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="fe854-978">776.36</span><span class="sxs-lookup"><span data-stu-id="fe854-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-979">223.64</span><span class="sxs-lookup"><span data-stu-id="fe854-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="fe854-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="fe854-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-982">000</span><span class="sxs-lookup"><span data-stu-id="fe854-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-983">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-984">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-985">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-986">0,00</span><span class="sxs-lookup"><span data-stu-id="fe854-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-987">30.00</span><span class="sxs-lookup"><span data-stu-id="fe854-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-988">10,00</span><span class="sxs-lookup"><span data-stu-id="fe854-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="fe854-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="fe854-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fe854-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="fe854-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="fe854-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="fe854-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="fe854-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="fe854-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="fe854-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="fe854-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="fe854-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="fe854-996">Aby uzyskać więcej informacji, [Zasady akumulacji kosztów i obliczanie narzutu](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="fe854-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]