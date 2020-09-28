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
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: cc6ad48ef80aa01739129b59cc1133d0a1930f24
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759479"
---
# <a name="overhead-calculation"></a><span data-ttu-id="64d33-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="64d33-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64d33-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="64d33-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="64d33-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="64d33-105">Term definition</span></span>
---------------

<span data-ttu-id="64d33-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="64d33-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="64d33-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="64d33-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="64d33-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="64d33-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="64d33-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="64d33-109">Rent</span></span>
-   <span data-ttu-id="64d33-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-110">Electricity</span></span>
-   <span data-ttu-id="64d33-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="64d33-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="64d33-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="64d33-112">Overhead calculation overview</span></span>
<span data-ttu-id="64d33-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="64d33-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="64d33-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="64d33-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="64d33-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="64d33-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="64d33-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="64d33-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="64d33-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="64d33-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="64d33-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="64d33-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="64d33-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="64d33-119">Version type</span></span>
-   <span data-ttu-id="64d33-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="64d33-120">Date and time</span></span>
-   <span data-ttu-id="64d33-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="64d33-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="64d33-122">Fiscal year</span></span>
-   <span data-ttu-id="64d33-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="64d33-123">Fiscal period</span></span>

<span data-ttu-id="64d33-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="64d33-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="64d33-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="64d33-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="64d33-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="64d33-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="64d33-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="64d33-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="64d33-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="64d33-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="64d33-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="64d33-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="64d33-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="64d33-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="64d33-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="64d33-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="64d33-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="64d33-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="64d33-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="64d33-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="64d33-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="64d33-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="64d33-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="64d33-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="64d33-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="64d33-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="64d33-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="64d33-140">Main account</span></span></th>
<th><span data-ttu-id="64d33-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="64d33-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="64d33-143">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-143">CC099</span></span></td>
<td><span data-ttu-id="64d33-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-144">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-145">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-145">10001</span></span></td>
<td><span data-ttu-id="64d33-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-146">Electricity</span></span></td>
<td><span data-ttu-id="64d33-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="64d33-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="64d33-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="64d33-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="64d33-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="64d33-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="64d33-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-151">Define the cost behavior rule</span></span>

<span data-ttu-id="64d33-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="64d33-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="64d33-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="64d33-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="64d33-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="64d33-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="64d33-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="64d33-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="64d33-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="64d33-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="64d33-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="64d33-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="64d33-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="64d33-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="64d33-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="64d33-160">Journal</span></span></th>
<th><span data-ttu-id="64d33-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="64d33-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="64d33-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="64d33-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="64d33-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="64d33-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-164">00001</span><span class="sxs-lookup"><span data-stu-id="64d33-164">00001</span></span></td>
<td><span data-ttu-id="64d33-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="64d33-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="64d33-166">Fiscal</span></span></td>
<td><span data-ttu-id="64d33-167">2017</span><span class="sxs-lookup"><span data-stu-id="64d33-167">2017</span></span></td>
<td><span data-ttu-id="64d33-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="64d33-168">Period 1</span></span></td>
<td><span data-ttu-id="64d33-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="64d33-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="64d33-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="64d33-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="64d33-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="64d33-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-173">Cost element</span></span></th>
<th><span data-ttu-id="64d33-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-174">Cost behavior</span></span></th>
<th><span data-ttu-id="64d33-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="64d33-177">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-177">CC099</span></span></td>
<td><span data-ttu-id="64d33-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-178">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-179">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-179">10001</span></span></td>
<td><span data-ttu-id="64d33-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-180">Electricity</span></span></td>
<td><span data-ttu-id="64d33-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="64d33-181">Unclassified</span></span></td>
<td><span data-ttu-id="64d33-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="64d33-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="64d33-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-185">Cost element</span></span></th>
<th><span data-ttu-id="64d33-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-186">Cost behavior</span></span></th>
<th><span data-ttu-id="64d33-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-187">Amount</span></span></th>
<th><span data-ttu-id="64d33-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="64d33-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-189">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-189">CC099</span></span></td>
<td><span data-ttu-id="64d33-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-190">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-191">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-191">10001</span></span></td>
<td><span data-ttu-id="64d33-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-192">Electricity</span></span></td>
<td><span data-ttu-id="64d33-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="64d33-193">Unclassified</span></span></td>
<td><span data-ttu-id="64d33-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="64d33-194">10,000.00</span></span></td>
<td><span data-ttu-id="64d33-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-196">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-196">CC099</span></span></td>
<td><span data-ttu-id="64d33-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-197">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-198">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-198">10001</span></span></td>
<td><span data-ttu-id="64d33-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-199">Electricity</span></span></td>
<td><span data-ttu-id="64d33-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="64d33-200">Unclassified</span></span></td>
<td><span data-ttu-id="64d33-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-201">-10,000.00</span></span></td>
<td><span data-ttu-id="64d33-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-203">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-203">CC099</span></span></td>
<td><span data-ttu-id="64d33-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-204">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-205">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-205">10001</span></span></td>
<td><span data-ttu-id="64d33-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-206">Electricity</span></span></td>
<td><span data-ttu-id="64d33-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-207">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-208">1,000.00</span></span></td>
<td><span data-ttu-id="64d33-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-210">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-210">CC099</span></span></td>
<td><span data-ttu-id="64d33-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-211">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-212">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-212">10001</span></span></td>
<td><span data-ttu-id="64d33-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-213">Electricity</span></span></td>
<td><span data-ttu-id="64d33-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-214">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="64d33-215">9,000.00</span></span></td>
<td><span data-ttu-id="64d33-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="64d33-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="64d33-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="64d33-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="64d33-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="64d33-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="64d33-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="64d33-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-221">Define the cost distribution rule</span></span>

<span data-ttu-id="64d33-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="64d33-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="64d33-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="64d33-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="64d33-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="64d33-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="64d33-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="64d33-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="64d33-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="64d33-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="64d33-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="64d33-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-228">Cost object</span></span></th>
<th><span data-ttu-id="64d33-229">kWh</span><span class="sxs-lookup"><span data-stu-id="64d33-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-230">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-230">CC001</span></span></td>
<td><span data-ttu-id="64d33-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-231">HR</span></span></td>
<td><span data-ttu-id="64d33-232">1 000</span><span class="sxs-lookup"><span data-stu-id="64d33-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-233">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-233">CC002</span></span></td>
<td><span data-ttu-id="64d33-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-234">Finance</span></span></td>
<td><span data-ttu-id="64d33-235">6,000</span><span class="sxs-lookup"><span data-stu-id="64d33-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-236">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-236">CC003</span></span></td>
<td><span data-ttu-id="64d33-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-237">Assembly</span></span></td>
<td><span data-ttu-id="64d33-238">0</span><span class="sxs-lookup"><span data-stu-id="64d33-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="64d33-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-240">Cost object</span></span></th>
<th><span data-ttu-id="64d33-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="64d33-241">Magnitude</span></span></th>
<th><span data-ttu-id="64d33-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="64d33-242">Allocation factor</span></span></th>
<th><span data-ttu-id="64d33-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-244">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-244">CC001</span></span></td>
<td><span data-ttu-id="64d33-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-245">HR</span></span></td>
<td><span data-ttu-id="64d33-246">1 000</span><span class="sxs-lookup"><span data-stu-id="64d33-246">1,000</span></span></td>
<td><span data-ttu-id="64d33-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="64d33-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="64d33-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-249">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-249">CC002</span></span></td>
<td><span data-ttu-id="64d33-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-250">Finance</span></span></td>
<td><span data-ttu-id="64d33-251">6,000</span><span class="sxs-lookup"><span data-stu-id="64d33-251">6,000</span></span></td>
<td><span data-ttu-id="64d33-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="64d33-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="64d33-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-254">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-254">CC003</span></span></td>
<td><span data-ttu-id="64d33-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-255">Assembly</span></span></td>
<td><span data-ttu-id="64d33-256">0</span><span class="sxs-lookup"><span data-stu-id="64d33-256">0</span></span></td>
<td><span data-ttu-id="64d33-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="64d33-258">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="64d33-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="64d33-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="64d33-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-261">Cost object</span></span></th>
<th><span data-ttu-id="64d33-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="64d33-262">Formula</span></span></th>
<th><span data-ttu-id="64d33-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="64d33-263">Magnitude</span></span></th>
<th><span data-ttu-id="64d33-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="64d33-264">Allocation factor</span></span></th>
<th><span data-ttu-id="64d33-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-266">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-266">CC001</span></span></td>
<td><span data-ttu-id="64d33-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-267">HR</span></span></td>
<td><span data-ttu-id="64d33-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="64d33-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="64d33-269">1</span><span class="sxs-lookup"><span data-stu-id="64d33-269">1</span></span></td>
<td><span data-ttu-id="64d33-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="64d33-271">500.00</span><span class="sxs-lookup"><span data-stu-id="64d33-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-272">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-272">CC002</span></span></td>
<td><span data-ttu-id="64d33-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-273">Finance</span></span></td>
<td><span data-ttu-id="64d33-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="64d33-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="64d33-275">1</span><span class="sxs-lookup"><span data-stu-id="64d33-275">1</span></span></td>
<td><span data-ttu-id="64d33-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="64d33-277">500.00</span><span class="sxs-lookup"><span data-stu-id="64d33-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-278">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-278">CC003</span></span></td>
<td><span data-ttu-id="64d33-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-279">Assembly</span></span></td>
<td><span data-ttu-id="64d33-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="64d33-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="64d33-281">0</span><span class="sxs-lookup"><span data-stu-id="64d33-281">0</span></span></td>
<td><span data-ttu-id="64d33-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="64d33-283">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="64d33-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="64d33-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="64d33-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="64d33-285">Journal</span></span></th>
<th><span data-ttu-id="64d33-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="64d33-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="64d33-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="64d33-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="64d33-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="64d33-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-289">00002</span><span class="sxs-lookup"><span data-stu-id="64d33-289">00002</span></span></td>
<td><span data-ttu-id="64d33-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="64d33-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="64d33-291">Fiscal</span></span></td>
<td><span data-ttu-id="64d33-292">2017</span><span class="sxs-lookup"><span data-stu-id="64d33-292">2017</span></span></td>
<td><span data-ttu-id="64d33-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="64d33-293">Period 1</span></span></td>
<td><span data-ttu-id="64d33-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="64d33-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="64d33-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="64d33-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="64d33-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="64d33-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-298">Cost element</span></span></th>
<th><span data-ttu-id="64d33-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-299">Cost behavior</span></span></th>
<th><span data-ttu-id="64d33-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-302">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-302">CC099</span></span></td>
<td><span data-ttu-id="64d33-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-303">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-304">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-304">10001</span></span></td>
<td><span data-ttu-id="64d33-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-305">Electricity</span></span></td>
<td><span data-ttu-id="64d33-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-306">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-309">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-309">CC099</span></span></td>
<td><span data-ttu-id="64d33-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-310">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-311">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-311">10001</span></span></td>
<td><span data-ttu-id="64d33-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-312">Electricity</span></span></td>
<td><span data-ttu-id="64d33-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-313">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="64d33-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="64d33-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-317">Cost element</span></span></th>
<th><span data-ttu-id="64d33-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-318">Cost behavior</span></span></th>
<th><span data-ttu-id="64d33-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-319">Amount</span></span></th>
<th><span data-ttu-id="64d33-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="64d33-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-321">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-321">CC099</span></span></td>
<td><span data-ttu-id="64d33-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-322">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-323">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-323">10001</span></span></td>
<td><span data-ttu-id="64d33-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-324">Electricity</span></span></td>
<td><span data-ttu-id="64d33-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-325">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-326">-1,000.00</span></span></td>
<td><span data-ttu-id="64d33-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-328">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-328">CC001</span></span></td>
<td><span data-ttu-id="64d33-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-329">HR</span></span></td>
<td><span data-ttu-id="64d33-330">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-330">10001</span></span></td>
<td><span data-ttu-id="64d33-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-331">Electricity</span></span></td>
<td><span data-ttu-id="64d33-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-332">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-333">500.00</span><span class="sxs-lookup"><span data-stu-id="64d33-333">500.00</span></span></td>
<td><span data-ttu-id="64d33-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-335">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-335">CC002</span></span></td>
<td><span data-ttu-id="64d33-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-336">Finance</span></span></td>
<td><span data-ttu-id="64d33-337">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-337">10001</span></span></td>
<td><span data-ttu-id="64d33-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-338">Electricity</span></span></td>
<td><span data-ttu-id="64d33-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-339">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-340">500.00</span><span class="sxs-lookup"><span data-stu-id="64d33-340">500.00</span></span></td>
<td><span data-ttu-id="64d33-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-342">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-342">CC099</span></span></td>
<td><span data-ttu-id="64d33-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-343">Default cost center</span></span></td>
<td><span data-ttu-id="64d33-344">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-344">10001</span></span></td>
<td><span data-ttu-id="64d33-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-345">Electricity</span></span></td>
<td><span data-ttu-id="64d33-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-346">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="64d33-347">-9,000.00</span></span></td>
<td><span data-ttu-id="64d33-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-349">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-349">CC001</span></span></td>
<td><span data-ttu-id="64d33-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-350">HR</span></span></td>
<td><span data-ttu-id="64d33-351">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-351">10001</span></span></td>
<td><span data-ttu-id="64d33-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-352">Electricity</span></span></td>
<td><span data-ttu-id="64d33-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-353">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="64d33-354">1,285.71</span></span></td>
<td><span data-ttu-id="64d33-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-356">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-356">CC002</span></span></td>
<td><span data-ttu-id="64d33-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-357">Finance</span></span></td>
<td><span data-ttu-id="64d33-358">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-358">10001</span></span></td>
<td><span data-ttu-id="64d33-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-359">Electricity</span></span></td>
<td><span data-ttu-id="64d33-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-360">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="64d33-361">7,714.29</span></span></td>
<td><span data-ttu-id="64d33-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="64d33-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="64d33-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="64d33-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="64d33-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="64d33-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="64d33-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="64d33-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="64d33-367">Define the overhead rate</span></span>

<span data-ttu-id="64d33-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="64d33-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="64d33-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="64d33-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-370">Cost object</span></span></th>
<th><span data-ttu-id="64d33-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="64d33-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="64d33-372">Proj 1</span></span></td>
<td><span data-ttu-id="64d33-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-373">Project 1</span></span></td>
<td><span data-ttu-id="64d33-374">3</span><span class="sxs-lookup"><span data-stu-id="64d33-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="64d33-375">Proj 2</span></span></td>
<td><span data-ttu-id="64d33-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-376">Project 2</span></span></td>
<td><span data-ttu-id="64d33-377">1</span><span class="sxs-lookup"><span data-stu-id="64d33-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="64d33-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-379">Cost object</span></span></th>
<th><span data-ttu-id="64d33-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-380">Cost element</span></span></th>
<th><span data-ttu-id="64d33-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-381">Cost behavior</span></span></th>
<th><span data-ttu-id="64d33-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="64d33-382">Units</span></span></th>
<th><span data-ttu-id="64d33-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="64d33-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-384">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-384">CC001</span></span></td>
<td><span data-ttu-id="64d33-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-385">HR</span></span></td>
<td><span data-ttu-id="64d33-386">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-386">10001</span></span></td>
<td><span data-ttu-id="64d33-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-387">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-388">1</span><span class="sxs-lookup"><span data-stu-id="64d33-388">1</span></span></td>
<td><span data-ttu-id="64d33-389">10</span><span class="sxs-lookup"><span data-stu-id="64d33-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="64d33-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-391">Cost object</span></span></th>
<th><span data-ttu-id="64d33-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="64d33-392">Magnitude</span></span></th>
<th><span data-ttu-id="64d33-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-393">Cost element</span></span></th>
<th><span data-ttu-id="64d33-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="64d33-394">Allocation factor</span></span></th>
<th><span data-ttu-id="64d33-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="64d33-396">Proj 1</span></span></td>
<td><span data-ttu-id="64d33-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-397">Project 1</span></span></td>
<td><span data-ttu-id="64d33-398">3</span><span class="sxs-lookup"><span data-stu-id="64d33-398">3</span></span></td>
<td><span data-ttu-id="64d33-399">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-399">10001</span></span></td>
<td><span data-ttu-id="64d33-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="64d33-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="64d33-401">30.00</span><span class="sxs-lookup"><span data-stu-id="64d33-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="64d33-402">Proj 2</span></span></td>
<td><span data-ttu-id="64d33-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-403">Project 2</span></span></td>
<td><span data-ttu-id="64d33-404">1</span><span class="sxs-lookup"><span data-stu-id="64d33-404">1</span></span></td>
<td><span data-ttu-id="64d33-405">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-405">10001</span></span></td>
<td><span data-ttu-id="64d33-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="64d33-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="64d33-407">10,00</span><span class="sxs-lookup"><span data-stu-id="64d33-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="64d33-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="64d33-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="64d33-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="64d33-409">Journal</span></span></th>
<th><span data-ttu-id="64d33-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="64d33-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="64d33-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="64d33-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="64d33-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="64d33-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-413">00003</span><span class="sxs-lookup"><span data-stu-id="64d33-413">00003</span></span></td>
<td><span data-ttu-id="64d33-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="64d33-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="64d33-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="64d33-415">Fiscal</span></span></td>
<td><span data-ttu-id="64d33-416">2017</span><span class="sxs-lookup"><span data-stu-id="64d33-416">2017</span></span></td>
<td><span data-ttu-id="64d33-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="64d33-417">Period 1</span></span></td>
<td><span data-ttu-id="64d33-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="64d33-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="64d33-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="64d33-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="64d33-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="64d33-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-421">Cost object</span></span></th>
<th><span data-ttu-id="64d33-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="64d33-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="64d33-424">Proj 1</span></span></td>
<td><span data-ttu-id="64d33-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="64d33-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="64d33-426">3,00</span><span class="sxs-lookup"><span data-stu-id="64d33-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="64d33-428">Proj 2</span></span></td>
<td><span data-ttu-id="64d33-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="64d33-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="64d33-430">1.00</span><span class="sxs-lookup"><span data-stu-id="64d33-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="64d33-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-433">Cost element</span></span></th>
<th><span data-ttu-id="64d33-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-434">Cost behavior</span></span></th>
<th><span data-ttu-id="64d33-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-435">Amount</span></span></th>
<th><span data-ttu-id="64d33-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="64d33-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="64d33-437">CC0001</span></span></td>
<td><span data-ttu-id="64d33-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-438">HR</span></span></td>
<td><span data-ttu-id="64d33-439">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-439">10001</span></span></td>
<td><span data-ttu-id="64d33-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-440">Electricity</span></span></td>
<td><span data-ttu-id="64d33-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-441">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="64d33-442">-30.00</span></span></td>
<td><span data-ttu-id="64d33-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="64d33-444">Proj 1</span></span></td>
<td><span data-ttu-id="64d33-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="64d33-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="64d33-446">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-446">10001</span></span></td>
<td><span data-ttu-id="64d33-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-447">Electricity</span></span></td>
<td><span data-ttu-id="64d33-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-448">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-449">30.00</span><span class="sxs-lookup"><span data-stu-id="64d33-449">30.00</span></span></td>
<td><span data-ttu-id="64d33-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-451">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-451">CC001</span></span></td>
<td><span data-ttu-id="64d33-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-452">HR</span></span></td>
<td><span data-ttu-id="64d33-453">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-453">10001</span></span></td>
<td><span data-ttu-id="64d33-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-454">Electricity</span></span></td>
<td><span data-ttu-id="64d33-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-455">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="64d33-456">-10.00</span></span></td>
<td><span data-ttu-id="64d33-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="64d33-458">Proj 2</span></span></td>
<td><span data-ttu-id="64d33-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="64d33-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="64d33-460">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-460">10001</span></span></td>
<td><span data-ttu-id="64d33-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-461">Electricity</span></span></td>
<td><span data-ttu-id="64d33-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-462">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-463">10,00</span><span class="sxs-lookup"><span data-stu-id="64d33-463">10.00</span></span></td>
<td><span data-ttu-id="64d33-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="64d33-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="64d33-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="64d33-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="64d33-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="64d33-468">Aplikacja Finance obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="64d33-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="64d33-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="64d33-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="64d33-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="64d33-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="64d33-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="64d33-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="64d33-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="64d33-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="64d33-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="64d33-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="64d33-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-475">Define the cost allocation</span></span>

<span data-ttu-id="64d33-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="64d33-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="64d33-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="64d33-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-479">Cost object</span></span></th>
<th><span data-ttu-id="64d33-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="64d33-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-481">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-481">CC002</span></span></td>
<td><span data-ttu-id="64d33-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-482">Finance</span></span></td>
<td><span data-ttu-id="64d33-483">35</span><span class="sxs-lookup"><span data-stu-id="64d33-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-484">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-484">CC003</span></span></td>
<td><span data-ttu-id="64d33-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-485">Assembly</span></span></td>
<td><span data-ttu-id="64d33-486">55</span><span class="sxs-lookup"><span data-stu-id="64d33-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-487">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-487">CC004</span></span></td>
<td><span data-ttu-id="64d33-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-488">Packaging</span></span></td>
<td><span data-ttu-id="64d33-489">10</span><span class="sxs-lookup"><span data-stu-id="64d33-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="64d33-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="64d33-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-492">Cost object</span></span></th>
<th><span data-ttu-id="64d33-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="64d33-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-494">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-494">CC003</span></span></td>
<td><span data-ttu-id="64d33-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-495">Assembly</span></span></td>
<td><span data-ttu-id="64d33-496">65</span><span class="sxs-lookup"><span data-stu-id="64d33-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-497">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-497">CC004</span></span></td>
<td><span data-ttu-id="64d33-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-498">Packaging</span></span></td>
<td><span data-ttu-id="64d33-499">35</span><span class="sxs-lookup"><span data-stu-id="64d33-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="64d33-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="64d33-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-502">Cost object</span></span></th>
<th><span data-ttu-id="64d33-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="64d33-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-504">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-505">Product 1</span></span></td>
<td><span data-ttu-id="64d33-506">60</span><span class="sxs-lookup"><span data-stu-id="64d33-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-507">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-508">Product 2</span></span></td>
<td><span data-ttu-id="64d33-509">20</span><span class="sxs-lookup"><span data-stu-id="64d33-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="64d33-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="64d33-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-512">Cost object</span></span></th>
<th><span data-ttu-id="64d33-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="64d33-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-514">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-515">Product 1</span></span></td>
<td><span data-ttu-id="64d33-516">80</span><span class="sxs-lookup"><span data-stu-id="64d33-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-517">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-518">Product 2</span></span></td>
<td><span data-ttu-id="64d33-519">15</span><span class="sxs-lookup"><span data-stu-id="64d33-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="64d33-520">Miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="64d33-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="64d33-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="64d33-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="64d33-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="64d33-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-523">Cost object</span></span></th>
<th><span data-ttu-id="64d33-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="64d33-524">Magnitude</span></span></th>
<th><span data-ttu-id="64d33-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="64d33-525">Allocation factor</span></span></th>
<th><span data-ttu-id="64d33-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-526">Amount</span></span></th>
<th><span data-ttu-id="64d33-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-528">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-528">CC002</span></span></td>
<td><span data-ttu-id="64d33-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-529">Finance</span></span></td>
<td><span data-ttu-id="64d33-530">35</span><span class="sxs-lookup"><span data-stu-id="64d33-530">35</span></span></td>
<td><span data-ttu-id="64d33-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="64d33-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="64d33-532">175.00</span><span class="sxs-lookup"><span data-stu-id="64d33-532">175.00</span></span></td>
<td><span data-ttu-id="64d33-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-534">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-534">CC003</span></span></td>
<td><span data-ttu-id="64d33-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-535">Assembly</span></span></td>
<td><span data-ttu-id="64d33-536">55</span><span class="sxs-lookup"><span data-stu-id="64d33-536">55</span></span></td>
<td><span data-ttu-id="64d33-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="64d33-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="64d33-538">275.00</span><span class="sxs-lookup"><span data-stu-id="64d33-538">275.00</span></span></td>
<td><span data-ttu-id="64d33-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-540">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-540">CC004</span></span></td>
<td><span data-ttu-id="64d33-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-541">Packaging</span></span></td>
<td><span data-ttu-id="64d33-542">10</span><span class="sxs-lookup"><span data-stu-id="64d33-542">10</span></span></td>
<td><span data-ttu-id="64d33-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="64d33-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="64d33-544">50,00</span><span class="sxs-lookup"><span data-stu-id="64d33-544">50.00</span></span></td>
<td><span data-ttu-id="64d33-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-546">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-546">CC002</span></span></td>
<td><span data-ttu-id="64d33-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-547">Finance</span></span></td>
<td><span data-ttu-id="64d33-548">35</span><span class="sxs-lookup"><span data-stu-id="64d33-548">35</span></span></td>
<td><span data-ttu-id="64d33-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="64d33-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="64d33-550">436.00</span><span class="sxs-lookup"><span data-stu-id="64d33-550">436.00</span></span></td>
<td><span data-ttu-id="64d33-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-552">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-552">CC003</span></span></td>
<td><span data-ttu-id="64d33-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-553">Assembly</span></span></td>
<td><span data-ttu-id="64d33-554">55</span><span class="sxs-lookup"><span data-stu-id="64d33-554">55</span></span></td>
<td><span data-ttu-id="64d33-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="64d33-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="64d33-556">685.14</span><span class="sxs-lookup"><span data-stu-id="64d33-556">685.14</span></span></td>
<td><span data-ttu-id="64d33-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-558">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-558">CC004</span></span></td>
<td><span data-ttu-id="64d33-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-559">Packaging</span></span></td>
<td><span data-ttu-id="64d33-560">10</span><span class="sxs-lookup"><span data-stu-id="64d33-560">10</span></span></td>
<td><span data-ttu-id="64d33-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="64d33-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="64d33-562">124.57</span><span class="sxs-lookup"><span data-stu-id="64d33-562">124.57</span></span></td>
<td><span data-ttu-id="64d33-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="64d33-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-565">Cost object</span></span></th>
<th><span data-ttu-id="64d33-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="64d33-566">Magnitude</span></span></th>
<th><span data-ttu-id="64d33-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="64d33-567">Allocation factor</span></span></th>
<th><span data-ttu-id="64d33-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-568">Amount</span></span></th>
<th><span data-ttu-id="64d33-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-570">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-570">CC003</span></span></td>
<td><span data-ttu-id="64d33-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-571">Assembly</span></span></td>
<td><span data-ttu-id="64d33-572">65</span><span class="sxs-lookup"><span data-stu-id="64d33-572">65</span></span></td>
<td><span data-ttu-id="64d33-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="64d33-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="64d33-574">438.75</span><span class="sxs-lookup"><span data-stu-id="64d33-574">438.75</span></span></td>
<td><span data-ttu-id="64d33-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-576">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-576">CC004</span></span></td>
<td><span data-ttu-id="64d33-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-577">Packaging</span></span></td>
<td><span data-ttu-id="64d33-578">35</span><span class="sxs-lookup"><span data-stu-id="64d33-578">35</span></span></td>
<td><span data-ttu-id="64d33-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="64d33-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="64d33-580">236.25</span><span class="sxs-lookup"><span data-stu-id="64d33-580">236.25</span></span></td>
<td><span data-ttu-id="64d33-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-582">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-582">CC003</span></span></td>
<td><span data-ttu-id="64d33-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-583">Assembly</span></span></td>
<td><span data-ttu-id="64d33-584">65</span><span class="sxs-lookup"><span data-stu-id="64d33-584">65</span></span></td>
<td><span data-ttu-id="64d33-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="64d33-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="64d33-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="64d33-586">5,297.69</span></span></td>
<td><span data-ttu-id="64d33-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-588">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-588">CC004</span></span></td>
<td><span data-ttu-id="64d33-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-589">Packaging</span></span></td>
<td><span data-ttu-id="64d33-590">35</span><span class="sxs-lookup"><span data-stu-id="64d33-590">35</span></span></td>
<td><span data-ttu-id="64d33-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="64d33-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="64d33-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="64d33-592">2,852.60</span></span></td>
<td><span data-ttu-id="64d33-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="64d33-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-595">Cost object</span></span></th>
<th><span data-ttu-id="64d33-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="64d33-596">Magnitude</span></span></th>
<th><span data-ttu-id="64d33-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="64d33-597">Allocation factor</span></span></th>
<th><span data-ttu-id="64d33-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-598">Amount</span></span></th>
<th><span data-ttu-id="64d33-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-600">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-601">Product 1</span></span></td>
<td><span data-ttu-id="64d33-602">60</span><span class="sxs-lookup"><span data-stu-id="64d33-602">60</span></span></td>
<td><span data-ttu-id="64d33-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="64d33-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="64d33-604">535.31</span><span class="sxs-lookup"><span data-stu-id="64d33-604">535.31</span></span></td>
<td><span data-ttu-id="64d33-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-606">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-607">Product 2</span></span></td>
<td><span data-ttu-id="64d33-608">20</span><span class="sxs-lookup"><span data-stu-id="64d33-608">20</span></span></td>
<td><span data-ttu-id="64d33-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="64d33-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="64d33-610">178.44</span><span class="sxs-lookup"><span data-stu-id="64d33-610">178.44</span></span></td>
<td><span data-ttu-id="64d33-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-612">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-613">Product 1</span></span></td>
<td><span data-ttu-id="64d33-614">60</span><span class="sxs-lookup"><span data-stu-id="64d33-614">60</span></span></td>
<td><span data-ttu-id="64d33-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="64d33-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="64d33-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="64d33-616">4,487.12</span></span></td>
<td><span data-ttu-id="64d33-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-618">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-619">Product 2</span></span></td>
<td><span data-ttu-id="64d33-620">20</span><span class="sxs-lookup"><span data-stu-id="64d33-620">20</span></span></td>
<td><span data-ttu-id="64d33-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="64d33-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="64d33-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="64d33-622">1,495.71</span></span></td>
<td><span data-ttu-id="64d33-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64d33-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="64d33-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-625">Cost object</span></span></th>
<th><span data-ttu-id="64d33-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="64d33-626">Magnitude</span></span></th>
<th><span data-ttu-id="64d33-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="64d33-627">Allocation factor</span></span></th>
<th><span data-ttu-id="64d33-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-628">Amount</span></span></th>
<th><span data-ttu-id="64d33-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-630">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-631">Product 1</span></span></td>
<td><span data-ttu-id="64d33-632">80</span><span class="sxs-lookup"><span data-stu-id="64d33-632">80</span></span></td>
<td><span data-ttu-id="64d33-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="64d33-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="64d33-634">241.05</span><span class="sxs-lookup"><span data-stu-id="64d33-634">241.05</span></span></td>
<td><span data-ttu-id="64d33-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-636">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-637">Product 2</span></span></td>
<td><span data-ttu-id="64d33-638">15</span><span class="sxs-lookup"><span data-stu-id="64d33-638">15</span></span></td>
<td><span data-ttu-id="64d33-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="64d33-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="64d33-640">45.20</span><span class="sxs-lookup"><span data-stu-id="64d33-640">45.20</span></span></td>
<td><span data-ttu-id="64d33-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-642">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-643">Product 1</span></span></td>
<td><span data-ttu-id="64d33-644">80</span><span class="sxs-lookup"><span data-stu-id="64d33-644">80</span></span></td>
<td><span data-ttu-id="64d33-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="64d33-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="64d33-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="64d33-646">2,507.09</span></span></td>
<td><span data-ttu-id="64d33-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-648">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-649">Product 2</span></span></td>
<td><span data-ttu-id="64d33-650">15</span><span class="sxs-lookup"><span data-stu-id="64d33-650">15</span></span></td>
<td><span data-ttu-id="64d33-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="64d33-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="64d33-652">470.08</span><span class="sxs-lookup"><span data-stu-id="64d33-652">470.08</span></span></td>
<td><span data-ttu-id="64d33-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="64d33-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="64d33-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="64d33-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="64d33-655">Journal</span></span></th>
<th><span data-ttu-id="64d33-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="64d33-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="64d33-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="64d33-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="64d33-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="64d33-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-659">00004</span><span class="sxs-lookup"><span data-stu-id="64d33-659">00004</span></span></td>
<td><span data-ttu-id="64d33-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="64d33-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="64d33-661">Fiscal</span></span></td>
<td><span data-ttu-id="64d33-662">2017</span><span class="sxs-lookup"><span data-stu-id="64d33-662">2017</span></span></td>
<td><span data-ttu-id="64d33-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="64d33-663">Period 1</span></span></td>
<td><span data-ttu-id="64d33-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="64d33-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="64d33-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="64d33-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="64d33-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="64d33-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-668">Cost element</span></span></th>
<th><span data-ttu-id="64d33-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-669">Cost behavior</span></span></th>
<th><span data-ttu-id="64d33-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-672">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-672">CC001</span></span></td>
<td><span data-ttu-id="64d33-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-673">HR</span></span></td>
<td><span data-ttu-id="64d33-674">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-674">10001</span></span></td>
<td><span data-ttu-id="64d33-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-675">Electricity</span></span></td>
<td><span data-ttu-id="64d33-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-676">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-677">500.00</span><span class="sxs-lookup"><span data-stu-id="64d33-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-679">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-679">CC001</span></span></td>
<td><span data-ttu-id="64d33-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-680">HR</span></span></td>
<td><span data-ttu-id="64d33-681">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-681">10001</span></span></td>
<td><span data-ttu-id="64d33-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-682">Electricity</span></span></td>
<td><span data-ttu-id="64d33-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-683">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="64d33-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-686">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-686">CC002</span></span></td>
<td><span data-ttu-id="64d33-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-687">Finance</span></span></td>
<td><span data-ttu-id="64d33-688">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-688">10001</span></span></td>
<td><span data-ttu-id="64d33-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-689">Electricity</span></span></td>
<td><span data-ttu-id="64d33-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-690">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-691">675.00</span><span class="sxs-lookup"><span data-stu-id="64d33-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-693">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-693">CC002</span></span></td>
<td><span data-ttu-id="64d33-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-694">Finance</span></span></td>
<td><span data-ttu-id="64d33-695">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-695">10001</span></span></td>
<td><span data-ttu-id="64d33-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-696">Electricity</span></span></td>
<td><span data-ttu-id="64d33-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-697">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="64d33-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-700">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-700">CC003</span></span></td>
<td><span data-ttu-id="64d33-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-701">Assembly</span></span></td>
<td><span data-ttu-id="64d33-702">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-702">10001</span></span></td>
<td><span data-ttu-id="64d33-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-703">Electricity</span></span></td>
<td><span data-ttu-id="64d33-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-704">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-705">713.75</span><span class="sxs-lookup"><span data-stu-id="64d33-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-707">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-707">CC003</span></span></td>
<td><span data-ttu-id="64d33-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-708">Assembly</span></span></td>
<td><span data-ttu-id="64d33-709">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-709">10001</span></span></td>
<td><span data-ttu-id="64d33-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-710">Electricity</span></span></td>
<td><span data-ttu-id="64d33-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-711">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="64d33-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-714">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-714">CC003</span></span></td>
<td><span data-ttu-id="64d33-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-715">Packaging</span></span></td>
<td><span data-ttu-id="64d33-716">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-716">10001</span></span></td>
<td><span data-ttu-id="64d33-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-717">Electricity</span></span></td>
<td><span data-ttu-id="64d33-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-718">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-719">286.25</span><span class="sxs-lookup"><span data-stu-id="64d33-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-721">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-721">CC003</span></span></td>
<td><span data-ttu-id="64d33-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-722">Packaging</span></span></td>
<td><span data-ttu-id="64d33-723">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-723">10001</span></span></td>
<td><span data-ttu-id="64d33-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-724">Electricity</span></span></td>
<td><span data-ttu-id="64d33-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-725">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="64d33-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-728">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-729">Product 1</span></span></td>
<td><span data-ttu-id="64d33-730">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-730">10001</span></span></td>
<td><span data-ttu-id="64d33-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-731">Electricity</span></span></td>
<td><span data-ttu-id="64d33-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-732">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-733">776.36</span><span class="sxs-lookup"><span data-stu-id="64d33-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-735">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-736">Product 1</span></span></td>
<td><span data-ttu-id="64d33-737">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-737">10001</span></span></td>
<td><span data-ttu-id="64d33-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-738">Electricity</span></span></td>
<td><span data-ttu-id="64d33-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-739">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="64d33-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-742">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-743">Product 1</span></span></td>
<td><span data-ttu-id="64d33-744">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-744">10001</span></span></td>
<td><span data-ttu-id="64d33-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-745">Electricity</span></span></td>
<td><span data-ttu-id="64d33-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-746">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-747">223.64</span><span class="sxs-lookup"><span data-stu-id="64d33-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="64d33-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-749">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-750">Product 1</span></span></td>
<td><span data-ttu-id="64d33-751">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-751">10001</span></span></td>
<td><span data-ttu-id="64d33-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-752">Electricity</span></span></td>
<td><span data-ttu-id="64d33-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-753">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="64d33-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="64d33-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="64d33-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="64d33-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-757">Cost element</span></span></th>
<th><span data-ttu-id="64d33-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-758">Cost behavior</span></span></th>
<th><span data-ttu-id="64d33-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="64d33-759">Amount</span></span></th>
<th><span data-ttu-id="64d33-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="64d33-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="64d33-761">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-761">CC001</span></span></td>
<td><span data-ttu-id="64d33-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-762">HR</span></span></td>
<td><span data-ttu-id="64d33-763">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-763">10001</span></span></td>
<td><span data-ttu-id="64d33-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-764">Electricity</span></span></td>
<td><span data-ttu-id="64d33-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-765">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="64d33-766">-500.00</span></span></td>
<td><span data-ttu-id="64d33-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-768">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-768">CC002</span></span></td>
<td><span data-ttu-id="64d33-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-769">Finance</span></span></td>
<td><span data-ttu-id="64d33-770">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-770">10001</span></span></td>
<td><span data-ttu-id="64d33-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-771">Electricity</span></span></td>
<td><span data-ttu-id="64d33-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-772">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-773">175.00</span><span class="sxs-lookup"><span data-stu-id="64d33-773">175.00</span></span></td>
<td><span data-ttu-id="64d33-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-775">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-775">CC003</span></span></td>
<td><span data-ttu-id="64d33-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-776">Assembly</span></span></td>
<td><span data-ttu-id="64d33-777">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-777">10001</span></span></td>
<td><span data-ttu-id="64d33-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-778">Electricity</span></span></td>
<td><span data-ttu-id="64d33-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-779">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-780">275.00</span><span class="sxs-lookup"><span data-stu-id="64d33-780">275.00</span></span></td>
<td><span data-ttu-id="64d33-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-782">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-782">CC004</span></span></td>
<td><span data-ttu-id="64d33-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-783">Packaging</span></span></td>
<td><span data-ttu-id="64d33-784">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-784">10001</span></span></td>
<td><span data-ttu-id="64d33-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-785">Electricity</span></span></td>
<td><span data-ttu-id="64d33-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-786">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-787">50,00</span><span class="sxs-lookup"><span data-stu-id="64d33-787">50,00</span></span></td>
<td><span data-ttu-id="64d33-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-789">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-789">CC001</span></span></td>
<td><span data-ttu-id="64d33-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="64d33-790">HR</span></span></td>
<td><span data-ttu-id="64d33-791">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-791">10001</span></span></td>
<td><span data-ttu-id="64d33-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-792">Electricity</span></span></td>
<td><span data-ttu-id="64d33-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-793">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="64d33-794">-1,245.71</span></span></td>
<td><span data-ttu-id="64d33-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-796">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-796">CC002</span></span></td>
<td><span data-ttu-id="64d33-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-797">Finance</span></span></td>
<td><span data-ttu-id="64d33-798">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-798">10001</span></span></td>
<td><span data-ttu-id="64d33-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-799">Electricity</span></span></td>
<td><span data-ttu-id="64d33-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-800">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-801">436.00</span><span class="sxs-lookup"><span data-stu-id="64d33-801">436.00</span></span></td>
<td><span data-ttu-id="64d33-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-803">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-803">CC003</span></span></td>
<td><span data-ttu-id="64d33-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-804">Assembly</span></span></td>
<td><span data-ttu-id="64d33-805">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-805">10001</span></span></td>
<td><span data-ttu-id="64d33-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-806">Electricity</span></span></td>
<td><span data-ttu-id="64d33-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-807">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-808">685.14</span><span class="sxs-lookup"><span data-stu-id="64d33-808">685.14</span></span></td>
<td><span data-ttu-id="64d33-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-810">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-810">CC004</span></span></td>
<td><span data-ttu-id="64d33-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-811">Packaging</span></span></td>
<td><span data-ttu-id="64d33-812">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-812">10001</span></span></td>
<td><span data-ttu-id="64d33-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-813">Electricity</span></span></td>
<td><span data-ttu-id="64d33-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-814">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-815">124.57</span><span class="sxs-lookup"><span data-stu-id="64d33-815">124.57</span></span></td>
<td><span data-ttu-id="64d33-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-817">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-817">CC002</span></span></td>
<td><span data-ttu-id="64d33-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-818">Finance</span></span></td>
<td><span data-ttu-id="64d33-819">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-819">10001</span></span></td>
<td><span data-ttu-id="64d33-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-820">Electricity</span></span></td>
<td><span data-ttu-id="64d33-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-821">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="64d33-822">-675.00</span></span></td>
<td><span data-ttu-id="64d33-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-824">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-824">CC003</span></span></td>
<td><span data-ttu-id="64d33-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-825">Assembly</span></span></td>
<td><span data-ttu-id="64d33-826">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-826">10001</span></span></td>
<td><span data-ttu-id="64d33-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-827">Electricity</span></span></td>
<td><span data-ttu-id="64d33-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-828">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-829">438.75</span><span class="sxs-lookup"><span data-stu-id="64d33-829">438.75</span></span></td>
<td><span data-ttu-id="64d33-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-831">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-831">CC004</span></span></td>
<td><span data-ttu-id="64d33-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-832">Packaging</span></span></td>
<td><span data-ttu-id="64d33-833">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-833">10001</span></span></td>
<td><span data-ttu-id="64d33-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-834">Electricity</span></span></td>
<td><span data-ttu-id="64d33-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-835">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-836">236.25</span><span class="sxs-lookup"><span data-stu-id="64d33-836">236.25</span></span></td>
<td><span data-ttu-id="64d33-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-838">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-838">CC002</span></span></td>
<td><span data-ttu-id="64d33-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="64d33-839">Finance</span></span></td>
<td><span data-ttu-id="64d33-840">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-840">10001</span></span></td>
<td><span data-ttu-id="64d33-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-841">Electricity</span></span></td>
<td><span data-ttu-id="64d33-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-842">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="64d33-843">-8,150.29</span></span></td>
<td><span data-ttu-id="64d33-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-845">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-845">CC003</span></span></td>
<td><span data-ttu-id="64d33-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-846">Assembly</span></span></td>
<td><span data-ttu-id="64d33-847">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-847">10001</span></span></td>
<td><span data-ttu-id="64d33-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-848">Electricity</span></span></td>
<td><span data-ttu-id="64d33-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-849">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="64d33-850">5,297.69</span></span></td>
<td><span data-ttu-id="64d33-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-852">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-852">CC004</span></span></td>
<td><span data-ttu-id="64d33-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="64d33-853">Packaging</span></span></td>
<td><span data-ttu-id="64d33-854">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-854">10001</span></span></td>
<td><span data-ttu-id="64d33-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-855">Electricity</span></span></td>
<td><span data-ttu-id="64d33-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-856">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="64d33-857">2,852.60</span></span></td>
<td><span data-ttu-id="64d33-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-859">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-859">CC003</span></span></td>
<td><span data-ttu-id="64d33-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-860">Assembly</span></span></td>
<td><span data-ttu-id="64d33-861">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-861">10001</span></span></td>
<td><span data-ttu-id="64d33-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-862">Electricity</span></span></td>
<td><span data-ttu-id="64d33-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-863">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="64d33-864">-713.75</span></span></td>
<td><span data-ttu-id="64d33-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-866">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-867">Product 1</span></span></td>
<td><span data-ttu-id="64d33-868">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-868">10001</span></span></td>
<td><span data-ttu-id="64d33-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-869">Electricity</span></span></td>
<td><span data-ttu-id="64d33-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-870">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-871">535.31</span><span class="sxs-lookup"><span data-stu-id="64d33-871">535.31</span></span></td>
<td><span data-ttu-id="64d33-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-873">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-874">Product 2</span></span></td>
<td><span data-ttu-id="64d33-875">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-875">10001</span></span></td>
<td><span data-ttu-id="64d33-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-876">Electricity</span></span></td>
<td><span data-ttu-id="64d33-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-877">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-878">178.44</span><span class="sxs-lookup"><span data-stu-id="64d33-878">178.44</span></span></td>
<td><span data-ttu-id="64d33-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-880">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-880">CC003</span></span></td>
<td><span data-ttu-id="64d33-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-881">Assembly</span></span></td>
<td><span data-ttu-id="64d33-882">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-882">10001</span></span></td>
<td><span data-ttu-id="64d33-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-883">Electricity</span></span></td>
<td><span data-ttu-id="64d33-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-884">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="64d33-885">-5,982.83</span></span></td>
<td><span data-ttu-id="64d33-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-887">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-888">Product 1</span></span></td>
<td><span data-ttu-id="64d33-889">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-889">10001</span></span></td>
<td><span data-ttu-id="64d33-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-890">Electricity</span></span></td>
<td><span data-ttu-id="64d33-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-891">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="64d33-892">4,487.12</span></span></td>
<td><span data-ttu-id="64d33-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-894">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-895">Product 2</span></span></td>
<td><span data-ttu-id="64d33-896">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-896">10001</span></span></td>
<td><span data-ttu-id="64d33-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-897">Electricity</span></span></td>
<td><span data-ttu-id="64d33-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-898">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="64d33-899">1,495.71</span></span></td>
<td><span data-ttu-id="64d33-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-901">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-901">CC003</span></span></td>
<td><span data-ttu-id="64d33-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-902">Assembly</span></span></td>
<td><span data-ttu-id="64d33-903">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-903">10001</span></span></td>
<td><span data-ttu-id="64d33-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-904">Electricity</span></span></td>
<td><span data-ttu-id="64d33-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-905">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="64d33-906">-286.25</span></span></td>
<td><span data-ttu-id="64d33-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-908">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-909">Product 1</span></span></td>
<td><span data-ttu-id="64d33-910">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-910">10001</span></span></td>
<td><span data-ttu-id="64d33-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-911">Electricity</span></span></td>
<td><span data-ttu-id="64d33-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-912">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-913">241.05</span><span class="sxs-lookup"><span data-stu-id="64d33-913">241.05</span></span></td>
<td><span data-ttu-id="64d33-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-915">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-916">Product 2</span></span></td>
<td><span data-ttu-id="64d33-917">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-917">10001</span></span></td>
<td><span data-ttu-id="64d33-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-918">Electricity</span></span></td>
<td><span data-ttu-id="64d33-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-919">Fixed cost</span></span></td>
<td><span data-ttu-id="64d33-920">45.20</span><span class="sxs-lookup"><span data-stu-id="64d33-920">45.20</span></span></td>
<td><span data-ttu-id="64d33-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-922">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-922">CC003</span></span></td>
<td><span data-ttu-id="64d33-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="64d33-923">Assembly</span></span></td>
<td><span data-ttu-id="64d33-924">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-924">10001</span></span></td>
<td><span data-ttu-id="64d33-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-925">Electricity</span></span></td>
<td><span data-ttu-id="64d33-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-926">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="64d33-927">-2,977.17</span></span></td>
<td><span data-ttu-id="64d33-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-929">Prod 1</span></span></td>
<td><span data-ttu-id="64d33-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="64d33-930">Product 1</span></span></td>
<td><span data-ttu-id="64d33-931">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-931">10001</span></span></td>
<td><span data-ttu-id="64d33-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-932">Electricity</span></span></td>
<td><span data-ttu-id="64d33-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-933">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="64d33-934">2,507.09</span></span></td>
<td><span data-ttu-id="64d33-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="64d33-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-936">Prod 2</span></span></td>
<td><span data-ttu-id="64d33-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="64d33-937">Product 2</span></span></td>
<td><span data-ttu-id="64d33-938">10001</span><span class="sxs-lookup"><span data-stu-id="64d33-938">10001</span></span></td>
<td><span data-ttu-id="64d33-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="64d33-939">Electricity</span></span></td>
<td><span data-ttu-id="64d33-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-940">Variable cost</span></span></td>
<td><span data-ttu-id="64d33-941">470.08</span><span class="sxs-lookup"><span data-stu-id="64d33-941">470.08</span></span></td>
<td><span data-ttu-id="64d33-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="64d33-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="64d33-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="64d33-943">Conclusion</span></span>
<span data-ttu-id="64d33-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="64d33-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="64d33-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="64d33-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="64d33-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="64d33-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="64d33-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="64d33-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="64d33-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="64d33-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="64d33-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="64d33-950">Razem</span><span class="sxs-lookup"><span data-stu-id="64d33-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="64d33-951">CC099</span><span class="sxs-lookup"><span data-stu-id="64d33-951">CC099</span></span></th>
<th><span data-ttu-id="64d33-952">CC001</span><span class="sxs-lookup"><span data-stu-id="64d33-952">CC001</span></span></th>
<th><span data-ttu-id="64d33-953">CC002</span><span class="sxs-lookup"><span data-stu-id="64d33-953">CC002</span></span></th>
<th><span data-ttu-id="64d33-954">CC003</span><span class="sxs-lookup"><span data-stu-id="64d33-954">CC003</span></span></th>
<th><span data-ttu-id="64d33-955">CC004</span><span class="sxs-lookup"><span data-stu-id="64d33-955">CC004</span></span></th>
<th><span data-ttu-id="64d33-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="64d33-956">Proj 1</span></span></th>
<th><span data-ttu-id="64d33-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="64d33-957">Proj 2</span></span></th>
<th><span data-ttu-id="64d33-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="64d33-958">Prod 1</span></span></th>
<th><span data-ttu-id="64d33-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="64d33-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="64d33-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="64d33-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="64d33-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="64d33-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="64d33-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-971">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="64d33-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="64d33-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-973">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-974">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-975">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-976">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-977">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="64d33-978">776.36</span><span class="sxs-lookup"><span data-stu-id="64d33-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-979">223.64</span><span class="sxs-lookup"><span data-stu-id="64d33-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="64d33-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="64d33-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-982">000</span><span class="sxs-lookup"><span data-stu-id="64d33-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-983">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-984">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-985">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-986">0,00</span><span class="sxs-lookup"><span data-stu-id="64d33-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-987">30.00</span><span class="sxs-lookup"><span data-stu-id="64d33-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-988">10,00</span><span class="sxs-lookup"><span data-stu-id="64d33-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="64d33-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="64d33-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="64d33-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="64d33-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="64d33-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="64d33-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="64d33-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="64d33-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="64d33-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="64d33-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="64d33-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="64d33-996">Aby uzyskać więcej informacji, [Zasady akumulacji kosztów i obliczanie narzutu](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="64d33-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



