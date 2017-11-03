---
title: "Umowy dotyczące projektu"
description: "Ten artykuł zawiera opisy i przykłady umów dotyczących projektów, które można tworzyć dla różnych typów projektów i źródeł finansowania, oraz opis metod zarządzania umowami i fakturowania klientów projektów w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7a69036327c6e818c1d4a3da72ee2f4c2d19cfcd
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="project-contracts"></a><span data-ttu-id="08a89-103">Umowy dotyczące projektu</span><span class="sxs-lookup"><span data-stu-id="08a89-103">Project contracts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="08a89-104">Ten artykuł zawiera opisy i przykłady umów dotyczących projektów, które można tworzyć dla różnych typów projektów i źródeł finansowania, oraz opis metod zarządzania umowami i fakturowania klientów projektów w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="08a89-104">This article describes and provides examples of the project contracts that you can create for various types of projects and funding sources, and how you can manage contracts and invoice project customers in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

<span data-ttu-id="08a89-105">Typ projektu tworzonego dla umowy dotyczącej projektu określa metodę wystawiania faktur dla klientów projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-105">The type of project that you create for a project contract determines the method that is used to invoice project customers.</span></span> <span data-ttu-id="08a89-106">Umowę dotyczącą projektu i powiązany projekt można zmienić, ale nie można zmienić typu projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-106">You can change a project contract and the related project, but you can't change the project type.</span></span> 

<span data-ttu-id="08a89-107">Za pomocą umowy dotyczącej projektu można fakturować jeden lub kilka projektów w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="08a89-107">By using a project contract, you can invoice one or more projects at the same time.</span></span> <span data-ttu-id="08a89-108">Umowa dotycząca projektu pozwala zapewnić spójną procedurę fakturowania każdego podprojektu w strukturze projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-108">The project contract also helps guarantee a consistent invoicing procedure for every subproject in a project structure.</span></span> 

<span data-ttu-id="08a89-109">Każdy projekt, dla którego zostanie wystawiona faktura, musi być skojarzony z umową dotyczącą projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-109">Every project that will be invoiced must be associated with a project contract.</span></span> <span data-ttu-id="08a89-110">Ustawienia dla umowy dotyczącej projektu są stosowane do wszystkich projektów i podprojektów, które są skojarzone z umową dotyczącą projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-110">The settings for a project contract apply to all projects and subprojects that are associated with that project contract.</span></span> 

<span data-ttu-id="08a89-111">Umowa dotycząca projektu może określać jedno lub więcej źródeł finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-111">A project contract can specify one or more sources of funding.</span></span> <span data-ttu-id="08a89-112">Dzięki temu można podzielić fakturę między wielu płatników, skonfigurować limity finansowania tak, aby źródła finansowania nie były wyświetlane na rachunku dla więcej niż określonej kwoty i skonfigurować reguły finansowania dla rozchodów związanych z opłatami.</span><span class="sxs-lookup"><span data-stu-id="08a89-112">Therefore, you can split the billing among multiple funders, set up funding limits so that funding sources are not billed more than a specified amount, and configure funding rules for charging expenditures.</span></span>

## <a name="funding-for-project-contracts"></a><span data-ttu-id="08a89-113">Finansowanie umów dotyczących projektów</span><span class="sxs-lookup"><span data-stu-id="08a89-113">Funding for project contracts</span></span>
<span data-ttu-id="08a89-114">Niektóre umowy dotyczące projektu określają, że kilka podmiotów finansuje koszty projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-114">Some project contracts specify that multiple parties share the responsibility for funding the project costs.</span></span> <span data-ttu-id="08a89-115">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="08a89-115">Here are some examples:</span></span>

-   <span data-ttu-id="08a89-116">Duży odbiorca, który ma wiele oddziałów, prosi o podzielenie finansowania projektu między oddziały.</span><span class="sxs-lookup"><span data-stu-id="08a89-116">A large customer that has multiple divisions requests that funding of a project be split by division.</span></span>
-   <span data-ttu-id="08a89-117">Twoja firma dzieli koszty dużego projektu z organizacją zewnętrzną.</span><span class="sxs-lookup"><span data-stu-id="08a89-117">Your company shares the costs of a large project with an external organization.</span></span>
-   <span data-ttu-id="08a89-118">Projekt drogi jest wspólnie finansowany przez dwie gminy.</span><span class="sxs-lookup"><span data-stu-id="08a89-118">A  road project is co-funded by two municipalities.</span></span>
-   <span data-ttu-id="08a89-119">Projekt mostu jest finansowany z dotacji rządowej oraz ze środków firmy prywatnej.</span><span class="sxs-lookup"><span data-stu-id="08a89-119">A bridge project is funded by a government grant and a private corporation.</span></span>

<span data-ttu-id="08a89-120">W programie Finance and Operations można podzielić rozliczenie jednej transakcji lub całego projektu między wielu klientów, wiele grantów i organizacji.</span><span class="sxs-lookup"><span data-stu-id="08a89-120">In Finance and Operations, you can split the billing for a single transaction or an entire project among multiple customers, grants, or organizations.</span></span> 

<span data-ttu-id="08a89-121">W przypadku projektów, które mają wiele fundatorów, wszystkie strony partycypujące w finansowaniu zaawansowanego projektu są nazywane źródłami finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-121">In projects that have multiple funders, all parties that contribute to the funding of an advanced funding project are called funding sources.</span></span> <span data-ttu-id="08a89-122">Po zdefiniowaniu odbiorcy, organizacji lub dotacji jako źródła finansowania można je przypisać do jednej lub kilku reguł finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-122">After a customer, organization, or grant is defined as a funding source, it can be assigned to one or more funding rules.</span></span> <span data-ttu-id="08a89-123">Reguły finansowania zawierają kryteria, które określają sposób podziału opłat między różne źródła finansowania projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-123">Funding rules contain the criteria that determines how charges are allocated to the various funding sources for a project.</span></span> 

<span data-ttu-id="08a89-124">Ponieważ towarów magazynowych, takich te, które są pojawiają się w zapotrzebowaniach na zakup i zamówieniach zakupu, nie można podzielić, kwoty kosztów nie można rozdzielić między wiele źródeł finansowania na etapie dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="08a89-124">Because stocked items, such as those that appear on purchase requisitions and purchase orders, can't be split, the cost amount can't be split among multiple funding sources at the time of distribution.</span></span> <span data-ttu-id="08a89-125">Dlatego wartość źródła finansowania pozostaje 0 (zero) do momentu zaksięgowania wydania zapasów.</span><span class="sxs-lookup"><span data-stu-id="08a89-125">Therefore, the funding source value remains 0 (zero) until the inventory issue is posted.</span></span> <span data-ttu-id="08a89-126">Po zaksięgowaniu wydania zapasów kwota kosztu jest rozdzielana zgodnie z regułami dystrybucji konta dla projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-126">When the inventory issue is posted, the cost amount is distributed according to the account distribution rules for the project.</span></span>

<span data-ttu-id="08a89-127">Poniżej przedstawiono niektóre czynności, które można wykonać, aby podzielić fakturowanie między kilka źródeł finansowania:</span><span class="sxs-lookup"><span data-stu-id="08a89-127">Here are some steps that you can take to make it easier to split the billing among multiple funding sources:</span></span>

-   <span data-ttu-id="08a89-128">Określ, że wszystkie transakcje w ramach projektu używają tej samej waluty sprzedaży co umowa dotycząca projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-128">Specify that all transactions that are entered for a project use the same sales currency as the project contract.</span></span>
-   <span data-ttu-id="08a89-129">ustaw limity finansowania. Dzięki temu dla jednego źródła finansowania nie zostaną wystawione faktury na kwotę wyższą niż kwota określona w projekcie.</span><span class="sxs-lookup"><span data-stu-id="08a89-129">Set up funding limits, so that a funding source isn't invoiced more than a specified amount toward a project.</span></span>
-   <span data-ttu-id="08a89-130">Ustaw reguły finansowania i limity finansowania dla każdego pracownika, pozycji, kategorii, grupy kategorii i typu transakcji (lub dla wszystkich typów transakcji).</span><span class="sxs-lookup"><span data-stu-id="08a89-130">Configure funding rules and funding limits for each worker, item, category, category group, and transaction type (or for all transaction types).</span></span>
-   <span data-ttu-id="08a89-131">Wybierz opcjonalne daty rozpoczęcia i zakończenia, aby zdefiniować okres ważności każdej z reguł finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-131">Select optional start and end dates to define the period when each funding rule is valid.</span></span>
-   <span data-ttu-id="08a89-132">Określ wartość procentową, za którą odpowiada każde źródło finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-132">Specify the percentage that each funding source is responsible for.</span></span>
-   <span data-ttu-id="08a89-133">Określ, które źródło finansowania jest odpowiedzialne za finansowanie różnic wynikających z obliczeń alokacji finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-133">Specify which funding source is responsible for rounding differences that are caused by funding allocation calculations.</span></span>
-   <span data-ttu-id="08a89-134">Ustaw reguły określające jak koszty projektu będą fakturowane dla odbiorców zewnętrznych i jak będą obciążały organizacje wewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="08a89-134">Set up rules that determine how project costs are invoiced to external customers and charged to internal organizations.</span></span>
-   <span data-ttu-id="08a89-135">Zapisz transakcje na zablokowanym koncie finansowania dopóki nie będzie możliwe uzyskanie dodatkowego finansowania lub nie zostanie podjęta decyzja o finansowaniu kosztów z wewnętrznego źródła.</span><span class="sxs-lookup"><span data-stu-id="08a89-135">Record transactions in an on-hold funding account until additional funding can be obtained, or until you decide to bear the costs internally.</span></span>

<span data-ttu-id="08a89-136">Aby określić, która grupa podatku ma zostać skojarzona z transakcją, projekt zostanie przeszukany pod kątem przypisania grupy podatku.</span><span class="sxs-lookup"><span data-stu-id="08a89-136">To determine which tax group to associate with a transaction, the project is searched for a tax group assignment.</span></span> <span data-ttu-id="08a89-137">Jeśli na etapie projektu nie została przypisana grupa podatku, zostanie przeszukana umowa dotycząca projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-137">If no tax group assignment has been made at the project level, the project contract is searched.</span></span>

### <a name="example-multiple-funding-sources-simple"></a><span data-ttu-id="08a89-138">Przykład: Wiele źródeł finansowania (uproszczone)</span><span class="sxs-lookup"><span data-stu-id="08a89-138">Example: Multiple funding sources (simple)</span></span>

<span data-ttu-id="08a89-139">Poniższa tabela zawiera scenariusze zarządzania alokacją finansowania między wiele źródeł finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-139">The following table provides scenarios for managing funding allocation among multiple funding sources.</span></span> <span data-ttu-id="08a89-140">Scenariusze te opierają się na następujących założeniach:</span><span class="sxs-lookup"><span data-stu-id="08a89-140">These scenarios are based on the following assumptions:</span></span>

-   <span data-ttu-id="08a89-141">Ustawienia priorytetu są uwzględniane w alokacji środków przed zastosowaniem innego kryterium reguły finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-141">Priority settings are factored into the allocation of funds before other funding rule criteria are applied.</span></span>
-   <span data-ttu-id="08a89-142">Nie określono zakresu dat w celu zdefiniowania okresu ważności reguły.</span><span class="sxs-lookup"><span data-stu-id="08a89-142">No date range has been specified to define the period d when the funding rule is valid.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="08a89-143"><strong>Scenariusz</strong></span><span class="sxs-lookup"><span data-stu-id="08a89-143"><strong>Scenario</strong></span></span></td>
<td><span data-ttu-id="08a89-144"><strong>Źródło finansowania </strong></span><span class="sxs-lookup"><span data-stu-id="08a89-144"><strong>Funding source</strong></span></span></td>
<td><span data-ttu-id="08a89-145"><strong>Procent alokacji </strong></span><span class="sxs-lookup"><span data-stu-id="08a89-145"><strong>Allocation percentage</strong></span></span></td>
<td><span data-ttu-id="08a89-146"><strong>Priorytet alokacji </strong></span><span class="sxs-lookup"><span data-stu-id="08a89-146"><strong>Allocation priority</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="08a89-147">Chcesz alokować koszty do jednego źródła finansowania do czasu wyczerpania się jej funduszy, alokować koszty do drugiego źródła finansowania do momentu wyczerpania jego funduszy, a na koniec pozostałe koszty przydzielić do trzeciego źródła finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-147">You want to allocate costs to one funding source until its funds are exhausted, allocate costs to a second funding source until its funds are exhausted, and finally allocate the remaining costs to a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="08a89-148">Źródło finansowania 1</span><span class="sxs-lookup"><span data-stu-id="08a89-148">Funding　source　1</span></span></li>
<li><span data-ttu-id="08a89-149">Źródło finansowania 2</span><span class="sxs-lookup"><span data-stu-id="08a89-149">Funding　source　2</span></span></li>
<li><span data-ttu-id="08a89-150">Źródło finansowania 3</span><span class="sxs-lookup"><span data-stu-id="08a89-150">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="08a89-151">100%</span><span class="sxs-lookup"><span data-stu-id="08a89-151">100%</span></span></li>
<li><span data-ttu-id="08a89-152">100%</span><span class="sxs-lookup"><span data-stu-id="08a89-152">100%</span></span></li>
<li><span data-ttu-id="08a89-153">100%</span><span class="sxs-lookup"><span data-stu-id="08a89-153">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="08a89-154">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="08a89-154">1</span></span></li>
<li><span data-ttu-id="08a89-155">2</span><span class="sxs-lookup"><span data-stu-id="08a89-155">2</span></span></li>
<li><span data-ttu-id="08a89-156">3</span><span class="sxs-lookup"><span data-stu-id="08a89-156">3</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="08a89-157">Chcesz alokować 75% kosztów do jednego źródła finansowania i 25% kosztów do drugiego źródła finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-157">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="08a89-158">Gdy oba źródła finansowania zostaną wyczerpane, chcesz zapłacić pozostałą kwotę z trzeciego źródła finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-158">When either of those funding sources is exhausted, you want to pay the remaining costs from a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="08a89-159">Źródło finansowania 1</span><span class="sxs-lookup"><span data-stu-id="08a89-159">Funding　source　1</span></span></li>
<li><span data-ttu-id="08a89-160">Źródło finansowania 2</span><span class="sxs-lookup"><span data-stu-id="08a89-160">Funding　source　2</span></span></li>
<li><span data-ttu-id="08a89-161">Źródło finansowania 3</span><span class="sxs-lookup"><span data-stu-id="08a89-161">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="08a89-162">75%</span><span class="sxs-lookup"><span data-stu-id="08a89-162">75%</span></span></li>
<li><span data-ttu-id="08a89-163">25%</span><span class="sxs-lookup"><span data-stu-id="08a89-163">25%</span></span></li>
<li><span data-ttu-id="08a89-164">100%</span><span class="sxs-lookup"><span data-stu-id="08a89-164">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="08a89-165">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="08a89-165">1</span></span></li>
<li><span data-ttu-id="08a89-166">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="08a89-166">1</span></span></li>
<li><span data-ttu-id="08a89-167">2</span><span class="sxs-lookup"><span data-stu-id="08a89-167">2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="08a89-168">Chcesz alokować 75% kosztów do jednego źródła finansowania i 25% kosztów do drugiego źródła finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-168">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="08a89-169">Gdy wszystkie te źródła finansowania zostaną wyczerpane, chcesz podzielić pozostały koszt między trzecie i czwarte źródło finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-169">When either of those funding sources is exhausted, you want to split the remaining costs between a third funding source and a fourth funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="08a89-170">Źródło finansowania 1</span><span class="sxs-lookup"><span data-stu-id="08a89-170">Funding　source　1</span></span></li>
<li><span data-ttu-id="08a89-171">Źródło finansowania 2</span><span class="sxs-lookup"><span data-stu-id="08a89-171">Funding　source　2</span></span></li>
<li><span data-ttu-id="08a89-172">Źródło finansowania 3</span><span class="sxs-lookup"><span data-stu-id="08a89-172">Funding　source　3</span></span></li>
<li><span data-ttu-id="08a89-173">Źródło finansowania 4</span><span class="sxs-lookup"><span data-stu-id="08a89-173">Funding　source　4</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="08a89-174">75%</span><span class="sxs-lookup"><span data-stu-id="08a89-174">75%</span></span></li>
<li><span data-ttu-id="08a89-175">25%</span><span class="sxs-lookup"><span data-stu-id="08a89-175">25%</span></span></li>
<li><span data-ttu-id="08a89-176">50%</span><span class="sxs-lookup"><span data-stu-id="08a89-176">50%</span></span></li>
<li><span data-ttu-id="08a89-177">50%</span><span class="sxs-lookup"><span data-stu-id="08a89-177">50%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="08a89-178">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="08a89-178">1</span></span></li>
<li><span data-ttu-id="08a89-179">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="08a89-179">1</span></span></li>
<li><span data-ttu-id="08a89-180">2</span><span class="sxs-lookup"><span data-stu-id="08a89-180">2</span></span></li>
<li><span data-ttu-id="08a89-181">2</span><span class="sxs-lookup"><span data-stu-id="08a89-181">2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="08a89-182">Chcesz alokować pierwsze 25% kosztów do jednego źródła finansowania, a resztę do drugiego.</span><span class="sxs-lookup"><span data-stu-id="08a89-182">You want to allocate the first 25 percent of costs to one funding source and the rest to a second funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="08a89-183">Źródło finansowania 1</span><span class="sxs-lookup"><span data-stu-id="08a89-183">Funding　source　1</span></span></li>
<li><span data-ttu-id="08a89-184">Źródło finansowania 2</span><span class="sxs-lookup"><span data-stu-id="08a89-184">Funding　source　2</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="08a89-185">25%</span><span class="sxs-lookup"><span data-stu-id="08a89-185">25%</span></span></li>
<li><span data-ttu-id="08a89-186">100%</span><span class="sxs-lookup"><span data-stu-id="08a89-186">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="08a89-187">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="08a89-187">1</span></span></li>
<li><span data-ttu-id="08a89-188">2</span><span class="sxs-lookup"><span data-stu-id="08a89-188">2</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a><span data-ttu-id="08a89-189">Przykład: Wiele źródeł finansowania (złożone)</span><span class="sxs-lookup"><span data-stu-id="08a89-189">Example: Multiple funding sources (complex)</span></span>

<span data-ttu-id="08a89-190">Masz trzy źródła finansowania, których chcesz użyć w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="08a89-190">You have three funding sources that you want to use in the following order:</span></span>

1.  <span data-ttu-id="08a89-191">Użyj równomiernie źródeł finansowania 2 i 3, aż do wyczerpania środków źródła 2.</span><span class="sxs-lookup"><span data-stu-id="08a89-191">Use funding source 2 and funding source 3 equally until funding source 2 is exhausted.</span></span>
2.  <span data-ttu-id="08a89-192">Kontynuuj korzystanie ze źródła finansowania 3 aż do jego wyczerpania.</span><span class="sxs-lookup"><span data-stu-id="08a89-192">Continue to use funding source 3 until it is exhausted.</span></span>
3.  <span data-ttu-id="08a89-193">Użyj 1 źródła finansowania 1 po wyczerpaniu środków źródła 3.</span><span class="sxs-lookup"><span data-stu-id="08a89-193">Use funding source 1 after funding source 3 is exhausted.</span></span>

<span data-ttu-id="08a89-194">Aby zrealizować ten cel, musisz wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="08a89-194">To accomplish this goal, you must do the following:</span></span>

-   <span data-ttu-id="08a89-195">Ustaw limity finansowania dla źródeł 2 i 3 jako odpowiednie kwoty.</span><span class="sxs-lookup"><span data-stu-id="08a89-195">Set up funding limits for funding source 2 and funding source 3, for their respective amounts.</span></span>
-   <span data-ttu-id="08a89-196">Utwórz następujące reguły finansowania:</span><span class="sxs-lookup"><span data-stu-id="08a89-196">Create the following funding rules:</span></span>
    -   <span data-ttu-id="08a89-197">Reguła 1 (Priorytet 1): Alokacja 50% transakcji do źródła finansowania 2 i 50% do źródła finansowania 3.</span><span class="sxs-lookup"><span data-stu-id="08a89-197">Rule 1 (Priority 1): Allocate 50 percent of transactions to funding source 2 and 50 percent to funding source 3.</span></span>
    -   <span data-ttu-id="08a89-198">Reguła 2 (Priorytet 2): Przydziel 100% transakcji do źródła finansowania 3.</span><span class="sxs-lookup"><span data-stu-id="08a89-198">Rule 2 (Priority 2): Allocate 100 percent of transactions to funding source 3.</span></span>
    -   <span data-ttu-id="08a89-199">Reguła 3 (Priorytet 3): Przydziel 100% transakcji do źródła finansowania 1.</span><span class="sxs-lookup"><span data-stu-id="08a89-199">Rule 3 (Priority 3): Allocate 100 percent of transactions to funding source 1.</span></span>

<span data-ttu-id="08a89-200">Ta konfiguracja zostanie wykonana, ponieważ transakcje są sprawdzane pod kątem reguł i limitów i system sprawdza, czy któreś z nich ma zastosowanie do transakcji.</span><span class="sxs-lookup"><span data-stu-id="08a89-200">This setup works because transactions are checked against rules and limits to determine whether any of them apply to the transaction.</span></span> <span data-ttu-id="08a89-201">Jeśli transakcji nie dotyczą żadne reguły ani limity, zostanie zastosowana reguła Wszystkie transakcje.</span><span class="sxs-lookup"><span data-stu-id="08a89-201">If no specific rules or limits apply to the transaction, the All transactions rule applies.</span></span> <span data-ttu-id="08a89-202">Reguła Wszystkie transakcje pasuje do wszystkich transakcji.</span><span class="sxs-lookup"><span data-stu-id="08a89-202">The All transactions rule matches all transactions.</span></span> 

<span data-ttu-id="08a89-203">Jeśli zostanie znaleziona reguła pasująca do transakcji, najpierw zostanie zastosowana wartość procentowa ustalona dla tej reguły, ale tylko po sprawdzeniu dopasowań pod kątem ustalonych limitów.</span><span class="sxs-lookup"><span data-stu-id="08a89-203">If a rule is found that matches a transaction, the percentage that has been allocated in that rule is applied first, but only after the matches are checked against any limits that have been set up.</span></span> <span data-ttu-id="08a89-204">Jeśli limit został osiągnięty, a źródło finansowania jest wyczerpane, reguła finansowania powiązana z limitem finansowania zostanie pominięta; program sprawdzi czy jest kolejna reguła do zastosowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-204">If a limit has been met, and a funding source’s funds are exhausted, the funding rule that is associated with the funding limit is disregarded, and the program checks for the next rule that applies.</span></span> 

<span data-ttu-id="08a89-205">W niektórych przypadkach do reguły można przydzielić tylko część transakcji.</span><span class="sxs-lookup"><span data-stu-id="08a89-205">In some cases, only part of a transaction can be allocated under a rule.</span></span> <span data-ttu-id="08a89-206">Może się tak zdarzyć, gdy limit zostanie osiągnięty podczas alokacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="08a89-206">This might happen because a limit is reached when the transaction is allocated.</span></span> <span data-ttu-id="08a89-207">W takim przypadku tylko ograniczona kwota zostanie alokowana zgodnie z regułą, np. po 50% do każdego źródła finansowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-207">In this case, only a certain amount is allocated according to that rule, such as 50 percent to each funding source.</span></span> <span data-ttu-id="08a89-208">Dotyczy to przypadku reguły 1 opisanej wcześniej.</span><span class="sxs-lookup"><span data-stu-id="08a89-208">This is the case in rule 1, which is described earlier in this section.</span></span> <span data-ttu-id="08a89-209">Reszta jest rozdzielana zgodnie z następną regułą w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="08a89-209">The remainder is allocated according to the next rule in the sequence.</span></span> 

<span data-ttu-id="08a89-210">Poniższa tabela przedstawia ten scenariusz w bardziej szczegółowy sposób.</span><span class="sxs-lookup"><span data-stu-id="08a89-210">The following table examines this scenario in more detail.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="08a89-211"><strong>Zespół </strong></span><span class="sxs-lookup"><span data-stu-id="08a89-211"><strong>Focus</strong></span></span></td>
<td><span data-ttu-id="08a89-212"><strong>Szczegóły</strong></span><span class="sxs-lookup"><span data-stu-id="08a89-212"><strong>Details</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="08a89-213">Reguły finansowania</span><span class="sxs-lookup"><span data-stu-id="08a89-213">Funding rules</span></span></td>
<td><ul>
<li><span data-ttu-id="08a89-214">Reguła 1 (Priorytet 1): Wszystkie transakcje.</span><span class="sxs-lookup"><span data-stu-id="08a89-214">Rule 1 (Priority 1): All transactions.</span></span> <span data-ttu-id="08a89-215">Alokacja do źródła finansowania 2 na poziomie 50% i źródła finansowania 3 na poziomie 50%.</span><span class="sxs-lookup"><span data-stu-id="08a89-215">Allocate funding source 2 at 50% and funding source 3 at 50%.</span></span></li>
<li><span data-ttu-id="08a89-216">Reguła 2 (Priorytet 2): Wszystkie transakcje.</span><span class="sxs-lookup"><span data-stu-id="08a89-216">Rule 2 (Priority 2): All transactions.</span></span> <span data-ttu-id="08a89-217">Alokacja do źródła finansowania 3 na poziomie 100%.</span><span class="sxs-lookup"><span data-stu-id="08a89-217">Allocate funding source 3 at 100%.</span></span></li>
<li><span data-ttu-id="08a89-218">Reguła 3 (Priorytet 2): Wszystkie transakcje.</span><span class="sxs-lookup"><span data-stu-id="08a89-218">Rule 3 (Priority 2): All transactions.</span></span> <span data-ttu-id="08a89-219">Alokacja do źródła finansowania 1 na poziomie 100%.</span><span class="sxs-lookup"><span data-stu-id="08a89-219">Allocate funding source 1 at 100%.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="08a89-220">Limity finansowania</span><span class="sxs-lookup"><span data-stu-id="08a89-220">Funding limits</span></span></td>
<td><ul>
<li><span data-ttu-id="08a89-221">Limit źródła finansowania 1 = 10 000,00</span><span class="sxs-lookup"><span data-stu-id="08a89-221">Funding source 1 limit = 10,000.00</span></span></li>
<li><span data-ttu-id="08a89-222">Limit źródła finansowania 2 = 500,00</span><span class="sxs-lookup"><span data-stu-id="08a89-222">Funding source 2 limit = 500.00</span></span></li>
<li><span data-ttu-id="08a89-223">Limit źródła finansowania 3 = 750,00</span><span class="sxs-lookup"><span data-stu-id="08a89-223">Funding source 3 limit = 750.00</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="08a89-224">Transakcja 1</span><span class="sxs-lookup"><span data-stu-id="08a89-224">Transaction 1</span></span></td>
<td><span data-ttu-id="08a89-225"><strong>Kwota transakcji:</strong> 100,00<strong>Finansowanie:</strong> transakcja jest opłacana zgodnie z regułą 1, ponieważ transakcja opłacana jest w pełni po zastosowaniu reguły 1.</span><span class="sxs-lookup"><span data-stu-id="08a89-225"><strong>Transaction amount:</strong> 100.00<strong>Funding:</strong> The transaction is paid according to rule 1 only, because the transaction is fully paid after rule 1 is applied.</span></span> <span data-ttu-id="08a89-226">Transakcja jest finansowana równomiernie ze źródeł finansowania 2 i 3.</span><span class="sxs-lookup"><span data-stu-id="08a89-226">The transaction is funded equally between funding source 2 and funding source 3.</span></span>
<ul>
<li><span data-ttu-id="08a89-227">Źródło finansowania 2: 50,00</span><span class="sxs-lookup"><span data-stu-id="08a89-227">Funding source 2: 50.00</span></span></li>
<li><span data-ttu-id="08a89-228">Źródło finansowania 3: 50,00</span><span class="sxs-lookup"><span data-stu-id="08a89-228">Funding source 3: 50.00</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="08a89-229">Transakcja 2</span><span class="sxs-lookup"><span data-stu-id="08a89-229">Transaction 2</span></span></td>
<td><span data-ttu-id="08a89-230"><strong>Kwota transakcji:</strong> 5000,00<strong>Finansowanie:</strong> Transakcja jest opłacana zgodnie ze wszystkimi trzema regułami.<strong>Reguła 1</strong>
</span><span class="sxs-lookup"><span data-stu-id="08a89-230"><strong>Transaction amount:</strong> 5,000.00<strong>Funding:</strong> The transaction is paid according to all three rules.<strong>Rule 1</strong>
</span></span><ul>
<li><span data-ttu-id="08a89-231">Źródło finansowania 2: 450,00</span><span class="sxs-lookup"><span data-stu-id="08a89-231">Funding source 2: 450.00</span></span></li>
<li><span data-ttu-id="08a89-232">Źródło finansowania 3: 450,00</span><span class="sxs-lookup"><span data-stu-id="08a89-232">Funding source 3: 450.00</span></span></li>
</ul><span data-ttu-id="08a89-233">
<strong>Reguła 2</strong>
</span><span class="sxs-lookup"><span data-stu-id="08a89-233">
<strong>Rule 2</strong>
</span></span><ul>
<li><span data-ttu-id="08a89-234">Źródło finansowania 3: 250,00 (= 750,00 – 50,00 – 450,00)</span><span class="sxs-lookup"><span data-stu-id="08a89-234">Funding source 3: 250.00 (= 750.00 – 50.00 – 450.00)</span></span></li>
</ul><span data-ttu-id="08a89-235">
<strong>Reguła 3</strong>
</span><span class="sxs-lookup"><span data-stu-id="08a89-235">
<strong>Rule 3</strong>
</span></span><ul>
<li><span data-ttu-id="08a89-236">Źródło finansowania 1: 3850,00 (= 5000,00 – 450,00 – 450,00 – 250,00)</span><span class="sxs-lookup"><span data-stu-id="08a89-236">Funding source 1: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="08a89-237">Łączne kwoty rozdzielone na wszystkie źródła finansowania</span><span class="sxs-lookup"><span data-stu-id="08a89-237">Total funds that are distributed for each funding source</span></span></td>
<td><ul>
<li><span data-ttu-id="08a89-238">Źródło finansowania 1: 3850,00</span><span class="sxs-lookup"><span data-stu-id="08a89-238">Funding source 1: 3,850.00</span></span></li>
<li><span data-ttu-id="08a89-239">Źródło finansowania 2: 500,00</span><span class="sxs-lookup"><span data-stu-id="08a89-239">Funding source 2: 500.00</span></span></li>
<li><span data-ttu-id="08a89-240">Źródło finansowania 3: 750,00</span><span class="sxs-lookup"><span data-stu-id="08a89-240">Funding source 3: 750.00</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a><span data-ttu-id="08a89-241">Reguły fakturowania</span><span class="sxs-lookup"><span data-stu-id="08a89-241">Billing rules</span></span>
<span data-ttu-id="08a89-242">Podczas negocjowania umową dotyczącej projektu z odbiorcą, można zdefiniować, jak i kiedy można wystawiać faktury dla odbiorcy z tytułu pracy w zakresie projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-242">When you negotiate a project contract with a customer, you define how and when you can invoice the customer for work on a project.</span></span> <span data-ttu-id="08a89-243">Po skonfigurowaniu umowy dotyczącej projektu oraz projektu, można skonfigurować reguły fakturowania dla projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-243">After you set up the project contract and the project, you can set up billing rules for the project.</span></span> <span data-ttu-id="08a89-244">Reguły fakturowania opierają się na warunkach projektu, które są określone w umowie dotyczącej projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-244">Billing rules are based on the project terms that are specified in the project contract.</span></span> <span data-ttu-id="08a89-245">Reguły fakturowania, które można utworzyć zależą od warunków umowy dotyczącej projektu i typu projektu, np. Czas i materiały lub Stała cena, który można skojarzyć z regułą fakturowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-245">The billing rules that you can create depend on the terms of the project contract and the project type, such as Time and material or Fixed-price, that you associate with the billing rule.</span></span> <span data-ttu-id="08a89-246">Można utworzyć tylko jedną regułę fakturowania dla kontraktu projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-246">You can create more than one billing rule for a project contract.</span></span> <span data-ttu-id="08a89-247">Regułę fakturowania można przypisać do wielu projektów, które są skojarzone z umową dotyczącą projektu i posiadają podobne warunki fakturowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-247">You can also assign a billing rule to multiple projects that are associated with the same project contract and have similar billing terms.</span></span> 

<span data-ttu-id="08a89-248">Można skonfigurować następujące typy reguł fakturowania:</span><span class="sxs-lookup"><span data-stu-id="08a89-248">You can set up the following types of billing rules:</span></span>

-   <span data-ttu-id="08a89-249">**Jednostka dostawy**— Wystawianie faktury dla odbiorcy po zakończeniu jednostki dostawy.</span><span class="sxs-lookup"><span data-stu-id="08a89-249">**Unit of delivery** – Invoice a customer when you complete a unit of delivery.</span></span> <span data-ttu-id="08a89-250">Istnieje możliwość zdefiniowania jednostek dostawy w umowie.</span><span class="sxs-lookup"><span data-stu-id="08a89-250">You define the units of delivery in the contract.</span></span>
-   <span data-ttu-id="08a89-251">**Postęp**— Wystawianie faktury dla odbiorcy po ukończeniu określonego procentu projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-251">**Progress** – Invoice a customer when you complete a specified percentage of the project.</span></span> <span data-ttu-id="08a89-252">Można skonfigurować regułę fakturowania, która automatycznie obliczy procent pracy wykonanej lub ręcznie obliczy procent pracy wykonanej, a także kwotę, na którą należy wystawić fakturę dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-252">You can set up a billing rule to automatically calculate the percentage of work completed, or you can manually calculate the percentage of work completed and the amount to invoice the customer.</span></span>
-   <span data-ttu-id="08a89-253">**Punkt kontrolny** — wystawianie faktury dla odbiorcy na całą kwotę w punkcie kontrolnym po jego osiągnięciu.</span><span class="sxs-lookup"><span data-stu-id="08a89-253">**Milestone** – Invoice a customer for the full amount of a project milestone when the milestone is reached.</span></span>
-   <span data-ttu-id="08a89-254">**Opłata**— Wystawianie faktury dla odbiorcy za usługi plus opłatę od zarządzania, zazwyczaj stanowiącą procent od kosztów usług.</span><span class="sxs-lookup"><span data-stu-id="08a89-254">**Fee** – Invoice a customer for your services plus a management fee, which is typically a percentage of the cost of services.</span></span>
-   <span data-ttu-id="08a89-255">**Czas i materiały**— Wystawianie faktury dla odbiorcy dla wartości z tytułu czasu i materiałów wykorzystanych w projekcie.</span><span class="sxs-lookup"><span data-stu-id="08a89-255">**Time and material** – Invoice a customer for the value of time and materials that are used on a project.</span></span>

<span data-ttu-id="08a89-256">Dla wszystkich typów reguł fakturowania można określić procent zatrzymania do odliczenia od faktur dla odbiorcy, dopóki projekt nie osiągnie uzgodnionego etapu.</span><span class="sxs-lookup"><span data-stu-id="08a89-256">For all types of billing rules, you can specify a retention percentage that is deducted from customer invoices until a project reaches an agreed-upon stage.</span></span> <span data-ttu-id="08a89-257">Procent zatrzymania płatności został określony w umowie dotyczącej projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-257">The payment retention percentage is specified in the project contract.</span></span> <span data-ttu-id="08a89-258">Kwota jest obliczana na podstawie i odejmowany od całkowitej wartości wierszy w fakturze dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-258">The amount is calculated based on, and subtracted from, the total value of the lines in a customer invoice.</span></span> 

<span data-ttu-id="08a89-259">Dla reguł fakturowania **czas i materiały** i **postęp** użycia reguł fakturowania, można przypisać kategorie płatne.</span><span class="sxs-lookup"><span data-stu-id="08a89-259">For **Time and material** and **Progress** billing rules, you can assign chargeable categories.</span></span> <span data-ttu-id="08a89-260">Kategorie płatnych wskazują transakcje, które należy uwzględnić na fakturach dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-260">Chargeable categories indicate the transactions that should be included in customer invoices.</span></span> 

<span data-ttu-id="08a89-261">Gdy jesteś gotowy do wystawienia faktury dla odbiorcy projektu, kwota do zafakturowania dla projektu jest obliczana na podstawie reguł fakturowania, a następnie generowana jest faktura projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-261">When you are ready to invoice the customer, the amount to invoice for the project is calculated based on the billing rules, and a project invoice proposal is generated.</span></span> 

<span data-ttu-id="08a89-262">Poniższe sekcje zawierają przykłady, które ilustrują sposób ustawiania i zarządzania regułą fakturowania dla projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-262">The following sections provide examples that show how to set up and manage billing rules for a project.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a><span data-ttu-id="08a89-263">Przykład: Tworzenie reguły fakturowania na podstawie liczby jednostek dostawy</span><span class="sxs-lookup"><span data-stu-id="08a89-263">Example: Create a billing rule that is based on the number of units delivered</span></span>

<span data-ttu-id="08a89-264">Twoja organizacja podpisuje umowę na przeprowadzenie cyklu pięciu szkoleń dla pracowników odbiorcy. Cena jednego szkolenia wynosi 10 000.</span><span class="sxs-lookup"><span data-stu-id="08a89-264">Your organization enters into an agreement to provide a total of five training sessions to a customer’s employees at a cost of 10,000 per training session.</span></span> <span data-ttu-id="08a89-265">Faktura odbiorcy jest wystawiana po zakończeniu każdego szkolenia.</span><span class="sxs-lookup"><span data-stu-id="08a89-265">You invoice the customer after each training session.</span></span> 

<span data-ttu-id="08a89-266">Konfigurując reguły fakturowania dla umowy, używasz następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="08a89-266">When you set up the billing rules for the contract, you use the following values:</span></span>

-   <span data-ttu-id="08a89-267">Jednostka dostawy to jedna sesja szkolenia.</span><span class="sxs-lookup"><span data-stu-id="08a89-267">The unit of delivery is one training session.</span></span>
-   <span data-ttu-id="08a89-268">Cena jednostkowa to 10 000 dla sesji szkoleniowej.</span><span class="sxs-lookup"><span data-stu-id="08a89-268">The unit price is 10,000 per training session.</span></span>
-   <span data-ttu-id="08a89-269">Łączna liczba jednostek to pięć sesji szkoleniowych.</span><span class="sxs-lookup"><span data-stu-id="08a89-269">The total number of units is five training sessions.</span></span>

<span data-ttu-id="08a89-270">Po zakończeniu jednej sesji szkoleniowej, można utworzyć fakturę na 10 000 z tytułu pierwszej dostarczonej jednostki dostawy i wysłać fakturę do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-270">When you have completed one training session, you can create an invoice for 10,000, for the first unit that was delivered, and send the invoice to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a><span data-ttu-id="08a89-271">Przykład: Tworzenie reguły fakturowania na podstawie określonego procentu ukończenia projektu (obliczanie ręczne)</span><span class="sxs-lookup"><span data-stu-id="08a89-271">Example: Create a billing rule that is based on a specified percentage of project completion (manual calculation)</span></span>

<span data-ttu-id="08a89-272">Organizacja będąca firmą konsultingową specjalizująca się w oprogramowaniu, zawiera umowę z odbiorcą, dotyczącą opracowywania części produktu, który jest opracowywany przez odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="08a89-272">Your organization, a software consulting firm, enters into an agreement with a customer to develop part of a product that the customer is developing.</span></span> <span data-ttu-id="08a89-273">Organizacja zgadza się dostarczać kod oprogramowania przez okres sześciu miesięcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-273">Your organization agrees to deliver the software code over a period of six months.</span></span> <span data-ttu-id="08a89-274">Odbiorca zgadza się na zapłacenie organizacji całkowitej kwoty równej 100 000 z tytułu wykonanej pracy.</span><span class="sxs-lookup"><span data-stu-id="08a89-274">The customer agrees to pay your organization a total of 100,000 for the work.</span></span> <span data-ttu-id="08a89-275">Tworzysz regułę fakturowania przy rozliczaniu odbiorcy na podstawie procentu pracy wykonanej nad projektem, jak określono w umowie.</span><span class="sxs-lookup"><span data-stu-id="08a89-275">You create a billing rule to invoice the customer based on the percentage of work that is completed on the project, as specified in the contract.</span></span>

-   <span data-ttu-id="08a89-276">Na koniec pierwszego miesiąca należy spotkać się z odbiorcą w celu określenia procentu pracy wykonanej.</span><span class="sxs-lookup"><span data-stu-id="08a89-276">At the end of the first month, you meet with the customer to determine the percentage of work completed.</span></span> <span data-ttu-id="08a89-277">Po sprawdzeniu projektu okazuje się, projekt został zrealizowany w 15%.</span><span class="sxs-lookup"><span data-stu-id="08a89-277">After you and the customer review the project, you decide that the project is 15 percent completed.</span></span>
-   <span data-ttu-id="08a89-278">Tworzysz fakturę na 15 000 (15% ze 100 000) i wysyłasz do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-278">You create an invoice for 15,000 (15 percent of 100,000) and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a><span data-ttu-id="08a89-279">Przykład: Tworzysz regułę fakturowania na podstawie określonego procentu ukończenia projektu (obliczanie automatyczne)</span><span class="sxs-lookup"><span data-stu-id="08a89-279">Example: Create a billing rule that is based on a specified percentage of project completion (automatic calculation)</span></span>

<span data-ttu-id="08a89-280">Twoja firma zajmująca się tworzeniem oprogramowania, wyraża zgodę na opracowanie pakietu księgowania listy płac dla odbiorcy za kwotę 30 000.</span><span class="sxs-lookup"><span data-stu-id="08a89-280">Your organization, a software development firm, agrees to develop a payroll accounting package for a customer for 30,000.</span></span> <span data-ttu-id="08a89-281">Odbiorca zgadza się na zapłacenie wynagrodzenia organizacji obliczonego na podstawie procentu zakończonej pracy.</span><span class="sxs-lookup"><span data-stu-id="08a89-281">The customer agrees to pay your organization based on the percentage of work completed.</span></span> <span data-ttu-id="08a89-282">Oszacowane koszty projektu wynoszą 20 000.</span><span class="sxs-lookup"><span data-stu-id="08a89-282">You estimate that the project costs are 20,000.</span></span> <span data-ttu-id="08a89-283">Umowa dotycząca projektu określa kategorie pracy, których można użyć w procesie fakturowania.</span><span class="sxs-lookup"><span data-stu-id="08a89-283">The project contract specifies the categories of work that you use in the billing process.</span></span> <span data-ttu-id="08a89-284">Należy zdefiniować reguły fakturowania, które obliczą automatycznie kwoty faktury dla procentu wykonanej pracy dla poszczególnych kategorii.</span><span class="sxs-lookup"><span data-stu-id="08a89-284">You set up billing rules that automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="08a89-285">Skonfiguruj budżet dla każdej kategorii:</span><span class="sxs-lookup"><span data-stu-id="08a89-285">You set up a budget for each category:</span></span>

-   <span data-ttu-id="08a89-286">**Programowanie** — Koszt w wysokości 15 000 i dochody wysokości 20 000</span><span class="sxs-lookup"><span data-stu-id="08a89-286">**Development** – Cost of 15,000 and revenue of 20,000</span></span>
-   <span data-ttu-id="08a89-287">**Instalacja** — Koszt w wysokości 5000 i dochody wysokości 10 000</span><span class="sxs-lookup"><span data-stu-id="08a89-287">**Installation** – Cost of 5,000 and revenue of 10,000</span></span>

<span data-ttu-id="08a89-288">Podczas tworzenia faktury dla odbiorcy po raz pierwszy, kwota faktury jest automatycznie obliczana na podstawie następujących informacji:</span><span class="sxs-lookup"><span data-stu-id="08a89-288">When you create a customer invoice for the first time, the invoice amount is automatically calculated based on the following information:</span></span>

-   <span data-ttu-id="08a89-289">Po miesiącu pracy, pracownik zatrudniony przy projekcie przesyła kartę czasu pracy dla projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-289">After a month, the worker on the project submits a timesheet for the project.</span></span> <span data-ttu-id="08a89-290">Koszt godzin pracy pracownika wynosi 5000 dla programowania i 1000 dla instalacji.</span><span class="sxs-lookup"><span data-stu-id="08a89-290">The cost of the worker’s hours is 5,000 for development and 1,000 for installation.</span></span> <span data-ttu-id="08a89-291">Praca w zakresie programowania została zakończona w 33% (koszt rzeczywisty wysokości 5000/koszt budżetowy wysokości 15 000), a praca w zakresie instalacji została w 20% (koszt rzeczywisty wysokości 1000/koszt budżetowych wysokości 5000).</span><span class="sxs-lookup"><span data-stu-id="08a89-291">The development work is 33 percent completed (5,000 actual cost/15,000 budget cost), and the installation work is 20 percent completed (1,000 actual cost/5,000 budget cost).</span></span>
-   <span data-ttu-id="08a89-292">Kwota faktury wynosi 8667 i jest automatycznie obliczana (33% z 20 000, powiększone o 20 procent z 10 000).</span><span class="sxs-lookup"><span data-stu-id="08a89-292">The invoice amount of 8,667 is automatically calculated (33 percent of 20,000 + 20 percent of 10,000).</span></span>
-   <span data-ttu-id="08a89-293">Tworzysz fakturę na 8667 i wysyłasz do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-293">You create an invoice for 8,667 and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a><span data-ttu-id="08a89-294">Przykład: Tworzenie reguły fakturowania, opartej na uzgodnionych punktach kontrolnych</span><span class="sxs-lookup"><span data-stu-id="08a89-294">Example: Create a billing rule that is based on agreed-upon milestones</span></span>

<span data-ttu-id="08a89-295">Organizacja będąca firmą konsultingowa specjalizującą się w zarządzaniu, zgadza się na przeprowadzenie badania rynku dla produktu konsumpcyjnego, którego planuje sprzedać odbiorca.</span><span class="sxs-lookup"><span data-stu-id="08a89-295">Your organization, a management consulting firm, agrees to conduct market research for a consumer product that the customer plans to sell.</span></span> <span data-ttu-id="08a89-296">Odbiorca zgadza się na korzystanie z usług przez trzy miesiące, począwszy od marca, i wyraża zgodę na wypłacenie organizacji kwoty równej 50000.</span><span class="sxs-lookup"><span data-stu-id="08a89-296">The customer agrees to use your services for a period of three months, starting in March, and agrees to pay your organization 50,000.</span></span> <span data-ttu-id="08a89-297">Projekt zawiera trzy punkty kontrolne:</span><span class="sxs-lookup"><span data-stu-id="08a89-297">The project has three milestones:</span></span>

-   <span data-ttu-id="08a89-298">Punkt kontrolny 1: Zbierz dane o konsumencie - 31 marca</span><span class="sxs-lookup"><span data-stu-id="08a89-298">Milestone 1: Collect consumer data – March 31</span></span>
-   <span data-ttu-id="08a89-299">Punkt kontrolny 2: Analizowanie danych konsumentów - kwiecień 30</span><span class="sxs-lookup"><span data-stu-id="08a89-299">Milestone 2: Analyze consumer data – April 30</span></span>
-   <span data-ttu-id="08a89-300">Punkt kontrolny 3: Przedstawienie propozycji żywotności produktu - maj 31</span><span class="sxs-lookup"><span data-stu-id="08a89-300">Milestone 3: Present a product viability proposal – May 31</span></span>

<span data-ttu-id="08a89-301">Odbiorca akceptuje płatność na rzecz organizacji w wysokości 10 000 dla pierwszego punktu kontrolnego , a 20 000 do drugiego i trzeciego punktu kontrolnego.</span><span class="sxs-lookup"><span data-stu-id="08a89-301">The customer agrees to pay your organization 10,000 for the first milestone, 20,000 for the second milestone, and 20,000 for the third milestone.</span></span> 

<span data-ttu-id="08a89-302">Podczas konfigurowania umowy dotyczącej projektu, zgadzasz się na wystawianie faktur dla odbiorcy na podstawie wypełnionych punktów kontrolnych projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-302">When you set up the project contract, you agree to bill the customer based on the milestone that has been completed.</span></span> <span data-ttu-id="08a89-303">Konfiguracja reguły fakturowania obejmuje następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="08a89-303">The billing rule setup includes the following steps:</span></span>

-   <span data-ttu-id="08a89-304">Określ punkty kontrolne projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-304">Define the project milestones.</span></span>
-   <span data-ttu-id="08a89-305">Zdefiniuj kwotę do zafakturowania dla faktury dla odbiorcy, po zakończeniu każdego punktu kontrolnego.</span><span class="sxs-lookup"><span data-stu-id="08a89-305">Define the amount to invoice the customer when each milestone is completed.</span></span>

<span data-ttu-id="08a89-306">Po zakończeniu pierwszego punktu kontrolnego w dniu 31 marca, zaznacz punkt kontrolny jako ukończony, a następnie utwórz fakturę na kwotę 10 000 i wyślij ją do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-306">When the first milestone is completed on March 31, you mark the milestone as completed, and then create an invoice for 10,000 and send it to the customer.</span></span> <span data-ttu-id="08a89-307">Nie można utworzyć fakturę dla punktu kontrolnego, dopóki nie zostanie on zaznaczony jako ukończony.</span><span class="sxs-lookup"><span data-stu-id="08a89-307">You can’t create an invoice for a milestone until you have marked the milestone as completed.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a><span data-ttu-id="08a89-308">Przykład: Tworzenie reguły fakturowania na podstawie usługi plus opłaty od zarządzania</span><span class="sxs-lookup"><span data-stu-id="08a89-308">Example: Create a billing rule that is based on services plus a management fee</span></span>

<span data-ttu-id="08a89-309">Twoja organizacja z branży consultingowej zgadza się na przeprowadzenie badania rynku w celu oceny rentowności produktu opracowywanego przez klienta z branży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="08a89-309">Your organization, a management consulting firm, agrees to conduct market research to evaluate the viability of a product that the customer, a retail company, is developing.</span></span> <span data-ttu-id="08a89-310">Warunki umowy określają, że zapewnisz usługi trzech najlepszych konsultantów ds. zarządzania w celu przeprowadzenia badania kosztu dla czasu i materiałów.</span><span class="sxs-lookup"><span data-stu-id="08a89-310">The terms of the agreement specify that you will provide the services of your top three management consultants, who will conduct the research on a time-and-materials basis.</span></span> <span data-ttu-id="08a89-311">Odbiorca zgadza się zapłacić 100 na godzinę plus 10-procentową opłatę za zarządzanie z tytułu godzin konsultacji, które zostały zafakturowane dla projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-311">The customer agrees to pay 100 per hour, plus a 10 percent management fee for the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="08a89-312">Podczas konfigurowania umowy dotyczącej projektu, należy utworzyć regułę fakturowania w celu dodania opłaty za zarządzanie o wysokości 10 procent opłat pobieranych z tytułu godzin konsultingowe spędzonych na projekcie.</span><span class="sxs-lookup"><span data-stu-id="08a89-312">When you set up the project contract, create a billing rule to add a 10 percent management fee to the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="08a89-313">Po utworzeniu faktury dla odbiorcy, wystawiany jest rachunek odbiorcy dotyczący 10-procentowej opłaty od zarządzania plus koszt godzin konsultingowych.</span><span class="sxs-lookup"><span data-stu-id="08a89-313">When you create an invoice for the customer, the customer is billed a 10 percent management fee plus the cost of the consulting hours.</span></span> <span data-ttu-id="08a89-314">Na przykład, jeśli trzech konsultantów pracowało łącznie 200 godzin w ramach projektu, zostanie utworzona faktura na kwotę 22 000 na podstawie następującego obliczenia:</span><span class="sxs-lookup"><span data-stu-id="08a89-314">For example, if the three consultants worked a total of 200 hours on the project, an invoice for 22,000 is created based on the following calculation:</span></span>

-   <span data-ttu-id="08a89-315">200 godzin przy 100 na godzinę = 20 000</span><span class="sxs-lookup"><span data-stu-id="08a89-315">200 hours at 100 per hour = 20,000</span></span>
-   <span data-ttu-id="08a89-316">Opłata od zarządzania wysokości 10 procent = 2000</span><span class="sxs-lookup"><span data-stu-id="08a89-316">10 percent management fee = 2,000</span></span>
-   <span data-ttu-id="08a89-317">Łączna kwota faktury = 22,000</span><span class="sxs-lookup"><span data-stu-id="08a89-317">Total invoice amount = 22,000</span></span>

<span data-ttu-id="08a89-318">Jeśli opłaty są należne dla odbiorcy, a użytkownik wybrał grupę podatków w umowie dotyczącej projektu, grupa podatku jest automatyczne wprowadzana do reguły fakturowania opłat.</span><span class="sxs-lookup"><span data-stu-id="08a89-318">If fees are taxable to a customer, and you select a sales tax group in the project contract, the sales tax group is automatically entered in a billing rule for fees.</span></span>

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a><span data-ttu-id="08a89-319">Przykład: Tworzenie reguły fakturowania dla wartości modułu czas i materiały</span><span class="sxs-lookup"><span data-stu-id="08a89-319">Example: Create a billing rule for the value of time and materials</span></span>

<span data-ttu-id="08a89-320">Organizacja z branży consultingowej zgadza się na zapewnienie pięciu konsultantów technicznych do pracy nad projektem oprogramowania rozwoju dla odbiorcy na następnych sześć miesięcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-320">Your organization, a software consulting firm, agrees to provide five technical consultants to work on a software development project for a customer for the next six months.</span></span> <span data-ttu-id="08a89-321">Klient akceptuje płatność 150 za każdą godzinę konsultacji plus koszty materiałów biurowych.</span><span class="sxs-lookup"><span data-stu-id="08a89-321">The customer agrees to pay 150 for each consulting hour, plus the cost of office supplies.</span></span> <span data-ttu-id="08a89-322">Organizacja wysyła faktury dla odbiorcy na koniec każdego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="08a89-322">Your organization sends an invoice to the customer at the end of each month.</span></span> 

<span data-ttu-id="08a89-323">Podczas konfigurowania umowy dotyczącej projektu, zgadzasz się wystawianie comiesięcznych faktur dla odbiorcy na podstawie zużytego czasu i materiałów dla projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-323">When you set up the project contract, you agree to bill the customer each month for time and materials on the project.</span></span> <span data-ttu-id="08a89-324">Utwórz regułę fakturowania, która zawiera następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="08a89-324">You create a billing rule that includes the following information:</span></span>

-   <span data-ttu-id="08a89-325">Okres umowy wynosi sześć miesięcy.</span><span class="sxs-lookup"><span data-stu-id="08a89-325">The contract period is six months.</span></span>
-   <span data-ttu-id="08a89-326">Skonsultowane godziny konsultingowe posiadają wartość 150 na godzinę.</span><span class="sxs-lookup"><span data-stu-id="08a89-326">Consulting time is calculated at a rate of 150 per hour.</span></span>
-   <span data-ttu-id="08a89-327">Materiały biurowe są fakturowane według kosztów, a łączny koszt projektu nie może przekroczyć 10 000.</span><span class="sxs-lookup"><span data-stu-id="08a89-327">Office supplies are invoiced at cost, and the total cost for the project must not exceed 10,000.</span></span>
-   <span data-ttu-id="08a89-328">Tworzysz fakturę dla odbiorcy na koniec każdego miesiąca kalendarzowego, w trakcie trwania projektu.</span><span class="sxs-lookup"><span data-stu-id="08a89-328">You create a customer invoice at the end of each calendar month during the project.</span></span>

<span data-ttu-id="08a89-329">Podczas pierwszego miesiąca, łącznie rejestrowanych jest 800 godzin pracy przez konsultantów pracujących nad projektem.</span><span class="sxs-lookup"><span data-stu-id="08a89-329">During the first month, a total of 800 hours are recorded by the consultants on the project.</span></span> <span data-ttu-id="08a89-330">Koszt materiałów biurowych do obciążenia projektu wynosi 2000.</span><span class="sxs-lookup"><span data-stu-id="08a89-330">The cost of office supplies that are charged to the project is 2,000.</span></span> <span data-ttu-id="08a89-331">Dlatego na koniec miesiąca, można utworzyć fakturę na sumę 122,000, obliczoną jako 800 godzin przy 150 za godzinę plus 2000 więcej za materiały biurowe.</span><span class="sxs-lookup"><span data-stu-id="08a89-331">Therefore, at the end of the month, you create an invoice for 122,000, which is calculated as 800 hours at 150 per hour, plus 2,000 for office supplies.</span></span>




