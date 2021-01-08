---
title: Aktualizowanie budżetu konserwacji
description: W tym temacie wyjaśniono, jak aktualizować budżet konserwacji w zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e43abd4644eec8c91606ec48bbecf30f12600856
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435286"
---
# <a name="update-maintenance-budgets"></a><span data-ttu-id="327fc-103">Aktualizowanie budżetu konserwacji</span><span class="sxs-lookup"><span data-stu-id="327fc-103">Update maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="327fc-104">Na stronie **Wiersze budżetu konserwacji** są wyświetlane wszystkie wiersze budżetu, które zostały utworzone dla budżetu wybranego na stronie **Budżety konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="327fc-104">The **Maintenance budget lines** page shows all the budget lines that have been created for the budget that is selected on the **Maintenance budgets** page.</span></span> <span data-ttu-id="327fc-105">(Aby uzyskać więcej informacji, przejrzyj temat [Tworzenie budżetu konserwacji](create-maintenance-budget.md)) wiersze budżetu konserwacji można ponownie obliczyć i skorygować do momentu zatwierdzenia budżetu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="327fc-105">(For more information, see [Create maintenance budgets](create-maintenance-budget.md).) You can recalculate and adjust maintenance budget lines until the maintenance budget is approved.</span></span> <span data-ttu-id="327fc-106">Po upływie okresu budżetu i zaksięgowaniu kosztów w module Zarządzanie składnikami majątku można również zaktualizować wiersze budżetu o koszty rzeczywiste.</span><span class="sxs-lookup"><span data-stu-id="327fc-106">After the budget period has passed, and costs have been posted in Asset Management, you can also update the budget lines with actual costs.</span></span>

## <a name="recalculate-a-maintenance-budget"></a><span data-ttu-id="327fc-107">Oblicz ponownie budżet konserwacji</span><span class="sxs-lookup"><span data-stu-id="327fc-107">Recalculate a maintenance budget</span></span>

<span data-ttu-id="327fc-108">Budżet obsługi można ponownie obliczyć na stronie **Wiersze budżetu konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="327fc-108">You can recalculate a maintenance budget on the **Maintenance budget lines** page.</span></span> <span data-ttu-id="327fc-109">Podczas ponownego obliczania budżetu obsługi są usuwane istniejące wiersze budżetu i wykonywane jest nowe obliczanie.</span><span class="sxs-lookup"><span data-stu-id="327fc-109">When you recalculate a maintenance budget, the existing budget lines are deleted, and a new calculation is done.</span></span>

1. <span data-ttu-id="327fc-110">Na stronie **Wiersze budżetu konserwacji** wybierz opcję **Oblicz ponownie.**</span><span class="sxs-lookup"><span data-stu-id="327fc-110">On the **Maintenance budget lines** page, select **Recalculate**.</span></span>
2. <span data-ttu-id="327fc-111">W oknie dialogowym **Ponowne obliczanie** budżetu wprowadź wymagane zmiany w nowych obliczeniach, a następnie kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="327fc-111">In the **Recalculate budget** dialog box, make the required changes for the new calculation, and then select **OK**.</span></span>

<span data-ttu-id="327fc-112">Nowe wiersze budżetu są tworzone zgodnie z ustawionymi wartościami.</span><span class="sxs-lookup"><span data-stu-id="327fc-112">New budget lines are created according to the values that you set.</span></span>

## <a name="adjust-budget-lines"></a><span data-ttu-id="327fc-113">Korygowanie wierszy budżetu</span><span class="sxs-lookup"><span data-stu-id="327fc-113">Adjust budget lines</span></span>

<span data-ttu-id="327fc-114">Zamiast ponownego obliczania całego budżetu konserwacji można skorygować wybrane wiersze związane z kosztami budżetowymi.</span><span class="sxs-lookup"><span data-stu-id="327fc-114">Instead of recalculating the whole maintenance budget, you can adjust selected lines that are related to budget costs.</span></span>

1. <span data-ttu-id="327fc-115">Na stronie **Wiersze budżetu konserwacji** wybierz wiersze, dla których ma zostać zaktualizowany koszt budżetowy.</span><span class="sxs-lookup"><span data-stu-id="327fc-115">On the **Maintenance budget lines** page, select the lines to update the budget cost for.</span></span>
2. <span data-ttu-id="327fc-116">Wybierz **Dostosuj**.</span><span class="sxs-lookup"><span data-stu-id="327fc-116">Select **Adjust**.</span></span>
3. <span data-ttu-id="327fc-117">Aby dodać kwotę do wybranych wierszy, zaznacz pole wyboru **Dodaj koszt**, a następnie wprowadź wartość w polu **Dodaj wartość**.</span><span class="sxs-lookup"><span data-stu-id="327fc-117">To add an amount to the selected lines, select the **Add cost** check box, and then enter the value in the **Add value** field.</span></span>
4. <span data-ttu-id="327fc-118">Aby pomnożyć koszt budżetowy w wybranych wierszach budżetu przez współczynnik, zaznacz pole wyboru **pomnóż koszt** i wprowadź współczynnik w polu **mnożenie wartości**.</span><span class="sxs-lookup"><span data-stu-id="327fc-118">To multiply the budget cost on the selected budget lines by a factor, select the **Multiply cost** check box, and enter the factor in the **Multiply value** field.</span></span>

    <span data-ttu-id="327fc-119">Jeśli na przykład w polu **mnożenie wartości** wprowadzono wartość **1,2** koszt budżetowy zostanie zwiększony w wybranych wierszach o 20 procent.</span><span class="sxs-lookup"><span data-stu-id="327fc-119">For example, if you enter **1.2** in the **Multiply value** field, you increase the budget cost on the selected lines by 20 percent.</span></span> <span data-ttu-id="327fc-120">W przypadku wprowadzenia wartości **0,7** koszt budżetowy jest redukowany w wybranych wierszach o 30 procent.</span><span class="sxs-lookup"><span data-stu-id="327fc-120">If you enter **0.7**, you reduce the budget cost on the selected lines by 30 percent.</span></span>

5. <span data-ttu-id="327fc-121">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="327fc-121">Select **OK**.</span></span>

<span data-ttu-id="327fc-122">Wybrane wiersze budżetu są aktualizowane zgodnie z wartościami określonymi w kroku 3 lub 4.</span><span class="sxs-lookup"><span data-stu-id="327fc-122">The selected budget lines are updated according to the values that you set in step 3 or 4.</span></span>

## <a name="update-actual-costs"></a><span data-ttu-id="327fc-123">Aktualizuj koszty rzeczywiste</span><span class="sxs-lookup"><span data-stu-id="327fc-123">Update actual costs</span></span>

<span data-ttu-id="327fc-124">Po upływie dat w wierszach budżetu i zaksięgowaniu kosztów rzeczywistych w module Zarządzanie składnikami majątku można również zaktualizować wiersze budżetu o koszty rzeczywiste.</span><span class="sxs-lookup"><span data-stu-id="327fc-124">After the dates on the budget lines have passed, and actual costs have been posted in Asset Management, you can update the actual costs on the maintenance budget.</span></span>

1. <span data-ttu-id="327fc-125">Na stronie **Wiersze budżetu konserwacji** wybierz opcję **Aktualizuj koszt**.</span><span class="sxs-lookup"><span data-stu-id="327fc-125">On the **Maintenance budget lines** page, select **Update cost**.</span></span>
2. <span data-ttu-id="327fc-126">W oknie dialogowym **Oblicz rzeczywisty koszt** wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="327fc-126">In the **Calculate actual cost** dialog box, select **OK**.</span></span>

<span data-ttu-id="327fc-127">Pola **koszt rzeczywisty** w wierszach budżetu są aktualizowane, jeśli koszty rzeczywiste zostały zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="327fc-127">The **Actual cost** fields on the budget lines are updated if actual costs have been posted.</span></span> <span data-ttu-id="327fc-128">Nowe wiersze budżetu mogą zostać wygenerowane, jeśli zostały utworzone nowe typy środków od momentu utworzenia budżetu, oraz jeśli te typy środków trwałych zostały użyte w środkach trwałych, dla których zostały zaksięgowane i pokrewne koszty</span><span class="sxs-lookup"><span data-stu-id="327fc-128">New budget lines might be generated if new asset types have been created since you created the budget, and if those asset types have been used on assets that work orders have been created for and related costs have been posted for.</span></span> <span data-ttu-id="327fc-129">W nowych wierszach budżetu są wyświetlane tylko koszty rzeczywiste, ponieważ nie zostały dla nich obliczone koszty budżetowe.</span><span class="sxs-lookup"><span data-stu-id="327fc-129">New budget lines show only actual costs, because no budget costs were calculated for them.</span></span>

> [!NOTE]
> <span data-ttu-id="327fc-130">Aby wyświetlić przegląd kosztów rzeczywistych podzielonych na koszty dodatkowe, korygujące i inwestycyjne, można wykonać obliczenia dla tego samego okresu na stronie **Formant kosztów składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="327fc-130">To see an overview of actual costs divided into preventive, corrective, and investment costs, you can do a calculation for the same period on the **Asset cost control** page.</span></span> 

## <a name="manually-add-budget-lines"></a><span data-ttu-id="327fc-131">Ręczne dodawanie wierszy planu budżetu</span><span class="sxs-lookup"><span data-stu-id="327fc-131">Manually add budget lines</span></span>

<span data-ttu-id="327fc-132">Na stronie **Wiersze budżetu konserwacji** można ręcznie dodać nowy wiersz budżetu, wybierając opcję **nowy**, a następnie dokonując wyboru w wierszu.</span><span class="sxs-lookup"><span data-stu-id="327fc-132">On the **Maintenance budget lines** page, you can manually add a new budget line by selecting **New** and then making selections on the line.</span></span> <span data-ttu-id="327fc-133">Oto kilka przykładów sytuacji, w których takie rozwiązanie może być użyteczne:</span><span class="sxs-lookup"><span data-stu-id="327fc-133">Here are some examples of situations where this approach might be useful:</span></span>

- <span data-ttu-id="327fc-134">Wiadomo, że odnawianiem niektórych środków trwałych znajduje się obecnie w fazie planowania, ale powiązane zadania nie zostały jeszcze utworzone w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="327fc-134">You know that refurbishment of some assets is currently in the planning phase, but related jobs haven't yet been created in Asset Management.</span></span> <span data-ttu-id="327fc-135">Należy jednak uwzględnić koszty budżetowe tych zadań, które mają być uwzględnione w budżecie konserwacji.</span><span class="sxs-lookup"><span data-stu-id="327fc-135">However, you want budget costs for those jobs to be included in the maintenance budget.</span></span>
- <span data-ttu-id="327fc-136">Nowe środki trwałe lub typy środków zostały utworzone od czasu dokonania budżetu konserwacji, ale nie skonfigurowano jeszcze planów konserwacji dla tych składników lub typów składników majątku.</span><span class="sxs-lookup"><span data-stu-id="327fc-136">New assets or asset types have been created since you made the maintenance budget, but maintenance plans haven't yet been set up on those assets or asset types.</span></span> <span data-ttu-id="327fc-137">Należy jednak uwzględnić koszty budżetowe tych składników majątku, które mają być uwzględnione w budżecie konserwacji.</span><span class="sxs-lookup"><span data-stu-id="327fc-137">However, you want budget costs for those asset types to be included in the maintenance budget.</span></span>
