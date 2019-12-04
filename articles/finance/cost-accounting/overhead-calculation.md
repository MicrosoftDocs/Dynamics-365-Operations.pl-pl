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
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
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
ms.openlocfilehash: 954e0669c3d24bcc20fe667c22b7dcc367aba1e7
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770811"
---
# <a name="overhead-calculation"></a><span data-ttu-id="734af-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="734af-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="734af-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="734af-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="734af-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="734af-105">Term definition</span></span>
---------------

<span data-ttu-id="734af-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="734af-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="734af-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="734af-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="734af-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="734af-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="734af-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="734af-109">Rent</span></span>
-   <span data-ttu-id="734af-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-110">Electricity</span></span>
-   <span data-ttu-id="734af-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="734af-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="734af-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="734af-112">Overhead calculation overview</span></span>
<span data-ttu-id="734af-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="734af-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="734af-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="734af-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="734af-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="734af-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="734af-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="734af-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="734af-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="734af-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="734af-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="734af-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="734af-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="734af-119">Version type</span></span>
-   <span data-ttu-id="734af-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="734af-120">Date and time</span></span>
-   <span data-ttu-id="734af-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="734af-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="734af-122">Fiscal year</span></span>
-   <span data-ttu-id="734af-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="734af-123">Fiscal period</span></span>

<span data-ttu-id="734af-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="734af-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="734af-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="734af-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="734af-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="734af-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="734af-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="734af-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="734af-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="734af-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="734af-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="734af-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="734af-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="734af-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="734af-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="734af-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="734af-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="734af-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="734af-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="734af-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="734af-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="734af-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="734af-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="734af-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="734af-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="734af-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="734af-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="734af-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="734af-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="734af-140">Main account</span></span></th>
<th><span data-ttu-id="734af-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="734af-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="734af-143">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-143">CC099</span></span></td>
<td><span data-ttu-id="734af-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-144">Default cost center</span></span></td>
<td><span data-ttu-id="734af-145">10001</span><span class="sxs-lookup"><span data-stu-id="734af-145">10001</span></span></td>
<td><span data-ttu-id="734af-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-146">Electricity</span></span></td>
<td><span data-ttu-id="734af-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="734af-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="734af-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="734af-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="734af-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="734af-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="734af-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-151">Define the cost behavior rule</span></span>

<span data-ttu-id="734af-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="734af-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="734af-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="734af-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="734af-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="734af-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="734af-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="734af-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="734af-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="734af-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="734af-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="734af-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="734af-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="734af-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="734af-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="734af-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="734af-160">Journal</span></span></th>
<th><span data-ttu-id="734af-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="734af-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="734af-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="734af-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="734af-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="734af-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-164">00001</span><span class="sxs-lookup"><span data-stu-id="734af-164">00001</span></span></td>
<td><span data-ttu-id="734af-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="734af-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="734af-166">Fiscal</span></span></td>
<td><span data-ttu-id="734af-167">2017</span><span class="sxs-lookup"><span data-stu-id="734af-167">2017</span></span></td>
<td><span data-ttu-id="734af-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="734af-168">Period 1</span></span></td>
<td><span data-ttu-id="734af-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="734af-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="734af-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="734af-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="734af-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="734af-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="734af-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="734af-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-173">Cost element</span></span></th>
<th><span data-ttu-id="734af-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-174">Cost behavior</span></span></th>
<th><span data-ttu-id="734af-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="734af-177">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-177">CC099</span></span></td>
<td><span data-ttu-id="734af-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-178">Default cost center</span></span></td>
<td><span data-ttu-id="734af-179">10001</span><span class="sxs-lookup"><span data-stu-id="734af-179">10001</span></span></td>
<td><span data-ttu-id="734af-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-180">Electricity</span></span></td>
<td><span data-ttu-id="734af-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="734af-181">Unclassified</span></span></td>
<td><span data-ttu-id="734af-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="734af-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="734af-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="734af-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-185">Cost element</span></span></th>
<th><span data-ttu-id="734af-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-186">Cost behavior</span></span></th>
<th><span data-ttu-id="734af-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-187">Amount</span></span></th>
<th><span data-ttu-id="734af-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="734af-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-189">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-189">CC099</span></span></td>
<td><span data-ttu-id="734af-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-190">Default cost center</span></span></td>
<td><span data-ttu-id="734af-191">10001</span><span class="sxs-lookup"><span data-stu-id="734af-191">10001</span></span></td>
<td><span data-ttu-id="734af-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-192">Electricity</span></span></td>
<td><span data-ttu-id="734af-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="734af-193">Unclassified</span></span></td>
<td><span data-ttu-id="734af-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="734af-194">10,000.00</span></span></td>
<td><span data-ttu-id="734af-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-196">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-196">CC099</span></span></td>
<td><span data-ttu-id="734af-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-197">Default cost center</span></span></td>
<td><span data-ttu-id="734af-198">10001</span><span class="sxs-lookup"><span data-stu-id="734af-198">10001</span></span></td>
<td><span data-ttu-id="734af-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-199">Electricity</span></span></td>
<td><span data-ttu-id="734af-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="734af-200">Unclassified</span></span></td>
<td><span data-ttu-id="734af-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="734af-201">-10,000.00</span></span></td>
<td><span data-ttu-id="734af-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-203">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-203">CC099</span></span></td>
<td><span data-ttu-id="734af-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-204">Default cost center</span></span></td>
<td><span data-ttu-id="734af-205">10001</span><span class="sxs-lookup"><span data-stu-id="734af-205">10001</span></span></td>
<td><span data-ttu-id="734af-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-206">Electricity</span></span></td>
<td><span data-ttu-id="734af-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-207">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="734af-208">1,000.00</span></span></td>
<td><span data-ttu-id="734af-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-210">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-210">CC099</span></span></td>
<td><span data-ttu-id="734af-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-211">Default cost center</span></span></td>
<td><span data-ttu-id="734af-212">10001</span><span class="sxs-lookup"><span data-stu-id="734af-212">10001</span></span></td>
<td><span data-ttu-id="734af-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-213">Electricity</span></span></td>
<td><span data-ttu-id="734af-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-214">Variable cost</span></span></td>
<td><span data-ttu-id="734af-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="734af-215">9,000.00</span></span></td>
<td><span data-ttu-id="734af-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="734af-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="734af-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="734af-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="734af-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="734af-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="734af-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="734af-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-221">Define the cost distribution rule</span></span>

<span data-ttu-id="734af-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="734af-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="734af-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="734af-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="734af-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="734af-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="734af-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="734af-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="734af-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="734af-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="734af-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="734af-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-228">Cost object</span></span></th>
<th><span data-ttu-id="734af-229">kWh</span><span class="sxs-lookup"><span data-stu-id="734af-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-230">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-230">CC001</span></span></td>
<td><span data-ttu-id="734af-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-231">HR</span></span></td>
<td><span data-ttu-id="734af-232">1 000</span><span class="sxs-lookup"><span data-stu-id="734af-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-233">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-233">CC002</span></span></td>
<td><span data-ttu-id="734af-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-234">Finance</span></span></td>
<td><span data-ttu-id="734af-235">6,000</span><span class="sxs-lookup"><span data-stu-id="734af-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-236">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-236">CC003</span></span></td>
<td><span data-ttu-id="734af-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-237">Assembly</span></span></td>
<td><span data-ttu-id="734af-238">0</span><span class="sxs-lookup"><span data-stu-id="734af-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="734af-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-240">Cost object</span></span></th>
<th><span data-ttu-id="734af-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="734af-241">Magnitude</span></span></th>
<th><span data-ttu-id="734af-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="734af-242">Allocation factor</span></span></th>
<th><span data-ttu-id="734af-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-244">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-244">CC001</span></span></td>
<td><span data-ttu-id="734af-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-245">HR</span></span></td>
<td><span data-ttu-id="734af-246">1 000</span><span class="sxs-lookup"><span data-stu-id="734af-246">1,000</span></span></td>
<td><span data-ttu-id="734af-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="734af-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="734af-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="734af-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-249">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-249">CC002</span></span></td>
<td><span data-ttu-id="734af-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-250">Finance</span></span></td>
<td><span data-ttu-id="734af-251">6,000</span><span class="sxs-lookup"><span data-stu-id="734af-251">6,000</span></span></td>
<td><span data-ttu-id="734af-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="734af-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="734af-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="734af-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-254">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-254">CC003</span></span></td>
<td><span data-ttu-id="734af-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-255">Assembly</span></span></td>
<td><span data-ttu-id="734af-256">0</span><span class="sxs-lookup"><span data-stu-id="734af-256">0</span></span></td>
<td><span data-ttu-id="734af-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="734af-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="734af-258">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="734af-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="734af-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="734af-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-261">Cost object</span></span></th>
<th><span data-ttu-id="734af-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="734af-262">Formula</span></span></th>
<th><span data-ttu-id="734af-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="734af-263">Magnitude</span></span></th>
<th><span data-ttu-id="734af-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="734af-264">Allocation factor</span></span></th>
<th><span data-ttu-id="734af-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-266">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-266">CC001</span></span></td>
<td><span data-ttu-id="734af-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-267">HR</span></span></td>
<td><span data-ttu-id="734af-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="734af-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="734af-269">1</span><span class="sxs-lookup"><span data-stu-id="734af-269">1</span></span></td>
<td><span data-ttu-id="734af-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="734af-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="734af-271">500.00</span><span class="sxs-lookup"><span data-stu-id="734af-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-272">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-272">CC002</span></span></td>
<td><span data-ttu-id="734af-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-273">Finance</span></span></td>
<td><span data-ttu-id="734af-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="734af-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="734af-275">1</span><span class="sxs-lookup"><span data-stu-id="734af-275">1</span></span></td>
<td><span data-ttu-id="734af-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="734af-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="734af-277">500.00</span><span class="sxs-lookup"><span data-stu-id="734af-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-278">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-278">CC003</span></span></td>
<td><span data-ttu-id="734af-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-279">Assembly</span></span></td>
<td><span data-ttu-id="734af-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="734af-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="734af-281">0</span><span class="sxs-lookup"><span data-stu-id="734af-281">0</span></span></td>
<td><span data-ttu-id="734af-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="734af-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="734af-283">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="734af-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="734af-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="734af-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="734af-285">Journal</span></span></th>
<th><span data-ttu-id="734af-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="734af-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="734af-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="734af-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="734af-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="734af-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-289">00002</span><span class="sxs-lookup"><span data-stu-id="734af-289">00002</span></span></td>
<td><span data-ttu-id="734af-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="734af-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="734af-291">Fiscal</span></span></td>
<td><span data-ttu-id="734af-292">2017</span><span class="sxs-lookup"><span data-stu-id="734af-292">2017</span></span></td>
<td><span data-ttu-id="734af-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="734af-293">Period 1</span></span></td>
<td><span data-ttu-id="734af-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="734af-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="734af-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="734af-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="734af-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="734af-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="734af-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="734af-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-298">Cost element</span></span></th>
<th><span data-ttu-id="734af-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-299">Cost behavior</span></span></th>
<th><span data-ttu-id="734af-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-302">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-302">CC099</span></span></td>
<td><span data-ttu-id="734af-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-303">Default cost center</span></span></td>
<td><span data-ttu-id="734af-304">10001</span><span class="sxs-lookup"><span data-stu-id="734af-304">10001</span></span></td>
<td><span data-ttu-id="734af-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-305">Electricity</span></span></td>
<td><span data-ttu-id="734af-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-306">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="734af-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-309">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-309">CC099</span></span></td>
<td><span data-ttu-id="734af-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-310">Default cost center</span></span></td>
<td><span data-ttu-id="734af-311">10001</span><span class="sxs-lookup"><span data-stu-id="734af-311">10001</span></span></td>
<td><span data-ttu-id="734af-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-312">Electricity</span></span></td>
<td><span data-ttu-id="734af-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-313">Variable cost</span></span></td>
<td><span data-ttu-id="734af-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="734af-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="734af-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="734af-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-317">Cost element</span></span></th>
<th><span data-ttu-id="734af-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-318">Cost behavior</span></span></th>
<th><span data-ttu-id="734af-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-319">Amount</span></span></th>
<th><span data-ttu-id="734af-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="734af-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-321">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-321">CC099</span></span></td>
<td><span data-ttu-id="734af-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-322">Default cost center</span></span></td>
<td><span data-ttu-id="734af-323">10001</span><span class="sxs-lookup"><span data-stu-id="734af-323">10001</span></span></td>
<td><span data-ttu-id="734af-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-324">Electricity</span></span></td>
<td><span data-ttu-id="734af-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-325">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="734af-326">-1,000.00</span></span></td>
<td><span data-ttu-id="734af-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-328">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-328">CC001</span></span></td>
<td><span data-ttu-id="734af-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-329">HR</span></span></td>
<td><span data-ttu-id="734af-330">10001</span><span class="sxs-lookup"><span data-stu-id="734af-330">10001</span></span></td>
<td><span data-ttu-id="734af-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-331">Electricity</span></span></td>
<td><span data-ttu-id="734af-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-332">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-333">500.00</span><span class="sxs-lookup"><span data-stu-id="734af-333">500.00</span></span></td>
<td><span data-ttu-id="734af-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-335">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-335">CC002</span></span></td>
<td><span data-ttu-id="734af-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-336">Finance</span></span></td>
<td><span data-ttu-id="734af-337">10001</span><span class="sxs-lookup"><span data-stu-id="734af-337">10001</span></span></td>
<td><span data-ttu-id="734af-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-338">Electricity</span></span></td>
<td><span data-ttu-id="734af-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-339">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-340">500.00</span><span class="sxs-lookup"><span data-stu-id="734af-340">500.00</span></span></td>
<td><span data-ttu-id="734af-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-342">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-342">CC099</span></span></td>
<td><span data-ttu-id="734af-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-343">Default cost center</span></span></td>
<td><span data-ttu-id="734af-344">10001</span><span class="sxs-lookup"><span data-stu-id="734af-344">10001</span></span></td>
<td><span data-ttu-id="734af-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-345">Electricity</span></span></td>
<td><span data-ttu-id="734af-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-346">Variable cost</span></span></td>
<td><span data-ttu-id="734af-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="734af-347">-9,000.00</span></span></td>
<td><span data-ttu-id="734af-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-349">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-349">CC001</span></span></td>
<td><span data-ttu-id="734af-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-350">HR</span></span></td>
<td><span data-ttu-id="734af-351">10001</span><span class="sxs-lookup"><span data-stu-id="734af-351">10001</span></span></td>
<td><span data-ttu-id="734af-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-352">Electricity</span></span></td>
<td><span data-ttu-id="734af-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-353">Variable cost</span></span></td>
<td><span data-ttu-id="734af-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="734af-354">1,285.71</span></span></td>
<td><span data-ttu-id="734af-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-356">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-356">CC002</span></span></td>
<td><span data-ttu-id="734af-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-357">Finance</span></span></td>
<td><span data-ttu-id="734af-358">10001</span><span class="sxs-lookup"><span data-stu-id="734af-358">10001</span></span></td>
<td><span data-ttu-id="734af-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-359">Electricity</span></span></td>
<td><span data-ttu-id="734af-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-360">Variable cost</span></span></td>
<td><span data-ttu-id="734af-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="734af-361">7,714.29</span></span></td>
<td><span data-ttu-id="734af-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="734af-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="734af-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="734af-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="734af-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="734af-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="734af-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="734af-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="734af-367">Define the overhead rate</span></span>

<span data-ttu-id="734af-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="734af-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="734af-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="734af-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-370">Cost object</span></span></th>
<th><span data-ttu-id="734af-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="734af-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="734af-372">Proj 1</span></span></td>
<td><span data-ttu-id="734af-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="734af-373">Project 1</span></span></td>
<td><span data-ttu-id="734af-374">3</span><span class="sxs-lookup"><span data-stu-id="734af-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="734af-375">Proj 2</span></span></td>
<td><span data-ttu-id="734af-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="734af-376">Project 2</span></span></td>
<td><span data-ttu-id="734af-377">1</span><span class="sxs-lookup"><span data-stu-id="734af-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="734af-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-379">Cost object</span></span></th>
<th><span data-ttu-id="734af-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-380">Cost element</span></span></th>
<th><span data-ttu-id="734af-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-381">Cost behavior</span></span></th>
<th><span data-ttu-id="734af-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="734af-382">Units</span></span></th>
<th><span data-ttu-id="734af-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="734af-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-384">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-384">CC001</span></span></td>
<td><span data-ttu-id="734af-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-385">HR</span></span></td>
<td><span data-ttu-id="734af-386">10001</span><span class="sxs-lookup"><span data-stu-id="734af-386">10001</span></span></td>
<td><span data-ttu-id="734af-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-387">Variable cost</span></span></td>
<td><span data-ttu-id="734af-388">1</span><span class="sxs-lookup"><span data-stu-id="734af-388">1</span></span></td>
<td><span data-ttu-id="734af-389">10</span><span class="sxs-lookup"><span data-stu-id="734af-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="734af-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-391">Cost object</span></span></th>
<th><span data-ttu-id="734af-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="734af-392">Magnitude</span></span></th>
<th><span data-ttu-id="734af-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-393">Cost element</span></span></th>
<th><span data-ttu-id="734af-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="734af-394">Allocation factor</span></span></th>
<th><span data-ttu-id="734af-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="734af-396">Proj 1</span></span></td>
<td><span data-ttu-id="734af-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="734af-397">Project 1</span></span></td>
<td><span data-ttu-id="734af-398">3</span><span class="sxs-lookup"><span data-stu-id="734af-398">3</span></span></td>
<td><span data-ttu-id="734af-399">10001</span><span class="sxs-lookup"><span data-stu-id="734af-399">10001</span></span></td>
<td><span data-ttu-id="734af-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="734af-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="734af-401">30.00</span><span class="sxs-lookup"><span data-stu-id="734af-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="734af-402">Proj 2</span></span></td>
<td><span data-ttu-id="734af-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="734af-403">Project 2</span></span></td>
<td><span data-ttu-id="734af-404">1</span><span class="sxs-lookup"><span data-stu-id="734af-404">1</span></span></td>
<td><span data-ttu-id="734af-405">10001</span><span class="sxs-lookup"><span data-stu-id="734af-405">10001</span></span></td>
<td><span data-ttu-id="734af-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="734af-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="734af-407">10,00</span><span class="sxs-lookup"><span data-stu-id="734af-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="734af-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="734af-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="734af-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="734af-409">Journal</span></span></th>
<th><span data-ttu-id="734af-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="734af-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="734af-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="734af-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="734af-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="734af-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-413">00003</span><span class="sxs-lookup"><span data-stu-id="734af-413">00003</span></span></td>
<td><span data-ttu-id="734af-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="734af-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="734af-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="734af-415">Fiscal</span></span></td>
<td><span data-ttu-id="734af-416">2017</span><span class="sxs-lookup"><span data-stu-id="734af-416">2017</span></span></td>
<td><span data-ttu-id="734af-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="734af-417">Period 1</span></span></td>
<td><span data-ttu-id="734af-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="734af-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="734af-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="734af-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="734af-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="734af-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="734af-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-421">Cost object</span></span></th>
<th><span data-ttu-id="734af-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="734af-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="734af-424">Proj 1</span></span></td>
<td><span data-ttu-id="734af-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="734af-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="734af-426">3,00</span><span class="sxs-lookup"><span data-stu-id="734af-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="734af-428">Proj 2</span></span></td>
<td><span data-ttu-id="734af-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="734af-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="734af-430">1.00</span><span class="sxs-lookup"><span data-stu-id="734af-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="734af-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="734af-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-433">Cost element</span></span></th>
<th><span data-ttu-id="734af-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-434">Cost behavior</span></span></th>
<th><span data-ttu-id="734af-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-435">Amount</span></span></th>
<th><span data-ttu-id="734af-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="734af-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="734af-437">CC0001</span></span></td>
<td><span data-ttu-id="734af-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-438">HR</span></span></td>
<td><span data-ttu-id="734af-439">10001</span><span class="sxs-lookup"><span data-stu-id="734af-439">10001</span></span></td>
<td><span data-ttu-id="734af-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-440">Electricity</span></span></td>
<td><span data-ttu-id="734af-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-441">Variable cost</span></span></td>
<td><span data-ttu-id="734af-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="734af-442">-30.00</span></span></td>
<td><span data-ttu-id="734af-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="734af-444">Proj 1</span></span></td>
<td><span data-ttu-id="734af-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="734af-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="734af-446">10001</span><span class="sxs-lookup"><span data-stu-id="734af-446">10001</span></span></td>
<td><span data-ttu-id="734af-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-447">Electricity</span></span></td>
<td><span data-ttu-id="734af-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-448">Variable cost</span></span></td>
<td><span data-ttu-id="734af-449">30.00</span><span class="sxs-lookup"><span data-stu-id="734af-449">30.00</span></span></td>
<td><span data-ttu-id="734af-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-451">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-451">CC001</span></span></td>
<td><span data-ttu-id="734af-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-452">HR</span></span></td>
<td><span data-ttu-id="734af-453">10001</span><span class="sxs-lookup"><span data-stu-id="734af-453">10001</span></span></td>
<td><span data-ttu-id="734af-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-454">Electricity</span></span></td>
<td><span data-ttu-id="734af-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-455">Variable cost</span></span></td>
<td><span data-ttu-id="734af-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="734af-456">-10.00</span></span></td>
<td><span data-ttu-id="734af-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="734af-458">Proj 2</span></span></td>
<td><span data-ttu-id="734af-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="734af-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="734af-460">10001</span><span class="sxs-lookup"><span data-stu-id="734af-460">10001</span></span></td>
<td><span data-ttu-id="734af-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-461">Electricity</span></span></td>
<td><span data-ttu-id="734af-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-462">Variable cost</span></span></td>
<td><span data-ttu-id="734af-463">10,00</span><span class="sxs-lookup"><span data-stu-id="734af-463">10.00</span></span></td>
<td><span data-ttu-id="734af-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="734af-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="734af-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="734af-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="734af-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="734af-468">Aplikacja Finance obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="734af-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="734af-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="734af-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="734af-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="734af-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="734af-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="734af-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="734af-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="734af-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="734af-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="734af-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="734af-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-475">Define the cost allocation</span></span>

<span data-ttu-id="734af-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="734af-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="734af-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="734af-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-479">Cost object</span></span></th>
<th><span data-ttu-id="734af-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="734af-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-481">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-481">CC002</span></span></td>
<td><span data-ttu-id="734af-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-482">Finance</span></span></td>
<td><span data-ttu-id="734af-483">35</span><span class="sxs-lookup"><span data-stu-id="734af-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-484">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-484">CC003</span></span></td>
<td><span data-ttu-id="734af-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-485">Assembly</span></span></td>
<td><span data-ttu-id="734af-486">55</span><span class="sxs-lookup"><span data-stu-id="734af-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-487">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-487">CC004</span></span></td>
<td><span data-ttu-id="734af-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-488">Packaging</span></span></td>
<td><span data-ttu-id="734af-489">10</span><span class="sxs-lookup"><span data-stu-id="734af-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="734af-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="734af-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-492">Cost object</span></span></th>
<th><span data-ttu-id="734af-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="734af-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-494">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-494">CC003</span></span></td>
<td><span data-ttu-id="734af-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-495">Assembly</span></span></td>
<td><span data-ttu-id="734af-496">65</span><span class="sxs-lookup"><span data-stu-id="734af-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-497">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-497">CC004</span></span></td>
<td><span data-ttu-id="734af-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-498">Packaging</span></span></td>
<td><span data-ttu-id="734af-499">35</span><span class="sxs-lookup"><span data-stu-id="734af-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="734af-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="734af-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-502">Cost object</span></span></th>
<th><span data-ttu-id="734af-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="734af-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-504">Prod 1</span></span></td>
<td><span data-ttu-id="734af-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-505">Product 1</span></span></td>
<td><span data-ttu-id="734af-506">60</span><span class="sxs-lookup"><span data-stu-id="734af-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-507">Prod 2</span></span></td>
<td><span data-ttu-id="734af-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-508">Product 2</span></span></td>
<td><span data-ttu-id="734af-509">20</span><span class="sxs-lookup"><span data-stu-id="734af-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="734af-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="734af-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-512">Cost object</span></span></th>
<th><span data-ttu-id="734af-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="734af-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-514">Prod 1</span></span></td>
<td><span data-ttu-id="734af-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-515">Product 1</span></span></td>
<td><span data-ttu-id="734af-516">80</span><span class="sxs-lookup"><span data-stu-id="734af-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-517">Prod 2</span></span></td>
<td><span data-ttu-id="734af-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-518">Product 2</span></span></td>
<td><span data-ttu-id="734af-519">15</span><span class="sxs-lookup"><span data-stu-id="734af-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="734af-520">Miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="734af-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="734af-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="734af-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="734af-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="734af-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-523">Cost object</span></span></th>
<th><span data-ttu-id="734af-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="734af-524">Magnitude</span></span></th>
<th><span data-ttu-id="734af-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="734af-525">Allocation factor</span></span></th>
<th><span data-ttu-id="734af-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-526">Amount</span></span></th>
<th><span data-ttu-id="734af-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-528">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-528">CC002</span></span></td>
<td><span data-ttu-id="734af-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-529">Finance</span></span></td>
<td><span data-ttu-id="734af-530">35</span><span class="sxs-lookup"><span data-stu-id="734af-530">35</span></span></td>
<td><span data-ttu-id="734af-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="734af-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="734af-532">175.00</span><span class="sxs-lookup"><span data-stu-id="734af-532">175.00</span></span></td>
<td><span data-ttu-id="734af-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-534">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-534">CC003</span></span></td>
<td><span data-ttu-id="734af-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-535">Assembly</span></span></td>
<td><span data-ttu-id="734af-536">55</span><span class="sxs-lookup"><span data-stu-id="734af-536">55</span></span></td>
<td><span data-ttu-id="734af-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="734af-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="734af-538">275.00</span><span class="sxs-lookup"><span data-stu-id="734af-538">275.00</span></span></td>
<td><span data-ttu-id="734af-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-540">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-540">CC004</span></span></td>
<td><span data-ttu-id="734af-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-541">Packaging</span></span></td>
<td><span data-ttu-id="734af-542">10</span><span class="sxs-lookup"><span data-stu-id="734af-542">10</span></span></td>
<td><span data-ttu-id="734af-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="734af-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="734af-544">50,00</span><span class="sxs-lookup"><span data-stu-id="734af-544">50.00</span></span></td>
<td><span data-ttu-id="734af-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-546">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-546">CC002</span></span></td>
<td><span data-ttu-id="734af-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-547">Finance</span></span></td>
<td><span data-ttu-id="734af-548">35</span><span class="sxs-lookup"><span data-stu-id="734af-548">35</span></span></td>
<td><span data-ttu-id="734af-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="734af-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="734af-550">436.00</span><span class="sxs-lookup"><span data-stu-id="734af-550">436.00</span></span></td>
<td><span data-ttu-id="734af-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-552">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-552">CC003</span></span></td>
<td><span data-ttu-id="734af-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-553">Assembly</span></span></td>
<td><span data-ttu-id="734af-554">55</span><span class="sxs-lookup"><span data-stu-id="734af-554">55</span></span></td>
<td><span data-ttu-id="734af-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="734af-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="734af-556">685.14</span><span class="sxs-lookup"><span data-stu-id="734af-556">685.14</span></span></td>
<td><span data-ttu-id="734af-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-558">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-558">CC004</span></span></td>
<td><span data-ttu-id="734af-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-559">Packaging</span></span></td>
<td><span data-ttu-id="734af-560">10</span><span class="sxs-lookup"><span data-stu-id="734af-560">10</span></span></td>
<td><span data-ttu-id="734af-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="734af-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="734af-562">124.57</span><span class="sxs-lookup"><span data-stu-id="734af-562">124.57</span></span></td>
<td><span data-ttu-id="734af-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="734af-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-565">Cost object</span></span></th>
<th><span data-ttu-id="734af-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="734af-566">Magnitude</span></span></th>
<th><span data-ttu-id="734af-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="734af-567">Allocation factor</span></span></th>
<th><span data-ttu-id="734af-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-568">Amount</span></span></th>
<th><span data-ttu-id="734af-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-570">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-570">CC003</span></span></td>
<td><span data-ttu-id="734af-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-571">Assembly</span></span></td>
<td><span data-ttu-id="734af-572">65</span><span class="sxs-lookup"><span data-stu-id="734af-572">65</span></span></td>
<td><span data-ttu-id="734af-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="734af-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="734af-574">438.75</span><span class="sxs-lookup"><span data-stu-id="734af-574">438.75</span></span></td>
<td><span data-ttu-id="734af-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-576">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-576">CC004</span></span></td>
<td><span data-ttu-id="734af-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-577">Packaging</span></span></td>
<td><span data-ttu-id="734af-578">35</span><span class="sxs-lookup"><span data-stu-id="734af-578">35</span></span></td>
<td><span data-ttu-id="734af-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="734af-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="734af-580">236.25</span><span class="sxs-lookup"><span data-stu-id="734af-580">236.25</span></span></td>
<td><span data-ttu-id="734af-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-582">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-582">CC003</span></span></td>
<td><span data-ttu-id="734af-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-583">Assembly</span></span></td>
<td><span data-ttu-id="734af-584">65</span><span class="sxs-lookup"><span data-stu-id="734af-584">65</span></span></td>
<td><span data-ttu-id="734af-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="734af-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="734af-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="734af-586">5,297.69</span></span></td>
<td><span data-ttu-id="734af-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-588">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-588">CC004</span></span></td>
<td><span data-ttu-id="734af-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-589">Packaging</span></span></td>
<td><span data-ttu-id="734af-590">35</span><span class="sxs-lookup"><span data-stu-id="734af-590">35</span></span></td>
<td><span data-ttu-id="734af-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="734af-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="734af-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="734af-592">2,852.60</span></span></td>
<td><span data-ttu-id="734af-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="734af-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-595">Cost object</span></span></th>
<th><span data-ttu-id="734af-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="734af-596">Magnitude</span></span></th>
<th><span data-ttu-id="734af-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="734af-597">Allocation factor</span></span></th>
<th><span data-ttu-id="734af-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-598">Amount</span></span></th>
<th><span data-ttu-id="734af-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-600">Prod 1</span></span></td>
<td><span data-ttu-id="734af-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-601">Product 1</span></span></td>
<td><span data-ttu-id="734af-602">60</span><span class="sxs-lookup"><span data-stu-id="734af-602">60</span></span></td>
<td><span data-ttu-id="734af-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="734af-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="734af-604">535.31</span><span class="sxs-lookup"><span data-stu-id="734af-604">535.31</span></span></td>
<td><span data-ttu-id="734af-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-606">Prod 2</span></span></td>
<td><span data-ttu-id="734af-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-607">Product 2</span></span></td>
<td><span data-ttu-id="734af-608">20</span><span class="sxs-lookup"><span data-stu-id="734af-608">20</span></span></td>
<td><span data-ttu-id="734af-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="734af-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="734af-610">178.44</span><span class="sxs-lookup"><span data-stu-id="734af-610">178.44</span></span></td>
<td><span data-ttu-id="734af-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-612">Prod 1</span></span></td>
<td><span data-ttu-id="734af-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-613">Product 1</span></span></td>
<td><span data-ttu-id="734af-614">60</span><span class="sxs-lookup"><span data-stu-id="734af-614">60</span></span></td>
<td><span data-ttu-id="734af-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="734af-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="734af-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="734af-616">4,487.12</span></span></td>
<td><span data-ttu-id="734af-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-618">Prod 2</span></span></td>
<td><span data-ttu-id="734af-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-619">Product 2</span></span></td>
<td><span data-ttu-id="734af-620">20</span><span class="sxs-lookup"><span data-stu-id="734af-620">20</span></span></td>
<td><span data-ttu-id="734af-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="734af-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="734af-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="734af-622">1,495.71</span></span></td>
<td><span data-ttu-id="734af-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="734af-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="734af-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-625">Cost object</span></span></th>
<th><span data-ttu-id="734af-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="734af-626">Magnitude</span></span></th>
<th><span data-ttu-id="734af-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="734af-627">Allocation factor</span></span></th>
<th><span data-ttu-id="734af-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-628">Amount</span></span></th>
<th><span data-ttu-id="734af-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-630">Prod 1</span></span></td>
<td><span data-ttu-id="734af-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-631">Product 1</span></span></td>
<td><span data-ttu-id="734af-632">80</span><span class="sxs-lookup"><span data-stu-id="734af-632">80</span></span></td>
<td><span data-ttu-id="734af-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="734af-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="734af-634">241.05</span><span class="sxs-lookup"><span data-stu-id="734af-634">241.05</span></span></td>
<td><span data-ttu-id="734af-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-636">Prod 2</span></span></td>
<td><span data-ttu-id="734af-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-637">Product 2</span></span></td>
<td><span data-ttu-id="734af-638">15</span><span class="sxs-lookup"><span data-stu-id="734af-638">15</span></span></td>
<td><span data-ttu-id="734af-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="734af-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="734af-640">45.20</span><span class="sxs-lookup"><span data-stu-id="734af-640">45.20</span></span></td>
<td><span data-ttu-id="734af-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-642">Prod 1</span></span></td>
<td><span data-ttu-id="734af-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-643">Product 1</span></span></td>
<td><span data-ttu-id="734af-644">80</span><span class="sxs-lookup"><span data-stu-id="734af-644">80</span></span></td>
<td><span data-ttu-id="734af-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="734af-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="734af-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="734af-646">2,507.09</span></span></td>
<td><span data-ttu-id="734af-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-648">Prod 2</span></span></td>
<td><span data-ttu-id="734af-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-649">Product 2</span></span></td>
<td><span data-ttu-id="734af-650">15</span><span class="sxs-lookup"><span data-stu-id="734af-650">15</span></span></td>
<td><span data-ttu-id="734af-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="734af-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="734af-652">470.08</span><span class="sxs-lookup"><span data-stu-id="734af-652">470.08</span></span></td>
<td><span data-ttu-id="734af-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="734af-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="734af-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="734af-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="734af-655">Journal</span></span></th>
<th><span data-ttu-id="734af-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="734af-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="734af-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="734af-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="734af-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="734af-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-659">00004</span><span class="sxs-lookup"><span data-stu-id="734af-659">00004</span></span></td>
<td><span data-ttu-id="734af-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="734af-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="734af-661">Fiscal</span></span></td>
<td><span data-ttu-id="734af-662">2017</span><span class="sxs-lookup"><span data-stu-id="734af-662">2017</span></span></td>
<td><span data-ttu-id="734af-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="734af-663">Period 1</span></span></td>
<td><span data-ttu-id="734af-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="734af-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="734af-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="734af-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="734af-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="734af-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="734af-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="734af-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-668">Cost element</span></span></th>
<th><span data-ttu-id="734af-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-669">Cost behavior</span></span></th>
<th><span data-ttu-id="734af-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-672">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-672">CC001</span></span></td>
<td><span data-ttu-id="734af-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-673">HR</span></span></td>
<td><span data-ttu-id="734af-674">10001</span><span class="sxs-lookup"><span data-stu-id="734af-674">10001</span></span></td>
<td><span data-ttu-id="734af-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-675">Electricity</span></span></td>
<td><span data-ttu-id="734af-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-676">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-677">500.00</span><span class="sxs-lookup"><span data-stu-id="734af-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-679">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-679">CC001</span></span></td>
<td><span data-ttu-id="734af-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-680">HR</span></span></td>
<td><span data-ttu-id="734af-681">10001</span><span class="sxs-lookup"><span data-stu-id="734af-681">10001</span></span></td>
<td><span data-ttu-id="734af-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-682">Electricity</span></span></td>
<td><span data-ttu-id="734af-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-683">Variable cost</span></span></td>
<td><span data-ttu-id="734af-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="734af-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-686">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-686">CC002</span></span></td>
<td><span data-ttu-id="734af-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-687">Finance</span></span></td>
<td><span data-ttu-id="734af-688">10001</span><span class="sxs-lookup"><span data-stu-id="734af-688">10001</span></span></td>
<td><span data-ttu-id="734af-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-689">Electricity</span></span></td>
<td><span data-ttu-id="734af-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-690">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-691">675.00</span><span class="sxs-lookup"><span data-stu-id="734af-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-693">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-693">CC002</span></span></td>
<td><span data-ttu-id="734af-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-694">Finance</span></span></td>
<td><span data-ttu-id="734af-695">10001</span><span class="sxs-lookup"><span data-stu-id="734af-695">10001</span></span></td>
<td><span data-ttu-id="734af-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-696">Electricity</span></span></td>
<td><span data-ttu-id="734af-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-697">Variable cost</span></span></td>
<td><span data-ttu-id="734af-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="734af-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-700">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-700">CC003</span></span></td>
<td><span data-ttu-id="734af-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-701">Assembly</span></span></td>
<td><span data-ttu-id="734af-702">10001</span><span class="sxs-lookup"><span data-stu-id="734af-702">10001</span></span></td>
<td><span data-ttu-id="734af-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-703">Electricity</span></span></td>
<td><span data-ttu-id="734af-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-704">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-705">713.75</span><span class="sxs-lookup"><span data-stu-id="734af-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-707">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-707">CC003</span></span></td>
<td><span data-ttu-id="734af-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-708">Assembly</span></span></td>
<td><span data-ttu-id="734af-709">10001</span><span class="sxs-lookup"><span data-stu-id="734af-709">10001</span></span></td>
<td><span data-ttu-id="734af-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-710">Electricity</span></span></td>
<td><span data-ttu-id="734af-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-711">Variable cost</span></span></td>
<td><span data-ttu-id="734af-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="734af-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-714">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-714">CC003</span></span></td>
<td><span data-ttu-id="734af-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-715">Packaging</span></span></td>
<td><span data-ttu-id="734af-716">10001</span><span class="sxs-lookup"><span data-stu-id="734af-716">10001</span></span></td>
<td><span data-ttu-id="734af-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-717">Electricity</span></span></td>
<td><span data-ttu-id="734af-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-718">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-719">286.25</span><span class="sxs-lookup"><span data-stu-id="734af-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-721">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-721">CC003</span></span></td>
<td><span data-ttu-id="734af-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-722">Packaging</span></span></td>
<td><span data-ttu-id="734af-723">10001</span><span class="sxs-lookup"><span data-stu-id="734af-723">10001</span></span></td>
<td><span data-ttu-id="734af-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-724">Electricity</span></span></td>
<td><span data-ttu-id="734af-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-725">Variable cost</span></span></td>
<td><span data-ttu-id="734af-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="734af-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-728">Prod 1</span></span></td>
<td><span data-ttu-id="734af-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-729">Product 1</span></span></td>
<td><span data-ttu-id="734af-730">10001</span><span class="sxs-lookup"><span data-stu-id="734af-730">10001</span></span></td>
<td><span data-ttu-id="734af-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-731">Electricity</span></span></td>
<td><span data-ttu-id="734af-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-732">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-733">776.36</span><span class="sxs-lookup"><span data-stu-id="734af-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-735">Prod 1</span></span></td>
<td><span data-ttu-id="734af-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-736">Product 1</span></span></td>
<td><span data-ttu-id="734af-737">10001</span><span class="sxs-lookup"><span data-stu-id="734af-737">10001</span></span></td>
<td><span data-ttu-id="734af-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-738">Electricity</span></span></td>
<td><span data-ttu-id="734af-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-739">Variable cost</span></span></td>
<td><span data-ttu-id="734af-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="734af-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-742">Prod 2</span></span></td>
<td><span data-ttu-id="734af-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-743">Product 1</span></span></td>
<td><span data-ttu-id="734af-744">10001</span><span class="sxs-lookup"><span data-stu-id="734af-744">10001</span></span></td>
<td><span data-ttu-id="734af-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-745">Electricity</span></span></td>
<td><span data-ttu-id="734af-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-746">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-747">223.64</span><span class="sxs-lookup"><span data-stu-id="734af-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="734af-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-749">Prod 2</span></span></td>
<td><span data-ttu-id="734af-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-750">Product 1</span></span></td>
<td><span data-ttu-id="734af-751">10001</span><span class="sxs-lookup"><span data-stu-id="734af-751">10001</span></span></td>
<td><span data-ttu-id="734af-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-752">Electricity</span></span></td>
<td><span data-ttu-id="734af-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-753">Variable cost</span></span></td>
<td><span data-ttu-id="734af-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="734af-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="734af-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="734af-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="734af-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-757">Cost element</span></span></th>
<th><span data-ttu-id="734af-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-758">Cost behavior</span></span></th>
<th><span data-ttu-id="734af-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="734af-759">Amount</span></span></th>
<th><span data-ttu-id="734af-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="734af-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="734af-761">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-761">CC001</span></span></td>
<td><span data-ttu-id="734af-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-762">HR</span></span></td>
<td><span data-ttu-id="734af-763">10001</span><span class="sxs-lookup"><span data-stu-id="734af-763">10001</span></span></td>
<td><span data-ttu-id="734af-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-764">Electricity</span></span></td>
<td><span data-ttu-id="734af-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-765">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="734af-766">-500.00</span></span></td>
<td><span data-ttu-id="734af-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-768">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-768">CC002</span></span></td>
<td><span data-ttu-id="734af-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-769">Finance</span></span></td>
<td><span data-ttu-id="734af-770">10001</span><span class="sxs-lookup"><span data-stu-id="734af-770">10001</span></span></td>
<td><span data-ttu-id="734af-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-771">Electricity</span></span></td>
<td><span data-ttu-id="734af-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-772">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-773">175.00</span><span class="sxs-lookup"><span data-stu-id="734af-773">175.00</span></span></td>
<td><span data-ttu-id="734af-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-775">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-775">CC003</span></span></td>
<td><span data-ttu-id="734af-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-776">Assembly</span></span></td>
<td><span data-ttu-id="734af-777">10001</span><span class="sxs-lookup"><span data-stu-id="734af-777">10001</span></span></td>
<td><span data-ttu-id="734af-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-778">Electricity</span></span></td>
<td><span data-ttu-id="734af-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-779">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-780">275.00</span><span class="sxs-lookup"><span data-stu-id="734af-780">275.00</span></span></td>
<td><span data-ttu-id="734af-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-782">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-782">CC004</span></span></td>
<td><span data-ttu-id="734af-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-783">Packaging</span></span></td>
<td><span data-ttu-id="734af-784">10001</span><span class="sxs-lookup"><span data-stu-id="734af-784">10001</span></span></td>
<td><span data-ttu-id="734af-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-785">Electricity</span></span></td>
<td><span data-ttu-id="734af-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-786">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-787">50,00</span><span class="sxs-lookup"><span data-stu-id="734af-787">50,00</span></span></td>
<td><span data-ttu-id="734af-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-789">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-789">CC001</span></span></td>
<td><span data-ttu-id="734af-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="734af-790">HR</span></span></td>
<td><span data-ttu-id="734af-791">10001</span><span class="sxs-lookup"><span data-stu-id="734af-791">10001</span></span></td>
<td><span data-ttu-id="734af-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-792">Electricity</span></span></td>
<td><span data-ttu-id="734af-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-793">Variable cost</span></span></td>
<td><span data-ttu-id="734af-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="734af-794">-1,245.71</span></span></td>
<td><span data-ttu-id="734af-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-796">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-796">CC002</span></span></td>
<td><span data-ttu-id="734af-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-797">Finance</span></span></td>
<td><span data-ttu-id="734af-798">10001</span><span class="sxs-lookup"><span data-stu-id="734af-798">10001</span></span></td>
<td><span data-ttu-id="734af-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-799">Electricity</span></span></td>
<td><span data-ttu-id="734af-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-800">Variable cost</span></span></td>
<td><span data-ttu-id="734af-801">436.00</span><span class="sxs-lookup"><span data-stu-id="734af-801">436.00</span></span></td>
<td><span data-ttu-id="734af-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-803">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-803">CC003</span></span></td>
<td><span data-ttu-id="734af-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-804">Assembly</span></span></td>
<td><span data-ttu-id="734af-805">10001</span><span class="sxs-lookup"><span data-stu-id="734af-805">10001</span></span></td>
<td><span data-ttu-id="734af-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-806">Electricity</span></span></td>
<td><span data-ttu-id="734af-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-807">Variable cost</span></span></td>
<td><span data-ttu-id="734af-808">685.14</span><span class="sxs-lookup"><span data-stu-id="734af-808">685.14</span></span></td>
<td><span data-ttu-id="734af-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-810">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-810">CC004</span></span></td>
<td><span data-ttu-id="734af-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-811">Packaging</span></span></td>
<td><span data-ttu-id="734af-812">10001</span><span class="sxs-lookup"><span data-stu-id="734af-812">10001</span></span></td>
<td><span data-ttu-id="734af-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-813">Electricity</span></span></td>
<td><span data-ttu-id="734af-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-814">Variable cost</span></span></td>
<td><span data-ttu-id="734af-815">124.57</span><span class="sxs-lookup"><span data-stu-id="734af-815">124.57</span></span></td>
<td><span data-ttu-id="734af-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-817">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-817">CC002</span></span></td>
<td><span data-ttu-id="734af-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-818">Finance</span></span></td>
<td><span data-ttu-id="734af-819">10001</span><span class="sxs-lookup"><span data-stu-id="734af-819">10001</span></span></td>
<td><span data-ttu-id="734af-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-820">Electricity</span></span></td>
<td><span data-ttu-id="734af-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-821">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="734af-822">-675.00</span></span></td>
<td><span data-ttu-id="734af-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-824">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-824">CC003</span></span></td>
<td><span data-ttu-id="734af-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-825">Assembly</span></span></td>
<td><span data-ttu-id="734af-826">10001</span><span class="sxs-lookup"><span data-stu-id="734af-826">10001</span></span></td>
<td><span data-ttu-id="734af-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-827">Electricity</span></span></td>
<td><span data-ttu-id="734af-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-828">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-829">438.75</span><span class="sxs-lookup"><span data-stu-id="734af-829">438.75</span></span></td>
<td><span data-ttu-id="734af-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-831">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-831">CC004</span></span></td>
<td><span data-ttu-id="734af-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-832">Packaging</span></span></td>
<td><span data-ttu-id="734af-833">10001</span><span class="sxs-lookup"><span data-stu-id="734af-833">10001</span></span></td>
<td><span data-ttu-id="734af-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-834">Electricity</span></span></td>
<td><span data-ttu-id="734af-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-835">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-836">236.25</span><span class="sxs-lookup"><span data-stu-id="734af-836">236.25</span></span></td>
<td><span data-ttu-id="734af-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-838">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-838">CC002</span></span></td>
<td><span data-ttu-id="734af-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="734af-839">Finance</span></span></td>
<td><span data-ttu-id="734af-840">10001</span><span class="sxs-lookup"><span data-stu-id="734af-840">10001</span></span></td>
<td><span data-ttu-id="734af-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-841">Electricity</span></span></td>
<td><span data-ttu-id="734af-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-842">Variable cost</span></span></td>
<td><span data-ttu-id="734af-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="734af-843">-8,150.29</span></span></td>
<td><span data-ttu-id="734af-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-845">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-845">CC003</span></span></td>
<td><span data-ttu-id="734af-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-846">Assembly</span></span></td>
<td><span data-ttu-id="734af-847">10001</span><span class="sxs-lookup"><span data-stu-id="734af-847">10001</span></span></td>
<td><span data-ttu-id="734af-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-848">Electricity</span></span></td>
<td><span data-ttu-id="734af-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-849">Variable cost</span></span></td>
<td><span data-ttu-id="734af-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="734af-850">5,297.69</span></span></td>
<td><span data-ttu-id="734af-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-852">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-852">CC004</span></span></td>
<td><span data-ttu-id="734af-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="734af-853">Packaging</span></span></td>
<td><span data-ttu-id="734af-854">10001</span><span class="sxs-lookup"><span data-stu-id="734af-854">10001</span></span></td>
<td><span data-ttu-id="734af-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-855">Electricity</span></span></td>
<td><span data-ttu-id="734af-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-856">Variable cost</span></span></td>
<td><span data-ttu-id="734af-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="734af-857">2,852.60</span></span></td>
<td><span data-ttu-id="734af-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-859">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-859">CC003</span></span></td>
<td><span data-ttu-id="734af-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-860">Assembly</span></span></td>
<td><span data-ttu-id="734af-861">10001</span><span class="sxs-lookup"><span data-stu-id="734af-861">10001</span></span></td>
<td><span data-ttu-id="734af-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-862">Electricity</span></span></td>
<td><span data-ttu-id="734af-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-863">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="734af-864">-713.75</span></span></td>
<td><span data-ttu-id="734af-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-866">Prod 1</span></span></td>
<td><span data-ttu-id="734af-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-867">Product 1</span></span></td>
<td><span data-ttu-id="734af-868">10001</span><span class="sxs-lookup"><span data-stu-id="734af-868">10001</span></span></td>
<td><span data-ttu-id="734af-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-869">Electricity</span></span></td>
<td><span data-ttu-id="734af-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-870">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-871">535.31</span><span class="sxs-lookup"><span data-stu-id="734af-871">535.31</span></span></td>
<td><span data-ttu-id="734af-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-873">Prod 2</span></span></td>
<td><span data-ttu-id="734af-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-874">Product 2</span></span></td>
<td><span data-ttu-id="734af-875">10001</span><span class="sxs-lookup"><span data-stu-id="734af-875">10001</span></span></td>
<td><span data-ttu-id="734af-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-876">Electricity</span></span></td>
<td><span data-ttu-id="734af-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-877">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-878">178.44</span><span class="sxs-lookup"><span data-stu-id="734af-878">178.44</span></span></td>
<td><span data-ttu-id="734af-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-880">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-880">CC003</span></span></td>
<td><span data-ttu-id="734af-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-881">Assembly</span></span></td>
<td><span data-ttu-id="734af-882">10001</span><span class="sxs-lookup"><span data-stu-id="734af-882">10001</span></span></td>
<td><span data-ttu-id="734af-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-883">Electricity</span></span></td>
<td><span data-ttu-id="734af-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-884">Variable cost</span></span></td>
<td><span data-ttu-id="734af-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="734af-885">-5,982.83</span></span></td>
<td><span data-ttu-id="734af-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-887">Prod 1</span></span></td>
<td><span data-ttu-id="734af-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-888">Product 1</span></span></td>
<td><span data-ttu-id="734af-889">10001</span><span class="sxs-lookup"><span data-stu-id="734af-889">10001</span></span></td>
<td><span data-ttu-id="734af-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-890">Electricity</span></span></td>
<td><span data-ttu-id="734af-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-891">Variable cost</span></span></td>
<td><span data-ttu-id="734af-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="734af-892">4,487.12</span></span></td>
<td><span data-ttu-id="734af-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-894">Prod 2</span></span></td>
<td><span data-ttu-id="734af-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-895">Product 2</span></span></td>
<td><span data-ttu-id="734af-896">10001</span><span class="sxs-lookup"><span data-stu-id="734af-896">10001</span></span></td>
<td><span data-ttu-id="734af-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-897">Electricity</span></span></td>
<td><span data-ttu-id="734af-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-898">Variable cost</span></span></td>
<td><span data-ttu-id="734af-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="734af-899">1,495.71</span></span></td>
<td><span data-ttu-id="734af-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-901">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-901">CC003</span></span></td>
<td><span data-ttu-id="734af-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-902">Assembly</span></span></td>
<td><span data-ttu-id="734af-903">10001</span><span class="sxs-lookup"><span data-stu-id="734af-903">10001</span></span></td>
<td><span data-ttu-id="734af-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-904">Electricity</span></span></td>
<td><span data-ttu-id="734af-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-905">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="734af-906">-286.25</span></span></td>
<td><span data-ttu-id="734af-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-908">Prod 1</span></span></td>
<td><span data-ttu-id="734af-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-909">Product 1</span></span></td>
<td><span data-ttu-id="734af-910">10001</span><span class="sxs-lookup"><span data-stu-id="734af-910">10001</span></span></td>
<td><span data-ttu-id="734af-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-911">Electricity</span></span></td>
<td><span data-ttu-id="734af-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-912">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-913">241.05</span><span class="sxs-lookup"><span data-stu-id="734af-913">241.05</span></span></td>
<td><span data-ttu-id="734af-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-915">Prod 2</span></span></td>
<td><span data-ttu-id="734af-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-916">Product 2</span></span></td>
<td><span data-ttu-id="734af-917">10001</span><span class="sxs-lookup"><span data-stu-id="734af-917">10001</span></span></td>
<td><span data-ttu-id="734af-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-918">Electricity</span></span></td>
<td><span data-ttu-id="734af-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-919">Fixed cost</span></span></td>
<td><span data-ttu-id="734af-920">45.20</span><span class="sxs-lookup"><span data-stu-id="734af-920">45.20</span></span></td>
<td><span data-ttu-id="734af-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-922">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-922">CC003</span></span></td>
<td><span data-ttu-id="734af-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="734af-923">Assembly</span></span></td>
<td><span data-ttu-id="734af-924">10001</span><span class="sxs-lookup"><span data-stu-id="734af-924">10001</span></span></td>
<td><span data-ttu-id="734af-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-925">Electricity</span></span></td>
<td><span data-ttu-id="734af-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-926">Variable cost</span></span></td>
<td><span data-ttu-id="734af-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="734af-927">-2,977.17</span></span></td>
<td><span data-ttu-id="734af-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-929">Prod 1</span></span></td>
<td><span data-ttu-id="734af-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="734af-930">Product 1</span></span></td>
<td><span data-ttu-id="734af-931">10001</span><span class="sxs-lookup"><span data-stu-id="734af-931">10001</span></span></td>
<td><span data-ttu-id="734af-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-932">Electricity</span></span></td>
<td><span data-ttu-id="734af-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-933">Variable cost</span></span></td>
<td><span data-ttu-id="734af-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="734af-934">2,507.09</span></span></td>
<td><span data-ttu-id="734af-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="734af-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-936">Prod 2</span></span></td>
<td><span data-ttu-id="734af-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="734af-937">Product 2</span></span></td>
<td><span data-ttu-id="734af-938">10001</span><span class="sxs-lookup"><span data-stu-id="734af-938">10001</span></span></td>
<td><span data-ttu-id="734af-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="734af-939">Electricity</span></span></td>
<td><span data-ttu-id="734af-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-940">Variable cost</span></span></td>
<td><span data-ttu-id="734af-941">470.08</span><span class="sxs-lookup"><span data-stu-id="734af-941">470.08</span></span></td>
<td><span data-ttu-id="734af-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="734af-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="734af-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="734af-943">Conclusion</span></span>
<span data-ttu-id="734af-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="734af-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="734af-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="734af-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="734af-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="734af-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="734af-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="734af-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="734af-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="734af-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="734af-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="734af-950">Razem</span><span class="sxs-lookup"><span data-stu-id="734af-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="734af-951">CC099</span><span class="sxs-lookup"><span data-stu-id="734af-951">CC099</span></span></th>
<th><span data-ttu-id="734af-952">CC001</span><span class="sxs-lookup"><span data-stu-id="734af-952">CC001</span></span></th>
<th><span data-ttu-id="734af-953">CC002</span><span class="sxs-lookup"><span data-stu-id="734af-953">CC002</span></span></th>
<th><span data-ttu-id="734af-954">CC003</span><span class="sxs-lookup"><span data-stu-id="734af-954">CC003</span></span></th>
<th><span data-ttu-id="734af-955">CC004</span><span class="sxs-lookup"><span data-stu-id="734af-955">CC004</span></span></th>
<th><span data-ttu-id="734af-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="734af-956">Proj 1</span></span></th>
<th><span data-ttu-id="734af-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="734af-957">Proj 2</span></span></th>
<th><span data-ttu-id="734af-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="734af-958">Prod 1</span></span></th>
<th><span data-ttu-id="734af-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="734af-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="734af-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="734af-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="734af-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="734af-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="734af-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="734af-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="734af-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="734af-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="734af-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="734af-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="734af-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="734af-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="734af-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="734af-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-971">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="734af-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="734af-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-973">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-974">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-975">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-976">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-977">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="734af-978">776.36</span><span class="sxs-lookup"><span data-stu-id="734af-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-979">223.64</span><span class="sxs-lookup"><span data-stu-id="734af-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="734af-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="734af-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="734af-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-982">000</span><span class="sxs-lookup"><span data-stu-id="734af-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-983">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-984">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-985">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-986">0,00</span><span class="sxs-lookup"><span data-stu-id="734af-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-987">30.00</span><span class="sxs-lookup"><span data-stu-id="734af-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-988">10,00</span><span class="sxs-lookup"><span data-stu-id="734af-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="734af-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="734af-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="734af-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="734af-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="734af-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="734af-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="734af-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="734af-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="734af-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="734af-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="734af-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="734af-996">Aby uzyskać więcej informacji, [Zasady akumulacji kosztów i obliczanie narzutu](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="734af-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



