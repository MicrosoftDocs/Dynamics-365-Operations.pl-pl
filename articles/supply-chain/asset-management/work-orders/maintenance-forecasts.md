---
title: Prognozy konserwacji
description: W tym temacie wyjaśniono prognozy konserwacji w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024506"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="343cb-103">Prognozy konserwacji</span><span class="sxs-lookup"><span data-stu-id="343cb-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="343cb-104">Podczas tworzenia zlecenia pracy, zadania zlecenia pracy są tworzone z uwzględnieniem odpowiednich typów składników majątku i zadań konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="343cb-104">When you create a work order, you create work order jobs with related assets and maintenance job types.</span></span> <span data-ttu-id="343cb-105">Po wybraniu typu zadania konserwacji zawierającego prognozy konserwacji, prognozy są automatycznie kopiowane do zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="343cb-105">When you select a maintenance job type containing maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="343cb-106">Istnieje możliwość dodawania lub usuwania wierszy prognozy w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="343cb-106">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="343cb-107">Konfiguracja stanu cyklu życia zlecenia pracy, powiązanego typu projektu oraz reguł etapów związanych z typem projektu określa, czy można dodawać lub edytować wiersze prognozy.</span><span class="sxs-lookup"><span data-stu-id="343cb-107">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determines if you are able to add or edit forecast lines.</span></span> 

1. <span data-ttu-id="343cb-108">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="343cb-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="343cb-109">Wybierz zlecenie pracy z listy i kliknij przycisk **prognoza.**</span><span class="sxs-lookup"><span data-stu-id="343cb-109">Select the work order in the list, and click **Forecast**.</span></span> <span data-ttu-id="343cb-110">W **prognozieobsługi zlecenia pracy** zostaną wyświetlone wiersze prognozy z typu zadania konserwacji wybrane w zadaniu zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="343cb-110">In **Work order maintenance forecast**, forecast lines from the maintenance job type selected on the work order job are displayed.</span></span>


## <a name="add-hours-forecast-to-a-work-order"></a><span data-ttu-id="343cb-111">Dodaj prognozę godzin dla zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="343cb-111">Add hours forecast to a work order</span></span>

1. <span data-ttu-id="343cb-112">Wybierz zadanie zlecenia pracy, w którym chcesz dodać wiersz prognozy.</span><span class="sxs-lookup"><span data-stu-id="343cb-112">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="343cb-113">Na skróconej karcie **Godziny** kliknij przycisk **Dodaj**, aby utworzyć nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="343cb-113">On the **Hours** FastTab, click **Add** to create a new line.</span></span>

3. <span data-ttu-id="343cb-114">Wybierz kategorię w polu **Kategoria**.</span><span class="sxs-lookup"><span data-stu-id="343cb-114">Select a category in the **Category** field.</span></span>

4. <span data-ttu-id="343cb-115">Wstaw liczbę prognozowanych godzin w polu **godziny**.</span><span class="sxs-lookup"><span data-stu-id="343cb-115">Insert number of forecasted hours in the **Hours** field.</span></span>

5. <span data-ttu-id="343cb-116">W polu **Właściwości wiersza** wybierz typ opłaty, który ma być używany w wierszu.</span><span class="sxs-lookup"><span data-stu-id="343cb-116">In the **Line property** field, select the charge type to be used on the line.</span></span>


## <a name="add-items-forecast-to-a-work-order"></a><span data-ttu-id="343cb-117">Dodaj pozycje prognozy dla zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="343cb-117">Add items forecast to a work order</span></span>

<span data-ttu-id="343cb-118">Istnieją trzy sposoby dodawania pozycji do prognozy zleceń pracy konserwacji: wiersze można tworzyć dla towarów (części zamienne), które nie są uwzględnione na liście części zamiennych lub BOM składników majątku, można wybierać części zamienne z listy zatwierdzone części zamienne, a także wybierać towary ze składników majatku BOM.</span><span class="sxs-lookup"><span data-stu-id="343cb-118">There are three ways to add items to a work order maintenance forecast: You can create lines for items (spare parts) that are not included in the spare parts list or asset BOM, you can select spare parts from the approved spare parts list, and you can select items from the asset BOM.</span></span>

1. <span data-ttu-id="343cb-119">Wybierz zadanie zlecenia pracy, w którym chcesz dodać wiersz prognozy.</span><span class="sxs-lookup"><span data-stu-id="343cb-119">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="343cb-120">Otwórz skróconą kartę **Towary**.</span><span class="sxs-lookup"><span data-stu-id="343cb-120">Select the **Items** FastTab.</span></span>

3. <span data-ttu-id="343cb-121">Kliknij **Dodaj**, aby utworzyć nowy wiersz dla części zamiennej, która nie znajduje się na liście części zamiennych lub na liście BOM składników majątku.</span><span class="sxs-lookup"><span data-stu-id="343cb-121">Click **Add** to create a new line for a spare part that is not on the spare parts list or the asset BOM list.</span></span>

4. <span data-ttu-id="343cb-122">Wybierz pozycję w polu **Kod pozycji**.</span><span class="sxs-lookup"><span data-stu-id="343cb-122">Select the item in the **Item number** field.</span></span>

5. <span data-ttu-id="343cb-123">Wstaw ilość w polu **ilość sprzedaży**, a następnie wybierz jednostkę ilości w polu **jednostka**.</span><span class="sxs-lookup"><span data-stu-id="343cb-123">Insert quantity in the **Sales quantity** field, and select a quantity unit in the **Unit** field.</span></span>

6. <span data-ttu-id="343cb-124">Wstaw koszt własny i walutę w odpowiednich polach i wybierz **Właściwość wiersza**.</span><span class="sxs-lookup"><span data-stu-id="343cb-124">Insert cost price and currency in the relevant fields, and select a **Line property**.</span></span>

7. <span data-ttu-id="343cb-125">Aby zmienić listę wymiarów wyświetlanych w wierszach towaru, kliknij **Zapasy** > **Wyświetl wymiary**, wybierz wymiary i wybierz wartość tak na przycisku przełącznika **Zapisz ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="343cb-125">If you want to change the list of dimensions displayed on the item lines, click **Inventory** > **Display dimensions**, select the dimensions, and select "Yes" on the **Save setup** toggle button.</span></span>

8. <span data-ttu-id="343cb-126">Jeśli chcesz dodać zatwierdzoną część zamienną do prognozy konserwacji, kliknij opcję **Dodaj części zamienne**, wybierz część zamienną, w razie potrzeby edytuj informacje i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="343cb-126">If you want to add an approved spare part to the maintenance forecast, click **Add spare parts**, select the spare part, edit related information if required, and click **OK**.</span></span>

9. <span data-ttu-id="343cb-127">Jeśli chcesz dodać towary BOM aktywów do prognozy, kliknij przycisk **Dodaj towary BOM**, wybierz towar, w razie potrzeby edytuj informacje związane, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="343cb-127">If you want to add asset BOM items to the forecast, click **Add BOM items**, select the item, edit related information if required, and click **OK**.</span></span>

10. <span data-ttu-id="343cb-128">Kliknij **Używająca pozycja** jeśli chcesz uzyskać informacje o tym, gdzie w module Zarządzaniu składnikami majątku jest używany element w wybranym wierszu, w odniesieniu do składników majątku, zadań konserwacji, części zamiennych i zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="343cb-128">Click **Item where used** if you want to get an overview of where the item on the selected line is used in Asset Management in relation to assets, maintenance job type defaults, spare parts, and work orders.</span></span> 



## <a name="add-expense-forecast-to-a-work-order"></a><span data-ttu-id="343cb-129">Dodaj prognozę wydatków dla zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="343cb-129">Add expense forecast to a work order</span></span>

1. <span data-ttu-id="343cb-130">W tym temacie opisano sposób dodawania prognozy wydatków do zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="343cb-130">This topic explains how to add an expense forecast to a work order.</span></span> <span data-ttu-id="343cb-131">Z lewej strony formularza wybierz zadanie zlecenia pracy, do którego chcesz dodać prognozę.</span><span class="sxs-lookup"><span data-stu-id="343cb-131">In the left-hand side of the form, select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="343cb-132">Otwórz skróconą kartę **Wydatki**.</span><span class="sxs-lookup"><span data-stu-id="343cb-132">Select the **Expense** FastTab.</span></span>

3. <span data-ttu-id="343cb-133">Kliknij przycisk **Dodaj**, aby utworzyć nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="343cb-133">Click **Add** to create a new line.</span></span>

4. <span data-ttu-id="343cb-134">Wybierz kategorię w polu **Kategoria**.</span><span class="sxs-lookup"><span data-stu-id="343cb-134">Select a category in the **Category** field.</span></span>

5. <span data-ttu-id="343cb-135">W polu **Ilość** wprowadź ilość.</span><span class="sxs-lookup"><span data-stu-id="343cb-135">Insert quantity in the **Quantity** field.</span></span>

6. <span data-ttu-id="343cb-136">Umożliwia wstawienie kosztu własnego, waluty sprzedaży i ceny sprzedaży w odpowiednich polach.</span><span class="sxs-lookup"><span data-stu-id="343cb-136">Insert cost price, sales currency, and sales price in the relevant fields.</span></span>

7. <span data-ttu-id="343cb-137">W polu **Właściwości wiersza** wybierz typ opłaty, który ma być używany w wierszu.</span><span class="sxs-lookup"><span data-stu-id="343cb-137">In the **Line property** field, select the charge type to be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="343cb-138">W skróconej karcie **sumy prognozy konserwacji** można wyświetlić przegląd liczby wierszy utworzonych na poszczególnych kartach dla wybranego zadania zlecenia oraz zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="343cb-138">On the **Maintenance forecast totals** FastTab, you can see an overview of the number of lines created on each tab, for the selected work order job and for the work order.</span></span> <span data-ttu-id="343cb-139">Ponadto w przypadku zlecenia pracy można wyświetlić sumę prognozowanych godzin pracy dla zadania zlecenia.</span><span class="sxs-lookup"><span data-stu-id="343cb-139">Also, you can see a sum of forecasted work hours for the work order job and for the work order.</span></span>

![Rysunek 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="343cb-141">Automatyczna aktualizacja prognoz zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="343cb-141">Automatic update of work order forecasts</span></span>

<span data-ttu-id="343cb-142">W module Zarządzanie składnikami majątku można automatycznie aktualizować zmiany prognoz zleceń, dotyczące kosztów godzinowych, kosztów towarów i wydatków, które zostały zaktualizowane w innych modułach.</span><span class="sxs-lookup"><span data-stu-id="343cb-142">In Asset Management, you can automatically update any changes in work order forecasts regarding hour costs, item costs, and expenses, which have been updated in other modules.</span></span> <span data-ttu-id="343cb-143">W tym celu należy upewnić się, że ostatnie koszty własne są zawsze używane w prognozach zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="343cb-143">This is done to ensure that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="343cb-144">Możliwe jest również tworzenie podobnych aktualizacji dla [Prognoza typu zadania konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="343cb-144">It is also possible to make similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="343cb-145">Kliknij **Zarządzanie składnikami majątku** > **Okresowe** > **Prognoza** > **Aktualizacja prognozy zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="343cb-145">Click **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="343cb-146">W oknie dialogowym **Aktualizacja prognozy zlecenia pracy** w razie potrzeby można dodawać wybory dotyczące określonych zleceń pracy lub zadań zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="343cb-146">In the **Update work order forecast** drop-down dialog, you can add selections regarding specific work orders or work order jobs, if required.</span></span> <span data-ttu-id="343cb-147">Kliknij **Filtruj**, aby wybrać te opcje.</span><span class="sxs-lookup"><span data-stu-id="343cb-147">Click **Filter** to make those selections.</span></span>

3. <span data-ttu-id="343cb-148">W razie potrzeby możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe na skróconej karcie **Uruchom w tle**.</span><span class="sxs-lookup"><span data-stu-id="343cb-148">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

4. <span data-ttu-id="343cb-149">Kliknij przycisk **OK**, aby rozpocząć aktualizację prognozy.</span><span class="sxs-lookup"><span data-stu-id="343cb-149">Click **OK** to start the forecast update.</span></span>


![Rysunek 2](media/07-work-orders.png)

