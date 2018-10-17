---
title: Obliczenie narzutu
description: "W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych."
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 12ae99c15bafcd9cc08b30903fe3f251f446b17d
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.contentlocale: pl-pl
ms.lasthandoff: 10/05/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="9c0c4-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c0c4-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="9c0c4-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-105">Term definition</span></span>
---------------

<span data-ttu-id="9c0c4-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="9c0c4-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="9c0c4-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="9c0c4-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="9c0c4-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="9c0c4-109">Rent</span></span>
-   <span data-ttu-id="9c0c4-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-110">Electricity</span></span>
-   <span data-ttu-id="9c0c4-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="9c0c4-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="9c0c4-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="9c0c4-112">Overhead calculation overview</span></span>
<span data-ttu-id="9c0c4-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="9c0c4-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="9c0c4-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="9c0c4-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="9c0c4-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="9c0c4-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="9c0c4-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="9c0c4-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="9c0c4-119">Version type</span></span>
-   <span data-ttu-id="9c0c4-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="9c0c4-120">Date and time</span></span>
-   <span data-ttu-id="9c0c4-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="9c0c4-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="9c0c4-122">Fiscal year</span></span>
-   <span data-ttu-id="9c0c4-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="9c0c4-123">Fiscal period</span></span>

<span data-ttu-id="9c0c4-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="9c0c4-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="9c0c4-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="9c0c4-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="9c0c4-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="9c0c4-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="9c0c4-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="9c0c4-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="9c0c4-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="9c0c4-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="9c0c4-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="9c0c4-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="9c0c4-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="9c0c4-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="9c0c4-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9c0c4-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="9c0c4-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="9c0c4-140">Main account</span></span></th>
<th><span data-ttu-id="9c0c4-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="9c0c4-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-143">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-143">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-144">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-145">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-145">10001</span></span></td>
<td><span data-ttu-id="9c0c4-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-146">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="9c0c4-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="9c0c4-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="9c0c4-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="9c0c4-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-151">Define the cost behavior rule</span></span>

<span data-ttu-id="9c0c4-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="9c0c4-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="9c0c4-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="9c0c4-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="9c0c4-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="9c0c4-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="9c0c4-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="9c0c4-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="9c0c4-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9c0c4-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-160">Journal</span></span></th>
<th><span data-ttu-id="9c0c4-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="9c0c4-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="9c0c4-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="9c0c4-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="9c0c4-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="9c0c4-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-164">00001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-164">00001</span></span></td>
<td><span data-ttu-id="9c0c4-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="9c0c4-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-166">Fiscal</span></span></td>
<td><span data-ttu-id="9c0c4-167">2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-167">2017</span></span></td>
<td><span data-ttu-id="9c0c4-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-168">Period 1</span></span></td>
<td><span data-ttu-id="9c0c4-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="9c0c4-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9c0c4-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="9c0c4-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-173">Cost element</span></span></th>
<th><span data-ttu-id="9c0c4-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-174">Cost behavior</span></span></th>
<th><span data-ttu-id="9c0c4-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-177">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-177">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-178">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-179">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-179">10001</span></span></td>
<td><span data-ttu-id="9c0c4-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-180">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="9c0c4-181">Unclassified</span></span></td>
<td><span data-ttu-id="9c0c4-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="9c0c4-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-185">Cost element</span></span></th>
<th><span data-ttu-id="9c0c4-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-186">Cost behavior</span></span></th>
<th><span data-ttu-id="9c0c4-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-187">Amount</span></span></th>
<th><span data-ttu-id="9c0c4-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="9c0c4-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-189">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-189">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-190">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-191">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-191">10001</span></span></td>
<td><span data-ttu-id="9c0c4-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-192">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="9c0c4-193">Unclassified</span></span></td>
<td><span data-ttu-id="9c0c4-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-194">10,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-196">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-196">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-197">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-198">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-198">10001</span></span></td>
<td><span data-ttu-id="9c0c4-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-199">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="9c0c4-200">Unclassified</span></span></td>
<td><span data-ttu-id="9c0c4-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-201">-10,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-203">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-203">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-204">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-205">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-205">10001</span></span></td>
<td><span data-ttu-id="9c0c4-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-206">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-207">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-208">1,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-210">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-210">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-211">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-212">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-212">10001</span></span></td>
<td><span data-ttu-id="9c0c4-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-213">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-214">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-215">9,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-217">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="9c0c4-218">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="9c0c4-219">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="9c0c4-220">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="9c0c4-221">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-221">Define the cost distribution rule</span></span>

<span data-ttu-id="9c0c4-222">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="9c0c4-223">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="9c0c4-224">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="9c0c4-225">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="9c0c4-226">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="9c0c4-227">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-228">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-228">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-229">kWh</span><span class="sxs-lookup"><span data-stu-id="9c0c4-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-230">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-230">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-231">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-231">HR</span></span></td>
<td><span data-ttu-id="9c0c4-232">1 000</span><span class="sxs-lookup"><span data-stu-id="9c0c4-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-233">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-233">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-234">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-234">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-235">6,000</span><span class="sxs-lookup"><span data-stu-id="9c0c4-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-236">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-236">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-237">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-237">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-238">0</span><span class="sxs-lookup"><span data-stu-id="9c0c4-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-239">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-240">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-240">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-241">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-241">Magnitude</span></span></th>
<th><span data-ttu-id="9c0c4-242">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="9c0c4-242">Allocation factor</span></span></th>
<th><span data-ttu-id="9c0c4-243">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-244">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-244">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-245">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-245">HR</span></span></td>
<td><span data-ttu-id="9c0c4-246">1 000</span><span class="sxs-lookup"><span data-stu-id="9c0c4-246">1,000</span></span></td>
<td><span data-ttu-id="9c0c4-247">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="9c0c4-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-249">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-249">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-250">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-250">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-251">6,000</span><span class="sxs-lookup"><span data-stu-id="9c0c4-251">6,000</span></span></td>
<td><span data-ttu-id="9c0c4-252">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="9c0c4-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-254">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-254">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-255">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-255">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-256">0</span><span class="sxs-lookup"><span data-stu-id="9c0c4-256">0</span></span></td>
<td><span data-ttu-id="9c0c4-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-258">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-259">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="9c0c4-260">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-261">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-261">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-262">Wzór</span><span class="sxs-lookup"><span data-stu-id="9c0c4-262">Formula</span></span></th>
<th><span data-ttu-id="9c0c4-263">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-263">Magnitude</span></span></th>
<th><span data-ttu-id="9c0c4-264">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="9c0c4-264">Allocation factor</span></span></th>
<th><span data-ttu-id="9c0c4-265">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-266">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-266">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-267">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-267">HR</span></span></td>
<td><span data-ttu-id="9c0c4-268">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="9c0c4-269">1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-269">1</span></span></td>
<td><span data-ttu-id="9c0c4-270">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-271">500.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-272">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-272">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-273">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-273">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-274">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="9c0c4-275">1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-275">1</span></span></td>
<td><span data-ttu-id="9c0c4-276">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-277">500.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-278">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-278">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-279">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-279">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="9c0c4-281">0</span><span class="sxs-lookup"><span data-stu-id="9c0c4-281">0</span></span></td>
<td><span data-ttu-id="9c0c4-282">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-283">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="9c0c4-284">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9c0c4-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-285">Journal</span></span></th>
<th><span data-ttu-id="9c0c4-286">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="9c0c4-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="9c0c4-287">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="9c0c4-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="9c0c4-288">Wersja</span><span class="sxs-lookup"><span data-stu-id="9c0c4-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-289">00002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-289">00002</span></span></td>
<td><span data-ttu-id="9c0c4-290">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="9c0c4-291">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-291">Fiscal</span></span></td>
<td><span data-ttu-id="9c0c4-292">2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-292">2017</span></span></td>
<td><span data-ttu-id="9c0c4-293">Okres 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-293">Period 1</span></span></td>
<td><span data-ttu-id="9c0c4-294">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="9c0c4-295">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9c0c4-296">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="9c0c4-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-297">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-298">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-298">Cost element</span></span></th>
<th><span data-ttu-id="9c0c4-299">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-299">Cost behavior</span></span></th>
<th><span data-ttu-id="9c0c4-300">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-301">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-302">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-302">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-303">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-303">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-304">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-304">10001</span></span></td>
<td><span data-ttu-id="9c0c4-305">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-305">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-306">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-306">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-308">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-309">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-309">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-310">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-310">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-311">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-311">10001</span></span></td>
<td><span data-ttu-id="9c0c4-312">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-312">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-313">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-313">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="9c0c4-315">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-316">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-317">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-317">Cost element</span></span></th>
<th><span data-ttu-id="9c0c4-318">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-318">Cost behavior</span></span></th>
<th><span data-ttu-id="9c0c4-319">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-319">Amount</span></span></th>
<th><span data-ttu-id="9c0c4-320">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="9c0c4-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-321">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-321">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-322">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-322">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-323">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-323">10001</span></span></td>
<td><span data-ttu-id="9c0c4-324">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-324">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-325">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-325">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-326">-1,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-327">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-328">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-328">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-329">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-329">HR</span></span></td>
<td><span data-ttu-id="9c0c4-330">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-330">10001</span></span></td>
<td><span data-ttu-id="9c0c4-331">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-331">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-332">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-332">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-333">500.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-333">500.00</span></span></td>
<td><span data-ttu-id="9c0c4-334">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-335">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-335">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-336">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-336">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-337">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-337">10001</span></span></td>
<td><span data-ttu-id="9c0c4-338">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-338">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-339">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-339">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-340">500.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-340">500.00</span></span></td>
<td><span data-ttu-id="9c0c4-341">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-342">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-342">CC099</span></span></td>
<td><span data-ttu-id="9c0c4-343">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-343">Default cost center</span></span></td>
<td><span data-ttu-id="9c0c4-344">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-344">10001</span></span></td>
<td><span data-ttu-id="9c0c4-345">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-345">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-346">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-346">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-347">-9000,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-347">-9,000.00</span></span></td>
<td><span data-ttu-id="9c0c4-348">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-349">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-349">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-350">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-350">HR</span></span></td>
<td><span data-ttu-id="9c0c4-351">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-351">10001</span></span></td>
<td><span data-ttu-id="9c0c4-352">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-352">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-353">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-353">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="9c0c4-354">1,285.71</span></span></td>
<td><span data-ttu-id="9c0c4-355">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-356">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-356">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-357">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-357">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-358">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-358">10001</span></span></td>
<td><span data-ttu-id="9c0c4-359">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-359">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-360">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-360">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="9c0c4-361">7,714.29</span></span></td>
<td><span data-ttu-id="9c0c4-362">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-363">Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="9c0c4-364">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="9c0c4-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="9c0c4-365">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="9c0c4-366">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="9c0c4-367">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="9c0c4-367">Define the overhead rate</span></span>

<span data-ttu-id="9c0c4-368">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="9c0c4-369">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-370">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-370">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-371">Godziny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-372">Proj 1</span></span></td>
<td><span data-ttu-id="9c0c4-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-373">Project 1</span></span></td>
<td><span data-ttu-id="9c0c4-374">3</span><span class="sxs-lookup"><span data-stu-id="9c0c4-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-375">Proj 2</span></span></td>
<td><span data-ttu-id="9c0c4-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-376">Project 2</span></span></td>
<td><span data-ttu-id="9c0c4-377">1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-378">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-379">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-379">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-380">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-380">Cost element</span></span></th>
<th><span data-ttu-id="9c0c4-381">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-381">Cost behavior</span></span></th>
<th><span data-ttu-id="9c0c4-382">Jednostki</span><span class="sxs-lookup"><span data-stu-id="9c0c4-382">Units</span></span></th>
<th><span data-ttu-id="9c0c4-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="9c0c4-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-384">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-384">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-385">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-385">HR</span></span></td>
<td><span data-ttu-id="9c0c4-386">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-386">10001</span></span></td>
<td><span data-ttu-id="9c0c4-387">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-387">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-388">1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-388">1</span></span></td>
<td><span data-ttu-id="9c0c4-389">10</span><span class="sxs-lookup"><span data-stu-id="9c0c4-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-390">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-391">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-391">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-392">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-392">Magnitude</span></span></th>
<th><span data-ttu-id="9c0c4-393">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-393">Cost element</span></span></th>
<th><span data-ttu-id="9c0c4-394">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="9c0c4-394">Allocation factor</span></span></th>
<th><span data-ttu-id="9c0c4-395">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-396">Proj 1</span></span></td>
<td><span data-ttu-id="9c0c4-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-397">Project 1</span></span></td>
<td><span data-ttu-id="9c0c4-398">3</span><span class="sxs-lookup"><span data-stu-id="9c0c4-398">3</span></span></td>
<td><span data-ttu-id="9c0c4-399">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-399">10001</span></span></td>
<td><span data-ttu-id="9c0c4-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="9c0c4-401">30.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-402">Proj 2</span></span></td>
<td><span data-ttu-id="9c0c4-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-403">Project 2</span></span></td>
<td><span data-ttu-id="9c0c4-404">1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-404">1</span></span></td>
<td><span data-ttu-id="9c0c4-405">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-405">10001</span></span></td>
<td><span data-ttu-id="9c0c4-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="9c0c4-407">10,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="9c0c4-408">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9c0c4-409">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-409">Journal</span></span></th>
<th><span data-ttu-id="9c0c4-410">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="9c0c4-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="9c0c4-411">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="9c0c4-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="9c0c4-412">Wersja</span><span class="sxs-lookup"><span data-stu-id="9c0c4-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-413">00003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-413">00003</span></span></td>
<td><span data-ttu-id="9c0c4-414">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="9c0c4-415">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-415">Fiscal</span></span></td>
<td><span data-ttu-id="9c0c4-416">2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-416">2017</span></span></td>
<td><span data-ttu-id="9c0c4-417">Okres 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-417">Period 1</span></span></td>
<td><span data-ttu-id="9c0c4-418">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="9c0c4-419">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9c0c4-420">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="9c0c4-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-421">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-421">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-422">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-423">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-424">Proj 1</span></span></td>
<td><span data-ttu-id="9c0c4-425">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="9c0c4-426">3,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-427">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-428">Proj 2</span></span></td>
<td><span data-ttu-id="9c0c4-429">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="9c0c4-430">1.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="9c0c4-431">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-432">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-433">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-433">Cost element</span></span></th>
<th><span data-ttu-id="9c0c4-434">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-434">Cost behavior</span></span></th>
<th><span data-ttu-id="9c0c4-435">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-435">Amount</span></span></th>
<th><span data-ttu-id="9c0c4-436">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="9c0c4-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-437">CC0001</span></span></td>
<td><span data-ttu-id="9c0c4-438">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-438">HR</span></span></td>
<td><span data-ttu-id="9c0c4-439">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-439">10001</span></span></td>
<td><span data-ttu-id="9c0c4-440">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-440">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-441">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-441">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-442">-30.00</span></span></td>
<td><span data-ttu-id="9c0c4-443">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-444">Proj 1</span></span></td>
<td><span data-ttu-id="9c0c4-445">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="9c0c4-446">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-446">10001</span></span></td>
<td><span data-ttu-id="9c0c4-447">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-447">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-448">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-448">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-449">30.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-449">30.00</span></span></td>
<td><span data-ttu-id="9c0c4-450">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-451">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-451">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-452">HR</span></span></td>
<td><span data-ttu-id="9c0c4-453">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-453">10001</span></span></td>
<td><span data-ttu-id="9c0c4-454">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-454">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-455">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-455">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-456">-10.00</span></span></td>
<td><span data-ttu-id="9c0c4-457">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-458">Proj 2</span></span></td>
<td><span data-ttu-id="9c0c4-459">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="9c0c4-460">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-460">10001</span></span></td>
<td><span data-ttu-id="9c0c4-461">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-461">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-462">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-462">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-463">10,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-463">10.00</span></span></td>
<td><span data-ttu-id="9c0c4-464">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-465">Aby uzyskać więcej informacji, zobacz [Obliczanie kosztów ogólnych](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="9c0c4-466">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="9c0c4-467">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="9c0c4-468">Program Finance and Operations obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="9c0c4-469">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="9c0c4-470">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="9c0c4-471">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="9c0c4-472">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="9c0c4-473">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="9c0c4-474">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="9c0c4-475">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-475">Define the cost allocation</span></span>

<span data-ttu-id="9c0c4-476">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="9c0c4-477">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="9c0c4-478">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-479">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-479">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-480">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="9c0c4-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-481">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-481">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-482">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-482">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-483">35</span><span class="sxs-lookup"><span data-stu-id="9c0c4-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-484">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-484">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-485">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-485">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-486">55</span><span class="sxs-lookup"><span data-stu-id="9c0c4-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-487">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-487">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-488">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-488">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-489">10</span><span class="sxs-lookup"><span data-stu-id="9c0c4-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-490">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="9c0c4-491">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-492">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-492">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-493">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="9c0c4-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-494">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-494">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-495">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-495">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-496">65</span><span class="sxs-lookup"><span data-stu-id="9c0c4-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-497">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-497">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-498">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-498">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-499">35</span><span class="sxs-lookup"><span data-stu-id="9c0c4-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-500">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="9c0c4-501">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-502">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-502">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-503">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-504">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-505">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-506">60</span><span class="sxs-lookup"><span data-stu-id="9c0c4-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-507">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-508">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-509">20</span><span class="sxs-lookup"><span data-stu-id="9c0c4-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-510">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="9c0c4-511">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-512">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-512">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-513">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-514">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-515">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-516">80</span><span class="sxs-lookup"><span data-stu-id="9c0c4-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-517">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-518">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-519">15</span><span class="sxs-lookup"><span data-stu-id="9c0c4-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="9c0c4-520">W programie Finance and Operations miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="9c0c4-521">Więcej informacji zawiera temat [Szablon dostawcy miar statystycznych](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="9c0c4-522">W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-523">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-523">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-524">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-524">Magnitude</span></span></th>
<th><span data-ttu-id="9c0c4-525">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="9c0c4-525">Allocation factor</span></span></th>
<th><span data-ttu-id="9c0c4-526">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-526">Amount</span></span></th>
<th><span data-ttu-id="9c0c4-527">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-528">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-528">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-529">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-529">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-530">35</span><span class="sxs-lookup"><span data-stu-id="9c0c4-530">35</span></span></td>
<td><span data-ttu-id="9c0c4-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="9c0c4-532">175.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-532">175.00</span></span></td>
<td><span data-ttu-id="9c0c4-533">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-534">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-534">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-535">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-535">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-536">55</span><span class="sxs-lookup"><span data-stu-id="9c0c4-536">55</span></span></td>
<td><span data-ttu-id="9c0c4-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="9c0c4-538">275.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-538">275.00</span></span></td>
<td><span data-ttu-id="9c0c4-539">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-540">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-540">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-541">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-541">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-542">10</span><span class="sxs-lookup"><span data-stu-id="9c0c4-542">10</span></span></td>
<td><span data-ttu-id="9c0c4-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="9c0c4-544">50,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-544">50.00</span></span></td>
<td><span data-ttu-id="9c0c4-545">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-546">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-546">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-547">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-547">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-548">35</span><span class="sxs-lookup"><span data-stu-id="9c0c4-548">35</span></span></td>
<td><span data-ttu-id="9c0c4-549">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="9c0c4-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="9c0c4-550">436.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-550">436.00</span></span></td>
<td><span data-ttu-id="9c0c4-551">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-552">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-552">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-553">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-553">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-554">55</span><span class="sxs-lookup"><span data-stu-id="9c0c4-554">55</span></span></td>
<td><span data-ttu-id="9c0c4-555">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="9c0c4-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="9c0c4-556">685.14</span><span class="sxs-lookup"><span data-stu-id="9c0c4-556">685.14</span></span></td>
<td><span data-ttu-id="9c0c4-557">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-558">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-558">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-559">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-559">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-560">10</span><span class="sxs-lookup"><span data-stu-id="9c0c4-560">10</span></span></td>
<td><span data-ttu-id="9c0c4-561">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="9c0c4-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="9c0c4-562">124.57</span><span class="sxs-lookup"><span data-stu-id="9c0c4-562">124.57</span></span></td>
<td><span data-ttu-id="9c0c4-563">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-564">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-565">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-565">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-566">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-566">Magnitude</span></span></th>
<th><span data-ttu-id="9c0c4-567">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="9c0c4-567">Allocation factor</span></span></th>
<th><span data-ttu-id="9c0c4-568">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-568">Amount</span></span></th>
<th><span data-ttu-id="9c0c4-569">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-570">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-570">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-571">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-571">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-572">65</span><span class="sxs-lookup"><span data-stu-id="9c0c4-572">65</span></span></td>
<td><span data-ttu-id="9c0c4-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="9c0c4-574">438.75</span><span class="sxs-lookup"><span data-stu-id="9c0c4-574">438.75</span></span></td>
<td><span data-ttu-id="9c0c4-575">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-576">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-576">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-577">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-577">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-578">35</span><span class="sxs-lookup"><span data-stu-id="9c0c4-578">35</span></span></td>
<td><span data-ttu-id="9c0c4-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="9c0c4-580">236.25</span><span class="sxs-lookup"><span data-stu-id="9c0c4-580">236.25</span></span></td>
<td><span data-ttu-id="9c0c4-581">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-582">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-582">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-583">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-583">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-584">65</span><span class="sxs-lookup"><span data-stu-id="9c0c4-584">65</span></span></td>
<td><span data-ttu-id="9c0c4-585">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="9c0c4-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="9c0c4-586">5,297.69</span></span></td>
<td><span data-ttu-id="9c0c4-587">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-588">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-588">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-589">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-589">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-590">35</span><span class="sxs-lookup"><span data-stu-id="9c0c4-590">35</span></span></td>
<td><span data-ttu-id="9c0c4-591">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="9c0c4-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="9c0c4-592">2,852.60</span></span></td>
<td><span data-ttu-id="9c0c4-593">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-594">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-595">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-595">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-596">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-596">Magnitude</span></span></th>
<th><span data-ttu-id="9c0c4-597">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="9c0c4-597">Allocation factor</span></span></th>
<th><span data-ttu-id="9c0c4-598">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-598">Amount</span></span></th>
<th><span data-ttu-id="9c0c4-599">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-600">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-601">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-602">60</span><span class="sxs-lookup"><span data-stu-id="9c0c4-602">60</span></span></td>
<td><span data-ttu-id="9c0c4-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="9c0c4-604">535.31</span><span class="sxs-lookup"><span data-stu-id="9c0c4-604">535.31</span></span></td>
<td><span data-ttu-id="9c0c4-605">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-606">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-607">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-608">20</span><span class="sxs-lookup"><span data-stu-id="9c0c4-608">20</span></span></td>
<td><span data-ttu-id="9c0c4-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="9c0c4-610">178.44</span><span class="sxs-lookup"><span data-stu-id="9c0c4-610">178.44</span></span></td>
<td><span data-ttu-id="9c0c4-611">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-612">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-613">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-614">60</span><span class="sxs-lookup"><span data-stu-id="9c0c4-614">60</span></span></td>
<td><span data-ttu-id="9c0c4-615">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="9c0c4-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="9c0c4-616">4,487.12</span></span></td>
<td><span data-ttu-id="9c0c4-617">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-618">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-619">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-620">20</span><span class="sxs-lookup"><span data-stu-id="9c0c4-620">20</span></span></td>
<td><span data-ttu-id="9c0c4-621">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="9c0c4-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="9c0c4-622">1,495.71</span></span></td>
<td><span data-ttu-id="9c0c4-623">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9c0c4-624">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-625">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-625">Cost object</span></span></th>
<th><span data-ttu-id="9c0c4-626">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-626">Magnitude</span></span></th>
<th><span data-ttu-id="9c0c4-627">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="9c0c4-627">Allocation factor</span></span></th>
<th><span data-ttu-id="9c0c4-628">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-628">Amount</span></span></th>
<th><span data-ttu-id="9c0c4-629">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-630">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-631">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-632">80</span><span class="sxs-lookup"><span data-stu-id="9c0c4-632">80</span></span></td>
<td><span data-ttu-id="9c0c4-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="9c0c4-634">241.05</span><span class="sxs-lookup"><span data-stu-id="9c0c4-634">241.05</span></span></td>
<td><span data-ttu-id="9c0c4-635">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-636">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-637">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-638">15</span><span class="sxs-lookup"><span data-stu-id="9c0c4-638">15</span></span></td>
<td><span data-ttu-id="9c0c4-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="9c0c4-640">45.20</span><span class="sxs-lookup"><span data-stu-id="9c0c4-640">45.20</span></span></td>
<td><span data-ttu-id="9c0c4-641">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-642">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-643">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-644">80</span><span class="sxs-lookup"><span data-stu-id="9c0c4-644">80</span></span></td>
<td><span data-ttu-id="9c0c4-645">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="9c0c4-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="9c0c4-646">2,507.09</span></span></td>
<td><span data-ttu-id="9c0c4-647">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-648">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-649">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-650">15</span><span class="sxs-lookup"><span data-stu-id="9c0c4-650">15</span></span></td>
<td><span data-ttu-id="9c0c4-651">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="9c0c4-652">470.08</span><span class="sxs-lookup"><span data-stu-id="9c0c4-652">470.08</span></span></td>
<td><span data-ttu-id="9c0c4-653">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="9c0c4-654">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="9c0c4-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9c0c4-655">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-655">Journal</span></span></th>
<th><span data-ttu-id="9c0c4-656">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="9c0c4-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="9c0c4-657">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="9c0c4-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="9c0c4-658">Wersja</span><span class="sxs-lookup"><span data-stu-id="9c0c4-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-659">00004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-659">00004</span></span></td>
<td><span data-ttu-id="9c0c4-660">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="9c0c4-661">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-661">Fiscal</span></span></td>
<td><span data-ttu-id="9c0c4-662">2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-662">2017</span></span></td>
<td><span data-ttu-id="9c0c4-663">Okres 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-663">Period 1</span></span></td>
<td><span data-ttu-id="9c0c4-664">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="9c0c4-665">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="9c0c4-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9c0c4-666">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="9c0c4-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-667">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-668">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-668">Cost element</span></span></th>
<th><span data-ttu-id="9c0c4-669">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-669">Cost behavior</span></span></th>
<th><span data-ttu-id="9c0c4-670">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-671">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-672">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-672">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-673">HR</span></span></td>
<td><span data-ttu-id="9c0c4-674">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-674">10001</span></span></td>
<td><span data-ttu-id="9c0c4-675">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-675">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-676">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-676">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-677">500.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-678">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-679">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-679">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-680">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-680">HR</span></span></td>
<td><span data-ttu-id="9c0c4-681">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-681">10001</span></span></td>
<td><span data-ttu-id="9c0c4-682">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-682">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-683">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-683">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="9c0c4-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-685">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-686">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-686">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-687">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-687">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-688">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-688">10001</span></span></td>
<td><span data-ttu-id="9c0c4-689">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-689">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-690">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-690">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-691">675.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-692">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-693">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-693">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-694">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-694">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-695">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-695">10001</span></span></td>
<td><span data-ttu-id="9c0c4-696">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-696">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-697">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-697">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="9c0c4-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-699">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-700">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-700">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-701">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-701">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-702">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-702">10001</span></span></td>
<td><span data-ttu-id="9c0c4-703">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-703">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-704">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-704">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-705">713.75</span><span class="sxs-lookup"><span data-stu-id="9c0c4-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-706">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-707">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-707">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-708">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-708">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-709">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-709">10001</span></span></td>
<td><span data-ttu-id="9c0c4-710">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-710">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-711">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-711">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="9c0c4-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-713">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-714">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-714">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-715">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-715">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-716">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-716">10001</span></span></td>
<td><span data-ttu-id="9c0c4-717">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-717">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-718">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-718">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-719">286.25</span><span class="sxs-lookup"><span data-stu-id="9c0c4-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-720">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-721">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-721">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-722">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-722">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-723">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-723">10001</span></span></td>
<td><span data-ttu-id="9c0c4-724">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-724">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-725">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-725">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="9c0c4-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-727">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-728">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-729">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-730">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-730">10001</span></span></td>
<td><span data-ttu-id="9c0c4-731">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-731">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-732">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-732">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-733">776.36</span><span class="sxs-lookup"><span data-stu-id="9c0c4-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-734">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-735">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-736">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-737">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-737">10001</span></span></td>
<td><span data-ttu-id="9c0c4-738">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-738">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-739">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-739">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="9c0c4-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-741">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-742">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-743">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-744">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-744">10001</span></span></td>
<td><span data-ttu-id="9c0c4-745">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-745">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-746">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-746">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-747">223.64</span><span class="sxs-lookup"><span data-stu-id="9c0c4-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-748">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="9c0c4-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-749">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-750">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-751">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-751">10001</span></span></td>
<td><span data-ttu-id="9c0c4-752">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-752">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-753">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-753">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="9c0c4-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="9c0c4-755">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="9c0c4-756">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="9c0c4-757">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-757">Cost element</span></span></th>
<th><span data-ttu-id="9c0c4-758">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-758">Cost behavior</span></span></th>
<th><span data-ttu-id="9c0c4-759">Ilość</span><span class="sxs-lookup"><span data-stu-id="9c0c4-759">Amount</span></span></th>
<th><span data-ttu-id="9c0c4-760">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="9c0c4-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9c0c4-761">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-761">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-762">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-762">HR</span></span></td>
<td><span data-ttu-id="9c0c4-763">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-763">10001</span></span></td>
<td><span data-ttu-id="9c0c4-764">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-764">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-765">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-765">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-766">-500.00</span></span></td>
<td><span data-ttu-id="9c0c4-767">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-768">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-768">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-769">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-769">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-770">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-770">10001</span></span></td>
<td><span data-ttu-id="9c0c4-771">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-771">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-772">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-772">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-773">175.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-773">175.00</span></span></td>
<td><span data-ttu-id="9c0c4-774">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-775">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-775">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-776">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-776">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-777">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-777">10001</span></span></td>
<td><span data-ttu-id="9c0c4-778">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-778">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-779">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-779">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-780">275.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-780">275.00</span></span></td>
<td><span data-ttu-id="9c0c4-781">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-782">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-782">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-783">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-783">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-784">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-784">10001</span></span></td>
<td><span data-ttu-id="9c0c4-785">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-785">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-786">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-786">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-787">50,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-787">50,00</span></span></td>
<td><span data-ttu-id="9c0c4-788">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-789">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-789">CC001</span></span></td>
<td><span data-ttu-id="9c0c4-790">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-790">HR</span></span></td>
<td><span data-ttu-id="9c0c4-791">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-791">10001</span></span></td>
<td><span data-ttu-id="9c0c4-792">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-792">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-793">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-793">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-794">-1245,71</span><span class="sxs-lookup"><span data-stu-id="9c0c4-794">-1,245.71</span></span></td>
<td><span data-ttu-id="9c0c4-795">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-796">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-796">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-797">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-797">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-798">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-798">10001</span></span></td>
<td><span data-ttu-id="9c0c4-799">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-799">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-800">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-800">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-801">436.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-801">436.00</span></span></td>
<td><span data-ttu-id="9c0c4-802">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-803">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-803">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-804">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-804">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-805">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-805">10001</span></span></td>
<td><span data-ttu-id="9c0c4-806">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-806">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-807">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-807">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-808">685.14</span><span class="sxs-lookup"><span data-stu-id="9c0c4-808">685.14</span></span></td>
<td><span data-ttu-id="9c0c4-809">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-810">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-810">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-811">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-811">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-812">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-812">10001</span></span></td>
<td><span data-ttu-id="9c0c4-813">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-813">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-814">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-814">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-815">124.57</span><span class="sxs-lookup"><span data-stu-id="9c0c4-815">124.57</span></span></td>
<td><span data-ttu-id="9c0c4-816">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-817">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-817">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-818">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-818">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-819">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-819">10001</span></span></td>
<td><span data-ttu-id="9c0c4-820">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-820">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-821">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-821">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-822">-675.00</span></span></td>
<td><span data-ttu-id="9c0c4-823">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-824">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-824">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-825">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-825">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-826">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-826">10001</span></span></td>
<td><span data-ttu-id="9c0c4-827">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-827">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-828">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-828">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-829">438.75</span><span class="sxs-lookup"><span data-stu-id="9c0c4-829">438.75</span></span></td>
<td><span data-ttu-id="9c0c4-830">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-831">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-831">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-832">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-832">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-833">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-833">10001</span></span></td>
<td><span data-ttu-id="9c0c4-834">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-834">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-835">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-835">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-836">236.25</span><span class="sxs-lookup"><span data-stu-id="9c0c4-836">236.25</span></span></td>
<td><span data-ttu-id="9c0c4-837">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-838">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-838">CC002</span></span></td>
<td><span data-ttu-id="9c0c4-839">Finanse</span><span class="sxs-lookup"><span data-stu-id="9c0c4-839">Finance</span></span></td>
<td><span data-ttu-id="9c0c4-840">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-840">10001</span></span></td>
<td><span data-ttu-id="9c0c4-841">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-841">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-842">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-842">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-843">-8150,29</span><span class="sxs-lookup"><span data-stu-id="9c0c4-843">-8,150.29</span></span></td>
<td><span data-ttu-id="9c0c4-844">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-845">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-845">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-846">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-846">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-847">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-847">10001</span></span></td>
<td><span data-ttu-id="9c0c4-848">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-848">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-849">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-849">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="9c0c4-850">5,297.69</span></span></td>
<td><span data-ttu-id="9c0c4-851">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-852">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-852">CC004</span></span></td>
<td><span data-ttu-id="9c0c4-853">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="9c0c4-853">Packaging</span></span></td>
<td><span data-ttu-id="9c0c4-854">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-854">10001</span></span></td>
<td><span data-ttu-id="9c0c4-855">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-855">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-856">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-856">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="9c0c4-857">2,852.60</span></span></td>
<td><span data-ttu-id="9c0c4-858">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-859">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-859">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-860">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-860">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-861">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-861">10001</span></span></td>
<td><span data-ttu-id="9c0c4-862">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-862">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-863">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-863">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="9c0c4-864">-713.75</span></span></td>
<td><span data-ttu-id="9c0c4-865">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-866">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-867">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-868">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-868">10001</span></span></td>
<td><span data-ttu-id="9c0c4-869">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-869">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-870">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-870">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-871">535.31</span><span class="sxs-lookup"><span data-stu-id="9c0c4-871">535.31</span></span></td>
<td><span data-ttu-id="9c0c4-872">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-873">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-874">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-875">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-875">10001</span></span></td>
<td><span data-ttu-id="9c0c4-876">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-876">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-877">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-877">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-878">178.44</span><span class="sxs-lookup"><span data-stu-id="9c0c4-878">178.44</span></span></td>
<td><span data-ttu-id="9c0c4-879">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-880">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-880">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-881">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-881">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-882">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-882">10001</span></span></td>
<td><span data-ttu-id="9c0c4-883">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-883">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-884">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-884">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-885">-5982,83</span><span class="sxs-lookup"><span data-stu-id="9c0c4-885">-5,982.83</span></span></td>
<td><span data-ttu-id="9c0c4-886">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-887">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-888">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-889">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-889">10001</span></span></td>
<td><span data-ttu-id="9c0c4-890">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-890">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-891">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-891">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="9c0c4-892">4,487.12</span></span></td>
<td><span data-ttu-id="9c0c4-893">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-894">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-895">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-896">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-896">10001</span></span></td>
<td><span data-ttu-id="9c0c4-897">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-897">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-898">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-898">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="9c0c4-899">1,495.71</span></span></td>
<td><span data-ttu-id="9c0c4-900">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-901">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-901">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-902">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-902">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-903">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-903">10001</span></span></td>
<td><span data-ttu-id="9c0c4-904">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-904">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-905">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-905">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="9c0c4-906">-286.25</span></span></td>
<td><span data-ttu-id="9c0c4-907">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-908">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-909">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-910">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-910">10001</span></span></td>
<td><span data-ttu-id="9c0c4-911">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-911">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-912">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-912">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-913">241.05</span><span class="sxs-lookup"><span data-stu-id="9c0c4-913">241.05</span></span></td>
<td><span data-ttu-id="9c0c4-914">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-915">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-916">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-917">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-917">10001</span></span></td>
<td><span data-ttu-id="9c0c4-918">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-918">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-919">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-919">Fixed cost</span></span></td>
<td><span data-ttu-id="9c0c4-920">45.20</span><span class="sxs-lookup"><span data-stu-id="9c0c4-920">45.20</span></span></td>
<td><span data-ttu-id="9c0c4-921">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-922">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-922">CC003</span></span></td>
<td><span data-ttu-id="9c0c4-923">Zestaw</span><span class="sxs-lookup"><span data-stu-id="9c0c4-923">Assembly</span></span></td>
<td><span data-ttu-id="9c0c4-924">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-924">10001</span></span></td>
<td><span data-ttu-id="9c0c4-925">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-925">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-926">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-926">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-927">-2977,17</span><span class="sxs-lookup"><span data-stu-id="9c0c4-927">-2,977.17</span></span></td>
<td><span data-ttu-id="9c0c4-928">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-929">Prod 1</span></span></td>
<td><span data-ttu-id="9c0c4-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-930">Product 1</span></span></td>
<td><span data-ttu-id="9c0c4-931">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-931">10001</span></span></td>
<td><span data-ttu-id="9c0c4-932">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-932">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-933">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-933">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="9c0c4-934">2,507.09</span></span></td>
<td><span data-ttu-id="9c0c4-935">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9c0c4-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-936">Prod 2</span></span></td>
<td><span data-ttu-id="9c0c4-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-937">Product 2</span></span></td>
<td><span data-ttu-id="9c0c4-938">10001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-938">10001</span></span></td>
<td><span data-ttu-id="9c0c4-939">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="9c0c4-939">Electricity</span></span></td>
<td><span data-ttu-id="9c0c4-940">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-940">Variable cost</span></span></td>
<td><span data-ttu-id="9c0c4-941">470.08</span><span class="sxs-lookup"><span data-stu-id="9c0c4-941">470.08</span></span></td>
<td><span data-ttu-id="9c0c4-942">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="9c0c4-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="9c0c4-943">Wniosek</span><span class="sxs-lookup"><span data-stu-id="9c0c4-943">Conclusion</span></span>
<span data-ttu-id="9c0c4-944">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="9c0c4-945">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="9c0c4-946">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="9c0c4-947">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="9c0c4-948">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="9c0c4-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="9c0c4-949">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="9c0c4-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="9c0c4-950">Razem</span><span class="sxs-lookup"><span data-stu-id="9c0c4-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="9c0c4-951">CC099</span><span class="sxs-lookup"><span data-stu-id="9c0c4-951">CC099</span></span></th>
<th><span data-ttu-id="9c0c4-952">CC001</span><span class="sxs-lookup"><span data-stu-id="9c0c4-952">CC001</span></span></th>
<th><span data-ttu-id="9c0c4-953">CC002</span><span class="sxs-lookup"><span data-stu-id="9c0c4-953">CC002</span></span></th>
<th><span data-ttu-id="9c0c4-954">CC003</span><span class="sxs-lookup"><span data-stu-id="9c0c4-954">CC003</span></span></th>
<th><span data-ttu-id="9c0c4-955">CC004</span><span class="sxs-lookup"><span data-stu-id="9c0c4-955">CC004</span></span></th>
<th><span data-ttu-id="9c0c4-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-956">Proj 1</span></span></th>
<th><span data-ttu-id="9c0c4-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-957">Proj 2</span></span></th>
<th><span data-ttu-id="9c0c4-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="9c0c4-958">Prod 1</span></span></th>
<th><span data-ttu-id="9c0c4-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="9c0c4-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="9c0c4-960">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="9c0c4-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="9c0c4-970">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="9c0c4-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-971">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="9c0c4-972">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="9c0c4-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-973">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-974">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-975">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-976">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-977">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-978">776.36</span><span class="sxs-lookup"><span data-stu-id="9c0c4-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-979">223.64</span><span class="sxs-lookup"><span data-stu-id="9c0c4-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="9c0c4-981">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="9c0c4-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-982">000</span><span class="sxs-lookup"><span data-stu-id="9c0c4-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-983">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-984">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-985">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-986">0,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-987">30.00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-988">10,00</span><span class="sxs-lookup"><span data-stu-id="9c0c4-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="9c0c4-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="9c0c4-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="9c0c4-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="9c0c4-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="9c0c4-992">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="9c0c4-993">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="9c0c4-994">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="9c0c4-995">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="9c0c4-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="9c0c4-996">Aby uzyskać więcej informacji, zobacz [Akumulacja kosztów](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="9c0c4-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>




