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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "335124"
---
# <a name="overhead-calculation"></a><span data-ttu-id="e0341-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="e0341-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0341-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="e0341-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="e0341-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="e0341-105">Term definition</span></span>
---------------

<span data-ttu-id="e0341-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="e0341-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="e0341-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="e0341-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="e0341-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="e0341-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="e0341-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="e0341-109">Rent</span></span>
-   <span data-ttu-id="e0341-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-110">Electricity</span></span>
-   <span data-ttu-id="e0341-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="e0341-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="e0341-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="e0341-112">Overhead calculation overview</span></span>
<span data-ttu-id="e0341-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="e0341-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="e0341-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="e0341-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="e0341-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="e0341-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="e0341-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="e0341-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="e0341-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="e0341-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="e0341-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="e0341-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="e0341-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="e0341-119">Version type</span></span>
-   <span data-ttu-id="e0341-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="e0341-120">Date and time</span></span>
-   <span data-ttu-id="e0341-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="e0341-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e0341-122">Fiscal year</span></span>
-   <span data-ttu-id="e0341-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e0341-123">Fiscal period</span></span>

<span data-ttu-id="e0341-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="e0341-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="e0341-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="e0341-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="e0341-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="e0341-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="e0341-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="e0341-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="e0341-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="e0341-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="e0341-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="e0341-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="e0341-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="e0341-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="e0341-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="e0341-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="e0341-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="e0341-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="e0341-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="e0341-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="e0341-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="e0341-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="e0341-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="e0341-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="e0341-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0341-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e0341-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="e0341-140">Main account</span></span></th>
<th><span data-ttu-id="e0341-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="e0341-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="e0341-143">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-143">CC099</span></span></td>
<td><span data-ttu-id="e0341-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-144">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-145">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-145">10001</span></span></td>
<td><span data-ttu-id="e0341-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-146">Electricity</span></span></td>
<td><span data-ttu-id="e0341-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="e0341-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="e0341-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="e0341-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="e0341-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="e0341-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="e0341-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-151">Define the cost behavior rule</span></span>

<span data-ttu-id="e0341-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="e0341-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="e0341-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="e0341-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="e0341-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="e0341-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="e0341-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="e0341-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="e0341-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="e0341-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="e0341-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="e0341-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="e0341-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e0341-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0341-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e0341-160">Journal</span></span></th>
<th><span data-ttu-id="e0341-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="e0341-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e0341-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e0341-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e0341-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="e0341-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-164">00001</span><span class="sxs-lookup"><span data-stu-id="e0341-164">00001</span></span></td>
<td><span data-ttu-id="e0341-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="e0341-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="e0341-166">Fiscal</span></span></td>
<td><span data-ttu-id="e0341-167">2017</span><span class="sxs-lookup"><span data-stu-id="e0341-167">2017</span></span></td>
<td><span data-ttu-id="e0341-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="e0341-168">Period 1</span></span></td>
<td><span data-ttu-id="e0341-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="e0341-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="e0341-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="e0341-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0341-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e0341-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-173">Cost element</span></span></th>
<th><span data-ttu-id="e0341-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-174">Cost behavior</span></span></th>
<th><span data-ttu-id="e0341-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="e0341-177">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-177">CC099</span></span></td>
<td><span data-ttu-id="e0341-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-178">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-179">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-179">10001</span></span></td>
<td><span data-ttu-id="e0341-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-180">Electricity</span></span></td>
<td><span data-ttu-id="e0341-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="e0341-181">Unclassified</span></span></td>
<td><span data-ttu-id="e0341-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="e0341-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e0341-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-185">Cost element</span></span></th>
<th><span data-ttu-id="e0341-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-186">Cost behavior</span></span></th>
<th><span data-ttu-id="e0341-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-187">Amount</span></span></th>
<th><span data-ttu-id="e0341-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e0341-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-189">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-189">CC099</span></span></td>
<td><span data-ttu-id="e0341-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-190">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-191">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-191">10001</span></span></td>
<td><span data-ttu-id="e0341-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-192">Electricity</span></span></td>
<td><span data-ttu-id="e0341-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="e0341-193">Unclassified</span></span></td>
<td><span data-ttu-id="e0341-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="e0341-194">10,000.00</span></span></td>
<td><span data-ttu-id="e0341-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-196">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-196">CC099</span></span></td>
<td><span data-ttu-id="e0341-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-197">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-198">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-198">10001</span></span></td>
<td><span data-ttu-id="e0341-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-199">Electricity</span></span></td>
<td><span data-ttu-id="e0341-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="e0341-200">Unclassified</span></span></td>
<td><span data-ttu-id="e0341-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-201">-10,000.00</span></span></td>
<td><span data-ttu-id="e0341-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-203">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-203">CC099</span></span></td>
<td><span data-ttu-id="e0341-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-204">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-205">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-205">10001</span></span></td>
<td><span data-ttu-id="e0341-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-206">Electricity</span></span></td>
<td><span data-ttu-id="e0341-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-207">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-208">1,000.00</span></span></td>
<td><span data-ttu-id="e0341-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-210">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-210">CC099</span></span></td>
<td><span data-ttu-id="e0341-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-211">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-212">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-212">10001</span></span></td>
<td><span data-ttu-id="e0341-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-213">Electricity</span></span></td>
<td><span data-ttu-id="e0341-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-214">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="e0341-215">9,000.00</span></span></td>
<td><span data-ttu-id="e0341-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="e0341-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="e0341-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="e0341-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e0341-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="e0341-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="e0341-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="e0341-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-221">Define the cost distribution rule</span></span>

<span data-ttu-id="e0341-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="e0341-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="e0341-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="e0341-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="e0341-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="e0341-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="e0341-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="e0341-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="e0341-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="e0341-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="e0341-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e0341-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-228">Cost object</span></span></th>
<th><span data-ttu-id="e0341-229">kWh</span><span class="sxs-lookup"><span data-stu-id="e0341-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-230">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-230">CC001</span></span></td>
<td><span data-ttu-id="e0341-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-231">HR</span></span></td>
<td><span data-ttu-id="e0341-232">1 000</span><span class="sxs-lookup"><span data-stu-id="e0341-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-233">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-233">CC002</span></span></td>
<td><span data-ttu-id="e0341-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-234">Finance</span></span></td>
<td><span data-ttu-id="e0341-235">6,000</span><span class="sxs-lookup"><span data-stu-id="e0341-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-236">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-236">CC003</span></span></td>
<td><span data-ttu-id="e0341-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-237">Assembly</span></span></td>
<td><span data-ttu-id="e0341-238">0</span><span class="sxs-lookup"><span data-stu-id="e0341-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="e0341-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-240">Cost object</span></span></th>
<th><span data-ttu-id="e0341-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="e0341-241">Magnitude</span></span></th>
<th><span data-ttu-id="e0341-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e0341-242">Allocation factor</span></span></th>
<th><span data-ttu-id="e0341-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-244">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-244">CC001</span></span></td>
<td><span data-ttu-id="e0341-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-245">HR</span></span></td>
<td><span data-ttu-id="e0341-246">1 000</span><span class="sxs-lookup"><span data-stu-id="e0341-246">1,000</span></span></td>
<td><span data-ttu-id="e0341-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="e0341-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="e0341-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-249">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-249">CC002</span></span></td>
<td><span data-ttu-id="e0341-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-250">Finance</span></span></td>
<td><span data-ttu-id="e0341-251">6,000</span><span class="sxs-lookup"><span data-stu-id="e0341-251">6,000</span></span></td>
<td><span data-ttu-id="e0341-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="e0341-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="e0341-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-254">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-254">CC003</span></span></td>
<td><span data-ttu-id="e0341-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-255">Assembly</span></span></td>
<td><span data-ttu-id="e0341-256">0</span><span class="sxs-lookup"><span data-stu-id="e0341-256">0</span></span></td>
<td><span data-ttu-id="e0341-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="e0341-258">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="e0341-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="e0341-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="e0341-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-261">Cost object</span></span></th>
<th><span data-ttu-id="e0341-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="e0341-262">Formula</span></span></th>
<th><span data-ttu-id="e0341-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="e0341-263">Magnitude</span></span></th>
<th><span data-ttu-id="e0341-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e0341-264">Allocation factor</span></span></th>
<th><span data-ttu-id="e0341-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-266">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-266">CC001</span></span></td>
<td><span data-ttu-id="e0341-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-267">HR</span></span></td>
<td><span data-ttu-id="e0341-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="e0341-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="e0341-269">1</span><span class="sxs-lookup"><span data-stu-id="e0341-269">1</span></span></td>
<td><span data-ttu-id="e0341-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="e0341-271">500.00</span><span class="sxs-lookup"><span data-stu-id="e0341-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-272">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-272">CC002</span></span></td>
<td><span data-ttu-id="e0341-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-273">Finance</span></span></td>
<td><span data-ttu-id="e0341-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="e0341-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="e0341-275">1</span><span class="sxs-lookup"><span data-stu-id="e0341-275">1</span></span></td>
<td><span data-ttu-id="e0341-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="e0341-277">500.00</span><span class="sxs-lookup"><span data-stu-id="e0341-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-278">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-278">CC003</span></span></td>
<td><span data-ttu-id="e0341-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-279">Assembly</span></span></td>
<td><span data-ttu-id="e0341-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="e0341-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="e0341-281">0</span><span class="sxs-lookup"><span data-stu-id="e0341-281">0</span></span></td>
<td><span data-ttu-id="e0341-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="e0341-283">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="e0341-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e0341-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0341-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e0341-285">Journal</span></span></th>
<th><span data-ttu-id="e0341-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="e0341-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e0341-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e0341-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e0341-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="e0341-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-289">00002</span><span class="sxs-lookup"><span data-stu-id="e0341-289">00002</span></span></td>
<td><span data-ttu-id="e0341-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="e0341-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="e0341-291">Fiscal</span></span></td>
<td><span data-ttu-id="e0341-292">2017</span><span class="sxs-lookup"><span data-stu-id="e0341-292">2017</span></span></td>
<td><span data-ttu-id="e0341-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="e0341-293">Period 1</span></span></td>
<td><span data-ttu-id="e0341-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="e0341-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="e0341-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="e0341-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0341-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e0341-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-298">Cost element</span></span></th>
<th><span data-ttu-id="e0341-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-299">Cost behavior</span></span></th>
<th><span data-ttu-id="e0341-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-302">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-302">CC099</span></span></td>
<td><span data-ttu-id="e0341-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-303">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-304">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-304">10001</span></span></td>
<td><span data-ttu-id="e0341-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-305">Electricity</span></span></td>
<td><span data-ttu-id="e0341-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-306">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-309">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-309">CC099</span></span></td>
<td><span data-ttu-id="e0341-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-310">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-311">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-311">10001</span></span></td>
<td><span data-ttu-id="e0341-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-312">Electricity</span></span></td>
<td><span data-ttu-id="e0341-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-313">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="e0341-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e0341-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-317">Cost element</span></span></th>
<th><span data-ttu-id="e0341-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-318">Cost behavior</span></span></th>
<th><span data-ttu-id="e0341-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-319">Amount</span></span></th>
<th><span data-ttu-id="e0341-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e0341-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-321">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-321">CC099</span></span></td>
<td><span data-ttu-id="e0341-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-322">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-323">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-323">10001</span></span></td>
<td><span data-ttu-id="e0341-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-324">Electricity</span></span></td>
<td><span data-ttu-id="e0341-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-325">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-326">-1,000.00</span></span></td>
<td><span data-ttu-id="e0341-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-328">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-328">CC001</span></span></td>
<td><span data-ttu-id="e0341-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-329">HR</span></span></td>
<td><span data-ttu-id="e0341-330">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-330">10001</span></span></td>
<td><span data-ttu-id="e0341-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-331">Electricity</span></span></td>
<td><span data-ttu-id="e0341-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-332">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-333">500.00</span><span class="sxs-lookup"><span data-stu-id="e0341-333">500.00</span></span></td>
<td><span data-ttu-id="e0341-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-335">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-335">CC002</span></span></td>
<td><span data-ttu-id="e0341-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-336">Finance</span></span></td>
<td><span data-ttu-id="e0341-337">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-337">10001</span></span></td>
<td><span data-ttu-id="e0341-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-338">Electricity</span></span></td>
<td><span data-ttu-id="e0341-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-339">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-340">500.00</span><span class="sxs-lookup"><span data-stu-id="e0341-340">500.00</span></span></td>
<td><span data-ttu-id="e0341-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-342">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-342">CC099</span></span></td>
<td><span data-ttu-id="e0341-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-343">Default cost center</span></span></td>
<td><span data-ttu-id="e0341-344">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-344">10001</span></span></td>
<td><span data-ttu-id="e0341-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-345">Electricity</span></span></td>
<td><span data-ttu-id="e0341-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-346">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="e0341-347">-9,000.00</span></span></td>
<td><span data-ttu-id="e0341-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-349">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-349">CC001</span></span></td>
<td><span data-ttu-id="e0341-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-350">HR</span></span></td>
<td><span data-ttu-id="e0341-351">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-351">10001</span></span></td>
<td><span data-ttu-id="e0341-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-352">Electricity</span></span></td>
<td><span data-ttu-id="e0341-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-353">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="e0341-354">1,285.71</span></span></td>
<td><span data-ttu-id="e0341-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-356">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-356">CC002</span></span></td>
<td><span data-ttu-id="e0341-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-357">Finance</span></span></td>
<td><span data-ttu-id="e0341-358">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-358">10001</span></span></td>
<td><span data-ttu-id="e0341-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-359">Electricity</span></span></td>
<td><span data-ttu-id="e0341-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-360">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="e0341-361">7,714.29</span></span></td>
<td><span data-ttu-id="e0341-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="e0341-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="e0341-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="e0341-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="e0341-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="e0341-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e0341-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="e0341-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="e0341-367">Define the overhead rate</span></span>

<span data-ttu-id="e0341-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="e0341-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="e0341-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e0341-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-370">Cost object</span></span></th>
<th><span data-ttu-id="e0341-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="e0341-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e0341-372">Proj 1</span></span></td>
<td><span data-ttu-id="e0341-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-373">Project 1</span></span></td>
<td><span data-ttu-id="e0341-374">3</span><span class="sxs-lookup"><span data-stu-id="e0341-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e0341-375">Proj 2</span></span></td>
<td><span data-ttu-id="e0341-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-376">Project 2</span></span></td>
<td><span data-ttu-id="e0341-377">1</span><span class="sxs-lookup"><span data-stu-id="e0341-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="e0341-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-379">Cost object</span></span></th>
<th><span data-ttu-id="e0341-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-380">Cost element</span></span></th>
<th><span data-ttu-id="e0341-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-381">Cost behavior</span></span></th>
<th><span data-ttu-id="e0341-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="e0341-382">Units</span></span></th>
<th><span data-ttu-id="e0341-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="e0341-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-384">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-384">CC001</span></span></td>
<td><span data-ttu-id="e0341-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-385">HR</span></span></td>
<td><span data-ttu-id="e0341-386">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-386">10001</span></span></td>
<td><span data-ttu-id="e0341-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-387">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-388">1</span><span class="sxs-lookup"><span data-stu-id="e0341-388">1</span></span></td>
<td><span data-ttu-id="e0341-389">10</span><span class="sxs-lookup"><span data-stu-id="e0341-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="e0341-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-391">Cost object</span></span></th>
<th><span data-ttu-id="e0341-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="e0341-392">Magnitude</span></span></th>
<th><span data-ttu-id="e0341-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-393">Cost element</span></span></th>
<th><span data-ttu-id="e0341-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e0341-394">Allocation factor</span></span></th>
<th><span data-ttu-id="e0341-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e0341-396">Proj 1</span></span></td>
<td><span data-ttu-id="e0341-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-397">Project 1</span></span></td>
<td><span data-ttu-id="e0341-398">3</span><span class="sxs-lookup"><span data-stu-id="e0341-398">3</span></span></td>
<td><span data-ttu-id="e0341-399">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-399">10001</span></span></td>
<td><span data-ttu-id="e0341-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="e0341-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="e0341-401">30.00</span><span class="sxs-lookup"><span data-stu-id="e0341-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e0341-402">Proj 2</span></span></td>
<td><span data-ttu-id="e0341-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-403">Project 2</span></span></td>
<td><span data-ttu-id="e0341-404">1</span><span class="sxs-lookup"><span data-stu-id="e0341-404">1</span></span></td>
<td><span data-ttu-id="e0341-405">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-405">10001</span></span></td>
<td><span data-ttu-id="e0341-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="e0341-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="e0341-407">10,00</span><span class="sxs-lookup"><span data-stu-id="e0341-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="e0341-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e0341-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0341-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e0341-409">Journal</span></span></th>
<th><span data-ttu-id="e0341-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="e0341-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e0341-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e0341-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e0341-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="e0341-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-413">00003</span><span class="sxs-lookup"><span data-stu-id="e0341-413">00003</span></span></td>
<td><span data-ttu-id="e0341-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="e0341-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="e0341-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="e0341-415">Fiscal</span></span></td>
<td><span data-ttu-id="e0341-416">2017</span><span class="sxs-lookup"><span data-stu-id="e0341-416">2017</span></span></td>
<td><span data-ttu-id="e0341-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="e0341-417">Period 1</span></span></td>
<td><span data-ttu-id="e0341-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="e0341-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="e0341-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="e0341-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0341-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e0341-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-421">Cost object</span></span></th>
<th><span data-ttu-id="e0341-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="e0341-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e0341-424">Proj 1</span></span></td>
<td><span data-ttu-id="e0341-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="e0341-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="e0341-426">3,00</span><span class="sxs-lookup"><span data-stu-id="e0341-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e0341-428">Proj 2</span></span></td>
<td><span data-ttu-id="e0341-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="e0341-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="e0341-430">1.00</span><span class="sxs-lookup"><span data-stu-id="e0341-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e0341-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-433">Cost element</span></span></th>
<th><span data-ttu-id="e0341-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-434">Cost behavior</span></span></th>
<th><span data-ttu-id="e0341-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-435">Amount</span></span></th>
<th><span data-ttu-id="e0341-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e0341-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="e0341-437">CC0001</span></span></td>
<td><span data-ttu-id="e0341-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-438">HR</span></span></td>
<td><span data-ttu-id="e0341-439">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-439">10001</span></span></td>
<td><span data-ttu-id="e0341-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-440">Electricity</span></span></td>
<td><span data-ttu-id="e0341-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-441">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="e0341-442">-30.00</span></span></td>
<td><span data-ttu-id="e0341-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e0341-444">Proj 1</span></span></td>
<td><span data-ttu-id="e0341-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="e0341-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="e0341-446">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-446">10001</span></span></td>
<td><span data-ttu-id="e0341-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-447">Electricity</span></span></td>
<td><span data-ttu-id="e0341-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-448">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-449">30.00</span><span class="sxs-lookup"><span data-stu-id="e0341-449">30.00</span></span></td>
<td><span data-ttu-id="e0341-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-451">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-451">CC001</span></span></td>
<td><span data-ttu-id="e0341-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-452">HR</span></span></td>
<td><span data-ttu-id="e0341-453">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-453">10001</span></span></td>
<td><span data-ttu-id="e0341-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-454">Electricity</span></span></td>
<td><span data-ttu-id="e0341-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-455">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="e0341-456">-10.00</span></span></td>
<td><span data-ttu-id="e0341-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e0341-458">Proj 2</span></span></td>
<td><span data-ttu-id="e0341-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="e0341-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="e0341-460">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-460">10001</span></span></td>
<td><span data-ttu-id="e0341-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-461">Electricity</span></span></td>
<td><span data-ttu-id="e0341-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-462">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-463">10,00</span><span class="sxs-lookup"><span data-stu-id="e0341-463">10.00</span></span></td>
<td><span data-ttu-id="e0341-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="e0341-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="e0341-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="e0341-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e0341-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="e0341-468">Program Finance and Operations obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="e0341-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="e0341-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="e0341-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="e0341-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="e0341-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="e0341-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="e0341-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="e0341-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="e0341-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="e0341-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="e0341-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="e0341-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-475">Define the cost allocation</span></span>

<span data-ttu-id="e0341-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="e0341-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="e0341-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e0341-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-479">Cost object</span></span></th>
<th><span data-ttu-id="e0341-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="e0341-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-481">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-481">CC002</span></span></td>
<td><span data-ttu-id="e0341-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-482">Finance</span></span></td>
<td><span data-ttu-id="e0341-483">35</span><span class="sxs-lookup"><span data-stu-id="e0341-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-484">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-484">CC003</span></span></td>
<td><span data-ttu-id="e0341-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-485">Assembly</span></span></td>
<td><span data-ttu-id="e0341-486">55</span><span class="sxs-lookup"><span data-stu-id="e0341-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-487">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-487">CC004</span></span></td>
<td><span data-ttu-id="e0341-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-488">Packaging</span></span></td>
<td><span data-ttu-id="e0341-489">10</span><span class="sxs-lookup"><span data-stu-id="e0341-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="e0341-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e0341-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-492">Cost object</span></span></th>
<th><span data-ttu-id="e0341-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="e0341-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-494">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-494">CC003</span></span></td>
<td><span data-ttu-id="e0341-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-495">Assembly</span></span></td>
<td><span data-ttu-id="e0341-496">65</span><span class="sxs-lookup"><span data-stu-id="e0341-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-497">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-497">CC004</span></span></td>
<td><span data-ttu-id="e0341-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-498">Packaging</span></span></td>
<td><span data-ttu-id="e0341-499">35</span><span class="sxs-lookup"><span data-stu-id="e0341-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="e0341-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e0341-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-502">Cost object</span></span></th>
<th><span data-ttu-id="e0341-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="e0341-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-504">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-505">Product 1</span></span></td>
<td><span data-ttu-id="e0341-506">60</span><span class="sxs-lookup"><span data-stu-id="e0341-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-507">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-508">Product 2</span></span></td>
<td><span data-ttu-id="e0341-509">20</span><span class="sxs-lookup"><span data-stu-id="e0341-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="e0341-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="e0341-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-512">Cost object</span></span></th>
<th><span data-ttu-id="e0341-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="e0341-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-514">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-515">Product 1</span></span></td>
<td><span data-ttu-id="e0341-516">80</span><span class="sxs-lookup"><span data-stu-id="e0341-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-517">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-518">Product 2</span></span></td>
<td><span data-ttu-id="e0341-519">15</span><span class="sxs-lookup"><span data-stu-id="e0341-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="e0341-520">W programie Finance and Operations miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="e0341-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="e0341-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="e0341-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="e0341-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="e0341-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-523">Cost object</span></span></th>
<th><span data-ttu-id="e0341-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="e0341-524">Magnitude</span></span></th>
<th><span data-ttu-id="e0341-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e0341-525">Allocation factor</span></span></th>
<th><span data-ttu-id="e0341-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-526">Amount</span></span></th>
<th><span data-ttu-id="e0341-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-528">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-528">CC002</span></span></td>
<td><span data-ttu-id="e0341-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-529">Finance</span></span></td>
<td><span data-ttu-id="e0341-530">35</span><span class="sxs-lookup"><span data-stu-id="e0341-530">35</span></span></td>
<td><span data-ttu-id="e0341-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="e0341-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="e0341-532">175.00</span><span class="sxs-lookup"><span data-stu-id="e0341-532">175.00</span></span></td>
<td><span data-ttu-id="e0341-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-534">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-534">CC003</span></span></td>
<td><span data-ttu-id="e0341-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-535">Assembly</span></span></td>
<td><span data-ttu-id="e0341-536">55</span><span class="sxs-lookup"><span data-stu-id="e0341-536">55</span></span></td>
<td><span data-ttu-id="e0341-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="e0341-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="e0341-538">275.00</span><span class="sxs-lookup"><span data-stu-id="e0341-538">275.00</span></span></td>
<td><span data-ttu-id="e0341-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-540">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-540">CC004</span></span></td>
<td><span data-ttu-id="e0341-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-541">Packaging</span></span></td>
<td><span data-ttu-id="e0341-542">10</span><span class="sxs-lookup"><span data-stu-id="e0341-542">10</span></span></td>
<td><span data-ttu-id="e0341-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="e0341-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="e0341-544">50,00</span><span class="sxs-lookup"><span data-stu-id="e0341-544">50.00</span></span></td>
<td><span data-ttu-id="e0341-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-546">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-546">CC002</span></span></td>
<td><span data-ttu-id="e0341-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-547">Finance</span></span></td>
<td><span data-ttu-id="e0341-548">35</span><span class="sxs-lookup"><span data-stu-id="e0341-548">35</span></span></td>
<td><span data-ttu-id="e0341-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="e0341-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="e0341-550">436.00</span><span class="sxs-lookup"><span data-stu-id="e0341-550">436.00</span></span></td>
<td><span data-ttu-id="e0341-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-552">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-552">CC003</span></span></td>
<td><span data-ttu-id="e0341-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-553">Assembly</span></span></td>
<td><span data-ttu-id="e0341-554">55</span><span class="sxs-lookup"><span data-stu-id="e0341-554">55</span></span></td>
<td><span data-ttu-id="e0341-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="e0341-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="e0341-556">685.14</span><span class="sxs-lookup"><span data-stu-id="e0341-556">685.14</span></span></td>
<td><span data-ttu-id="e0341-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-558">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-558">CC004</span></span></td>
<td><span data-ttu-id="e0341-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-559">Packaging</span></span></td>
<td><span data-ttu-id="e0341-560">10</span><span class="sxs-lookup"><span data-stu-id="e0341-560">10</span></span></td>
<td><span data-ttu-id="e0341-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="e0341-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="e0341-562">124.57</span><span class="sxs-lookup"><span data-stu-id="e0341-562">124.57</span></span></td>
<td><span data-ttu-id="e0341-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="e0341-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-565">Cost object</span></span></th>
<th><span data-ttu-id="e0341-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="e0341-566">Magnitude</span></span></th>
<th><span data-ttu-id="e0341-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e0341-567">Allocation factor</span></span></th>
<th><span data-ttu-id="e0341-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-568">Amount</span></span></th>
<th><span data-ttu-id="e0341-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-570">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-570">CC003</span></span></td>
<td><span data-ttu-id="e0341-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-571">Assembly</span></span></td>
<td><span data-ttu-id="e0341-572">65</span><span class="sxs-lookup"><span data-stu-id="e0341-572">65</span></span></td>
<td><span data-ttu-id="e0341-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="e0341-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="e0341-574">438.75</span><span class="sxs-lookup"><span data-stu-id="e0341-574">438.75</span></span></td>
<td><span data-ttu-id="e0341-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-576">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-576">CC004</span></span></td>
<td><span data-ttu-id="e0341-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-577">Packaging</span></span></td>
<td><span data-ttu-id="e0341-578">35</span><span class="sxs-lookup"><span data-stu-id="e0341-578">35</span></span></td>
<td><span data-ttu-id="e0341-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="e0341-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="e0341-580">236.25</span><span class="sxs-lookup"><span data-stu-id="e0341-580">236.25</span></span></td>
<td><span data-ttu-id="e0341-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-582">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-582">CC003</span></span></td>
<td><span data-ttu-id="e0341-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-583">Assembly</span></span></td>
<td><span data-ttu-id="e0341-584">65</span><span class="sxs-lookup"><span data-stu-id="e0341-584">65</span></span></td>
<td><span data-ttu-id="e0341-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="e0341-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="e0341-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="e0341-586">5,297.69</span></span></td>
<td><span data-ttu-id="e0341-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-588">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-588">CC004</span></span></td>
<td><span data-ttu-id="e0341-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-589">Packaging</span></span></td>
<td><span data-ttu-id="e0341-590">35</span><span class="sxs-lookup"><span data-stu-id="e0341-590">35</span></span></td>
<td><span data-ttu-id="e0341-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="e0341-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="e0341-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="e0341-592">2,852.60</span></span></td>
<td><span data-ttu-id="e0341-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="e0341-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-595">Cost object</span></span></th>
<th><span data-ttu-id="e0341-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="e0341-596">Magnitude</span></span></th>
<th><span data-ttu-id="e0341-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e0341-597">Allocation factor</span></span></th>
<th><span data-ttu-id="e0341-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-598">Amount</span></span></th>
<th><span data-ttu-id="e0341-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-600">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-601">Product 1</span></span></td>
<td><span data-ttu-id="e0341-602">60</span><span class="sxs-lookup"><span data-stu-id="e0341-602">60</span></span></td>
<td><span data-ttu-id="e0341-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="e0341-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="e0341-604">535.31</span><span class="sxs-lookup"><span data-stu-id="e0341-604">535.31</span></span></td>
<td><span data-ttu-id="e0341-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-606">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-607">Product 2</span></span></td>
<td><span data-ttu-id="e0341-608">20</span><span class="sxs-lookup"><span data-stu-id="e0341-608">20</span></span></td>
<td><span data-ttu-id="e0341-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="e0341-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="e0341-610">178.44</span><span class="sxs-lookup"><span data-stu-id="e0341-610">178.44</span></span></td>
<td><span data-ttu-id="e0341-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-612">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-613">Product 1</span></span></td>
<td><span data-ttu-id="e0341-614">60</span><span class="sxs-lookup"><span data-stu-id="e0341-614">60</span></span></td>
<td><span data-ttu-id="e0341-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="e0341-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="e0341-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="e0341-616">4,487.12</span></span></td>
<td><span data-ttu-id="e0341-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-618">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-619">Product 2</span></span></td>
<td><span data-ttu-id="e0341-620">20</span><span class="sxs-lookup"><span data-stu-id="e0341-620">20</span></span></td>
<td><span data-ttu-id="e0341-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="e0341-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="e0341-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="e0341-622">1,495.71</span></span></td>
<td><span data-ttu-id="e0341-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e0341-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="e0341-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-625">Cost object</span></span></th>
<th><span data-ttu-id="e0341-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="e0341-626">Magnitude</span></span></th>
<th><span data-ttu-id="e0341-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="e0341-627">Allocation factor</span></span></th>
<th><span data-ttu-id="e0341-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-628">Amount</span></span></th>
<th><span data-ttu-id="e0341-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-630">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-631">Product 1</span></span></td>
<td><span data-ttu-id="e0341-632">80</span><span class="sxs-lookup"><span data-stu-id="e0341-632">80</span></span></td>
<td><span data-ttu-id="e0341-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="e0341-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="e0341-634">241.05</span><span class="sxs-lookup"><span data-stu-id="e0341-634">241.05</span></span></td>
<td><span data-ttu-id="e0341-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-636">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-637">Product 2</span></span></td>
<td><span data-ttu-id="e0341-638">15</span><span class="sxs-lookup"><span data-stu-id="e0341-638">15</span></span></td>
<td><span data-ttu-id="e0341-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="e0341-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="e0341-640">45.20</span><span class="sxs-lookup"><span data-stu-id="e0341-640">45.20</span></span></td>
<td><span data-ttu-id="e0341-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-642">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-643">Product 1</span></span></td>
<td><span data-ttu-id="e0341-644">80</span><span class="sxs-lookup"><span data-stu-id="e0341-644">80</span></span></td>
<td><span data-ttu-id="e0341-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="e0341-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="e0341-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="e0341-646">2,507.09</span></span></td>
<td><span data-ttu-id="e0341-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-648">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-649">Product 2</span></span></td>
<td><span data-ttu-id="e0341-650">15</span><span class="sxs-lookup"><span data-stu-id="e0341-650">15</span></span></td>
<td><span data-ttu-id="e0341-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="e0341-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="e0341-652">470.08</span><span class="sxs-lookup"><span data-stu-id="e0341-652">470.08</span></span></td>
<td><span data-ttu-id="e0341-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="e0341-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="e0341-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0341-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="e0341-655">Journal</span></span></th>
<th><span data-ttu-id="e0341-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="e0341-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e0341-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="e0341-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e0341-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="e0341-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-659">00004</span><span class="sxs-lookup"><span data-stu-id="e0341-659">00004</span></span></td>
<td><span data-ttu-id="e0341-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="e0341-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="e0341-661">Fiscal</span></span></td>
<td><span data-ttu-id="e0341-662">2017</span><span class="sxs-lookup"><span data-stu-id="e0341-662">2017</span></span></td>
<td><span data-ttu-id="e0341-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="e0341-663">Period 1</span></span></td>
<td><span data-ttu-id="e0341-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="e0341-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="e0341-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="e0341-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e0341-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e0341-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-668">Cost element</span></span></th>
<th><span data-ttu-id="e0341-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-669">Cost behavior</span></span></th>
<th><span data-ttu-id="e0341-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-672">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-672">CC001</span></span></td>
<td><span data-ttu-id="e0341-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-673">HR</span></span></td>
<td><span data-ttu-id="e0341-674">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-674">10001</span></span></td>
<td><span data-ttu-id="e0341-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-675">Electricity</span></span></td>
<td><span data-ttu-id="e0341-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-676">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-677">500.00</span><span class="sxs-lookup"><span data-stu-id="e0341-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-679">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-679">CC001</span></span></td>
<td><span data-ttu-id="e0341-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-680">HR</span></span></td>
<td><span data-ttu-id="e0341-681">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-681">10001</span></span></td>
<td><span data-ttu-id="e0341-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-682">Electricity</span></span></td>
<td><span data-ttu-id="e0341-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-683">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="e0341-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-686">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-686">CC002</span></span></td>
<td><span data-ttu-id="e0341-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-687">Finance</span></span></td>
<td><span data-ttu-id="e0341-688">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-688">10001</span></span></td>
<td><span data-ttu-id="e0341-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-689">Electricity</span></span></td>
<td><span data-ttu-id="e0341-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-690">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-691">675.00</span><span class="sxs-lookup"><span data-stu-id="e0341-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-693">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-693">CC002</span></span></td>
<td><span data-ttu-id="e0341-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-694">Finance</span></span></td>
<td><span data-ttu-id="e0341-695">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-695">10001</span></span></td>
<td><span data-ttu-id="e0341-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-696">Electricity</span></span></td>
<td><span data-ttu-id="e0341-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-697">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="e0341-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-700">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-700">CC003</span></span></td>
<td><span data-ttu-id="e0341-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-701">Assembly</span></span></td>
<td><span data-ttu-id="e0341-702">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-702">10001</span></span></td>
<td><span data-ttu-id="e0341-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-703">Electricity</span></span></td>
<td><span data-ttu-id="e0341-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-704">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-705">713.75</span><span class="sxs-lookup"><span data-stu-id="e0341-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-707">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-707">CC003</span></span></td>
<td><span data-ttu-id="e0341-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-708">Assembly</span></span></td>
<td><span data-ttu-id="e0341-709">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-709">10001</span></span></td>
<td><span data-ttu-id="e0341-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-710">Electricity</span></span></td>
<td><span data-ttu-id="e0341-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-711">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="e0341-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-714">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-714">CC003</span></span></td>
<td><span data-ttu-id="e0341-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-715">Packaging</span></span></td>
<td><span data-ttu-id="e0341-716">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-716">10001</span></span></td>
<td><span data-ttu-id="e0341-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-717">Electricity</span></span></td>
<td><span data-ttu-id="e0341-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-718">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-719">286.25</span><span class="sxs-lookup"><span data-stu-id="e0341-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-721">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-721">CC003</span></span></td>
<td><span data-ttu-id="e0341-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-722">Packaging</span></span></td>
<td><span data-ttu-id="e0341-723">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-723">10001</span></span></td>
<td><span data-ttu-id="e0341-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-724">Electricity</span></span></td>
<td><span data-ttu-id="e0341-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-725">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="e0341-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-728">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-729">Product 1</span></span></td>
<td><span data-ttu-id="e0341-730">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-730">10001</span></span></td>
<td><span data-ttu-id="e0341-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-731">Electricity</span></span></td>
<td><span data-ttu-id="e0341-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-732">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-733">776.36</span><span class="sxs-lookup"><span data-stu-id="e0341-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-735">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-736">Product 1</span></span></td>
<td><span data-ttu-id="e0341-737">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-737">10001</span></span></td>
<td><span data-ttu-id="e0341-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-738">Electricity</span></span></td>
<td><span data-ttu-id="e0341-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-739">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="e0341-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-742">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-743">Product 1</span></span></td>
<td><span data-ttu-id="e0341-744">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-744">10001</span></span></td>
<td><span data-ttu-id="e0341-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-745">Electricity</span></span></td>
<td><span data-ttu-id="e0341-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-746">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-747">223.64</span><span class="sxs-lookup"><span data-stu-id="e0341-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="e0341-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-749">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-750">Product 1</span></span></td>
<td><span data-ttu-id="e0341-751">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-751">10001</span></span></td>
<td><span data-ttu-id="e0341-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-752">Electricity</span></span></td>
<td><span data-ttu-id="e0341-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-753">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="e0341-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e0341-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e0341-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e0341-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-757">Cost element</span></span></th>
<th><span data-ttu-id="e0341-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-758">Cost behavior</span></span></th>
<th><span data-ttu-id="e0341-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="e0341-759">Amount</span></span></th>
<th><span data-ttu-id="e0341-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="e0341-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e0341-761">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-761">CC001</span></span></td>
<td><span data-ttu-id="e0341-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-762">HR</span></span></td>
<td><span data-ttu-id="e0341-763">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-763">10001</span></span></td>
<td><span data-ttu-id="e0341-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-764">Electricity</span></span></td>
<td><span data-ttu-id="e0341-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-765">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="e0341-766">-500.00</span></span></td>
<td><span data-ttu-id="e0341-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-768">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-768">CC002</span></span></td>
<td><span data-ttu-id="e0341-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-769">Finance</span></span></td>
<td><span data-ttu-id="e0341-770">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-770">10001</span></span></td>
<td><span data-ttu-id="e0341-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-771">Electricity</span></span></td>
<td><span data-ttu-id="e0341-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-772">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-773">175.00</span><span class="sxs-lookup"><span data-stu-id="e0341-773">175.00</span></span></td>
<td><span data-ttu-id="e0341-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-775">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-775">CC003</span></span></td>
<td><span data-ttu-id="e0341-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-776">Assembly</span></span></td>
<td><span data-ttu-id="e0341-777">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-777">10001</span></span></td>
<td><span data-ttu-id="e0341-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-778">Electricity</span></span></td>
<td><span data-ttu-id="e0341-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-779">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-780">275.00</span><span class="sxs-lookup"><span data-stu-id="e0341-780">275.00</span></span></td>
<td><span data-ttu-id="e0341-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-782">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-782">CC004</span></span></td>
<td><span data-ttu-id="e0341-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-783">Packaging</span></span></td>
<td><span data-ttu-id="e0341-784">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-784">10001</span></span></td>
<td><span data-ttu-id="e0341-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-785">Electricity</span></span></td>
<td><span data-ttu-id="e0341-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-786">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-787">50,00</span><span class="sxs-lookup"><span data-stu-id="e0341-787">50,00</span></span></td>
<td><span data-ttu-id="e0341-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-789">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-789">CC001</span></span></td>
<td><span data-ttu-id="e0341-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="e0341-790">HR</span></span></td>
<td><span data-ttu-id="e0341-791">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-791">10001</span></span></td>
<td><span data-ttu-id="e0341-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-792">Electricity</span></span></td>
<td><span data-ttu-id="e0341-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-793">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="e0341-794">-1,245.71</span></span></td>
<td><span data-ttu-id="e0341-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-796">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-796">CC002</span></span></td>
<td><span data-ttu-id="e0341-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-797">Finance</span></span></td>
<td><span data-ttu-id="e0341-798">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-798">10001</span></span></td>
<td><span data-ttu-id="e0341-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-799">Electricity</span></span></td>
<td><span data-ttu-id="e0341-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-800">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-801">436.00</span><span class="sxs-lookup"><span data-stu-id="e0341-801">436.00</span></span></td>
<td><span data-ttu-id="e0341-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-803">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-803">CC003</span></span></td>
<td><span data-ttu-id="e0341-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-804">Assembly</span></span></td>
<td><span data-ttu-id="e0341-805">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-805">10001</span></span></td>
<td><span data-ttu-id="e0341-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-806">Electricity</span></span></td>
<td><span data-ttu-id="e0341-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-807">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-808">685.14</span><span class="sxs-lookup"><span data-stu-id="e0341-808">685.14</span></span></td>
<td><span data-ttu-id="e0341-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-810">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-810">CC004</span></span></td>
<td><span data-ttu-id="e0341-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-811">Packaging</span></span></td>
<td><span data-ttu-id="e0341-812">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-812">10001</span></span></td>
<td><span data-ttu-id="e0341-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-813">Electricity</span></span></td>
<td><span data-ttu-id="e0341-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-814">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-815">124.57</span><span class="sxs-lookup"><span data-stu-id="e0341-815">124.57</span></span></td>
<td><span data-ttu-id="e0341-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-817">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-817">CC002</span></span></td>
<td><span data-ttu-id="e0341-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-818">Finance</span></span></td>
<td><span data-ttu-id="e0341-819">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-819">10001</span></span></td>
<td><span data-ttu-id="e0341-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-820">Electricity</span></span></td>
<td><span data-ttu-id="e0341-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-821">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="e0341-822">-675.00</span></span></td>
<td><span data-ttu-id="e0341-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-824">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-824">CC003</span></span></td>
<td><span data-ttu-id="e0341-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-825">Assembly</span></span></td>
<td><span data-ttu-id="e0341-826">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-826">10001</span></span></td>
<td><span data-ttu-id="e0341-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-827">Electricity</span></span></td>
<td><span data-ttu-id="e0341-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-828">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-829">438.75</span><span class="sxs-lookup"><span data-stu-id="e0341-829">438.75</span></span></td>
<td><span data-ttu-id="e0341-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-831">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-831">CC004</span></span></td>
<td><span data-ttu-id="e0341-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-832">Packaging</span></span></td>
<td><span data-ttu-id="e0341-833">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-833">10001</span></span></td>
<td><span data-ttu-id="e0341-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-834">Electricity</span></span></td>
<td><span data-ttu-id="e0341-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-835">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-836">236.25</span><span class="sxs-lookup"><span data-stu-id="e0341-836">236.25</span></span></td>
<td><span data-ttu-id="e0341-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-838">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-838">CC002</span></span></td>
<td><span data-ttu-id="e0341-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="e0341-839">Finance</span></span></td>
<td><span data-ttu-id="e0341-840">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-840">10001</span></span></td>
<td><span data-ttu-id="e0341-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-841">Electricity</span></span></td>
<td><span data-ttu-id="e0341-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-842">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="e0341-843">-8,150.29</span></span></td>
<td><span data-ttu-id="e0341-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-845">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-845">CC003</span></span></td>
<td><span data-ttu-id="e0341-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-846">Assembly</span></span></td>
<td><span data-ttu-id="e0341-847">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-847">10001</span></span></td>
<td><span data-ttu-id="e0341-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-848">Electricity</span></span></td>
<td><span data-ttu-id="e0341-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-849">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="e0341-850">5,297.69</span></span></td>
<td><span data-ttu-id="e0341-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-852">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-852">CC004</span></span></td>
<td><span data-ttu-id="e0341-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="e0341-853">Packaging</span></span></td>
<td><span data-ttu-id="e0341-854">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-854">10001</span></span></td>
<td><span data-ttu-id="e0341-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-855">Electricity</span></span></td>
<td><span data-ttu-id="e0341-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-856">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="e0341-857">2,852.60</span></span></td>
<td><span data-ttu-id="e0341-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-859">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-859">CC003</span></span></td>
<td><span data-ttu-id="e0341-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-860">Assembly</span></span></td>
<td><span data-ttu-id="e0341-861">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-861">10001</span></span></td>
<td><span data-ttu-id="e0341-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-862">Electricity</span></span></td>
<td><span data-ttu-id="e0341-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-863">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="e0341-864">-713.75</span></span></td>
<td><span data-ttu-id="e0341-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-866">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-867">Product 1</span></span></td>
<td><span data-ttu-id="e0341-868">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-868">10001</span></span></td>
<td><span data-ttu-id="e0341-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-869">Electricity</span></span></td>
<td><span data-ttu-id="e0341-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-870">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-871">535.31</span><span class="sxs-lookup"><span data-stu-id="e0341-871">535.31</span></span></td>
<td><span data-ttu-id="e0341-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-873">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-874">Product 2</span></span></td>
<td><span data-ttu-id="e0341-875">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-875">10001</span></span></td>
<td><span data-ttu-id="e0341-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-876">Electricity</span></span></td>
<td><span data-ttu-id="e0341-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-877">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-878">178.44</span><span class="sxs-lookup"><span data-stu-id="e0341-878">178.44</span></span></td>
<td><span data-ttu-id="e0341-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-880">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-880">CC003</span></span></td>
<td><span data-ttu-id="e0341-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-881">Assembly</span></span></td>
<td><span data-ttu-id="e0341-882">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-882">10001</span></span></td>
<td><span data-ttu-id="e0341-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-883">Electricity</span></span></td>
<td><span data-ttu-id="e0341-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-884">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="e0341-885">-5,982.83</span></span></td>
<td><span data-ttu-id="e0341-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-887">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-888">Product 1</span></span></td>
<td><span data-ttu-id="e0341-889">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-889">10001</span></span></td>
<td><span data-ttu-id="e0341-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-890">Electricity</span></span></td>
<td><span data-ttu-id="e0341-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-891">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="e0341-892">4,487.12</span></span></td>
<td><span data-ttu-id="e0341-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-894">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-895">Product 2</span></span></td>
<td><span data-ttu-id="e0341-896">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-896">10001</span></span></td>
<td><span data-ttu-id="e0341-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-897">Electricity</span></span></td>
<td><span data-ttu-id="e0341-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-898">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="e0341-899">1,495.71</span></span></td>
<td><span data-ttu-id="e0341-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-901">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-901">CC003</span></span></td>
<td><span data-ttu-id="e0341-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-902">Assembly</span></span></td>
<td><span data-ttu-id="e0341-903">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-903">10001</span></span></td>
<td><span data-ttu-id="e0341-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-904">Electricity</span></span></td>
<td><span data-ttu-id="e0341-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-905">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="e0341-906">-286.25</span></span></td>
<td><span data-ttu-id="e0341-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-908">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-909">Product 1</span></span></td>
<td><span data-ttu-id="e0341-910">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-910">10001</span></span></td>
<td><span data-ttu-id="e0341-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-911">Electricity</span></span></td>
<td><span data-ttu-id="e0341-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-912">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-913">241.05</span><span class="sxs-lookup"><span data-stu-id="e0341-913">241.05</span></span></td>
<td><span data-ttu-id="e0341-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-915">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-916">Product 2</span></span></td>
<td><span data-ttu-id="e0341-917">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-917">10001</span></span></td>
<td><span data-ttu-id="e0341-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-918">Electricity</span></span></td>
<td><span data-ttu-id="e0341-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-919">Fixed cost</span></span></td>
<td><span data-ttu-id="e0341-920">45.20</span><span class="sxs-lookup"><span data-stu-id="e0341-920">45.20</span></span></td>
<td><span data-ttu-id="e0341-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-922">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-922">CC003</span></span></td>
<td><span data-ttu-id="e0341-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="e0341-923">Assembly</span></span></td>
<td><span data-ttu-id="e0341-924">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-924">10001</span></span></td>
<td><span data-ttu-id="e0341-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-925">Electricity</span></span></td>
<td><span data-ttu-id="e0341-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-926">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="e0341-927">-2,977.17</span></span></td>
<td><span data-ttu-id="e0341-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-929">Prod 1</span></span></td>
<td><span data-ttu-id="e0341-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="e0341-930">Product 1</span></span></td>
<td><span data-ttu-id="e0341-931">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-931">10001</span></span></td>
<td><span data-ttu-id="e0341-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-932">Electricity</span></span></td>
<td><span data-ttu-id="e0341-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-933">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="e0341-934">2,507.09</span></span></td>
<td><span data-ttu-id="e0341-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e0341-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-936">Prod 2</span></span></td>
<td><span data-ttu-id="e0341-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="e0341-937">Product 2</span></span></td>
<td><span data-ttu-id="e0341-938">10001</span><span class="sxs-lookup"><span data-stu-id="e0341-938">10001</span></span></td>
<td><span data-ttu-id="e0341-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="e0341-939">Electricity</span></span></td>
<td><span data-ttu-id="e0341-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-940">Variable cost</span></span></td>
<td><span data-ttu-id="e0341-941">470.08</span><span class="sxs-lookup"><span data-stu-id="e0341-941">470.08</span></span></td>
<td><span data-ttu-id="e0341-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="e0341-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="e0341-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="e0341-943">Conclusion</span></span>
<span data-ttu-id="e0341-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="e0341-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="e0341-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="e0341-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="e0341-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="e0341-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="e0341-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="e0341-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="e0341-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="e0341-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="e0341-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="e0341-950">Razem</span><span class="sxs-lookup"><span data-stu-id="e0341-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="e0341-951">CC099</span><span class="sxs-lookup"><span data-stu-id="e0341-951">CC099</span></span></th>
<th><span data-ttu-id="e0341-952">CC001</span><span class="sxs-lookup"><span data-stu-id="e0341-952">CC001</span></span></th>
<th><span data-ttu-id="e0341-953">CC002</span><span class="sxs-lookup"><span data-stu-id="e0341-953">CC002</span></span></th>
<th><span data-ttu-id="e0341-954">CC003</span><span class="sxs-lookup"><span data-stu-id="e0341-954">CC003</span></span></th>
<th><span data-ttu-id="e0341-955">CC004</span><span class="sxs-lookup"><span data-stu-id="e0341-955">CC004</span></span></th>
<th><span data-ttu-id="e0341-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e0341-956">Proj 1</span></span></th>
<th><span data-ttu-id="e0341-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e0341-957">Proj 2</span></span></th>
<th><span data-ttu-id="e0341-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e0341-958">Prod 1</span></span></th>
<th><span data-ttu-id="e0341-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e0341-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="e0341-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="e0341-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="e0341-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="e0341-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="e0341-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-971">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="e0341-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="e0341-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-973">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-974">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-975">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-976">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-977">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="e0341-978">776.36</span><span class="sxs-lookup"><span data-stu-id="e0341-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-979">223.64</span><span class="sxs-lookup"><span data-stu-id="e0341-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="e0341-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="e0341-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-982">000</span><span class="sxs-lookup"><span data-stu-id="e0341-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-983">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-984">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-985">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-986">0,00</span><span class="sxs-lookup"><span data-stu-id="e0341-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-987">30.00</span><span class="sxs-lookup"><span data-stu-id="e0341-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-988">10,00</span><span class="sxs-lookup"><span data-stu-id="e0341-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="e0341-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="e0341-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e0341-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="e0341-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="e0341-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="e0341-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="e0341-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="e0341-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="e0341-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="e0341-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="e0341-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="e0341-996">Aby uzyskać więcej informacji, zobacz [Akumulacja kosztów](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="e0341-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



