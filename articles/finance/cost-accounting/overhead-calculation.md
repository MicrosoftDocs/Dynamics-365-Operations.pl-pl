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
ms.openlocfilehash: 6c045f82f3288dba193721dd80c90e68750af9a7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179419"
---
# <a name="overhead-calculation"></a><span data-ttu-id="89982-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="89982-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89982-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="89982-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="89982-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="89982-105">Term definition</span></span>
---------------

<span data-ttu-id="89982-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="89982-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="89982-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="89982-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="89982-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="89982-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="89982-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="89982-109">Rent</span></span>
-   <span data-ttu-id="89982-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-110">Electricity</span></span>
-   <span data-ttu-id="89982-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="89982-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="89982-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="89982-112">Overhead calculation overview</span></span>
<span data-ttu-id="89982-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="89982-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="89982-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="89982-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="89982-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="89982-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="89982-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="89982-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="89982-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="89982-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="89982-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="89982-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="89982-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="89982-119">Version type</span></span>
-   <span data-ttu-id="89982-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="89982-120">Date and time</span></span>
-   <span data-ttu-id="89982-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="89982-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="89982-122">Fiscal year</span></span>
-   <span data-ttu-id="89982-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="89982-123">Fiscal period</span></span>

<span data-ttu-id="89982-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="89982-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="89982-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="89982-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="89982-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="89982-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="89982-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="89982-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="89982-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="89982-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="89982-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="89982-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="89982-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="89982-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="89982-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="89982-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="89982-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="89982-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="89982-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="89982-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="89982-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="89982-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="89982-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="89982-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="89982-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="89982-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="89982-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="89982-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="89982-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="89982-140">Main account</span></span></th>
<th><span data-ttu-id="89982-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="89982-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="89982-143">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-143">CC099</span></span></td>
<td><span data-ttu-id="89982-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-144">Default cost center</span></span></td>
<td><span data-ttu-id="89982-145">10001</span><span class="sxs-lookup"><span data-stu-id="89982-145">10001</span></span></td>
<td><span data-ttu-id="89982-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-146">Electricity</span></span></td>
<td><span data-ttu-id="89982-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="89982-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="89982-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="89982-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="89982-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="89982-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="89982-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-151">Define the cost behavior rule</span></span>

<span data-ttu-id="89982-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="89982-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="89982-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="89982-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="89982-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="89982-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="89982-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="89982-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="89982-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="89982-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="89982-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="89982-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="89982-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="89982-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="89982-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="89982-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="89982-160">Journal</span></span></th>
<th><span data-ttu-id="89982-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="89982-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="89982-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="89982-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="89982-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="89982-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-164">00001</span><span class="sxs-lookup"><span data-stu-id="89982-164">00001</span></span></td>
<td><span data-ttu-id="89982-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="89982-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="89982-166">Fiscal</span></span></td>
<td><span data-ttu-id="89982-167">2017</span><span class="sxs-lookup"><span data-stu-id="89982-167">2017</span></span></td>
<td><span data-ttu-id="89982-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="89982-168">Period 1</span></span></td>
<td><span data-ttu-id="89982-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="89982-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="89982-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="89982-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="89982-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="89982-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="89982-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="89982-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-173">Cost element</span></span></th>
<th><span data-ttu-id="89982-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-174">Cost behavior</span></span></th>
<th><span data-ttu-id="89982-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="89982-177">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-177">CC099</span></span></td>
<td><span data-ttu-id="89982-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-178">Default cost center</span></span></td>
<td><span data-ttu-id="89982-179">10001</span><span class="sxs-lookup"><span data-stu-id="89982-179">10001</span></span></td>
<td><span data-ttu-id="89982-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-180">Electricity</span></span></td>
<td><span data-ttu-id="89982-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="89982-181">Unclassified</span></span></td>
<td><span data-ttu-id="89982-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="89982-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="89982-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="89982-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-185">Cost element</span></span></th>
<th><span data-ttu-id="89982-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-186">Cost behavior</span></span></th>
<th><span data-ttu-id="89982-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-187">Amount</span></span></th>
<th><span data-ttu-id="89982-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="89982-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-189">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-189">CC099</span></span></td>
<td><span data-ttu-id="89982-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-190">Default cost center</span></span></td>
<td><span data-ttu-id="89982-191">10001</span><span class="sxs-lookup"><span data-stu-id="89982-191">10001</span></span></td>
<td><span data-ttu-id="89982-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-192">Electricity</span></span></td>
<td><span data-ttu-id="89982-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="89982-193">Unclassified</span></span></td>
<td><span data-ttu-id="89982-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="89982-194">10,000.00</span></span></td>
<td><span data-ttu-id="89982-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-196">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-196">CC099</span></span></td>
<td><span data-ttu-id="89982-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-197">Default cost center</span></span></td>
<td><span data-ttu-id="89982-198">10001</span><span class="sxs-lookup"><span data-stu-id="89982-198">10001</span></span></td>
<td><span data-ttu-id="89982-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-199">Electricity</span></span></td>
<td><span data-ttu-id="89982-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="89982-200">Unclassified</span></span></td>
<td><span data-ttu-id="89982-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="89982-201">-10,000.00</span></span></td>
<td><span data-ttu-id="89982-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-203">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-203">CC099</span></span></td>
<td><span data-ttu-id="89982-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-204">Default cost center</span></span></td>
<td><span data-ttu-id="89982-205">10001</span><span class="sxs-lookup"><span data-stu-id="89982-205">10001</span></span></td>
<td><span data-ttu-id="89982-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-206">Electricity</span></span></td>
<td><span data-ttu-id="89982-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-207">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="89982-208">1,000.00</span></span></td>
<td><span data-ttu-id="89982-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-210">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-210">CC099</span></span></td>
<td><span data-ttu-id="89982-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-211">Default cost center</span></span></td>
<td><span data-ttu-id="89982-212">10001</span><span class="sxs-lookup"><span data-stu-id="89982-212">10001</span></span></td>
<td><span data-ttu-id="89982-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-213">Electricity</span></span></td>
<td><span data-ttu-id="89982-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-214">Variable cost</span></span></td>
<td><span data-ttu-id="89982-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="89982-215">9,000.00</span></span></td>
<td><span data-ttu-id="89982-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="89982-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="89982-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="89982-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="89982-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="89982-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="89982-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="89982-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-221">Define the cost distribution rule</span></span>

<span data-ttu-id="89982-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="89982-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="89982-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="89982-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="89982-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="89982-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="89982-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="89982-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="89982-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="89982-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="89982-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="89982-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-228">Cost object</span></span></th>
<th><span data-ttu-id="89982-229">kWh</span><span class="sxs-lookup"><span data-stu-id="89982-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-230">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-230">CC001</span></span></td>
<td><span data-ttu-id="89982-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-231">HR</span></span></td>
<td><span data-ttu-id="89982-232">1 000</span><span class="sxs-lookup"><span data-stu-id="89982-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-233">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-233">CC002</span></span></td>
<td><span data-ttu-id="89982-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-234">Finance</span></span></td>
<td><span data-ttu-id="89982-235">6,000</span><span class="sxs-lookup"><span data-stu-id="89982-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-236">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-236">CC003</span></span></td>
<td><span data-ttu-id="89982-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-237">Assembly</span></span></td>
<td><span data-ttu-id="89982-238">0</span><span class="sxs-lookup"><span data-stu-id="89982-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="89982-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-240">Cost object</span></span></th>
<th><span data-ttu-id="89982-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="89982-241">Magnitude</span></span></th>
<th><span data-ttu-id="89982-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="89982-242">Allocation factor</span></span></th>
<th><span data-ttu-id="89982-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-244">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-244">CC001</span></span></td>
<td><span data-ttu-id="89982-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-245">HR</span></span></td>
<td><span data-ttu-id="89982-246">1 000</span><span class="sxs-lookup"><span data-stu-id="89982-246">1,000</span></span></td>
<td><span data-ttu-id="89982-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="89982-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="89982-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="89982-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-249">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-249">CC002</span></span></td>
<td><span data-ttu-id="89982-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-250">Finance</span></span></td>
<td><span data-ttu-id="89982-251">6,000</span><span class="sxs-lookup"><span data-stu-id="89982-251">6,000</span></span></td>
<td><span data-ttu-id="89982-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="89982-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="89982-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="89982-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-254">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-254">CC003</span></span></td>
<td><span data-ttu-id="89982-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-255">Assembly</span></span></td>
<td><span data-ttu-id="89982-256">0</span><span class="sxs-lookup"><span data-stu-id="89982-256">0</span></span></td>
<td><span data-ttu-id="89982-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="89982-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="89982-258">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="89982-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="89982-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="89982-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-261">Cost object</span></span></th>
<th><span data-ttu-id="89982-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="89982-262">Formula</span></span></th>
<th><span data-ttu-id="89982-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="89982-263">Magnitude</span></span></th>
<th><span data-ttu-id="89982-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="89982-264">Allocation factor</span></span></th>
<th><span data-ttu-id="89982-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-266">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-266">CC001</span></span></td>
<td><span data-ttu-id="89982-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-267">HR</span></span></td>
<td><span data-ttu-id="89982-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="89982-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="89982-269">1</span><span class="sxs-lookup"><span data-stu-id="89982-269">1</span></span></td>
<td><span data-ttu-id="89982-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="89982-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="89982-271">500.00</span><span class="sxs-lookup"><span data-stu-id="89982-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-272">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-272">CC002</span></span></td>
<td><span data-ttu-id="89982-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-273">Finance</span></span></td>
<td><span data-ttu-id="89982-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="89982-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="89982-275">1</span><span class="sxs-lookup"><span data-stu-id="89982-275">1</span></span></td>
<td><span data-ttu-id="89982-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="89982-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="89982-277">500.00</span><span class="sxs-lookup"><span data-stu-id="89982-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-278">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-278">CC003</span></span></td>
<td><span data-ttu-id="89982-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-279">Assembly</span></span></td>
<td><span data-ttu-id="89982-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="89982-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="89982-281">0</span><span class="sxs-lookup"><span data-stu-id="89982-281">0</span></span></td>
<td><span data-ttu-id="89982-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="89982-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="89982-283">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="89982-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="89982-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="89982-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="89982-285">Journal</span></span></th>
<th><span data-ttu-id="89982-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="89982-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="89982-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="89982-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="89982-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="89982-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-289">00002</span><span class="sxs-lookup"><span data-stu-id="89982-289">00002</span></span></td>
<td><span data-ttu-id="89982-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="89982-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="89982-291">Fiscal</span></span></td>
<td><span data-ttu-id="89982-292">2017</span><span class="sxs-lookup"><span data-stu-id="89982-292">2017</span></span></td>
<td><span data-ttu-id="89982-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="89982-293">Period 1</span></span></td>
<td><span data-ttu-id="89982-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="89982-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="89982-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="89982-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="89982-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="89982-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="89982-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="89982-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-298">Cost element</span></span></th>
<th><span data-ttu-id="89982-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-299">Cost behavior</span></span></th>
<th><span data-ttu-id="89982-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-302">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-302">CC099</span></span></td>
<td><span data-ttu-id="89982-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-303">Default cost center</span></span></td>
<td><span data-ttu-id="89982-304">10001</span><span class="sxs-lookup"><span data-stu-id="89982-304">10001</span></span></td>
<td><span data-ttu-id="89982-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-305">Electricity</span></span></td>
<td><span data-ttu-id="89982-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-306">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="89982-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-309">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-309">CC099</span></span></td>
<td><span data-ttu-id="89982-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-310">Default cost center</span></span></td>
<td><span data-ttu-id="89982-311">10001</span><span class="sxs-lookup"><span data-stu-id="89982-311">10001</span></span></td>
<td><span data-ttu-id="89982-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-312">Electricity</span></span></td>
<td><span data-ttu-id="89982-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-313">Variable cost</span></span></td>
<td><span data-ttu-id="89982-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="89982-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="89982-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="89982-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-317">Cost element</span></span></th>
<th><span data-ttu-id="89982-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-318">Cost behavior</span></span></th>
<th><span data-ttu-id="89982-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-319">Amount</span></span></th>
<th><span data-ttu-id="89982-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="89982-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-321">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-321">CC099</span></span></td>
<td><span data-ttu-id="89982-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-322">Default cost center</span></span></td>
<td><span data-ttu-id="89982-323">10001</span><span class="sxs-lookup"><span data-stu-id="89982-323">10001</span></span></td>
<td><span data-ttu-id="89982-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-324">Electricity</span></span></td>
<td><span data-ttu-id="89982-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-325">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="89982-326">-1,000.00</span></span></td>
<td><span data-ttu-id="89982-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-328">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-328">CC001</span></span></td>
<td><span data-ttu-id="89982-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-329">HR</span></span></td>
<td><span data-ttu-id="89982-330">10001</span><span class="sxs-lookup"><span data-stu-id="89982-330">10001</span></span></td>
<td><span data-ttu-id="89982-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-331">Electricity</span></span></td>
<td><span data-ttu-id="89982-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-332">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-333">500.00</span><span class="sxs-lookup"><span data-stu-id="89982-333">500.00</span></span></td>
<td><span data-ttu-id="89982-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-335">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-335">CC002</span></span></td>
<td><span data-ttu-id="89982-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-336">Finance</span></span></td>
<td><span data-ttu-id="89982-337">10001</span><span class="sxs-lookup"><span data-stu-id="89982-337">10001</span></span></td>
<td><span data-ttu-id="89982-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-338">Electricity</span></span></td>
<td><span data-ttu-id="89982-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-339">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-340">500.00</span><span class="sxs-lookup"><span data-stu-id="89982-340">500.00</span></span></td>
<td><span data-ttu-id="89982-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-342">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-342">CC099</span></span></td>
<td><span data-ttu-id="89982-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-343">Default cost center</span></span></td>
<td><span data-ttu-id="89982-344">10001</span><span class="sxs-lookup"><span data-stu-id="89982-344">10001</span></span></td>
<td><span data-ttu-id="89982-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-345">Electricity</span></span></td>
<td><span data-ttu-id="89982-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-346">Variable cost</span></span></td>
<td><span data-ttu-id="89982-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="89982-347">-9,000.00</span></span></td>
<td><span data-ttu-id="89982-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-349">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-349">CC001</span></span></td>
<td><span data-ttu-id="89982-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-350">HR</span></span></td>
<td><span data-ttu-id="89982-351">10001</span><span class="sxs-lookup"><span data-stu-id="89982-351">10001</span></span></td>
<td><span data-ttu-id="89982-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-352">Electricity</span></span></td>
<td><span data-ttu-id="89982-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-353">Variable cost</span></span></td>
<td><span data-ttu-id="89982-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="89982-354">1,285.71</span></span></td>
<td><span data-ttu-id="89982-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-356">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-356">CC002</span></span></td>
<td><span data-ttu-id="89982-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-357">Finance</span></span></td>
<td><span data-ttu-id="89982-358">10001</span><span class="sxs-lookup"><span data-stu-id="89982-358">10001</span></span></td>
<td><span data-ttu-id="89982-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-359">Electricity</span></span></td>
<td><span data-ttu-id="89982-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-360">Variable cost</span></span></td>
<td><span data-ttu-id="89982-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="89982-361">7,714.29</span></span></td>
<td><span data-ttu-id="89982-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="89982-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="89982-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="89982-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="89982-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="89982-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="89982-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="89982-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="89982-367">Define the overhead rate</span></span>

<span data-ttu-id="89982-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="89982-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="89982-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="89982-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-370">Cost object</span></span></th>
<th><span data-ttu-id="89982-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="89982-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="89982-372">Proj 1</span></span></td>
<td><span data-ttu-id="89982-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="89982-373">Project 1</span></span></td>
<td><span data-ttu-id="89982-374">3</span><span class="sxs-lookup"><span data-stu-id="89982-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="89982-375">Proj 2</span></span></td>
<td><span data-ttu-id="89982-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="89982-376">Project 2</span></span></td>
<td><span data-ttu-id="89982-377">1</span><span class="sxs-lookup"><span data-stu-id="89982-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="89982-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-379">Cost object</span></span></th>
<th><span data-ttu-id="89982-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-380">Cost element</span></span></th>
<th><span data-ttu-id="89982-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-381">Cost behavior</span></span></th>
<th><span data-ttu-id="89982-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="89982-382">Units</span></span></th>
<th><span data-ttu-id="89982-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="89982-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-384">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-384">CC001</span></span></td>
<td><span data-ttu-id="89982-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-385">HR</span></span></td>
<td><span data-ttu-id="89982-386">10001</span><span class="sxs-lookup"><span data-stu-id="89982-386">10001</span></span></td>
<td><span data-ttu-id="89982-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-387">Variable cost</span></span></td>
<td><span data-ttu-id="89982-388">1</span><span class="sxs-lookup"><span data-stu-id="89982-388">1</span></span></td>
<td><span data-ttu-id="89982-389">10</span><span class="sxs-lookup"><span data-stu-id="89982-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="89982-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-391">Cost object</span></span></th>
<th><span data-ttu-id="89982-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="89982-392">Magnitude</span></span></th>
<th><span data-ttu-id="89982-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-393">Cost element</span></span></th>
<th><span data-ttu-id="89982-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="89982-394">Allocation factor</span></span></th>
<th><span data-ttu-id="89982-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="89982-396">Proj 1</span></span></td>
<td><span data-ttu-id="89982-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="89982-397">Project 1</span></span></td>
<td><span data-ttu-id="89982-398">3</span><span class="sxs-lookup"><span data-stu-id="89982-398">3</span></span></td>
<td><span data-ttu-id="89982-399">10001</span><span class="sxs-lookup"><span data-stu-id="89982-399">10001</span></span></td>
<td><span data-ttu-id="89982-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="89982-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="89982-401">30.00</span><span class="sxs-lookup"><span data-stu-id="89982-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="89982-402">Proj 2</span></span></td>
<td><span data-ttu-id="89982-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="89982-403">Project 2</span></span></td>
<td><span data-ttu-id="89982-404">1</span><span class="sxs-lookup"><span data-stu-id="89982-404">1</span></span></td>
<td><span data-ttu-id="89982-405">10001</span><span class="sxs-lookup"><span data-stu-id="89982-405">10001</span></span></td>
<td><span data-ttu-id="89982-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="89982-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="89982-407">10,00</span><span class="sxs-lookup"><span data-stu-id="89982-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="89982-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="89982-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="89982-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="89982-409">Journal</span></span></th>
<th><span data-ttu-id="89982-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="89982-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="89982-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="89982-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="89982-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="89982-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-413">00003</span><span class="sxs-lookup"><span data-stu-id="89982-413">00003</span></span></td>
<td><span data-ttu-id="89982-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="89982-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="89982-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="89982-415">Fiscal</span></span></td>
<td><span data-ttu-id="89982-416">2017</span><span class="sxs-lookup"><span data-stu-id="89982-416">2017</span></span></td>
<td><span data-ttu-id="89982-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="89982-417">Period 1</span></span></td>
<td><span data-ttu-id="89982-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="89982-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="89982-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="89982-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="89982-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="89982-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="89982-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-421">Cost object</span></span></th>
<th><span data-ttu-id="89982-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="89982-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="89982-424">Proj 1</span></span></td>
<td><span data-ttu-id="89982-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="89982-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="89982-426">3,00</span><span class="sxs-lookup"><span data-stu-id="89982-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="89982-428">Proj 2</span></span></td>
<td><span data-ttu-id="89982-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="89982-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="89982-430">1.00</span><span class="sxs-lookup"><span data-stu-id="89982-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="89982-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="89982-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-433">Cost element</span></span></th>
<th><span data-ttu-id="89982-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-434">Cost behavior</span></span></th>
<th><span data-ttu-id="89982-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-435">Amount</span></span></th>
<th><span data-ttu-id="89982-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="89982-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="89982-437">CC0001</span></span></td>
<td><span data-ttu-id="89982-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-438">HR</span></span></td>
<td><span data-ttu-id="89982-439">10001</span><span class="sxs-lookup"><span data-stu-id="89982-439">10001</span></span></td>
<td><span data-ttu-id="89982-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-440">Electricity</span></span></td>
<td><span data-ttu-id="89982-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-441">Variable cost</span></span></td>
<td><span data-ttu-id="89982-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="89982-442">-30.00</span></span></td>
<td><span data-ttu-id="89982-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="89982-444">Proj 1</span></span></td>
<td><span data-ttu-id="89982-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="89982-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="89982-446">10001</span><span class="sxs-lookup"><span data-stu-id="89982-446">10001</span></span></td>
<td><span data-ttu-id="89982-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-447">Electricity</span></span></td>
<td><span data-ttu-id="89982-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-448">Variable cost</span></span></td>
<td><span data-ttu-id="89982-449">30.00</span><span class="sxs-lookup"><span data-stu-id="89982-449">30.00</span></span></td>
<td><span data-ttu-id="89982-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-451">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-451">CC001</span></span></td>
<td><span data-ttu-id="89982-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-452">HR</span></span></td>
<td><span data-ttu-id="89982-453">10001</span><span class="sxs-lookup"><span data-stu-id="89982-453">10001</span></span></td>
<td><span data-ttu-id="89982-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-454">Electricity</span></span></td>
<td><span data-ttu-id="89982-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-455">Variable cost</span></span></td>
<td><span data-ttu-id="89982-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="89982-456">-10.00</span></span></td>
<td><span data-ttu-id="89982-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="89982-458">Proj 2</span></span></td>
<td><span data-ttu-id="89982-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="89982-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="89982-460">10001</span><span class="sxs-lookup"><span data-stu-id="89982-460">10001</span></span></td>
<td><span data-ttu-id="89982-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-461">Electricity</span></span></td>
<td><span data-ttu-id="89982-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-462">Variable cost</span></span></td>
<td><span data-ttu-id="89982-463">10,00</span><span class="sxs-lookup"><span data-stu-id="89982-463">10.00</span></span></td>
<td><span data-ttu-id="89982-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="89982-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="89982-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="89982-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="89982-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="89982-468">Aplikacja Finance obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="89982-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="89982-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="89982-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="89982-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="89982-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="89982-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="89982-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="89982-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="89982-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="89982-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="89982-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="89982-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-475">Define the cost allocation</span></span>

<span data-ttu-id="89982-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="89982-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="89982-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="89982-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-479">Cost object</span></span></th>
<th><span data-ttu-id="89982-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="89982-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-481">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-481">CC002</span></span></td>
<td><span data-ttu-id="89982-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-482">Finance</span></span></td>
<td><span data-ttu-id="89982-483">35</span><span class="sxs-lookup"><span data-stu-id="89982-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-484">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-484">CC003</span></span></td>
<td><span data-ttu-id="89982-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-485">Assembly</span></span></td>
<td><span data-ttu-id="89982-486">55</span><span class="sxs-lookup"><span data-stu-id="89982-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-487">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-487">CC004</span></span></td>
<td><span data-ttu-id="89982-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-488">Packaging</span></span></td>
<td><span data-ttu-id="89982-489">10</span><span class="sxs-lookup"><span data-stu-id="89982-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="89982-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="89982-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-492">Cost object</span></span></th>
<th><span data-ttu-id="89982-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="89982-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-494">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-494">CC003</span></span></td>
<td><span data-ttu-id="89982-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-495">Assembly</span></span></td>
<td><span data-ttu-id="89982-496">65</span><span class="sxs-lookup"><span data-stu-id="89982-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-497">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-497">CC004</span></span></td>
<td><span data-ttu-id="89982-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-498">Packaging</span></span></td>
<td><span data-ttu-id="89982-499">35</span><span class="sxs-lookup"><span data-stu-id="89982-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="89982-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="89982-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-502">Cost object</span></span></th>
<th><span data-ttu-id="89982-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="89982-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-504">Prod 1</span></span></td>
<td><span data-ttu-id="89982-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-505">Product 1</span></span></td>
<td><span data-ttu-id="89982-506">60</span><span class="sxs-lookup"><span data-stu-id="89982-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-507">Prod 2</span></span></td>
<td><span data-ttu-id="89982-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-508">Product 2</span></span></td>
<td><span data-ttu-id="89982-509">20</span><span class="sxs-lookup"><span data-stu-id="89982-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="89982-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="89982-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-512">Cost object</span></span></th>
<th><span data-ttu-id="89982-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="89982-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-514">Prod 1</span></span></td>
<td><span data-ttu-id="89982-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-515">Product 1</span></span></td>
<td><span data-ttu-id="89982-516">80</span><span class="sxs-lookup"><span data-stu-id="89982-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-517">Prod 2</span></span></td>
<td><span data-ttu-id="89982-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-518">Product 2</span></span></td>
<td><span data-ttu-id="89982-519">15</span><span class="sxs-lookup"><span data-stu-id="89982-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="89982-520">Miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="89982-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="89982-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="89982-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="89982-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="89982-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-523">Cost object</span></span></th>
<th><span data-ttu-id="89982-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="89982-524">Magnitude</span></span></th>
<th><span data-ttu-id="89982-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="89982-525">Allocation factor</span></span></th>
<th><span data-ttu-id="89982-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-526">Amount</span></span></th>
<th><span data-ttu-id="89982-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-528">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-528">CC002</span></span></td>
<td><span data-ttu-id="89982-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-529">Finance</span></span></td>
<td><span data-ttu-id="89982-530">35</span><span class="sxs-lookup"><span data-stu-id="89982-530">35</span></span></td>
<td><span data-ttu-id="89982-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="89982-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="89982-532">175.00</span><span class="sxs-lookup"><span data-stu-id="89982-532">175.00</span></span></td>
<td><span data-ttu-id="89982-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-534">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-534">CC003</span></span></td>
<td><span data-ttu-id="89982-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-535">Assembly</span></span></td>
<td><span data-ttu-id="89982-536">55</span><span class="sxs-lookup"><span data-stu-id="89982-536">55</span></span></td>
<td><span data-ttu-id="89982-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="89982-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="89982-538">275.00</span><span class="sxs-lookup"><span data-stu-id="89982-538">275.00</span></span></td>
<td><span data-ttu-id="89982-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-540">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-540">CC004</span></span></td>
<td><span data-ttu-id="89982-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-541">Packaging</span></span></td>
<td><span data-ttu-id="89982-542">10</span><span class="sxs-lookup"><span data-stu-id="89982-542">10</span></span></td>
<td><span data-ttu-id="89982-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="89982-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="89982-544">50,00</span><span class="sxs-lookup"><span data-stu-id="89982-544">50.00</span></span></td>
<td><span data-ttu-id="89982-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-546">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-546">CC002</span></span></td>
<td><span data-ttu-id="89982-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-547">Finance</span></span></td>
<td><span data-ttu-id="89982-548">35</span><span class="sxs-lookup"><span data-stu-id="89982-548">35</span></span></td>
<td><span data-ttu-id="89982-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="89982-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="89982-550">436.00</span><span class="sxs-lookup"><span data-stu-id="89982-550">436.00</span></span></td>
<td><span data-ttu-id="89982-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-552">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-552">CC003</span></span></td>
<td><span data-ttu-id="89982-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-553">Assembly</span></span></td>
<td><span data-ttu-id="89982-554">55</span><span class="sxs-lookup"><span data-stu-id="89982-554">55</span></span></td>
<td><span data-ttu-id="89982-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="89982-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="89982-556">685.14</span><span class="sxs-lookup"><span data-stu-id="89982-556">685.14</span></span></td>
<td><span data-ttu-id="89982-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-558">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-558">CC004</span></span></td>
<td><span data-ttu-id="89982-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-559">Packaging</span></span></td>
<td><span data-ttu-id="89982-560">10</span><span class="sxs-lookup"><span data-stu-id="89982-560">10</span></span></td>
<td><span data-ttu-id="89982-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="89982-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="89982-562">124.57</span><span class="sxs-lookup"><span data-stu-id="89982-562">124.57</span></span></td>
<td><span data-ttu-id="89982-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="89982-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-565">Cost object</span></span></th>
<th><span data-ttu-id="89982-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="89982-566">Magnitude</span></span></th>
<th><span data-ttu-id="89982-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="89982-567">Allocation factor</span></span></th>
<th><span data-ttu-id="89982-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-568">Amount</span></span></th>
<th><span data-ttu-id="89982-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-570">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-570">CC003</span></span></td>
<td><span data-ttu-id="89982-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-571">Assembly</span></span></td>
<td><span data-ttu-id="89982-572">65</span><span class="sxs-lookup"><span data-stu-id="89982-572">65</span></span></td>
<td><span data-ttu-id="89982-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="89982-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="89982-574">438.75</span><span class="sxs-lookup"><span data-stu-id="89982-574">438.75</span></span></td>
<td><span data-ttu-id="89982-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-576">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-576">CC004</span></span></td>
<td><span data-ttu-id="89982-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-577">Packaging</span></span></td>
<td><span data-ttu-id="89982-578">35</span><span class="sxs-lookup"><span data-stu-id="89982-578">35</span></span></td>
<td><span data-ttu-id="89982-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="89982-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="89982-580">236.25</span><span class="sxs-lookup"><span data-stu-id="89982-580">236.25</span></span></td>
<td><span data-ttu-id="89982-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-582">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-582">CC003</span></span></td>
<td><span data-ttu-id="89982-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-583">Assembly</span></span></td>
<td><span data-ttu-id="89982-584">65</span><span class="sxs-lookup"><span data-stu-id="89982-584">65</span></span></td>
<td><span data-ttu-id="89982-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="89982-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="89982-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="89982-586">5,297.69</span></span></td>
<td><span data-ttu-id="89982-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-588">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-588">CC004</span></span></td>
<td><span data-ttu-id="89982-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-589">Packaging</span></span></td>
<td><span data-ttu-id="89982-590">35</span><span class="sxs-lookup"><span data-stu-id="89982-590">35</span></span></td>
<td><span data-ttu-id="89982-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="89982-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="89982-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="89982-592">2,852.60</span></span></td>
<td><span data-ttu-id="89982-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="89982-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-595">Cost object</span></span></th>
<th><span data-ttu-id="89982-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="89982-596">Magnitude</span></span></th>
<th><span data-ttu-id="89982-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="89982-597">Allocation factor</span></span></th>
<th><span data-ttu-id="89982-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-598">Amount</span></span></th>
<th><span data-ttu-id="89982-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-600">Prod 1</span></span></td>
<td><span data-ttu-id="89982-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-601">Product 1</span></span></td>
<td><span data-ttu-id="89982-602">60</span><span class="sxs-lookup"><span data-stu-id="89982-602">60</span></span></td>
<td><span data-ttu-id="89982-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="89982-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="89982-604">535.31</span><span class="sxs-lookup"><span data-stu-id="89982-604">535.31</span></span></td>
<td><span data-ttu-id="89982-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-606">Prod 2</span></span></td>
<td><span data-ttu-id="89982-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-607">Product 2</span></span></td>
<td><span data-ttu-id="89982-608">20</span><span class="sxs-lookup"><span data-stu-id="89982-608">20</span></span></td>
<td><span data-ttu-id="89982-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="89982-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="89982-610">178.44</span><span class="sxs-lookup"><span data-stu-id="89982-610">178.44</span></span></td>
<td><span data-ttu-id="89982-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-612">Prod 1</span></span></td>
<td><span data-ttu-id="89982-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-613">Product 1</span></span></td>
<td><span data-ttu-id="89982-614">60</span><span class="sxs-lookup"><span data-stu-id="89982-614">60</span></span></td>
<td><span data-ttu-id="89982-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="89982-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="89982-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="89982-616">4,487.12</span></span></td>
<td><span data-ttu-id="89982-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-618">Prod 2</span></span></td>
<td><span data-ttu-id="89982-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-619">Product 2</span></span></td>
<td><span data-ttu-id="89982-620">20</span><span class="sxs-lookup"><span data-stu-id="89982-620">20</span></span></td>
<td><span data-ttu-id="89982-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="89982-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="89982-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="89982-622">1,495.71</span></span></td>
<td><span data-ttu-id="89982-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89982-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="89982-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-625">Cost object</span></span></th>
<th><span data-ttu-id="89982-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="89982-626">Magnitude</span></span></th>
<th><span data-ttu-id="89982-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="89982-627">Allocation factor</span></span></th>
<th><span data-ttu-id="89982-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-628">Amount</span></span></th>
<th><span data-ttu-id="89982-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-630">Prod 1</span></span></td>
<td><span data-ttu-id="89982-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-631">Product 1</span></span></td>
<td><span data-ttu-id="89982-632">80</span><span class="sxs-lookup"><span data-stu-id="89982-632">80</span></span></td>
<td><span data-ttu-id="89982-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="89982-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="89982-634">241.05</span><span class="sxs-lookup"><span data-stu-id="89982-634">241.05</span></span></td>
<td><span data-ttu-id="89982-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-636">Prod 2</span></span></td>
<td><span data-ttu-id="89982-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-637">Product 2</span></span></td>
<td><span data-ttu-id="89982-638">15</span><span class="sxs-lookup"><span data-stu-id="89982-638">15</span></span></td>
<td><span data-ttu-id="89982-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="89982-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="89982-640">45.20</span><span class="sxs-lookup"><span data-stu-id="89982-640">45.20</span></span></td>
<td><span data-ttu-id="89982-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-642">Prod 1</span></span></td>
<td><span data-ttu-id="89982-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-643">Product 1</span></span></td>
<td><span data-ttu-id="89982-644">80</span><span class="sxs-lookup"><span data-stu-id="89982-644">80</span></span></td>
<td><span data-ttu-id="89982-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="89982-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="89982-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="89982-646">2,507.09</span></span></td>
<td><span data-ttu-id="89982-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-648">Prod 2</span></span></td>
<td><span data-ttu-id="89982-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-649">Product 2</span></span></td>
<td><span data-ttu-id="89982-650">15</span><span class="sxs-lookup"><span data-stu-id="89982-650">15</span></span></td>
<td><span data-ttu-id="89982-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="89982-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="89982-652">470.08</span><span class="sxs-lookup"><span data-stu-id="89982-652">470.08</span></span></td>
<td><span data-ttu-id="89982-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="89982-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="89982-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="89982-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="89982-655">Journal</span></span></th>
<th><span data-ttu-id="89982-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="89982-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="89982-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="89982-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="89982-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="89982-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-659">00004</span><span class="sxs-lookup"><span data-stu-id="89982-659">00004</span></span></td>
<td><span data-ttu-id="89982-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="89982-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="89982-661">Fiscal</span></span></td>
<td><span data-ttu-id="89982-662">2017</span><span class="sxs-lookup"><span data-stu-id="89982-662">2017</span></span></td>
<td><span data-ttu-id="89982-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="89982-663">Period 1</span></span></td>
<td><span data-ttu-id="89982-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="89982-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="89982-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="89982-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="89982-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="89982-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="89982-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="89982-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-668">Cost element</span></span></th>
<th><span data-ttu-id="89982-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-669">Cost behavior</span></span></th>
<th><span data-ttu-id="89982-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-672">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-672">CC001</span></span></td>
<td><span data-ttu-id="89982-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-673">HR</span></span></td>
<td><span data-ttu-id="89982-674">10001</span><span class="sxs-lookup"><span data-stu-id="89982-674">10001</span></span></td>
<td><span data-ttu-id="89982-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-675">Electricity</span></span></td>
<td><span data-ttu-id="89982-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-676">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-677">500.00</span><span class="sxs-lookup"><span data-stu-id="89982-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-679">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-679">CC001</span></span></td>
<td><span data-ttu-id="89982-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-680">HR</span></span></td>
<td><span data-ttu-id="89982-681">10001</span><span class="sxs-lookup"><span data-stu-id="89982-681">10001</span></span></td>
<td><span data-ttu-id="89982-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-682">Electricity</span></span></td>
<td><span data-ttu-id="89982-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-683">Variable cost</span></span></td>
<td><span data-ttu-id="89982-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="89982-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-686">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-686">CC002</span></span></td>
<td><span data-ttu-id="89982-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-687">Finance</span></span></td>
<td><span data-ttu-id="89982-688">10001</span><span class="sxs-lookup"><span data-stu-id="89982-688">10001</span></span></td>
<td><span data-ttu-id="89982-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-689">Electricity</span></span></td>
<td><span data-ttu-id="89982-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-690">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-691">675.00</span><span class="sxs-lookup"><span data-stu-id="89982-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-693">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-693">CC002</span></span></td>
<td><span data-ttu-id="89982-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-694">Finance</span></span></td>
<td><span data-ttu-id="89982-695">10001</span><span class="sxs-lookup"><span data-stu-id="89982-695">10001</span></span></td>
<td><span data-ttu-id="89982-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-696">Electricity</span></span></td>
<td><span data-ttu-id="89982-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-697">Variable cost</span></span></td>
<td><span data-ttu-id="89982-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="89982-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-700">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-700">CC003</span></span></td>
<td><span data-ttu-id="89982-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-701">Assembly</span></span></td>
<td><span data-ttu-id="89982-702">10001</span><span class="sxs-lookup"><span data-stu-id="89982-702">10001</span></span></td>
<td><span data-ttu-id="89982-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-703">Electricity</span></span></td>
<td><span data-ttu-id="89982-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-704">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-705">713.75</span><span class="sxs-lookup"><span data-stu-id="89982-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-707">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-707">CC003</span></span></td>
<td><span data-ttu-id="89982-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-708">Assembly</span></span></td>
<td><span data-ttu-id="89982-709">10001</span><span class="sxs-lookup"><span data-stu-id="89982-709">10001</span></span></td>
<td><span data-ttu-id="89982-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-710">Electricity</span></span></td>
<td><span data-ttu-id="89982-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-711">Variable cost</span></span></td>
<td><span data-ttu-id="89982-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="89982-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-714">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-714">CC003</span></span></td>
<td><span data-ttu-id="89982-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-715">Packaging</span></span></td>
<td><span data-ttu-id="89982-716">10001</span><span class="sxs-lookup"><span data-stu-id="89982-716">10001</span></span></td>
<td><span data-ttu-id="89982-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-717">Electricity</span></span></td>
<td><span data-ttu-id="89982-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-718">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-719">286.25</span><span class="sxs-lookup"><span data-stu-id="89982-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-721">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-721">CC003</span></span></td>
<td><span data-ttu-id="89982-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-722">Packaging</span></span></td>
<td><span data-ttu-id="89982-723">10001</span><span class="sxs-lookup"><span data-stu-id="89982-723">10001</span></span></td>
<td><span data-ttu-id="89982-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-724">Electricity</span></span></td>
<td><span data-ttu-id="89982-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-725">Variable cost</span></span></td>
<td><span data-ttu-id="89982-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="89982-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-728">Prod 1</span></span></td>
<td><span data-ttu-id="89982-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-729">Product 1</span></span></td>
<td><span data-ttu-id="89982-730">10001</span><span class="sxs-lookup"><span data-stu-id="89982-730">10001</span></span></td>
<td><span data-ttu-id="89982-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-731">Electricity</span></span></td>
<td><span data-ttu-id="89982-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-732">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-733">776.36</span><span class="sxs-lookup"><span data-stu-id="89982-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-735">Prod 1</span></span></td>
<td><span data-ttu-id="89982-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-736">Product 1</span></span></td>
<td><span data-ttu-id="89982-737">10001</span><span class="sxs-lookup"><span data-stu-id="89982-737">10001</span></span></td>
<td><span data-ttu-id="89982-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-738">Electricity</span></span></td>
<td><span data-ttu-id="89982-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-739">Variable cost</span></span></td>
<td><span data-ttu-id="89982-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="89982-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-742">Prod 2</span></span></td>
<td><span data-ttu-id="89982-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-743">Product 1</span></span></td>
<td><span data-ttu-id="89982-744">10001</span><span class="sxs-lookup"><span data-stu-id="89982-744">10001</span></span></td>
<td><span data-ttu-id="89982-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-745">Electricity</span></span></td>
<td><span data-ttu-id="89982-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-746">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-747">223.64</span><span class="sxs-lookup"><span data-stu-id="89982-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="89982-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-749">Prod 2</span></span></td>
<td><span data-ttu-id="89982-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-750">Product 1</span></span></td>
<td><span data-ttu-id="89982-751">10001</span><span class="sxs-lookup"><span data-stu-id="89982-751">10001</span></span></td>
<td><span data-ttu-id="89982-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-752">Electricity</span></span></td>
<td><span data-ttu-id="89982-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-753">Variable cost</span></span></td>
<td><span data-ttu-id="89982-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="89982-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="89982-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="89982-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="89982-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-757">Cost element</span></span></th>
<th><span data-ttu-id="89982-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-758">Cost behavior</span></span></th>
<th><span data-ttu-id="89982-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="89982-759">Amount</span></span></th>
<th><span data-ttu-id="89982-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="89982-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="89982-761">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-761">CC001</span></span></td>
<td><span data-ttu-id="89982-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-762">HR</span></span></td>
<td><span data-ttu-id="89982-763">10001</span><span class="sxs-lookup"><span data-stu-id="89982-763">10001</span></span></td>
<td><span data-ttu-id="89982-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-764">Electricity</span></span></td>
<td><span data-ttu-id="89982-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-765">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="89982-766">-500.00</span></span></td>
<td><span data-ttu-id="89982-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-768">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-768">CC002</span></span></td>
<td><span data-ttu-id="89982-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-769">Finance</span></span></td>
<td><span data-ttu-id="89982-770">10001</span><span class="sxs-lookup"><span data-stu-id="89982-770">10001</span></span></td>
<td><span data-ttu-id="89982-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-771">Electricity</span></span></td>
<td><span data-ttu-id="89982-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-772">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-773">175.00</span><span class="sxs-lookup"><span data-stu-id="89982-773">175.00</span></span></td>
<td><span data-ttu-id="89982-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-775">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-775">CC003</span></span></td>
<td><span data-ttu-id="89982-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-776">Assembly</span></span></td>
<td><span data-ttu-id="89982-777">10001</span><span class="sxs-lookup"><span data-stu-id="89982-777">10001</span></span></td>
<td><span data-ttu-id="89982-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-778">Electricity</span></span></td>
<td><span data-ttu-id="89982-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-779">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-780">275.00</span><span class="sxs-lookup"><span data-stu-id="89982-780">275.00</span></span></td>
<td><span data-ttu-id="89982-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-782">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-782">CC004</span></span></td>
<td><span data-ttu-id="89982-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-783">Packaging</span></span></td>
<td><span data-ttu-id="89982-784">10001</span><span class="sxs-lookup"><span data-stu-id="89982-784">10001</span></span></td>
<td><span data-ttu-id="89982-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-785">Electricity</span></span></td>
<td><span data-ttu-id="89982-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-786">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-787">50,00</span><span class="sxs-lookup"><span data-stu-id="89982-787">50,00</span></span></td>
<td><span data-ttu-id="89982-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-789">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-789">CC001</span></span></td>
<td><span data-ttu-id="89982-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="89982-790">HR</span></span></td>
<td><span data-ttu-id="89982-791">10001</span><span class="sxs-lookup"><span data-stu-id="89982-791">10001</span></span></td>
<td><span data-ttu-id="89982-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-792">Electricity</span></span></td>
<td><span data-ttu-id="89982-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-793">Variable cost</span></span></td>
<td><span data-ttu-id="89982-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="89982-794">-1,245.71</span></span></td>
<td><span data-ttu-id="89982-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-796">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-796">CC002</span></span></td>
<td><span data-ttu-id="89982-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-797">Finance</span></span></td>
<td><span data-ttu-id="89982-798">10001</span><span class="sxs-lookup"><span data-stu-id="89982-798">10001</span></span></td>
<td><span data-ttu-id="89982-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-799">Electricity</span></span></td>
<td><span data-ttu-id="89982-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-800">Variable cost</span></span></td>
<td><span data-ttu-id="89982-801">436.00</span><span class="sxs-lookup"><span data-stu-id="89982-801">436.00</span></span></td>
<td><span data-ttu-id="89982-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-803">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-803">CC003</span></span></td>
<td><span data-ttu-id="89982-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-804">Assembly</span></span></td>
<td><span data-ttu-id="89982-805">10001</span><span class="sxs-lookup"><span data-stu-id="89982-805">10001</span></span></td>
<td><span data-ttu-id="89982-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-806">Electricity</span></span></td>
<td><span data-ttu-id="89982-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-807">Variable cost</span></span></td>
<td><span data-ttu-id="89982-808">685.14</span><span class="sxs-lookup"><span data-stu-id="89982-808">685.14</span></span></td>
<td><span data-ttu-id="89982-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-810">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-810">CC004</span></span></td>
<td><span data-ttu-id="89982-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-811">Packaging</span></span></td>
<td><span data-ttu-id="89982-812">10001</span><span class="sxs-lookup"><span data-stu-id="89982-812">10001</span></span></td>
<td><span data-ttu-id="89982-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-813">Electricity</span></span></td>
<td><span data-ttu-id="89982-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-814">Variable cost</span></span></td>
<td><span data-ttu-id="89982-815">124.57</span><span class="sxs-lookup"><span data-stu-id="89982-815">124.57</span></span></td>
<td><span data-ttu-id="89982-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-817">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-817">CC002</span></span></td>
<td><span data-ttu-id="89982-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-818">Finance</span></span></td>
<td><span data-ttu-id="89982-819">10001</span><span class="sxs-lookup"><span data-stu-id="89982-819">10001</span></span></td>
<td><span data-ttu-id="89982-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-820">Electricity</span></span></td>
<td><span data-ttu-id="89982-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-821">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="89982-822">-675.00</span></span></td>
<td><span data-ttu-id="89982-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-824">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-824">CC003</span></span></td>
<td><span data-ttu-id="89982-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-825">Assembly</span></span></td>
<td><span data-ttu-id="89982-826">10001</span><span class="sxs-lookup"><span data-stu-id="89982-826">10001</span></span></td>
<td><span data-ttu-id="89982-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-827">Electricity</span></span></td>
<td><span data-ttu-id="89982-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-828">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-829">438.75</span><span class="sxs-lookup"><span data-stu-id="89982-829">438.75</span></span></td>
<td><span data-ttu-id="89982-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-831">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-831">CC004</span></span></td>
<td><span data-ttu-id="89982-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-832">Packaging</span></span></td>
<td><span data-ttu-id="89982-833">10001</span><span class="sxs-lookup"><span data-stu-id="89982-833">10001</span></span></td>
<td><span data-ttu-id="89982-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-834">Electricity</span></span></td>
<td><span data-ttu-id="89982-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-835">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-836">236.25</span><span class="sxs-lookup"><span data-stu-id="89982-836">236.25</span></span></td>
<td><span data-ttu-id="89982-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-838">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-838">CC002</span></span></td>
<td><span data-ttu-id="89982-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="89982-839">Finance</span></span></td>
<td><span data-ttu-id="89982-840">10001</span><span class="sxs-lookup"><span data-stu-id="89982-840">10001</span></span></td>
<td><span data-ttu-id="89982-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-841">Electricity</span></span></td>
<td><span data-ttu-id="89982-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-842">Variable cost</span></span></td>
<td><span data-ttu-id="89982-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="89982-843">-8,150.29</span></span></td>
<td><span data-ttu-id="89982-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-845">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-845">CC003</span></span></td>
<td><span data-ttu-id="89982-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-846">Assembly</span></span></td>
<td><span data-ttu-id="89982-847">10001</span><span class="sxs-lookup"><span data-stu-id="89982-847">10001</span></span></td>
<td><span data-ttu-id="89982-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-848">Electricity</span></span></td>
<td><span data-ttu-id="89982-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-849">Variable cost</span></span></td>
<td><span data-ttu-id="89982-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="89982-850">5,297.69</span></span></td>
<td><span data-ttu-id="89982-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-852">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-852">CC004</span></span></td>
<td><span data-ttu-id="89982-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="89982-853">Packaging</span></span></td>
<td><span data-ttu-id="89982-854">10001</span><span class="sxs-lookup"><span data-stu-id="89982-854">10001</span></span></td>
<td><span data-ttu-id="89982-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-855">Electricity</span></span></td>
<td><span data-ttu-id="89982-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-856">Variable cost</span></span></td>
<td><span data-ttu-id="89982-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="89982-857">2,852.60</span></span></td>
<td><span data-ttu-id="89982-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-859">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-859">CC003</span></span></td>
<td><span data-ttu-id="89982-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-860">Assembly</span></span></td>
<td><span data-ttu-id="89982-861">10001</span><span class="sxs-lookup"><span data-stu-id="89982-861">10001</span></span></td>
<td><span data-ttu-id="89982-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-862">Electricity</span></span></td>
<td><span data-ttu-id="89982-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-863">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="89982-864">-713.75</span></span></td>
<td><span data-ttu-id="89982-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-866">Prod 1</span></span></td>
<td><span data-ttu-id="89982-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-867">Product 1</span></span></td>
<td><span data-ttu-id="89982-868">10001</span><span class="sxs-lookup"><span data-stu-id="89982-868">10001</span></span></td>
<td><span data-ttu-id="89982-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-869">Electricity</span></span></td>
<td><span data-ttu-id="89982-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-870">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-871">535.31</span><span class="sxs-lookup"><span data-stu-id="89982-871">535.31</span></span></td>
<td><span data-ttu-id="89982-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-873">Prod 2</span></span></td>
<td><span data-ttu-id="89982-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-874">Product 2</span></span></td>
<td><span data-ttu-id="89982-875">10001</span><span class="sxs-lookup"><span data-stu-id="89982-875">10001</span></span></td>
<td><span data-ttu-id="89982-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-876">Electricity</span></span></td>
<td><span data-ttu-id="89982-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-877">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-878">178.44</span><span class="sxs-lookup"><span data-stu-id="89982-878">178.44</span></span></td>
<td><span data-ttu-id="89982-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-880">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-880">CC003</span></span></td>
<td><span data-ttu-id="89982-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-881">Assembly</span></span></td>
<td><span data-ttu-id="89982-882">10001</span><span class="sxs-lookup"><span data-stu-id="89982-882">10001</span></span></td>
<td><span data-ttu-id="89982-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-883">Electricity</span></span></td>
<td><span data-ttu-id="89982-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-884">Variable cost</span></span></td>
<td><span data-ttu-id="89982-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="89982-885">-5,982.83</span></span></td>
<td><span data-ttu-id="89982-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-887">Prod 1</span></span></td>
<td><span data-ttu-id="89982-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-888">Product 1</span></span></td>
<td><span data-ttu-id="89982-889">10001</span><span class="sxs-lookup"><span data-stu-id="89982-889">10001</span></span></td>
<td><span data-ttu-id="89982-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-890">Electricity</span></span></td>
<td><span data-ttu-id="89982-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-891">Variable cost</span></span></td>
<td><span data-ttu-id="89982-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="89982-892">4,487.12</span></span></td>
<td><span data-ttu-id="89982-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-894">Prod 2</span></span></td>
<td><span data-ttu-id="89982-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-895">Product 2</span></span></td>
<td><span data-ttu-id="89982-896">10001</span><span class="sxs-lookup"><span data-stu-id="89982-896">10001</span></span></td>
<td><span data-ttu-id="89982-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-897">Electricity</span></span></td>
<td><span data-ttu-id="89982-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-898">Variable cost</span></span></td>
<td><span data-ttu-id="89982-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="89982-899">1,495.71</span></span></td>
<td><span data-ttu-id="89982-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-901">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-901">CC003</span></span></td>
<td><span data-ttu-id="89982-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-902">Assembly</span></span></td>
<td><span data-ttu-id="89982-903">10001</span><span class="sxs-lookup"><span data-stu-id="89982-903">10001</span></span></td>
<td><span data-ttu-id="89982-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-904">Electricity</span></span></td>
<td><span data-ttu-id="89982-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-905">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="89982-906">-286.25</span></span></td>
<td><span data-ttu-id="89982-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-908">Prod 1</span></span></td>
<td><span data-ttu-id="89982-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-909">Product 1</span></span></td>
<td><span data-ttu-id="89982-910">10001</span><span class="sxs-lookup"><span data-stu-id="89982-910">10001</span></span></td>
<td><span data-ttu-id="89982-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-911">Electricity</span></span></td>
<td><span data-ttu-id="89982-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-912">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-913">241.05</span><span class="sxs-lookup"><span data-stu-id="89982-913">241.05</span></span></td>
<td><span data-ttu-id="89982-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-915">Prod 2</span></span></td>
<td><span data-ttu-id="89982-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-916">Product 2</span></span></td>
<td><span data-ttu-id="89982-917">10001</span><span class="sxs-lookup"><span data-stu-id="89982-917">10001</span></span></td>
<td><span data-ttu-id="89982-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-918">Electricity</span></span></td>
<td><span data-ttu-id="89982-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-919">Fixed cost</span></span></td>
<td><span data-ttu-id="89982-920">45.20</span><span class="sxs-lookup"><span data-stu-id="89982-920">45.20</span></span></td>
<td><span data-ttu-id="89982-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-922">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-922">CC003</span></span></td>
<td><span data-ttu-id="89982-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="89982-923">Assembly</span></span></td>
<td><span data-ttu-id="89982-924">10001</span><span class="sxs-lookup"><span data-stu-id="89982-924">10001</span></span></td>
<td><span data-ttu-id="89982-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-925">Electricity</span></span></td>
<td><span data-ttu-id="89982-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-926">Variable cost</span></span></td>
<td><span data-ttu-id="89982-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="89982-927">-2,977.17</span></span></td>
<td><span data-ttu-id="89982-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-929">Prod 1</span></span></td>
<td><span data-ttu-id="89982-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="89982-930">Product 1</span></span></td>
<td><span data-ttu-id="89982-931">10001</span><span class="sxs-lookup"><span data-stu-id="89982-931">10001</span></span></td>
<td><span data-ttu-id="89982-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-932">Electricity</span></span></td>
<td><span data-ttu-id="89982-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-933">Variable cost</span></span></td>
<td><span data-ttu-id="89982-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="89982-934">2,507.09</span></span></td>
<td><span data-ttu-id="89982-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="89982-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-936">Prod 2</span></span></td>
<td><span data-ttu-id="89982-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="89982-937">Product 2</span></span></td>
<td><span data-ttu-id="89982-938">10001</span><span class="sxs-lookup"><span data-stu-id="89982-938">10001</span></span></td>
<td><span data-ttu-id="89982-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="89982-939">Electricity</span></span></td>
<td><span data-ttu-id="89982-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-940">Variable cost</span></span></td>
<td><span data-ttu-id="89982-941">470.08</span><span class="sxs-lookup"><span data-stu-id="89982-941">470.08</span></span></td>
<td><span data-ttu-id="89982-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="89982-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="89982-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="89982-943">Conclusion</span></span>
<span data-ttu-id="89982-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="89982-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="89982-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="89982-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="89982-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="89982-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="89982-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="89982-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="89982-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="89982-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="89982-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="89982-950">Razem</span><span class="sxs-lookup"><span data-stu-id="89982-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="89982-951">CC099</span><span class="sxs-lookup"><span data-stu-id="89982-951">CC099</span></span></th>
<th><span data-ttu-id="89982-952">CC001</span><span class="sxs-lookup"><span data-stu-id="89982-952">CC001</span></span></th>
<th><span data-ttu-id="89982-953">CC002</span><span class="sxs-lookup"><span data-stu-id="89982-953">CC002</span></span></th>
<th><span data-ttu-id="89982-954">CC003</span><span class="sxs-lookup"><span data-stu-id="89982-954">CC003</span></span></th>
<th><span data-ttu-id="89982-955">CC004</span><span class="sxs-lookup"><span data-stu-id="89982-955">CC004</span></span></th>
<th><span data-ttu-id="89982-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="89982-956">Proj 1</span></span></th>
<th><span data-ttu-id="89982-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="89982-957">Proj 2</span></span></th>
<th><span data-ttu-id="89982-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="89982-958">Prod 1</span></span></th>
<th><span data-ttu-id="89982-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="89982-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="89982-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="89982-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="89982-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="89982-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="89982-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="89982-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="89982-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="89982-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="89982-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="89982-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="89982-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="89982-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="89982-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="89982-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-971">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="89982-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="89982-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-973">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-974">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-975">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-976">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-977">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="89982-978">776.36</span><span class="sxs-lookup"><span data-stu-id="89982-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-979">223.64</span><span class="sxs-lookup"><span data-stu-id="89982-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="89982-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="89982-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="89982-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-982">000</span><span class="sxs-lookup"><span data-stu-id="89982-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-983">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-984">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-985">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-986">0,00</span><span class="sxs-lookup"><span data-stu-id="89982-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-987">30.00</span><span class="sxs-lookup"><span data-stu-id="89982-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-988">10,00</span><span class="sxs-lookup"><span data-stu-id="89982-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="89982-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="89982-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="89982-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="89982-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="89982-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="89982-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="89982-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="89982-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="89982-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="89982-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="89982-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="89982-996">Aby uzyskać więcej informacji, zobacz [Akumulacja kosztów](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="89982-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



