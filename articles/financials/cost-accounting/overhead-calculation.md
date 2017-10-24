---
title: Obliczenie narzutu
description: "W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 0ea6f7428cd5c7618d2d69f1fb66fd9539ad1073
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="overhead-calculation"></a><span data-ttu-id="4d9e0-103">Obliczenie narzutu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4d9e0-104">W tym temacie opisano typowe procesy służące obliczaniu i podzielaniu kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="4d9e0-105">Definicja terminu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-105">Term definition</span></span>
---------------

<span data-ttu-id="4d9e0-106">Koszty ogólne to koszty poniesione w celu prowadzenia firmy, których nie można bezpośrednio przypisać do żadnej konkretnej aktywności biznesowej, produktu ani usługi.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="4d9e0-107">Koszty ogólne zapewniają newralgiczne wsparcie działań generujących zysk.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="4d9e0-108">Oto kilka przykładów kosztów ogólnych:</span><span class="sxs-lookup"><span data-stu-id="4d9e0-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="4d9e0-109">Dzierżawa</span><span class="sxs-lookup"><span data-stu-id="4d9e0-109">Rent</span></span>
-   <span data-ttu-id="4d9e0-110">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-110">Electricity</span></span>
-   <span data-ttu-id="4d9e0-111">Wynagrodzenia administracyjne</span><span class="sxs-lookup"><span data-stu-id="4d9e0-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="4d9e0-112">Omówienie obliczania kosztów ogólnych</span><span class="sxs-lookup"><span data-stu-id="4d9e0-112">Overhead calculation overview</span></span>
<span data-ttu-id="4d9e0-113">W obliczaniu kosztów ogólnych następuje wykonanie zasad rachunku kosztów w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="4d9e0-114">Można uruchomić obliczanie kosztów ogólnych wiele razy dla tego samego okresu obrachunkowego, jeśli zmieniono zasady rachunku kosztów lub wykryto określone błędy.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="4d9e0-115">Każda sesja obliczania kosztów ogólnych jest zapisywana i otrzymuje unikatowy identyfikator wersji, który pozwala porównywać obliczenia w różnych wersjach.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="4d9e0-116">Wpisy kosztów generowane przez obliczanie kosztów ogólnych otrzymują datę księgowania.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="4d9e0-117">Ta data księgowania odpowiada dacie zakończenia okresu obrachunkowego użytego w obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="4d9e0-118">Unikatowy identyfikator wersji składa się z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="4d9e0-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="4d9e0-119">Typ wersji</span><span class="sxs-lookup"><span data-stu-id="4d9e0-119">Version type</span></span>
-   <span data-ttu-id="4d9e0-120">Data i godzina</span><span class="sxs-lookup"><span data-stu-id="4d9e0-120">Date and time</span></span>
-   <span data-ttu-id="4d9e0-121">Księga rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="4d9e0-122">Rok obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="4d9e0-122">Fiscal year</span></span>
-   <span data-ttu-id="4d9e0-123">Okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="4d9e0-123">Fiscal period</span></span>

<span data-ttu-id="4d9e0-124">Obliczanie kosztów ogólnych jest uruchamiane niezależnie od wersji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="4d9e0-125">W związku z tym można obliczyć wersję budżetową przed wersją rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="4d9e0-126">Obliczanie kosztów ogólnych składa się z czterech etapów, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="4d9e0-127">Na każdym etapie jest tworzony nagłówek arkusza z zapisami w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="4d9e0-128">Ten nagłówek arkusza przechowuje dane wejściowe dla każdego etapu obliczeń.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="4d9e0-129">Zasady i reguły są stosowane do każdego wiersza arkusza, a jako dane wyjściowe są generowane wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="4d9e0-130">Dlatego zawsze masz pełną identyfikację źródeł wyników obliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="4d9e0-131">[![Obliczanie kosztów ogólnych](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="4d9e0-132">Obliczanie i przypisywanie kosztów ogólnych energii elektrycznej</span><span class="sxs-lookup"><span data-stu-id="4d9e0-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="4d9e0-133">W rachunkowości finansowej niektóre koszty, takie jak energii elektrycznej, są rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="4d9e0-134">W związku z tym menedżerowie nie mają szczegółowego wglądu w te dane w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="4d9e0-135">Aby w module Rachunek kosztów zapewnić poprawne prezentowanie informacji kierownictwu we wszystkich jednostkach organizacyjnych i na wszystkich poziomach, koszty muszą przepływać przez jednostki organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="4d9e0-136">Ten przepływ musi się opierać na dokładnym rejestrze zużycia lub na uczciwej ocenie.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="4d9e0-137">W księdze głównej koszty energii elektrycznej mogą być księgowane w sposób pokazany w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4d9e0-138">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="4d9e0-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-139">Centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-140">Konto główne</span><span class="sxs-lookup"><span data-stu-id="4d9e0-140">Main account</span></span></th>
<th><span data-ttu-id="4d9e0-141">Kwota w walucie rozliczeniowej</span><span class="sxs-lookup"><span data-stu-id="4d9e0-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-142">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-143">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-143">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-144">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-144">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-145">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-145">10001</span></span></td>
<td><span data-ttu-id="4d9e0-146">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-146">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="4d9e0-148">Krok 1: Przetwarzanie obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="4d9e0-149">Domyślnie podczas importowania z danych źródłowych wpisy kosztów otrzymują kategorię zachowania kosztów **Niesklasyfikowane** w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="4d9e0-150">Stosując reguły zachowania kosztów, można zmienić klasyfikację wpisów kosztów na **Koszt stały** lub **Koszt zmienny**.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="4d9e0-151">Definiowanie reguły zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-151">Define the cost behavior rule</span></span>

<span data-ttu-id="4d9e0-152">W niektórych przypadkach część kosztu jest stałą opłatą, a pozostały koszt opiera się na zużyciu.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="4d9e0-153">Rachunki za energię elektryczną często pasują do tej definicji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="4d9e0-154">Po zapłaceniu określonej stałej opłaty płaci się za zużycie kilowatogodzin (kWh).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="4d9e0-155">Na przykład jeśli stała opłata wynosi 1000,00, oto jak jest definiowana reguła zachowania kosztów:</span><span class="sxs-lookup"><span data-stu-id="4d9e0-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="4d9e0-156">Kwota stała 1000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="4d9e0-157">0 &lt;= 1000,00 = Stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="4d9e0-158">1000,01 &lt; N = Zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="4d9e0-159">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4d9e0-160">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-160">Journal</span></span></th>
<th><span data-ttu-id="4d9e0-161">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="4d9e0-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4d9e0-162">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="4d9e0-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4d9e0-163">Wersja</span><span class="sxs-lookup"><span data-stu-id="4d9e0-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-164">00001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-164">00001</span></span></td>
<td><span data-ttu-id="4d9e0-165">Arkusz obliczania zachowania kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="4d9e0-166">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-166">Fiscal</span></span></td>
<td><span data-ttu-id="4d9e0-167">2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-167">2017</span></span></td>
<td><span data-ttu-id="4d9e0-168">Okres 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-168">Period 1</span></span></td>
<td><span data-ttu-id="4d9e0-169">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4d9e0-170">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4d9e0-171">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="4d9e0-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-172">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-173">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-173">Cost element</span></span></th>
<th><span data-ttu-id="4d9e0-174">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-174">Cost behavior</span></span></th>
<th><span data-ttu-id="4d9e0-175">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-176">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-177">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-177">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-178">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-178">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-179">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-179">10001</span></span></td>
<td><span data-ttu-id="4d9e0-180">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-180">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-181">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="4d9e0-181">Unclassified</span></span></td>
<td><span data-ttu-id="4d9e0-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4d9e0-183">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-184">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-185">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-185">Cost element</span></span></th>
<th><span data-ttu-id="4d9e0-186">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-186">Cost behavior</span></span></th>
<th><span data-ttu-id="4d9e0-187">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-187">Amount</span></span></th>
<th><span data-ttu-id="4d9e0-188">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="4d9e0-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-189">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-189">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-190">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-190">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-191">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-191">10001</span></span></td>
<td><span data-ttu-id="4d9e0-192">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-192">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-193">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="4d9e0-193">Unclassified</span></span></td>
<td><span data-ttu-id="4d9e0-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-194">10,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-195">3 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-196">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-196">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-197">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-197">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-198">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-198">10001</span></span></td>
<td><span data-ttu-id="4d9e0-199">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-199">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-200">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="4d9e0-200">Unclassified</span></span></td>
<td><span data-ttu-id="4d9e0-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-201">-10,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-202">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-203">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-203">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-204">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-204">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-205">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-205">10001</span></span></td>
<td><span data-ttu-id="4d9e0-206">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-206">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-207">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-207">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-208">1,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-209">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-210">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-210">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-211">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-211">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-212">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-212">10001</span></span></td>
<td><span data-ttu-id="4d9e0-213">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-213">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-214">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-214">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-215">9,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-216">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-217">Aby uzyskać szczegółowe informacje o zachowaniu kosztów, zobacz temat Zasada zachowania kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="4d9e0-218">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="4d9e0-219">Krok 2: Przetwarzanie obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="4d9e0-220">Dystrybucja kosztów umożliwia rozdzielenie kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="4d9e0-221">Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="4d9e0-222">Definiowanie reguły dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-222">Define the cost distribution rule</span></span>

<span data-ttu-id="4d9e0-223">W rachunkowości finansowej koszty energii elektrycznej są często rejestrowane jako ryczałt.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="4d9e0-224">W rachunku kosztów to podejście nie jest wystarczająco szczegółowe.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="4d9e0-225">Koszt zmienny powinien zostać rozpisany między poszczególne obiekty kosztów na podstawie najlepszej wiedzy.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="4d9e0-226">Najbardziej logiczną podstawą alokacji jest zużycie energii elektrycznej (kWh).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="4d9e0-227">Jest tworzony element członkowski wymiaru statystycznego o nazwie Energia elektryczna, po czym jest rejestrowane zużycie energii elektrycznej.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="4d9e0-228">Domyślnie wszystkie elementy członkowskie wymiarów statystycznych stają się dostępne jako podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-229">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-229">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-230">kWh</span><span class="sxs-lookup"><span data-stu-id="4d9e0-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-231">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-231">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-232">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-232">HR</span></span></td>
<td><span data-ttu-id="4d9e0-233">1 000</span><span class="sxs-lookup"><span data-stu-id="4d9e0-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-234">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-234">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-235">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-235">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-236">6,000</span><span class="sxs-lookup"><span data-stu-id="4d9e0-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-237">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-237">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-238">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-238">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-239">0</span><span class="sxs-lookup"><span data-stu-id="4d9e0-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-240">W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-241">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-241">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-242">Wartość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-242">Magnitude</span></span></th>
<th><span data-ttu-id="4d9e0-243">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="4d9e0-243">Allocation factor</span></span></th>
<th><span data-ttu-id="4d9e0-244">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-245">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-245">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-246">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-246">HR</span></span></td>
<td><span data-ttu-id="4d9e0-247">1 000</span><span class="sxs-lookup"><span data-stu-id="4d9e0-247">1,000</span></span></td>
<td><span data-ttu-id="4d9e0-248">(1000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="4d9e0-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-250">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-250">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-251">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-251">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-252">6,000</span><span class="sxs-lookup"><span data-stu-id="4d9e0-252">6,000</span></span></td>
<td><span data-ttu-id="4d9e0-253">(6000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="4d9e0-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-255">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-255">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-256">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-256">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-257">0</span><span class="sxs-lookup"><span data-stu-id="4d9e0-257">0</span></span></td>
<td><span data-ttu-id="4d9e0-258">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-259">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-260">Koszt stały powinien zostać rozdzielony równomiernie między poszczególne obiektów kosztów, które zużywały prąd.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="4d9e0-261">Ten wynik można uzyskać poprzez użycie elementu członkowskiego wymiaru statystycznego Energia elektryczna w podstawie alokacji w formule: (Energia elektryczna &gt; 0,00) W poniższej tabeli przedstawiono wynik, gdy zużycie energii elektrycznej jest stosowane jako podstawa alokacji dla kosztów zmiennych.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-262">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-262">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-263">Wzór</span><span class="sxs-lookup"><span data-stu-id="4d9e0-263">Formula</span></span></th>
<th><span data-ttu-id="4d9e0-264">Wartość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-264">Magnitude</span></span></th>
<th><span data-ttu-id="4d9e0-265">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="4d9e0-265">Allocation factor</span></span></th>
<th><span data-ttu-id="4d9e0-266">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-267">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-267">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-268">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-268">HR</span></span></td>
<td><span data-ttu-id="4d9e0-269">(1000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4d9e0-270">1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-270">1</span></span></td>
<td><span data-ttu-id="4d9e0-271">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-272">500.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-273">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-273">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-274">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-274">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-275">(6000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4d9e0-276">1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-276">1</span></span></td>
<td><span data-ttu-id="4d9e0-277">(1 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-278">500.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-279">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-279">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-280">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-280">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4d9e0-282">0</span><span class="sxs-lookup"><span data-stu-id="4d9e0-282">0</span></span></td>
<td><span data-ttu-id="4d9e0-283">(0 ÷ 2) × 1000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-284">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="4d9e0-285">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4d9e0-286">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-286">Journal</span></span></th>
<th><span data-ttu-id="4d9e0-287">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="4d9e0-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4d9e0-288">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="4d9e0-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4d9e0-289">Wersja</span><span class="sxs-lookup"><span data-stu-id="4d9e0-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-290">00002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-290">00002</span></span></td>
<td><span data-ttu-id="4d9e0-291">Arkusz obliczania dystrybucji kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="4d9e0-292">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-292">Fiscal</span></span></td>
<td><span data-ttu-id="4d9e0-293">2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-293">2017</span></span></td>
<td><span data-ttu-id="4d9e0-294">Okres 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-294">Period 1</span></span></td>
<td><span data-ttu-id="4d9e0-295">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4d9e0-296">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4d9e0-297">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="4d9e0-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-298">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-299">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-299">Cost element</span></span></th>
<th><span data-ttu-id="4d9e0-300">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-300">Cost behavior</span></span></th>
<th><span data-ttu-id="4d9e0-301">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-302">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-303">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-303">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-304">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-304">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-305">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-305">10001</span></span></td>
<td><span data-ttu-id="4d9e0-306">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-306">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-307">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-307">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-308">1000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-309">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-310">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-310">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-311">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-311">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-312">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-312">10001</span></span></td>
<td><span data-ttu-id="4d9e0-313">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-313">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-314">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-314">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4d9e0-316">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-317">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-318">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-318">Cost element</span></span></th>
<th><span data-ttu-id="4d9e0-319">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-319">Cost behavior</span></span></th>
<th><span data-ttu-id="4d9e0-320">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-320">Amount</span></span></th>
<th><span data-ttu-id="4d9e0-321">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="4d9e0-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-322">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-322">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-323">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-323">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-324">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-324">10001</span></span></td>
<td><span data-ttu-id="4d9e0-325">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-325">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-326">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-326">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-327">-1000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-327">-1,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-328">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-329">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-329">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-330">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-330">HR</span></span></td>
<td><span data-ttu-id="4d9e0-331">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-331">10001</span></span></td>
<td><span data-ttu-id="4d9e0-332">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-332">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-333">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-333">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-334">500.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-334">500.00</span></span></td>
<td><span data-ttu-id="4d9e0-335">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-336">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-336">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-337">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-337">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-338">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-338">10001</span></span></td>
<td><span data-ttu-id="4d9e0-339">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-339">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-340">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-340">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-341">500.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-341">500.00</span></span></td>
<td><span data-ttu-id="4d9e0-342">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-343">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-343">CC099</span></span></td>
<td><span data-ttu-id="4d9e0-344">Domyślne centrum kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-344">Default cost center</span></span></td>
<td><span data-ttu-id="4d9e0-345">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-345">10001</span></span></td>
<td><span data-ttu-id="4d9e0-346">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-346">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-347">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-347">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-348">-9000,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-348">-9,000.00</span></span></td>
<td><span data-ttu-id="4d9e0-349">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-350">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-350">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-351">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-351">HR</span></span></td>
<td><span data-ttu-id="4d9e0-352">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-352">10001</span></span></td>
<td><span data-ttu-id="4d9e0-353">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-353">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-354">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-354">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="4d9e0-355">1,285.71</span></span></td>
<td><span data-ttu-id="4d9e0-356">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-357">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-357">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-358">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-358">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-359">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-359">10001</span></span></td>
<td><span data-ttu-id="4d9e0-360">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-360">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-361">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-361">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="4d9e0-362">7,714.29</span></span></td>
<td><span data-ttu-id="4d9e0-363">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-364">Aby uzyskać szczegółowe informacje na temat dystrybucji kosztów i podstaw alokacji, zobacz tematy Zasada dystrybucji kosztów i Podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="4d9e0-365">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="4d9e0-366">Krok 3: Przetwarzanie obliczania stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="4d9e0-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="4d9e0-367">Stawka kosztu ogólnego jest używana do zapisywania w ciężar jednego lub więcej konkretnych obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="4d9e0-368">Obciążenie bazuje na wstępnie określonej stawce kosztu oraz na wartości względem przypisanej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="4d9e0-369">Definiowanie stawki kosztu ogólnego</span><span class="sxs-lookup"><span data-stu-id="4d9e0-369">Define the overhead rate</span></span>

<span data-ttu-id="4d9e0-370">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do zestawu projektów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="4d9e0-371">Jest tworzony element członkowski wymiaru statystycznego o nazwie Projekty kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-372">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-372">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-373">Godziny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-374">Proj 1</span></span></td>
<td><span data-ttu-id="4d9e0-375">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-375">Project 1</span></span></td>
<td><span data-ttu-id="4d9e0-376">3</span><span class="sxs-lookup"><span data-stu-id="4d9e0-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-377">Proj 2</span></span></td>
<td><span data-ttu-id="4d9e0-378">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-378">Project 2</span></span></td>
<td><span data-ttu-id="4d9e0-379">1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-380">Wstępnie zdefiniowano stawkę kosztu dla udziału w projektach kosztowych.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-381">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-381">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-382">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-382">Cost element</span></span></th>
<th><span data-ttu-id="4d9e0-383">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-383">Cost behavior</span></span></th>
<th><span data-ttu-id="4d9e0-384">Jednostki</span><span class="sxs-lookup"><span data-stu-id="4d9e0-384">Units</span></span></th>
<th><span data-ttu-id="4d9e0-385">Kurs</span><span class="sxs-lookup"><span data-stu-id="4d9e0-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-386">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-386">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-387">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-387">HR</span></span></td>
<td><span data-ttu-id="4d9e0-388">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-388">10001</span></span></td>
<td><span data-ttu-id="4d9e0-389">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-389">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-390">1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-390">1</span></span></td>
<td><span data-ttu-id="4d9e0-391">10</span><span class="sxs-lookup"><span data-stu-id="4d9e0-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-392">W poniższej tabeli przedstawiono wynik, gdy projekty kadrowe są stosowane jako podstawa alokacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-393">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-393">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-394">Wartość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-394">Magnitude</span></span></th>
<th><span data-ttu-id="4d9e0-395">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-395">Cost element</span></span></th>
<th><span data-ttu-id="4d9e0-396">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="4d9e0-396">Allocation factor</span></span></th>
<th><span data-ttu-id="4d9e0-397">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-398">Proj 1</span></span></td>
<td><span data-ttu-id="4d9e0-399">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-399">Project 1</span></span></td>
<td><span data-ttu-id="4d9e0-400">3</span><span class="sxs-lookup"><span data-stu-id="4d9e0-400">3</span></span></td>
<td><span data-ttu-id="4d9e0-401">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-401">10001</span></span></td>
<td><span data-ttu-id="4d9e0-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="4d9e0-403">30.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-404">Proj 2</span></span></td>
<td><span data-ttu-id="4d9e0-405">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-405">Project 2</span></span></td>
<td><span data-ttu-id="4d9e0-406">1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-406">1</span></span></td>
<td><span data-ttu-id="4d9e0-407">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-407">10001</span></span></td>
<td><span data-ttu-id="4d9e0-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="4d9e0-409">10,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="4d9e0-410">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4d9e0-411">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-411">Journal</span></span></th>
<th><span data-ttu-id="4d9e0-412">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="4d9e0-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4d9e0-413">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="4d9e0-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4d9e0-414">Wersja</span><span class="sxs-lookup"><span data-stu-id="4d9e0-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-415">00003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-415">00003</span></span></td>
<td><span data-ttu-id="4d9e0-416">Arkusz obliczania stawek narzutów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="4d9e0-417">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-417">Fiscal</span></span></td>
<td><span data-ttu-id="4d9e0-418">2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-418">2017</span></span></td>
<td><span data-ttu-id="4d9e0-419">Okres 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-419">Period 1</span></span></td>
<td><span data-ttu-id="4d9e0-420">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="4d9e0-421">Zapisy w arkuszu (wpisy w arkuszu do obliczania stawki kosztu ogólnego)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4d9e0-422">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="4d9e0-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-423">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-423">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-424">Wartość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-425">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-426">Proj 1</span></span></td>
<td><span data-ttu-id="4d9e0-427">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="4d9e0-428">3,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-429">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-430">Proj 2</span></span></td>
<td><span data-ttu-id="4d9e0-431">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="4d9e0-432">1.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4d9e0-433">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-434">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-435">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-435">Cost element</span></span></th>
<th><span data-ttu-id="4d9e0-436">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-436">Cost behavior</span></span></th>
<th><span data-ttu-id="4d9e0-437">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-437">Amount</span></span></th>
<th><span data-ttu-id="4d9e0-438">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="4d9e0-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-439">CC0001</span></span></td>
<td><span data-ttu-id="4d9e0-440">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-440">HR</span></span></td>
<td><span data-ttu-id="4d9e0-441">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-441">10001</span></span></td>
<td><span data-ttu-id="4d9e0-442">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-442">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-443">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-443">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-444">-30.00</span></span></td>
<td><span data-ttu-id="4d9e0-445">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-446">Proj 1</span></span></td>
<td><span data-ttu-id="4d9e0-447">Proj wewnętrzny 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="4d9e0-448">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-448">10001</span></span></td>
<td><span data-ttu-id="4d9e0-449">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-449">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-450">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-450">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-451">30.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-451">30.00</span></span></td>
<td><span data-ttu-id="4d9e0-452">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-453">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-453">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-454">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-454">HR</span></span></td>
<td><span data-ttu-id="4d9e0-455">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-455">10001</span></span></td>
<td><span data-ttu-id="4d9e0-456">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-456">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-457">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-457">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-458">-10.00</span></span></td>
<td><span data-ttu-id="4d9e0-459">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-460">Proj 2</span></span></td>
<td><span data-ttu-id="4d9e0-461">Proj wewnętrzny 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="4d9e0-462">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-462">10001</span></span></td>
<td><span data-ttu-id="4d9e0-463">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-463">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-464">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-464">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-465">10,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-465">10.00</span></span></td>
<td><span data-ttu-id="4d9e0-466">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-467">Aby uzyskać szczegółowe informacje o zasadach stawek kosztów ogólnych, zobacz tematy Zasada stawki kosztu ogólnego i Podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="4d9e0-468">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="4d9e0-469">Krok 4: Przetwarzanie obliczania alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="4d9e0-470">Alokacja jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="4d9e0-471">Program Finance and Operations obsługuje metody wzajemnej alokacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="4d9e0-472">W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="4d9e0-473">System automatycznie ustala kolejność, w jakiej ma zostać wykonana alokacja.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="4d9e0-474">Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="4d9e0-475">Są obsługiwane alokacje między wymiarami obiektów kosztów i ich elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="4d9e0-476">Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="4d9e0-477">[![Metoda wzajemna](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="4d9e0-478">Definiowanie alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-478">Define the cost allocation</span></span>

<span data-ttu-id="4d9e0-479">Poniżej przedstawiono prosty przykład wyjaśniający, jak można śledzić przepływ kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="4d9e0-480">Obiekt kosztów CC001 Zasoby ludzkie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="4d9e0-481">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi kadrowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-482">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-482">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-483">Usługi kadrowe</span><span class="sxs-lookup"><span data-stu-id="4d9e0-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-484">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-484">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-485">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-485">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-486">35</span><span class="sxs-lookup"><span data-stu-id="4d9e0-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-487">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-487">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-488">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-488">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-489">55</span><span class="sxs-lookup"><span data-stu-id="4d9e0-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-490">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-490">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-491">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-491">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-492">10</span><span class="sxs-lookup"><span data-stu-id="4d9e0-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-493">Obiekt kosztów CC002 Finanse wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="4d9e0-494">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi finansowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-495">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-495">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-496">Usługi finansowe</span><span class="sxs-lookup"><span data-stu-id="4d9e0-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-497">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-497">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-498">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-498">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-499">65</span><span class="sxs-lookup"><span data-stu-id="4d9e0-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-500">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-500">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-501">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-501">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-502">35</span><span class="sxs-lookup"><span data-stu-id="4d9e0-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-503">Obiekt kosztów CC003 Montaż wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="4d9e0-504">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi montażowe w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-505">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-505">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-506">Usługi montażowe (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-507">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-508">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-508">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-509">60</span><span class="sxs-lookup"><span data-stu-id="4d9e0-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-510">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-511">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-511">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-512">20</span><span class="sxs-lookup"><span data-stu-id="4d9e0-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-513">Obiekt kosztów CC004 Pakowanie wnosi wkład do kilku obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="4d9e0-514">Jest tworzony element członkowski wymiaru statystycznego o nazwie Usługi pakowania w celu mierzenia zużywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-515">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-515">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-516">Usługi pakowania (w godzinach)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-517">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-518">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-518">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-519">80</span><span class="sxs-lookup"><span data-stu-id="4d9e0-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-520">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-521">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-521">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-522">15</span><span class="sxs-lookup"><span data-stu-id="4d9e0-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-523">**Uwaga:** W programie Finance and Operations miary statystyczne, takiej jak liczba godzin produkcji zużywana przez produkt, mogą być wyprowadzane z danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="4d9e0-524">Aby uzyskać bardziej szczegółowe informacje o dostawcach miar statystycznych, zobacz temat Szablon dostawcy miar statystycznych</span><span class="sxs-lookup"><span data-stu-id="4d9e0-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="4d9e0-525">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy). W poniższej tabeli przedstawiono wynik, gdy usługi kadrowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-526">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-526">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-527">Wartość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-527">Magnitude</span></span></th>
<th><span data-ttu-id="4d9e0-528">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="4d9e0-528">Allocation factor</span></span></th>
<th><span data-ttu-id="4d9e0-529">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-529">Amount</span></span></th>
<th><span data-ttu-id="4d9e0-530">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-531">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-531">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-532">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-532">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-533">35</span><span class="sxs-lookup"><span data-stu-id="4d9e0-533">35</span></span></td>
<td><span data-ttu-id="4d9e0-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4d9e0-535">175.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-535">175.00</span></span></td>
<td><span data-ttu-id="4d9e0-536">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-537">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-537">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-538">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-538">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-539">55</span><span class="sxs-lookup"><span data-stu-id="4d9e0-539">55</span></span></td>
<td><span data-ttu-id="4d9e0-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4d9e0-541">275.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-541">275.00</span></span></td>
<td><span data-ttu-id="4d9e0-542">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-543">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-543">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-544">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-544">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-545">10</span><span class="sxs-lookup"><span data-stu-id="4d9e0-545">10</span></span></td>
<td><span data-ttu-id="4d9e0-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4d9e0-547">50,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-547">50.00</span></span></td>
<td><span data-ttu-id="4d9e0-548">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-549">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-549">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-550">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-550">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-551">35</span><span class="sxs-lookup"><span data-stu-id="4d9e0-551">35</span></span></td>
<td><span data-ttu-id="4d9e0-552">(35 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="4d9e0-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4d9e0-553">436.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-553">436.00</span></span></td>
<td><span data-ttu-id="4d9e0-554">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-555">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-555">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-556">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-556">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-557">55</span><span class="sxs-lookup"><span data-stu-id="4d9e0-557">55</span></span></td>
<td><span data-ttu-id="4d9e0-558">(55 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="4d9e0-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4d9e0-559">685.14</span><span class="sxs-lookup"><span data-stu-id="4d9e0-559">685.14</span></span></td>
<td><span data-ttu-id="4d9e0-560">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-561">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-561">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-562">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-562">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-563">10</span><span class="sxs-lookup"><span data-stu-id="4d9e0-563">10</span></span></td>
<td><span data-ttu-id="4d9e0-564">(10 ÷ 100) × 1245,71</span><span class="sxs-lookup"><span data-stu-id="4d9e0-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4d9e0-565">124.57</span><span class="sxs-lookup"><span data-stu-id="4d9e0-565">124.57</span></span></td>
<td><span data-ttu-id="4d9e0-566">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-567">W poniższej tabeli przedstawiono wynik, gdy usługi finansowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-568">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-568">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-569">Wartość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-569">Magnitude</span></span></th>
<th><span data-ttu-id="4d9e0-570">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="4d9e0-570">Allocation factor</span></span></th>
<th><span data-ttu-id="4d9e0-571">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-571">Amount</span></span></th>
<th><span data-ttu-id="4d9e0-572">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-573">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-573">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-574">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-574">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-575">65</span><span class="sxs-lookup"><span data-stu-id="4d9e0-575">65</span></span></td>
<td><span data-ttu-id="4d9e0-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="4d9e0-577">438.75</span><span class="sxs-lookup"><span data-stu-id="4d9e0-577">438.75</span></span></td>
<td><span data-ttu-id="4d9e0-578">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-579">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-579">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-580">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-580">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-581">35</span><span class="sxs-lookup"><span data-stu-id="4d9e0-581">35</span></span></td>
<td><span data-ttu-id="4d9e0-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="4d9e0-583">236.25</span><span class="sxs-lookup"><span data-stu-id="4d9e0-583">236.25</span></span></td>
<td><span data-ttu-id="4d9e0-584">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-585">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-585">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-586">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-586">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-587">65</span><span class="sxs-lookup"><span data-stu-id="4d9e0-587">65</span></span></td>
<td><span data-ttu-id="4d9e0-588">(65 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="4d9e0-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="4d9e0-589">5,297.69</span></span></td>
<td><span data-ttu-id="4d9e0-590">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-591">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-591">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-592">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-592">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-593">35</span><span class="sxs-lookup"><span data-stu-id="4d9e0-593">35</span></span></td>
<td><span data-ttu-id="4d9e0-594">(35 ÷ 100) × (7714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="4d9e0-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="4d9e0-595">2,852.60</span></span></td>
<td><span data-ttu-id="4d9e0-596">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-597">W poniższej tabeli przedstawiono wynik, gdy usługi montażowe są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-598">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-598">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-599">Wartość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-599">Magnitude</span></span></th>
<th><span data-ttu-id="4d9e0-600">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="4d9e0-600">Allocation factor</span></span></th>
<th><span data-ttu-id="4d9e0-601">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-601">Amount</span></span></th>
<th><span data-ttu-id="4d9e0-602">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-603">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-604">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-604">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-605">60</span><span class="sxs-lookup"><span data-stu-id="4d9e0-605">60</span></span></td>
<td><span data-ttu-id="4d9e0-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="4d9e0-607">535.31</span><span class="sxs-lookup"><span data-stu-id="4d9e0-607">535.31</span></span></td>
<td><span data-ttu-id="4d9e0-608">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-609">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-610">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-610">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-611">20</span><span class="sxs-lookup"><span data-stu-id="4d9e0-611">20</span></span></td>
<td><span data-ttu-id="4d9e0-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="4d9e0-613">178.44</span><span class="sxs-lookup"><span data-stu-id="4d9e0-613">178.44</span></span></td>
<td><span data-ttu-id="4d9e0-614">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-615">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-616">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-616">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-617">60</span><span class="sxs-lookup"><span data-stu-id="4d9e0-617">60</span></span></td>
<td><span data-ttu-id="4d9e0-618">(60 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="4d9e0-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="4d9e0-619">4,487.12</span></span></td>
<td><span data-ttu-id="4d9e0-620">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-621">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-622">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-622">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-623">20</span><span class="sxs-lookup"><span data-stu-id="4d9e0-623">20</span></span></td>
<td><span data-ttu-id="4d9e0-624">(20 ÷ 80) × (5297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="4d9e0-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="4d9e0-625">1,495.71</span></span></td>
<td><span data-ttu-id="4d9e0-626">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4d9e0-627">W poniższej tabeli przedstawiono wynik, gdy usługi pakowania są stosowane jako podstawa alokacji dla kosztu łącznego (stałego i zmiennego).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-628">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-628">Cost object</span></span></th>
<th><span data-ttu-id="4d9e0-629">Wartość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-629">Magnitude</span></span></th>
<th><span data-ttu-id="4d9e0-630">Współczynnik alokacji</span><span class="sxs-lookup"><span data-stu-id="4d9e0-630">Allocation factor</span></span></th>
<th><span data-ttu-id="4d9e0-631">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-631">Amount</span></span></th>
<th><span data-ttu-id="4d9e0-632">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-633">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-634">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-634">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-635">80</span><span class="sxs-lookup"><span data-stu-id="4d9e0-635">80</span></span></td>
<td><span data-ttu-id="4d9e0-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="4d9e0-637">241.05</span><span class="sxs-lookup"><span data-stu-id="4d9e0-637">241.05</span></span></td>
<td><span data-ttu-id="4d9e0-638">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-639">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-640">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-640">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-641">15</span><span class="sxs-lookup"><span data-stu-id="4d9e0-641">15</span></span></td>
<td><span data-ttu-id="4d9e0-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="4d9e0-643">45.20</span><span class="sxs-lookup"><span data-stu-id="4d9e0-643">45.20</span></span></td>
<td><span data-ttu-id="4d9e0-644">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-645">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-646">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-646">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-647">80</span><span class="sxs-lookup"><span data-stu-id="4d9e0-647">80</span></span></td>
<td><span data-ttu-id="4d9e0-648">(80 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="4d9e0-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="4d9e0-649">2,507.09</span></span></td>
<td><span data-ttu-id="4d9e0-650">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-651">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-652">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-652">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-653">15</span><span class="sxs-lookup"><span data-stu-id="4d9e0-653">15</span></span></td>
<td><span data-ttu-id="4d9e0-654">(15 ÷ 95) × (2852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="4d9e0-655">470.08</span><span class="sxs-lookup"><span data-stu-id="4d9e0-655">470.08</span></span></td>
<td><span data-ttu-id="4d9e0-656">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4d9e0-657">Zapisy w arkuszu (wpisy w arkuszu dotyczące salda obiektów kosztów)</span><span class="sxs-lookup"><span data-stu-id="4d9e0-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4d9e0-658">W arkuszu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-658">Journal</span></span></th>
<th><span data-ttu-id="4d9e0-659">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="4d9e0-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4d9e0-660">Kalendarzowy okres obrachunkowy</span><span class="sxs-lookup"><span data-stu-id="4d9e0-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4d9e0-661">Wersja</span><span class="sxs-lookup"><span data-stu-id="4d9e0-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-662">00004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-662">00004</span></span></td>
<td><span data-ttu-id="4d9e0-663">Arkusz alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="4d9e0-664">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-664">Fiscal</span></span></td>
<td><span data-ttu-id="4d9e0-665">2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-665">2017</span></span></td>
<td><span data-ttu-id="4d9e0-666">Okres 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-666">Period 1</span></span></td>
<td><span data-ttu-id="4d9e0-667">Obliczanie kosztów ogólnych / 01-02-2017 23:51:00: 00 / Księga /2017 / Okres 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="4d9e0-668">Wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="4d9e0-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4d9e0-669">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="4d9e0-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-670">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-671">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-671">Cost element</span></span></th>
<th><span data-ttu-id="4d9e0-672">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-672">Cost behavior</span></span></th>
<th><span data-ttu-id="4d9e0-673">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-674">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-675">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-675">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-676">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-676">HR</span></span></td>
<td><span data-ttu-id="4d9e0-677">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-677">10001</span></span></td>
<td><span data-ttu-id="4d9e0-678">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-678">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-679">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-679">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-680">500.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-681">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-682">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-682">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-683">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-683">HR</span></span></td>
<td><span data-ttu-id="4d9e0-684">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-684">10001</span></span></td>
<td><span data-ttu-id="4d9e0-685">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-685">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-686">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-686">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="4d9e0-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-688">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-689">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-689">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-690">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-690">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-691">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-691">10001</span></span></td>
<td><span data-ttu-id="4d9e0-692">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-692">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-693">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-693">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-694">675.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-695">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-696">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-696">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-697">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-697">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-698">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-698">10001</span></span></td>
<td><span data-ttu-id="4d9e0-699">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-699">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-700">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-700">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="4d9e0-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-702">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-703">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-703">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-704">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-704">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-705">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-705">10001</span></span></td>
<td><span data-ttu-id="4d9e0-706">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-706">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-707">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-707">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-708">713.75</span><span class="sxs-lookup"><span data-stu-id="4d9e0-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-709">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-710">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-710">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-711">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-711">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-712">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-712">10001</span></span></td>
<td><span data-ttu-id="4d9e0-713">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-713">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-714">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-714">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="4d9e0-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-716">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-717">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-717">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-718">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-718">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-719">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-719">10001</span></span></td>
<td><span data-ttu-id="4d9e0-720">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-720">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-721">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-721">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-722">286.25</span><span class="sxs-lookup"><span data-stu-id="4d9e0-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-723">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-724">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-724">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-725">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-725">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-726">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-726">10001</span></span></td>
<td><span data-ttu-id="4d9e0-727">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-727">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-728">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-728">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="4d9e0-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-730">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-731">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-732">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-732">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-733">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-733">10001</span></span></td>
<td><span data-ttu-id="4d9e0-734">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-734">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-735">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-735">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-736">776.36</span><span class="sxs-lookup"><span data-stu-id="4d9e0-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-737">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-738">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-739">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-739">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-740">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-740">10001</span></span></td>
<td><span data-ttu-id="4d9e0-741">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-741">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-742">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-742">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="4d9e0-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-744">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-745">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-746">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-746">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-747">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-747">10001</span></span></td>
<td><span data-ttu-id="4d9e0-748">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-748">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-749">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-749">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-750">223.64</span><span class="sxs-lookup"><span data-stu-id="4d9e0-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-751">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="4d9e0-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-752">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-753">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-753">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-754">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-754">10001</span></span></td>
<td><span data-ttu-id="4d9e0-755">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-755">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-756">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-756">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="4d9e0-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4d9e0-758">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4d9e0-759">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4d9e0-760">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-760">Cost element</span></span></th>
<th><span data-ttu-id="4d9e0-761">Zachowanie kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-761">Cost behavior</span></span></th>
<th><span data-ttu-id="4d9e0-762">Ilość</span><span class="sxs-lookup"><span data-stu-id="4d9e0-762">Amount</span></span></th>
<th><span data-ttu-id="4d9e0-763">Data księgowania</span><span class="sxs-lookup"><span data-stu-id="4d9e0-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4d9e0-764">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-764">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-765">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-765">HR</span></span></td>
<td><span data-ttu-id="4d9e0-766">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-766">10001</span></span></td>
<td><span data-ttu-id="4d9e0-767">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-767">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-768">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-768">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-769">-500.00</span></span></td>
<td><span data-ttu-id="4d9e0-770">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-771">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-771">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-772">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-772">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-773">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-773">10001</span></span></td>
<td><span data-ttu-id="4d9e0-774">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-774">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-775">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-775">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-776">175.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-776">175.00</span></span></td>
<td><span data-ttu-id="4d9e0-777">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-778">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-778">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-779">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-779">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-780">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-780">10001</span></span></td>
<td><span data-ttu-id="4d9e0-781">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-781">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-782">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-782">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-783">275.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-783">275.00</span></span></td>
<td><span data-ttu-id="4d9e0-784">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-785">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-785">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-786">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-786">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-787">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-787">10001</span></span></td>
<td><span data-ttu-id="4d9e0-788">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-788">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-789">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-789">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-790">50,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-790">50,00</span></span></td>
<td><span data-ttu-id="4d9e0-791">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-792">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-792">CC001</span></span></td>
<td><span data-ttu-id="4d9e0-793">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-793">HR</span></span></td>
<td><span data-ttu-id="4d9e0-794">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-794">10001</span></span></td>
<td><span data-ttu-id="4d9e0-795">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-795">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-796">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-796">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-797">-1245,71</span><span class="sxs-lookup"><span data-stu-id="4d9e0-797">-1,245.71</span></span></td>
<td><span data-ttu-id="4d9e0-798">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-799">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-799">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-800">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-800">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-801">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-801">10001</span></span></td>
<td><span data-ttu-id="4d9e0-802">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-802">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-803">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-803">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-804">436.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-804">436.00</span></span></td>
<td><span data-ttu-id="4d9e0-805">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-806">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-806">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-807">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-807">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-808">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-808">10001</span></span></td>
<td><span data-ttu-id="4d9e0-809">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-809">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-810">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-810">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-811">685.14</span><span class="sxs-lookup"><span data-stu-id="4d9e0-811">685.14</span></span></td>
<td><span data-ttu-id="4d9e0-812">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-813">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-813">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-814">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-814">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-815">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-815">10001</span></span></td>
<td><span data-ttu-id="4d9e0-816">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-816">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-817">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-817">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-818">124.57</span><span class="sxs-lookup"><span data-stu-id="4d9e0-818">124.57</span></span></td>
<td><span data-ttu-id="4d9e0-819">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-820">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-820">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-821">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-821">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-822">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-822">10001</span></span></td>
<td><span data-ttu-id="4d9e0-823">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-823">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-824">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-824">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-825">-675.00</span></span></td>
<td><span data-ttu-id="4d9e0-826">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-827">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-827">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-828">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-828">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-829">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-829">10001</span></span></td>
<td><span data-ttu-id="4d9e0-830">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-830">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-831">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-831">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-832">438.75</span><span class="sxs-lookup"><span data-stu-id="4d9e0-832">438.75</span></span></td>
<td><span data-ttu-id="4d9e0-833">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-834">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-834">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-835">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-835">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-836">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-836">10001</span></span></td>
<td><span data-ttu-id="4d9e0-837">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-837">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-838">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-838">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-839">236.25</span><span class="sxs-lookup"><span data-stu-id="4d9e0-839">236.25</span></span></td>
<td><span data-ttu-id="4d9e0-840">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-841">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-841">CC002</span></span></td>
<td><span data-ttu-id="4d9e0-842">Finanse</span><span class="sxs-lookup"><span data-stu-id="4d9e0-842">Finance</span></span></td>
<td><span data-ttu-id="4d9e0-843">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-843">10001</span></span></td>
<td><span data-ttu-id="4d9e0-844">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-844">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-845">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-845">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-846">-8150,29</span><span class="sxs-lookup"><span data-stu-id="4d9e0-846">-8,150.29</span></span></td>
<td><span data-ttu-id="4d9e0-847">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-848">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-848">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-849">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-849">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-850">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-850">10001</span></span></td>
<td><span data-ttu-id="4d9e0-851">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-851">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-852">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-852">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="4d9e0-853">5,297.69</span></span></td>
<td><span data-ttu-id="4d9e0-854">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-855">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-855">CC004</span></span></td>
<td><span data-ttu-id="4d9e0-856">Opakowanie</span><span class="sxs-lookup"><span data-stu-id="4d9e0-856">Packaging</span></span></td>
<td><span data-ttu-id="4d9e0-857">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-857">10001</span></span></td>
<td><span data-ttu-id="4d9e0-858">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-858">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-859">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-859">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="4d9e0-860">2,852.60</span></span></td>
<td><span data-ttu-id="4d9e0-861">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-862">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-862">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-863">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-863">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-864">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-864">10001</span></span></td>
<td><span data-ttu-id="4d9e0-865">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-865">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-866">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-866">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="4d9e0-867">-713.75</span></span></td>
<td><span data-ttu-id="4d9e0-868">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-869">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-870">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-870">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-871">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-871">10001</span></span></td>
<td><span data-ttu-id="4d9e0-872">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-872">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-873">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-873">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-874">535.31</span><span class="sxs-lookup"><span data-stu-id="4d9e0-874">535.31</span></span></td>
<td><span data-ttu-id="4d9e0-875">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-876">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-877">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-877">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-878">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-878">10001</span></span></td>
<td><span data-ttu-id="4d9e0-879">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-879">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-880">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-880">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-881">178.44</span><span class="sxs-lookup"><span data-stu-id="4d9e0-881">178.44</span></span></td>
<td><span data-ttu-id="4d9e0-882">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-883">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-883">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-884">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-884">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-885">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-885">10001</span></span></td>
<td><span data-ttu-id="4d9e0-886">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-886">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-887">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-887">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-888">-5982,83</span><span class="sxs-lookup"><span data-stu-id="4d9e0-888">-5,982.83</span></span></td>
<td><span data-ttu-id="4d9e0-889">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-890">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-891">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-891">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-892">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-892">10001</span></span></td>
<td><span data-ttu-id="4d9e0-893">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-893">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-894">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-894">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="4d9e0-895">4,487.12</span></span></td>
<td><span data-ttu-id="4d9e0-896">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-897">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-898">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-898">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-899">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-899">10001</span></span></td>
<td><span data-ttu-id="4d9e0-900">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-900">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-901">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-901">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="4d9e0-902">1,495.71</span></span></td>
<td><span data-ttu-id="4d9e0-903">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-904">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-904">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-905">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-905">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-906">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-906">10001</span></span></td>
<td><span data-ttu-id="4d9e0-907">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-907">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-908">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-908">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="4d9e0-909">-286.25</span></span></td>
<td><span data-ttu-id="4d9e0-910">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-911">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-912">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-912">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-913">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-913">10001</span></span></td>
<td><span data-ttu-id="4d9e0-914">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-914">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-915">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-915">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-916">241.05</span><span class="sxs-lookup"><span data-stu-id="4d9e0-916">241.05</span></span></td>
<td><span data-ttu-id="4d9e0-917">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-918">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-919">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-919">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-920">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-920">10001</span></span></td>
<td><span data-ttu-id="4d9e0-921">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-921">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-922">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-922">Fixed cost</span></span></td>
<td><span data-ttu-id="4d9e0-923">45.20</span><span class="sxs-lookup"><span data-stu-id="4d9e0-923">45.20</span></span></td>
<td><span data-ttu-id="4d9e0-924">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-925">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-925">CC003</span></span></td>
<td><span data-ttu-id="4d9e0-926">Zestaw</span><span class="sxs-lookup"><span data-stu-id="4d9e0-926">Assembly</span></span></td>
<td><span data-ttu-id="4d9e0-927">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-927">10001</span></span></td>
<td><span data-ttu-id="4d9e0-928">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-928">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-929">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-929">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-930">-2977,17</span><span class="sxs-lookup"><span data-stu-id="4d9e0-930">-2,977.17</span></span></td>
<td><span data-ttu-id="4d9e0-931">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-932">Prod 1</span></span></td>
<td><span data-ttu-id="4d9e0-933">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-933">Product 1</span></span></td>
<td><span data-ttu-id="4d9e0-934">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-934">10001</span></span></td>
<td><span data-ttu-id="4d9e0-935">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-935">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-936">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-936">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="4d9e0-937">2,507.09</span></span></td>
<td><span data-ttu-id="4d9e0-938">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4d9e0-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-939">Prod 2</span></span></td>
<td><span data-ttu-id="4d9e0-940">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-940">Product 2</span></span></td>
<td><span data-ttu-id="4d9e0-941">10001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-941">10001</span></span></td>
<td><span data-ttu-id="4d9e0-942">Elektryczność</span><span class="sxs-lookup"><span data-stu-id="4d9e0-942">Electricity</span></span></td>
<td><span data-ttu-id="4d9e0-943">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-943">Variable cost</span></span></td>
<td><span data-ttu-id="4d9e0-944">470.08</span><span class="sxs-lookup"><span data-stu-id="4d9e0-944">470.08</span></span></td>
<td><span data-ttu-id="4d9e0-945">31 stycznia 2017</span><span class="sxs-lookup"><span data-stu-id="4d9e0-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="4d9e0-946">Wniosek</span><span class="sxs-lookup"><span data-stu-id="4d9e0-946">Conclusion</span></span>
<span data-ttu-id="4d9e0-947">W rachunkowości finansowej koszt 10 000,00 za energię elektryczną jest księgowany w centrum kosztu o fikcyjnym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="4d9e0-948">W związku z tym księgowi kosztów będą wiedzieć, że ten koszt musi zostać rozdzielony.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="4d9e0-949">W rachunku kosztów koszty przepływają przez jednostki organizacyjne i poziomy na podstawie zasad i reguł, które są stosowane.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="4d9e0-950">Każdy koszt został skojarzony z podstawą alokacji, która zapewnia najlepszą ocenę alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="4d9e0-951">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="4d9e0-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="4d9e0-952">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="4d9e0-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="4d9e0-953">Razem</span><span class="sxs-lookup"><span data-stu-id="4d9e0-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="4d9e0-954">CC099</span><span class="sxs-lookup"><span data-stu-id="4d9e0-954">CC099</span></span></th>
<th><span data-ttu-id="4d9e0-955">CC001</span><span class="sxs-lookup"><span data-stu-id="4d9e0-955">CC001</span></span></th>
<th><span data-ttu-id="4d9e0-956">CC002</span><span class="sxs-lookup"><span data-stu-id="4d9e0-956">CC002</span></span></th>
<th><span data-ttu-id="4d9e0-957">CC003</span><span class="sxs-lookup"><span data-stu-id="4d9e0-957">CC003</span></span></th>
<th><span data-ttu-id="4d9e0-958">CC004</span><span class="sxs-lookup"><span data-stu-id="4d9e0-958">CC004</span></span></th>
<th><span data-ttu-id="4d9e0-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-959">Proj 1</span></span></th>
<th><span data-ttu-id="4d9e0-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-960">Proj 2</span></span></th>
<th><span data-ttu-id="4d9e0-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4d9e0-961">Prod 1</span></span></th>
<th><span data-ttu-id="4d9e0-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4d9e0-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="4d9e0-963">10001 Energia elektryczna</span><span class="sxs-lookup"><span data-stu-id="4d9e0-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-965"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-966"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-967"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-968"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-969"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-970"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-971"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-972"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="4d9e0-973">Niesklasyfikowane</span><span class="sxs-lookup"><span data-stu-id="4d9e0-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-974">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="4d9e0-975">Koszt stały</span><span class="sxs-lookup"><span data-stu-id="4d9e0-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-976">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-977">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-978">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-979">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-980">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-981">776.36</span><span class="sxs-lookup"><span data-stu-id="4d9e0-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-982">223.64</span><span class="sxs-lookup"><span data-stu-id="4d9e0-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-983"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="4d9e0-984">Koszt zmienny</span><span class="sxs-lookup"><span data-stu-id="4d9e0-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-985">000</span><span class="sxs-lookup"><span data-stu-id="4d9e0-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-986">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-987">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-988">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-989">0,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-990">30.00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-991">10,00</span><span class="sxs-lookup"><span data-stu-id="4d9e0-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="4d9e0-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="4d9e0-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4d9e0-994"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="4d9e0-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="4d9e0-995">W tym temacie opisano, jak podstawowy składnik kosztów — 10001 Energia elektryczna — przepływa przez obiekty kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="4d9e0-996">W efekcie ten koszt ogólny jest rozdzielany (alokowany) do najniższego poziomu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="4d9e0-997">Innymi słowy koszt jest zapisywany w ciężar (obciąża) obiekty kosztów na najniższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="4d9e0-998">Jeśli potrzebujesz obrazowego przepływu kosztów między obiektami kosztów, można to uzyskać za pomocą zasad akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="4d9e0-999">Aby uzyskać szczegółowe informacje, zobacz temat Zasada akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="4d9e0-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="4d9e0-1000">(należy zwrócić uwagę, że ten temat nie jest jeszcze ukończony, ale niedługo będzie gotowy).</span><span class="sxs-lookup"><span data-stu-id="4d9e0-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




