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
ms.openlocfilehash: 8dc312e66dc666ac6c23bac6b705ffc7893fd06b
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188004"
---
# <a name="overhead-calculation"></a><span data-ttu-id="de2ba-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="de2ba-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de2ba-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="de2ba-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

## <a name="term-definition"></a><span data-ttu-id="de2ba-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="de2ba-105">Term definition</span></span>

<span data-ttu-id="de2ba-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="de2ba-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="de2ba-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="de2ba-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="de2ba-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="de2ba-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="de2ba-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="de2ba-109">Rent</span></span>
-   <span data-ttu-id="de2ba-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-110">Electricity</span></span>
-   <span data-ttu-id="de2ba-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="de2ba-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="de2ba-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="de2ba-112">Overhead calculation overview</span></span>
<span data-ttu-id="de2ba-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="de2ba-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="de2ba-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="de2ba-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="de2ba-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="de2ba-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="de2ba-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="de2ba-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="de2ba-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="de2ba-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="de2ba-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="de2ba-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="de2ba-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="de2ba-119">Version type</span></span>
-   <span data-ttu-id="de2ba-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="de2ba-120">Date and time</span></span>
-   <span data-ttu-id="de2ba-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="de2ba-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="de2ba-122">Fiscal year</span></span>
-   <span data-ttu-id="de2ba-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="de2ba-123">Fiscal period</span></span>

<span data-ttu-id="de2ba-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="de2ba-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="de2ba-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="de2ba-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="de2ba-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="de2ba-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="de2ba-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="de2ba-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="de2ba-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="de2ba-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="de2ba-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="de2ba-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="de2ba-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="de2ba-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="de2ba-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="de2ba-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="de2ba-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="de2ba-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="de2ba-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="de2ba-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="de2ba-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="de2ba-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="de2ba-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="de2ba-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="de2ba-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="de2ba-140">Main account</span></span></th>
<th><span data-ttu-id="de2ba-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="de2ba-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="de2ba-143">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-143">CC099</span></span></td>
<td><span data-ttu-id="de2ba-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-144">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-145">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-145">10001</span></span></td>
<td><span data-ttu-id="de2ba-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-146">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="de2ba-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="de2ba-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="de2ba-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="de2ba-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="de2ba-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-151">Define the cost behavior rule</span></span>

<span data-ttu-id="de2ba-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="de2ba-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="de2ba-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="de2ba-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="de2ba-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="de2ba-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="de2ba-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="de2ba-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="de2ba-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="de2ba-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="de2ba-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="de2ba-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="de2ba-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="de2ba-160">Journal</span></span></th>
<th><span data-ttu-id="de2ba-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="de2ba-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="de2ba-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="de2ba-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="de2ba-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="de2ba-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-164">00001</span><span class="sxs-lookup"><span data-stu-id="de2ba-164">00001</span></span></td>
<td><span data-ttu-id="de2ba-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="de2ba-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="de2ba-166">Fiscal</span></span></td>
<td><span data-ttu-id="de2ba-167">2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-167">2017</span></span></td>
<td><span data-ttu-id="de2ba-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-168">Period 1</span></span></td>
<td><span data-ttu-id="de2ba-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="de2ba-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="de2ba-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="de2ba-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="de2ba-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-173">Cost element</span></span></th>
<th><span data-ttu-id="de2ba-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-174">Cost behavior</span></span></th>
<th><span data-ttu-id="de2ba-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="de2ba-177">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-177">CC099</span></span></td>
<td><span data-ttu-id="de2ba-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-178">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-179">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-179">10001</span></span></td>
<td><span data-ttu-id="de2ba-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-180">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="de2ba-181">Unclassified</span></span></td>
<td><span data-ttu-id="de2ba-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="de2ba-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-185">Cost element</span></span></th>
<th><span data-ttu-id="de2ba-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-186">Cost behavior</span></span></th>
<th><span data-ttu-id="de2ba-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-187">Amount</span></span></th>
<th><span data-ttu-id="de2ba-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="de2ba-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-189">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-189">CC099</span></span></td>
<td><span data-ttu-id="de2ba-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-190">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-191">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-191">10001</span></span></td>
<td><span data-ttu-id="de2ba-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-192">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="de2ba-193">Unclassified</span></span></td>
<td><span data-ttu-id="de2ba-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-194">10,000.00</span></span></td>
<td><span data-ttu-id="de2ba-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-196">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-196">CC099</span></span></td>
<td><span data-ttu-id="de2ba-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-197">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-198">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-198">10001</span></span></td>
<td><span data-ttu-id="de2ba-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-199">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="de2ba-200">Unclassified</span></span></td>
<td><span data-ttu-id="de2ba-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-201">-10,000.00</span></span></td>
<td><span data-ttu-id="de2ba-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-203">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-203">CC099</span></span></td>
<td><span data-ttu-id="de2ba-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-204">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-205">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-205">10001</span></span></td>
<td><span data-ttu-id="de2ba-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-206">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-207">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-208">1,000.00</span></span></td>
<td><span data-ttu-id="de2ba-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-210">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-210">CC099</span></span></td>
<td><span data-ttu-id="de2ba-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-211">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-212">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-212">10001</span></span></td>
<td><span data-ttu-id="de2ba-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-213">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-214">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-215">9,000.00</span></span></td>
<td><span data-ttu-id="de2ba-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="de2ba-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="de2ba-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="de2ba-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="de2ba-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="de2ba-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="de2ba-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-221">Define the cost distribution rule</span></span>

<span data-ttu-id="de2ba-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="de2ba-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="de2ba-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="de2ba-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="de2ba-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="de2ba-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="de2ba-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="de2ba-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="de2ba-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="de2ba-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="de2ba-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-228">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-229">kWh</span><span class="sxs-lookup"><span data-stu-id="de2ba-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-230">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-230">CC001</span></span></td>
<td><span data-ttu-id="de2ba-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-231">HR</span></span></td>
<td><span data-ttu-id="de2ba-232">1 000</span><span class="sxs-lookup"><span data-stu-id="de2ba-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-233">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-233">CC002</span></span></td>
<td><span data-ttu-id="de2ba-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-234">Finance</span></span></td>
<td><span data-ttu-id="de2ba-235">6,000</span><span class="sxs-lookup"><span data-stu-id="de2ba-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-236">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-236">CC003</span></span></td>
<td><span data-ttu-id="de2ba-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-237">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-238">0</span><span class="sxs-lookup"><span data-stu-id="de2ba-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="de2ba-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-240">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="de2ba-241">Magnitude</span></span></th>
<th><span data-ttu-id="de2ba-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="de2ba-242">Allocation factor</span></span></th>
<th><span data-ttu-id="de2ba-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-244">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-244">CC001</span></span></td>
<td><span data-ttu-id="de2ba-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-245">HR</span></span></td>
<td><span data-ttu-id="de2ba-246">1 000</span><span class="sxs-lookup"><span data-stu-id="de2ba-246">1,000</span></span></td>
<td><span data-ttu-id="de2ba-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="de2ba-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="de2ba-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-249">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-249">CC002</span></span></td>
<td><span data-ttu-id="de2ba-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-250">Finance</span></span></td>
<td><span data-ttu-id="de2ba-251">6,000</span><span class="sxs-lookup"><span data-stu-id="de2ba-251">6,000</span></span></td>
<td><span data-ttu-id="de2ba-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="de2ba-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="de2ba-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-254">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-254">CC003</span></span></td>
<td><span data-ttu-id="de2ba-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-255">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-256">0</span><span class="sxs-lookup"><span data-stu-id="de2ba-256">0</span></span></td>
<td><span data-ttu-id="de2ba-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="de2ba-258">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="de2ba-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="de2ba-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="de2ba-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-261">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="de2ba-262">Formula</span></span></th>
<th><span data-ttu-id="de2ba-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="de2ba-263">Magnitude</span></span></th>
<th><span data-ttu-id="de2ba-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="de2ba-264">Allocation factor</span></span></th>
<th><span data-ttu-id="de2ba-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-266">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-266">CC001</span></span></td>
<td><span data-ttu-id="de2ba-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-267">HR</span></span></td>
<td><span data-ttu-id="de2ba-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="de2ba-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="de2ba-269">1</span><span class="sxs-lookup"><span data-stu-id="de2ba-269">1</span></span></td>
<td><span data-ttu-id="de2ba-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="de2ba-271">500.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-272">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-272">CC002</span></span></td>
<td><span data-ttu-id="de2ba-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-273">Finance</span></span></td>
<td><span data-ttu-id="de2ba-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="de2ba-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="de2ba-275">1</span><span class="sxs-lookup"><span data-stu-id="de2ba-275">1</span></span></td>
<td><span data-ttu-id="de2ba-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="de2ba-277">500.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-278">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-278">CC003</span></span></td>
<td><span data-ttu-id="de2ba-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-279">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="de2ba-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="de2ba-281">0</span><span class="sxs-lookup"><span data-stu-id="de2ba-281">0</span></span></td>
<td><span data-ttu-id="de2ba-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="de2ba-283">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="de2ba-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="de2ba-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="de2ba-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="de2ba-285">Journal</span></span></th>
<th><span data-ttu-id="de2ba-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="de2ba-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="de2ba-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="de2ba-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="de2ba-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="de2ba-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-289">00002</span><span class="sxs-lookup"><span data-stu-id="de2ba-289">00002</span></span></td>
<td><span data-ttu-id="de2ba-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="de2ba-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="de2ba-291">Fiscal</span></span></td>
<td><span data-ttu-id="de2ba-292">2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-292">2017</span></span></td>
<td><span data-ttu-id="de2ba-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-293">Period 1</span></span></td>
<td><span data-ttu-id="de2ba-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="de2ba-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="de2ba-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="de2ba-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="de2ba-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-298">Cost element</span></span></th>
<th><span data-ttu-id="de2ba-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-299">Cost behavior</span></span></th>
<th><span data-ttu-id="de2ba-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-302">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-302">CC099</span></span></td>
<td><span data-ttu-id="de2ba-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-303">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-304">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-304">10001</span></span></td>
<td><span data-ttu-id="de2ba-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-305">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-306">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-309">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-309">CC099</span></span></td>
<td><span data-ttu-id="de2ba-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-310">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-311">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-311">10001</span></span></td>
<td><span data-ttu-id="de2ba-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-312">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-313">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="de2ba-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-317">Cost element</span></span></th>
<th><span data-ttu-id="de2ba-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-318">Cost behavior</span></span></th>
<th><span data-ttu-id="de2ba-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-319">Amount</span></span></th>
<th><span data-ttu-id="de2ba-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="de2ba-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-321">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-321">CC099</span></span></td>
<td><span data-ttu-id="de2ba-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-322">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-323">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-323">10001</span></span></td>
<td><span data-ttu-id="de2ba-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-324">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-325">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-326">-1,000.00</span></span></td>
<td><span data-ttu-id="de2ba-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-328">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-328">CC001</span></span></td>
<td><span data-ttu-id="de2ba-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-329">HR</span></span></td>
<td><span data-ttu-id="de2ba-330">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-330">10001</span></span></td>
<td><span data-ttu-id="de2ba-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-331">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-332">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-333">500.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-333">500.00</span></span></td>
<td><span data-ttu-id="de2ba-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-335">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-335">CC002</span></span></td>
<td><span data-ttu-id="de2ba-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-336">Finance</span></span></td>
<td><span data-ttu-id="de2ba-337">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-337">10001</span></span></td>
<td><span data-ttu-id="de2ba-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-338">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-339">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-340">500.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-340">500.00</span></span></td>
<td><span data-ttu-id="de2ba-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-342">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-342">CC099</span></span></td>
<td><span data-ttu-id="de2ba-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-343">Default cost center</span></span></td>
<td><span data-ttu-id="de2ba-344">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-344">10001</span></span></td>
<td><span data-ttu-id="de2ba-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-345">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-346">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-347">-9,000.00</span></span></td>
<td><span data-ttu-id="de2ba-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-349">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-349">CC001</span></span></td>
<td><span data-ttu-id="de2ba-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-350">HR</span></span></td>
<td><span data-ttu-id="de2ba-351">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-351">10001</span></span></td>
<td><span data-ttu-id="de2ba-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-352">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-353">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="de2ba-354">1,285.71</span></span></td>
<td><span data-ttu-id="de2ba-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-356">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-356">CC002</span></span></td>
<td><span data-ttu-id="de2ba-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-357">Finance</span></span></td>
<td><span data-ttu-id="de2ba-358">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-358">10001</span></span></td>
<td><span data-ttu-id="de2ba-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-359">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-360">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="de2ba-361">7,714.29</span></span></td>
<td><span data-ttu-id="de2ba-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="de2ba-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="de2ba-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="de2ba-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="de2ba-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="de2ba-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="de2ba-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="de2ba-367">Define the overhead rate</span></span>

<span data-ttu-id="de2ba-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="de2ba-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="de2ba-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="de2ba-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-370">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="de2ba-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-372">Proj 1</span></span></td>
<td><span data-ttu-id="de2ba-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-373">Project 1</span></span></td>
<td><span data-ttu-id="de2ba-374">3</span><span class="sxs-lookup"><span data-stu-id="de2ba-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-375">Proj 2</span></span></td>
<td><span data-ttu-id="de2ba-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-376">Project 2</span></span></td>
<td><span data-ttu-id="de2ba-377">1</span><span class="sxs-lookup"><span data-stu-id="de2ba-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="de2ba-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-379">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-380">Cost element</span></span></th>
<th><span data-ttu-id="de2ba-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-381">Cost behavior</span></span></th>
<th><span data-ttu-id="de2ba-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="de2ba-382">Units</span></span></th>
<th><span data-ttu-id="de2ba-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="de2ba-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-384">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-384">CC001</span></span></td>
<td><span data-ttu-id="de2ba-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-385">HR</span></span></td>
<td><span data-ttu-id="de2ba-386">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-386">10001</span></span></td>
<td><span data-ttu-id="de2ba-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-387">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-388">1</span><span class="sxs-lookup"><span data-stu-id="de2ba-388">1</span></span></td>
<td><span data-ttu-id="de2ba-389">10</span><span class="sxs-lookup"><span data-stu-id="de2ba-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-391">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="de2ba-392">Magnitude</span></span></th>
<th><span data-ttu-id="de2ba-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-393">Cost element</span></span></th>
<th><span data-ttu-id="de2ba-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="de2ba-394">Allocation factor</span></span></th>
<th><span data-ttu-id="de2ba-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-396">Proj 1</span></span></td>
<td><span data-ttu-id="de2ba-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-397">Project 1</span></span></td>
<td><span data-ttu-id="de2ba-398">3</span><span class="sxs-lookup"><span data-stu-id="de2ba-398">3</span></span></td>
<td><span data-ttu-id="de2ba-399">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-399">10001</span></span></td>
<td><span data-ttu-id="de2ba-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="de2ba-401">30.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-402">Proj 2</span></span></td>
<td><span data-ttu-id="de2ba-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-403">Project 2</span></span></td>
<td><span data-ttu-id="de2ba-404">1</span><span class="sxs-lookup"><span data-stu-id="de2ba-404">1</span></span></td>
<td><span data-ttu-id="de2ba-405">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-405">10001</span></span></td>
<td><span data-ttu-id="de2ba-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="de2ba-407">10,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="de2ba-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="de2ba-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="de2ba-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="de2ba-409">Journal</span></span></th>
<th><span data-ttu-id="de2ba-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="de2ba-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="de2ba-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="de2ba-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="de2ba-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="de2ba-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-413">00003</span><span class="sxs-lookup"><span data-stu-id="de2ba-413">00003</span></span></td>
<td><span data-ttu-id="de2ba-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="de2ba-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="de2ba-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="de2ba-415">Fiscal</span></span></td>
<td><span data-ttu-id="de2ba-416">2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-416">2017</span></span></td>
<td><span data-ttu-id="de2ba-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-417">Period 1</span></span></td>
<td><span data-ttu-id="de2ba-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="de2ba-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="de2ba-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="de2ba-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="de2ba-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-421">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="de2ba-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-424">Proj 1</span></span></td>
<td><span data-ttu-id="de2ba-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="de2ba-426">3,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-428">Proj 2</span></span></td>
<td><span data-ttu-id="de2ba-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="de2ba-430">1.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="de2ba-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-433">Cost element</span></span></th>
<th><span data-ttu-id="de2ba-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-434">Cost behavior</span></span></th>
<th><span data-ttu-id="de2ba-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-435">Amount</span></span></th>
<th><span data-ttu-id="de2ba-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="de2ba-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="de2ba-437">CC0001</span></span></td>
<td><span data-ttu-id="de2ba-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-438">HR</span></span></td>
<td><span data-ttu-id="de2ba-439">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-439">10001</span></span></td>
<td><span data-ttu-id="de2ba-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-440">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-441">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-442">-30.00</span></span></td>
<td><span data-ttu-id="de2ba-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-444">Proj 1</span></span></td>
<td><span data-ttu-id="de2ba-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="de2ba-446">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-446">10001</span></span></td>
<td><span data-ttu-id="de2ba-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-447">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-448">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-449">30.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-449">30.00</span></span></td>
<td><span data-ttu-id="de2ba-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-451">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-451">CC001</span></span></td>
<td><span data-ttu-id="de2ba-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-452">HR</span></span></td>
<td><span data-ttu-id="de2ba-453">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-453">10001</span></span></td>
<td><span data-ttu-id="de2ba-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-454">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-455">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-456">-10.00</span></span></td>
<td><span data-ttu-id="de2ba-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-458">Proj 2</span></span></td>
<td><span data-ttu-id="de2ba-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="de2ba-460">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-460">10001</span></span></td>
<td><span data-ttu-id="de2ba-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-461">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-462">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-463">10,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-463">10.00</span></span></td>
<td><span data-ttu-id="de2ba-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="de2ba-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="de2ba-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="de2ba-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="de2ba-468">Aplikacja Finance obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="de2ba-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="de2ba-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="de2ba-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="de2ba-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="de2ba-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="de2ba-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="de2ba-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="de2ba-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="de2ba-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="de2ba-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-475">Define the cost allocation</span></span>

<span data-ttu-id="de2ba-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="de2ba-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="de2ba-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="de2ba-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-479">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="de2ba-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-481">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-481">CC002</span></span></td>
<td><span data-ttu-id="de2ba-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-482">Finance</span></span></td>
<td><span data-ttu-id="de2ba-483">35</span><span class="sxs-lookup"><span data-stu-id="de2ba-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-484">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-484">CC003</span></span></td>
<td><span data-ttu-id="de2ba-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-485">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-486">55</span><span class="sxs-lookup"><span data-stu-id="de2ba-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-487">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-487">CC004</span></span></td>
<td><span data-ttu-id="de2ba-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-488">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-489">10</span><span class="sxs-lookup"><span data-stu-id="de2ba-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="de2ba-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="de2ba-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-492">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="de2ba-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-494">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-494">CC003</span></span></td>
<td><span data-ttu-id="de2ba-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-495">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-496">65</span><span class="sxs-lookup"><span data-stu-id="de2ba-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-497">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-497">CC004</span></span></td>
<td><span data-ttu-id="de2ba-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-498">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-499">35</span><span class="sxs-lookup"><span data-stu-id="de2ba-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="de2ba-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="de2ba-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-502">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="de2ba-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-504">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-505">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-506">60</span><span class="sxs-lookup"><span data-stu-id="de2ba-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-507">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-508">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-509">20</span><span class="sxs-lookup"><span data-stu-id="de2ba-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="de2ba-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="de2ba-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-512">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="de2ba-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-514">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-515">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-516">80</span><span class="sxs-lookup"><span data-stu-id="de2ba-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-517">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-518">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-519">15</span><span class="sxs-lookup"><span data-stu-id="de2ba-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="de2ba-520">Miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="de2ba-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="de2ba-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="de2ba-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="de2ba-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="de2ba-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-523">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="de2ba-524">Magnitude</span></span></th>
<th><span data-ttu-id="de2ba-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="de2ba-525">Allocation factor</span></span></th>
<th><span data-ttu-id="de2ba-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-526">Amount</span></span></th>
<th><span data-ttu-id="de2ba-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-528">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-528">CC002</span></span></td>
<td><span data-ttu-id="de2ba-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-529">Finance</span></span></td>
<td><span data-ttu-id="de2ba-530">35</span><span class="sxs-lookup"><span data-stu-id="de2ba-530">35</span></span></td>
<td><span data-ttu-id="de2ba-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="de2ba-532">175.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-532">175.00</span></span></td>
<td><span data-ttu-id="de2ba-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-534">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-534">CC003</span></span></td>
<td><span data-ttu-id="de2ba-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-535">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-536">55</span><span class="sxs-lookup"><span data-stu-id="de2ba-536">55</span></span></td>
<td><span data-ttu-id="de2ba-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="de2ba-538">275.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-538">275.00</span></span></td>
<td><span data-ttu-id="de2ba-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-540">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-540">CC004</span></span></td>
<td><span data-ttu-id="de2ba-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-541">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-542">10</span><span class="sxs-lookup"><span data-stu-id="de2ba-542">10</span></span></td>
<td><span data-ttu-id="de2ba-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="de2ba-544">50,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-544">50.00</span></span></td>
<td><span data-ttu-id="de2ba-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-546">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-546">CC002</span></span></td>
<td><span data-ttu-id="de2ba-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-547">Finance</span></span></td>
<td><span data-ttu-id="de2ba-548">35</span><span class="sxs-lookup"><span data-stu-id="de2ba-548">35</span></span></td>
<td><span data-ttu-id="de2ba-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="de2ba-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="de2ba-550">436.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-550">436.00</span></span></td>
<td><span data-ttu-id="de2ba-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-552">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-552">CC003</span></span></td>
<td><span data-ttu-id="de2ba-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-553">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-554">55</span><span class="sxs-lookup"><span data-stu-id="de2ba-554">55</span></span></td>
<td><span data-ttu-id="de2ba-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="de2ba-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="de2ba-556">685.14</span><span class="sxs-lookup"><span data-stu-id="de2ba-556">685.14</span></span></td>
<td><span data-ttu-id="de2ba-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-558">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-558">CC004</span></span></td>
<td><span data-ttu-id="de2ba-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-559">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-560">10</span><span class="sxs-lookup"><span data-stu-id="de2ba-560">10</span></span></td>
<td><span data-ttu-id="de2ba-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="de2ba-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="de2ba-562">124.57</span><span class="sxs-lookup"><span data-stu-id="de2ba-562">124.57</span></span></td>
<td><span data-ttu-id="de2ba-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="de2ba-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-565">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="de2ba-566">Magnitude</span></span></th>
<th><span data-ttu-id="de2ba-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="de2ba-567">Allocation factor</span></span></th>
<th><span data-ttu-id="de2ba-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-568">Amount</span></span></th>
<th><span data-ttu-id="de2ba-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-570">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-570">CC003</span></span></td>
<td><span data-ttu-id="de2ba-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-571">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-572">65</span><span class="sxs-lookup"><span data-stu-id="de2ba-572">65</span></span></td>
<td><span data-ttu-id="de2ba-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="de2ba-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="de2ba-574">438.75</span><span class="sxs-lookup"><span data-stu-id="de2ba-574">438.75</span></span></td>
<td><span data-ttu-id="de2ba-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-576">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-576">CC004</span></span></td>
<td><span data-ttu-id="de2ba-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-577">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-578">35</span><span class="sxs-lookup"><span data-stu-id="de2ba-578">35</span></span></td>
<td><span data-ttu-id="de2ba-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="de2ba-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="de2ba-580">236.25</span><span class="sxs-lookup"><span data-stu-id="de2ba-580">236.25</span></span></td>
<td><span data-ttu-id="de2ba-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-582">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-582">CC003</span></span></td>
<td><span data-ttu-id="de2ba-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-583">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-584">65</span><span class="sxs-lookup"><span data-stu-id="de2ba-584">65</span></span></td>
<td><span data-ttu-id="de2ba-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="de2ba-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="de2ba-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="de2ba-586">5,297.69</span></span></td>
<td><span data-ttu-id="de2ba-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-588">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-588">CC004</span></span></td>
<td><span data-ttu-id="de2ba-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-589">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-590">35</span><span class="sxs-lookup"><span data-stu-id="de2ba-590">35</span></span></td>
<td><span data-ttu-id="de2ba-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="de2ba-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="de2ba-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="de2ba-592">2,852.60</span></span></td>
<td><span data-ttu-id="de2ba-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="de2ba-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-595">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="de2ba-596">Magnitude</span></span></th>
<th><span data-ttu-id="de2ba-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="de2ba-597">Allocation factor</span></span></th>
<th><span data-ttu-id="de2ba-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-598">Amount</span></span></th>
<th><span data-ttu-id="de2ba-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-600">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-601">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-602">60</span><span class="sxs-lookup"><span data-stu-id="de2ba-602">60</span></span></td>
<td><span data-ttu-id="de2ba-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="de2ba-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="de2ba-604">535.31</span><span class="sxs-lookup"><span data-stu-id="de2ba-604">535.31</span></span></td>
<td><span data-ttu-id="de2ba-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-606">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-607">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-608">20</span><span class="sxs-lookup"><span data-stu-id="de2ba-608">20</span></span></td>
<td><span data-ttu-id="de2ba-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="de2ba-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="de2ba-610">178.44</span><span class="sxs-lookup"><span data-stu-id="de2ba-610">178.44</span></span></td>
<td><span data-ttu-id="de2ba-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-612">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-613">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-614">60</span><span class="sxs-lookup"><span data-stu-id="de2ba-614">60</span></span></td>
<td><span data-ttu-id="de2ba-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="de2ba-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="de2ba-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="de2ba-616">4,487.12</span></span></td>
<td><span data-ttu-id="de2ba-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-618">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-619">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-620">20</span><span class="sxs-lookup"><span data-stu-id="de2ba-620">20</span></span></td>
<td><span data-ttu-id="de2ba-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="de2ba-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="de2ba-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="de2ba-622">1,495.71</span></span></td>
<td><span data-ttu-id="de2ba-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de2ba-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="de2ba-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-625">Cost object</span></span></th>
<th><span data-ttu-id="de2ba-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="de2ba-626">Magnitude</span></span></th>
<th><span data-ttu-id="de2ba-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="de2ba-627">Allocation factor</span></span></th>
<th><span data-ttu-id="de2ba-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-628">Amount</span></span></th>
<th><span data-ttu-id="de2ba-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-630">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-631">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-632">80</span><span class="sxs-lookup"><span data-stu-id="de2ba-632">80</span></span></td>
<td><span data-ttu-id="de2ba-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="de2ba-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="de2ba-634">241.05</span><span class="sxs-lookup"><span data-stu-id="de2ba-634">241.05</span></span></td>
<td><span data-ttu-id="de2ba-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-636">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-637">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-638">15</span><span class="sxs-lookup"><span data-stu-id="de2ba-638">15</span></span></td>
<td><span data-ttu-id="de2ba-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="de2ba-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="de2ba-640">45.20</span><span class="sxs-lookup"><span data-stu-id="de2ba-640">45.20</span></span></td>
<td><span data-ttu-id="de2ba-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-642">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-643">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-644">80</span><span class="sxs-lookup"><span data-stu-id="de2ba-644">80</span></span></td>
<td><span data-ttu-id="de2ba-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="de2ba-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="de2ba-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="de2ba-646">2,507.09</span></span></td>
<td><span data-ttu-id="de2ba-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-648">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-649">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-650">15</span><span class="sxs-lookup"><span data-stu-id="de2ba-650">15</span></span></td>
<td><span data-ttu-id="de2ba-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="de2ba-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="de2ba-652">470.08</span><span class="sxs-lookup"><span data-stu-id="de2ba-652">470.08</span></span></td>
<td><span data-ttu-id="de2ba-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="de2ba-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="de2ba-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="de2ba-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="de2ba-655">Journal</span></span></th>
<th><span data-ttu-id="de2ba-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="de2ba-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="de2ba-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="de2ba-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="de2ba-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="de2ba-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-659">00004</span><span class="sxs-lookup"><span data-stu-id="de2ba-659">00004</span></span></td>
<td><span data-ttu-id="de2ba-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="de2ba-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="de2ba-661">Fiscal</span></span></td>
<td><span data-ttu-id="de2ba-662">2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-662">2017</span></span></td>
<td><span data-ttu-id="de2ba-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-663">Period 1</span></span></td>
<td><span data-ttu-id="de2ba-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="de2ba-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="de2ba-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="de2ba-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="de2ba-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-668">Cost element</span></span></th>
<th><span data-ttu-id="de2ba-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-669">Cost behavior</span></span></th>
<th><span data-ttu-id="de2ba-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-672">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-672">CC001</span></span></td>
<td><span data-ttu-id="de2ba-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-673">HR</span></span></td>
<td><span data-ttu-id="de2ba-674">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-674">10001</span></span></td>
<td><span data-ttu-id="de2ba-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-675">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-676">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-677">500.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-679">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-679">CC001</span></span></td>
<td><span data-ttu-id="de2ba-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-680">HR</span></span></td>
<td><span data-ttu-id="de2ba-681">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-681">10001</span></span></td>
<td><span data-ttu-id="de2ba-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-682">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-683">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="de2ba-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-686">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-686">CC002</span></span></td>
<td><span data-ttu-id="de2ba-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-687">Finance</span></span></td>
<td><span data-ttu-id="de2ba-688">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-688">10001</span></span></td>
<td><span data-ttu-id="de2ba-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-689">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-690">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-691">675.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-693">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-693">CC002</span></span></td>
<td><span data-ttu-id="de2ba-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-694">Finance</span></span></td>
<td><span data-ttu-id="de2ba-695">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-695">10001</span></span></td>
<td><span data-ttu-id="de2ba-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-696">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-697">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="de2ba-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-700">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-700">CC003</span></span></td>
<td><span data-ttu-id="de2ba-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-701">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-702">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-702">10001</span></span></td>
<td><span data-ttu-id="de2ba-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-703">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-704">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-705">713.75</span><span class="sxs-lookup"><span data-stu-id="de2ba-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-707">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-707">CC003</span></span></td>
<td><span data-ttu-id="de2ba-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-708">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-709">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-709">10001</span></span></td>
<td><span data-ttu-id="de2ba-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-710">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-711">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="de2ba-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-714">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-714">CC003</span></span></td>
<td><span data-ttu-id="de2ba-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-715">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-716">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-716">10001</span></span></td>
<td><span data-ttu-id="de2ba-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-717">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-718">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-719">286.25</span><span class="sxs-lookup"><span data-stu-id="de2ba-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-721">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-721">CC003</span></span></td>
<td><span data-ttu-id="de2ba-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-722">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-723">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-723">10001</span></span></td>
<td><span data-ttu-id="de2ba-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-724">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-725">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="de2ba-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-728">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-729">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-730">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-730">10001</span></span></td>
<td><span data-ttu-id="de2ba-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-731">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-732">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-733">776.36</span><span class="sxs-lookup"><span data-stu-id="de2ba-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-735">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-736">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-737">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-737">10001</span></span></td>
<td><span data-ttu-id="de2ba-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-738">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-739">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="de2ba-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-742">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-743">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-744">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-744">10001</span></span></td>
<td><span data-ttu-id="de2ba-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-745">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-746">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-747">223.64</span><span class="sxs-lookup"><span data-stu-id="de2ba-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="de2ba-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-749">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-750">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-751">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-751">10001</span></span></td>
<td><span data-ttu-id="de2ba-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-752">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-753">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="de2ba-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="de2ba-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="de2ba-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="de2ba-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-757">Cost element</span></span></th>
<th><span data-ttu-id="de2ba-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-758">Cost behavior</span></span></th>
<th><span data-ttu-id="de2ba-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="de2ba-759">Amount</span></span></th>
<th><span data-ttu-id="de2ba-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="de2ba-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="de2ba-761">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-761">CC001</span></span></td>
<td><span data-ttu-id="de2ba-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-762">HR</span></span></td>
<td><span data-ttu-id="de2ba-763">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-763">10001</span></span></td>
<td><span data-ttu-id="de2ba-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-764">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-765">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-766">-500.00</span></span></td>
<td><span data-ttu-id="de2ba-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-768">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-768">CC002</span></span></td>
<td><span data-ttu-id="de2ba-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-769">Finance</span></span></td>
<td><span data-ttu-id="de2ba-770">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-770">10001</span></span></td>
<td><span data-ttu-id="de2ba-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-771">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-772">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-773">175.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-773">175.00</span></span></td>
<td><span data-ttu-id="de2ba-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-775">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-775">CC003</span></span></td>
<td><span data-ttu-id="de2ba-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-776">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-777">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-777">10001</span></span></td>
<td><span data-ttu-id="de2ba-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-778">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-779">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-780">275.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-780">275.00</span></span></td>
<td><span data-ttu-id="de2ba-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-782">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-782">CC004</span></span></td>
<td><span data-ttu-id="de2ba-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-783">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-784">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-784">10001</span></span></td>
<td><span data-ttu-id="de2ba-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-785">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-786">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-787">50,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-787">50,00</span></span></td>
<td><span data-ttu-id="de2ba-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-789">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-789">CC001</span></span></td>
<td><span data-ttu-id="de2ba-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="de2ba-790">HR</span></span></td>
<td><span data-ttu-id="de2ba-791">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-791">10001</span></span></td>
<td><span data-ttu-id="de2ba-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-792">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-793">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="de2ba-794">-1,245.71</span></span></td>
<td><span data-ttu-id="de2ba-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-796">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-796">CC002</span></span></td>
<td><span data-ttu-id="de2ba-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-797">Finance</span></span></td>
<td><span data-ttu-id="de2ba-798">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-798">10001</span></span></td>
<td><span data-ttu-id="de2ba-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-799">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-800">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-801">436.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-801">436.00</span></span></td>
<td><span data-ttu-id="de2ba-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-803">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-803">CC003</span></span></td>
<td><span data-ttu-id="de2ba-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-804">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-805">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-805">10001</span></span></td>
<td><span data-ttu-id="de2ba-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-806">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-807">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-808">685.14</span><span class="sxs-lookup"><span data-stu-id="de2ba-808">685.14</span></span></td>
<td><span data-ttu-id="de2ba-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-810">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-810">CC004</span></span></td>
<td><span data-ttu-id="de2ba-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-811">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-812">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-812">10001</span></span></td>
<td><span data-ttu-id="de2ba-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-813">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-814">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-815">124.57</span><span class="sxs-lookup"><span data-stu-id="de2ba-815">124.57</span></span></td>
<td><span data-ttu-id="de2ba-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-817">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-817">CC002</span></span></td>
<td><span data-ttu-id="de2ba-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-818">Finance</span></span></td>
<td><span data-ttu-id="de2ba-819">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-819">10001</span></span></td>
<td><span data-ttu-id="de2ba-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-820">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-821">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-822">-675.00</span></span></td>
<td><span data-ttu-id="de2ba-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-824">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-824">CC003</span></span></td>
<td><span data-ttu-id="de2ba-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-825">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-826">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-826">10001</span></span></td>
<td><span data-ttu-id="de2ba-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-827">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-828">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-829">438.75</span><span class="sxs-lookup"><span data-stu-id="de2ba-829">438.75</span></span></td>
<td><span data-ttu-id="de2ba-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-831">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-831">CC004</span></span></td>
<td><span data-ttu-id="de2ba-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-832">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-833">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-833">10001</span></span></td>
<td><span data-ttu-id="de2ba-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-834">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-835">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-836">236.25</span><span class="sxs-lookup"><span data-stu-id="de2ba-836">236.25</span></span></td>
<td><span data-ttu-id="de2ba-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-838">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-838">CC002</span></span></td>
<td><span data-ttu-id="de2ba-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="de2ba-839">Finance</span></span></td>
<td><span data-ttu-id="de2ba-840">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-840">10001</span></span></td>
<td><span data-ttu-id="de2ba-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-841">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-842">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="de2ba-843">-8,150.29</span></span></td>
<td><span data-ttu-id="de2ba-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-845">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-845">CC003</span></span></td>
<td><span data-ttu-id="de2ba-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-846">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-847">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-847">10001</span></span></td>
<td><span data-ttu-id="de2ba-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-848">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-849">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="de2ba-850">5,297.69</span></span></td>
<td><span data-ttu-id="de2ba-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-852">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-852">CC004</span></span></td>
<td><span data-ttu-id="de2ba-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="de2ba-853">Packaging</span></span></td>
<td><span data-ttu-id="de2ba-854">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-854">10001</span></span></td>
<td><span data-ttu-id="de2ba-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-855">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-856">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="de2ba-857">2,852.60</span></span></td>
<td><span data-ttu-id="de2ba-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-859">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-859">CC003</span></span></td>
<td><span data-ttu-id="de2ba-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-860">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-861">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-861">10001</span></span></td>
<td><span data-ttu-id="de2ba-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-862">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-863">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="de2ba-864">-713.75</span></span></td>
<td><span data-ttu-id="de2ba-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-866">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-867">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-868">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-868">10001</span></span></td>
<td><span data-ttu-id="de2ba-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-869">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-870">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-871">535.31</span><span class="sxs-lookup"><span data-stu-id="de2ba-871">535.31</span></span></td>
<td><span data-ttu-id="de2ba-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-873">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-874">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-875">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-875">10001</span></span></td>
<td><span data-ttu-id="de2ba-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-876">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-877">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-878">178.44</span><span class="sxs-lookup"><span data-stu-id="de2ba-878">178.44</span></span></td>
<td><span data-ttu-id="de2ba-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-880">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-880">CC003</span></span></td>
<td><span data-ttu-id="de2ba-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-881">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-882">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-882">10001</span></span></td>
<td><span data-ttu-id="de2ba-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-883">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-884">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="de2ba-885">-5,982.83</span></span></td>
<td><span data-ttu-id="de2ba-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-887">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-888">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-889">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-889">10001</span></span></td>
<td><span data-ttu-id="de2ba-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-890">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-891">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="de2ba-892">4,487.12</span></span></td>
<td><span data-ttu-id="de2ba-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-894">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-895">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-896">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-896">10001</span></span></td>
<td><span data-ttu-id="de2ba-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-897">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-898">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="de2ba-899">1,495.71</span></span></td>
<td><span data-ttu-id="de2ba-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-901">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-901">CC003</span></span></td>
<td><span data-ttu-id="de2ba-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-902">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-903">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-903">10001</span></span></td>
<td><span data-ttu-id="de2ba-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-904">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-905">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="de2ba-906">-286.25</span></span></td>
<td><span data-ttu-id="de2ba-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-908">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-909">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-910">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-910">10001</span></span></td>
<td><span data-ttu-id="de2ba-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-911">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-912">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-913">241.05</span><span class="sxs-lookup"><span data-stu-id="de2ba-913">241.05</span></span></td>
<td><span data-ttu-id="de2ba-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-915">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-916">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-917">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-917">10001</span></span></td>
<td><span data-ttu-id="de2ba-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-918">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-919">Fixed cost</span></span></td>
<td><span data-ttu-id="de2ba-920">45.20</span><span class="sxs-lookup"><span data-stu-id="de2ba-920">45.20</span></span></td>
<td><span data-ttu-id="de2ba-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-922">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-922">CC003</span></span></td>
<td><span data-ttu-id="de2ba-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="de2ba-923">Assembly</span></span></td>
<td><span data-ttu-id="de2ba-924">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-924">10001</span></span></td>
<td><span data-ttu-id="de2ba-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-925">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-926">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="de2ba-927">-2,977.17</span></span></td>
<td><span data-ttu-id="de2ba-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-929">Prod 1</span></span></td>
<td><span data-ttu-id="de2ba-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-930">Product 1</span></span></td>
<td><span data-ttu-id="de2ba-931">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-931">10001</span></span></td>
<td><span data-ttu-id="de2ba-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-932">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-933">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="de2ba-934">2,507.09</span></span></td>
<td><span data-ttu-id="de2ba-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="de2ba-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-936">Prod 2</span></span></td>
<td><span data-ttu-id="de2ba-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-937">Product 2</span></span></td>
<td><span data-ttu-id="de2ba-938">10001</span><span class="sxs-lookup"><span data-stu-id="de2ba-938">10001</span></span></td>
<td><span data-ttu-id="de2ba-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="de2ba-939">Electricity</span></span></td>
<td><span data-ttu-id="de2ba-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-940">Variable cost</span></span></td>
<td><span data-ttu-id="de2ba-941">470.08</span><span class="sxs-lookup"><span data-stu-id="de2ba-941">470.08</span></span></td>
<td><span data-ttu-id="de2ba-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="de2ba-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="de2ba-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="de2ba-943">Conclusion</span></span>
<span data-ttu-id="de2ba-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="de2ba-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="de2ba-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="de2ba-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="de2ba-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="de2ba-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="de2ba-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="de2ba-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="de2ba-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="de2ba-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="de2ba-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="de2ba-950">Razem</span><span class="sxs-lookup"><span data-stu-id="de2ba-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="de2ba-951">CC099</span><span class="sxs-lookup"><span data-stu-id="de2ba-951">CC099</span></span></th>
<th><span data-ttu-id="de2ba-952">CC001</span><span class="sxs-lookup"><span data-stu-id="de2ba-952">CC001</span></span></th>
<th><span data-ttu-id="de2ba-953">CC002</span><span class="sxs-lookup"><span data-stu-id="de2ba-953">CC002</span></span></th>
<th><span data-ttu-id="de2ba-954">CC003</span><span class="sxs-lookup"><span data-stu-id="de2ba-954">CC003</span></span></th>
<th><span data-ttu-id="de2ba-955">CC004</span><span class="sxs-lookup"><span data-stu-id="de2ba-955">CC004</span></span></th>
<th><span data-ttu-id="de2ba-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-956">Proj 1</span></span></th>
<th><span data-ttu-id="de2ba-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-957">Proj 2</span></span></th>
<th><span data-ttu-id="de2ba-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="de2ba-958">Prod 1</span></span></th>
<th><span data-ttu-id="de2ba-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="de2ba-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="de2ba-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="de2ba-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="de2ba-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="de2ba-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-971">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="de2ba-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="de2ba-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-973">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-974">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-975">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-976">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-977">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-978">776.36</span><span class="sxs-lookup"><span data-stu-id="de2ba-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-979">223.64</span><span class="sxs-lookup"><span data-stu-id="de2ba-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="de2ba-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="de2ba-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-982">000</span><span class="sxs-lookup"><span data-stu-id="de2ba-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-983">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-984">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-985">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-986">0,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-987">30.00</span><span class="sxs-lookup"><span data-stu-id="de2ba-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-988">10,00</span><span class="sxs-lookup"><span data-stu-id="de2ba-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="de2ba-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="de2ba-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="de2ba-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="de2ba-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="de2ba-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="de2ba-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="de2ba-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="de2ba-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="de2ba-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="de2ba-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="de2ba-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="de2ba-996">Aby uzyskać więcej informacji, [Zasady akumulacji kosztów i obliczanie narzutu](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="de2ba-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]