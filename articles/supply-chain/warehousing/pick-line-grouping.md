---
title: Grupowanie wierszy pobrania
description: Ten temat zawiera omówienie grupowania wierszy pobrania.
author: Mirzaab
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: fe0e63ef742b7bfd09684a94d273a1841d24599c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828280"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="76d69-103">Grupowanie wierszy pobrania</span><span class="sxs-lookup"><span data-stu-id="76d69-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76d69-104">Grupowanie wierszy pobrania sprawia, że wiele wierszy pracy, które mają ten sam element i lokalizację, można łączyć w jednym pobraniu prezentowanym użytkownikowi na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="76d69-104">Pick line grouping enables multiple work lines that have the same item and location to be combined into a single pick that is presented to the user on the mobile device.</span></span> <span data-ttu-id="76d69-105">Dzięki temu pracownicy magazynu mogą odbierać najbardziej efektywne instrukcje, ale wymagane rozdzielenie wierszy pracy w systemie może być również zachowane (na przykład dla różnych kontenerów, zamówień itd.).</span><span class="sxs-lookup"><span data-stu-id="76d69-105">Therefore, warehouse workers can receive the most efficient instructions, but required work line separation (for different containers, orders, and so on) can still be maintained in the system.</span></span>

## <a name="turn-on-the-pick-line-grouping-feature"></a><span data-ttu-id="76d69-106">Włącz funkcję grupowania wierszy pobrania</span><span class="sxs-lookup"><span data-stu-id="76d69-106">Turn on the pick line grouping feature</span></span>

<span data-ttu-id="76d69-107">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="76d69-107">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="76d69-108">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="76d69-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="76d69-109">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="76d69-109">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="76d69-110">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="76d69-110">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="76d69-111">**Nazwa funkcji:** *Grupowanie wiersza pobrania*</span><span class="sxs-lookup"><span data-stu-id="76d69-111">**Feature name:** *Pick line grouping*</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="76d69-112">Konfigurowanie grupowania wierszy pobrania</span><span class="sxs-lookup"><span data-stu-id="76d69-112">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="76d69-113">Tworzenie elementu menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="76d69-113">Create a mobile device menu item</span></span>

1. <span data-ttu-id="76d69-114">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="76d69-114">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="76d69-115">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="76d69-115">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="76d69-116">W polu **Nazwa elementu menu** wprowadź pozycję *Pobranie wierszy grupy sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="76d69-116">In the **Menu item name** field, enter *Sales group line picking*.</span></span>
1. <span data-ttu-id="76d69-117">W polu **Tytuł** wprowadź pozycję *Pobranie wierszy grupy sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="76d69-117">In the **Title** field, enter *Sales group line picking*.</span></span> <span data-ttu-id="76d69-118">Ten tytuł będzie wyświetlany w menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="76d69-118">This title will be shown on the mobile device menu.</span></span>
1. <span data-ttu-id="76d69-119">W polu **Tryb** wybierz opcję *Praca*.</span><span class="sxs-lookup"><span data-stu-id="76d69-119">In the **Mode** field, select *Work*.</span></span>
1. <span data-ttu-id="76d69-120">W opcji **Użyj istniejącej pracy** zaznacz wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="76d69-120">Set the **Use existing work** option to *Yes*.</span></span>
1. <span data-ttu-id="76d69-121">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="76d69-121">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="76d69-122">W polu **Sterowane przez** wybierz opcję *Sterowane przez użytkownika*.</span><span class="sxs-lookup"><span data-stu-id="76d69-122">In the **Directed by** field, select *User directed*.</span></span>
    - <span data-ttu-id="76d69-123">Ustaw opcję **Generuj numer identyfikacyjny:** na *Tak*.</span><span class="sxs-lookup"><span data-stu-id="76d69-123">Set the **Generate license plate** option to *Yes*.</span></span>
    - <span data-ttu-id="76d69-124">Ustaw opcję *Pobranie grupowe* na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="76d69-124">Set the **Group pick** option to *Yes*.</span></span>
    - <span data-ttu-id="76d69-125">Zaakceptuj wartość domyślną dla wszystkich pozostałych opcji.</span><span class="sxs-lookup"><span data-stu-id="76d69-125">Accept the default values for the remaining options.</span></span>

1. <span data-ttu-id="76d69-126">Wykonaj następujące kroki, aby skonfigurować prawidłowe klasy robocze dla elementu menu urządzenia przenośnego:</span><span class="sxs-lookup"><span data-stu-id="76d69-126">Follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="76d69-127">Na skróconej karcie **Klasy pracy** wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="76d69-127">On the **Work classes** FastTab, elect **New**.</span></span>
    2. <span data-ttu-id="76d69-128">W polu **Identyfikator klasy roboczej** możesz wybrać pozycję *Sprzedaż* lub *Pobranie zamówienia sprzedaży*, zależnie od magazynu, którego będziesz używać.</span><span class="sxs-lookup"><span data-stu-id="76d69-128">In the **Work class ID** field, you can select either *Sales* or *SO Pick*, depending on the warehouse that you will use.</span></span> <span data-ttu-id="76d69-129">W tym scenariuszu wybierz opcję *Pobranie zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="76d69-129">For this scenario, select *SO Pick*.</span></span>

        <span data-ttu-id="76d69-130">Pole **Typ zlecenia pracy** jest automatycznie ustawiane na *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="76d69-130">The **Work order type** field is automatically set to *Sales orders*.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="76d69-131">Konfigurowanie menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="76d69-131">Set up a mobile device menu</span></span>

<span data-ttu-id="76d69-132">Aby dodać utworzony właśnie element menu do menu **Wychodzące**, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="76d69-132">Follow these steps to add the menu item that you just created to the **Outbound** menu.</span></span>

1. <span data-ttu-id="76d69-133">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="76d69-133">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="76d69-134">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="76d69-134">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="76d69-135">W okienku listy są pokazywane wszystkie istniejące menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="76d69-135">The list pane shows all existing mobile device menus.</span></span> <span data-ttu-id="76d69-136">Na liście wybierz *Wychodzące*.</span><span class="sxs-lookup"><span data-stu-id="76d69-136">Select *Outbound* in the list.</span></span>
1. <span data-ttu-id="76d69-137">Na liście **Dostępne menu i elementy menu** znajdź i wybierz element menu *Pobranie wierszy grupy sprzedaży*, który został utworzony.</span><span class="sxs-lookup"><span data-stu-id="76d69-137">In the **Available menus and menu items** list, find and select the *Sales group line picking* menu item that you created.</span></span>
1. <span data-ttu-id="76d69-138">Wybierz przycisk strzałki w prawo, aby przenieść element menu *Pobranie wierszy grupy sprzedaży* na listę **Struktura menu**.</span><span class="sxs-lookup"><span data-stu-id="76d69-138">Select the right arrow button to move the *Sales group line picking* menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="76d69-139">Za pomocą przycisków strzałki w górę i w dół przenieś element menu w żądane miejsce w strukturze menu.</span><span class="sxs-lookup"><span data-stu-id="76d69-139">Use the up arrow and down arrow buttons to move the menu item into the desired position in the menu structure.</span></span>
1. <span data-ttu-id="76d69-140">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="76d69-140">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="76d69-141">Konfigurowanie szablonów pracy</span><span class="sxs-lookup"><span data-stu-id="76d69-141">Set up a work template</span></span>

1. <span data-ttu-id="76d69-142">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="76d69-142">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="76d69-143">W polu **Typ zlecenia pracy** wybierz opcję *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="76d69-143">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="76d69-144">W siatce **Omówienie** znajdź i wybierz szablon pracy, który ma być używany z tą funkcją.</span><span class="sxs-lookup"><span data-stu-id="76d69-144">In the **Overview** grid, find and select the work template that should be used with this function.</span></span> <span data-ttu-id="76d69-145">W tym scenariuszu wybierz szablon *51 Pobranie do lokalizacji przejściowej*.</span><span class="sxs-lookup"><span data-stu-id="76d69-145">For this scenario, select the *51 Pick to stage* template.</span></span>
1. <span data-ttu-id="76d69-146">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="76d69-146">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="76d69-147">W oknie dialogowym edytora zapytań, na karcie **Sortowanie** wybierz opcję **Dodaj**, a następnie określ następujące wartości nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="76d69-147">In the query editor dialog box, on the **Sorting** tab, select **Add**, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="76d69-148">W kolumnie **Tabela** wybierz pozycję *Transakcje pracy tymczasowej*.</span><span class="sxs-lookup"><span data-stu-id="76d69-148">In the **Table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="76d69-149">W kolumnie **Tabela pochodna** wybierz pozycję *Transakcje pracy tymczasowej*.</span><span class="sxs-lookup"><span data-stu-id="76d69-149">In the **Derived table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="76d69-150">W kolumnie **Pole** wybierz pozycję *Numer elementu*.</span><span class="sxs-lookup"><span data-stu-id="76d69-150">In the **Field** column, select *Item number*.</span></span>
    - <span data-ttu-id="76d69-151">W kolumnie **Kierunek wyszukiwania** wybierz opcję *Rosnąco*.</span><span class="sxs-lookup"><span data-stu-id="76d69-151">In the **Search direction** column, select *Ascending*.</span></span>

1. <span data-ttu-id="76d69-152">Wybierz przycisk **OK**, aby zamknąć okno dialogowe i zapisać wybrane opcje.</span><span class="sxs-lookup"><span data-stu-id="76d69-152">Select **OK** to close the dialog box and save your selection.</span></span>
1. <span data-ttu-id="76d69-153">Zostanie wyświetlony następujący komunikat: „Grupowanie zostanie zresetowane, czy chcesz kontynuować?”</span><span class="sxs-lookup"><span data-stu-id="76d69-153">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="76d69-154">Wybierz przycisk **Tak**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="76d69-154">Select **Yes** to continue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76d69-155">Aby funkcja grupowania wierszy pobrania mogła działać, wiersze pracy muszą być sortowane według identyfikatora elementu.</span><span class="sxs-lookup"><span data-stu-id="76d69-155">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="76d69-156">Jeśli wiersze, które mają te same elementy, nie są sekwencjonowane jeden po drugim, nie zostaną zgrupowane.</span><span class="sxs-lookup"><span data-stu-id="76d69-156">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="76d69-157">Przykład</span><span class="sxs-lookup"><span data-stu-id="76d69-157">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="76d69-158">Tworzenie pracy pobrania</span><span class="sxs-lookup"><span data-stu-id="76d69-158">Create picking work</span></span>

<span data-ttu-id="76d69-159">Aby można było skonfigurować grupowanie wierszy pobrania, należy utworzyć kilka kwalifikujących się prac wychodzących.</span><span class="sxs-lookup"><span data-stu-id="76d69-159">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="76d69-160">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="76d69-160">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="76d69-161">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="76d69-161">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="76d69-162">W polu **Konto odbiorcy** zaznacz wartość *US-004*.</span><span class="sxs-lookup"><span data-stu-id="76d69-162">In the **Customer account** field, select *US-004*.</span></span>
1. <span data-ttu-id="76d69-163">Na skróconej karcie **Ogólne** w polu **Magazyn** wybierz wartość *51*.</span><span class="sxs-lookup"><span data-stu-id="76d69-163">On the **General** FastTab, in the **Warehouse** field, select *51*.</span></span>
1. <span data-ttu-id="76d69-164">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="76d69-164">Select **OK**.</span></span>
1. <span data-ttu-id="76d69-165">Na skróconej karcie **Wiersze zamówienia sprzedaży** dodaj sześć następujących wierszy:</span><span class="sxs-lookup"><span data-stu-id="76d69-165">On the **Sales order lines** FastTab, add the following six lines:</span></span>

    - <span data-ttu-id="76d69-166">**Wiersz 1:** w polu **Numer elementu** wybierz wartość *M9200*.</span><span class="sxs-lookup"><span data-stu-id="76d69-166">**Line 1:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="76d69-167">W polu **Ilość** wpisz wartość *3*.</span><span class="sxs-lookup"><span data-stu-id="76d69-167">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="76d69-168">**Wiersz 2:** w polu **Numer elementu** wybierz wartość *M9201*.</span><span class="sxs-lookup"><span data-stu-id="76d69-168">**Line 2:** In the **Item number** field, select *M9201*.</span></span> <span data-ttu-id="76d69-169">W polu **Ilość** wpisz wartość *3*.</span><span class="sxs-lookup"><span data-stu-id="76d69-169">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="76d69-170">**Wiersz 3:** w polu **Numer elementu** wybierz wartość *M9202*.</span><span class="sxs-lookup"><span data-stu-id="76d69-170">**Line 3:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="76d69-171">W polu **Ilość** wpisz wartość *2*.</span><span class="sxs-lookup"><span data-stu-id="76d69-171">In the **Quantity** field, enter *2*.</span></span>
    - <span data-ttu-id="76d69-172">**Wiersz 4:** w polu **Numer elementu** wybierz wartość *M9200*.</span><span class="sxs-lookup"><span data-stu-id="76d69-172">**Line 4:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="76d69-173">W polu **Ilość** wpisz wartość *1*.</span><span class="sxs-lookup"><span data-stu-id="76d69-173">In the **Quantity** field, enter *1*.</span></span>
    - <span data-ttu-id="76d69-174">**Wiersz 5:** w polu **Numer elementu** wybierz wartość *M9200*.</span><span class="sxs-lookup"><span data-stu-id="76d69-174">**Line 5:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="76d69-175">W polu **Ilość** wpisz wartość *3*.</span><span class="sxs-lookup"><span data-stu-id="76d69-175">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="76d69-176">**Wiersz 6:** w polu **Numer elementu** wybierz wartość *M9202*.</span><span class="sxs-lookup"><span data-stu-id="76d69-176">**Line 6:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="76d69-177">W polu **Ilość** wpisz wartość *7*.</span><span class="sxs-lookup"><span data-stu-id="76d69-177">In the **Quantity** field, enter *7*.</span></span>

    <span data-ttu-id="76d69-178">Poniżej znajduje się podsumowanie całkowitych ilości dla każdego elementu:</span><span class="sxs-lookup"><span data-stu-id="76d69-178">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="76d69-179">**Element M9200:** *7* szt.</span><span class="sxs-lookup"><span data-stu-id="76d69-179">**Item M9200:** *7* each</span></span>
    - <span data-ttu-id="76d69-180">**Element M9201:** *3* szt.</span><span class="sxs-lookup"><span data-stu-id="76d69-180">**Item M9201:** *3* each</span></span>
    - <span data-ttu-id="76d69-181">**Element M9202:** *9* szt.</span><span class="sxs-lookup"><span data-stu-id="76d69-181">**Item M9202:** *9* each</span></span>

1. <span data-ttu-id="76d69-182">Przed zwolnieniem zleceń do magazynu należy upewnić się, że lokalizacje pobrania mają wystarczającą ilość zapasów dla wszystkich pozycji na wszystkich zamówieniach.</span><span class="sxs-lookup"><span data-stu-id="76d69-182">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="76d69-183">Przejrzyj ustawienie **Dyrektywa lokalizacji**, aby określić, które lokalizacje pobrania są używane do pobrania zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="76d69-183">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span> <span data-ttu-id="76d69-184">Jeśli używasz pokazowego środowiska danych firmy Contoso dla magazynu *51*, potwierdź, że są dostępne zapasy.</span><span class="sxs-lookup"><span data-stu-id="76d69-184">If you're using the Contoso demo data environment for warehouse *51*, confirm that there is available inventory.</span></span>

    <span data-ttu-id="76d69-185">Teraz musisz zarezerwować zapasy dla każdego wiersza.</span><span class="sxs-lookup"><span data-stu-id="76d69-185">You must now reserve the inventory for each line.</span></span>

1. <span data-ttu-id="76d69-186">Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz jeden z wierszy, które muszą zostać zarezerwowane.</span><span class="sxs-lookup"><span data-stu-id="76d69-186">On the **Sales order lines** FastTab, select one of the lines that must be reserved.</span></span>
1. <span data-ttu-id="76d69-187">W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="76d69-187">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="76d69-188">Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zastosować rezerwację.</span><span class="sxs-lookup"><span data-stu-id="76d69-188">On the **Reservation** page, on the Action Pane, select **Reserve lot** to apply the reservation.</span></span> <span data-ttu-id="76d69-189">Następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="76d69-189">Then close the page.</span></span>
1. <span data-ttu-id="76d69-190">Powtórz kroki od 8 do 10 w przypadku pozostałych wierszy, które muszą zostać zarezerwowane.</span><span class="sxs-lookup"><span data-stu-id="76d69-190">Repeat steps 8 through 10 for the remaining lines that must be reserved.</span></span>

    <span data-ttu-id="76d69-191">Musisz teraz wydać zamówienie sprzedaży do magazynu.</span><span class="sxs-lookup"><span data-stu-id="76d69-191">You must now release the sales order to the warehouse.</span></span>

1. <span data-ttu-id="76d69-192">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="76d69-192">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="76d69-193">Zostanie wyświetlony komunikat informujący o utworzeniu wysyłki i grupy czynności, a następnie o przesłaniu grupy czynności do uruchomienia w partii.</span><span class="sxs-lookup"><span data-stu-id="76d69-193">You receive a message that states that a shipment and a wave have been created, and that the wave has been submitted to run in a batch.</span></span>

    <span data-ttu-id="76d69-194">Po zakończeniu grupy czynności i wszystkich zadań w kierunku od dołu do klienta jest tworzony identyfikator pracy, która ma sześć wierszy.</span><span class="sxs-lookup"><span data-stu-id="76d69-194">When the wave and all downstream jobs have been completed, a work ID is created for work that has six lines.</span></span> <span data-ttu-id="76d69-195">Wiersze są sortowane według numeru elementu.</span><span class="sxs-lookup"><span data-stu-id="76d69-195">The lines are sorted by item number.</span></span>

1. <span data-ttu-id="76d69-196">Przejdź do obszaru **Zarządzanie magazynem \> Praca \> Cała praca**, aby wyświetlić utworzoną pracę.</span><span class="sxs-lookup"><span data-stu-id="76d69-196">Go to **Warehouse management \> Work \> All work** to view the work that was created.</span></span> <span data-ttu-id="76d69-197">Zanotuj wartość **Identyfikatora pracy**. Będziesz go używać w następnej procedurze.</span><span class="sxs-lookup"><span data-stu-id="76d69-197">Make a note of the **Work ID** value, because you will need it in the next procedure.</span></span>

### <a name="initiate-picking-from-the-mobile-device"></a><span data-ttu-id="76d69-198">Inicjowanie pobierania z urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="76d69-198">Initiate picking from the mobile device</span></span>

1. <span data-ttu-id="76d69-199">Zaloguj się do urządzenia mobilnego jako użytkownik skonfigurowany dla magazynu *51*.</span><span class="sxs-lookup"><span data-stu-id="76d69-199">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="76d69-200">Na urządzeniu przenośnym wybierz menu, które zawiera nowy element menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="76d69-200">On the mobile device, select the menu that includes the new mobile device menu item.</span></span> <span data-ttu-id="76d69-201">W tym scenariuszu wybierz opcję **Wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="76d69-201">For this scenario, select **Outbound**.</span></span>
1. <span data-ttu-id="76d69-202">Wybierz element menu **Pobranie wierszy grupy sprzedaży** i zainicjuj pobranie.</span><span class="sxs-lookup"><span data-stu-id="76d69-202">Select the **Sales group line picking** menu item to initiate the pick.</span></span>
1. <span data-ttu-id="76d69-203">Wprowadź wartość **identyfikatora pracy** zanotowaną w poprzedniej procedurze.</span><span class="sxs-lookup"><span data-stu-id="76d69-203">Enter the **Work ID** value that you made a note of in the previous procedure.</span></span>

    <span data-ttu-id="76d69-204">Powinien zostać wyświetlony krok pobrania, w którym wszystkie wiersze pobrania dla towaru *M9200* są pogrupowane i otrzymasz instrukcję pobrania *7* sztuk towaru *M9200*.</span><span class="sxs-lookup"><span data-stu-id="76d69-204">You should see a pick step where all pick lines for item *M9200* are grouped, and you should receive an instruction to pick *7* each of item *M9200*.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="76d69-205">Na urządzeniu przenośnym praca pobierania dla trzech wierszy pobrania pracy została zsumowana w jednym kroku pobrania dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="76d69-205">On the mobile device, the pick work for the three pick work lines has been aggregated into one picking step for the user.</span></span>

1. <span data-ttu-id="76d69-206">Potwierdź krok pobrania.</span><span class="sxs-lookup"><span data-stu-id="76d69-206">Confirm the pick step.</span></span>
1. <span data-ttu-id="76d69-207">Przejdź do strony pracy, aby sprawdzić jej identyfikator, i zwróć uwagę, że wszystkie trzy wiersze pobrania dla elementu *M9200* zostały zamknięte jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="76d69-207">Go to the work page for the work ID, and notice that all three pick lines for item *M9200* were closed simultaneously.</span></span>
1. <span data-ttu-id="76d69-208">Wróć na urządzenie przenośne i kontynuuj pobieranie.</span><span class="sxs-lookup"><span data-stu-id="76d69-208">Go back to the mobile device, and continue to pick.</span></span> <span data-ttu-id="76d69-209">Powinien zostać pokazany wiersz pracy 4 dla pozycji *M9201*.</span><span class="sxs-lookup"><span data-stu-id="76d69-209">Work line 4 for item *M9201* should be presented.</span></span> <span data-ttu-id="76d69-210">Ponieważ w zamówieniu był tylko jeden wiersz pracy, nie ma żadnych danych do zagregowania.</span><span class="sxs-lookup"><span data-stu-id="76d69-210">Because there was only one work line on the order, there is nothing to aggregate.</span></span>
1. <span data-ttu-id="76d69-211">Potwierdź krok pobrania.</span><span class="sxs-lookup"><span data-stu-id="76d69-211">Confirm the pick step.</span></span>
1. <span data-ttu-id="76d69-212">Ostatni krok pobrania na urządzeniu przenośnym agreguje ostatnie dwa wiersze pobrania ze zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="76d69-212">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>
1. <span data-ttu-id="76d69-213">Ukończ krok pobrania dla *9* sztuk elementu *M9202*.</span><span class="sxs-lookup"><span data-stu-id="76d69-213">Complete the pick step for *9* each of item *M9202*.</span></span>
1. <span data-ttu-id="76d69-214">Potwierdź krok odłożenia i wszelkie dodatkowe pary pobranie/odłożenie, aby ukończyć pracę.</span><span class="sxs-lookup"><span data-stu-id="76d69-214">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="76d69-215">Wiersze pracy można grupować tylko wtedy, gdy są ustawione w kolejności.</span><span class="sxs-lookup"><span data-stu-id="76d69-215">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="76d69-216">Poniższe funkcje nie są obsługiwane:</span><span class="sxs-lookup"><span data-stu-id="76d69-216">The following functionality isn't supported:</span></span>
>
>   - <span data-ttu-id="76d69-217">Towary w ilości efektywnej</span><span class="sxs-lookup"><span data-stu-id="76d69-217">Catch-weight items</span></span>
>
>    <span data-ttu-id="76d69-218">Jeśli w pracy znajdują się wszystkie dowolne towary w ilości efektywnej, przed rozpoczęciem pobrania zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="76d69-218">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>
>   - <span data-ttu-id="76d69-219">Pobranie sztuk</span><span class="sxs-lookup"><span data-stu-id="76d69-219">Piece picking</span></span>
>   - <span data-ttu-id="76d69-220">Wiersze pracy z niedokończoną pracą uzupełniania zapasów</span><span class="sxs-lookup"><span data-stu-id="76d69-220">Work lines that have unfinished replenishment work</span></span>
>   - <span data-ttu-id="76d69-221">Pobranie nadmiarowe</span><span class="sxs-lookup"><span data-stu-id="76d69-221">Over-picking</span></span>
>   - <span data-ttu-id="76d69-222">Pobieranie w niedomiarze wraz ze zmianą alokacji pozycji</span><span class="sxs-lookup"><span data-stu-id="76d69-222">Short picking with item reallocation</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]