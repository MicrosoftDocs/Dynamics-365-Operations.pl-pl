---
title: Obliczenie narzutu
description: W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976482"
---
# <a name="overhead-calculation"></a><span data-ttu-id="e524a-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="e524a-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e524a-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="e524a-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="e524a-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="e524a-105">Term definition</span></span>
---------------

<span data-ttu-id="e524a-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="e524a-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="e524a-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="e524a-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="e524a-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="e524a-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="e524a-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="e524a-109">Rent</span></span>
-   <span data-ttu-id="e524a-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-110">Electricity</span></span>
-   <span data-ttu-id="e524a-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="e524a-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="e524a-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="e524a-112">Overhead calculation overview</span></span>
<span data-ttu-id="e524a-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="e524a-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="e524a-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="e524a-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="e524a-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="e524a-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="e524a-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="e524a-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="e524a-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="e524a-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="e524a-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="e524a-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="e524a-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="e524a-119">Version type</span></span>
-   <span data-ttu-id="e524a-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="e524a-120">Date and time</span></span>
-   <span data-ttu-id="e524a-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="e524a-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e524a-122">Fiscal year</span></span>
-   <span data-ttu-id="e524a-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e524a-123">Fiscal period</span></span>

<span data-ttu-id="e524a-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="e524a-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="e524a-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="e524a-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="e524a-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="e524a-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="e524a-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="e524a-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="e524a-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="e524a-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="e524a-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="e524a-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="e524a-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="e524a-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="e524a-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="e524a-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="e524a-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="e524a-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="e524a-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="e524a-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="e524a-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="e524a-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="e524a-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="e524a-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="e524a-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e524a-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e524a-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="e524a-140">Main account</span></span></th>
<th><span data-ttu-id="e524a-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="e524a-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="e524a-143">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-143">CC099</span></span></td>
<td><span data-ttu-id="e524a-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-144">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-145">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-145">10001</span></span></td>
<td><span data-ttu-id="e524a-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-146">Electricity</span></span></td>
<td><span data-ttu-id="e524a-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="e524a-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="e524a-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="e524a-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="e524a-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="e524a-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="e524a-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-151">Define the cost behavior rule</span></span>

<span data-ttu-id="e524a-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="e524a-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="e524a-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="e524a-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="e524a-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="e524a-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="e524a-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="e524a-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="e524a-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="e524a-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="e524a-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="e524a-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="e524a-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e524a-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e524a-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e524a-160">Journal</span></span></th>
<th><span data-ttu-id="e524a-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="e524a-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e524a-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e524a-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e524a-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="e524a-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-164">00001</span><span class="sxs-lookup"><span data-stu-id="e524a-164">00001</span></span></td>
<td><span data-ttu-id="e524a-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="e524a-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="e524a-166">Fiscal</span></span></td>
<td><span data-ttu-id="e524a-167">2017</span><span class="sxs-lookup"><span data-stu-id="e524a-167">2017</span></span></td>
<td><span data-ttu-id="e524a-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="e524a-168">Period 1</span></span></td>
<td><span data-ttu-id="e524a-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="e524a-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="e524a-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="e524a-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e524a-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e524a-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-173">Cost element</span></span></th>
<th><span data-ttu-id="e524a-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-174">Cost behavior</span></span></th>
<th><span data-ttu-id="e524a-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="e524a-177">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-177">CC099</span></span></td>
<td><span data-ttu-id="e524a-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-178">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-179">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-179">10001</span></span></td>
<td><span data-ttu-id="e524a-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-180">Electricity</span></span></td>
<td><span data-ttu-id="e524a-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="e524a-181">Unclassified</span></span></td>
<td><span data-ttu-id="e524a-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="e524a-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e524a-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-185">Cost element</span></span></th>
<th><span data-ttu-id="e524a-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-186">Cost behavior</span></span></th>
<th><span data-ttu-id="e524a-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-187">Amount</span></span></th>
<th><span data-ttu-id="e524a-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e524a-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-189">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-189">CC099</span></span></td>
<td><span data-ttu-id="e524a-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-190">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-191">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-191">10001</span></span></td>
<td><span data-ttu-id="e524a-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-192">Electricity</span></span></td>
<td><span data-ttu-id="e524a-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="e524a-193">Unclassified</span></span></td>
<td><span data-ttu-id="e524a-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="e524a-194">10,000.00</span></span></td>
<td><span data-ttu-id="e524a-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-196">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-196">CC099</span></span></td>
<td><span data-ttu-id="e524a-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-197">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-198">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-198">10001</span></span></td>
<td><span data-ttu-id="e524a-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-199">Electricity</span></span></td>
<td><span data-ttu-id="e524a-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="e524a-200">Unclassified</span></span></td>
<td><span data-ttu-id="e524a-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-201">-10,000.00</span></span></td>
<td><span data-ttu-id="e524a-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-203">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-203">CC099</span></span></td>
<td><span data-ttu-id="e524a-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-204">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-205">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-205">10001</span></span></td>
<td><span data-ttu-id="e524a-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-206">Electricity</span></span></td>
<td><span data-ttu-id="e524a-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-207">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-208">1,000.00</span></span></td>
<td><span data-ttu-id="e524a-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-210">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-210">CC099</span></span></td>
<td><span data-ttu-id="e524a-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-211">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-212">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-212">10001</span></span></td>
<td><span data-ttu-id="e524a-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-213">Electricity</span></span></td>
<td><span data-ttu-id="e524a-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-214">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="e524a-215">9,000.00</span></span></td>
<td><span data-ttu-id="e524a-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="e524a-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="e524a-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="e524a-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e524a-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="e524a-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="e524a-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="e524a-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-221">Define the cost distribution rule</span></span>

<span data-ttu-id="e524a-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="e524a-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="e524a-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="e524a-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="e524a-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="e524a-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="e524a-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="e524a-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="e524a-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="e524a-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="e524a-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e524a-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-228">Cost object</span></span></th>
<th><span data-ttu-id="e524a-229">kWh</span><span class="sxs-lookup"><span data-stu-id="e524a-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-230">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-230">CC001</span></span></td>
<td><span data-ttu-id="e524a-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-231">HR</span></span></td>
<td><span data-ttu-id="e524a-232">1 000</span><span class="sxs-lookup"><span data-stu-id="e524a-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-233">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-233">CC002</span></span></td>
<td><span data-ttu-id="e524a-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-234">Finance</span></span></td>
<td><span data-ttu-id="e524a-235">6,000</span><span class="sxs-lookup"><span data-stu-id="e524a-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-236">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-236">CC003</span></span></td>
<td><span data-ttu-id="e524a-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-237">Assembly</span></span></td>
<td><span data-ttu-id="e524a-238">0</span><span class="sxs-lookup"><span data-stu-id="e524a-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="e524a-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-240">Cost object</span></span></th>
<th><span data-ttu-id="e524a-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="e524a-241">Magnitude</span></span></th>
<th><span data-ttu-id="e524a-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e524a-242">Allocation factor</span></span></th>
<th><span data-ttu-id="e524a-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-244">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-244">CC001</span></span></td>
<td><span data-ttu-id="e524a-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-245">HR</span></span></td>
<td><span data-ttu-id="e524a-246">1 000</span><span class="sxs-lookup"><span data-stu-id="e524a-246">1,000</span></span></td>
<td><span data-ttu-id="e524a-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="e524a-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="e524a-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-249">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-249">CC002</span></span></td>
<td><span data-ttu-id="e524a-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-250">Finance</span></span></td>
<td><span data-ttu-id="e524a-251">6,000</span><span class="sxs-lookup"><span data-stu-id="e524a-251">6,000</span></span></td>
<td><span data-ttu-id="e524a-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="e524a-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="e524a-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-254">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-254">CC003</span></span></td>
<td><span data-ttu-id="e524a-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-255">Assembly</span></span></td>
<td><span data-ttu-id="e524a-256">0</span><span class="sxs-lookup"><span data-stu-id="e524a-256">0</span></span></td>
<td><span data-ttu-id="e524a-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="e524a-258">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="e524a-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="e524a-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="e524a-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-261">Cost object</span></span></th>
<th><span data-ttu-id="e524a-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="e524a-262">Formula</span></span></th>
<th><span data-ttu-id="e524a-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="e524a-263">Magnitude</span></span></th>
<th><span data-ttu-id="e524a-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e524a-264">Allocation factor</span></span></th>
<th><span data-ttu-id="e524a-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-266">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-266">CC001</span></span></td>
<td><span data-ttu-id="e524a-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-267">HR</span></span></td>
<td><span data-ttu-id="e524a-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="e524a-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="e524a-269">1</span><span class="sxs-lookup"><span data-stu-id="e524a-269">1</span></span></td>
<td><span data-ttu-id="e524a-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="e524a-271">500.00</span><span class="sxs-lookup"><span data-stu-id="e524a-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-272">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-272">CC002</span></span></td>
<td><span data-ttu-id="e524a-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-273">Finance</span></span></td>
<td><span data-ttu-id="e524a-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="e524a-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="e524a-275">1</span><span class="sxs-lookup"><span data-stu-id="e524a-275">1</span></span></td>
<td><span data-ttu-id="e524a-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="e524a-277">500.00</span><span class="sxs-lookup"><span data-stu-id="e524a-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-278">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-278">CC003</span></span></td>
<td><span data-ttu-id="e524a-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-279">Assembly</span></span></td>
<td><span data-ttu-id="e524a-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="e524a-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="e524a-281">0</span><span class="sxs-lookup"><span data-stu-id="e524a-281">0</span></span></td>
<td><span data-ttu-id="e524a-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="e524a-283">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="e524a-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e524a-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e524a-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e524a-285">Journal</span></span></th>
<th><span data-ttu-id="e524a-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="e524a-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e524a-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e524a-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e524a-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="e524a-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-289">00002</span><span class="sxs-lookup"><span data-stu-id="e524a-289">00002</span></span></td>
<td><span data-ttu-id="e524a-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="e524a-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="e524a-291">Fiscal</span></span></td>
<td><span data-ttu-id="e524a-292">2017</span><span class="sxs-lookup"><span data-stu-id="e524a-292">2017</span></span></td>
<td><span data-ttu-id="e524a-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="e524a-293">Period 1</span></span></td>
<td><span data-ttu-id="e524a-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="e524a-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="e524a-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="e524a-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e524a-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e524a-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-298">Cost element</span></span></th>
<th><span data-ttu-id="e524a-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-299">Cost behavior</span></span></th>
<th><span data-ttu-id="e524a-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-302">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-302">CC099</span></span></td>
<td><span data-ttu-id="e524a-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-303">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-304">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-304">10001</span></span></td>
<td><span data-ttu-id="e524a-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-305">Electricity</span></span></td>
<td><span data-ttu-id="e524a-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-306">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-309">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-309">CC099</span></span></td>
<td><span data-ttu-id="e524a-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-310">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-311">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-311">10001</span></span></td>
<td><span data-ttu-id="e524a-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-312">Electricity</span></span></td>
<td><span data-ttu-id="e524a-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-313">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="e524a-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e524a-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-317">Cost element</span></span></th>
<th><span data-ttu-id="e524a-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-318">Cost behavior</span></span></th>
<th><span data-ttu-id="e524a-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-319">Amount</span></span></th>
<th><span data-ttu-id="e524a-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e524a-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-321">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-321">CC099</span></span></td>
<td><span data-ttu-id="e524a-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-322">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-323">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-323">10001</span></span></td>
<td><span data-ttu-id="e524a-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-324">Electricity</span></span></td>
<td><span data-ttu-id="e524a-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-325">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-326">-1,000.00</span></span></td>
<td><span data-ttu-id="e524a-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-328">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-328">CC001</span></span></td>
<td><span data-ttu-id="e524a-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-329">HR</span></span></td>
<td><span data-ttu-id="e524a-330">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-330">10001</span></span></td>
<td><span data-ttu-id="e524a-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-331">Electricity</span></span></td>
<td><span data-ttu-id="e524a-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-332">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-333">500.00</span><span class="sxs-lookup"><span data-stu-id="e524a-333">500.00</span></span></td>
<td><span data-ttu-id="e524a-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-335">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-335">CC002</span></span></td>
<td><span data-ttu-id="e524a-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-336">Finance</span></span></td>
<td><span data-ttu-id="e524a-337">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-337">10001</span></span></td>
<td><span data-ttu-id="e524a-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-338">Electricity</span></span></td>
<td><span data-ttu-id="e524a-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-339">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-340">500.00</span><span class="sxs-lookup"><span data-stu-id="e524a-340">500.00</span></span></td>
<td><span data-ttu-id="e524a-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-342">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-342">CC099</span></span></td>
<td><span data-ttu-id="e524a-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-343">Default cost center</span></span></td>
<td><span data-ttu-id="e524a-344">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-344">10001</span></span></td>
<td><span data-ttu-id="e524a-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-345">Electricity</span></span></td>
<td><span data-ttu-id="e524a-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-346">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="e524a-347">-9,000.00</span></span></td>
<td><span data-ttu-id="e524a-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-349">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-349">CC001</span></span></td>
<td><span data-ttu-id="e524a-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-350">HR</span></span></td>
<td><span data-ttu-id="e524a-351">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-351">10001</span></span></td>
<td><span data-ttu-id="e524a-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-352">Electricity</span></span></td>
<td><span data-ttu-id="e524a-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-353">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="e524a-354">1,285.71</span></span></td>
<td><span data-ttu-id="e524a-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-356">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-356">CC002</span></span></td>
<td><span data-ttu-id="e524a-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-357">Finance</span></span></td>
<td><span data-ttu-id="e524a-358">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-358">10001</span></span></td>
<td><span data-ttu-id="e524a-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-359">Electricity</span></span></td>
<td><span data-ttu-id="e524a-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-360">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="e524a-361">7,714.29</span></span></td>
<td><span data-ttu-id="e524a-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="e524a-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="e524a-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="e524a-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="e524a-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="e524a-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e524a-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="e524a-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="e524a-367">Define the overhead rate</span></span>

<span data-ttu-id="e524a-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="e524a-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="e524a-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e524a-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-370">Cost object</span></span></th>
<th><span data-ttu-id="e524a-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="e524a-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e524a-372">Proj 1</span></span></td>
<td><span data-ttu-id="e524a-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-373">Project 1</span></span></td>
<td><span data-ttu-id="e524a-374">3</span><span class="sxs-lookup"><span data-stu-id="e524a-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e524a-375">Proj 2</span></span></td>
<td><span data-ttu-id="e524a-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-376">Project 2</span></span></td>
<td><span data-ttu-id="e524a-377">1</span><span class="sxs-lookup"><span data-stu-id="e524a-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="e524a-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-379">Cost object</span></span></th>
<th><span data-ttu-id="e524a-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-380">Cost element</span></span></th>
<th><span data-ttu-id="e524a-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-381">Cost behavior</span></span></th>
<th><span data-ttu-id="e524a-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="e524a-382">Units</span></span></th>
<th><span data-ttu-id="e524a-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="e524a-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-384">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-384">CC001</span></span></td>
<td><span data-ttu-id="e524a-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-385">HR</span></span></td>
<td><span data-ttu-id="e524a-386">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-386">10001</span></span></td>
<td><span data-ttu-id="e524a-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-387">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-388">1</span><span class="sxs-lookup"><span data-stu-id="e524a-388">1</span></span></td>
<td><span data-ttu-id="e524a-389">10</span><span class="sxs-lookup"><span data-stu-id="e524a-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="e524a-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-391">Cost object</span></span></th>
<th><span data-ttu-id="e524a-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="e524a-392">Magnitude</span></span></th>
<th><span data-ttu-id="e524a-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-393">Cost element</span></span></th>
<th><span data-ttu-id="e524a-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e524a-394">Allocation factor</span></span></th>
<th><span data-ttu-id="e524a-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e524a-396">Proj 1</span></span></td>
<td><span data-ttu-id="e524a-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-397">Project 1</span></span></td>
<td><span data-ttu-id="e524a-398">3</span><span class="sxs-lookup"><span data-stu-id="e524a-398">3</span></span></td>
<td><span data-ttu-id="e524a-399">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-399">10001</span></span></td>
<td><span data-ttu-id="e524a-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="e524a-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="e524a-401">30.00</span><span class="sxs-lookup"><span data-stu-id="e524a-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e524a-402">Proj 2</span></span></td>
<td><span data-ttu-id="e524a-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-403">Project 2</span></span></td>
<td><span data-ttu-id="e524a-404">1</span><span class="sxs-lookup"><span data-stu-id="e524a-404">1</span></span></td>
<td><span data-ttu-id="e524a-405">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-405">10001</span></span></td>
<td><span data-ttu-id="e524a-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="e524a-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="e524a-407">10,00</span><span class="sxs-lookup"><span data-stu-id="e524a-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="e524a-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e524a-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e524a-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e524a-409">Journal</span></span></th>
<th><span data-ttu-id="e524a-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="e524a-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e524a-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e524a-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e524a-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="e524a-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-413">00003</span><span class="sxs-lookup"><span data-stu-id="e524a-413">00003</span></span></td>
<td><span data-ttu-id="e524a-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="e524a-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="e524a-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="e524a-415">Fiscal</span></span></td>
<td><span data-ttu-id="e524a-416">2017</span><span class="sxs-lookup"><span data-stu-id="e524a-416">2017</span></span></td>
<td><span data-ttu-id="e524a-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="e524a-417">Period 1</span></span></td>
<td><span data-ttu-id="e524a-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="e524a-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="e524a-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="e524a-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e524a-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e524a-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-421">Cost object</span></span></th>
<th><span data-ttu-id="e524a-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="e524a-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e524a-424">Proj 1</span></span></td>
<td><span data-ttu-id="e524a-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="e524a-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="e524a-426">3,00</span><span class="sxs-lookup"><span data-stu-id="e524a-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e524a-428">Proj 2</span></span></td>
<td><span data-ttu-id="e524a-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="e524a-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="e524a-430">1.00</span><span class="sxs-lookup"><span data-stu-id="e524a-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e524a-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-433">Cost element</span></span></th>
<th><span data-ttu-id="e524a-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-434">Cost behavior</span></span></th>
<th><span data-ttu-id="e524a-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-435">Amount</span></span></th>
<th><span data-ttu-id="e524a-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e524a-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="e524a-437">CC0001</span></span></td>
<td><span data-ttu-id="e524a-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-438">HR</span></span></td>
<td><span data-ttu-id="e524a-439">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-439">10001</span></span></td>
<td><span data-ttu-id="e524a-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-440">Electricity</span></span></td>
<td><span data-ttu-id="e524a-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-441">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="e524a-442">-30.00</span></span></td>
<td><span data-ttu-id="e524a-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e524a-444">Proj 1</span></span></td>
<td><span data-ttu-id="e524a-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="e524a-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="e524a-446">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-446">10001</span></span></td>
<td><span data-ttu-id="e524a-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-447">Electricity</span></span></td>
<td><span data-ttu-id="e524a-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-448">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-449">30.00</span><span class="sxs-lookup"><span data-stu-id="e524a-449">30.00</span></span></td>
<td><span data-ttu-id="e524a-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-451">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-451">CC001</span></span></td>
<td><span data-ttu-id="e524a-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-452">HR</span></span></td>
<td><span data-ttu-id="e524a-453">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-453">10001</span></span></td>
<td><span data-ttu-id="e524a-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-454">Electricity</span></span></td>
<td><span data-ttu-id="e524a-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-455">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="e524a-456">-10.00</span></span></td>
<td><span data-ttu-id="e524a-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e524a-458">Proj 2</span></span></td>
<td><span data-ttu-id="e524a-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="e524a-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="e524a-460">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-460">10001</span></span></td>
<td><span data-ttu-id="e524a-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-461">Electricity</span></span></td>
<td><span data-ttu-id="e524a-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-462">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-463">10,00</span><span class="sxs-lookup"><span data-stu-id="e524a-463">10.00</span></span></td>
<td><span data-ttu-id="e524a-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="e524a-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="e524a-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="e524a-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e524a-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="e524a-468">Aplikacja Finance obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="e524a-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="e524a-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="e524a-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="e524a-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="e524a-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e524a-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="e524a-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="e524a-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="e524a-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="e524a-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="e524a-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="e524a-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-475">Define the cost allocation</span></span>

<span data-ttu-id="e524a-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="e524a-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="e524a-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e524a-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-479">Cost object</span></span></th>
<th><span data-ttu-id="e524a-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="e524a-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-481">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-481">CC002</span></span></td>
<td><span data-ttu-id="e524a-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-482">Finance</span></span></td>
<td><span data-ttu-id="e524a-483">35</span><span class="sxs-lookup"><span data-stu-id="e524a-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-484">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-484">CC003</span></span></td>
<td><span data-ttu-id="e524a-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-485">Assembly</span></span></td>
<td><span data-ttu-id="e524a-486">55</span><span class="sxs-lookup"><span data-stu-id="e524a-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-487">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-487">CC004</span></span></td>
<td><span data-ttu-id="e524a-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-488">Packaging</span></span></td>
<td><span data-ttu-id="e524a-489">10</span><span class="sxs-lookup"><span data-stu-id="e524a-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="e524a-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e524a-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-492">Cost object</span></span></th>
<th><span data-ttu-id="e524a-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="e524a-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-494">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-494">CC003</span></span></td>
<td><span data-ttu-id="e524a-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-495">Assembly</span></span></td>
<td><span data-ttu-id="e524a-496">65</span><span class="sxs-lookup"><span data-stu-id="e524a-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-497">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-497">CC004</span></span></td>
<td><span data-ttu-id="e524a-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-498">Packaging</span></span></td>
<td><span data-ttu-id="e524a-499">35</span><span class="sxs-lookup"><span data-stu-id="e524a-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="e524a-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e524a-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-502">Cost object</span></span></th>
<th><span data-ttu-id="e524a-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="e524a-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-504">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-505">Product 1</span></span></td>
<td><span data-ttu-id="e524a-506">60</span><span class="sxs-lookup"><span data-stu-id="e524a-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-507">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-508">Product 2</span></span></td>
<td><span data-ttu-id="e524a-509">20</span><span class="sxs-lookup"><span data-stu-id="e524a-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="e524a-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e524a-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-512">Cost object</span></span></th>
<th><span data-ttu-id="e524a-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="e524a-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-514">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-515">Product 1</span></span></td>
<td><span data-ttu-id="e524a-516">80</span><span class="sxs-lookup"><span data-stu-id="e524a-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-517">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-518">Product 2</span></span></td>
<td><span data-ttu-id="e524a-519">15</span><span class="sxs-lookup"><span data-stu-id="e524a-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="e524a-520">Miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="e524a-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="e524a-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="e524a-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="e524a-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="e524a-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-523">Cost object</span></span></th>
<th><span data-ttu-id="e524a-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="e524a-524">Magnitude</span></span></th>
<th><span data-ttu-id="e524a-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e524a-525">Allocation factor</span></span></th>
<th><span data-ttu-id="e524a-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-526">Amount</span></span></th>
<th><span data-ttu-id="e524a-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-528">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-528">CC002</span></span></td>
<td><span data-ttu-id="e524a-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-529">Finance</span></span></td>
<td><span data-ttu-id="e524a-530">35</span><span class="sxs-lookup"><span data-stu-id="e524a-530">35</span></span></td>
<td><span data-ttu-id="e524a-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="e524a-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="e524a-532">175.00</span><span class="sxs-lookup"><span data-stu-id="e524a-532">175.00</span></span></td>
<td><span data-ttu-id="e524a-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-534">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-534">CC003</span></span></td>
<td><span data-ttu-id="e524a-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-535">Assembly</span></span></td>
<td><span data-ttu-id="e524a-536">55</span><span class="sxs-lookup"><span data-stu-id="e524a-536">55</span></span></td>
<td><span data-ttu-id="e524a-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="e524a-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="e524a-538">275.00</span><span class="sxs-lookup"><span data-stu-id="e524a-538">275.00</span></span></td>
<td><span data-ttu-id="e524a-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-540">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-540">CC004</span></span></td>
<td><span data-ttu-id="e524a-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-541">Packaging</span></span></td>
<td><span data-ttu-id="e524a-542">10</span><span class="sxs-lookup"><span data-stu-id="e524a-542">10</span></span></td>
<td><span data-ttu-id="e524a-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="e524a-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="e524a-544">50,00</span><span class="sxs-lookup"><span data-stu-id="e524a-544">50.00</span></span></td>
<td><span data-ttu-id="e524a-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-546">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-546">CC002</span></span></td>
<td><span data-ttu-id="e524a-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-547">Finance</span></span></td>
<td><span data-ttu-id="e524a-548">35</span><span class="sxs-lookup"><span data-stu-id="e524a-548">35</span></span></td>
<td><span data-ttu-id="e524a-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="e524a-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="e524a-550">436.00</span><span class="sxs-lookup"><span data-stu-id="e524a-550">436.00</span></span></td>
<td><span data-ttu-id="e524a-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-552">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-552">CC003</span></span></td>
<td><span data-ttu-id="e524a-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-553">Assembly</span></span></td>
<td><span data-ttu-id="e524a-554">55</span><span class="sxs-lookup"><span data-stu-id="e524a-554">55</span></span></td>
<td><span data-ttu-id="e524a-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="e524a-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="e524a-556">685.14</span><span class="sxs-lookup"><span data-stu-id="e524a-556">685.14</span></span></td>
<td><span data-ttu-id="e524a-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-558">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-558">CC004</span></span></td>
<td><span data-ttu-id="e524a-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-559">Packaging</span></span></td>
<td><span data-ttu-id="e524a-560">10</span><span class="sxs-lookup"><span data-stu-id="e524a-560">10</span></span></td>
<td><span data-ttu-id="e524a-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="e524a-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="e524a-562">124.57</span><span class="sxs-lookup"><span data-stu-id="e524a-562">124.57</span></span></td>
<td><span data-ttu-id="e524a-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="e524a-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-565">Cost object</span></span></th>
<th><span data-ttu-id="e524a-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="e524a-566">Magnitude</span></span></th>
<th><span data-ttu-id="e524a-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e524a-567">Allocation factor</span></span></th>
<th><span data-ttu-id="e524a-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-568">Amount</span></span></th>
<th><span data-ttu-id="e524a-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-570">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-570">CC003</span></span></td>
<td><span data-ttu-id="e524a-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-571">Assembly</span></span></td>
<td><span data-ttu-id="e524a-572">65</span><span class="sxs-lookup"><span data-stu-id="e524a-572">65</span></span></td>
<td><span data-ttu-id="e524a-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="e524a-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="e524a-574">438.75</span><span class="sxs-lookup"><span data-stu-id="e524a-574">438.75</span></span></td>
<td><span data-ttu-id="e524a-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-576">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-576">CC004</span></span></td>
<td><span data-ttu-id="e524a-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-577">Packaging</span></span></td>
<td><span data-ttu-id="e524a-578">35</span><span class="sxs-lookup"><span data-stu-id="e524a-578">35</span></span></td>
<td><span data-ttu-id="e524a-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="e524a-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="e524a-580">236.25</span><span class="sxs-lookup"><span data-stu-id="e524a-580">236.25</span></span></td>
<td><span data-ttu-id="e524a-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-582">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-582">CC003</span></span></td>
<td><span data-ttu-id="e524a-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-583">Assembly</span></span></td>
<td><span data-ttu-id="e524a-584">65</span><span class="sxs-lookup"><span data-stu-id="e524a-584">65</span></span></td>
<td><span data-ttu-id="e524a-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="e524a-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="e524a-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="e524a-586">5,297.69</span></span></td>
<td><span data-ttu-id="e524a-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-588">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-588">CC004</span></span></td>
<td><span data-ttu-id="e524a-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-589">Packaging</span></span></td>
<td><span data-ttu-id="e524a-590">35</span><span class="sxs-lookup"><span data-stu-id="e524a-590">35</span></span></td>
<td><span data-ttu-id="e524a-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="e524a-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="e524a-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="e524a-592">2,852.60</span></span></td>
<td><span data-ttu-id="e524a-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="e524a-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-595">Cost object</span></span></th>
<th><span data-ttu-id="e524a-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="e524a-596">Magnitude</span></span></th>
<th><span data-ttu-id="e524a-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e524a-597">Allocation factor</span></span></th>
<th><span data-ttu-id="e524a-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-598">Amount</span></span></th>
<th><span data-ttu-id="e524a-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-600">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-601">Product 1</span></span></td>
<td><span data-ttu-id="e524a-602">60</span><span class="sxs-lookup"><span data-stu-id="e524a-602">60</span></span></td>
<td><span data-ttu-id="e524a-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="e524a-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="e524a-604">535.31</span><span class="sxs-lookup"><span data-stu-id="e524a-604">535.31</span></span></td>
<td><span data-ttu-id="e524a-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-606">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-607">Product 2</span></span></td>
<td><span data-ttu-id="e524a-608">20</span><span class="sxs-lookup"><span data-stu-id="e524a-608">20</span></span></td>
<td><span data-ttu-id="e524a-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="e524a-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="e524a-610">178.44</span><span class="sxs-lookup"><span data-stu-id="e524a-610">178.44</span></span></td>
<td><span data-ttu-id="e524a-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-612">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-613">Product 1</span></span></td>
<td><span data-ttu-id="e524a-614">60</span><span class="sxs-lookup"><span data-stu-id="e524a-614">60</span></span></td>
<td><span data-ttu-id="e524a-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="e524a-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="e524a-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="e524a-616">4,487.12</span></span></td>
<td><span data-ttu-id="e524a-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-618">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-619">Product 2</span></span></td>
<td><span data-ttu-id="e524a-620">20</span><span class="sxs-lookup"><span data-stu-id="e524a-620">20</span></span></td>
<td><span data-ttu-id="e524a-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="e524a-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="e524a-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="e524a-622">1,495.71</span></span></td>
<td><span data-ttu-id="e524a-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e524a-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="e524a-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-625">Cost object</span></span></th>
<th><span data-ttu-id="e524a-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="e524a-626">Magnitude</span></span></th>
<th><span data-ttu-id="e524a-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e524a-627">Allocation factor</span></span></th>
<th><span data-ttu-id="e524a-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-628">Amount</span></span></th>
<th><span data-ttu-id="e524a-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-630">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-631">Product 1</span></span></td>
<td><span data-ttu-id="e524a-632">80</span><span class="sxs-lookup"><span data-stu-id="e524a-632">80</span></span></td>
<td><span data-ttu-id="e524a-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="e524a-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="e524a-634">241.05</span><span class="sxs-lookup"><span data-stu-id="e524a-634">241.05</span></span></td>
<td><span data-ttu-id="e524a-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-636">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-637">Product 2</span></span></td>
<td><span data-ttu-id="e524a-638">15</span><span class="sxs-lookup"><span data-stu-id="e524a-638">15</span></span></td>
<td><span data-ttu-id="e524a-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="e524a-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="e524a-640">45.20</span><span class="sxs-lookup"><span data-stu-id="e524a-640">45.20</span></span></td>
<td><span data-ttu-id="e524a-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-642">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-643">Product 1</span></span></td>
<td><span data-ttu-id="e524a-644">80</span><span class="sxs-lookup"><span data-stu-id="e524a-644">80</span></span></td>
<td><span data-ttu-id="e524a-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="e524a-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="e524a-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="e524a-646">2,507.09</span></span></td>
<td><span data-ttu-id="e524a-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-648">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-649">Product 2</span></span></td>
<td><span data-ttu-id="e524a-650">15</span><span class="sxs-lookup"><span data-stu-id="e524a-650">15</span></span></td>
<td><span data-ttu-id="e524a-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="e524a-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="e524a-652">470.08</span><span class="sxs-lookup"><span data-stu-id="e524a-652">470.08</span></span></td>
<td><span data-ttu-id="e524a-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="e524a-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="e524a-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e524a-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e524a-655">Journal</span></span></th>
<th><span data-ttu-id="e524a-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="e524a-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e524a-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e524a-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e524a-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="e524a-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-659">00004</span><span class="sxs-lookup"><span data-stu-id="e524a-659">00004</span></span></td>
<td><span data-ttu-id="e524a-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="e524a-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="e524a-661">Fiscal</span></span></td>
<td><span data-ttu-id="e524a-662">2017</span><span class="sxs-lookup"><span data-stu-id="e524a-662">2017</span></span></td>
<td><span data-ttu-id="e524a-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="e524a-663">Period 1</span></span></td>
<td><span data-ttu-id="e524a-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="e524a-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="e524a-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="e524a-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e524a-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e524a-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-668">Cost element</span></span></th>
<th><span data-ttu-id="e524a-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-669">Cost behavior</span></span></th>
<th><span data-ttu-id="e524a-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-672">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-672">CC001</span></span></td>
<td><span data-ttu-id="e524a-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-673">HR</span></span></td>
<td><span data-ttu-id="e524a-674">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-674">10001</span></span></td>
<td><span data-ttu-id="e524a-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-675">Electricity</span></span></td>
<td><span data-ttu-id="e524a-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-676">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-677">500.00</span><span class="sxs-lookup"><span data-stu-id="e524a-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-679">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-679">CC001</span></span></td>
<td><span data-ttu-id="e524a-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-680">HR</span></span></td>
<td><span data-ttu-id="e524a-681">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-681">10001</span></span></td>
<td><span data-ttu-id="e524a-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-682">Electricity</span></span></td>
<td><span data-ttu-id="e524a-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-683">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="e524a-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-686">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-686">CC002</span></span></td>
<td><span data-ttu-id="e524a-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-687">Finance</span></span></td>
<td><span data-ttu-id="e524a-688">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-688">10001</span></span></td>
<td><span data-ttu-id="e524a-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-689">Electricity</span></span></td>
<td><span data-ttu-id="e524a-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-690">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-691">675.00</span><span class="sxs-lookup"><span data-stu-id="e524a-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-693">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-693">CC002</span></span></td>
<td><span data-ttu-id="e524a-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-694">Finance</span></span></td>
<td><span data-ttu-id="e524a-695">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-695">10001</span></span></td>
<td><span data-ttu-id="e524a-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-696">Electricity</span></span></td>
<td><span data-ttu-id="e524a-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-697">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="e524a-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-700">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-700">CC003</span></span></td>
<td><span data-ttu-id="e524a-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-701">Assembly</span></span></td>
<td><span data-ttu-id="e524a-702">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-702">10001</span></span></td>
<td><span data-ttu-id="e524a-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-703">Electricity</span></span></td>
<td><span data-ttu-id="e524a-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-704">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-705">713.75</span><span class="sxs-lookup"><span data-stu-id="e524a-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-707">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-707">CC003</span></span></td>
<td><span data-ttu-id="e524a-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-708">Assembly</span></span></td>
<td><span data-ttu-id="e524a-709">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-709">10001</span></span></td>
<td><span data-ttu-id="e524a-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-710">Electricity</span></span></td>
<td><span data-ttu-id="e524a-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-711">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="e524a-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-714">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-714">CC003</span></span></td>
<td><span data-ttu-id="e524a-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-715">Packaging</span></span></td>
<td><span data-ttu-id="e524a-716">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-716">10001</span></span></td>
<td><span data-ttu-id="e524a-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-717">Electricity</span></span></td>
<td><span data-ttu-id="e524a-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-718">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-719">286.25</span><span class="sxs-lookup"><span data-stu-id="e524a-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-721">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-721">CC003</span></span></td>
<td><span data-ttu-id="e524a-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-722">Packaging</span></span></td>
<td><span data-ttu-id="e524a-723">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-723">10001</span></span></td>
<td><span data-ttu-id="e524a-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-724">Electricity</span></span></td>
<td><span data-ttu-id="e524a-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-725">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="e524a-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-728">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-729">Product 1</span></span></td>
<td><span data-ttu-id="e524a-730">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-730">10001</span></span></td>
<td><span data-ttu-id="e524a-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-731">Electricity</span></span></td>
<td><span data-ttu-id="e524a-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-732">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-733">776.36</span><span class="sxs-lookup"><span data-stu-id="e524a-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-735">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-736">Product 1</span></span></td>
<td><span data-ttu-id="e524a-737">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-737">10001</span></span></td>
<td><span data-ttu-id="e524a-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-738">Electricity</span></span></td>
<td><span data-ttu-id="e524a-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-739">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="e524a-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-742">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-743">Product 1</span></span></td>
<td><span data-ttu-id="e524a-744">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-744">10001</span></span></td>
<td><span data-ttu-id="e524a-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-745">Electricity</span></span></td>
<td><span data-ttu-id="e524a-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-746">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-747">223.64</span><span class="sxs-lookup"><span data-stu-id="e524a-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="e524a-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-749">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-750">Product 1</span></span></td>
<td><span data-ttu-id="e524a-751">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-751">10001</span></span></td>
<td><span data-ttu-id="e524a-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-752">Electricity</span></span></td>
<td><span data-ttu-id="e524a-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-753">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="e524a-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e524a-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e524a-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e524a-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-757">Cost element</span></span></th>
<th><span data-ttu-id="e524a-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-758">Cost behavior</span></span></th>
<th><span data-ttu-id="e524a-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="e524a-759">Amount</span></span></th>
<th><span data-ttu-id="e524a-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e524a-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e524a-761">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-761">CC001</span></span></td>
<td><span data-ttu-id="e524a-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-762">HR</span></span></td>
<td><span data-ttu-id="e524a-763">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-763">10001</span></span></td>
<td><span data-ttu-id="e524a-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-764">Electricity</span></span></td>
<td><span data-ttu-id="e524a-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-765">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="e524a-766">-500.00</span></span></td>
<td><span data-ttu-id="e524a-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-768">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-768">CC002</span></span></td>
<td><span data-ttu-id="e524a-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-769">Finance</span></span></td>
<td><span data-ttu-id="e524a-770">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-770">10001</span></span></td>
<td><span data-ttu-id="e524a-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-771">Electricity</span></span></td>
<td><span data-ttu-id="e524a-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-772">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-773">175.00</span><span class="sxs-lookup"><span data-stu-id="e524a-773">175.00</span></span></td>
<td><span data-ttu-id="e524a-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-775">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-775">CC003</span></span></td>
<td><span data-ttu-id="e524a-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-776">Assembly</span></span></td>
<td><span data-ttu-id="e524a-777">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-777">10001</span></span></td>
<td><span data-ttu-id="e524a-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-778">Electricity</span></span></td>
<td><span data-ttu-id="e524a-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-779">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-780">275.00</span><span class="sxs-lookup"><span data-stu-id="e524a-780">275.00</span></span></td>
<td><span data-ttu-id="e524a-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-782">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-782">CC004</span></span></td>
<td><span data-ttu-id="e524a-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-783">Packaging</span></span></td>
<td><span data-ttu-id="e524a-784">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-784">10001</span></span></td>
<td><span data-ttu-id="e524a-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-785">Electricity</span></span></td>
<td><span data-ttu-id="e524a-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-786">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-787">50,00</span><span class="sxs-lookup"><span data-stu-id="e524a-787">50,00</span></span></td>
<td><span data-ttu-id="e524a-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-789">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-789">CC001</span></span></td>
<td><span data-ttu-id="e524a-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e524a-790">HR</span></span></td>
<td><span data-ttu-id="e524a-791">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-791">10001</span></span></td>
<td><span data-ttu-id="e524a-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-792">Electricity</span></span></td>
<td><span data-ttu-id="e524a-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-793">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="e524a-794">-1,245.71</span></span></td>
<td><span data-ttu-id="e524a-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-796">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-796">CC002</span></span></td>
<td><span data-ttu-id="e524a-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-797">Finance</span></span></td>
<td><span data-ttu-id="e524a-798">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-798">10001</span></span></td>
<td><span data-ttu-id="e524a-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-799">Electricity</span></span></td>
<td><span data-ttu-id="e524a-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-800">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-801">436.00</span><span class="sxs-lookup"><span data-stu-id="e524a-801">436.00</span></span></td>
<td><span data-ttu-id="e524a-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-803">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-803">CC003</span></span></td>
<td><span data-ttu-id="e524a-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-804">Assembly</span></span></td>
<td><span data-ttu-id="e524a-805">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-805">10001</span></span></td>
<td><span data-ttu-id="e524a-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-806">Electricity</span></span></td>
<td><span data-ttu-id="e524a-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-807">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-808">685.14</span><span class="sxs-lookup"><span data-stu-id="e524a-808">685.14</span></span></td>
<td><span data-ttu-id="e524a-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-810">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-810">CC004</span></span></td>
<td><span data-ttu-id="e524a-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-811">Packaging</span></span></td>
<td><span data-ttu-id="e524a-812">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-812">10001</span></span></td>
<td><span data-ttu-id="e524a-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-813">Electricity</span></span></td>
<td><span data-ttu-id="e524a-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-814">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-815">124.57</span><span class="sxs-lookup"><span data-stu-id="e524a-815">124.57</span></span></td>
<td><span data-ttu-id="e524a-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-817">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-817">CC002</span></span></td>
<td><span data-ttu-id="e524a-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-818">Finance</span></span></td>
<td><span data-ttu-id="e524a-819">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-819">10001</span></span></td>
<td><span data-ttu-id="e524a-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-820">Electricity</span></span></td>
<td><span data-ttu-id="e524a-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-821">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="e524a-822">-675.00</span></span></td>
<td><span data-ttu-id="e524a-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-824">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-824">CC003</span></span></td>
<td><span data-ttu-id="e524a-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-825">Assembly</span></span></td>
<td><span data-ttu-id="e524a-826">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-826">10001</span></span></td>
<td><span data-ttu-id="e524a-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-827">Electricity</span></span></td>
<td><span data-ttu-id="e524a-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-828">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-829">438.75</span><span class="sxs-lookup"><span data-stu-id="e524a-829">438.75</span></span></td>
<td><span data-ttu-id="e524a-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-831">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-831">CC004</span></span></td>
<td><span data-ttu-id="e524a-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-832">Packaging</span></span></td>
<td><span data-ttu-id="e524a-833">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-833">10001</span></span></td>
<td><span data-ttu-id="e524a-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-834">Electricity</span></span></td>
<td><span data-ttu-id="e524a-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-835">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-836">236.25</span><span class="sxs-lookup"><span data-stu-id="e524a-836">236.25</span></span></td>
<td><span data-ttu-id="e524a-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-838">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-838">CC002</span></span></td>
<td><span data-ttu-id="e524a-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="e524a-839">Finance</span></span></td>
<td><span data-ttu-id="e524a-840">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-840">10001</span></span></td>
<td><span data-ttu-id="e524a-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-841">Electricity</span></span></td>
<td><span data-ttu-id="e524a-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-842">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="e524a-843">-8,150.29</span></span></td>
<td><span data-ttu-id="e524a-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-845">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-845">CC003</span></span></td>
<td><span data-ttu-id="e524a-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-846">Assembly</span></span></td>
<td><span data-ttu-id="e524a-847">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-847">10001</span></span></td>
<td><span data-ttu-id="e524a-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-848">Electricity</span></span></td>
<td><span data-ttu-id="e524a-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-849">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="e524a-850">5,297.69</span></span></td>
<td><span data-ttu-id="e524a-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-852">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-852">CC004</span></span></td>
<td><span data-ttu-id="e524a-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e524a-853">Packaging</span></span></td>
<td><span data-ttu-id="e524a-854">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-854">10001</span></span></td>
<td><span data-ttu-id="e524a-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-855">Electricity</span></span></td>
<td><span data-ttu-id="e524a-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-856">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="e524a-857">2,852.60</span></span></td>
<td><span data-ttu-id="e524a-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-859">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-859">CC003</span></span></td>
<td><span data-ttu-id="e524a-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-860">Assembly</span></span></td>
<td><span data-ttu-id="e524a-861">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-861">10001</span></span></td>
<td><span data-ttu-id="e524a-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-862">Electricity</span></span></td>
<td><span data-ttu-id="e524a-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-863">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="e524a-864">-713.75</span></span></td>
<td><span data-ttu-id="e524a-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-866">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-867">Product 1</span></span></td>
<td><span data-ttu-id="e524a-868">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-868">10001</span></span></td>
<td><span data-ttu-id="e524a-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-869">Electricity</span></span></td>
<td><span data-ttu-id="e524a-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-870">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-871">535.31</span><span class="sxs-lookup"><span data-stu-id="e524a-871">535.31</span></span></td>
<td><span data-ttu-id="e524a-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-873">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-874">Product 2</span></span></td>
<td><span data-ttu-id="e524a-875">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-875">10001</span></span></td>
<td><span data-ttu-id="e524a-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-876">Electricity</span></span></td>
<td><span data-ttu-id="e524a-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-877">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-878">178.44</span><span class="sxs-lookup"><span data-stu-id="e524a-878">178.44</span></span></td>
<td><span data-ttu-id="e524a-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-880">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-880">CC003</span></span></td>
<td><span data-ttu-id="e524a-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-881">Assembly</span></span></td>
<td><span data-ttu-id="e524a-882">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-882">10001</span></span></td>
<td><span data-ttu-id="e524a-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-883">Electricity</span></span></td>
<td><span data-ttu-id="e524a-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-884">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="e524a-885">-5,982.83</span></span></td>
<td><span data-ttu-id="e524a-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-887">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-888">Product 1</span></span></td>
<td><span data-ttu-id="e524a-889">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-889">10001</span></span></td>
<td><span data-ttu-id="e524a-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-890">Electricity</span></span></td>
<td><span data-ttu-id="e524a-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-891">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="e524a-892">4,487.12</span></span></td>
<td><span data-ttu-id="e524a-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-894">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-895">Product 2</span></span></td>
<td><span data-ttu-id="e524a-896">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-896">10001</span></span></td>
<td><span data-ttu-id="e524a-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-897">Electricity</span></span></td>
<td><span data-ttu-id="e524a-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-898">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="e524a-899">1,495.71</span></span></td>
<td><span data-ttu-id="e524a-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-901">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-901">CC003</span></span></td>
<td><span data-ttu-id="e524a-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-902">Assembly</span></span></td>
<td><span data-ttu-id="e524a-903">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-903">10001</span></span></td>
<td><span data-ttu-id="e524a-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-904">Electricity</span></span></td>
<td><span data-ttu-id="e524a-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-905">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="e524a-906">-286.25</span></span></td>
<td><span data-ttu-id="e524a-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-908">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-909">Product 1</span></span></td>
<td><span data-ttu-id="e524a-910">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-910">10001</span></span></td>
<td><span data-ttu-id="e524a-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-911">Electricity</span></span></td>
<td><span data-ttu-id="e524a-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-912">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-913">241.05</span><span class="sxs-lookup"><span data-stu-id="e524a-913">241.05</span></span></td>
<td><span data-ttu-id="e524a-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-915">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-916">Product 2</span></span></td>
<td><span data-ttu-id="e524a-917">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-917">10001</span></span></td>
<td><span data-ttu-id="e524a-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-918">Electricity</span></span></td>
<td><span data-ttu-id="e524a-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-919">Fixed cost</span></span></td>
<td><span data-ttu-id="e524a-920">45.20</span><span class="sxs-lookup"><span data-stu-id="e524a-920">45.20</span></span></td>
<td><span data-ttu-id="e524a-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-922">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-922">CC003</span></span></td>
<td><span data-ttu-id="e524a-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e524a-923">Assembly</span></span></td>
<td><span data-ttu-id="e524a-924">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-924">10001</span></span></td>
<td><span data-ttu-id="e524a-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-925">Electricity</span></span></td>
<td><span data-ttu-id="e524a-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-926">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="e524a-927">-2,977.17</span></span></td>
<td><span data-ttu-id="e524a-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-929">Prod 1</span></span></td>
<td><span data-ttu-id="e524a-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e524a-930">Product 1</span></span></td>
<td><span data-ttu-id="e524a-931">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-931">10001</span></span></td>
<td><span data-ttu-id="e524a-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-932">Electricity</span></span></td>
<td><span data-ttu-id="e524a-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-933">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="e524a-934">2,507.09</span></span></td>
<td><span data-ttu-id="e524a-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e524a-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-936">Prod 2</span></span></td>
<td><span data-ttu-id="e524a-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e524a-937">Product 2</span></span></td>
<td><span data-ttu-id="e524a-938">10001</span><span class="sxs-lookup"><span data-stu-id="e524a-938">10001</span></span></td>
<td><span data-ttu-id="e524a-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e524a-939">Electricity</span></span></td>
<td><span data-ttu-id="e524a-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-940">Variable cost</span></span></td>
<td><span data-ttu-id="e524a-941">470.08</span><span class="sxs-lookup"><span data-stu-id="e524a-941">470.08</span></span></td>
<td><span data-ttu-id="e524a-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e524a-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="e524a-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="e524a-943">Conclusion</span></span>
<span data-ttu-id="e524a-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="e524a-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="e524a-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="e524a-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="e524a-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="e524a-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="e524a-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="e524a-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e524a-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="e524a-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e524a-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="e524a-950">Razem</span><span class="sxs-lookup"><span data-stu-id="e524a-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="e524a-951">CC099</span><span class="sxs-lookup"><span data-stu-id="e524a-951">CC099</span></span></th>
<th><span data-ttu-id="e524a-952">CC001</span><span class="sxs-lookup"><span data-stu-id="e524a-952">CC001</span></span></th>
<th><span data-ttu-id="e524a-953">CC002</span><span class="sxs-lookup"><span data-stu-id="e524a-953">CC002</span></span></th>
<th><span data-ttu-id="e524a-954">CC003</span><span class="sxs-lookup"><span data-stu-id="e524a-954">CC003</span></span></th>
<th><span data-ttu-id="e524a-955">CC004</span><span class="sxs-lookup"><span data-stu-id="e524a-955">CC004</span></span></th>
<th><span data-ttu-id="e524a-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e524a-956">Proj 1</span></span></th>
<th><span data-ttu-id="e524a-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e524a-957">Proj 2</span></span></th>
<th><span data-ttu-id="e524a-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e524a-958">Prod 1</span></span></th>
<th><span data-ttu-id="e524a-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e524a-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="e524a-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="e524a-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="e524a-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="e524a-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="e524a-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-971">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="e524a-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e524a-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-973">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-974">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-975">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-976">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-977">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="e524a-978">776.36</span><span class="sxs-lookup"><span data-stu-id="e524a-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-979">223.64</span><span class="sxs-lookup"><span data-stu-id="e524a-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="e524a-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e524a-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-982">000</span><span class="sxs-lookup"><span data-stu-id="e524a-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-983">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-984">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-985">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-986">0,00</span><span class="sxs-lookup"><span data-stu-id="e524a-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-987">30.00</span><span class="sxs-lookup"><span data-stu-id="e524a-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-988">10,00</span><span class="sxs-lookup"><span data-stu-id="e524a-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="e524a-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="e524a-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e524a-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="e524a-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="e524a-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="e524a-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="e524a-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="e524a-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="e524a-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="e524a-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="e524a-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="e524a-996">Aby uzyskać więcej informacji, [Zasady akumulacji kosztów i obliczanie narzutu](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="e524a-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



