---
title: Zadania serwisowe
description: "Zadania serwisowe służą do opisywania zadań, które mają zostać wykonane podczas zlecenia serwisowego. Te informacje są widoczne zarówno dla techników, jak i klientów."
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6504fa18fe983607f74670e043ae6713b3d5a7af
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="service-tasks"></a><span data-ttu-id="3f9ff-104">Zadania serwisowe</span><span class="sxs-lookup"><span data-stu-id="3f9ff-104">Service tasks</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3f9ff-105">Zadania serwisowe służą do opisywania zadań, które mają zostać wykonane podczas zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-105">Use service tasks to describe the task to be completed during a service order.</span></span>
<span data-ttu-id="3f9ff-106">Te informacje są widoczne zarówno dla techników, jak i klientów.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-106">Both technicians and customers can see this information.</span></span>

<span data-ttu-id="3f9ff-107">Zadania serwisowe tworzy się na stronie **Zadania serwisowe** i kojarzy z określoną umową serwisową lub zleceniem serwisowym przez utworzenie relacji zadania serwisowego.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-107">You create service tasks in the **Service tasks** page, and you associate service tasks with a specific service agreement or service order by creating service task relations.</span></span> <span data-ttu-id="3f9ff-108">Przy każdym tworzeniu relacji zadania serwisowego można utworzyć następujące obiekty:</span><span class="sxs-lookup"><span data-stu-id="3f9ff-108">Every time that you create a service task relation, you can create the following:</span></span>

-  <span data-ttu-id="3f9ff-109">Wewnętrzne notatki dotyczące zadania, na przykład szczegółowe wymagania techniczne dotyczące zadania, których znajomość jest istotna dla techników.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-109">Internal notes for the task, such as detailed technical requests for the task that are important for the technician to know.</span></span>

-  <span data-ttu-id="3f9ff-110">Zewnętrzne notatki widoczne dla klienta.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-110">External notes that the customer can see.</span></span> <span data-ttu-id="3f9ff-111">Mogą one zawierać mniej techniczne objaśnienie zadania, które jest wykonywane zgodnie z umową między klientem a firma serwisową.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-111">These might provide a less technical explanation of the task that is being completed, according to the agreement between the customer and the service company.</span></span>

<span data-ttu-id="3f9ff-112">Po skonfigurowaniu relacji między zadaniem serwisowym a zleceniem serwisowym lub umową serwisową można określić to zadanie serwisowe podczas tworzenia wierszy zlecenia serwisowego lub wierszy umowy serwisowej dla bieżącego zlecenia serwisowego lub umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-112">When you have set up a service task relation between a service task and a service order or service agreement, you can specify this service task when you create service order lines or service agreement lines for the current service order or service agreement.</span></span>

<span data-ttu-id="3f9ff-113">Podczas generowania zleceń serwisowych z umowy serwisowej można używać zadań serwisowych przypisanych do poszczególnych wierszy umowy serwisowej w celu grupowania wierszy zlecenia serwisowego w zlecenia serwisowe.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-113">When you generate service orders from a service agreement, you can use the service tasks that are assigned to each service agreement line to group service order lines into service orders.</span></span>

## <a name="create-a-service-task"></a><span data-ttu-id="3f9ff-114">Tworzenie zadania serwisowego</span><span class="sxs-lookup"><span data-stu-id="3f9ff-114">Create a service task</span></span>

1. <span data-ttu-id="3f9ff-115">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Zadania serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-115">Click **Service management** \> **Setup** \> **Service tasks**.</span></span>
2. <span data-ttu-id="3f9ff-116">Utwórz nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-116">Create a new line.</span></span>
3. <span data-ttu-id="3f9ff-117">Wprowadź identyfikator i opis usługi.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-117">Enter the service ID and description.</span></span>

## <a name="example"></a><span data-ttu-id="3f9ff-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="3f9ff-118">Example</span></span>

<span data-ttu-id="3f9ff-119">Technik musi wykonać dwie prace związane ze skrzynią biegów (przedmiot serwisu GB-1234) na miejscu u klienta.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-119">A technician must complete two jobs on a gearbox (service object GB-1234) at a customer site.</span></span> <span data-ttu-id="3f9ff-120">Dla klienta zostaje utworzona umowa serwisowa, a z pracami zostaje skojarzonych klika transakcji.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-120">A service agreement is created for the customer, and several transactions are associated with the jobs.</span></span> <span data-ttu-id="3f9ff-121">Oto umowa serwisowa i wiersze umowy serwisowej dotyczące tych dwóch prac:</span><span class="sxs-lookup"><span data-stu-id="3f9ff-121">The service agreement and service agreement lines for the two jobs are as follows:</span></span>

### <a name="service-agreement"></a><span data-ttu-id="3f9ff-122">Umowa serwisowa</span><span class="sxs-lookup"><span data-stu-id="3f9ff-122">Service agreement</span></span>

| <span data-ttu-id="3f9ff-123">Project</span><span class="sxs-lookup"><span data-stu-id="3f9ff-123">Project</span></span> | <span data-ttu-id="3f9ff-124">Umowa serwisowa</span><span class="sxs-lookup"><span data-stu-id="3f9ff-124">Service agreement</span></span> | <span data-ttu-id="3f9ff-125">opis</span><span class="sxs-lookup"><span data-stu-id="3f9ff-125">Description</span></span>                                  | <span data-ttu-id="3f9ff-126">Grupa</span><span class="sxs-lookup"><span data-stu-id="3f9ff-126">Group</span></span>   |
|---------|-------------------|----------------------------------------------|---------|
| <span data-ttu-id="3f9ff-127">9012</span><span class="sxs-lookup"><span data-stu-id="3f9ff-127">9012</span></span>    | <span data-ttu-id="3f9ff-128">000008\_001</span><span class="sxs-lookup"><span data-stu-id="3f9ff-128">000008\_001</span></span>       | <span data-ttu-id="3f9ff-129">Przegląd i rutynowa wymiana — GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-129">Inspection and routine replacement – GB-1234</span></span> | <span data-ttu-id="3f9ff-130">Premia</span><span class="sxs-lookup"><span data-stu-id="3f9ff-130">Premium</span></span> |

### <a name="service-agreement-lines"></a><span data-ttu-id="3f9ff-131">Wiersze umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="3f9ff-131">Service agreement lines</span></span>

| <span data-ttu-id="3f9ff-132">opis</span><span class="sxs-lookup"><span data-stu-id="3f9ff-132">Description</span></span>             | <span data-ttu-id="3f9ff-133">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="3f9ff-133">Transaction type</span></span> | <span data-ttu-id="3f9ff-134">Przedmiot serwisu</span><span class="sxs-lookup"><span data-stu-id="3f9ff-134">Service object</span></span> | <span data-ttu-id="3f9ff-135">Zadanie serwisowe</span><span class="sxs-lookup"><span data-stu-id="3f9ff-135">Service task</span></span> |
|-------------------------|------------------|----------------|--------------|
| <span data-ttu-id="3f9ff-136">Przegląd i oczyszczenie</span><span class="sxs-lookup"><span data-stu-id="3f9ff-136">Inspection and cleaning</span></span> | <span data-ttu-id="3f9ff-137">Godzina</span><span class="sxs-lookup"><span data-stu-id="3f9ff-137">Hour</span></span>             | <span data-ttu-id="3f9ff-138">GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-138">GB-1234</span></span>        | <span data-ttu-id="3f9ff-139">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-139">I/C - GB1234</span></span> |
| <span data-ttu-id="3f9ff-140">Podróże</span><span class="sxs-lookup"><span data-stu-id="3f9ff-140">Travel</span></span>                  | <span data-ttu-id="3f9ff-141">Expense</span><span class="sxs-lookup"><span data-stu-id="3f9ff-141">Expense</span></span>          | <span data-ttu-id="3f9ff-142">GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-142">GB-1234</span></span>        | <span data-ttu-id="3f9ff-143">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-143">I/C - GB1234</span></span> |
| <span data-ttu-id="3f9ff-144">Materiały</span><span class="sxs-lookup"><span data-stu-id="3f9ff-144">Materials</span></span>               | <span data-ttu-id="3f9ff-145">Element</span><span class="sxs-lookup"><span data-stu-id="3f9ff-145">Item</span></span>             | <span data-ttu-id="3f9ff-146">GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-146">GB-1234</span></span>        | <span data-ttu-id="3f9ff-147">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-147">I/C - GB1234</span></span> |
| <span data-ttu-id="3f9ff-148">Rutynowa wymiana</span><span class="sxs-lookup"><span data-stu-id="3f9ff-148">Routine replacement</span></span>     | <span data-ttu-id="3f9ff-149">Godzina</span><span class="sxs-lookup"><span data-stu-id="3f9ff-149">Hour</span></span>             | <span data-ttu-id="3f9ff-150">GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-150">GB-1234</span></span>        | <span data-ttu-id="3f9ff-151">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-151">RR - GB1234</span></span>  |
| <span data-ttu-id="3f9ff-152">GR-1</span><span class="sxs-lookup"><span data-stu-id="3f9ff-152">GR-1</span></span>                    | <span data-ttu-id="3f9ff-153">Element</span><span class="sxs-lookup"><span data-stu-id="3f9ff-153">Item</span></span>             | <span data-ttu-id="3f9ff-154">GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-154">GB-1234</span></span>        | <span data-ttu-id="3f9ff-155">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-155">RR - GB1234</span></span>  |
| <span data-ttu-id="3f9ff-156">GR-5</span><span class="sxs-lookup"><span data-stu-id="3f9ff-156">GR-5</span></span>                    | <span data-ttu-id="3f9ff-157">Element</span><span class="sxs-lookup"><span data-stu-id="3f9ff-157">Item</span></span>             | <span data-ttu-id="3f9ff-158">GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-158">GB-1234</span></span>        | <span data-ttu-id="3f9ff-159">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-159">RR - GB1234</span></span>  |

<span data-ttu-id="3f9ff-160">W wierszach umowy serwisowej dla tych dwóch prac są określone dwa zadania serwisowe.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-160">The service agreement lines for the two jobs have two service tasks attached to them.</span></span> <span data-ttu-id="3f9ff-161">Zadania serwisowe określają transakcje, które należą do każdej pracy.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-161">The service tasks determine the transactions that belong to each job.</span></span> <span data-ttu-id="3f9ff-162">W pierwszym przypadku zadanie serwisowe I/C - GB1234 określa wszystkie wiersze umowy serwisowej związane z przeglądem i oczyszczeniem przedmiotu GB-1234.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-162">In the first case, service task I/C - GB1234 identifies all the service agreement lines that are involved in the inspection and cleaning of object GB-1234.</span></span> <span data-ttu-id="3f9ff-163">W drugim przypadku zadanie serwisowe RR - GB1234 określa wszystkie wiersze umowy serwisowej związane z przeprowadzeniem rutynowej wymiany.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-163">In the second case, service task RR - GB1234 identifies all the service agreement lines that are involved in completing a routine replacement job.</span></span>

<span data-ttu-id="3f9ff-164">Relacje zadań serwisowych łączące zadania serwisowe z określoną umową są następujące:</span><span class="sxs-lookup"><span data-stu-id="3f9ff-164">The service task relations that connect the service tasks to the specific agreement are as follows:</span></span>

### <a name="service-tasks"></a><span data-ttu-id="3f9ff-165">Zadania serwisowe</span><span class="sxs-lookup"><span data-stu-id="3f9ff-165">Service tasks</span></span>

| <span data-ttu-id="3f9ff-166">Zadanie serwisowe</span><span class="sxs-lookup"><span data-stu-id="3f9ff-166">Service task</span></span> | <span data-ttu-id="3f9ff-167">Opis</span><span class="sxs-lookup"><span data-stu-id="3f9ff-167">Description</span></span>                             | <span data-ttu-id="3f9ff-168">Notatka wewnętrzna</span><span class="sxs-lookup"><span data-stu-id="3f9ff-168">Internal note</span></span>                                                                                                                 | <span data-ttu-id="3f9ff-169">Notatka zewnętrzna</span><span class="sxs-lookup"><span data-stu-id="3f9ff-169">External note</span></span>                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| <span data-ttu-id="3f9ff-170">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-170">I/C - GB1234</span></span> | <span data-ttu-id="3f9ff-171">Przegląd skrzyni biegów GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-171">Inspection of gearbox GB-1234</span></span>           | <span data-ttu-id="3f9ff-172">Wzrokowy i mechaniczny przegląd oraz oczyszczenie skrzyni biegów GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-172">Visual and mechanical inspection and cleaning of gearbox GB-1234</span></span>                                                              | <span data-ttu-id="3f9ff-173">Rutynowy przegląd skrzyni biegów</span><span class="sxs-lookup"><span data-stu-id="3f9ff-173">Routine inspection of gearbox</span></span> |
| <span data-ttu-id="3f9ff-174">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-174">RR - GB1234</span></span>  | <span data-ttu-id="3f9ff-175">Rutynowa wymiana części w skrzyni biegów GB-1234</span><span class="sxs-lookup"><span data-stu-id="3f9ff-175">Routine replacement of parts in GB-1234</span></span> | <span data-ttu-id="3f9ff-176">Rutynowa wymiana części GR-1 i GR-5 (skrzyń biegów wyprodukowanych przed 2002 rokiem dotyczy również wymiana części GR-2)</span><span class="sxs-lookup"><span data-stu-id="3f9ff-176">Routine service replacement of GR-1 and GR-5 components (for gearboxes manufactured before 2002, also replace GR-2 component)</span></span> | <span data-ttu-id="3f9ff-177">Rutynowa wymiana części</span><span class="sxs-lookup"><span data-stu-id="3f9ff-177">Routine replacement of parts</span></span>  |

## <a name="group-service-orders"></a><span data-ttu-id="3f9ff-178">Grupowanie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="3f9ff-178">Group service orders</span></span>

<span data-ttu-id="3f9ff-179">W przypadku automatycznego tworzenia zleceń serwisowych zadania serwisowe mogą służyć jako kryteria grupowania.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-179">When you create service orders automatically, you can use service tasks as grouping criteria.</span></span> <span data-ttu-id="3f9ff-180">Aby pogrupować zlecenia serwisowe według zadań serwisowych, należy określić w umowie serwisowej, że oparte na niej zlecenia serwisowe powinny być grupowane najpierw według identyfikatorów zadań serwisowych.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-180">To group service orders by service tasks, define on the service agreement that service orders that are based on the service agreement should be grouped by service task ID as their initial grouping criteria.</span></span>

<span data-ttu-id="3f9ff-181">**Grupowanie według zadań serwisowych**</span><span class="sxs-lookup"><span data-stu-id="3f9ff-181">**Group by service task**</span></span>

1. <span data-ttu-id="3f9ff-182">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-182">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>
2. <span data-ttu-id="3f9ff-183">Na karcie **Ustawienia** w polu **Łączenie zleceń serwisowych** wybierz opcję **Według zadania serwisowego**.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-183">On the **Setup** tab, select **By service task** in the **Combine service orders** field.</span></span>



