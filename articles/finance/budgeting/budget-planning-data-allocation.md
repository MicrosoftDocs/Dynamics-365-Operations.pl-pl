---
title: Alokacja danych na potrzeby planowania budżetu
description: W tym temacie opisano różne metody alokacji dostępne w Microsoft Dynamics 365 Finance oraz sposoby ich wykorzystywania.
author: ShylaThompson
manager: AnnBe
ms.date: 03/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b07a0f59dfba1cc38133f0cc8ea02e0515f43443
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971260"
---
# <a name="budget-planning-data-allocation"></a><span data-ttu-id="f2338-103">Alokacja danych na potrzeby planowania budżetu</span><span class="sxs-lookup"><span data-stu-id="f2338-103">Budget planning data allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2338-104">W tym temacie opisano różne metody alokacji dostępne w Microsoft Dynamics 365 Finance oraz sposoby ich wykorzystywania.</span><span class="sxs-lookup"><span data-stu-id="f2338-104">This topic describes the allocation methods that are available in Microsoft Dynamics 365 Finance and how they can be used.</span></span>  

<span data-ttu-id="f2338-105">Dane planu budżetu można dystrybuować na wiele sposobów, by dokładnie odzwierciedlić przewidywane kwoty.</span><span class="sxs-lookup"><span data-stu-id="f2338-105">You can distribute the data in a budget plan in a number of ways to accurately portray the projected amounts.</span></span>

## <a name="allocation-methods"></a><span data-ttu-id="f2338-106">Metody alokacji</span><span class="sxs-lookup"><span data-stu-id="f2338-106">Allocation methods</span></span>
<span data-ttu-id="f2338-107">Za pomocą trzech metod alokacji (Alokuj między okresami, Alokuj do wymiarów i Użyj reguł alokacji księgi) można utworzyć wiersze planu budżetu oparte na wierszach w tym samym planie budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-107">Three allocation methods (Allocate across periods, Allocate to dimensions, and Use ledger allocation rules) can create budget plan lines that are based on lines in the same budget plan.</span></span> <span data-ttu-id="f2338-108">Za pomocą trzech innych metod (Agreguj, Dystrybuuj i Kopiuj z planu budżetu) można utworzyć wiersze planu budżetu w innych planach budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-108">Three other methods (Aggregate, Distribute, and Copy from budget plan) can create budget plan lines in other budget plans.</span></span> <span data-ttu-id="f2338-109">We wszystkich sześciu metodach alokacji można określić scenariusza docelowy.</span><span class="sxs-lookup"><span data-stu-id="f2338-109">For all six allocation methods, you specify the destination scenario.</span></span> <span data-ttu-id="f2338-110">Scenariusz docelowy może być albo taki sam jak scenariusz źródłowy lub inny od scenariusza źródłowego.</span><span class="sxs-lookup"><span data-stu-id="f2338-110">The destination scenario can be either the same as the source scenario or different from the source scenario.</span></span> <span data-ttu-id="f2338-111">Ponadto można określić, czy nowe wiersze są dołączane do planu budżetu czy zastępują bieżące wiersze planu budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-111">Additionally, you can specify whether new lines are appended to the budget plan or replace the current lines in the budget plan.</span></span>

> [!NOTE] 
> <span data-ttu-id="f2338-112">W celu agregacji, który jest inny niż scenariusz używany do dystrybucji lub innych modyfikacji wykonanych wcześniej w planie nadrzędnym, należy używać unikatowego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="f2338-112">A unique scenario should be used for aggregation that is different from the scenario that was used for distribution or other modifications that were previously performed  in the parent plan.</span></span>  

<span data-ttu-id="f2338-113">[![Alokacja między okresami metodą alokacji](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Alokuj między okresami** — Kategoria alokacji okresu jest używana do alokacji wierszy planu budżetu ze źródłowego scenariusza planu budżetu między okresy w scenariuszu docelowym.</span><span class="sxs-lookup"><span data-stu-id="f2338-113">[![Allocate across Periods allocation method](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Allocate across periods** – A period allocation category is used to allocate the budget plan lines from the source budget plan scenario across periods in the destination scenario.</span></span> <span data-ttu-id="f2338-114">Kwota źródłowa jest przypisywana do wielu wierszy w scenariuszu docelowym na podstawie wartości procentowej i danych zdefiniowanych w kategorii alokacji okresu.</span><span class="sxs-lookup"><span data-stu-id="f2338-114">The source amount is assigned to multiple lines in the destination scenario, based on the percentage and date that are defined in the period allocation category.</span></span>         

<span data-ttu-id="f2338-115">[![Alokacja do wymiarów metodą alokacji](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Alokuj do wymiarów** — wiersze planu budżetu są alokowane ze scenariusza źródłowego planowania budżetu do jednego lub kilku wierszy w scenariuszu docelowym na podstawie wartości procentowych i wymiarów finansowych, które są zdefiniowane w wybranym warunku alokacji budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-115">[![Allocate to Dimensions allocation method](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Allocate to dimensions** – The budget plan lines are allocated from the source budget planning scenario to one or more lines in the destination scenario, based on the percentages and financial dimensions that are defined in a selected budget allocation term.</span></span>           

<span data-ttu-id="f2338-116">![Agregowanie wykresu](./media/aggregatechart-300x230.png)
**Agreguj** — agregowanie wierszy planu budżetu następuje ze źródłowego scenariusza planu budżetu w powiązanych (podrzędnych) planach budżetu do docelowego scenariusza w nadrzędnym planie budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-116">![Aggregate chart](./media/aggregatechart-300x230.png)
**Aggregate** – The budget plan lines are aggregated from the source budget plan scenario in the associated (child) budget plans to the destination scenario in the parent budget plan.</span></span> <span data-ttu-id="f2338-117">Ta metoda umożliwia konsolidowanie z wyższym poziomem kwot budżetowych przygotowywanych na niższym poziomie organizacji.</span><span class="sxs-lookup"><span data-stu-id="f2338-117">This method enables budget amounts that are prepared at a lower level in the organization to be consolidated at a higher level.</span></span>          

<span data-ttu-id="f2338-118">[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Dystybuowanie wykresu** — wiersze planu budżetu są rozdzielane ze scenariusza źródłowego planowania budżetu w nadrzędnym planie budżetu do scenariusza docelowego w skojarzonych planach budżetu (podrzędnych) na podstawie wymiarów finansowych jednostek organizacyjnych skojarzonych planów.</span><span class="sxs-lookup"><span data-stu-id="f2338-118">[![Distribute chart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Distribute** – The budget plan lines are distributed from the source budget planning scenario in the parent budget plan to the destination scenario in the associated (child) budget plans, based on the financial dimensions of the organization units of the associated plans.</span></span> <span data-ttu-id="f2338-119">Ta metoda umożliwia rozkładanie do kontroli lokalnej kwot budżetowych przygotowywanych na wyższym poziomie organizacji.</span><span class="sxs-lookup"><span data-stu-id="f2338-119">This method enables budget amounts that are prepared at a higher level in the organization to be spread out for more localized review.</span></span>           

<span data-ttu-id="f2338-120">[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Reguły alokacji księgi** — rozdzielanie wierszy planu budżetu następuje ze źródłowego scenariusza planowania budżetu do docelowego scenariusza planu budżetu na podstawie wybranej reguły alokacji księgi.</span><span class="sxs-lookup"><span data-stu-id="f2338-120">[![Ledger allocation rules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Use ledger allocation rules** – The budget plan lines are distributed from the source budget planning scenario to the destination scenario, based on the ledger allocation rule that is selected.</span></span> 

<span data-ttu-id="f2338-121">[![Kopiuj z planu budżetowego](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Kopiuj z planu budżetu** — tak jak w metodzie dystrybucji alokacji wiersze planu budżetu są tworzone w lokalizacji docelowej na podstawie wierszy w powiązanym planie budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-121">[![Copy from budget plan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Copy from budget plan** – As in the Distribute allocation method, budget plan lines are created in the destination, based on lines in a related budget plan.</span></span> <span data-ttu-id="f2338-122">Jednak w tej metodzie źródłowy plan budżetu nie musi być elementem nadrzędnym, ale może być na dowolnym wyższym poziomie w hierarchii planów budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-122">However, for this method, the source budget plan doesn't have to be the parent but can be at any higher level in the budget plan hierarchy.</span></span> <span data-ttu-id="f2338-123">Ta metoda alokacji jest użyteczna, jeśli skonsolidowane kwoty są pierwotnie budżetowane na dużo wyższym poziomie, i muszą być przekazywane na niższy poziom organizacji do szczegółowego sprawdzenia i korekty, zanim będą mogły zostać zatwierdzone na wyższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="f2338-123">This allocation method is useful if consolidated amounts are originally budgeted at a much higher level, and must be transferred to a lower level of the organization for detailed review and adjustment before they can receive upper-level approval.</span></span>          

## <a name="using-allocation-methods-in-a-budget-plan"></a><span data-ttu-id="f2338-124">Korzystanie z metod alokacji w planie budżetu</span><span class="sxs-lookup"><span data-stu-id="f2338-124">Using allocation methods in a budget plan</span></span>
<span data-ttu-id="f2338-125">Aby wykonać alokacje na stronie plan budżetu, wybierz wiersze do alokowania, a następnie kliknij przycisk **Alokuj budżet**.</span><span class="sxs-lookup"><span data-stu-id="f2338-125">To perform allocations on the budget plan page, select the lines to allocate, and then click **Allocate budget**.</span></span>

<span data-ttu-id="f2338-126">[![Przycisk alokowania budżetu](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png)</span><span class="sxs-lookup"><span data-stu-id="f2338-126">[![Allocate budget button](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png)</span></span> 

<span data-ttu-id="f2338-127">Następnie wybierz metodę alokacji.</span><span class="sxs-lookup"><span data-stu-id="f2338-127">Next, select an allocation method.</span></span> <span data-ttu-id="f2338-128">Pozostałe pola są następnie ustawiane na podstawie wybranej metody.</span><span class="sxs-lookup"><span data-stu-id="f2338-128">The remaining fields are then set, based on the method that you selected.</span></span> <span data-ttu-id="f2338-129">Te pola uwzględniają źródło i lokalizację docelową danych planu budżetu oraz opcję mnożenia źródeł przez określony współczynnik podczas tworzenia kwoty docelowej, aby uprościć korekty wsadowe.</span><span class="sxs-lookup"><span data-stu-id="f2338-129">These fields include the source and destination of the budget plan data, and an option that lets you multiply the source by a specified factor when the destination amounts are created, to simplify bulk adjustment.</span></span> <span data-ttu-id="f2338-130">Można również ustawić opcję **Dołącz do planu**.</span><span class="sxs-lookup"><span data-stu-id="f2338-130">You can also set the **Append to plan** option.</span></span> <span data-ttu-id="f2338-131">Wybierz **Nie**, aby zastąpić istniejące wiersze planu budżetu lub wybierz **Tak**, aby zachować istniejące wiersze planu budżetu i dodać nowe wiersze dla alokowanych kwot.</span><span class="sxs-lookup"><span data-stu-id="f2338-131">Select **No** to replace the existing budget plan lines, or select **Yes** to retain the existing budget plan lines and add new lines for the allocated amounts.</span></span>

## <a name="automating-allocations-during-a-workflow"></a><span data-ttu-id="f2338-132">Automatyzacja alokacji podczas przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="f2338-132">Automating allocations during a workflow</span></span>
<span data-ttu-id="f2338-133">Jedna zaawansowana funkcja pozwala wykonywać alokacje automatycznie w ramach przepływu pracy planowania budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-133">One powerful feature enables allocations to be performed automatically as part of a budget planning workflow.</span></span> <span data-ttu-id="f2338-134">W miarę realizacji przepływu pracy planu budżetu zautomatyzowane zadania mogą wywoływać alokację na określonym etapie planowania budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-134">As a budget plan moves through its workflow, automated tasks can invoke an allocation at a specified budget planning stage.</span></span> 

<span data-ttu-id="f2338-135">Aby skonfigurować automatyczne alokacje, należy najpierw utworzyć harmonogram alokacji na stronie **Konfiguracja planowania budżetu**.</span><span class="sxs-lookup"><span data-stu-id="f2338-135">To set up automated allocation, you must first create an allocation schedule on the **Budget planning configuration** page.</span></span> <span data-ttu-id="f2338-136">Harmonogram alokacji definiuje metodę alokacji, która będzie używana podczas automatycznego alokowania oraz wartości różnych opcji alokacji (opisy znajdują się w poprzedniej sekcji).</span><span class="sxs-lookup"><span data-stu-id="f2338-136">The allocation schedule defines the allocation method that will be used when the automated allocation is run, and the values of the various allocation options (see the previous section for descriptions).</span></span> 

<span data-ttu-id="f2338-137">Następnie należy utworzyć alokację etapu na stronie **Konfiguracja planowania budżetu**.</span><span class="sxs-lookup"><span data-stu-id="f2338-137">Next, you create a stage allocation on the **Budget planning configuration** page.</span></span> <span data-ttu-id="f2338-138">Alokacja etapu przypisuje harmonogram alokacji do przepływu pracy i etapu planowania budżetu.</span><span class="sxs-lookup"><span data-stu-id="f2338-138">The stage allocation assigns an allocation schedule to the budget planning workflow and stage.</span></span> 

<span data-ttu-id="f2338-139">Na koniec należy dodać zautomatyzowane zadanie dla alokacji etapu planowania budżetu na wybranych etapie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f2338-139">Finally, add an automated task for budget planning stage allocation at the desired workflow stage.</span></span> <span data-ttu-id="f2338-140">W poniższym przykładzie dwie alokacje etapu planowania budżetu (wyróżnione na czerwono) zostały wstawione do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f2338-140">In the following example, two budget planning stage allocations (outlined in red) have been inserted into the workflow.</span></span>

<span data-ttu-id="f2338-141">[![Alokacje etapu planowania budżetu](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)</span><span class="sxs-lookup"><span data-stu-id="f2338-141">[![Budget planning stage allocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)</span></span>



