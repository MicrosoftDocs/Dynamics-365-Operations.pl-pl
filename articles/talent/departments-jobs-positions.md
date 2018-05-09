---
title: "Organizowanie pracowników za pomocą zadań, działów i stanowisk"
description: "Działy, zadania i stanowiska to elementy organizacyjne zarządzane w module Zasoby ludzkie. W tym temacie opisano koncepcję tych elementów."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent, Retail
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a084cb00e7aeeefce186efbf626bb63a97132862
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="organize-your-workforce-using-departments-jobs-and-positions"></a><span data-ttu-id="c9e52-104">Organizowanie pracowników za pomocą zadań, działów i stanowisk</span><span class="sxs-lookup"><span data-stu-id="c9e52-104">Organize your workforce using departments, jobs, and positions</span></span>

[!include [banner](includes/banner.md)]

[!include [retail name](includes/retail-name.md)]

<span data-ttu-id="c9e52-105">Działy, zadania i stanowiska to elementy organizacyjne zarządzane w module Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="c9e52-105">Departments, jobs, and positions are organizational elements that are maintained within Human resources.</span></span> <span data-ttu-id="c9e52-106">W tym temacie opisano koncepcję tych elementów.</span><span class="sxs-lookup"><span data-stu-id="c9e52-106">This topic describes conceptual information about these elements.</span></span> 

<span data-ttu-id="c9e52-107">Poniższy przykład ilustruje koncepcje opisane w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="c9e52-107">The following example is used to illustrate the concepts described in this topic.</span></span>

|<span data-ttu-id="c9e52-108">**Dział**</span><span class="sxs-lookup"><span data-stu-id="c9e52-108">**Department**</span></span>|<span data-ttu-id="c9e52-109">**Stanowisko**</span><span class="sxs-lookup"><span data-stu-id="c9e52-109">**Position**</span></span>|<span data-ttu-id="c9e52-110">**Zadanie**</span><span class="sxs-lookup"><span data-stu-id="c9e52-110">**Job**</span></span>|
|---|---|---|
|<span data-ttu-id="c9e52-111">**Sprzedaż**</span><span class="sxs-lookup"><span data-stu-id="c9e52-111">**Sales**</span></span>|<span data-ttu-id="c9e52-112">Menedżer ds. sprzedaży (Wschód)</span><span class="sxs-lookup"><span data-stu-id="c9e52-112">Sales manager (East)</span></span>|<span data-ttu-id="c9e52-113">Menedżer ds. sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c9e52-113">Sales manager</span></span>|
|<span data-ttu-id="c9e52-114">**Sprzedaż**</span><span class="sxs-lookup"><span data-stu-id="c9e52-114">**Sales**</span></span>|<span data-ttu-id="c9e52-115">Menedżer ds. sprzedaży (Zachód)</span><span class="sxs-lookup"><span data-stu-id="c9e52-115">Sales manager (West)</span></span>|<span data-ttu-id="c9e52-116">Menedżer ds. sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c9e52-116">Sales manager</span></span>|
|<span data-ttu-id="c9e52-117">**Sprzedaż**</span><span class="sxs-lookup"><span data-stu-id="c9e52-117">**Sales**</span></span>|<span data-ttu-id="c9e52-118">Menedżer ds. sprzedaży (Centrala)</span><span class="sxs-lookup"><span data-stu-id="c9e52-118">Sales manager (Central)</span></span>|<span data-ttu-id="c9e52-119">Menedżer ds. sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c9e52-119">Sales manager</span></span>|
|<span data-ttu-id="c9e52-120">**Księgowość**</span><span class="sxs-lookup"><span data-stu-id="c9e52-120">**Accounting**</span></span>|<span data-ttu-id="c9e52-121">Kierownik ds. księgowania</span><span class="sxs-lookup"><span data-stu-id="c9e52-121">Accounting supervisor</span></span>|<span data-ttu-id="c9e52-122">Menedżer ds. księgowania</span><span class="sxs-lookup"><span data-stu-id="c9e52-122">Accounting manager</span></span>|
|<span data-ttu-id="c9e52-123">**Księgowość**</span><span class="sxs-lookup"><span data-stu-id="c9e52-123">**Accounting**</span></span>|<span data-ttu-id="c9e52-124">Księgowanie-A</span><span class="sxs-lookup"><span data-stu-id="c9e52-124">Accounting-A</span></span>|<span data-ttu-id="c9e52-125">Księgowy</span><span class="sxs-lookup"><span data-stu-id="c9e52-125">Accountant</span></span>|
|<span data-ttu-id="c9e52-126">**Kadry**</span><span class="sxs-lookup"><span data-stu-id="c9e52-126">**Human resources**</span></span>|<span data-ttu-id="c9e52-127">Menedżer ds. HR (Wschód)</span><span class="sxs-lookup"><span data-stu-id="c9e52-127">HR manager (East)</span></span>|<span data-ttu-id="c9e52-128">Menedżer ds. HR</span><span class="sxs-lookup"><span data-stu-id="c9e52-128">HR manager</span></span>|
|<span data-ttu-id="c9e52-129">**Kadry**</span><span class="sxs-lookup"><span data-stu-id="c9e52-129">**Human resources**</span></span>|<span data-ttu-id="c9e52-130">Menedżer ds. HR (Zachód)</span><span class="sxs-lookup"><span data-stu-id="c9e52-130">HR manager (West)</span></span>|<span data-ttu-id="c9e52-131">Menedżer ds. HR</span><span class="sxs-lookup"><span data-stu-id="c9e52-131">HR manager</span></span>|
|<span data-ttu-id="c9e52-132">**Kadry**</span><span class="sxs-lookup"><span data-stu-id="c9e52-132">**Human resources**</span></span>|<span data-ttu-id="c9e52-133">Menedżer ds. HR (Centrala)</span><span class="sxs-lookup"><span data-stu-id="c9e52-133">HR manager (Central)</span></span>|<span data-ttu-id="c9e52-134">Menedżer ds. HR</span><span class="sxs-lookup"><span data-stu-id="c9e52-134">HR manager</span></span>|


 <a name="departments"></a><span data-ttu-id="c9e52-135">Działy</span><span class="sxs-lookup"><span data-stu-id="c9e52-135">Departments</span></span>
------------

<span data-ttu-id="c9e52-136">Dział jest jednostką operacyjną, która reprezentuje kategorię lub obszar funkcjonalny organizacji, który odpowiada za określony obszar organizacji, np. sprzedaż lub księgowość.</span><span class="sxs-lookup"><span data-stu-id="c9e52-136">A department is an operating unit that represents a category or functional area of an organization that is responsible for a specific area of the organization, such as sales or accounting.</span></span> <span data-ttu-id="c9e52-137">Dział jest używany w raportach dla obszarów funkcjonalnych i może mieć obowiązek raportowania zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="c9e52-137">A department is used to report on functional areas and may have profit and loss responsibility.</span></span> <span data-ttu-id="c9e52-138">Ponadto dział może zawierać grupę centrów kosztów.</span><span class="sxs-lookup"><span data-stu-id="c9e52-138">Also, a department might include a group of cost centers.</span></span> <span data-ttu-id="c9e52-139">Sprzedaż, księgowość i zasoby ludzkie to wybrane przykłady działów w organizacji.</span><span class="sxs-lookup"><span data-stu-id="c9e52-139">Sales, accounting, and human resources are some examples of departments in an organization.</span></span>

## <a name="jobs-and-positions"></a><span data-ttu-id="c9e52-140"> Stanowiska i pozycje</span><span class="sxs-lookup"><span data-stu-id="c9e52-140">Jobs and positions</span></span>
<span data-ttu-id="c9e52-141">Stanowisko to zbiór zadań i odpowiedzialności, które są wymagane od osoby, która wykonuje zadanie.</span><span class="sxs-lookup"><span data-stu-id="c9e52-141">A job is a collection of tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="c9e52-142">Pozycja jest pojedynczym wystąpieniem zadania.</span><span class="sxs-lookup"><span data-stu-id="c9e52-142">A position is an individual instance of a job.</span></span> <span data-ttu-id="c9e52-143">Zakresy odpowiedzialności, obowiązki, funkcje stanowisk, umiejętności, informacje o wykształceniu i certyfikaty, które są wymagane dla stanowisk, które są skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="c9e52-143">Areas of responsibility, job tasks, job functions, skills, education information, and certificates that are required for a job are also required for positions that are associated with a job.</span></span>
### <a name="job-tasks"></a><span data-ttu-id="c9e52-144">Zadania zlecenia</span><span class="sxs-lookup"><span data-stu-id="c9e52-144">Job tasks</span></span>

<span data-ttu-id="c9e52-145">Można tworzyć zadania opisujące podstawowe zadania, które pracownik zajmujący stanowisko obejmujące to zadanie musi wykonać.</span><span class="sxs-lookup"><span data-stu-id="c9e52-145">You can create job tasks that describe the basic tasks that a worker in a position for that job must complete.</span></span> <span data-ttu-id="c9e52-146">To samo zadanie można dodać do wielu stanowisk, i pozycje dla tego zadania będą je dziedziczyć.</span><span class="sxs-lookup"><span data-stu-id="c9e52-146">The same job task can be added to multiple jobs, and positions for those jobs will inherit those job tasks.</span></span> <span data-ttu-id="c9e52-147">Niektóre przykłady znajdują się w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c9e52-147">Examples of job tasks are listed in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c9e52-148">Zadanie</span><span class="sxs-lookup"><span data-stu-id="c9e52-148">Job</span></span></th>
<th><span data-ttu-id="c9e52-149">Zadanie zlecenia</span><span class="sxs-lookup"><span data-stu-id="c9e52-149">Job task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c9e52-150">Menedżer ds. sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c9e52-150">Sales manager</span></span></td>
<td><ul>
<li><span data-ttu-id="c9e52-151"><span class="input">Perf-review</span> — przeglądanie wydajności poszczególnych sprzedawców.</span><span class="sxs-lookup"><span data-stu-id="c9e52-151"><span class="input">Perf-review</span> – Review each salesperson’s job performance.</span></span></li>
<li><span data-ttu-id="c9e52-152"><span class="input">Abs-review</span> — zatwierdzanie lub odrzucanie wniosków urlopowych lub rejestracji nieobecności.</span><span class="sxs-lookup"><span data-stu-id="c9e52-152"><span class="input">Abs-review</span> – Approve or reject each salesperson’s absence requests or registrations.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c9e52-153">Księgowy</span><span class="sxs-lookup"><span data-stu-id="c9e52-153">Accountant</span></span></td>
<td><span data-ttu-id="c9e52-154"><span class="input">FIN-Report</span> — przeglądanie tygodniowych raportów finansowych dla dyrektora finansowego.</span><span class="sxs-lookup"><span data-stu-id="c9e52-154"><span class="input">FIN-Report</span> – Present weekly financial reports to chief financial officer.</span></span></td>
</tr>
</tbody>
</table>

### <a name="job-functions"></a><span data-ttu-id="c9e52-155">Funkcje stanowisk</span><span class="sxs-lookup"><span data-stu-id="c9e52-155">Job functions</span></span>

<span data-ttu-id="c9e52-156">Funkcje stanowisk są podobne do zadań.</span><span class="sxs-lookup"><span data-stu-id="c9e52-156">Job functions are like job tasks.</span></span> <span data-ttu-id="c9e52-157">Zadanie opisuj jedno lub więcej zadań, obowiązków i zakresów odpowiedzialności które są przypisane do stanowiska.</span><span class="sxs-lookup"><span data-stu-id="c9e52-157">A job function describes one or more tasks, duties or responsibilities that are assigned to a job.</span></span> <span data-ttu-id="c9e52-158">Funkcje stanowisk mogą być przypisywane do zadań i mogą służyć do ustawiania i wdrażania reguł uprawnień w systemach wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="c9e52-158">Job functions can be assigned to jobs and used to set up and implement eligibility rules for compensation plans.</span></span> <span data-ttu-id="c9e52-159">W poniższej tabeli przedstawiono przykłady funkcji stanowisk.</span><span class="sxs-lookup"><span data-stu-id="c9e52-159">Examples of job functions are listed in the following table.</span></span>

| <span data-ttu-id="c9e52-160">Zadanie</span><span class="sxs-lookup"><span data-stu-id="c9e52-160">Job</span></span>           | <span data-ttu-id="c9e52-161">Funkcja stanowiska</span><span class="sxs-lookup"><span data-stu-id="c9e52-161">Job function</span></span>                                                |
|---------------|-------------------------------------------------------------|
| <span data-ttu-id="c9e52-162">Menedżer ds. sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c9e52-162">Sales manager</span></span> | <span data-ttu-id="c9e52-163">Mng-people — zarządzanie ludźmi, którzy Ci podlegają.</span><span class="sxs-lookup"><span data-stu-id="c9e52-163">Mng-people – Manage people who report to you.</span></span>               |
| <span data-ttu-id="c9e52-164">Księgowy</span><span class="sxs-lookup"><span data-stu-id="c9e52-164">Accountant</span></span>    | <span data-ttu-id="c9e52-165">FIN-Review — obsługa danych finansowych dla zestawu kont.</span><span class="sxs-lookup"><span data-stu-id="c9e52-165">FIN-Review – Maintain financial data for a set of accounts.</span></span> |

### <a name="job-types"></a><span data-ttu-id="c9e52-166">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="c9e52-166">Job types</span></span>

<span data-ttu-id="c9e52-167">Typy zadań umożliwiają klasyfikowanie podobnych zadań wg kategorii.</span><span class="sxs-lookup"><span data-stu-id="c9e52-167">Use job types to classify similar jobs into categories.</span></span> <span data-ttu-id="c9e52-168">Funkcje stanowisk mogą być przypisywane do zadań i mogą służyć do ustawiania i wdrażania reguł uprawnień w systemie wynagrodzeń. W poniższej tabeli przedstawiono przykłady funkcji stanowisk.</span><span class="sxs-lookup"><span data-stu-id="c9e52-168">Job types, just like job functions, can be assigned to jobs and used to set up and implement eligibility rules for compensation plans.</span></span> <span data-ttu-id="c9e52-169">Poniższa lista zawiera kilka przykładów typów zadań:</span><span class="sxs-lookup"><span data-stu-id="c9e52-169">Some examples of job types are included in the following list:</span></span>
-   <span data-ttu-id="c9e52-170">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="c9e52-170">Full-time</span></span>
-   <span data-ttu-id="c9e52-171">Część etatu</span><span class="sxs-lookup"><span data-stu-id="c9e52-171">Part-time</span></span>
-   <span data-ttu-id="c9e52-172">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="c9e52-172">Salary</span></span>
-   <span data-ttu-id="c9e52-173">Stawka godzinowa</span><span class="sxs-lookup"><span data-stu-id="c9e52-173">Hourly pay</span></span>

### <a name="areas-of-responsibility"></a><span data-ttu-id="c9e52-174">Zakres odpowiedzialności</span><span class="sxs-lookup"><span data-stu-id="c9e52-174">Areas of responsibility</span></span>

<span data-ttu-id="c9e52-175">Zakresy odpowiedzialności pozwalają wskazać role pracy, procesy i produkty, za które byłby odpowiedzialny pracownik na danym stanowisku.</span><span class="sxs-lookup"><span data-stu-id="c9e52-175">Use areas of responsibility to indicate the work roles, processes, and products that a worker in a position for that job would be responsible for.</span></span> <span data-ttu-id="c9e52-176">Przykładem zakresu odpowiedzialności dla stanowiska „Księgowy” może być „Raporty finansowe dla produktu A”.</span><span class="sxs-lookup"><span data-stu-id="c9e52-176">An example of an area of responsibility for a job titled “Accountant” might be “Financial reporting for Product A”.</span></span>

<a name="positions"></a><span data-ttu-id="c9e52-177">Pozycje</span><span class="sxs-lookup"><span data-stu-id="c9e52-177">Positions</span></span>
----------

<span data-ttu-id="c9e52-178">Pozycje są ważnym elementem dla niższego poziomu hierarchii organizacji.</span><span class="sxs-lookup"><span data-stu-id="c9e52-178">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="c9e52-179">Pozycja jest pojedynczym wystąpieniem zadania.</span><span class="sxs-lookup"><span data-stu-id="c9e52-179">A position is an individual instance of a job.</span></span> <span data-ttu-id="c9e52-180">Na przykład stanowisko „Menedżer ds. sprzedaży (Wschód)” jest tylko jednym ze stanowisk skojarzonych z zadaniem „Menedżer ds. sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="c9e52-180">For example, the position, “Sales manager (East),” is just one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="c9e52-181">Stanowiska istnieją w działach i są przypisane do pracowników.</span><span class="sxs-lookup"><span data-stu-id="c9e52-181">Positions exist in a department and are assigned to workers.</span></span>
### <a name="position-creation-and-maintenance"></a><span data-ttu-id="c9e52-182">Tworzenie i obsługa pozycji</span><span class="sxs-lookup"><span data-stu-id="c9e52-182">Position creation and maintenance</span></span>

-   <span data-ttu-id="c9e52-183">Można wyświetlić historię zmian związanych z systemem na łatwo dostępnej stronie listy.</span><span class="sxs-lookup"><span data-stu-id="c9e52-183">You can view a history of position-related system changes in an easy-to-access list page.</span></span>
-   <span data-ttu-id="c9e52-184">Można tworzyć kody przyczyn, które użytkownicy mogą wybierać podczas tworzenia i modyfikowania stanowisk.</span><span class="sxs-lookup"><span data-stu-id="c9e52-184">You can create reason codes that your users can select when they create or modify positions.</span></span>
-   <span data-ttu-id="c9e52-185">Można tworzyć typy akcji dotyczących pracowników i przypisywać sekwencje numerów do tych akcji.</span><span class="sxs-lookup"><span data-stu-id="c9e52-185">You can create personnel action types and assign a number sequence to personnel actions.</span></span>
-   <span data-ttu-id="c9e52-186">Można ustawić przepływ pracy w taki sposób, by dodawanie pozycji i wprowadzanie zmian wymagało zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="c9e52-186">You can set up workflow so that position additions and changes can require approval.</span></span>

### <a name="position-duration"></a><span data-ttu-id="c9e52-187">Okres ważności stanowiska</span><span class="sxs-lookup"><span data-stu-id="c9e52-187">Position duration</span></span>

<span data-ttu-id="c9e52-188">Każda pozycja ma okres ważności.</span><span class="sxs-lookup"><span data-stu-id="c9e52-188">Every position has a length of time that the position is effective.</span></span> <span data-ttu-id="c9e52-189">Ten okres jest określany jako czas trwania.</span><span class="sxs-lookup"><span data-stu-id="c9e52-189">This length of time is referred to as duration.</span></span> <span data-ttu-id="c9e52-190">Na przykład letnie stanowiska mogą mieć czas trwania od 1 maja 2015 r. do 31 sierpnia 2015 r.</span><span class="sxs-lookup"><span data-stu-id="c9e52-190">For example, summer positions might have duration of May 1, 2015 until August 31, 2015.</span></span>

### <a name="worker-assignments"></a><span data-ttu-id="c9e52-191">Przypisania pracownika</span><span class="sxs-lookup"><span data-stu-id="c9e52-191">Worker assignments</span></span>

<span data-ttu-id="c9e52-192">Przypisanie pracownika do pozycji oznacza wypełnienie tej pozycji.</span><span class="sxs-lookup"><span data-stu-id="c9e52-192">When you assign a worker to a position, you fill that position.</span></span> <span data-ttu-id="c9e52-193">Pracowników można przypisać do wielu pozycji, ale jednocześnie do pozycji może być przypisany tylko jeden pracownik.</span><span class="sxs-lookup"><span data-stu-id="c9e52-193">You can assign workers to multiple positions, but only one worker can be assigned to a position at the same time.</span></span>

### <a name="reporting-relationships"></a><span data-ttu-id="c9e52-194">Relacje raportowania</span><span class="sxs-lookup"><span data-stu-id="c9e52-194">Reporting relationships</span></span>

<span data-ttu-id="c9e52-195">Pozycje są ważnymi elementami dla niższego poziomu hierarchii organizacji.</span><span class="sxs-lookup"><span data-stu-id="c9e52-195">Positions are important elements of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="c9e52-196">W formularzu Pozycje można określać pozycje nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c9e52-196">In the Position form, you can specify the position that a position reports to.</span></span> <span data-ttu-id="c9e52-197">Podczas przypisywania pracownika do pozycji podrzędnej względem innej pozycji, tworzy się relację raportowania między pracownikami przypisanymi do tych dwóch miejsc.</span><span class="sxs-lookup"><span data-stu-id="c9e52-197">When you assign a worker to a position that reports to another position, you create a reporting relationship between the workers who are assigned to the two positions.</span></span> <span data-ttu-id="c9e52-198">Na przykład pozycja „Księgowy-A” podlega pozycji „Kierownik rachunkowości”.</span><span class="sxs-lookup"><span data-stu-id="c9e52-198">For example, position “Accountant-A” reports to position “Accounting Supervisor”.</span></span> <span data-ttu-id="c9e52-199">Kim Akers jest przydzielona do pozycji „Kierownika rachunkowości”, a Sanjay Patel jest przypisany do pozycja „Księgowy-A”.</span><span class="sxs-lookup"><span data-stu-id="c9e52-199">Kim Akers is assigned to position “Accounting Supervisor” and Sanjay Patel is assigned to position “Accountant-A”.</span></span> <span data-ttu-id="c9e52-200">To znaczy, że Sanjay Patel podlega Kim Akers.</span><span class="sxs-lookup"><span data-stu-id="c9e52-200">This means that Sanjay Patel reports to Kim Akers.</span></span> 

<span data-ttu-id="c9e52-201">Jeśli organizacja korzysta z hierarchii macierzy lub innej hierarchii niestandardowej, można ustawić typy hierarchii pozycji i dodawać relacje raportowania do pozycji dla każdego konfigurowanego typu hierarchii.</span><span class="sxs-lookup"><span data-stu-id="c9e52-201">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span> <span data-ttu-id="c9e52-202">Na przykład Lori Penor jest kierownikiem głównym w Adventure Works i jest przypisana do pozycji „Kierownik główny”.</span><span class="sxs-lookup"><span data-stu-id="c9e52-202">For example, Lori Penor is a general manager at Adventure Works and is assigned to the “General Manager” position.</span></span> <span data-ttu-id="c9e52-203">Zarządza rozwojem produktu służącego do czyszczenia widżetów.</span><span class="sxs-lookup"><span data-stu-id="c9e52-203">Lori manages the development of a product that is used to clean widgets.</span></span> <span data-ttu-id="c9e52-204">Lori chce, aby księgowy pomagał jej przy finansach podczas opracowywania produktu.</span><span class="sxs-lookup"><span data-stu-id="c9e52-204">Lori requires an accountant to help her with the finances for developing the product.</span></span> <span data-ttu-id="c9e52-205">W związku z tym prosi Sanjaya Patela, by był jej księgowym.</span><span class="sxs-lookup"><span data-stu-id="c9e52-205">Therefore, she has recruited Sanjay Patel to be her accountant.</span></span> <span data-ttu-id="c9e52-206">Sanjay podlega bezpośrednio Kim Akers i jednocześnie współpracuje z Lori Penor przy finansowaniu programu do czyszczenia widżetów.</span><span class="sxs-lookup"><span data-stu-id="c9e52-206">Sanjay reports directly to Kim Akers, but also works with Lori Penor on his work related to the finances for developing the widget cleaner.</span></span> 

<span data-ttu-id="c9e52-207">W poprzednim przykładzie wykonaliśmy następujące zadania w celu skonfigurowania relacji roboczej między Sanjay Patel i Lori Penor:</span><span class="sxs-lookup"><span data-stu-id="c9e52-207">For the previous example, you would complete the following tasks to set up the working relationship between Sanjay Patel and Lori Penor:</span></span>
1.  <span data-ttu-id="c9e52-208">Utworzyliśmy niestandardowy typ pozycji o nazwie „Widżet”, by stworzyć hierarchię obejmującą pozycje dla osób pracujących przy projekcie programu do czyszczenia widżetów.</span><span class="sxs-lookup"><span data-stu-id="c9e52-208">Create a custom position hierarchy type called “Widget” to create a hierarchy that includes positions responsible for working on the widget cleaner product.</span></span>
2.  <span data-ttu-id="c9e52-209">Przypisaliśmy pozycję Kierownika głównego jako nadrzędne względem pozycji Księgowego-A w hierarchii Widżet.</span><span class="sxs-lookup"><span data-stu-id="c9e52-209">Assign the General Manager position to be the position that the Accountant-A position reports to in the Widget hierarchy.</span></span>

<span data-ttu-id="c9e52-210">Hierarchia pozycji służy do wyświetlania struktury relacji służbowych pozycji.</span><span class="sxs-lookup"><span data-stu-id="c9e52-210">Use the position hierarchy to view the reporting structure of positions.</span></span> <span data-ttu-id="c9e52-211">Jeśli masz wiele hierarchii pozycji, można wyświetlić hierarchię dla każdego typu hierarchii w hierarchii pozycji.</span><span class="sxs-lookup"><span data-stu-id="c9e52-211">If you have multiple position hierarchies, you can view the hierarchy for each hierarchy type in the position hierarchy.</span></span> <span data-ttu-id="c9e52-212">Można też wyszukiwać pozycje według identyfikatora lub nazwy pracownika, który jest przypisany do pozycji.</span><span class="sxs-lookup"><span data-stu-id="c9e52-212">Also, you can search for a position by position ID or by the name of the worker who is assigned to the position.</span></span> <span data-ttu-id="c9e52-213">Hierarchia pozycji jest hierarchią organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="c9e52-213">The position hierarchy is an organizational hierarchy.</span></span>

## <a name="date-effective-records"></a><span data-ttu-id="c9e52-214">Rekordy efektywne dat</span><span class="sxs-lookup"><span data-stu-id="c9e52-214">Date effective records</span></span>
<span data-ttu-id="c9e52-215">Dla niektórych rekordów można określić przyszłe zmiany w rekordzie.</span><span class="sxs-lookup"><span data-stu-id="c9e52-215">For some records, you can specify future changes to the record.</span></span> <span data-ttu-id="c9e52-216">Następujące informacje są uzależnione od dat obowiązywania.</span><span class="sxs-lookup"><span data-stu-id="c9e52-216">The following information is date effective.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c9e52-217">Rekordy</span><span class="sxs-lookup"><span data-stu-id="c9e52-217">Records</span></span></th>
<th><span data-ttu-id="c9e52-218">Informacje uzależnione od daty obowiązywania</span><span class="sxs-lookup"><span data-stu-id="c9e52-218">Date effective information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c9e52-219">Zadania</span><span class="sxs-lookup"><span data-stu-id="c9e52-219">Jobs</span></span></td>
<td><ul>
<li><span data-ttu-id="c9e52-220">Wybrane szczegółowe informacje o zadaniu</span><span class="sxs-lookup"><span data-stu-id="c9e52-220">Some detailed job information</span></span></li>
<li><span data-ttu-id="c9e52-221">Informacje o klasyfikacji zadań</span><span class="sxs-lookup"><span data-stu-id="c9e52-221">Job classification information</span></span></li>
<li><span data-ttu-id="c9e52-222">Informacje o wynagrodzeniach</span><span class="sxs-lookup"><span data-stu-id="c9e52-222">Compensation information</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c9e52-223">Pozycje</span><span class="sxs-lookup"><span data-stu-id="c9e52-223">Positions</span></span></td>
<td><ul>
<li><span data-ttu-id="c9e52-224">Wybrane szczegółowe informacje o pozycji</span><span class="sxs-lookup"><span data-stu-id="c9e52-224">Some detailed position information</span></span></li>
<li><span data-ttu-id="c9e52-225">Przypisania pracownika</span><span class="sxs-lookup"><span data-stu-id="c9e52-225">Worker assignments</span></span></li>
<li><span data-ttu-id="c9e52-226">Okresy ważności stanowisk</span><span class="sxs-lookup"><span data-stu-id="c9e52-226">Position durations</span></span></li>
<li><span data-ttu-id="c9e52-227">Hierarchie stanowisk</span><span class="sxs-lookup"><span data-stu-id="c9e52-227">Position hierarchies</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c9e52-228">Można modyfikować informacje wymienione w poprzedniej tabeli dla pozycji lub zadania i określić datę, kiedy modyfikacja pozycji lub zadania ma zacząć obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="c9e52-228">You can modify the information mentioned in the previous table for a position or a job and specify a date when the modifications to the position or job should take effect.</span></span> <span data-ttu-id="c9e52-229">Na przykład pozycja może być przypisana tylko do jednego pracownika, ale Sanjay Patel, który jest przypisany do stanowiska Księgowy-A, odchodzi za dwa tygodnie.</span><span class="sxs-lookup"><span data-stu-id="c9e52-229">For example, a position can only be assigned to one worker, but Sanjay Patel, who is assigned to the position Accountant-A, will be leaving in two weeks.</span></span> <span data-ttu-id="c9e52-230">Zastąpi go Joe Healy.</span><span class="sxs-lookup"><span data-stu-id="c9e52-230">Joe Healy will replace Sanjay Patel when he leaves.</span></span> <span data-ttu-id="c9e52-231">Mimo że Sanjay jest nadal przypisany do pozycji, Joe Healy może zostać przypisany do tej samej pozycji w taki sposób, by przypisanie zaczęło obowiązywać dopiero po odejściu Sanjaya z firmy.</span><span class="sxs-lookup"><span data-stu-id="c9e52-231">Even though Sanjay is still assigned to his position, you can assign Joe Healy to the same position so that the assignment is effective only after Sanjay’s last day.</span></span>






