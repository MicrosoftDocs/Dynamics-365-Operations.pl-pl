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
ms.openlocfilehash: cef4a80aa12927fdbffea4bb6bcb108ad81494a6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841496"
---
# <a name="overhead-calculation"></a><span data-ttu-id="5eb31-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="5eb31-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5eb31-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="5eb31-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="5eb31-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="5eb31-105">Term definition</span></span>
---------------

<span data-ttu-id="5eb31-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="5eb31-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="5eb31-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="5eb31-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="5eb31-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="5eb31-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="5eb31-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="5eb31-109">Rent</span></span>
-   <span data-ttu-id="5eb31-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-110">Electricity</span></span>
-   <span data-ttu-id="5eb31-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="5eb31-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="5eb31-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="5eb31-112">Overhead calculation overview</span></span>
<span data-ttu-id="5eb31-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="5eb31-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="5eb31-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="5eb31-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="5eb31-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="5eb31-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="5eb31-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="5eb31-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="5eb31-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="5eb31-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="5eb31-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="5eb31-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="5eb31-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="5eb31-119">Version type</span></span>
-   <span data-ttu-id="5eb31-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="5eb31-120">Date and time</span></span>
-   <span data-ttu-id="5eb31-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="5eb31-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="5eb31-122">Fiscal year</span></span>
-   <span data-ttu-id="5eb31-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="5eb31-123">Fiscal period</span></span>

<span data-ttu-id="5eb31-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="5eb31-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="5eb31-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="5eb31-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="5eb31-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="5eb31-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="5eb31-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="5eb31-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="5eb31-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="5eb31-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="5eb31-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="5eb31-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="5eb31-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="5eb31-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="5eb31-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="5eb31-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="5eb31-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="5eb31-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="5eb31-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="5eb31-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="5eb31-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="5eb31-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="5eb31-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5eb31-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="5eb31-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="5eb31-140">Main account</span></span></th>
<th><span data-ttu-id="5eb31-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="5eb31-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="5eb31-143">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-143">CC099</span></span></td>
<td><span data-ttu-id="5eb31-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-144">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-145">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-145">10001</span></span></td>
<td><span data-ttu-id="5eb31-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-146">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="5eb31-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="5eb31-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="5eb31-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="5eb31-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="5eb31-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-151">Define the cost behavior rule</span></span>

<span data-ttu-id="5eb31-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="5eb31-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="5eb31-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="5eb31-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="5eb31-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="5eb31-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="5eb31-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="5eb31-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="5eb31-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="5eb31-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="5eb31-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="5eb31-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5eb31-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="5eb31-160">Journal</span></span></th>
<th><span data-ttu-id="5eb31-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="5eb31-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5eb31-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="5eb31-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5eb31-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="5eb31-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-164">00001</span><span class="sxs-lookup"><span data-stu-id="5eb31-164">00001</span></span></td>
<td><span data-ttu-id="5eb31-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="5eb31-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="5eb31-166">Fiscal</span></span></td>
<td><span data-ttu-id="5eb31-167">2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-167">2017</span></span></td>
<td><span data-ttu-id="5eb31-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-168">Period 1</span></span></td>
<td><span data-ttu-id="5eb31-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5eb31-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="5eb31-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5eb31-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="5eb31-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-173">Cost element</span></span></th>
<th><span data-ttu-id="5eb31-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-174">Cost behavior</span></span></th>
<th><span data-ttu-id="5eb31-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="5eb31-177">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-177">CC099</span></span></td>
<td><span data-ttu-id="5eb31-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-178">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-179">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-179">10001</span></span></td>
<td><span data-ttu-id="5eb31-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-180">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="5eb31-181">Unclassified</span></span></td>
<td><span data-ttu-id="5eb31-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5eb31-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-185">Cost element</span></span></th>
<th><span data-ttu-id="5eb31-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-186">Cost behavior</span></span></th>
<th><span data-ttu-id="5eb31-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-187">Amount</span></span></th>
<th><span data-ttu-id="5eb31-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="5eb31-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-189">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-189">CC099</span></span></td>
<td><span data-ttu-id="5eb31-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-190">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-191">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-191">10001</span></span></td>
<td><span data-ttu-id="5eb31-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-192">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="5eb31-193">Unclassified</span></span></td>
<td><span data-ttu-id="5eb31-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-194">10,000.00</span></span></td>
<td><span data-ttu-id="5eb31-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-196">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-196">CC099</span></span></td>
<td><span data-ttu-id="5eb31-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-197">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-198">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-198">10001</span></span></td>
<td><span data-ttu-id="5eb31-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-199">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="5eb31-200">Unclassified</span></span></td>
<td><span data-ttu-id="5eb31-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-201">-10,000.00</span></span></td>
<td><span data-ttu-id="5eb31-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-203">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-203">CC099</span></span></td>
<td><span data-ttu-id="5eb31-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-204">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-205">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-205">10001</span></span></td>
<td><span data-ttu-id="5eb31-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-206">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-207">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-208">1,000.00</span></span></td>
<td><span data-ttu-id="5eb31-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-210">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-210">CC099</span></span></td>
<td><span data-ttu-id="5eb31-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-211">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-212">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-212">10001</span></span></td>
<td><span data-ttu-id="5eb31-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-213">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-214">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-215">9,000.00</span></span></td>
<td><span data-ttu-id="5eb31-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="5eb31-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="5eb31-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="5eb31-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="5eb31-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="5eb31-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="5eb31-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-221">Define the cost distribution rule</span></span>

<span data-ttu-id="5eb31-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="5eb31-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="5eb31-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="5eb31-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="5eb31-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="5eb31-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="5eb31-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="5eb31-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="5eb31-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="5eb31-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="5eb31-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-228">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-229">kWh</span><span class="sxs-lookup"><span data-stu-id="5eb31-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-230">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-230">CC001</span></span></td>
<td><span data-ttu-id="5eb31-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-231">HR</span></span></td>
<td><span data-ttu-id="5eb31-232">1 000</span><span class="sxs-lookup"><span data-stu-id="5eb31-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-233">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-233">CC002</span></span></td>
<td><span data-ttu-id="5eb31-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-234">Finance</span></span></td>
<td><span data-ttu-id="5eb31-235">6,000</span><span class="sxs-lookup"><span data-stu-id="5eb31-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-236">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-236">CC003</span></span></td>
<td><span data-ttu-id="5eb31-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-237">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-238">0</span><span class="sxs-lookup"><span data-stu-id="5eb31-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="5eb31-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-240">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="5eb31-241">Magnitude</span></span></th>
<th><span data-ttu-id="5eb31-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="5eb31-242">Allocation factor</span></span></th>
<th><span data-ttu-id="5eb31-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-244">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-244">CC001</span></span></td>
<td><span data-ttu-id="5eb31-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-245">HR</span></span></td>
<td><span data-ttu-id="5eb31-246">1 000</span><span class="sxs-lookup"><span data-stu-id="5eb31-246">1,000</span></span></td>
<td><span data-ttu-id="5eb31-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5eb31-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5eb31-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-249">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-249">CC002</span></span></td>
<td><span data-ttu-id="5eb31-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-250">Finance</span></span></td>
<td><span data-ttu-id="5eb31-251">6,000</span><span class="sxs-lookup"><span data-stu-id="5eb31-251">6,000</span></span></td>
<td><span data-ttu-id="5eb31-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5eb31-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5eb31-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-254">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-254">CC003</span></span></td>
<td><span data-ttu-id="5eb31-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-255">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-256">0</span><span class="sxs-lookup"><span data-stu-id="5eb31-256">0</span></span></td>
<td><span data-ttu-id="5eb31-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5eb31-258">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="5eb31-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="5eb31-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="5eb31-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-261">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="5eb31-262">Formula</span></span></th>
<th><span data-ttu-id="5eb31-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="5eb31-263">Magnitude</span></span></th>
<th><span data-ttu-id="5eb31-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="5eb31-264">Allocation factor</span></span></th>
<th><span data-ttu-id="5eb31-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-266">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-266">CC001</span></span></td>
<td><span data-ttu-id="5eb31-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-267">HR</span></span></td>
<td><span data-ttu-id="5eb31-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5eb31-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5eb31-269">1</span><span class="sxs-lookup"><span data-stu-id="5eb31-269">1</span></span></td>
<td><span data-ttu-id="5eb31-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5eb31-271">500.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-272">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-272">CC002</span></span></td>
<td><span data-ttu-id="5eb31-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-273">Finance</span></span></td>
<td><span data-ttu-id="5eb31-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5eb31-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5eb31-275">1</span><span class="sxs-lookup"><span data-stu-id="5eb31-275">1</span></span></td>
<td><span data-ttu-id="5eb31-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5eb31-277">500.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-278">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-278">CC003</span></span></td>
<td><span data-ttu-id="5eb31-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-279">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5eb31-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5eb31-281">0</span><span class="sxs-lookup"><span data-stu-id="5eb31-281">0</span></span></td>
<td><span data-ttu-id="5eb31-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5eb31-283">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5eb31-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="5eb31-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5eb31-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="5eb31-285">Journal</span></span></th>
<th><span data-ttu-id="5eb31-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="5eb31-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5eb31-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="5eb31-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5eb31-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="5eb31-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-289">00002</span><span class="sxs-lookup"><span data-stu-id="5eb31-289">00002</span></span></td>
<td><span data-ttu-id="5eb31-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="5eb31-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="5eb31-291">Fiscal</span></span></td>
<td><span data-ttu-id="5eb31-292">2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-292">2017</span></span></td>
<td><span data-ttu-id="5eb31-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-293">Period 1</span></span></td>
<td><span data-ttu-id="5eb31-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5eb31-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="5eb31-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5eb31-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="5eb31-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-298">Cost element</span></span></th>
<th><span data-ttu-id="5eb31-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-299">Cost behavior</span></span></th>
<th><span data-ttu-id="5eb31-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-302">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-302">CC099</span></span></td>
<td><span data-ttu-id="5eb31-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-303">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-304">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-304">10001</span></span></td>
<td><span data-ttu-id="5eb31-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-305">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-306">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-309">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-309">CC099</span></span></td>
<td><span data-ttu-id="5eb31-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-310">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-311">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-311">10001</span></span></td>
<td><span data-ttu-id="5eb31-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-312">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-313">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5eb31-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-317">Cost element</span></span></th>
<th><span data-ttu-id="5eb31-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-318">Cost behavior</span></span></th>
<th><span data-ttu-id="5eb31-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-319">Amount</span></span></th>
<th><span data-ttu-id="5eb31-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="5eb31-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-321">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-321">CC099</span></span></td>
<td><span data-ttu-id="5eb31-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-322">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-323">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-323">10001</span></span></td>
<td><span data-ttu-id="5eb31-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-324">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-325">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-326">-1,000.00</span></span></td>
<td><span data-ttu-id="5eb31-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-328">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-328">CC001</span></span></td>
<td><span data-ttu-id="5eb31-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-329">HR</span></span></td>
<td><span data-ttu-id="5eb31-330">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-330">10001</span></span></td>
<td><span data-ttu-id="5eb31-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-331">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-332">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-333">500.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-333">500.00</span></span></td>
<td><span data-ttu-id="5eb31-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-335">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-335">CC002</span></span></td>
<td><span data-ttu-id="5eb31-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-336">Finance</span></span></td>
<td><span data-ttu-id="5eb31-337">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-337">10001</span></span></td>
<td><span data-ttu-id="5eb31-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-338">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-339">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-340">500.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-340">500.00</span></span></td>
<td><span data-ttu-id="5eb31-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-342">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-342">CC099</span></span></td>
<td><span data-ttu-id="5eb31-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-343">Default cost center</span></span></td>
<td><span data-ttu-id="5eb31-344">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-344">10001</span></span></td>
<td><span data-ttu-id="5eb31-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-345">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-346">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-347">-9,000.00</span></span></td>
<td><span data-ttu-id="5eb31-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-349">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-349">CC001</span></span></td>
<td><span data-ttu-id="5eb31-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-350">HR</span></span></td>
<td><span data-ttu-id="5eb31-351">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-351">10001</span></span></td>
<td><span data-ttu-id="5eb31-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-352">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-353">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5eb31-354">1,285.71</span></span></td>
<td><span data-ttu-id="5eb31-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-356">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-356">CC002</span></span></td>
<td><span data-ttu-id="5eb31-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-357">Finance</span></span></td>
<td><span data-ttu-id="5eb31-358">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-358">10001</span></span></td>
<td><span data-ttu-id="5eb31-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-359">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-360">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5eb31-361">7,714.29</span></span></td>
<td><span data-ttu-id="5eb31-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="5eb31-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="5eb31-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="5eb31-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="5eb31-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="5eb31-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="5eb31-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="5eb31-367">Define the overhead rate</span></span>

<span data-ttu-id="5eb31-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="5eb31-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="5eb31-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="5eb31-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-370">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="5eb31-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-372">Proj 1</span></span></td>
<td><span data-ttu-id="5eb31-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-373">Project 1</span></span></td>
<td><span data-ttu-id="5eb31-374">3</span><span class="sxs-lookup"><span data-stu-id="5eb31-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-375">Proj 2</span></span></td>
<td><span data-ttu-id="5eb31-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-376">Project 2</span></span></td>
<td><span data-ttu-id="5eb31-377">1</span><span class="sxs-lookup"><span data-stu-id="5eb31-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="5eb31-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-379">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-380">Cost element</span></span></th>
<th><span data-ttu-id="5eb31-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-381">Cost behavior</span></span></th>
<th><span data-ttu-id="5eb31-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="5eb31-382">Units</span></span></th>
<th><span data-ttu-id="5eb31-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="5eb31-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-384">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-384">CC001</span></span></td>
<td><span data-ttu-id="5eb31-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-385">HR</span></span></td>
<td><span data-ttu-id="5eb31-386">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-386">10001</span></span></td>
<td><span data-ttu-id="5eb31-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-387">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-388">1</span><span class="sxs-lookup"><span data-stu-id="5eb31-388">1</span></span></td>
<td><span data-ttu-id="5eb31-389">10</span><span class="sxs-lookup"><span data-stu-id="5eb31-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-391">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="5eb31-392">Magnitude</span></span></th>
<th><span data-ttu-id="5eb31-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-393">Cost element</span></span></th>
<th><span data-ttu-id="5eb31-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="5eb31-394">Allocation factor</span></span></th>
<th><span data-ttu-id="5eb31-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-396">Proj 1</span></span></td>
<td><span data-ttu-id="5eb31-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-397">Project 1</span></span></td>
<td><span data-ttu-id="5eb31-398">3</span><span class="sxs-lookup"><span data-stu-id="5eb31-398">3</span></span></td>
<td><span data-ttu-id="5eb31-399">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-399">10001</span></span></td>
<td><span data-ttu-id="5eb31-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5eb31-401">30.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-402">Proj 2</span></span></td>
<td><span data-ttu-id="5eb31-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-403">Project 2</span></span></td>
<td><span data-ttu-id="5eb31-404">1</span><span class="sxs-lookup"><span data-stu-id="5eb31-404">1</span></span></td>
<td><span data-ttu-id="5eb31-405">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-405">10001</span></span></td>
<td><span data-ttu-id="5eb31-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5eb31-407">10,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5eb31-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="5eb31-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5eb31-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="5eb31-409">Journal</span></span></th>
<th><span data-ttu-id="5eb31-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="5eb31-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5eb31-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="5eb31-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5eb31-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="5eb31-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-413">00003</span><span class="sxs-lookup"><span data-stu-id="5eb31-413">00003</span></span></td>
<td><span data-ttu-id="5eb31-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="5eb31-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="5eb31-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="5eb31-415">Fiscal</span></span></td>
<td><span data-ttu-id="5eb31-416">2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-416">2017</span></span></td>
<td><span data-ttu-id="5eb31-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-417">Period 1</span></span></td>
<td><span data-ttu-id="5eb31-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="5eb31-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="5eb31-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5eb31-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="5eb31-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-421">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="5eb31-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-424">Proj 1</span></span></td>
<td><span data-ttu-id="5eb31-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5eb31-426">3,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-428">Proj 2</span></span></td>
<td><span data-ttu-id="5eb31-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5eb31-430">1.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5eb31-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-433">Cost element</span></span></th>
<th><span data-ttu-id="5eb31-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-434">Cost behavior</span></span></th>
<th><span data-ttu-id="5eb31-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-435">Amount</span></span></th>
<th><span data-ttu-id="5eb31-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="5eb31-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="5eb31-437">CC0001</span></span></td>
<td><span data-ttu-id="5eb31-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-438">HR</span></span></td>
<td><span data-ttu-id="5eb31-439">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-439">10001</span></span></td>
<td><span data-ttu-id="5eb31-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-440">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-441">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-442">-30.00</span></span></td>
<td><span data-ttu-id="5eb31-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-444">Proj 1</span></span></td>
<td><span data-ttu-id="5eb31-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5eb31-446">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-446">10001</span></span></td>
<td><span data-ttu-id="5eb31-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-447">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-448">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-449">30.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-449">30.00</span></span></td>
<td><span data-ttu-id="5eb31-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-451">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-451">CC001</span></span></td>
<td><span data-ttu-id="5eb31-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-452">HR</span></span></td>
<td><span data-ttu-id="5eb31-453">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-453">10001</span></span></td>
<td><span data-ttu-id="5eb31-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-454">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-455">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-456">-10.00</span></span></td>
<td><span data-ttu-id="5eb31-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-458">Proj 2</span></span></td>
<td><span data-ttu-id="5eb31-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5eb31-460">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-460">10001</span></span></td>
<td><span data-ttu-id="5eb31-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-461">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-462">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-463">10,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-463">10.00</span></span></td>
<td><span data-ttu-id="5eb31-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="5eb31-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="5eb31-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="5eb31-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="5eb31-468">Program Finance and Operations obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="5eb31-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="5eb31-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="5eb31-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="5eb31-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="5eb31-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="5eb31-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="5eb31-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="5eb31-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="5eb31-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="5eb31-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-475">Define the cost allocation</span></span>

<span data-ttu-id="5eb31-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="5eb31-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="5eb31-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="5eb31-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-479">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="5eb31-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-481">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-481">CC002</span></span></td>
<td><span data-ttu-id="5eb31-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-482">Finance</span></span></td>
<td><span data-ttu-id="5eb31-483">35</span><span class="sxs-lookup"><span data-stu-id="5eb31-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-484">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-484">CC003</span></span></td>
<td><span data-ttu-id="5eb31-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-485">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-486">55</span><span class="sxs-lookup"><span data-stu-id="5eb31-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-487">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-487">CC004</span></span></td>
<td><span data-ttu-id="5eb31-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-488">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-489">10</span><span class="sxs-lookup"><span data-stu-id="5eb31-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="5eb31-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="5eb31-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-492">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="5eb31-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-494">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-494">CC003</span></span></td>
<td><span data-ttu-id="5eb31-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-495">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-496">65</span><span class="sxs-lookup"><span data-stu-id="5eb31-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-497">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-497">CC004</span></span></td>
<td><span data-ttu-id="5eb31-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-498">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-499">35</span><span class="sxs-lookup"><span data-stu-id="5eb31-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="5eb31-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="5eb31-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-502">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="5eb31-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-504">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-505">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-506">60</span><span class="sxs-lookup"><span data-stu-id="5eb31-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-507">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-508">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-509">20</span><span class="sxs-lookup"><span data-stu-id="5eb31-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="5eb31-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="5eb31-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-512">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="5eb31-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-514">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-515">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-516">80</span><span class="sxs-lookup"><span data-stu-id="5eb31-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-517">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-518">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-519">15</span><span class="sxs-lookup"><span data-stu-id="5eb31-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5eb31-520">W programie Finance and Operations miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="5eb31-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="5eb31-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="5eb31-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="5eb31-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="5eb31-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-523">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="5eb31-524">Magnitude</span></span></th>
<th><span data-ttu-id="5eb31-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="5eb31-525">Allocation factor</span></span></th>
<th><span data-ttu-id="5eb31-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-526">Amount</span></span></th>
<th><span data-ttu-id="5eb31-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-528">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-528">CC002</span></span></td>
<td><span data-ttu-id="5eb31-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-529">Finance</span></span></td>
<td><span data-ttu-id="5eb31-530">35</span><span class="sxs-lookup"><span data-stu-id="5eb31-530">35</span></span></td>
<td><span data-ttu-id="5eb31-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5eb31-532">175.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-532">175.00</span></span></td>
<td><span data-ttu-id="5eb31-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-534">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-534">CC003</span></span></td>
<td><span data-ttu-id="5eb31-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-535">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-536">55</span><span class="sxs-lookup"><span data-stu-id="5eb31-536">55</span></span></td>
<td><span data-ttu-id="5eb31-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5eb31-538">275.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-538">275.00</span></span></td>
<td><span data-ttu-id="5eb31-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-540">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-540">CC004</span></span></td>
<td><span data-ttu-id="5eb31-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-541">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-542">10</span><span class="sxs-lookup"><span data-stu-id="5eb31-542">10</span></span></td>
<td><span data-ttu-id="5eb31-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5eb31-544">50,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-544">50.00</span></span></td>
<td><span data-ttu-id="5eb31-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-546">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-546">CC002</span></span></td>
<td><span data-ttu-id="5eb31-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-547">Finance</span></span></td>
<td><span data-ttu-id="5eb31-548">35</span><span class="sxs-lookup"><span data-stu-id="5eb31-548">35</span></span></td>
<td><span data-ttu-id="5eb31-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="5eb31-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5eb31-550">436.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-550">436.00</span></span></td>
<td><span data-ttu-id="5eb31-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-552">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-552">CC003</span></span></td>
<td><span data-ttu-id="5eb31-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-553">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-554">55</span><span class="sxs-lookup"><span data-stu-id="5eb31-554">55</span></span></td>
<td><span data-ttu-id="5eb31-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="5eb31-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5eb31-556">685.14</span><span class="sxs-lookup"><span data-stu-id="5eb31-556">685.14</span></span></td>
<td><span data-ttu-id="5eb31-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-558">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-558">CC004</span></span></td>
<td><span data-ttu-id="5eb31-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-559">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-560">10</span><span class="sxs-lookup"><span data-stu-id="5eb31-560">10</span></span></td>
<td><span data-ttu-id="5eb31-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="5eb31-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5eb31-562">124.57</span><span class="sxs-lookup"><span data-stu-id="5eb31-562">124.57</span></span></td>
<td><span data-ttu-id="5eb31-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="5eb31-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-565">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="5eb31-566">Magnitude</span></span></th>
<th><span data-ttu-id="5eb31-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="5eb31-567">Allocation factor</span></span></th>
<th><span data-ttu-id="5eb31-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-568">Amount</span></span></th>
<th><span data-ttu-id="5eb31-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-570">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-570">CC003</span></span></td>
<td><span data-ttu-id="5eb31-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-571">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-572">65</span><span class="sxs-lookup"><span data-stu-id="5eb31-572">65</span></span></td>
<td><span data-ttu-id="5eb31-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="5eb31-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5eb31-574">438.75</span><span class="sxs-lookup"><span data-stu-id="5eb31-574">438.75</span></span></td>
<td><span data-ttu-id="5eb31-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-576">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-576">CC004</span></span></td>
<td><span data-ttu-id="5eb31-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-577">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-578">35</span><span class="sxs-lookup"><span data-stu-id="5eb31-578">35</span></span></td>
<td><span data-ttu-id="5eb31-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="5eb31-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5eb31-580">236.25</span><span class="sxs-lookup"><span data-stu-id="5eb31-580">236.25</span></span></td>
<td><span data-ttu-id="5eb31-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-582">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-582">CC003</span></span></td>
<td><span data-ttu-id="5eb31-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-583">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-584">65</span><span class="sxs-lookup"><span data-stu-id="5eb31-584">65</span></span></td>
<td><span data-ttu-id="5eb31-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="5eb31-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5eb31-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5eb31-586">5,297.69</span></span></td>
<td><span data-ttu-id="5eb31-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-588">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-588">CC004</span></span></td>
<td><span data-ttu-id="5eb31-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-589">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-590">35</span><span class="sxs-lookup"><span data-stu-id="5eb31-590">35</span></span></td>
<td><span data-ttu-id="5eb31-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="5eb31-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5eb31-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5eb31-592">2,852.60</span></span></td>
<td><span data-ttu-id="5eb31-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="5eb31-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-595">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="5eb31-596">Magnitude</span></span></th>
<th><span data-ttu-id="5eb31-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="5eb31-597">Allocation factor</span></span></th>
<th><span data-ttu-id="5eb31-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-598">Amount</span></span></th>
<th><span data-ttu-id="5eb31-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-600">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-601">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-602">60</span><span class="sxs-lookup"><span data-stu-id="5eb31-602">60</span></span></td>
<td><span data-ttu-id="5eb31-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="5eb31-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5eb31-604">535.31</span><span class="sxs-lookup"><span data-stu-id="5eb31-604">535.31</span></span></td>
<td><span data-ttu-id="5eb31-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-606">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-607">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-608">20</span><span class="sxs-lookup"><span data-stu-id="5eb31-608">20</span></span></td>
<td><span data-ttu-id="5eb31-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="5eb31-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5eb31-610">178.44</span><span class="sxs-lookup"><span data-stu-id="5eb31-610">178.44</span></span></td>
<td><span data-ttu-id="5eb31-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-612">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-613">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-614">60</span><span class="sxs-lookup"><span data-stu-id="5eb31-614">60</span></span></td>
<td><span data-ttu-id="5eb31-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="5eb31-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5eb31-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5eb31-616">4,487.12</span></span></td>
<td><span data-ttu-id="5eb31-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-618">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-619">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-620">20</span><span class="sxs-lookup"><span data-stu-id="5eb31-620">20</span></span></td>
<td><span data-ttu-id="5eb31-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="5eb31-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5eb31-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5eb31-622">1,495.71</span></span></td>
<td><span data-ttu-id="5eb31-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5eb31-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="5eb31-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-625">Cost object</span></span></th>
<th><span data-ttu-id="5eb31-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="5eb31-626">Magnitude</span></span></th>
<th><span data-ttu-id="5eb31-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="5eb31-627">Allocation factor</span></span></th>
<th><span data-ttu-id="5eb31-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-628">Amount</span></span></th>
<th><span data-ttu-id="5eb31-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-630">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-631">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-632">80</span><span class="sxs-lookup"><span data-stu-id="5eb31-632">80</span></span></td>
<td><span data-ttu-id="5eb31-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="5eb31-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5eb31-634">241.05</span><span class="sxs-lookup"><span data-stu-id="5eb31-634">241.05</span></span></td>
<td><span data-ttu-id="5eb31-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-636">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-637">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-638">15</span><span class="sxs-lookup"><span data-stu-id="5eb31-638">15</span></span></td>
<td><span data-ttu-id="5eb31-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="5eb31-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5eb31-640">45.20</span><span class="sxs-lookup"><span data-stu-id="5eb31-640">45.20</span></span></td>
<td><span data-ttu-id="5eb31-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-642">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-643">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-644">80</span><span class="sxs-lookup"><span data-stu-id="5eb31-644">80</span></span></td>
<td><span data-ttu-id="5eb31-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="5eb31-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5eb31-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5eb31-646">2,507.09</span></span></td>
<td><span data-ttu-id="5eb31-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-648">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-649">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-650">15</span><span class="sxs-lookup"><span data-stu-id="5eb31-650">15</span></span></td>
<td><span data-ttu-id="5eb31-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="5eb31-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5eb31-652">470.08</span><span class="sxs-lookup"><span data-stu-id="5eb31-652">470.08</span></span></td>
<td><span data-ttu-id="5eb31-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5eb31-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="5eb31-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5eb31-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="5eb31-655">Journal</span></span></th>
<th><span data-ttu-id="5eb31-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="5eb31-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5eb31-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="5eb31-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5eb31-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="5eb31-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-659">00004</span><span class="sxs-lookup"><span data-stu-id="5eb31-659">00004</span></span></td>
<td><span data-ttu-id="5eb31-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="5eb31-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="5eb31-661">Fiscal</span></span></td>
<td><span data-ttu-id="5eb31-662">2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-662">2017</span></span></td>
<td><span data-ttu-id="5eb31-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-663">Period 1</span></span></td>
<td><span data-ttu-id="5eb31-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="5eb31-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="5eb31-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5eb31-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="5eb31-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-668">Cost element</span></span></th>
<th><span data-ttu-id="5eb31-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-669">Cost behavior</span></span></th>
<th><span data-ttu-id="5eb31-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-672">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-672">CC001</span></span></td>
<td><span data-ttu-id="5eb31-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-673">HR</span></span></td>
<td><span data-ttu-id="5eb31-674">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-674">10001</span></span></td>
<td><span data-ttu-id="5eb31-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-675">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-676">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-677">500.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-679">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-679">CC001</span></span></td>
<td><span data-ttu-id="5eb31-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-680">HR</span></span></td>
<td><span data-ttu-id="5eb31-681">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-681">10001</span></span></td>
<td><span data-ttu-id="5eb31-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-682">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-683">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="5eb31-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-686">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-686">CC002</span></span></td>
<td><span data-ttu-id="5eb31-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-687">Finance</span></span></td>
<td><span data-ttu-id="5eb31-688">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-688">10001</span></span></td>
<td><span data-ttu-id="5eb31-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-689">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-690">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-691">675.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-693">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-693">CC002</span></span></td>
<td><span data-ttu-id="5eb31-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-694">Finance</span></span></td>
<td><span data-ttu-id="5eb31-695">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-695">10001</span></span></td>
<td><span data-ttu-id="5eb31-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-696">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-697">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="5eb31-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-700">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-700">CC003</span></span></td>
<td><span data-ttu-id="5eb31-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-701">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-702">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-702">10001</span></span></td>
<td><span data-ttu-id="5eb31-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-703">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-704">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-705">713.75</span><span class="sxs-lookup"><span data-stu-id="5eb31-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-707">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-707">CC003</span></span></td>
<td><span data-ttu-id="5eb31-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-708">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-709">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-709">10001</span></span></td>
<td><span data-ttu-id="5eb31-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-710">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-711">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="5eb31-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-714">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-714">CC003</span></span></td>
<td><span data-ttu-id="5eb31-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-715">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-716">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-716">10001</span></span></td>
<td><span data-ttu-id="5eb31-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-717">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-718">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-719">286.25</span><span class="sxs-lookup"><span data-stu-id="5eb31-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-721">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-721">CC003</span></span></td>
<td><span data-ttu-id="5eb31-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-722">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-723">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-723">10001</span></span></td>
<td><span data-ttu-id="5eb31-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-724">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-725">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="5eb31-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-728">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-729">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-730">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-730">10001</span></span></td>
<td><span data-ttu-id="5eb31-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-731">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-732">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-733">776.36</span><span class="sxs-lookup"><span data-stu-id="5eb31-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-735">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-736">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-737">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-737">10001</span></span></td>
<td><span data-ttu-id="5eb31-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-738">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-739">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5eb31-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-742">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-743">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-744">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-744">10001</span></span></td>
<td><span data-ttu-id="5eb31-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-745">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-746">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-747">223.64</span><span class="sxs-lookup"><span data-stu-id="5eb31-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="5eb31-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-749">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-750">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-751">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-751">10001</span></span></td>
<td><span data-ttu-id="5eb31-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-752">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-753">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5eb31-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5eb31-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5eb31-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5eb31-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-757">Cost element</span></span></th>
<th><span data-ttu-id="5eb31-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-758">Cost behavior</span></span></th>
<th><span data-ttu-id="5eb31-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="5eb31-759">Amount</span></span></th>
<th><span data-ttu-id="5eb31-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="5eb31-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5eb31-761">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-761">CC001</span></span></td>
<td><span data-ttu-id="5eb31-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-762">HR</span></span></td>
<td><span data-ttu-id="5eb31-763">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-763">10001</span></span></td>
<td><span data-ttu-id="5eb31-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-764">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-765">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-766">-500.00</span></span></td>
<td><span data-ttu-id="5eb31-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-768">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-768">CC002</span></span></td>
<td><span data-ttu-id="5eb31-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-769">Finance</span></span></td>
<td><span data-ttu-id="5eb31-770">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-770">10001</span></span></td>
<td><span data-ttu-id="5eb31-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-771">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-772">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-773">175.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-773">175.00</span></span></td>
<td><span data-ttu-id="5eb31-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-775">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-775">CC003</span></span></td>
<td><span data-ttu-id="5eb31-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-776">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-777">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-777">10001</span></span></td>
<td><span data-ttu-id="5eb31-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-778">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-779">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-780">275.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-780">275.00</span></span></td>
<td><span data-ttu-id="5eb31-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-782">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-782">CC004</span></span></td>
<td><span data-ttu-id="5eb31-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-783">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-784">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-784">10001</span></span></td>
<td><span data-ttu-id="5eb31-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-785">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-786">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-787">50,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-787">50,00</span></span></td>
<td><span data-ttu-id="5eb31-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-789">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-789">CC001</span></span></td>
<td><span data-ttu-id="5eb31-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5eb31-790">HR</span></span></td>
<td><span data-ttu-id="5eb31-791">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-791">10001</span></span></td>
<td><span data-ttu-id="5eb31-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-792">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-793">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="5eb31-794">-1,245.71</span></span></td>
<td><span data-ttu-id="5eb31-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-796">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-796">CC002</span></span></td>
<td><span data-ttu-id="5eb31-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-797">Finance</span></span></td>
<td><span data-ttu-id="5eb31-798">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-798">10001</span></span></td>
<td><span data-ttu-id="5eb31-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-799">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-800">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-801">436.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-801">436.00</span></span></td>
<td><span data-ttu-id="5eb31-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-803">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-803">CC003</span></span></td>
<td><span data-ttu-id="5eb31-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-804">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-805">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-805">10001</span></span></td>
<td><span data-ttu-id="5eb31-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-806">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-807">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-808">685.14</span><span class="sxs-lookup"><span data-stu-id="5eb31-808">685.14</span></span></td>
<td><span data-ttu-id="5eb31-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-810">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-810">CC004</span></span></td>
<td><span data-ttu-id="5eb31-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-811">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-812">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-812">10001</span></span></td>
<td><span data-ttu-id="5eb31-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-813">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-814">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-815">124.57</span><span class="sxs-lookup"><span data-stu-id="5eb31-815">124.57</span></span></td>
<td><span data-ttu-id="5eb31-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-817">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-817">CC002</span></span></td>
<td><span data-ttu-id="5eb31-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-818">Finance</span></span></td>
<td><span data-ttu-id="5eb31-819">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-819">10001</span></span></td>
<td><span data-ttu-id="5eb31-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-820">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-821">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-822">-675.00</span></span></td>
<td><span data-ttu-id="5eb31-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-824">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-824">CC003</span></span></td>
<td><span data-ttu-id="5eb31-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-825">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-826">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-826">10001</span></span></td>
<td><span data-ttu-id="5eb31-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-827">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-828">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-829">438.75</span><span class="sxs-lookup"><span data-stu-id="5eb31-829">438.75</span></span></td>
<td><span data-ttu-id="5eb31-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-831">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-831">CC004</span></span></td>
<td><span data-ttu-id="5eb31-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-832">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-833">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-833">10001</span></span></td>
<td><span data-ttu-id="5eb31-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-834">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-835">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-836">236.25</span><span class="sxs-lookup"><span data-stu-id="5eb31-836">236.25</span></span></td>
<td><span data-ttu-id="5eb31-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-838">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-838">CC002</span></span></td>
<td><span data-ttu-id="5eb31-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eb31-839">Finance</span></span></td>
<td><span data-ttu-id="5eb31-840">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-840">10001</span></span></td>
<td><span data-ttu-id="5eb31-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-841">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-842">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="5eb31-843">-8,150.29</span></span></td>
<td><span data-ttu-id="5eb31-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-845">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-845">CC003</span></span></td>
<td><span data-ttu-id="5eb31-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-846">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-847">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-847">10001</span></span></td>
<td><span data-ttu-id="5eb31-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-848">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-849">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5eb31-850">5,297.69</span></span></td>
<td><span data-ttu-id="5eb31-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-852">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-852">CC004</span></span></td>
<td><span data-ttu-id="5eb31-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="5eb31-853">Packaging</span></span></td>
<td><span data-ttu-id="5eb31-854">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-854">10001</span></span></td>
<td><span data-ttu-id="5eb31-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-855">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-856">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5eb31-857">2,852.60</span></span></td>
<td><span data-ttu-id="5eb31-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-859">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-859">CC003</span></span></td>
<td><span data-ttu-id="5eb31-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-860">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-861">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-861">10001</span></span></td>
<td><span data-ttu-id="5eb31-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-862">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-863">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="5eb31-864">-713.75</span></span></td>
<td><span data-ttu-id="5eb31-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-866">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-867">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-868">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-868">10001</span></span></td>
<td><span data-ttu-id="5eb31-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-869">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-870">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-871">535.31</span><span class="sxs-lookup"><span data-stu-id="5eb31-871">535.31</span></span></td>
<td><span data-ttu-id="5eb31-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-873">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-874">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-875">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-875">10001</span></span></td>
<td><span data-ttu-id="5eb31-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-876">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-877">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-878">178.44</span><span class="sxs-lookup"><span data-stu-id="5eb31-878">178.44</span></span></td>
<td><span data-ttu-id="5eb31-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-880">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-880">CC003</span></span></td>
<td><span data-ttu-id="5eb31-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-881">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-882">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-882">10001</span></span></td>
<td><span data-ttu-id="5eb31-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-883">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-884">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="5eb31-885">-5,982.83</span></span></td>
<td><span data-ttu-id="5eb31-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-887">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-888">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-889">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-889">10001</span></span></td>
<td><span data-ttu-id="5eb31-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-890">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-891">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5eb31-892">4,487.12</span></span></td>
<td><span data-ttu-id="5eb31-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-894">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-895">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-896">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-896">10001</span></span></td>
<td><span data-ttu-id="5eb31-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-897">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-898">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5eb31-899">1,495.71</span></span></td>
<td><span data-ttu-id="5eb31-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-901">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-901">CC003</span></span></td>
<td><span data-ttu-id="5eb31-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-902">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-903">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-903">10001</span></span></td>
<td><span data-ttu-id="5eb31-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-904">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-905">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="5eb31-906">-286.25</span></span></td>
<td><span data-ttu-id="5eb31-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-908">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-909">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-910">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-910">10001</span></span></td>
<td><span data-ttu-id="5eb31-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-911">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-912">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-913">241.05</span><span class="sxs-lookup"><span data-stu-id="5eb31-913">241.05</span></span></td>
<td><span data-ttu-id="5eb31-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-915">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-916">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-917">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-917">10001</span></span></td>
<td><span data-ttu-id="5eb31-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-918">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-919">Fixed cost</span></span></td>
<td><span data-ttu-id="5eb31-920">45.20</span><span class="sxs-lookup"><span data-stu-id="5eb31-920">45.20</span></span></td>
<td><span data-ttu-id="5eb31-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-922">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-922">CC003</span></span></td>
<td><span data-ttu-id="5eb31-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="5eb31-923">Assembly</span></span></td>
<td><span data-ttu-id="5eb31-924">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-924">10001</span></span></td>
<td><span data-ttu-id="5eb31-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-925">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-926">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="5eb31-927">-2,977.17</span></span></td>
<td><span data-ttu-id="5eb31-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-929">Prod 1</span></span></td>
<td><span data-ttu-id="5eb31-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-930">Product 1</span></span></td>
<td><span data-ttu-id="5eb31-931">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-931">10001</span></span></td>
<td><span data-ttu-id="5eb31-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-932">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-933">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5eb31-934">2,507.09</span></span></td>
<td><span data-ttu-id="5eb31-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5eb31-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-936">Prod 2</span></span></td>
<td><span data-ttu-id="5eb31-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-937">Product 2</span></span></td>
<td><span data-ttu-id="5eb31-938">10001</span><span class="sxs-lookup"><span data-stu-id="5eb31-938">10001</span></span></td>
<td><span data-ttu-id="5eb31-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="5eb31-939">Electricity</span></span></td>
<td><span data-ttu-id="5eb31-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-940">Variable cost</span></span></td>
<td><span data-ttu-id="5eb31-941">470.08</span><span class="sxs-lookup"><span data-stu-id="5eb31-941">470.08</span></span></td>
<td><span data-ttu-id="5eb31-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="5eb31-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="5eb31-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="5eb31-943">Conclusion</span></span>
<span data-ttu-id="5eb31-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="5eb31-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="5eb31-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="5eb31-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="5eb31-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="5eb31-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="5eb31-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="5eb31-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="5eb31-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="5eb31-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="5eb31-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="5eb31-950">Razem</span><span class="sxs-lookup"><span data-stu-id="5eb31-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="5eb31-951">CC099</span><span class="sxs-lookup"><span data-stu-id="5eb31-951">CC099</span></span></th>
<th><span data-ttu-id="5eb31-952">CC001</span><span class="sxs-lookup"><span data-stu-id="5eb31-952">CC001</span></span></th>
<th><span data-ttu-id="5eb31-953">CC002</span><span class="sxs-lookup"><span data-stu-id="5eb31-953">CC002</span></span></th>
<th><span data-ttu-id="5eb31-954">CC003</span><span class="sxs-lookup"><span data-stu-id="5eb31-954">CC003</span></span></th>
<th><span data-ttu-id="5eb31-955">CC004</span><span class="sxs-lookup"><span data-stu-id="5eb31-955">CC004</span></span></th>
<th><span data-ttu-id="5eb31-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-956">Proj 1</span></span></th>
<th><span data-ttu-id="5eb31-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-957">Proj 2</span></span></th>
<th><span data-ttu-id="5eb31-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5eb31-958">Prod 1</span></span></th>
<th><span data-ttu-id="5eb31-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5eb31-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="5eb31-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="5eb31-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="5eb31-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="5eb31-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-971">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="5eb31-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="5eb31-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-973">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-974">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-975">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-976">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-977">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-978">776.36</span><span class="sxs-lookup"><span data-stu-id="5eb31-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-979">223.64</span><span class="sxs-lookup"><span data-stu-id="5eb31-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="5eb31-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="5eb31-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-982">000</span><span class="sxs-lookup"><span data-stu-id="5eb31-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-983">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-984">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-985">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-986">0,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-987">30.00</span><span class="sxs-lookup"><span data-stu-id="5eb31-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-988">10,00</span><span class="sxs-lookup"><span data-stu-id="5eb31-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5eb31-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5eb31-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5eb31-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="5eb31-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5eb31-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="5eb31-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="5eb31-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="5eb31-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="5eb31-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="5eb31-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="5eb31-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="5eb31-996">Aby uzyskać więcej informacji, zobacz [Akumulacja kosztów](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="5eb31-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



