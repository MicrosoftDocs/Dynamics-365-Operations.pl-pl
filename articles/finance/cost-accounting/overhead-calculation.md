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
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: d60248f2bd6774b2e9afdb3632b6eb31d67349ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009525"
---
# <a name="overhead-calculation"></a><span data-ttu-id="dcff8-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="dcff8-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dcff8-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="dcff8-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="dcff8-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="dcff8-105">Term definition</span></span>
---------------

<span data-ttu-id="dcff8-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="dcff8-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="dcff8-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="dcff8-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="dcff8-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="dcff8-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="dcff8-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="dcff8-109">Rent</span></span>
-   <span data-ttu-id="dcff8-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-110">Electricity</span></span>
-   <span data-ttu-id="dcff8-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="dcff8-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="dcff8-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="dcff8-112">Overhead calculation overview</span></span>
<span data-ttu-id="dcff8-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="dcff8-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="dcff8-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="dcff8-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="dcff8-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="dcff8-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="dcff8-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="dcff8-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="dcff8-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="dcff8-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="dcff8-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="dcff8-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="dcff8-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="dcff8-119">Version type</span></span>
-   <span data-ttu-id="dcff8-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="dcff8-120">Date and time</span></span>
-   <span data-ttu-id="dcff8-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="dcff8-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="dcff8-122">Fiscal year</span></span>
-   <span data-ttu-id="dcff8-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="dcff8-123">Fiscal period</span></span>

<span data-ttu-id="dcff8-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="dcff8-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="dcff8-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="dcff8-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="dcff8-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="dcff8-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="dcff8-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="dcff8-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="dcff8-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="dcff8-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="dcff8-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="dcff8-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="dcff8-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="dcff8-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="dcff8-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="dcff8-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="dcff8-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="dcff8-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="dcff8-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="dcff8-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="dcff8-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="dcff8-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dcff8-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dcff8-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="dcff8-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="dcff8-140">Main account</span></span></th>
<th><span data-ttu-id="dcff8-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="dcff8-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="dcff8-143">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-143">CC099</span></span></td>
<td><span data-ttu-id="dcff8-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-144">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-145">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-145">10001</span></span></td>
<td><span data-ttu-id="dcff8-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-146">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="dcff8-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="dcff8-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="dcff8-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="dcff8-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="dcff8-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-151">Define the cost behavior rule</span></span>

<span data-ttu-id="dcff8-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="dcff8-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="dcff8-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="dcff8-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="dcff8-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="dcff8-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="dcff8-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="dcff8-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="dcff8-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="dcff8-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="dcff8-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="dcff8-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dcff8-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="dcff8-160">Journal</span></span></th>
<th><span data-ttu-id="dcff8-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="dcff8-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dcff8-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="dcff8-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dcff8-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="dcff8-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-164">00001</span><span class="sxs-lookup"><span data-stu-id="dcff8-164">00001</span></span></td>
<td><span data-ttu-id="dcff8-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="dcff8-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="dcff8-166">Fiscal</span></span></td>
<td><span data-ttu-id="dcff8-167">2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-167">2017</span></span></td>
<td><span data-ttu-id="dcff8-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-168">Period 1</span></span></td>
<td><span data-ttu-id="dcff8-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="dcff8-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="dcff8-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dcff8-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="dcff8-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-173">Cost element</span></span></th>
<th><span data-ttu-id="dcff8-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-174">Cost behavior</span></span></th>
<th><span data-ttu-id="dcff8-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="dcff8-177">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-177">CC099</span></span></td>
<td><span data-ttu-id="dcff8-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-178">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-179">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-179">10001</span></span></td>
<td><span data-ttu-id="dcff8-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-180">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="dcff8-181">Unclassified</span></span></td>
<td><span data-ttu-id="dcff8-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dcff8-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-185">Cost element</span></span></th>
<th><span data-ttu-id="dcff8-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-186">Cost behavior</span></span></th>
<th><span data-ttu-id="dcff8-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-187">Amount</span></span></th>
<th><span data-ttu-id="dcff8-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="dcff8-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-189">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-189">CC099</span></span></td>
<td><span data-ttu-id="dcff8-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-190">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-191">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-191">10001</span></span></td>
<td><span data-ttu-id="dcff8-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-192">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="dcff8-193">Unclassified</span></span></td>
<td><span data-ttu-id="dcff8-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-194">10,000.00</span></span></td>
<td><span data-ttu-id="dcff8-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-196">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-196">CC099</span></span></td>
<td><span data-ttu-id="dcff8-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-197">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-198">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-198">10001</span></span></td>
<td><span data-ttu-id="dcff8-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-199">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="dcff8-200">Unclassified</span></span></td>
<td><span data-ttu-id="dcff8-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-201">-10,000.00</span></span></td>
<td><span data-ttu-id="dcff8-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-203">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-203">CC099</span></span></td>
<td><span data-ttu-id="dcff8-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-204">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-205">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-205">10001</span></span></td>
<td><span data-ttu-id="dcff8-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-206">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-207">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-208">1,000.00</span></span></td>
<td><span data-ttu-id="dcff8-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-210">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-210">CC099</span></span></td>
<td><span data-ttu-id="dcff8-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-211">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-212">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-212">10001</span></span></td>
<td><span data-ttu-id="dcff8-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-213">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-214">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-215">9,000.00</span></span></td>
<td><span data-ttu-id="dcff8-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="dcff8-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="dcff8-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="dcff8-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="dcff8-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="dcff8-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="dcff8-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-221">Define the cost distribution rule</span></span>

<span data-ttu-id="dcff8-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="dcff8-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="dcff8-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="dcff8-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="dcff8-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="dcff8-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="dcff8-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="dcff8-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="dcff8-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="dcff8-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="dcff8-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-228">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-229">kWh</span><span class="sxs-lookup"><span data-stu-id="dcff8-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-230">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-230">CC001</span></span></td>
<td><span data-ttu-id="dcff8-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-231">HR</span></span></td>
<td><span data-ttu-id="dcff8-232">1 000</span><span class="sxs-lookup"><span data-stu-id="dcff8-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-233">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-233">CC002</span></span></td>
<td><span data-ttu-id="dcff8-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-234">Finance</span></span></td>
<td><span data-ttu-id="dcff8-235">6,000</span><span class="sxs-lookup"><span data-stu-id="dcff8-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-236">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-236">CC003</span></span></td>
<td><span data-ttu-id="dcff8-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-237">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-238">0</span><span class="sxs-lookup"><span data-stu-id="dcff8-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="dcff8-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-240">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="dcff8-241">Magnitude</span></span></th>
<th><span data-ttu-id="dcff8-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="dcff8-242">Allocation factor</span></span></th>
<th><span data-ttu-id="dcff8-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-244">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-244">CC001</span></span></td>
<td><span data-ttu-id="dcff8-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-245">HR</span></span></td>
<td><span data-ttu-id="dcff8-246">1 000</span><span class="sxs-lookup"><span data-stu-id="dcff8-246">1,000</span></span></td>
<td><span data-ttu-id="dcff8-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="dcff8-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="dcff8-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-249">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-249">CC002</span></span></td>
<td><span data-ttu-id="dcff8-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-250">Finance</span></span></td>
<td><span data-ttu-id="dcff8-251">6,000</span><span class="sxs-lookup"><span data-stu-id="dcff8-251">6,000</span></span></td>
<td><span data-ttu-id="dcff8-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="dcff8-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="dcff8-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-254">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-254">CC003</span></span></td>
<td><span data-ttu-id="dcff8-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-255">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-256">0</span><span class="sxs-lookup"><span data-stu-id="dcff8-256">0</span></span></td>
<td><span data-ttu-id="dcff8-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="dcff8-258">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="dcff8-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="dcff8-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="dcff8-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-261">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="dcff8-262">Formula</span></span></th>
<th><span data-ttu-id="dcff8-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="dcff8-263">Magnitude</span></span></th>
<th><span data-ttu-id="dcff8-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="dcff8-264">Allocation factor</span></span></th>
<th><span data-ttu-id="dcff8-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-266">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-266">CC001</span></span></td>
<td><span data-ttu-id="dcff8-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-267">HR</span></span></td>
<td><span data-ttu-id="dcff8-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="dcff8-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="dcff8-269">1</span><span class="sxs-lookup"><span data-stu-id="dcff8-269">1</span></span></td>
<td><span data-ttu-id="dcff8-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="dcff8-271">500.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-272">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-272">CC002</span></span></td>
<td><span data-ttu-id="dcff8-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-273">Finance</span></span></td>
<td><span data-ttu-id="dcff8-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="dcff8-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="dcff8-275">1</span><span class="sxs-lookup"><span data-stu-id="dcff8-275">1</span></span></td>
<td><span data-ttu-id="dcff8-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="dcff8-277">500.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-278">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-278">CC003</span></span></td>
<td><span data-ttu-id="dcff8-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-279">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="dcff8-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="dcff8-281">0</span><span class="sxs-lookup"><span data-stu-id="dcff8-281">0</span></span></td>
<td><span data-ttu-id="dcff8-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="dcff8-283">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="dcff8-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="dcff8-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dcff8-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="dcff8-285">Journal</span></span></th>
<th><span data-ttu-id="dcff8-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="dcff8-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dcff8-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="dcff8-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dcff8-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="dcff8-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-289">00002</span><span class="sxs-lookup"><span data-stu-id="dcff8-289">00002</span></span></td>
<td><span data-ttu-id="dcff8-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="dcff8-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="dcff8-291">Fiscal</span></span></td>
<td><span data-ttu-id="dcff8-292">2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-292">2017</span></span></td>
<td><span data-ttu-id="dcff8-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-293">Period 1</span></span></td>
<td><span data-ttu-id="dcff8-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="dcff8-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="dcff8-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dcff8-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="dcff8-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-298">Cost element</span></span></th>
<th><span data-ttu-id="dcff8-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-299">Cost behavior</span></span></th>
<th><span data-ttu-id="dcff8-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-302">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-302">CC099</span></span></td>
<td><span data-ttu-id="dcff8-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-303">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-304">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-304">10001</span></span></td>
<td><span data-ttu-id="dcff8-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-305">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-306">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-309">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-309">CC099</span></span></td>
<td><span data-ttu-id="dcff8-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-310">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-311">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-311">10001</span></span></td>
<td><span data-ttu-id="dcff8-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-312">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-313">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dcff8-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-317">Cost element</span></span></th>
<th><span data-ttu-id="dcff8-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-318">Cost behavior</span></span></th>
<th><span data-ttu-id="dcff8-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-319">Amount</span></span></th>
<th><span data-ttu-id="dcff8-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="dcff8-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-321">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-321">CC099</span></span></td>
<td><span data-ttu-id="dcff8-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-322">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-323">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-323">10001</span></span></td>
<td><span data-ttu-id="dcff8-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-324">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-325">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-326">-1,000.00</span></span></td>
<td><span data-ttu-id="dcff8-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-328">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-328">CC001</span></span></td>
<td><span data-ttu-id="dcff8-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-329">HR</span></span></td>
<td><span data-ttu-id="dcff8-330">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-330">10001</span></span></td>
<td><span data-ttu-id="dcff8-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-331">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-332">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-333">500.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-333">500.00</span></span></td>
<td><span data-ttu-id="dcff8-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-335">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-335">CC002</span></span></td>
<td><span data-ttu-id="dcff8-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-336">Finance</span></span></td>
<td><span data-ttu-id="dcff8-337">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-337">10001</span></span></td>
<td><span data-ttu-id="dcff8-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-338">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-339">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-340">500.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-340">500.00</span></span></td>
<td><span data-ttu-id="dcff8-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-342">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-342">CC099</span></span></td>
<td><span data-ttu-id="dcff8-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-343">Default cost center</span></span></td>
<td><span data-ttu-id="dcff8-344">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-344">10001</span></span></td>
<td><span data-ttu-id="dcff8-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-345">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-346">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-347">-9,000.00</span></span></td>
<td><span data-ttu-id="dcff8-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-349">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-349">CC001</span></span></td>
<td><span data-ttu-id="dcff8-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-350">HR</span></span></td>
<td><span data-ttu-id="dcff8-351">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-351">10001</span></span></td>
<td><span data-ttu-id="dcff8-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-352">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-353">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="dcff8-354">1,285.71</span></span></td>
<td><span data-ttu-id="dcff8-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-356">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-356">CC002</span></span></td>
<td><span data-ttu-id="dcff8-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-357">Finance</span></span></td>
<td><span data-ttu-id="dcff8-358">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-358">10001</span></span></td>
<td><span data-ttu-id="dcff8-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-359">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-360">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="dcff8-361">7,714.29</span></span></td>
<td><span data-ttu-id="dcff8-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="dcff8-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="dcff8-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="dcff8-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="dcff8-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="dcff8-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="dcff8-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="dcff8-367">Define the overhead rate</span></span>

<span data-ttu-id="dcff8-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="dcff8-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="dcff8-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="dcff8-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-370">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="dcff8-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-372">Proj 1</span></span></td>
<td><span data-ttu-id="dcff8-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-373">Project 1</span></span></td>
<td><span data-ttu-id="dcff8-374">3</span><span class="sxs-lookup"><span data-stu-id="dcff8-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-375">Proj 2</span></span></td>
<td><span data-ttu-id="dcff8-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-376">Project 2</span></span></td>
<td><span data-ttu-id="dcff8-377">1</span><span class="sxs-lookup"><span data-stu-id="dcff8-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="dcff8-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-379">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-380">Cost element</span></span></th>
<th><span data-ttu-id="dcff8-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-381">Cost behavior</span></span></th>
<th><span data-ttu-id="dcff8-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="dcff8-382">Units</span></span></th>
<th><span data-ttu-id="dcff8-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="dcff8-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-384">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-384">CC001</span></span></td>
<td><span data-ttu-id="dcff8-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-385">HR</span></span></td>
<td><span data-ttu-id="dcff8-386">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-386">10001</span></span></td>
<td><span data-ttu-id="dcff8-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-387">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-388">1</span><span class="sxs-lookup"><span data-stu-id="dcff8-388">1</span></span></td>
<td><span data-ttu-id="dcff8-389">10</span><span class="sxs-lookup"><span data-stu-id="dcff8-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-391">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="dcff8-392">Magnitude</span></span></th>
<th><span data-ttu-id="dcff8-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-393">Cost element</span></span></th>
<th><span data-ttu-id="dcff8-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="dcff8-394">Allocation factor</span></span></th>
<th><span data-ttu-id="dcff8-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-396">Proj 1</span></span></td>
<td><span data-ttu-id="dcff8-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-397">Project 1</span></span></td>
<td><span data-ttu-id="dcff8-398">3</span><span class="sxs-lookup"><span data-stu-id="dcff8-398">3</span></span></td>
<td><span data-ttu-id="dcff8-399">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-399">10001</span></span></td>
<td><span data-ttu-id="dcff8-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="dcff8-401">30.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-402">Proj 2</span></span></td>
<td><span data-ttu-id="dcff8-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-403">Project 2</span></span></td>
<td><span data-ttu-id="dcff8-404">1</span><span class="sxs-lookup"><span data-stu-id="dcff8-404">1</span></span></td>
<td><span data-ttu-id="dcff8-405">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-405">10001</span></span></td>
<td><span data-ttu-id="dcff8-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="dcff8-407">10,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="dcff8-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="dcff8-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dcff8-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="dcff8-409">Journal</span></span></th>
<th><span data-ttu-id="dcff8-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="dcff8-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dcff8-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="dcff8-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dcff8-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="dcff8-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-413">00003</span><span class="sxs-lookup"><span data-stu-id="dcff8-413">00003</span></span></td>
<td><span data-ttu-id="dcff8-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="dcff8-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="dcff8-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="dcff8-415">Fiscal</span></span></td>
<td><span data-ttu-id="dcff8-416">2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-416">2017</span></span></td>
<td><span data-ttu-id="dcff8-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-417">Period 1</span></span></td>
<td><span data-ttu-id="dcff8-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="dcff8-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="dcff8-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dcff8-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="dcff8-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-421">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="dcff8-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-424">Proj 1</span></span></td>
<td><span data-ttu-id="dcff8-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="dcff8-426">3,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-428">Proj 2</span></span></td>
<td><span data-ttu-id="dcff8-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="dcff8-430">1.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dcff8-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-433">Cost element</span></span></th>
<th><span data-ttu-id="dcff8-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-434">Cost behavior</span></span></th>
<th><span data-ttu-id="dcff8-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-435">Amount</span></span></th>
<th><span data-ttu-id="dcff8-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="dcff8-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="dcff8-437">CC0001</span></span></td>
<td><span data-ttu-id="dcff8-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-438">HR</span></span></td>
<td><span data-ttu-id="dcff8-439">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-439">10001</span></span></td>
<td><span data-ttu-id="dcff8-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-440">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-441">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-442">-30.00</span></span></td>
<td><span data-ttu-id="dcff8-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-444">Proj 1</span></span></td>
<td><span data-ttu-id="dcff8-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="dcff8-446">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-446">10001</span></span></td>
<td><span data-ttu-id="dcff8-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-447">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-448">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-449">30.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-449">30.00</span></span></td>
<td><span data-ttu-id="dcff8-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-451">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-451">CC001</span></span></td>
<td><span data-ttu-id="dcff8-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-452">HR</span></span></td>
<td><span data-ttu-id="dcff8-453">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-453">10001</span></span></td>
<td><span data-ttu-id="dcff8-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-454">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-455">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-456">-10.00</span></span></td>
<td><span data-ttu-id="dcff8-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-458">Proj 2</span></span></td>
<td><span data-ttu-id="dcff8-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="dcff8-460">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-460">10001</span></span></td>
<td><span data-ttu-id="dcff8-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-461">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-462">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-463">10,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-463">10.00</span></span></td>
<td><span data-ttu-id="dcff8-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="dcff8-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="dcff8-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="dcff8-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="dcff8-468">Aplikacja Finance obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="dcff8-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="dcff8-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="dcff8-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="dcff8-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="dcff8-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="dcff8-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="dcff8-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="dcff8-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="dcff8-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="dcff8-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-475">Define the cost allocation</span></span>

<span data-ttu-id="dcff8-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="dcff8-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="dcff8-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="dcff8-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-479">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="dcff8-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-481">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-481">CC002</span></span></td>
<td><span data-ttu-id="dcff8-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-482">Finance</span></span></td>
<td><span data-ttu-id="dcff8-483">35</span><span class="sxs-lookup"><span data-stu-id="dcff8-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-484">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-484">CC003</span></span></td>
<td><span data-ttu-id="dcff8-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-485">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-486">55</span><span class="sxs-lookup"><span data-stu-id="dcff8-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-487">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-487">CC004</span></span></td>
<td><span data-ttu-id="dcff8-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-488">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-489">10</span><span class="sxs-lookup"><span data-stu-id="dcff8-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="dcff8-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="dcff8-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-492">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="dcff8-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-494">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-494">CC003</span></span></td>
<td><span data-ttu-id="dcff8-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-495">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-496">65</span><span class="sxs-lookup"><span data-stu-id="dcff8-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-497">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-497">CC004</span></span></td>
<td><span data-ttu-id="dcff8-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-498">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-499">35</span><span class="sxs-lookup"><span data-stu-id="dcff8-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="dcff8-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="dcff8-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-502">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="dcff8-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-504">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-505">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-506">60</span><span class="sxs-lookup"><span data-stu-id="dcff8-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-507">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-508">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-509">20</span><span class="sxs-lookup"><span data-stu-id="dcff8-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="dcff8-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="dcff8-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-512">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="dcff8-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-514">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-515">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-516">80</span><span class="sxs-lookup"><span data-stu-id="dcff8-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-517">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-518">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-519">15</span><span class="sxs-lookup"><span data-stu-id="dcff8-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="dcff8-520">Miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="dcff8-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="dcff8-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="dcff8-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="dcff8-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="dcff8-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-523">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="dcff8-524">Magnitude</span></span></th>
<th><span data-ttu-id="dcff8-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="dcff8-525">Allocation factor</span></span></th>
<th><span data-ttu-id="dcff8-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-526">Amount</span></span></th>
<th><span data-ttu-id="dcff8-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-528">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-528">CC002</span></span></td>
<td><span data-ttu-id="dcff8-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-529">Finance</span></span></td>
<td><span data-ttu-id="dcff8-530">35</span><span class="sxs-lookup"><span data-stu-id="dcff8-530">35</span></span></td>
<td><span data-ttu-id="dcff8-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="dcff8-532">175.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-532">175.00</span></span></td>
<td><span data-ttu-id="dcff8-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-534">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-534">CC003</span></span></td>
<td><span data-ttu-id="dcff8-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-535">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-536">55</span><span class="sxs-lookup"><span data-stu-id="dcff8-536">55</span></span></td>
<td><span data-ttu-id="dcff8-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="dcff8-538">275.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-538">275.00</span></span></td>
<td><span data-ttu-id="dcff8-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-540">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-540">CC004</span></span></td>
<td><span data-ttu-id="dcff8-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-541">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-542">10</span><span class="sxs-lookup"><span data-stu-id="dcff8-542">10</span></span></td>
<td><span data-ttu-id="dcff8-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="dcff8-544">50,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-544">50.00</span></span></td>
<td><span data-ttu-id="dcff8-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-546">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-546">CC002</span></span></td>
<td><span data-ttu-id="dcff8-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-547">Finance</span></span></td>
<td><span data-ttu-id="dcff8-548">35</span><span class="sxs-lookup"><span data-stu-id="dcff8-548">35</span></span></td>
<td><span data-ttu-id="dcff8-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="dcff8-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="dcff8-550">436.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-550">436.00</span></span></td>
<td><span data-ttu-id="dcff8-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-552">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-552">CC003</span></span></td>
<td><span data-ttu-id="dcff8-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-553">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-554">55</span><span class="sxs-lookup"><span data-stu-id="dcff8-554">55</span></span></td>
<td><span data-ttu-id="dcff8-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="dcff8-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="dcff8-556">685.14</span><span class="sxs-lookup"><span data-stu-id="dcff8-556">685.14</span></span></td>
<td><span data-ttu-id="dcff8-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-558">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-558">CC004</span></span></td>
<td><span data-ttu-id="dcff8-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-559">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-560">10</span><span class="sxs-lookup"><span data-stu-id="dcff8-560">10</span></span></td>
<td><span data-ttu-id="dcff8-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="dcff8-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="dcff8-562">124.57</span><span class="sxs-lookup"><span data-stu-id="dcff8-562">124.57</span></span></td>
<td><span data-ttu-id="dcff8-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="dcff8-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-565">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="dcff8-566">Magnitude</span></span></th>
<th><span data-ttu-id="dcff8-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="dcff8-567">Allocation factor</span></span></th>
<th><span data-ttu-id="dcff8-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-568">Amount</span></span></th>
<th><span data-ttu-id="dcff8-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-570">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-570">CC003</span></span></td>
<td><span data-ttu-id="dcff8-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-571">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-572">65</span><span class="sxs-lookup"><span data-stu-id="dcff8-572">65</span></span></td>
<td><span data-ttu-id="dcff8-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="dcff8-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="dcff8-574">438.75</span><span class="sxs-lookup"><span data-stu-id="dcff8-574">438.75</span></span></td>
<td><span data-ttu-id="dcff8-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-576">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-576">CC004</span></span></td>
<td><span data-ttu-id="dcff8-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-577">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-578">35</span><span class="sxs-lookup"><span data-stu-id="dcff8-578">35</span></span></td>
<td><span data-ttu-id="dcff8-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="dcff8-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="dcff8-580">236.25</span><span class="sxs-lookup"><span data-stu-id="dcff8-580">236.25</span></span></td>
<td><span data-ttu-id="dcff8-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-582">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-582">CC003</span></span></td>
<td><span data-ttu-id="dcff8-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-583">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-584">65</span><span class="sxs-lookup"><span data-stu-id="dcff8-584">65</span></span></td>
<td><span data-ttu-id="dcff8-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="dcff8-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="dcff8-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="dcff8-586">5,297.69</span></span></td>
<td><span data-ttu-id="dcff8-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-588">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-588">CC004</span></span></td>
<td><span data-ttu-id="dcff8-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-589">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-590">35</span><span class="sxs-lookup"><span data-stu-id="dcff8-590">35</span></span></td>
<td><span data-ttu-id="dcff8-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="dcff8-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="dcff8-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="dcff8-592">2,852.60</span></span></td>
<td><span data-ttu-id="dcff8-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="dcff8-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-595">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="dcff8-596">Magnitude</span></span></th>
<th><span data-ttu-id="dcff8-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="dcff8-597">Allocation factor</span></span></th>
<th><span data-ttu-id="dcff8-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-598">Amount</span></span></th>
<th><span data-ttu-id="dcff8-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-600">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-601">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-602">60</span><span class="sxs-lookup"><span data-stu-id="dcff8-602">60</span></span></td>
<td><span data-ttu-id="dcff8-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="dcff8-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="dcff8-604">535.31</span><span class="sxs-lookup"><span data-stu-id="dcff8-604">535.31</span></span></td>
<td><span data-ttu-id="dcff8-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-606">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-607">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-608">20</span><span class="sxs-lookup"><span data-stu-id="dcff8-608">20</span></span></td>
<td><span data-ttu-id="dcff8-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="dcff8-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="dcff8-610">178.44</span><span class="sxs-lookup"><span data-stu-id="dcff8-610">178.44</span></span></td>
<td><span data-ttu-id="dcff8-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-612">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-613">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-614">60</span><span class="sxs-lookup"><span data-stu-id="dcff8-614">60</span></span></td>
<td><span data-ttu-id="dcff8-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="dcff8-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="dcff8-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="dcff8-616">4,487.12</span></span></td>
<td><span data-ttu-id="dcff8-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-618">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-619">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-620">20</span><span class="sxs-lookup"><span data-stu-id="dcff8-620">20</span></span></td>
<td><span data-ttu-id="dcff8-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="dcff8-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="dcff8-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="dcff8-622">1,495.71</span></span></td>
<td><span data-ttu-id="dcff8-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dcff8-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="dcff8-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-625">Cost object</span></span></th>
<th><span data-ttu-id="dcff8-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="dcff8-626">Magnitude</span></span></th>
<th><span data-ttu-id="dcff8-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="dcff8-627">Allocation factor</span></span></th>
<th><span data-ttu-id="dcff8-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-628">Amount</span></span></th>
<th><span data-ttu-id="dcff8-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-630">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-631">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-632">80</span><span class="sxs-lookup"><span data-stu-id="dcff8-632">80</span></span></td>
<td><span data-ttu-id="dcff8-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="dcff8-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="dcff8-634">241.05</span><span class="sxs-lookup"><span data-stu-id="dcff8-634">241.05</span></span></td>
<td><span data-ttu-id="dcff8-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-636">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-637">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-638">15</span><span class="sxs-lookup"><span data-stu-id="dcff8-638">15</span></span></td>
<td><span data-ttu-id="dcff8-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="dcff8-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="dcff8-640">45.20</span><span class="sxs-lookup"><span data-stu-id="dcff8-640">45.20</span></span></td>
<td><span data-ttu-id="dcff8-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-642">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-643">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-644">80</span><span class="sxs-lookup"><span data-stu-id="dcff8-644">80</span></span></td>
<td><span data-ttu-id="dcff8-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="dcff8-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="dcff8-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="dcff8-646">2,507.09</span></span></td>
<td><span data-ttu-id="dcff8-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-648">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-649">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-650">15</span><span class="sxs-lookup"><span data-stu-id="dcff8-650">15</span></span></td>
<td><span data-ttu-id="dcff8-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="dcff8-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="dcff8-652">470.08</span><span class="sxs-lookup"><span data-stu-id="dcff8-652">470.08</span></span></td>
<td><span data-ttu-id="dcff8-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="dcff8-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="dcff8-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dcff8-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="dcff8-655">Journal</span></span></th>
<th><span data-ttu-id="dcff8-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="dcff8-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dcff8-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="dcff8-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dcff8-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="dcff8-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-659">00004</span><span class="sxs-lookup"><span data-stu-id="dcff8-659">00004</span></span></td>
<td><span data-ttu-id="dcff8-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="dcff8-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="dcff8-661">Fiscal</span></span></td>
<td><span data-ttu-id="dcff8-662">2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-662">2017</span></span></td>
<td><span data-ttu-id="dcff8-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-663">Period 1</span></span></td>
<td><span data-ttu-id="dcff8-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="dcff8-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="dcff8-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dcff8-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="dcff8-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-668">Cost element</span></span></th>
<th><span data-ttu-id="dcff8-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-669">Cost behavior</span></span></th>
<th><span data-ttu-id="dcff8-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-672">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-672">CC001</span></span></td>
<td><span data-ttu-id="dcff8-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-673">HR</span></span></td>
<td><span data-ttu-id="dcff8-674">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-674">10001</span></span></td>
<td><span data-ttu-id="dcff8-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-675">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-676">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-677">500.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-679">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-679">CC001</span></span></td>
<td><span data-ttu-id="dcff8-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-680">HR</span></span></td>
<td><span data-ttu-id="dcff8-681">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-681">10001</span></span></td>
<td><span data-ttu-id="dcff8-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-682">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-683">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="dcff8-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-686">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-686">CC002</span></span></td>
<td><span data-ttu-id="dcff8-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-687">Finance</span></span></td>
<td><span data-ttu-id="dcff8-688">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-688">10001</span></span></td>
<td><span data-ttu-id="dcff8-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-689">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-690">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-691">675.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-693">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-693">CC002</span></span></td>
<td><span data-ttu-id="dcff8-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-694">Finance</span></span></td>
<td><span data-ttu-id="dcff8-695">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-695">10001</span></span></td>
<td><span data-ttu-id="dcff8-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-696">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-697">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="dcff8-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-700">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-700">CC003</span></span></td>
<td><span data-ttu-id="dcff8-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-701">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-702">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-702">10001</span></span></td>
<td><span data-ttu-id="dcff8-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-703">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-704">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-705">713.75</span><span class="sxs-lookup"><span data-stu-id="dcff8-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-707">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-707">CC003</span></span></td>
<td><span data-ttu-id="dcff8-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-708">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-709">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-709">10001</span></span></td>
<td><span data-ttu-id="dcff8-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-710">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-711">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="dcff8-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-714">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-714">CC003</span></span></td>
<td><span data-ttu-id="dcff8-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-715">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-716">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-716">10001</span></span></td>
<td><span data-ttu-id="dcff8-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-717">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-718">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-719">286.25</span><span class="sxs-lookup"><span data-stu-id="dcff8-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-721">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-721">CC003</span></span></td>
<td><span data-ttu-id="dcff8-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-722">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-723">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-723">10001</span></span></td>
<td><span data-ttu-id="dcff8-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-724">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-725">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="dcff8-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-728">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-729">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-730">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-730">10001</span></span></td>
<td><span data-ttu-id="dcff8-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-731">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-732">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-733">776.36</span><span class="sxs-lookup"><span data-stu-id="dcff8-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-735">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-736">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-737">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-737">10001</span></span></td>
<td><span data-ttu-id="dcff8-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-738">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-739">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="dcff8-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-742">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-743">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-744">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-744">10001</span></span></td>
<td><span data-ttu-id="dcff8-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-745">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-746">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-747">223.64</span><span class="sxs-lookup"><span data-stu-id="dcff8-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="dcff8-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-749">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-750">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-751">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-751">10001</span></span></td>
<td><span data-ttu-id="dcff8-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-752">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-753">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="dcff8-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dcff8-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dcff8-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dcff8-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-757">Cost element</span></span></th>
<th><span data-ttu-id="dcff8-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-758">Cost behavior</span></span></th>
<th><span data-ttu-id="dcff8-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="dcff8-759">Amount</span></span></th>
<th><span data-ttu-id="dcff8-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="dcff8-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dcff8-761">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-761">CC001</span></span></td>
<td><span data-ttu-id="dcff8-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-762">HR</span></span></td>
<td><span data-ttu-id="dcff8-763">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-763">10001</span></span></td>
<td><span data-ttu-id="dcff8-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-764">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-765">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-766">-500.00</span></span></td>
<td><span data-ttu-id="dcff8-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-768">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-768">CC002</span></span></td>
<td><span data-ttu-id="dcff8-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-769">Finance</span></span></td>
<td><span data-ttu-id="dcff8-770">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-770">10001</span></span></td>
<td><span data-ttu-id="dcff8-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-771">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-772">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-773">175.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-773">175.00</span></span></td>
<td><span data-ttu-id="dcff8-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-775">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-775">CC003</span></span></td>
<td><span data-ttu-id="dcff8-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-776">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-777">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-777">10001</span></span></td>
<td><span data-ttu-id="dcff8-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-778">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-779">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-780">275.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-780">275.00</span></span></td>
<td><span data-ttu-id="dcff8-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-782">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-782">CC004</span></span></td>
<td><span data-ttu-id="dcff8-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-783">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-784">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-784">10001</span></span></td>
<td><span data-ttu-id="dcff8-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-785">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-786">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-787">50,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-787">50,00</span></span></td>
<td><span data-ttu-id="dcff8-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-789">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-789">CC001</span></span></td>
<td><span data-ttu-id="dcff8-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="dcff8-790">HR</span></span></td>
<td><span data-ttu-id="dcff8-791">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-791">10001</span></span></td>
<td><span data-ttu-id="dcff8-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-792">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-793">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="dcff8-794">-1,245.71</span></span></td>
<td><span data-ttu-id="dcff8-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-796">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-796">CC002</span></span></td>
<td><span data-ttu-id="dcff8-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-797">Finance</span></span></td>
<td><span data-ttu-id="dcff8-798">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-798">10001</span></span></td>
<td><span data-ttu-id="dcff8-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-799">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-800">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-801">436.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-801">436.00</span></span></td>
<td><span data-ttu-id="dcff8-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-803">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-803">CC003</span></span></td>
<td><span data-ttu-id="dcff8-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-804">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-805">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-805">10001</span></span></td>
<td><span data-ttu-id="dcff8-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-806">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-807">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-808">685.14</span><span class="sxs-lookup"><span data-stu-id="dcff8-808">685.14</span></span></td>
<td><span data-ttu-id="dcff8-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-810">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-810">CC004</span></span></td>
<td><span data-ttu-id="dcff8-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-811">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-812">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-812">10001</span></span></td>
<td><span data-ttu-id="dcff8-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-813">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-814">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-815">124.57</span><span class="sxs-lookup"><span data-stu-id="dcff8-815">124.57</span></span></td>
<td><span data-ttu-id="dcff8-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-817">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-817">CC002</span></span></td>
<td><span data-ttu-id="dcff8-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-818">Finance</span></span></td>
<td><span data-ttu-id="dcff8-819">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-819">10001</span></span></td>
<td><span data-ttu-id="dcff8-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-820">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-821">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-822">-675.00</span></span></td>
<td><span data-ttu-id="dcff8-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-824">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-824">CC003</span></span></td>
<td><span data-ttu-id="dcff8-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-825">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-826">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-826">10001</span></span></td>
<td><span data-ttu-id="dcff8-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-827">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-828">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-829">438.75</span><span class="sxs-lookup"><span data-stu-id="dcff8-829">438.75</span></span></td>
<td><span data-ttu-id="dcff8-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-831">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-831">CC004</span></span></td>
<td><span data-ttu-id="dcff8-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-832">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-833">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-833">10001</span></span></td>
<td><span data-ttu-id="dcff8-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-834">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-835">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-836">236.25</span><span class="sxs-lookup"><span data-stu-id="dcff8-836">236.25</span></span></td>
<td><span data-ttu-id="dcff8-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-838">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-838">CC002</span></span></td>
<td><span data-ttu-id="dcff8-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="dcff8-839">Finance</span></span></td>
<td><span data-ttu-id="dcff8-840">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-840">10001</span></span></td>
<td><span data-ttu-id="dcff8-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-841">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-842">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="dcff8-843">-8,150.29</span></span></td>
<td><span data-ttu-id="dcff8-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-845">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-845">CC003</span></span></td>
<td><span data-ttu-id="dcff8-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-846">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-847">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-847">10001</span></span></td>
<td><span data-ttu-id="dcff8-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-848">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-849">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="dcff8-850">5,297.69</span></span></td>
<td><span data-ttu-id="dcff8-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-852">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-852">CC004</span></span></td>
<td><span data-ttu-id="dcff8-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="dcff8-853">Packaging</span></span></td>
<td><span data-ttu-id="dcff8-854">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-854">10001</span></span></td>
<td><span data-ttu-id="dcff8-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-855">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-856">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="dcff8-857">2,852.60</span></span></td>
<td><span data-ttu-id="dcff8-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-859">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-859">CC003</span></span></td>
<td><span data-ttu-id="dcff8-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-860">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-861">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-861">10001</span></span></td>
<td><span data-ttu-id="dcff8-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-862">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-863">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="dcff8-864">-713.75</span></span></td>
<td><span data-ttu-id="dcff8-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-866">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-867">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-868">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-868">10001</span></span></td>
<td><span data-ttu-id="dcff8-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-869">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-870">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-871">535.31</span><span class="sxs-lookup"><span data-stu-id="dcff8-871">535.31</span></span></td>
<td><span data-ttu-id="dcff8-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-873">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-874">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-875">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-875">10001</span></span></td>
<td><span data-ttu-id="dcff8-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-876">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-877">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-878">178.44</span><span class="sxs-lookup"><span data-stu-id="dcff8-878">178.44</span></span></td>
<td><span data-ttu-id="dcff8-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-880">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-880">CC003</span></span></td>
<td><span data-ttu-id="dcff8-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-881">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-882">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-882">10001</span></span></td>
<td><span data-ttu-id="dcff8-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-883">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-884">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="dcff8-885">-5,982.83</span></span></td>
<td><span data-ttu-id="dcff8-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-887">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-888">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-889">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-889">10001</span></span></td>
<td><span data-ttu-id="dcff8-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-890">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-891">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="dcff8-892">4,487.12</span></span></td>
<td><span data-ttu-id="dcff8-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-894">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-895">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-896">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-896">10001</span></span></td>
<td><span data-ttu-id="dcff8-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-897">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-898">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="dcff8-899">1,495.71</span></span></td>
<td><span data-ttu-id="dcff8-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-901">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-901">CC003</span></span></td>
<td><span data-ttu-id="dcff8-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-902">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-903">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-903">10001</span></span></td>
<td><span data-ttu-id="dcff8-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-904">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-905">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="dcff8-906">-286.25</span></span></td>
<td><span data-ttu-id="dcff8-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-908">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-909">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-910">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-910">10001</span></span></td>
<td><span data-ttu-id="dcff8-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-911">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-912">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-913">241.05</span><span class="sxs-lookup"><span data-stu-id="dcff8-913">241.05</span></span></td>
<td><span data-ttu-id="dcff8-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-915">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-916">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-917">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-917">10001</span></span></td>
<td><span data-ttu-id="dcff8-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-918">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-919">Fixed cost</span></span></td>
<td><span data-ttu-id="dcff8-920">45.20</span><span class="sxs-lookup"><span data-stu-id="dcff8-920">45.20</span></span></td>
<td><span data-ttu-id="dcff8-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-922">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-922">CC003</span></span></td>
<td><span data-ttu-id="dcff8-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="dcff8-923">Assembly</span></span></td>
<td><span data-ttu-id="dcff8-924">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-924">10001</span></span></td>
<td><span data-ttu-id="dcff8-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-925">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-926">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="dcff8-927">-2,977.17</span></span></td>
<td><span data-ttu-id="dcff8-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-929">Prod 1</span></span></td>
<td><span data-ttu-id="dcff8-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-930">Product 1</span></span></td>
<td><span data-ttu-id="dcff8-931">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-931">10001</span></span></td>
<td><span data-ttu-id="dcff8-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-932">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-933">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="dcff8-934">2,507.09</span></span></td>
<td><span data-ttu-id="dcff8-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dcff8-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-936">Prod 2</span></span></td>
<td><span data-ttu-id="dcff8-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-937">Product 2</span></span></td>
<td><span data-ttu-id="dcff8-938">10001</span><span class="sxs-lookup"><span data-stu-id="dcff8-938">10001</span></span></td>
<td><span data-ttu-id="dcff8-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="dcff8-939">Electricity</span></span></td>
<td><span data-ttu-id="dcff8-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-940">Variable cost</span></span></td>
<td><span data-ttu-id="dcff8-941">470.08</span><span class="sxs-lookup"><span data-stu-id="dcff8-941">470.08</span></span></td>
<td><span data-ttu-id="dcff8-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="dcff8-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="dcff8-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="dcff8-943">Conclusion</span></span>
<span data-ttu-id="dcff8-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="dcff8-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="dcff8-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="dcff8-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="dcff8-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="dcff8-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="dcff8-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="dcff8-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="dcff8-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="dcff8-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="dcff8-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="dcff8-950">Razem</span><span class="sxs-lookup"><span data-stu-id="dcff8-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="dcff8-951">CC099</span><span class="sxs-lookup"><span data-stu-id="dcff8-951">CC099</span></span></th>
<th><span data-ttu-id="dcff8-952">CC001</span><span class="sxs-lookup"><span data-stu-id="dcff8-952">CC001</span></span></th>
<th><span data-ttu-id="dcff8-953">CC002</span><span class="sxs-lookup"><span data-stu-id="dcff8-953">CC002</span></span></th>
<th><span data-ttu-id="dcff8-954">CC003</span><span class="sxs-lookup"><span data-stu-id="dcff8-954">CC003</span></span></th>
<th><span data-ttu-id="dcff8-955">CC004</span><span class="sxs-lookup"><span data-stu-id="dcff8-955">CC004</span></span></th>
<th><span data-ttu-id="dcff8-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-956">Proj 1</span></span></th>
<th><span data-ttu-id="dcff8-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-957">Proj 2</span></span></th>
<th><span data-ttu-id="dcff8-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="dcff8-958">Prod 1</span></span></th>
<th><span data-ttu-id="dcff8-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="dcff8-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="dcff8-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="dcff8-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="dcff8-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="dcff8-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-971">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="dcff8-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="dcff8-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-973">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-974">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-975">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-976">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-977">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-978">776.36</span><span class="sxs-lookup"><span data-stu-id="dcff8-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-979">223.64</span><span class="sxs-lookup"><span data-stu-id="dcff8-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="dcff8-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="dcff8-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-982">000</span><span class="sxs-lookup"><span data-stu-id="dcff8-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-983">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-984">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-985">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-986">0,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-987">30.00</span><span class="sxs-lookup"><span data-stu-id="dcff8-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-988">10,00</span><span class="sxs-lookup"><span data-stu-id="dcff8-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="dcff8-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="dcff8-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dcff8-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="dcff8-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="dcff8-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="dcff8-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="dcff8-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="dcff8-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="dcff8-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="dcff8-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="dcff8-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="dcff8-996">Aby uzyskać więcej informacji, [Zasady akumulacji kosztów i obliczanie narzutu](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="dcff8-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



