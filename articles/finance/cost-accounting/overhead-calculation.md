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
ms.openlocfilehash: 882804141a6b520e2420343958c7a6b02a7e09ae
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208854"
---
# <a name="overhead-calculation"></a><span data-ttu-id="83da3-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="83da3-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83da3-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="83da3-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="83da3-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="83da3-105">Term definition</span></span>
---------------

<span data-ttu-id="83da3-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="83da3-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="83da3-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="83da3-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="83da3-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="83da3-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="83da3-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="83da3-109">Rent</span></span>
-   <span data-ttu-id="83da3-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-110">Electricity</span></span>
-   <span data-ttu-id="83da3-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="83da3-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="83da3-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="83da3-112">Overhead calculation overview</span></span>
<span data-ttu-id="83da3-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="83da3-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="83da3-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="83da3-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="83da3-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="83da3-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="83da3-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="83da3-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="83da3-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="83da3-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="83da3-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="83da3-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="83da3-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="83da3-119">Version type</span></span>
-   <span data-ttu-id="83da3-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="83da3-120">Date and time</span></span>
-   <span data-ttu-id="83da3-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="83da3-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="83da3-122">Fiscal year</span></span>
-   <span data-ttu-id="83da3-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="83da3-123">Fiscal period</span></span>

<span data-ttu-id="83da3-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="83da3-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="83da3-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="83da3-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="83da3-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="83da3-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="83da3-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="83da3-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="83da3-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="83da3-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="83da3-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="83da3-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="83da3-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="83da3-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="83da3-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="83da3-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="83da3-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="83da3-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="83da3-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="83da3-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="83da3-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="83da3-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="83da3-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="83da3-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="83da3-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="83da3-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="83da3-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="83da3-140">Main account</span></span></th>
<th><span data-ttu-id="83da3-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="83da3-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="83da3-143">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-143">CC099</span></span></td>
<td><span data-ttu-id="83da3-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-144">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-145">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-145">10001</span></span></td>
<td><span data-ttu-id="83da3-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-146">Electricity</span></span></td>
<td><span data-ttu-id="83da3-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="83da3-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="83da3-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="83da3-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="83da3-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="83da3-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="83da3-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-151">Define the cost behavior rule</span></span>

<span data-ttu-id="83da3-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="83da3-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="83da3-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="83da3-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="83da3-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="83da3-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="83da3-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="83da3-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="83da3-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="83da3-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="83da3-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="83da3-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="83da3-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="83da3-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="83da3-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="83da3-160">Journal</span></span></th>
<th><span data-ttu-id="83da3-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="83da3-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="83da3-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="83da3-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="83da3-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="83da3-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-164">00001</span><span class="sxs-lookup"><span data-stu-id="83da3-164">00001</span></span></td>
<td><span data-ttu-id="83da3-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="83da3-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="83da3-166">Fiscal</span></span></td>
<td><span data-ttu-id="83da3-167">2017</span><span class="sxs-lookup"><span data-stu-id="83da3-167">2017</span></span></td>
<td><span data-ttu-id="83da3-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="83da3-168">Period 1</span></span></td>
<td><span data-ttu-id="83da3-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="83da3-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="83da3-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="83da3-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="83da3-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="83da3-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-173">Cost element</span></span></th>
<th><span data-ttu-id="83da3-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-174">Cost behavior</span></span></th>
<th><span data-ttu-id="83da3-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="83da3-177">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-177">CC099</span></span></td>
<td><span data-ttu-id="83da3-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-178">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-179">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-179">10001</span></span></td>
<td><span data-ttu-id="83da3-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-180">Electricity</span></span></td>
<td><span data-ttu-id="83da3-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="83da3-181">Unclassified</span></span></td>
<td><span data-ttu-id="83da3-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="83da3-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="83da3-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-185">Cost element</span></span></th>
<th><span data-ttu-id="83da3-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-186">Cost behavior</span></span></th>
<th><span data-ttu-id="83da3-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-187">Amount</span></span></th>
<th><span data-ttu-id="83da3-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="83da3-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-189">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-189">CC099</span></span></td>
<td><span data-ttu-id="83da3-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-190">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-191">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-191">10001</span></span></td>
<td><span data-ttu-id="83da3-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-192">Electricity</span></span></td>
<td><span data-ttu-id="83da3-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="83da3-193">Unclassified</span></span></td>
<td><span data-ttu-id="83da3-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="83da3-194">10,000.00</span></span></td>
<td><span data-ttu-id="83da3-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-196">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-196">CC099</span></span></td>
<td><span data-ttu-id="83da3-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-197">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-198">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-198">10001</span></span></td>
<td><span data-ttu-id="83da3-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-199">Electricity</span></span></td>
<td><span data-ttu-id="83da3-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="83da3-200">Unclassified</span></span></td>
<td><span data-ttu-id="83da3-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-201">-10,000.00</span></span></td>
<td><span data-ttu-id="83da3-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-203">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-203">CC099</span></span></td>
<td><span data-ttu-id="83da3-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-204">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-205">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-205">10001</span></span></td>
<td><span data-ttu-id="83da3-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-206">Electricity</span></span></td>
<td><span data-ttu-id="83da3-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-207">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-208">1,000.00</span></span></td>
<td><span data-ttu-id="83da3-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-210">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-210">CC099</span></span></td>
<td><span data-ttu-id="83da3-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-211">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-212">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-212">10001</span></span></td>
<td><span data-ttu-id="83da3-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-213">Electricity</span></span></td>
<td><span data-ttu-id="83da3-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-214">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="83da3-215">9,000.00</span></span></td>
<td><span data-ttu-id="83da3-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="83da3-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="83da3-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="83da3-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="83da3-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="83da3-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="83da3-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="83da3-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-221">Define the cost distribution rule</span></span>

<span data-ttu-id="83da3-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="83da3-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="83da3-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="83da3-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="83da3-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="83da3-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="83da3-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="83da3-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="83da3-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="83da3-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="83da3-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="83da3-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-228">Cost object</span></span></th>
<th><span data-ttu-id="83da3-229">kWh</span><span class="sxs-lookup"><span data-stu-id="83da3-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-230">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-230">CC001</span></span></td>
<td><span data-ttu-id="83da3-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-231">HR</span></span></td>
<td><span data-ttu-id="83da3-232">1 000</span><span class="sxs-lookup"><span data-stu-id="83da3-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-233">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-233">CC002</span></span></td>
<td><span data-ttu-id="83da3-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-234">Finance</span></span></td>
<td><span data-ttu-id="83da3-235">6,000</span><span class="sxs-lookup"><span data-stu-id="83da3-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-236">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-236">CC003</span></span></td>
<td><span data-ttu-id="83da3-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-237">Assembly</span></span></td>
<td><span data-ttu-id="83da3-238">0</span><span class="sxs-lookup"><span data-stu-id="83da3-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="83da3-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-240">Cost object</span></span></th>
<th><span data-ttu-id="83da3-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="83da3-241">Magnitude</span></span></th>
<th><span data-ttu-id="83da3-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="83da3-242">Allocation factor</span></span></th>
<th><span data-ttu-id="83da3-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-244">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-244">CC001</span></span></td>
<td><span data-ttu-id="83da3-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-245">HR</span></span></td>
<td><span data-ttu-id="83da3-246">1 000</span><span class="sxs-lookup"><span data-stu-id="83da3-246">1,000</span></span></td>
<td><span data-ttu-id="83da3-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="83da3-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="83da3-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-249">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-249">CC002</span></span></td>
<td><span data-ttu-id="83da3-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-250">Finance</span></span></td>
<td><span data-ttu-id="83da3-251">6,000</span><span class="sxs-lookup"><span data-stu-id="83da3-251">6,000</span></span></td>
<td><span data-ttu-id="83da3-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="83da3-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="83da3-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-254">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-254">CC003</span></span></td>
<td><span data-ttu-id="83da3-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-255">Assembly</span></span></td>
<td><span data-ttu-id="83da3-256">0</span><span class="sxs-lookup"><span data-stu-id="83da3-256">0</span></span></td>
<td><span data-ttu-id="83da3-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="83da3-258">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="83da3-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="83da3-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="83da3-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-261">Cost object</span></span></th>
<th><span data-ttu-id="83da3-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="83da3-262">Formula</span></span></th>
<th><span data-ttu-id="83da3-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="83da3-263">Magnitude</span></span></th>
<th><span data-ttu-id="83da3-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="83da3-264">Allocation factor</span></span></th>
<th><span data-ttu-id="83da3-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-266">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-266">CC001</span></span></td>
<td><span data-ttu-id="83da3-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-267">HR</span></span></td>
<td><span data-ttu-id="83da3-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="83da3-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="83da3-269">1</span><span class="sxs-lookup"><span data-stu-id="83da3-269">1</span></span></td>
<td><span data-ttu-id="83da3-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="83da3-271">500.00</span><span class="sxs-lookup"><span data-stu-id="83da3-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-272">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-272">CC002</span></span></td>
<td><span data-ttu-id="83da3-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-273">Finance</span></span></td>
<td><span data-ttu-id="83da3-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="83da3-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="83da3-275">1</span><span class="sxs-lookup"><span data-stu-id="83da3-275">1</span></span></td>
<td><span data-ttu-id="83da3-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="83da3-277">500.00</span><span class="sxs-lookup"><span data-stu-id="83da3-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-278">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-278">CC003</span></span></td>
<td><span data-ttu-id="83da3-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-279">Assembly</span></span></td>
<td><span data-ttu-id="83da3-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="83da3-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="83da3-281">0</span><span class="sxs-lookup"><span data-stu-id="83da3-281">0</span></span></td>
<td><span data-ttu-id="83da3-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="83da3-283">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="83da3-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="83da3-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="83da3-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="83da3-285">Journal</span></span></th>
<th><span data-ttu-id="83da3-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="83da3-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="83da3-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="83da3-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="83da3-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="83da3-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-289">00002</span><span class="sxs-lookup"><span data-stu-id="83da3-289">00002</span></span></td>
<td><span data-ttu-id="83da3-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="83da3-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="83da3-291">Fiscal</span></span></td>
<td><span data-ttu-id="83da3-292">2017</span><span class="sxs-lookup"><span data-stu-id="83da3-292">2017</span></span></td>
<td><span data-ttu-id="83da3-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="83da3-293">Period 1</span></span></td>
<td><span data-ttu-id="83da3-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="83da3-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="83da3-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="83da3-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="83da3-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="83da3-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-298">Cost element</span></span></th>
<th><span data-ttu-id="83da3-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-299">Cost behavior</span></span></th>
<th><span data-ttu-id="83da3-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-302">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-302">CC099</span></span></td>
<td><span data-ttu-id="83da3-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-303">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-304">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-304">10001</span></span></td>
<td><span data-ttu-id="83da3-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-305">Electricity</span></span></td>
<td><span data-ttu-id="83da3-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-306">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-309">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-309">CC099</span></span></td>
<td><span data-ttu-id="83da3-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-310">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-311">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-311">10001</span></span></td>
<td><span data-ttu-id="83da3-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-312">Electricity</span></span></td>
<td><span data-ttu-id="83da3-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-313">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="83da3-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="83da3-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-317">Cost element</span></span></th>
<th><span data-ttu-id="83da3-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-318">Cost behavior</span></span></th>
<th><span data-ttu-id="83da3-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-319">Amount</span></span></th>
<th><span data-ttu-id="83da3-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="83da3-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-321">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-321">CC099</span></span></td>
<td><span data-ttu-id="83da3-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-322">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-323">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-323">10001</span></span></td>
<td><span data-ttu-id="83da3-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-324">Electricity</span></span></td>
<td><span data-ttu-id="83da3-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-325">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-326">-1,000.00</span></span></td>
<td><span data-ttu-id="83da3-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-328">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-328">CC001</span></span></td>
<td><span data-ttu-id="83da3-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-329">HR</span></span></td>
<td><span data-ttu-id="83da3-330">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-330">10001</span></span></td>
<td><span data-ttu-id="83da3-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-331">Electricity</span></span></td>
<td><span data-ttu-id="83da3-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-332">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-333">500.00</span><span class="sxs-lookup"><span data-stu-id="83da3-333">500.00</span></span></td>
<td><span data-ttu-id="83da3-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-335">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-335">CC002</span></span></td>
<td><span data-ttu-id="83da3-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-336">Finance</span></span></td>
<td><span data-ttu-id="83da3-337">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-337">10001</span></span></td>
<td><span data-ttu-id="83da3-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-338">Electricity</span></span></td>
<td><span data-ttu-id="83da3-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-339">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-340">500.00</span><span class="sxs-lookup"><span data-stu-id="83da3-340">500.00</span></span></td>
<td><span data-ttu-id="83da3-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-342">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-342">CC099</span></span></td>
<td><span data-ttu-id="83da3-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-343">Default cost center</span></span></td>
<td><span data-ttu-id="83da3-344">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-344">10001</span></span></td>
<td><span data-ttu-id="83da3-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-345">Electricity</span></span></td>
<td><span data-ttu-id="83da3-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-346">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="83da3-347">-9,000.00</span></span></td>
<td><span data-ttu-id="83da3-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-349">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-349">CC001</span></span></td>
<td><span data-ttu-id="83da3-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-350">HR</span></span></td>
<td><span data-ttu-id="83da3-351">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-351">10001</span></span></td>
<td><span data-ttu-id="83da3-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-352">Electricity</span></span></td>
<td><span data-ttu-id="83da3-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-353">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="83da3-354">1,285.71</span></span></td>
<td><span data-ttu-id="83da3-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-356">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-356">CC002</span></span></td>
<td><span data-ttu-id="83da3-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-357">Finance</span></span></td>
<td><span data-ttu-id="83da3-358">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-358">10001</span></span></td>
<td><span data-ttu-id="83da3-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-359">Electricity</span></span></td>
<td><span data-ttu-id="83da3-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-360">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="83da3-361">7,714.29</span></span></td>
<td><span data-ttu-id="83da3-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="83da3-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="83da3-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="83da3-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="83da3-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="83da3-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="83da3-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="83da3-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="83da3-367">Define the overhead rate</span></span>

<span data-ttu-id="83da3-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="83da3-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="83da3-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="83da3-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-370">Cost object</span></span></th>
<th><span data-ttu-id="83da3-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="83da3-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="83da3-372">Proj 1</span></span></td>
<td><span data-ttu-id="83da3-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-373">Project 1</span></span></td>
<td><span data-ttu-id="83da3-374">3</span><span class="sxs-lookup"><span data-stu-id="83da3-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="83da3-375">Proj 2</span></span></td>
<td><span data-ttu-id="83da3-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-376">Project 2</span></span></td>
<td><span data-ttu-id="83da3-377">1</span><span class="sxs-lookup"><span data-stu-id="83da3-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="83da3-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-379">Cost object</span></span></th>
<th><span data-ttu-id="83da3-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-380">Cost element</span></span></th>
<th><span data-ttu-id="83da3-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-381">Cost behavior</span></span></th>
<th><span data-ttu-id="83da3-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="83da3-382">Units</span></span></th>
<th><span data-ttu-id="83da3-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="83da3-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-384">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-384">CC001</span></span></td>
<td><span data-ttu-id="83da3-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-385">HR</span></span></td>
<td><span data-ttu-id="83da3-386">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-386">10001</span></span></td>
<td><span data-ttu-id="83da3-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-387">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-388">1</span><span class="sxs-lookup"><span data-stu-id="83da3-388">1</span></span></td>
<td><span data-ttu-id="83da3-389">10</span><span class="sxs-lookup"><span data-stu-id="83da3-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="83da3-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-391">Cost object</span></span></th>
<th><span data-ttu-id="83da3-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="83da3-392">Magnitude</span></span></th>
<th><span data-ttu-id="83da3-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-393">Cost element</span></span></th>
<th><span data-ttu-id="83da3-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="83da3-394">Allocation factor</span></span></th>
<th><span data-ttu-id="83da3-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="83da3-396">Proj 1</span></span></td>
<td><span data-ttu-id="83da3-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-397">Project 1</span></span></td>
<td><span data-ttu-id="83da3-398">3</span><span class="sxs-lookup"><span data-stu-id="83da3-398">3</span></span></td>
<td><span data-ttu-id="83da3-399">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-399">10001</span></span></td>
<td><span data-ttu-id="83da3-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="83da3-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="83da3-401">30.00</span><span class="sxs-lookup"><span data-stu-id="83da3-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="83da3-402">Proj 2</span></span></td>
<td><span data-ttu-id="83da3-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-403">Project 2</span></span></td>
<td><span data-ttu-id="83da3-404">1</span><span class="sxs-lookup"><span data-stu-id="83da3-404">1</span></span></td>
<td><span data-ttu-id="83da3-405">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-405">10001</span></span></td>
<td><span data-ttu-id="83da3-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="83da3-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="83da3-407">10,00</span><span class="sxs-lookup"><span data-stu-id="83da3-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="83da3-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="83da3-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="83da3-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="83da3-409">Journal</span></span></th>
<th><span data-ttu-id="83da3-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="83da3-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="83da3-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="83da3-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="83da3-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="83da3-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-413">00003</span><span class="sxs-lookup"><span data-stu-id="83da3-413">00003</span></span></td>
<td><span data-ttu-id="83da3-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="83da3-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="83da3-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="83da3-415">Fiscal</span></span></td>
<td><span data-ttu-id="83da3-416">2017</span><span class="sxs-lookup"><span data-stu-id="83da3-416">2017</span></span></td>
<td><span data-ttu-id="83da3-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="83da3-417">Period 1</span></span></td>
<td><span data-ttu-id="83da3-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="83da3-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="83da3-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="83da3-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="83da3-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="83da3-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-421">Cost object</span></span></th>
<th><span data-ttu-id="83da3-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="83da3-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="83da3-424">Proj 1</span></span></td>
<td><span data-ttu-id="83da3-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="83da3-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="83da3-426">3,00</span><span class="sxs-lookup"><span data-stu-id="83da3-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="83da3-428">Proj 2</span></span></td>
<td><span data-ttu-id="83da3-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="83da3-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="83da3-430">1.00</span><span class="sxs-lookup"><span data-stu-id="83da3-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="83da3-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-433">Cost element</span></span></th>
<th><span data-ttu-id="83da3-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-434">Cost behavior</span></span></th>
<th><span data-ttu-id="83da3-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-435">Amount</span></span></th>
<th><span data-ttu-id="83da3-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="83da3-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="83da3-437">CC0001</span></span></td>
<td><span data-ttu-id="83da3-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-438">HR</span></span></td>
<td><span data-ttu-id="83da3-439">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-439">10001</span></span></td>
<td><span data-ttu-id="83da3-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-440">Electricity</span></span></td>
<td><span data-ttu-id="83da3-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-441">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="83da3-442">-30.00</span></span></td>
<td><span data-ttu-id="83da3-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="83da3-444">Proj 1</span></span></td>
<td><span data-ttu-id="83da3-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="83da3-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="83da3-446">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-446">10001</span></span></td>
<td><span data-ttu-id="83da3-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-447">Electricity</span></span></td>
<td><span data-ttu-id="83da3-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-448">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-449">30.00</span><span class="sxs-lookup"><span data-stu-id="83da3-449">30.00</span></span></td>
<td><span data-ttu-id="83da3-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-451">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-451">CC001</span></span></td>
<td><span data-ttu-id="83da3-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-452">HR</span></span></td>
<td><span data-ttu-id="83da3-453">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-453">10001</span></span></td>
<td><span data-ttu-id="83da3-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-454">Electricity</span></span></td>
<td><span data-ttu-id="83da3-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-455">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="83da3-456">-10.00</span></span></td>
<td><span data-ttu-id="83da3-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="83da3-458">Proj 2</span></span></td>
<td><span data-ttu-id="83da3-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="83da3-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="83da3-460">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-460">10001</span></span></td>
<td><span data-ttu-id="83da3-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-461">Electricity</span></span></td>
<td><span data-ttu-id="83da3-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-462">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-463">10,00</span><span class="sxs-lookup"><span data-stu-id="83da3-463">10.00</span></span></td>
<td><span data-ttu-id="83da3-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="83da3-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="83da3-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="83da3-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="83da3-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="83da3-468">Aplikacja Finance obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="83da3-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="83da3-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="83da3-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="83da3-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="83da3-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="83da3-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="83da3-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="83da3-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="83da3-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="83da3-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="83da3-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="83da3-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-475">Define the cost allocation</span></span>

<span data-ttu-id="83da3-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="83da3-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="83da3-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="83da3-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-479">Cost object</span></span></th>
<th><span data-ttu-id="83da3-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="83da3-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-481">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-481">CC002</span></span></td>
<td><span data-ttu-id="83da3-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-482">Finance</span></span></td>
<td><span data-ttu-id="83da3-483">35</span><span class="sxs-lookup"><span data-stu-id="83da3-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-484">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-484">CC003</span></span></td>
<td><span data-ttu-id="83da3-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-485">Assembly</span></span></td>
<td><span data-ttu-id="83da3-486">55</span><span class="sxs-lookup"><span data-stu-id="83da3-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-487">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-487">CC004</span></span></td>
<td><span data-ttu-id="83da3-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-488">Packaging</span></span></td>
<td><span data-ttu-id="83da3-489">10</span><span class="sxs-lookup"><span data-stu-id="83da3-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="83da3-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="83da3-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-492">Cost object</span></span></th>
<th><span data-ttu-id="83da3-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="83da3-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-494">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-494">CC003</span></span></td>
<td><span data-ttu-id="83da3-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-495">Assembly</span></span></td>
<td><span data-ttu-id="83da3-496">65</span><span class="sxs-lookup"><span data-stu-id="83da3-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-497">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-497">CC004</span></span></td>
<td><span data-ttu-id="83da3-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-498">Packaging</span></span></td>
<td><span data-ttu-id="83da3-499">35</span><span class="sxs-lookup"><span data-stu-id="83da3-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="83da3-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="83da3-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-502">Cost object</span></span></th>
<th><span data-ttu-id="83da3-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="83da3-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-504">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-505">Product 1</span></span></td>
<td><span data-ttu-id="83da3-506">60</span><span class="sxs-lookup"><span data-stu-id="83da3-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-507">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-508">Product 2</span></span></td>
<td><span data-ttu-id="83da3-509">20</span><span class="sxs-lookup"><span data-stu-id="83da3-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="83da3-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="83da3-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-512">Cost object</span></span></th>
<th><span data-ttu-id="83da3-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="83da3-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-514">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-515">Product 1</span></span></td>
<td><span data-ttu-id="83da3-516">80</span><span class="sxs-lookup"><span data-stu-id="83da3-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-517">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-518">Product 2</span></span></td>
<td><span data-ttu-id="83da3-519">15</span><span class="sxs-lookup"><span data-stu-id="83da3-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="83da3-520">Miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="83da3-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="83da3-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="83da3-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="83da3-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="83da3-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-523">Cost object</span></span></th>
<th><span data-ttu-id="83da3-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="83da3-524">Magnitude</span></span></th>
<th><span data-ttu-id="83da3-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="83da3-525">Allocation factor</span></span></th>
<th><span data-ttu-id="83da3-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-526">Amount</span></span></th>
<th><span data-ttu-id="83da3-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-528">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-528">CC002</span></span></td>
<td><span data-ttu-id="83da3-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-529">Finance</span></span></td>
<td><span data-ttu-id="83da3-530">35</span><span class="sxs-lookup"><span data-stu-id="83da3-530">35</span></span></td>
<td><span data-ttu-id="83da3-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="83da3-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="83da3-532">175.00</span><span class="sxs-lookup"><span data-stu-id="83da3-532">175.00</span></span></td>
<td><span data-ttu-id="83da3-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-534">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-534">CC003</span></span></td>
<td><span data-ttu-id="83da3-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-535">Assembly</span></span></td>
<td><span data-ttu-id="83da3-536">55</span><span class="sxs-lookup"><span data-stu-id="83da3-536">55</span></span></td>
<td><span data-ttu-id="83da3-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="83da3-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="83da3-538">275.00</span><span class="sxs-lookup"><span data-stu-id="83da3-538">275.00</span></span></td>
<td><span data-ttu-id="83da3-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-540">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-540">CC004</span></span></td>
<td><span data-ttu-id="83da3-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-541">Packaging</span></span></td>
<td><span data-ttu-id="83da3-542">10</span><span class="sxs-lookup"><span data-stu-id="83da3-542">10</span></span></td>
<td><span data-ttu-id="83da3-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="83da3-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="83da3-544">50,00</span><span class="sxs-lookup"><span data-stu-id="83da3-544">50.00</span></span></td>
<td><span data-ttu-id="83da3-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-546">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-546">CC002</span></span></td>
<td><span data-ttu-id="83da3-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-547">Finance</span></span></td>
<td><span data-ttu-id="83da3-548">35</span><span class="sxs-lookup"><span data-stu-id="83da3-548">35</span></span></td>
<td><span data-ttu-id="83da3-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="83da3-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="83da3-550">436.00</span><span class="sxs-lookup"><span data-stu-id="83da3-550">436.00</span></span></td>
<td><span data-ttu-id="83da3-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-552">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-552">CC003</span></span></td>
<td><span data-ttu-id="83da3-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-553">Assembly</span></span></td>
<td><span data-ttu-id="83da3-554">55</span><span class="sxs-lookup"><span data-stu-id="83da3-554">55</span></span></td>
<td><span data-ttu-id="83da3-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="83da3-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="83da3-556">685.14</span><span class="sxs-lookup"><span data-stu-id="83da3-556">685.14</span></span></td>
<td><span data-ttu-id="83da3-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-558">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-558">CC004</span></span></td>
<td><span data-ttu-id="83da3-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-559">Packaging</span></span></td>
<td><span data-ttu-id="83da3-560">10</span><span class="sxs-lookup"><span data-stu-id="83da3-560">10</span></span></td>
<td><span data-ttu-id="83da3-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="83da3-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="83da3-562">124.57</span><span class="sxs-lookup"><span data-stu-id="83da3-562">124.57</span></span></td>
<td><span data-ttu-id="83da3-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="83da3-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-565">Cost object</span></span></th>
<th><span data-ttu-id="83da3-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="83da3-566">Magnitude</span></span></th>
<th><span data-ttu-id="83da3-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="83da3-567">Allocation factor</span></span></th>
<th><span data-ttu-id="83da3-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-568">Amount</span></span></th>
<th><span data-ttu-id="83da3-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-570">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-570">CC003</span></span></td>
<td><span data-ttu-id="83da3-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-571">Assembly</span></span></td>
<td><span data-ttu-id="83da3-572">65</span><span class="sxs-lookup"><span data-stu-id="83da3-572">65</span></span></td>
<td><span data-ttu-id="83da3-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="83da3-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="83da3-574">438.75</span><span class="sxs-lookup"><span data-stu-id="83da3-574">438.75</span></span></td>
<td><span data-ttu-id="83da3-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-576">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-576">CC004</span></span></td>
<td><span data-ttu-id="83da3-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-577">Packaging</span></span></td>
<td><span data-ttu-id="83da3-578">35</span><span class="sxs-lookup"><span data-stu-id="83da3-578">35</span></span></td>
<td><span data-ttu-id="83da3-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="83da3-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="83da3-580">236.25</span><span class="sxs-lookup"><span data-stu-id="83da3-580">236.25</span></span></td>
<td><span data-ttu-id="83da3-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-582">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-582">CC003</span></span></td>
<td><span data-ttu-id="83da3-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-583">Assembly</span></span></td>
<td><span data-ttu-id="83da3-584">65</span><span class="sxs-lookup"><span data-stu-id="83da3-584">65</span></span></td>
<td><span data-ttu-id="83da3-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="83da3-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="83da3-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="83da3-586">5,297.69</span></span></td>
<td><span data-ttu-id="83da3-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-588">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-588">CC004</span></span></td>
<td><span data-ttu-id="83da3-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-589">Packaging</span></span></td>
<td><span data-ttu-id="83da3-590">35</span><span class="sxs-lookup"><span data-stu-id="83da3-590">35</span></span></td>
<td><span data-ttu-id="83da3-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="83da3-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="83da3-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="83da3-592">2,852.60</span></span></td>
<td><span data-ttu-id="83da3-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="83da3-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-595">Cost object</span></span></th>
<th><span data-ttu-id="83da3-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="83da3-596">Magnitude</span></span></th>
<th><span data-ttu-id="83da3-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="83da3-597">Allocation factor</span></span></th>
<th><span data-ttu-id="83da3-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-598">Amount</span></span></th>
<th><span data-ttu-id="83da3-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-600">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-601">Product 1</span></span></td>
<td><span data-ttu-id="83da3-602">60</span><span class="sxs-lookup"><span data-stu-id="83da3-602">60</span></span></td>
<td><span data-ttu-id="83da3-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="83da3-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="83da3-604">535.31</span><span class="sxs-lookup"><span data-stu-id="83da3-604">535.31</span></span></td>
<td><span data-ttu-id="83da3-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-606">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-607">Product 2</span></span></td>
<td><span data-ttu-id="83da3-608">20</span><span class="sxs-lookup"><span data-stu-id="83da3-608">20</span></span></td>
<td><span data-ttu-id="83da3-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="83da3-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="83da3-610">178.44</span><span class="sxs-lookup"><span data-stu-id="83da3-610">178.44</span></span></td>
<td><span data-ttu-id="83da3-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-612">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-613">Product 1</span></span></td>
<td><span data-ttu-id="83da3-614">60</span><span class="sxs-lookup"><span data-stu-id="83da3-614">60</span></span></td>
<td><span data-ttu-id="83da3-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="83da3-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="83da3-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="83da3-616">4,487.12</span></span></td>
<td><span data-ttu-id="83da3-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-618">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-619">Product 2</span></span></td>
<td><span data-ttu-id="83da3-620">20</span><span class="sxs-lookup"><span data-stu-id="83da3-620">20</span></span></td>
<td><span data-ttu-id="83da3-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="83da3-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="83da3-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="83da3-622">1,495.71</span></span></td>
<td><span data-ttu-id="83da3-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83da3-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="83da3-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-625">Cost object</span></span></th>
<th><span data-ttu-id="83da3-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="83da3-626">Magnitude</span></span></th>
<th><span data-ttu-id="83da3-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="83da3-627">Allocation factor</span></span></th>
<th><span data-ttu-id="83da3-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-628">Amount</span></span></th>
<th><span data-ttu-id="83da3-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-630">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-631">Product 1</span></span></td>
<td><span data-ttu-id="83da3-632">80</span><span class="sxs-lookup"><span data-stu-id="83da3-632">80</span></span></td>
<td><span data-ttu-id="83da3-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="83da3-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="83da3-634">241.05</span><span class="sxs-lookup"><span data-stu-id="83da3-634">241.05</span></span></td>
<td><span data-ttu-id="83da3-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-636">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-637">Product 2</span></span></td>
<td><span data-ttu-id="83da3-638">15</span><span class="sxs-lookup"><span data-stu-id="83da3-638">15</span></span></td>
<td><span data-ttu-id="83da3-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="83da3-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="83da3-640">45.20</span><span class="sxs-lookup"><span data-stu-id="83da3-640">45.20</span></span></td>
<td><span data-ttu-id="83da3-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-642">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-643">Product 1</span></span></td>
<td><span data-ttu-id="83da3-644">80</span><span class="sxs-lookup"><span data-stu-id="83da3-644">80</span></span></td>
<td><span data-ttu-id="83da3-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="83da3-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="83da3-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="83da3-646">2,507.09</span></span></td>
<td><span data-ttu-id="83da3-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-648">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-649">Product 2</span></span></td>
<td><span data-ttu-id="83da3-650">15</span><span class="sxs-lookup"><span data-stu-id="83da3-650">15</span></span></td>
<td><span data-ttu-id="83da3-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="83da3-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="83da3-652">470.08</span><span class="sxs-lookup"><span data-stu-id="83da3-652">470.08</span></span></td>
<td><span data-ttu-id="83da3-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="83da3-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="83da3-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="83da3-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="83da3-655">Journal</span></span></th>
<th><span data-ttu-id="83da3-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="83da3-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="83da3-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="83da3-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="83da3-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="83da3-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-659">00004</span><span class="sxs-lookup"><span data-stu-id="83da3-659">00004</span></span></td>
<td><span data-ttu-id="83da3-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="83da3-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="83da3-661">Fiscal</span></span></td>
<td><span data-ttu-id="83da3-662">2017</span><span class="sxs-lookup"><span data-stu-id="83da3-662">2017</span></span></td>
<td><span data-ttu-id="83da3-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="83da3-663">Period 1</span></span></td>
<td><span data-ttu-id="83da3-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="83da3-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="83da3-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="83da3-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="83da3-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="83da3-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-668">Cost element</span></span></th>
<th><span data-ttu-id="83da3-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-669">Cost behavior</span></span></th>
<th><span data-ttu-id="83da3-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-672">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-672">CC001</span></span></td>
<td><span data-ttu-id="83da3-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-673">HR</span></span></td>
<td><span data-ttu-id="83da3-674">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-674">10001</span></span></td>
<td><span data-ttu-id="83da3-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-675">Electricity</span></span></td>
<td><span data-ttu-id="83da3-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-676">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-677">500.00</span><span class="sxs-lookup"><span data-stu-id="83da3-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-679">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-679">CC001</span></span></td>
<td><span data-ttu-id="83da3-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-680">HR</span></span></td>
<td><span data-ttu-id="83da3-681">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-681">10001</span></span></td>
<td><span data-ttu-id="83da3-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-682">Electricity</span></span></td>
<td><span data-ttu-id="83da3-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-683">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="83da3-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-686">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-686">CC002</span></span></td>
<td><span data-ttu-id="83da3-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-687">Finance</span></span></td>
<td><span data-ttu-id="83da3-688">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-688">10001</span></span></td>
<td><span data-ttu-id="83da3-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-689">Electricity</span></span></td>
<td><span data-ttu-id="83da3-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-690">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-691">675.00</span><span class="sxs-lookup"><span data-stu-id="83da3-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-693">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-693">CC002</span></span></td>
<td><span data-ttu-id="83da3-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-694">Finance</span></span></td>
<td><span data-ttu-id="83da3-695">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-695">10001</span></span></td>
<td><span data-ttu-id="83da3-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-696">Electricity</span></span></td>
<td><span data-ttu-id="83da3-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-697">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="83da3-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-700">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-700">CC003</span></span></td>
<td><span data-ttu-id="83da3-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-701">Assembly</span></span></td>
<td><span data-ttu-id="83da3-702">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-702">10001</span></span></td>
<td><span data-ttu-id="83da3-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-703">Electricity</span></span></td>
<td><span data-ttu-id="83da3-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-704">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-705">713.75</span><span class="sxs-lookup"><span data-stu-id="83da3-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-707">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-707">CC003</span></span></td>
<td><span data-ttu-id="83da3-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-708">Assembly</span></span></td>
<td><span data-ttu-id="83da3-709">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-709">10001</span></span></td>
<td><span data-ttu-id="83da3-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-710">Electricity</span></span></td>
<td><span data-ttu-id="83da3-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-711">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="83da3-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-714">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-714">CC003</span></span></td>
<td><span data-ttu-id="83da3-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-715">Packaging</span></span></td>
<td><span data-ttu-id="83da3-716">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-716">10001</span></span></td>
<td><span data-ttu-id="83da3-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-717">Electricity</span></span></td>
<td><span data-ttu-id="83da3-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-718">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-719">286.25</span><span class="sxs-lookup"><span data-stu-id="83da3-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-721">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-721">CC003</span></span></td>
<td><span data-ttu-id="83da3-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-722">Packaging</span></span></td>
<td><span data-ttu-id="83da3-723">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-723">10001</span></span></td>
<td><span data-ttu-id="83da3-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-724">Electricity</span></span></td>
<td><span data-ttu-id="83da3-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-725">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="83da3-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-728">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-729">Product 1</span></span></td>
<td><span data-ttu-id="83da3-730">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-730">10001</span></span></td>
<td><span data-ttu-id="83da3-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-731">Electricity</span></span></td>
<td><span data-ttu-id="83da3-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-732">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-733">776.36</span><span class="sxs-lookup"><span data-stu-id="83da3-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-735">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-736">Product 1</span></span></td>
<td><span data-ttu-id="83da3-737">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-737">10001</span></span></td>
<td><span data-ttu-id="83da3-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-738">Electricity</span></span></td>
<td><span data-ttu-id="83da3-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-739">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="83da3-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-742">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-743">Product 1</span></span></td>
<td><span data-ttu-id="83da3-744">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-744">10001</span></span></td>
<td><span data-ttu-id="83da3-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-745">Electricity</span></span></td>
<td><span data-ttu-id="83da3-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-746">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-747">223.64</span><span class="sxs-lookup"><span data-stu-id="83da3-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="83da3-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-749">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-750">Product 1</span></span></td>
<td><span data-ttu-id="83da3-751">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-751">10001</span></span></td>
<td><span data-ttu-id="83da3-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-752">Electricity</span></span></td>
<td><span data-ttu-id="83da3-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-753">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="83da3-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="83da3-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="83da3-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="83da3-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-757">Cost element</span></span></th>
<th><span data-ttu-id="83da3-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-758">Cost behavior</span></span></th>
<th><span data-ttu-id="83da3-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="83da3-759">Amount</span></span></th>
<th><span data-ttu-id="83da3-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="83da3-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="83da3-761">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-761">CC001</span></span></td>
<td><span data-ttu-id="83da3-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-762">HR</span></span></td>
<td><span data-ttu-id="83da3-763">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-763">10001</span></span></td>
<td><span data-ttu-id="83da3-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-764">Electricity</span></span></td>
<td><span data-ttu-id="83da3-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-765">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="83da3-766">-500.00</span></span></td>
<td><span data-ttu-id="83da3-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-768">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-768">CC002</span></span></td>
<td><span data-ttu-id="83da3-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-769">Finance</span></span></td>
<td><span data-ttu-id="83da3-770">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-770">10001</span></span></td>
<td><span data-ttu-id="83da3-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-771">Electricity</span></span></td>
<td><span data-ttu-id="83da3-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-772">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-773">175.00</span><span class="sxs-lookup"><span data-stu-id="83da3-773">175.00</span></span></td>
<td><span data-ttu-id="83da3-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-775">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-775">CC003</span></span></td>
<td><span data-ttu-id="83da3-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-776">Assembly</span></span></td>
<td><span data-ttu-id="83da3-777">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-777">10001</span></span></td>
<td><span data-ttu-id="83da3-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-778">Electricity</span></span></td>
<td><span data-ttu-id="83da3-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-779">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-780">275.00</span><span class="sxs-lookup"><span data-stu-id="83da3-780">275.00</span></span></td>
<td><span data-ttu-id="83da3-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-782">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-782">CC004</span></span></td>
<td><span data-ttu-id="83da3-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-783">Packaging</span></span></td>
<td><span data-ttu-id="83da3-784">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-784">10001</span></span></td>
<td><span data-ttu-id="83da3-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-785">Electricity</span></span></td>
<td><span data-ttu-id="83da3-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-786">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-787">50,00</span><span class="sxs-lookup"><span data-stu-id="83da3-787">50,00</span></span></td>
<td><span data-ttu-id="83da3-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-789">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-789">CC001</span></span></td>
<td><span data-ttu-id="83da3-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="83da3-790">HR</span></span></td>
<td><span data-ttu-id="83da3-791">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-791">10001</span></span></td>
<td><span data-ttu-id="83da3-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-792">Electricity</span></span></td>
<td><span data-ttu-id="83da3-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-793">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="83da3-794">-1,245.71</span></span></td>
<td><span data-ttu-id="83da3-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-796">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-796">CC002</span></span></td>
<td><span data-ttu-id="83da3-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-797">Finance</span></span></td>
<td><span data-ttu-id="83da3-798">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-798">10001</span></span></td>
<td><span data-ttu-id="83da3-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-799">Electricity</span></span></td>
<td><span data-ttu-id="83da3-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-800">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-801">436.00</span><span class="sxs-lookup"><span data-stu-id="83da3-801">436.00</span></span></td>
<td><span data-ttu-id="83da3-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-803">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-803">CC003</span></span></td>
<td><span data-ttu-id="83da3-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-804">Assembly</span></span></td>
<td><span data-ttu-id="83da3-805">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-805">10001</span></span></td>
<td><span data-ttu-id="83da3-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-806">Electricity</span></span></td>
<td><span data-ttu-id="83da3-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-807">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-808">685.14</span><span class="sxs-lookup"><span data-stu-id="83da3-808">685.14</span></span></td>
<td><span data-ttu-id="83da3-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-810">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-810">CC004</span></span></td>
<td><span data-ttu-id="83da3-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-811">Packaging</span></span></td>
<td><span data-ttu-id="83da3-812">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-812">10001</span></span></td>
<td><span data-ttu-id="83da3-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-813">Electricity</span></span></td>
<td><span data-ttu-id="83da3-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-814">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-815">124.57</span><span class="sxs-lookup"><span data-stu-id="83da3-815">124.57</span></span></td>
<td><span data-ttu-id="83da3-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-817">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-817">CC002</span></span></td>
<td><span data-ttu-id="83da3-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-818">Finance</span></span></td>
<td><span data-ttu-id="83da3-819">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-819">10001</span></span></td>
<td><span data-ttu-id="83da3-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-820">Electricity</span></span></td>
<td><span data-ttu-id="83da3-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-821">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="83da3-822">-675.00</span></span></td>
<td><span data-ttu-id="83da3-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-824">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-824">CC003</span></span></td>
<td><span data-ttu-id="83da3-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-825">Assembly</span></span></td>
<td><span data-ttu-id="83da3-826">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-826">10001</span></span></td>
<td><span data-ttu-id="83da3-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-827">Electricity</span></span></td>
<td><span data-ttu-id="83da3-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-828">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-829">438.75</span><span class="sxs-lookup"><span data-stu-id="83da3-829">438.75</span></span></td>
<td><span data-ttu-id="83da3-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-831">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-831">CC004</span></span></td>
<td><span data-ttu-id="83da3-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-832">Packaging</span></span></td>
<td><span data-ttu-id="83da3-833">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-833">10001</span></span></td>
<td><span data-ttu-id="83da3-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-834">Electricity</span></span></td>
<td><span data-ttu-id="83da3-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-835">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-836">236.25</span><span class="sxs-lookup"><span data-stu-id="83da3-836">236.25</span></span></td>
<td><span data-ttu-id="83da3-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-838">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-838">CC002</span></span></td>
<td><span data-ttu-id="83da3-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="83da3-839">Finance</span></span></td>
<td><span data-ttu-id="83da3-840">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-840">10001</span></span></td>
<td><span data-ttu-id="83da3-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-841">Electricity</span></span></td>
<td><span data-ttu-id="83da3-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-842">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="83da3-843">-8,150.29</span></span></td>
<td><span data-ttu-id="83da3-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-845">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-845">CC003</span></span></td>
<td><span data-ttu-id="83da3-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-846">Assembly</span></span></td>
<td><span data-ttu-id="83da3-847">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-847">10001</span></span></td>
<td><span data-ttu-id="83da3-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-848">Electricity</span></span></td>
<td><span data-ttu-id="83da3-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-849">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="83da3-850">5,297.69</span></span></td>
<td><span data-ttu-id="83da3-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-852">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-852">CC004</span></span></td>
<td><span data-ttu-id="83da3-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="83da3-853">Packaging</span></span></td>
<td><span data-ttu-id="83da3-854">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-854">10001</span></span></td>
<td><span data-ttu-id="83da3-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-855">Electricity</span></span></td>
<td><span data-ttu-id="83da3-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-856">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="83da3-857">2,852.60</span></span></td>
<td><span data-ttu-id="83da3-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-859">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-859">CC003</span></span></td>
<td><span data-ttu-id="83da3-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-860">Assembly</span></span></td>
<td><span data-ttu-id="83da3-861">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-861">10001</span></span></td>
<td><span data-ttu-id="83da3-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-862">Electricity</span></span></td>
<td><span data-ttu-id="83da3-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-863">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="83da3-864">-713.75</span></span></td>
<td><span data-ttu-id="83da3-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-866">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-867">Product 1</span></span></td>
<td><span data-ttu-id="83da3-868">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-868">10001</span></span></td>
<td><span data-ttu-id="83da3-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-869">Electricity</span></span></td>
<td><span data-ttu-id="83da3-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-870">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-871">535.31</span><span class="sxs-lookup"><span data-stu-id="83da3-871">535.31</span></span></td>
<td><span data-ttu-id="83da3-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-873">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-874">Product 2</span></span></td>
<td><span data-ttu-id="83da3-875">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-875">10001</span></span></td>
<td><span data-ttu-id="83da3-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-876">Electricity</span></span></td>
<td><span data-ttu-id="83da3-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-877">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-878">178.44</span><span class="sxs-lookup"><span data-stu-id="83da3-878">178.44</span></span></td>
<td><span data-ttu-id="83da3-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-880">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-880">CC003</span></span></td>
<td><span data-ttu-id="83da3-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-881">Assembly</span></span></td>
<td><span data-ttu-id="83da3-882">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-882">10001</span></span></td>
<td><span data-ttu-id="83da3-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-883">Electricity</span></span></td>
<td><span data-ttu-id="83da3-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-884">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="83da3-885">-5,982.83</span></span></td>
<td><span data-ttu-id="83da3-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-887">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-888">Product 1</span></span></td>
<td><span data-ttu-id="83da3-889">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-889">10001</span></span></td>
<td><span data-ttu-id="83da3-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-890">Electricity</span></span></td>
<td><span data-ttu-id="83da3-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-891">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="83da3-892">4,487.12</span></span></td>
<td><span data-ttu-id="83da3-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-894">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-895">Product 2</span></span></td>
<td><span data-ttu-id="83da3-896">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-896">10001</span></span></td>
<td><span data-ttu-id="83da3-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-897">Electricity</span></span></td>
<td><span data-ttu-id="83da3-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-898">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="83da3-899">1,495.71</span></span></td>
<td><span data-ttu-id="83da3-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-901">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-901">CC003</span></span></td>
<td><span data-ttu-id="83da3-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-902">Assembly</span></span></td>
<td><span data-ttu-id="83da3-903">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-903">10001</span></span></td>
<td><span data-ttu-id="83da3-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-904">Electricity</span></span></td>
<td><span data-ttu-id="83da3-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-905">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="83da3-906">-286.25</span></span></td>
<td><span data-ttu-id="83da3-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-908">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-909">Product 1</span></span></td>
<td><span data-ttu-id="83da3-910">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-910">10001</span></span></td>
<td><span data-ttu-id="83da3-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-911">Electricity</span></span></td>
<td><span data-ttu-id="83da3-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-912">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-913">241.05</span><span class="sxs-lookup"><span data-stu-id="83da3-913">241.05</span></span></td>
<td><span data-ttu-id="83da3-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-915">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-916">Product 2</span></span></td>
<td><span data-ttu-id="83da3-917">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-917">10001</span></span></td>
<td><span data-ttu-id="83da3-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-918">Electricity</span></span></td>
<td><span data-ttu-id="83da3-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-919">Fixed cost</span></span></td>
<td><span data-ttu-id="83da3-920">45.20</span><span class="sxs-lookup"><span data-stu-id="83da3-920">45.20</span></span></td>
<td><span data-ttu-id="83da3-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-922">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-922">CC003</span></span></td>
<td><span data-ttu-id="83da3-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="83da3-923">Assembly</span></span></td>
<td><span data-ttu-id="83da3-924">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-924">10001</span></span></td>
<td><span data-ttu-id="83da3-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-925">Electricity</span></span></td>
<td><span data-ttu-id="83da3-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-926">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="83da3-927">-2,977.17</span></span></td>
<td><span data-ttu-id="83da3-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-929">Prod 1</span></span></td>
<td><span data-ttu-id="83da3-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="83da3-930">Product 1</span></span></td>
<td><span data-ttu-id="83da3-931">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-931">10001</span></span></td>
<td><span data-ttu-id="83da3-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-932">Electricity</span></span></td>
<td><span data-ttu-id="83da3-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-933">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="83da3-934">2,507.09</span></span></td>
<td><span data-ttu-id="83da3-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83da3-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-936">Prod 2</span></span></td>
<td><span data-ttu-id="83da3-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="83da3-937">Product 2</span></span></td>
<td><span data-ttu-id="83da3-938">10001</span><span class="sxs-lookup"><span data-stu-id="83da3-938">10001</span></span></td>
<td><span data-ttu-id="83da3-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="83da3-939">Electricity</span></span></td>
<td><span data-ttu-id="83da3-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-940">Variable cost</span></span></td>
<td><span data-ttu-id="83da3-941">470.08</span><span class="sxs-lookup"><span data-stu-id="83da3-941">470.08</span></span></td>
<td><span data-ttu-id="83da3-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="83da3-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="83da3-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="83da3-943">Conclusion</span></span>
<span data-ttu-id="83da3-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="83da3-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="83da3-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="83da3-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="83da3-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="83da3-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="83da3-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="83da3-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="83da3-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="83da3-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="83da3-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="83da3-950">Razem</span><span class="sxs-lookup"><span data-stu-id="83da3-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="83da3-951">CC099</span><span class="sxs-lookup"><span data-stu-id="83da3-951">CC099</span></span></th>
<th><span data-ttu-id="83da3-952">CC001</span><span class="sxs-lookup"><span data-stu-id="83da3-952">CC001</span></span></th>
<th><span data-ttu-id="83da3-953">CC002</span><span class="sxs-lookup"><span data-stu-id="83da3-953">CC002</span></span></th>
<th><span data-ttu-id="83da3-954">CC003</span><span class="sxs-lookup"><span data-stu-id="83da3-954">CC003</span></span></th>
<th><span data-ttu-id="83da3-955">CC004</span><span class="sxs-lookup"><span data-stu-id="83da3-955">CC004</span></span></th>
<th><span data-ttu-id="83da3-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="83da3-956">Proj 1</span></span></th>
<th><span data-ttu-id="83da3-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="83da3-957">Proj 2</span></span></th>
<th><span data-ttu-id="83da3-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="83da3-958">Prod 1</span></span></th>
<th><span data-ttu-id="83da3-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="83da3-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="83da3-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="83da3-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="83da3-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="83da3-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="83da3-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-971">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="83da3-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="83da3-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-973">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-974">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-975">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-976">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-977">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="83da3-978">776.36</span><span class="sxs-lookup"><span data-stu-id="83da3-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-979">223.64</span><span class="sxs-lookup"><span data-stu-id="83da3-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="83da3-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="83da3-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-982">000</span><span class="sxs-lookup"><span data-stu-id="83da3-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-983">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-984">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-985">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-986">0,00</span><span class="sxs-lookup"><span data-stu-id="83da3-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-987">30.00</span><span class="sxs-lookup"><span data-stu-id="83da3-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-988">10,00</span><span class="sxs-lookup"><span data-stu-id="83da3-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="83da3-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="83da3-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="83da3-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="83da3-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="83da3-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="83da3-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="83da3-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="83da3-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="83da3-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="83da3-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="83da3-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="83da3-996">Aby uzyskać więcej informacji, [Zasady akumulacji kosztów i obliczanie narzutu](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="83da3-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]