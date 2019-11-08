---
title: Prognozy konserwacji
description: W tym temacie wyjaśniono prognozy konserwacji w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a1596b283c3eaffca25ff7f03c722a2bcce109fb
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626300"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="d177d-103">Prognozy konserwacji</span><span class="sxs-lookup"><span data-stu-id="d177d-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d177d-104">Podczas tworzenia zlecenia pracy, są tworzone zadania zlecenia pracy, które mają powiązane typy składników majątku i zadań konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="d177d-104">When you create a work order, you create work order jobs that have related assets and maintenance job types.</span></span> <span data-ttu-id="d177d-105">Po wybraniu typu zadania konserwacji zawierającego prognozy konserwacji, prognozy są automatycznie kopiowane do zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d177d-105">When you select a maintenance job type that contains maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="d177d-106">Można dodawać wiersze prognozy do zlecenia pracy lub usuwać je ze zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d177d-106">You might be able to add forecast lines to a work order or delete them from a work order.</span></span> <span data-ttu-id="d177d-107">Konfiguracja stanu cyklu życia zlecenia pracy, powiązanego typu projektu oraz reguł etapów związanych z typem projektu określa, czy można dodawać lub edytować wiersze prognozy.</span><span class="sxs-lookup"><span data-stu-id="d177d-107">The setup of the work order lifecycle state, the related project type, and the stage rules that are related to the project type determine whether you can add or edit forecast lines.</span></span> <span data-ttu-id="d177d-108">Aby uzyskać więcej informacji na temat stanów cyklu życia zlecenia pracy i etapów projektu należy zapoznać się z [Prognozy, zlecenia pracy i projekty](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="d177d-108">For more information about work order lifecycle states and related project stages, see [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

1. <span data-ttu-id="d177d-109">Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="d177d-109">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="d177d-110">Wybierz zlecenie pracy na liście, a następnie w okienku akcji > na karcie **Zlecenie pracy**, w grupie **Projekt** wybierz pozycję **Prognozy**.</span><span class="sxs-lookup"><span data-stu-id="d177d-110">Select the work order in the list, and then, on the Action Pane > **Work order** tab > the **Project** group, select **Forecast**.</span></span> <span data-ttu-id="d177d-111">Na stronie **Prognoza konserwacji zlecenia pracy** zostaną wyświetlone wiersze prognozy z typu zadania konserwacji wybrane w zadaniu zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d177d-111">The **Work order maintenance forecast** page shows forecast lines from the maintenance job type that is selected on the work order job.</span></span>


## <a name="add-an-hours-forecast-to-a-work-order"></a><span data-ttu-id="d177d-112">Dodaj prognozę godzin dla zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="d177d-112">Add an hours forecast to a work order</span></span>

1. <span data-ttu-id="d177d-113">Na stronie **Prognoza konserwacji zlecenia pracy** wybierz zadanie zlecenia pracy, do którego chcesz dodać prognozę.</span><span class="sxs-lookup"><span data-stu-id="d177d-113">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="d177d-114">Na skróconej karcie **Godziny** wybierz **Dodaj**, aby utworzyć nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="d177d-114">On the **Hours** FastTab, select **Add** to create a new line.</span></span>

3. <span data-ttu-id="d177d-115">W polu **Kategoria** wybierz kategorię.</span><span class="sxs-lookup"><span data-stu-id="d177d-115">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="d177d-116">W polu **Godziny** wstaw liczbę prognozowanych godzin.</span><span class="sxs-lookup"><span data-stu-id="d177d-116">In the **Hours** field, enter the number of forecasted hours.</span></span>

5. <span data-ttu-id="d177d-117">W polu **Właściwości wiersza** wybierz typ opłaty, który ma być używany w wierszu.</span><span class="sxs-lookup"><span data-stu-id="d177d-117">In the **Line property** field, select the type of charge that should be used on the line.</span></span>


## <a name="add-an-items-forecast-to-a-work-order"></a><span data-ttu-id="d177d-118">Dodaj pozycje prognozy dla zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="d177d-118">Add an items forecast to a work order</span></span>

<span data-ttu-id="d177d-119">Istnieją trzy sposoby dodawania pozycji do prognozy konserwacji zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d177d-119">There are three ways to add items to a work order maintenance forecast.</span></span> <span data-ttu-id="d177d-120">Wiersze można tworzyć dla pozycji (części zamienne), które nie są uwzględnione na liście części zamiennych lub list składowych składników majątku (BOM), można wybierać części zamienne z listy zatwierdzone części zamienne, a także wybierać pozycje ze składników majatku BOM.</span><span class="sxs-lookup"><span data-stu-id="d177d-120">You can create lines for items (spare parts) that aren't included on the spare parts list or the asset bill of materials (BOM), you can select spare parts from the approved spare parts list, or you can select items from the asset BOM.</span></span>

- <span data-ttu-id="d177d-121">Na stronie **Prognoza konserwacji zlecenia pracy** wybierz zadanie zlecenia pracy, do którego chcesz dodać prognozę.</span><span class="sxs-lookup"><span data-stu-id="d177d-121">On the **Work order maintenance forecast** page, select the work order job to to add a forecast to.</span></span>

- <span data-ttu-id="d177d-122">Na skróconej karcie **Pozycje** dodaj pozycje do prognozy konserwacji, stosując odpowiednią metodę.</span><span class="sxs-lookup"><span data-stu-id="d177d-122">On the **Items** FastTab, add items to the maintenance forecast by using the appropriate method.</span></span>

<span data-ttu-id="d177d-123">Aby utworzyć nowy wiersz dla części zamiennej, która nie znajduje się na liście części zamiennych lub na liście BOM składników majątku, postępuj zgodnie z następującymi krokami:</span><span class="sxs-lookup"><span data-stu-id="d177d-123">To create a line for a spare part that isn't on the spare parts list or the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="d177d-124">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="d177d-124">Select **Add**.</span></span>
2. <span data-ttu-id="d177d-125">W polu **Numer pozycji** wybierz pozycję.</span><span class="sxs-lookup"><span data-stu-id="d177d-125">In the **Item number** field, select the item.</span></span>
3. <span data-ttu-id="d177d-126">W polu **Ilość sprzedaży** wprowadź ilość.</span><span class="sxs-lookup"><span data-stu-id="d177d-126">In the **Sales quantity** field, enter the quantity.</span></span>
4. <span data-ttu-id="d177d-127">W polu **Jednostka** wybierz jednostkę miary dla ilości.</span><span class="sxs-lookup"><span data-stu-id="d177d-127">In the **Unit** field, select the unit of measure for the quantity.</span></span>
5. <span data-ttu-id="d177d-128">W polach **Koszt własny** i **Waluta** wprowadź odpowiednie wartości.</span><span class="sxs-lookup"><span data-stu-id="d177d-128">In the **Cost price** and **Currency** fields, enter appropriate values.</span></span>
6. <span data-ttu-id="d177d-129">W polu **Właściwość wiersza** wybierz właściwość wiersza.</span><span class="sxs-lookup"><span data-stu-id="d177d-129">In the **Line property** field, select a line property.</span></span>
7. <span data-ttu-id="d177d-130">Aby zmienić listę wymiarów wyświetlanych w wierszach pozycji, kliknij **Zapasy** > **Wyświetl wymiary**, wybierz wymiary i na przycisku przełącznika **Zapisz ustawienia** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d177d-130">To change the list of dimensions that is shown on the item lines, select **Inventory** > **Display dimensions**, select the dimensions, and then set the **Save setup** option to **Yes**.</span></span>

<span data-ttu-id="d177d-131">Aby dodać część zamienną z listy zatwierdzonych części zamiennych, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="d177d-131">To add a spare part from an approved spare parts list, follow these steps:</span></span>

1. <span data-ttu-id="d177d-132">Wybierz **Dodaj części zamienne**.</span><span class="sxs-lookup"><span data-stu-id="d177d-132">Select **Add spare parts**.</span></span>
2. <span data-ttu-id="d177d-133">Wybierz część zamienną i w razie konieczności zmodyfikuj odpowiednie informacje.</span><span class="sxs-lookup"><span data-stu-id="d177d-133">Select the spare part, and edit the related information as you require.</span></span>
3. <span data-ttu-id="d177d-134">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d177d-134">Select **OK**.</span></span>

<span data-ttu-id="d177d-135">Aby dodać towar z BOM środka trwałego, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="d177d-135">To add an item from the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="d177d-136">Wybierz **Dodaj pozycje BOM**.</span><span class="sxs-lookup"><span data-stu-id="d177d-136">Select **Add BOM items**.</span></span>
2. <span data-ttu-id="d177d-137">Wybierz pozycje i w razie konieczności zmodyfikuj odpowiednie informacje.</span><span class="sxs-lookup"><span data-stu-id="d177d-137">Select the item, and edit the related information as you require.</span></span>
3. <span data-ttu-id="d177d-138">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d177d-138">Select **OK**.</span></span>

<span data-ttu-id="d177d-139">Aby uzyskać informacje o tym, gdzie jest używana pozycja w wybranym wierszu w odniesieniu do składników majątku, domyślnych typów zadań konserwacji, części zamiennych i zleceń pracy w module Zarządzanie składnikami majątku, wybierz opcję **Używająca pozycja**.</span><span class="sxs-lookup"><span data-stu-id="d177d-139">To get an overview that shows where the item on the selected line is used in relation to assets, maintenance job type defaults, spare parts, and work orders in Asset Management, select **Item where used**.</span></span> <span data-ttu-id="d177d-140">Aby uzyskać więcej informacji na temat tego przeglądu, zobacz [Używająca pozycja](../controlling-and-reporting/item-where-used.md).</span><span class="sxs-lookup"><span data-stu-id="d177d-140">For more information about this overview, see [Item where used](../controlling-and-reporting/item-where-used.md).</span></span>


## <a name="add-an-expense-forecast-to-a-work-order"></a><span data-ttu-id="d177d-141">Dodaj prognozę wydatków dla zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="d177d-141">Add an expense forecast to a work order</span></span>

1. <span data-ttu-id="d177d-142">Na stronie **Prognoza konserwacji zlecenia pracy** wybierz zadanie zlecenia pracy, do którego chcesz dodać prognozę.</span><span class="sxs-lookup"><span data-stu-id="d177d-142">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="d177d-143">Na skróconej karcie **Wydatki** wybierz **Dodaj**, aby utworzyć nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="d177d-143">On the **Expense** FastTab, select **Add** to create a line.</span></span>

3. <span data-ttu-id="d177d-144">W polu **Kategoria** wybierz kategorię.</span><span class="sxs-lookup"><span data-stu-id="d177d-144">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="d177d-145">W polu **Ilość** wprowadź ilość.</span><span class="sxs-lookup"><span data-stu-id="d177d-145">In the **Quantity** field, enter the quantity.</span></span>

5. <span data-ttu-id="d177d-146">W polach **Koszt własny**, **Waluta sprzedaży** i **Cena sprzedaży** wpisz odpowiednie wartości.</span><span class="sxs-lookup"><span data-stu-id="d177d-146">In the **Cost price**, **Sales currency**, and **Sales price** fields, enter appropriate values.</span></span>

6. <span data-ttu-id="d177d-147">W polu **Właściwości wiersza** wybierz typ opłaty, który ma być używany w wierszu.</span><span class="sxs-lookup"><span data-stu-id="d177d-147">In the **Line property** field, select the type of charge that should be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="d177d-148">W skróconej karcie **Sumy prognozy konserwacji** można wyświetlić przegląd liczby wierszy utworzonych na poszczególnych kartach dla wybranego zadania zlecenia oraz zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d177d-148">The **Maintenance forecast totals** FastTab shows an overview of the number of lines that have been created, for the selected work order job and for the work order, on each FastTab.</span></span> <span data-ttu-id="d177d-149">Ponadto pokazuje sumę prognozowanych godzin dla zadania zlecenia pracy i zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d177d-149">It also shows the total forecasted work hours for the work order job and the work order.</span></span>

<span data-ttu-id="d177d-150">Na poniższej ilustracji pokazano przykład strony listy **Prognoza konserwacji zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="d177d-150">The illustration below shows an example of the **Work order maintenance forecast** page.</span></span>

![Rysunek 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="d177d-152">Automatyczna aktualizacja prognoz zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="d177d-152">Automatic update of work order forecasts</span></span>

<span data-ttu-id="d177d-153">W module Zarządzanie składnikami majątku można automatycznie aktualizować zmiany prognoz zleceń, aby odzwierciedlały zmainy w kosztach godzinowych, kosztach towarów i wydatków, które zostały zaktualizowane w innych modułach w Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d177d-153">If hour costs, item costs, and expenses are updated in other modules in Microsoft Dynamics 365 for Finance and Operations, work order forecasts in Asset Management can automatically be updated to reflect those changes.</span></span> <span data-ttu-id="d177d-154">Pomaga to upewnić się, że ostatnie koszty własne są zawsze używane w prognozach zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="d177d-154">This capability helps guarantee that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="d177d-155">Możliwe jest również tworzenie podobnych aktualizacji dla [prognoz typu zadania konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="d177d-155">You can also do similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="d177d-156">Wybierz **Zarządzanie składnikami majątku** > **Okresowe** > **Prognoza** > **Aktualizacja prognozy zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="d177d-156">Select **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="d177d-157">W oknie dialogowym **Aktualizacja prognozy zlecenia pracy** na skróconej karcie **Rekordy do uwzględnienia** w razie potrzeby można dodawać wybory dotyczące określonych zleceń pracy lub zadań zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d177d-157">In the **Update work order forecast** dialog, on the **Records to include** FastTab, you can add selections regarding specific work orders or work order jobs, as you require.</span></span> <span data-ttu-id="d177d-158">Wybierz pozycję **Filtruj** i wybierz odpowiednie opcje.</span><span class="sxs-lookup"><span data-stu-id="d177d-158">Click **Filter** to make the relevant selections.</span></span>

3. <span data-ttu-id="d177d-159">Na skróconej karcie **uruchom w tle** w razie potrzeby możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="d177d-159">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

4. <span data-ttu-id="d177d-160">Wybierz przycisk **OK**, aby rozpocząć aktualizację prognozy.</span><span class="sxs-lookup"><span data-stu-id="d177d-160">Select **OK** to start the forecast update.</span></span>


<span data-ttu-id="d177d-161">Na poniższej ilustracji pokazano przykład okna dialogowego **Aktualizacja prognozy zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="d177d-161">The illustration below shows an example of the **Update work order forecast** dialog.</span></span>

![Rysunek 2](media/07-work-orders.png)
