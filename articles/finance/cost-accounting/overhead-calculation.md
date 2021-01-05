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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446909"
---
# <a name="overhead-calculation"></a><span data-ttu-id="a9f98-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="a9f98-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9f98-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="a9f98-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="a9f98-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="a9f98-105">Term definition</span></span>
---------------

<span data-ttu-id="a9f98-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="a9f98-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="a9f98-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="a9f98-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="a9f98-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="a9f98-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="a9f98-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="a9f98-109">Rent</span></span>
-   <span data-ttu-id="a9f98-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-110">Electricity</span></span>
-   <span data-ttu-id="a9f98-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="a9f98-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="a9f98-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="a9f98-112">Overhead calculation overview</span></span>
<span data-ttu-id="a9f98-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="a9f98-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="a9f98-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="a9f98-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="a9f98-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="a9f98-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="a9f98-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="a9f98-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="a9f98-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="a9f98-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="a9f98-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="a9f98-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="a9f98-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="a9f98-119">Version type</span></span>
-   <span data-ttu-id="a9f98-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="a9f98-120">Date and time</span></span>
-   <span data-ttu-id="a9f98-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="a9f98-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="a9f98-122">Fiscal year</span></span>
-   <span data-ttu-id="a9f98-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="a9f98-123">Fiscal period</span></span>

<span data-ttu-id="a9f98-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="a9f98-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="a9f98-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="a9f98-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="a9f98-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="a9f98-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="a9f98-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="a9f98-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="a9f98-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="a9f98-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="a9f98-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="a9f98-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="a9f98-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="a9f98-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="a9f98-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="a9f98-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="a9f98-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="a9f98-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="a9f98-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="a9f98-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="a9f98-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="a9f98-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="a9f98-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a9f98-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="a9f98-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="a9f98-140">Main account</span></span></th>
<th><span data-ttu-id="a9f98-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="a9f98-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="a9f98-143">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-143">CC099</span></span></td>
<td><span data-ttu-id="a9f98-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-144">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-145">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-145">10001</span></span></td>
<td><span data-ttu-id="a9f98-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-146">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="a9f98-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="a9f98-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="a9f98-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="a9f98-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="a9f98-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-151">Define the cost behavior rule</span></span>

<span data-ttu-id="a9f98-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="a9f98-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="a9f98-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="a9f98-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="a9f98-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="a9f98-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="a9f98-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="a9f98-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="a9f98-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="a9f98-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="a9f98-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="a9f98-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a9f98-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="a9f98-160">Journal</span></span></th>
<th><span data-ttu-id="a9f98-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="a9f98-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a9f98-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="a9f98-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a9f98-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="a9f98-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-164">00001</span><span class="sxs-lookup"><span data-stu-id="a9f98-164">00001</span></span></td>
<td><span data-ttu-id="a9f98-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="a9f98-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="a9f98-166">Fiscal</span></span></td>
<td><span data-ttu-id="a9f98-167">2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-167">2017</span></span></td>
<td><span data-ttu-id="a9f98-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-168">Period 1</span></span></td>
<td><span data-ttu-id="a9f98-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a9f98-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="a9f98-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a9f98-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="a9f98-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-173">Cost element</span></span></th>
<th><span data-ttu-id="a9f98-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-174">Cost behavior</span></span></th>
<th><span data-ttu-id="a9f98-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="a9f98-177">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-177">CC099</span></span></td>
<td><span data-ttu-id="a9f98-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-178">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-179">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-179">10001</span></span></td>
<td><span data-ttu-id="a9f98-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-180">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="a9f98-181">Unclassified</span></span></td>
<td><span data-ttu-id="a9f98-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a9f98-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-185">Cost element</span></span></th>
<th><span data-ttu-id="a9f98-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-186">Cost behavior</span></span></th>
<th><span data-ttu-id="a9f98-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-187">Amount</span></span></th>
<th><span data-ttu-id="a9f98-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="a9f98-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-189">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-189">CC099</span></span></td>
<td><span data-ttu-id="a9f98-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-190">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-191">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-191">10001</span></span></td>
<td><span data-ttu-id="a9f98-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-192">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="a9f98-193">Unclassified</span></span></td>
<td><span data-ttu-id="a9f98-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-194">10,000.00</span></span></td>
<td><span data-ttu-id="a9f98-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-196">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-196">CC099</span></span></td>
<td><span data-ttu-id="a9f98-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-197">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-198">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-198">10001</span></span></td>
<td><span data-ttu-id="a9f98-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-199">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="a9f98-200">Unclassified</span></span></td>
<td><span data-ttu-id="a9f98-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-201">-10,000.00</span></span></td>
<td><span data-ttu-id="a9f98-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-203">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-203">CC099</span></span></td>
<td><span data-ttu-id="a9f98-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-204">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-205">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-205">10001</span></span></td>
<td><span data-ttu-id="a9f98-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-206">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-207">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-208">1,000.00</span></span></td>
<td><span data-ttu-id="a9f98-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-210">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-210">CC099</span></span></td>
<td><span data-ttu-id="a9f98-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-211">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-212">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-212">10001</span></span></td>
<td><span data-ttu-id="a9f98-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-213">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-214">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-215">9,000.00</span></span></td>
<td><span data-ttu-id="a9f98-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="a9f98-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="a9f98-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="a9f98-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="a9f98-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="a9f98-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="a9f98-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-221">Define the cost distribution rule</span></span>

<span data-ttu-id="a9f98-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="a9f98-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="a9f98-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="a9f98-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="a9f98-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="a9f98-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="a9f98-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="a9f98-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="a9f98-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="a9f98-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="a9f98-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-228">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-229">kWh</span><span class="sxs-lookup"><span data-stu-id="a9f98-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-230">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-230">CC001</span></span></td>
<td><span data-ttu-id="a9f98-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-231">HR</span></span></td>
<td><span data-ttu-id="a9f98-232">1 000</span><span class="sxs-lookup"><span data-stu-id="a9f98-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-233">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-233">CC002</span></span></td>
<td><span data-ttu-id="a9f98-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-234">Finance</span></span></td>
<td><span data-ttu-id="a9f98-235">6,000</span><span class="sxs-lookup"><span data-stu-id="a9f98-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-236">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-236">CC003</span></span></td>
<td><span data-ttu-id="a9f98-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-237">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-238">0</span><span class="sxs-lookup"><span data-stu-id="a9f98-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="a9f98-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-240">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="a9f98-241">Magnitude</span></span></th>
<th><span data-ttu-id="a9f98-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="a9f98-242">Allocation factor</span></span></th>
<th><span data-ttu-id="a9f98-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-244">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-244">CC001</span></span></td>
<td><span data-ttu-id="a9f98-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-245">HR</span></span></td>
<td><span data-ttu-id="a9f98-246">1 000</span><span class="sxs-lookup"><span data-stu-id="a9f98-246">1,000</span></span></td>
<td><span data-ttu-id="a9f98-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a9f98-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a9f98-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-249">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-249">CC002</span></span></td>
<td><span data-ttu-id="a9f98-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-250">Finance</span></span></td>
<td><span data-ttu-id="a9f98-251">6,000</span><span class="sxs-lookup"><span data-stu-id="a9f98-251">6,000</span></span></td>
<td><span data-ttu-id="a9f98-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a9f98-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a9f98-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-254">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-254">CC003</span></span></td>
<td><span data-ttu-id="a9f98-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-255">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-256">0</span><span class="sxs-lookup"><span data-stu-id="a9f98-256">0</span></span></td>
<td><span data-ttu-id="a9f98-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a9f98-258">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="a9f98-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="a9f98-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="a9f98-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-261">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="a9f98-262">Formula</span></span></th>
<th><span data-ttu-id="a9f98-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="a9f98-263">Magnitude</span></span></th>
<th><span data-ttu-id="a9f98-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="a9f98-264">Allocation factor</span></span></th>
<th><span data-ttu-id="a9f98-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-266">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-266">CC001</span></span></td>
<td><span data-ttu-id="a9f98-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-267">HR</span></span></td>
<td><span data-ttu-id="a9f98-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a9f98-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a9f98-269">1</span><span class="sxs-lookup"><span data-stu-id="a9f98-269">1</span></span></td>
<td><span data-ttu-id="a9f98-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a9f98-271">500.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-272">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-272">CC002</span></span></td>
<td><span data-ttu-id="a9f98-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-273">Finance</span></span></td>
<td><span data-ttu-id="a9f98-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a9f98-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a9f98-275">1</span><span class="sxs-lookup"><span data-stu-id="a9f98-275">1</span></span></td>
<td><span data-ttu-id="a9f98-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a9f98-277">500.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-278">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-278">CC003</span></span></td>
<td><span data-ttu-id="a9f98-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-279">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a9f98-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a9f98-281">0</span><span class="sxs-lookup"><span data-stu-id="a9f98-281">0</span></span></td>
<td><span data-ttu-id="a9f98-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a9f98-283">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a9f98-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="a9f98-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a9f98-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="a9f98-285">Journal</span></span></th>
<th><span data-ttu-id="a9f98-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="a9f98-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a9f98-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="a9f98-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a9f98-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="a9f98-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-289">00002</span><span class="sxs-lookup"><span data-stu-id="a9f98-289">00002</span></span></td>
<td><span data-ttu-id="a9f98-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="a9f98-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="a9f98-291">Fiscal</span></span></td>
<td><span data-ttu-id="a9f98-292">2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-292">2017</span></span></td>
<td><span data-ttu-id="a9f98-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-293">Period 1</span></span></td>
<td><span data-ttu-id="a9f98-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a9f98-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="a9f98-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a9f98-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="a9f98-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-298">Cost element</span></span></th>
<th><span data-ttu-id="a9f98-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-299">Cost behavior</span></span></th>
<th><span data-ttu-id="a9f98-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-302">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-302">CC099</span></span></td>
<td><span data-ttu-id="a9f98-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-303">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-304">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-304">10001</span></span></td>
<td><span data-ttu-id="a9f98-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-305">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-306">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-309">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-309">CC099</span></span></td>
<td><span data-ttu-id="a9f98-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-310">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-311">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-311">10001</span></span></td>
<td><span data-ttu-id="a9f98-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-312">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-313">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a9f98-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-317">Cost element</span></span></th>
<th><span data-ttu-id="a9f98-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-318">Cost behavior</span></span></th>
<th><span data-ttu-id="a9f98-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-319">Amount</span></span></th>
<th><span data-ttu-id="a9f98-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="a9f98-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-321">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-321">CC099</span></span></td>
<td><span data-ttu-id="a9f98-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-322">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-323">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-323">10001</span></span></td>
<td><span data-ttu-id="a9f98-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-324">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-325">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-326">-1,000.00</span></span></td>
<td><span data-ttu-id="a9f98-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-328">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-328">CC001</span></span></td>
<td><span data-ttu-id="a9f98-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-329">HR</span></span></td>
<td><span data-ttu-id="a9f98-330">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-330">10001</span></span></td>
<td><span data-ttu-id="a9f98-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-331">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-332">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-333">500.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-333">500.00</span></span></td>
<td><span data-ttu-id="a9f98-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-335">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-335">CC002</span></span></td>
<td><span data-ttu-id="a9f98-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-336">Finance</span></span></td>
<td><span data-ttu-id="a9f98-337">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-337">10001</span></span></td>
<td><span data-ttu-id="a9f98-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-338">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-339">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-340">500.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-340">500.00</span></span></td>
<td><span data-ttu-id="a9f98-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-342">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-342">CC099</span></span></td>
<td><span data-ttu-id="a9f98-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-343">Default cost center</span></span></td>
<td><span data-ttu-id="a9f98-344">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-344">10001</span></span></td>
<td><span data-ttu-id="a9f98-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-345">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-346">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-347">-9,000.00</span></span></td>
<td><span data-ttu-id="a9f98-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-349">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-349">CC001</span></span></td>
<td><span data-ttu-id="a9f98-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-350">HR</span></span></td>
<td><span data-ttu-id="a9f98-351">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-351">10001</span></span></td>
<td><span data-ttu-id="a9f98-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-352">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-353">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a9f98-354">1,285.71</span></span></td>
<td><span data-ttu-id="a9f98-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-356">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-356">CC002</span></span></td>
<td><span data-ttu-id="a9f98-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-357">Finance</span></span></td>
<td><span data-ttu-id="a9f98-358">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-358">10001</span></span></td>
<td><span data-ttu-id="a9f98-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-359">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-360">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a9f98-361">7,714.29</span></span></td>
<td><span data-ttu-id="a9f98-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="a9f98-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="a9f98-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="a9f98-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="a9f98-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="a9f98-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="a9f98-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="a9f98-367">Define the overhead rate</span></span>

<span data-ttu-id="a9f98-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="a9f98-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="a9f98-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="a9f98-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-370">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="a9f98-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-372">Proj 1</span></span></td>
<td><span data-ttu-id="a9f98-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-373">Project 1</span></span></td>
<td><span data-ttu-id="a9f98-374">3</span><span class="sxs-lookup"><span data-stu-id="a9f98-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-375">Proj 2</span></span></td>
<td><span data-ttu-id="a9f98-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-376">Project 2</span></span></td>
<td><span data-ttu-id="a9f98-377">1</span><span class="sxs-lookup"><span data-stu-id="a9f98-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="a9f98-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-379">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-380">Cost element</span></span></th>
<th><span data-ttu-id="a9f98-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-381">Cost behavior</span></span></th>
<th><span data-ttu-id="a9f98-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="a9f98-382">Units</span></span></th>
<th><span data-ttu-id="a9f98-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="a9f98-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-384">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-384">CC001</span></span></td>
<td><span data-ttu-id="a9f98-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-385">HR</span></span></td>
<td><span data-ttu-id="a9f98-386">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-386">10001</span></span></td>
<td><span data-ttu-id="a9f98-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-387">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-388">1</span><span class="sxs-lookup"><span data-stu-id="a9f98-388">1</span></span></td>
<td><span data-ttu-id="a9f98-389">10</span><span class="sxs-lookup"><span data-stu-id="a9f98-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-391">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="a9f98-392">Magnitude</span></span></th>
<th><span data-ttu-id="a9f98-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-393">Cost element</span></span></th>
<th><span data-ttu-id="a9f98-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="a9f98-394">Allocation factor</span></span></th>
<th><span data-ttu-id="a9f98-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-396">Proj 1</span></span></td>
<td><span data-ttu-id="a9f98-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-397">Project 1</span></span></td>
<td><span data-ttu-id="a9f98-398">3</span><span class="sxs-lookup"><span data-stu-id="a9f98-398">3</span></span></td>
<td><span data-ttu-id="a9f98-399">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-399">10001</span></span></td>
<td><span data-ttu-id="a9f98-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a9f98-401">30.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-402">Proj 2</span></span></td>
<td><span data-ttu-id="a9f98-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-403">Project 2</span></span></td>
<td><span data-ttu-id="a9f98-404">1</span><span class="sxs-lookup"><span data-stu-id="a9f98-404">1</span></span></td>
<td><span data-ttu-id="a9f98-405">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-405">10001</span></span></td>
<td><span data-ttu-id="a9f98-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a9f98-407">10,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a9f98-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="a9f98-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a9f98-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="a9f98-409">Journal</span></span></th>
<th><span data-ttu-id="a9f98-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="a9f98-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a9f98-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="a9f98-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a9f98-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="a9f98-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-413">00003</span><span class="sxs-lookup"><span data-stu-id="a9f98-413">00003</span></span></td>
<td><span data-ttu-id="a9f98-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="a9f98-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="a9f98-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="a9f98-415">Fiscal</span></span></td>
<td><span data-ttu-id="a9f98-416">2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-416">2017</span></span></td>
<td><span data-ttu-id="a9f98-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-417">Period 1</span></span></td>
<td><span data-ttu-id="a9f98-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="a9f98-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="a9f98-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a9f98-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="a9f98-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-421">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="a9f98-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-424">Proj 1</span></span></td>
<td><span data-ttu-id="a9f98-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a9f98-426">3,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-428">Proj 2</span></span></td>
<td><span data-ttu-id="a9f98-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a9f98-430">1.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a9f98-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-433">Cost element</span></span></th>
<th><span data-ttu-id="a9f98-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-434">Cost behavior</span></span></th>
<th><span data-ttu-id="a9f98-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-435">Amount</span></span></th>
<th><span data-ttu-id="a9f98-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="a9f98-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="a9f98-437">CC0001</span></span></td>
<td><span data-ttu-id="a9f98-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-438">HR</span></span></td>
<td><span data-ttu-id="a9f98-439">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-439">10001</span></span></td>
<td><span data-ttu-id="a9f98-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-440">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-441">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-442">-30.00</span></span></td>
<td><span data-ttu-id="a9f98-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-444">Proj 1</span></span></td>
<td><span data-ttu-id="a9f98-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a9f98-446">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-446">10001</span></span></td>
<td><span data-ttu-id="a9f98-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-447">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-448">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-449">30.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-449">30.00</span></span></td>
<td><span data-ttu-id="a9f98-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-451">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-451">CC001</span></span></td>
<td><span data-ttu-id="a9f98-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-452">HR</span></span></td>
<td><span data-ttu-id="a9f98-453">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-453">10001</span></span></td>
<td><span data-ttu-id="a9f98-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-454">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-455">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-456">-10.00</span></span></td>
<td><span data-ttu-id="a9f98-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-458">Proj 2</span></span></td>
<td><span data-ttu-id="a9f98-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a9f98-460">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-460">10001</span></span></td>
<td><span data-ttu-id="a9f98-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-461">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-462">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-463">10,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-463">10.00</span></span></td>
<td><span data-ttu-id="a9f98-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="a9f98-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="a9f98-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="a9f98-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="a9f98-468">Aplikacja Finance obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="a9f98-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="a9f98-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="a9f98-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="a9f98-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="a9f98-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="a9f98-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="a9f98-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="a9f98-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="a9f98-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="a9f98-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-475">Define the cost allocation</span></span>

<span data-ttu-id="a9f98-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="a9f98-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="a9f98-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="a9f98-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-479">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="a9f98-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-481">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-481">CC002</span></span></td>
<td><span data-ttu-id="a9f98-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-482">Finance</span></span></td>
<td><span data-ttu-id="a9f98-483">35</span><span class="sxs-lookup"><span data-stu-id="a9f98-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-484">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-484">CC003</span></span></td>
<td><span data-ttu-id="a9f98-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-485">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-486">55</span><span class="sxs-lookup"><span data-stu-id="a9f98-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-487">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-487">CC004</span></span></td>
<td><span data-ttu-id="a9f98-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-488">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-489">10</span><span class="sxs-lookup"><span data-stu-id="a9f98-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="a9f98-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="a9f98-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-492">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="a9f98-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-494">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-494">CC003</span></span></td>
<td><span data-ttu-id="a9f98-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-495">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-496">65</span><span class="sxs-lookup"><span data-stu-id="a9f98-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-497">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-497">CC004</span></span></td>
<td><span data-ttu-id="a9f98-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-498">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-499">35</span><span class="sxs-lookup"><span data-stu-id="a9f98-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="a9f98-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="a9f98-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-502">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="a9f98-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-504">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-505">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-506">60</span><span class="sxs-lookup"><span data-stu-id="a9f98-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-507">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-508">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-509">20</span><span class="sxs-lookup"><span data-stu-id="a9f98-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="a9f98-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="a9f98-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-512">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="a9f98-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-514">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-515">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-516">80</span><span class="sxs-lookup"><span data-stu-id="a9f98-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-517">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-518">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-519">15</span><span class="sxs-lookup"><span data-stu-id="a9f98-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a9f98-520">Miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="a9f98-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="a9f98-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="a9f98-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="a9f98-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="a9f98-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-523">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="a9f98-524">Magnitude</span></span></th>
<th><span data-ttu-id="a9f98-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="a9f98-525">Allocation factor</span></span></th>
<th><span data-ttu-id="a9f98-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-526">Amount</span></span></th>
<th><span data-ttu-id="a9f98-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-528">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-528">CC002</span></span></td>
<td><span data-ttu-id="a9f98-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-529">Finance</span></span></td>
<td><span data-ttu-id="a9f98-530">35</span><span class="sxs-lookup"><span data-stu-id="a9f98-530">35</span></span></td>
<td><span data-ttu-id="a9f98-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a9f98-532">175.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-532">175.00</span></span></td>
<td><span data-ttu-id="a9f98-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-534">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-534">CC003</span></span></td>
<td><span data-ttu-id="a9f98-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-535">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-536">55</span><span class="sxs-lookup"><span data-stu-id="a9f98-536">55</span></span></td>
<td><span data-ttu-id="a9f98-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a9f98-538">275.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-538">275.00</span></span></td>
<td><span data-ttu-id="a9f98-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-540">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-540">CC004</span></span></td>
<td><span data-ttu-id="a9f98-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-541">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-542">10</span><span class="sxs-lookup"><span data-stu-id="a9f98-542">10</span></span></td>
<td><span data-ttu-id="a9f98-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a9f98-544">50,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-544">50.00</span></span></td>
<td><span data-ttu-id="a9f98-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-546">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-546">CC002</span></span></td>
<td><span data-ttu-id="a9f98-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-547">Finance</span></span></td>
<td><span data-ttu-id="a9f98-548">35</span><span class="sxs-lookup"><span data-stu-id="a9f98-548">35</span></span></td>
<td><span data-ttu-id="a9f98-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="a9f98-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a9f98-550">436.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-550">436.00</span></span></td>
<td><span data-ttu-id="a9f98-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-552">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-552">CC003</span></span></td>
<td><span data-ttu-id="a9f98-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-553">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-554">55</span><span class="sxs-lookup"><span data-stu-id="a9f98-554">55</span></span></td>
<td><span data-ttu-id="a9f98-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="a9f98-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a9f98-556">685.14</span><span class="sxs-lookup"><span data-stu-id="a9f98-556">685.14</span></span></td>
<td><span data-ttu-id="a9f98-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-558">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-558">CC004</span></span></td>
<td><span data-ttu-id="a9f98-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-559">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-560">10</span><span class="sxs-lookup"><span data-stu-id="a9f98-560">10</span></span></td>
<td><span data-ttu-id="a9f98-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="a9f98-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a9f98-562">124.57</span><span class="sxs-lookup"><span data-stu-id="a9f98-562">124.57</span></span></td>
<td><span data-ttu-id="a9f98-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="a9f98-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-565">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="a9f98-566">Magnitude</span></span></th>
<th><span data-ttu-id="a9f98-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="a9f98-567">Allocation factor</span></span></th>
<th><span data-ttu-id="a9f98-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-568">Amount</span></span></th>
<th><span data-ttu-id="a9f98-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-570">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-570">CC003</span></span></td>
<td><span data-ttu-id="a9f98-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-571">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-572">65</span><span class="sxs-lookup"><span data-stu-id="a9f98-572">65</span></span></td>
<td><span data-ttu-id="a9f98-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="a9f98-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a9f98-574">438.75</span><span class="sxs-lookup"><span data-stu-id="a9f98-574">438.75</span></span></td>
<td><span data-ttu-id="a9f98-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-576">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-576">CC004</span></span></td>
<td><span data-ttu-id="a9f98-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-577">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-578">35</span><span class="sxs-lookup"><span data-stu-id="a9f98-578">35</span></span></td>
<td><span data-ttu-id="a9f98-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="a9f98-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a9f98-580">236.25</span><span class="sxs-lookup"><span data-stu-id="a9f98-580">236.25</span></span></td>
<td><span data-ttu-id="a9f98-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-582">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-582">CC003</span></span></td>
<td><span data-ttu-id="a9f98-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-583">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-584">65</span><span class="sxs-lookup"><span data-stu-id="a9f98-584">65</span></span></td>
<td><span data-ttu-id="a9f98-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="a9f98-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a9f98-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a9f98-586">5,297.69</span></span></td>
<td><span data-ttu-id="a9f98-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-588">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-588">CC004</span></span></td>
<td><span data-ttu-id="a9f98-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-589">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-590">35</span><span class="sxs-lookup"><span data-stu-id="a9f98-590">35</span></span></td>
<td><span data-ttu-id="a9f98-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="a9f98-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a9f98-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a9f98-592">2,852.60</span></span></td>
<td><span data-ttu-id="a9f98-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="a9f98-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-595">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="a9f98-596">Magnitude</span></span></th>
<th><span data-ttu-id="a9f98-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="a9f98-597">Allocation factor</span></span></th>
<th><span data-ttu-id="a9f98-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-598">Amount</span></span></th>
<th><span data-ttu-id="a9f98-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-600">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-601">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-602">60</span><span class="sxs-lookup"><span data-stu-id="a9f98-602">60</span></span></td>
<td><span data-ttu-id="a9f98-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="a9f98-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a9f98-604">535.31</span><span class="sxs-lookup"><span data-stu-id="a9f98-604">535.31</span></span></td>
<td><span data-ttu-id="a9f98-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-606">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-607">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-608">20</span><span class="sxs-lookup"><span data-stu-id="a9f98-608">20</span></span></td>
<td><span data-ttu-id="a9f98-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="a9f98-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a9f98-610">178.44</span><span class="sxs-lookup"><span data-stu-id="a9f98-610">178.44</span></span></td>
<td><span data-ttu-id="a9f98-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-612">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-613">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-614">60</span><span class="sxs-lookup"><span data-stu-id="a9f98-614">60</span></span></td>
<td><span data-ttu-id="a9f98-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="a9f98-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a9f98-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a9f98-616">4,487.12</span></span></td>
<td><span data-ttu-id="a9f98-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-618">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-619">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-620">20</span><span class="sxs-lookup"><span data-stu-id="a9f98-620">20</span></span></td>
<td><span data-ttu-id="a9f98-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="a9f98-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a9f98-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a9f98-622">1,495.71</span></span></td>
<td><span data-ttu-id="a9f98-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9f98-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="a9f98-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-625">Cost object</span></span></th>
<th><span data-ttu-id="a9f98-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="a9f98-626">Magnitude</span></span></th>
<th><span data-ttu-id="a9f98-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="a9f98-627">Allocation factor</span></span></th>
<th><span data-ttu-id="a9f98-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-628">Amount</span></span></th>
<th><span data-ttu-id="a9f98-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-630">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-631">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-632">80</span><span class="sxs-lookup"><span data-stu-id="a9f98-632">80</span></span></td>
<td><span data-ttu-id="a9f98-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="a9f98-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a9f98-634">241.05</span><span class="sxs-lookup"><span data-stu-id="a9f98-634">241.05</span></span></td>
<td><span data-ttu-id="a9f98-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-636">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-637">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-638">15</span><span class="sxs-lookup"><span data-stu-id="a9f98-638">15</span></span></td>
<td><span data-ttu-id="a9f98-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="a9f98-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a9f98-640">45.20</span><span class="sxs-lookup"><span data-stu-id="a9f98-640">45.20</span></span></td>
<td><span data-ttu-id="a9f98-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-642">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-643">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-644">80</span><span class="sxs-lookup"><span data-stu-id="a9f98-644">80</span></span></td>
<td><span data-ttu-id="a9f98-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="a9f98-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a9f98-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a9f98-646">2,507.09</span></span></td>
<td><span data-ttu-id="a9f98-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-648">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-649">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-650">15</span><span class="sxs-lookup"><span data-stu-id="a9f98-650">15</span></span></td>
<td><span data-ttu-id="a9f98-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="a9f98-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a9f98-652">470.08</span><span class="sxs-lookup"><span data-stu-id="a9f98-652">470.08</span></span></td>
<td><span data-ttu-id="a9f98-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a9f98-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="a9f98-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a9f98-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="a9f98-655">Journal</span></span></th>
<th><span data-ttu-id="a9f98-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="a9f98-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a9f98-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="a9f98-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a9f98-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="a9f98-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-659">00004</span><span class="sxs-lookup"><span data-stu-id="a9f98-659">00004</span></span></td>
<td><span data-ttu-id="a9f98-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="a9f98-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="a9f98-661">Fiscal</span></span></td>
<td><span data-ttu-id="a9f98-662">2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-662">2017</span></span></td>
<td><span data-ttu-id="a9f98-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-663">Period 1</span></span></td>
<td><span data-ttu-id="a9f98-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="a9f98-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="a9f98-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a9f98-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="a9f98-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-668">Cost element</span></span></th>
<th><span data-ttu-id="a9f98-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-669">Cost behavior</span></span></th>
<th><span data-ttu-id="a9f98-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-672">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-672">CC001</span></span></td>
<td><span data-ttu-id="a9f98-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-673">HR</span></span></td>
<td><span data-ttu-id="a9f98-674">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-674">10001</span></span></td>
<td><span data-ttu-id="a9f98-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-675">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-676">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-677">500.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-679">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-679">CC001</span></span></td>
<td><span data-ttu-id="a9f98-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-680">HR</span></span></td>
<td><span data-ttu-id="a9f98-681">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-681">10001</span></span></td>
<td><span data-ttu-id="a9f98-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-682">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-683">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="a9f98-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-686">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-686">CC002</span></span></td>
<td><span data-ttu-id="a9f98-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-687">Finance</span></span></td>
<td><span data-ttu-id="a9f98-688">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-688">10001</span></span></td>
<td><span data-ttu-id="a9f98-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-689">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-690">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-691">675.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-693">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-693">CC002</span></span></td>
<td><span data-ttu-id="a9f98-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-694">Finance</span></span></td>
<td><span data-ttu-id="a9f98-695">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-695">10001</span></span></td>
<td><span data-ttu-id="a9f98-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-696">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-697">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="a9f98-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-700">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-700">CC003</span></span></td>
<td><span data-ttu-id="a9f98-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-701">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-702">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-702">10001</span></span></td>
<td><span data-ttu-id="a9f98-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-703">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-704">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-705">713.75</span><span class="sxs-lookup"><span data-stu-id="a9f98-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-707">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-707">CC003</span></span></td>
<td><span data-ttu-id="a9f98-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-708">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-709">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-709">10001</span></span></td>
<td><span data-ttu-id="a9f98-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-710">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-711">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="a9f98-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-714">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-714">CC003</span></span></td>
<td><span data-ttu-id="a9f98-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-715">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-716">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-716">10001</span></span></td>
<td><span data-ttu-id="a9f98-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-717">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-718">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-719">286.25</span><span class="sxs-lookup"><span data-stu-id="a9f98-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-721">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-721">CC003</span></span></td>
<td><span data-ttu-id="a9f98-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-722">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-723">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-723">10001</span></span></td>
<td><span data-ttu-id="a9f98-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-724">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-725">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="a9f98-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-728">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-729">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-730">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-730">10001</span></span></td>
<td><span data-ttu-id="a9f98-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-731">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-732">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-733">776.36</span><span class="sxs-lookup"><span data-stu-id="a9f98-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-735">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-736">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-737">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-737">10001</span></span></td>
<td><span data-ttu-id="a9f98-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-738">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-739">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a9f98-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-742">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-743">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-744">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-744">10001</span></span></td>
<td><span data-ttu-id="a9f98-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-745">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-746">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-747">223.64</span><span class="sxs-lookup"><span data-stu-id="a9f98-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="a9f98-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-749">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-750">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-751">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-751">10001</span></span></td>
<td><span data-ttu-id="a9f98-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-752">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-753">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a9f98-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a9f98-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a9f98-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a9f98-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-757">Cost element</span></span></th>
<th><span data-ttu-id="a9f98-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-758">Cost behavior</span></span></th>
<th><span data-ttu-id="a9f98-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="a9f98-759">Amount</span></span></th>
<th><span data-ttu-id="a9f98-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="a9f98-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a9f98-761">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-761">CC001</span></span></td>
<td><span data-ttu-id="a9f98-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-762">HR</span></span></td>
<td><span data-ttu-id="a9f98-763">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-763">10001</span></span></td>
<td><span data-ttu-id="a9f98-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-764">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-765">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-766">-500.00</span></span></td>
<td><span data-ttu-id="a9f98-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-768">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-768">CC002</span></span></td>
<td><span data-ttu-id="a9f98-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-769">Finance</span></span></td>
<td><span data-ttu-id="a9f98-770">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-770">10001</span></span></td>
<td><span data-ttu-id="a9f98-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-771">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-772">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-773">175.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-773">175.00</span></span></td>
<td><span data-ttu-id="a9f98-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-775">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-775">CC003</span></span></td>
<td><span data-ttu-id="a9f98-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-776">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-777">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-777">10001</span></span></td>
<td><span data-ttu-id="a9f98-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-778">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-779">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-780">275.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-780">275.00</span></span></td>
<td><span data-ttu-id="a9f98-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-782">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-782">CC004</span></span></td>
<td><span data-ttu-id="a9f98-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-783">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-784">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-784">10001</span></span></td>
<td><span data-ttu-id="a9f98-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-785">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-786">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-787">50,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-787">50,00</span></span></td>
<td><span data-ttu-id="a9f98-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-789">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-789">CC001</span></span></td>
<td><span data-ttu-id="a9f98-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="a9f98-790">HR</span></span></td>
<td><span data-ttu-id="a9f98-791">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-791">10001</span></span></td>
<td><span data-ttu-id="a9f98-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-792">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-793">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="a9f98-794">-1,245.71</span></span></td>
<td><span data-ttu-id="a9f98-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-796">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-796">CC002</span></span></td>
<td><span data-ttu-id="a9f98-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-797">Finance</span></span></td>
<td><span data-ttu-id="a9f98-798">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-798">10001</span></span></td>
<td><span data-ttu-id="a9f98-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-799">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-800">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-801">436.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-801">436.00</span></span></td>
<td><span data-ttu-id="a9f98-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-803">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-803">CC003</span></span></td>
<td><span data-ttu-id="a9f98-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-804">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-805">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-805">10001</span></span></td>
<td><span data-ttu-id="a9f98-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-806">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-807">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-808">685.14</span><span class="sxs-lookup"><span data-stu-id="a9f98-808">685.14</span></span></td>
<td><span data-ttu-id="a9f98-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-810">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-810">CC004</span></span></td>
<td><span data-ttu-id="a9f98-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-811">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-812">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-812">10001</span></span></td>
<td><span data-ttu-id="a9f98-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-813">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-814">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-815">124.57</span><span class="sxs-lookup"><span data-stu-id="a9f98-815">124.57</span></span></td>
<td><span data-ttu-id="a9f98-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-817">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-817">CC002</span></span></td>
<td><span data-ttu-id="a9f98-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-818">Finance</span></span></td>
<td><span data-ttu-id="a9f98-819">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-819">10001</span></span></td>
<td><span data-ttu-id="a9f98-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-820">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-821">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-822">-675.00</span></span></td>
<td><span data-ttu-id="a9f98-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-824">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-824">CC003</span></span></td>
<td><span data-ttu-id="a9f98-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-825">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-826">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-826">10001</span></span></td>
<td><span data-ttu-id="a9f98-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-827">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-828">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-829">438.75</span><span class="sxs-lookup"><span data-stu-id="a9f98-829">438.75</span></span></td>
<td><span data-ttu-id="a9f98-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-831">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-831">CC004</span></span></td>
<td><span data-ttu-id="a9f98-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-832">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-833">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-833">10001</span></span></td>
<td><span data-ttu-id="a9f98-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-834">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-835">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-836">236.25</span><span class="sxs-lookup"><span data-stu-id="a9f98-836">236.25</span></span></td>
<td><span data-ttu-id="a9f98-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-838">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-838">CC002</span></span></td>
<td><span data-ttu-id="a9f98-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="a9f98-839">Finance</span></span></td>
<td><span data-ttu-id="a9f98-840">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-840">10001</span></span></td>
<td><span data-ttu-id="a9f98-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-841">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-842">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="a9f98-843">-8,150.29</span></span></td>
<td><span data-ttu-id="a9f98-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-845">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-845">CC003</span></span></td>
<td><span data-ttu-id="a9f98-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-846">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-847">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-847">10001</span></span></td>
<td><span data-ttu-id="a9f98-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-848">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-849">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a9f98-850">5,297.69</span></span></td>
<td><span data-ttu-id="a9f98-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-852">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-852">CC004</span></span></td>
<td><span data-ttu-id="a9f98-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="a9f98-853">Packaging</span></span></td>
<td><span data-ttu-id="a9f98-854">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-854">10001</span></span></td>
<td><span data-ttu-id="a9f98-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-855">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-856">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a9f98-857">2,852.60</span></span></td>
<td><span data-ttu-id="a9f98-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-859">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-859">CC003</span></span></td>
<td><span data-ttu-id="a9f98-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-860">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-861">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-861">10001</span></span></td>
<td><span data-ttu-id="a9f98-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-862">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-863">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="a9f98-864">-713.75</span></span></td>
<td><span data-ttu-id="a9f98-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-866">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-867">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-868">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-868">10001</span></span></td>
<td><span data-ttu-id="a9f98-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-869">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-870">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-871">535.31</span><span class="sxs-lookup"><span data-stu-id="a9f98-871">535.31</span></span></td>
<td><span data-ttu-id="a9f98-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-873">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-874">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-875">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-875">10001</span></span></td>
<td><span data-ttu-id="a9f98-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-876">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-877">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-878">178.44</span><span class="sxs-lookup"><span data-stu-id="a9f98-878">178.44</span></span></td>
<td><span data-ttu-id="a9f98-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-880">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-880">CC003</span></span></td>
<td><span data-ttu-id="a9f98-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-881">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-882">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-882">10001</span></span></td>
<td><span data-ttu-id="a9f98-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-883">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-884">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="a9f98-885">-5,982.83</span></span></td>
<td><span data-ttu-id="a9f98-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-887">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-888">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-889">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-889">10001</span></span></td>
<td><span data-ttu-id="a9f98-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-890">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-891">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a9f98-892">4,487.12</span></span></td>
<td><span data-ttu-id="a9f98-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-894">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-895">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-896">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-896">10001</span></span></td>
<td><span data-ttu-id="a9f98-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-897">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-898">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a9f98-899">1,495.71</span></span></td>
<td><span data-ttu-id="a9f98-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-901">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-901">CC003</span></span></td>
<td><span data-ttu-id="a9f98-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-902">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-903">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-903">10001</span></span></td>
<td><span data-ttu-id="a9f98-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-904">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-905">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="a9f98-906">-286.25</span></span></td>
<td><span data-ttu-id="a9f98-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-908">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-909">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-910">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-910">10001</span></span></td>
<td><span data-ttu-id="a9f98-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-911">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-912">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-913">241.05</span><span class="sxs-lookup"><span data-stu-id="a9f98-913">241.05</span></span></td>
<td><span data-ttu-id="a9f98-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-915">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-916">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-917">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-917">10001</span></span></td>
<td><span data-ttu-id="a9f98-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-918">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-919">Fixed cost</span></span></td>
<td><span data-ttu-id="a9f98-920">45.20</span><span class="sxs-lookup"><span data-stu-id="a9f98-920">45.20</span></span></td>
<td><span data-ttu-id="a9f98-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-922">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-922">CC003</span></span></td>
<td><span data-ttu-id="a9f98-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="a9f98-923">Assembly</span></span></td>
<td><span data-ttu-id="a9f98-924">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-924">10001</span></span></td>
<td><span data-ttu-id="a9f98-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-925">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-926">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="a9f98-927">-2,977.17</span></span></td>
<td><span data-ttu-id="a9f98-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-929">Prod 1</span></span></td>
<td><span data-ttu-id="a9f98-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-930">Product 1</span></span></td>
<td><span data-ttu-id="a9f98-931">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-931">10001</span></span></td>
<td><span data-ttu-id="a9f98-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-932">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-933">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a9f98-934">2,507.09</span></span></td>
<td><span data-ttu-id="a9f98-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a9f98-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-936">Prod 2</span></span></td>
<td><span data-ttu-id="a9f98-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-937">Product 2</span></span></td>
<td><span data-ttu-id="a9f98-938">10001</span><span class="sxs-lookup"><span data-stu-id="a9f98-938">10001</span></span></td>
<td><span data-ttu-id="a9f98-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="a9f98-939">Electricity</span></span></td>
<td><span data-ttu-id="a9f98-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-940">Variable cost</span></span></td>
<td><span data-ttu-id="a9f98-941">470.08</span><span class="sxs-lookup"><span data-stu-id="a9f98-941">470.08</span></span></td>
<td><span data-ttu-id="a9f98-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="a9f98-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="a9f98-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="a9f98-943">Conclusion</span></span>
<span data-ttu-id="a9f98-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="a9f98-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="a9f98-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="a9f98-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="a9f98-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="a9f98-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="a9f98-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="a9f98-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="a9f98-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="a9f98-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="a9f98-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="a9f98-950">Razem</span><span class="sxs-lookup"><span data-stu-id="a9f98-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a9f98-951">CC099</span><span class="sxs-lookup"><span data-stu-id="a9f98-951">CC099</span></span></th>
<th><span data-ttu-id="a9f98-952">CC001</span><span class="sxs-lookup"><span data-stu-id="a9f98-952">CC001</span></span></th>
<th><span data-ttu-id="a9f98-953">CC002</span><span class="sxs-lookup"><span data-stu-id="a9f98-953">CC002</span></span></th>
<th><span data-ttu-id="a9f98-954">CC003</span><span class="sxs-lookup"><span data-stu-id="a9f98-954">CC003</span></span></th>
<th><span data-ttu-id="a9f98-955">CC004</span><span class="sxs-lookup"><span data-stu-id="a9f98-955">CC004</span></span></th>
<th><span data-ttu-id="a9f98-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-956">Proj 1</span></span></th>
<th><span data-ttu-id="a9f98-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-957">Proj 2</span></span></th>
<th><span data-ttu-id="a9f98-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a9f98-958">Prod 1</span></span></th>
<th><span data-ttu-id="a9f98-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a9f98-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="a9f98-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="a9f98-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="a9f98-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="a9f98-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-971">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="a9f98-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="a9f98-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-973">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-974">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-975">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-976">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-977">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-978">776.36</span><span class="sxs-lookup"><span data-stu-id="a9f98-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-979">223.64</span><span class="sxs-lookup"><span data-stu-id="a9f98-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="a9f98-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="a9f98-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-982">000</span><span class="sxs-lookup"><span data-stu-id="a9f98-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-983">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-984">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-985">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-986">0,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-987">30.00</span><span class="sxs-lookup"><span data-stu-id="a9f98-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-988">10,00</span><span class="sxs-lookup"><span data-stu-id="a9f98-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a9f98-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a9f98-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a9f98-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="a9f98-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a9f98-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="a9f98-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="a9f98-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="a9f98-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="a9f98-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="a9f98-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f98-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="a9f98-996">Aby uzyskać więcej informacji, [Zasady akumulacji kosztów i obliczanie narzutu](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="a9f98-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



