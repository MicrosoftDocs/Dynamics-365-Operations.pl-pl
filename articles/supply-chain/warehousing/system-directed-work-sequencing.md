---
title: Harmonogram prac sterowany przez system
description: Ten temat zawiera informacje dotyczące harmonogramu prac sterowanego przez system. Ta funkcja umożliwia sortowanie i filtrowanie zleceń roboczych przedstawianych przez system użytkownikom w celu wykonania. Jest to przydatne w sytuacjach, w których dodatkowe kryteria są wymagane do kierowania procesu pobierania z magazynu.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 3811486a31d079cac7f7c27ea6323f16de4478d5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970213"
---
# <a name="system-directed-work-sequencing"></a><span data-ttu-id="c19b6-105">Harmonogram prac sterowany przez system</span><span class="sxs-lookup"><span data-stu-id="c19b6-105">System-directed work sequencing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c19b6-106">Funkcja harmonogramu prac sterowanego przez system umożliwia sortowanie i filtrowanie zleceń roboczych przedstawianych przez system użytkownikom w celu wykonania.</span><span class="sxs-lookup"><span data-stu-id="c19b6-106">System-directed work sequencing lets you sort and filter the work orders that the system presents to users for execution.</span></span> <span data-ttu-id="c19b6-107">Jest to przydatne w sytuacjach, w których dodatkowe kryteria (takie jak czas wysyłki, strefa pobrania, profil lokalizacji lub kombinacja różnych kryteriów) są wymagane do kierowania procesem pobierania magazynowego.</span><span class="sxs-lookup"><span data-stu-id="c19b6-107">It's helpful in scenarios where additional criteria (such as the time of shipping, the picking zone, the location profile, or a combination of various criteria) are required to drive the warehouse picking process.</span></span>

<span data-ttu-id="c19b6-108">Ta funkcja rozszerza bieżącą funkcję pobierania sterowanego przez system o nową opcję, Sterowane przez system porządkowanie według, dzięki której użytkownik może skonfigurować sekwencję oraz zapytanie lub wiele zapytań, które będą oceniać wszystkie utworzone zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-108">This functionality extends the current system-directed picking functionality by adding a system-directed query order, where users can set up a sequence and one or more queries that will evaluate all work orders that are created.</span></span> <span data-ttu-id="c19b6-109">Zostaną przechwycone i przedstawione tylko te zlecenia pracy, które spełniają kryteria określone w konfiguracji elementu menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="c19b6-109">Only work orders that meet the criteria that are specified in the setup of the mobile device menu item will be captured and presented.</span></span>

<span data-ttu-id="c19b6-110">Ta funkcja pozwala na dalszą optymalizację procesów pobierania magazynowego, ponieważ identyfikuje zlecenia pracy spełniające określone kryteria, przypisuje je do poprawnego elementu menu urządzenia przenośnego, a następnie przedstawia je pracownikowi na podstawie określonego zestawu umiejętności, sprzętu pobrania lub innego zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="c19b6-110">Therefore, this functionality allows for further optimization of warehouse picking processes as it identifies work orders that match the specified criteria, assigns them to the correct mobile device menu item, and then presents them to a worker, based on a specific skill set, picking equipment, or other requirement.</span></span>

> [!NOTE]
> <span data-ttu-id="c19b6-111">Jeśli są potrzebne jest zastosowanie innych kryteriów, należy użyć wielu elementów menu urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="c19b6-111">If different criteria are needed, multiple mobile device menu items must be used.</span></span>

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a><span data-ttu-id="c19b6-112">Należy włączyć funkcję harmonogramu prac sterowanego przez system obowiązującego dla całej organizacji</span><span class="sxs-lookup"><span data-stu-id="c19b6-112">Turn on the Organization-wide system directed work sequencing feature</span></span>

<span data-ttu-id="c19b6-113">Aby można było korzystać z funkcji harmonogramu pracy kierowanej przez system, funkcja ta musi być włączona w systemie.</span><span class="sxs-lookup"><span data-stu-id="c19b6-113">Before you can use system-directed work sequencing, the feature must be turned on in your system.</span></span> <span data-ttu-id="c19b6-114">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="c19b6-114">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="c19b6-115">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c19b6-115">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c19b6-116">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="c19b6-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c19b6-117">**Nazwa funkcji:** *Harmonogram prac sterowany przez system obowiązujący dla całej organizacji*</span><span class="sxs-lookup"><span data-stu-id="c19b6-117">**Feature name:** *Organization-wide system directed work sequencing*</span></span>

## <a name="setup"></a><span data-ttu-id="c19b6-118">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="c19b6-118">Setup</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="c19b6-119">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="c19b6-119">Make demo data available</span></span>

<span data-ttu-id="c19b6-120">Aby przejść przez ten scenariusz przy użyciu określonych przykładowych rekordów i wartości zaprezentowanych w tym temacie, należy korzystać z systemu, w którym są zainstalowane standardowe dane demonstracyjne.</span><span class="sxs-lookup"><span data-stu-id="c19b6-120">To work through the scenario by using the values that are presented in this topic, you must work on a system where the standard demo data is installed.</span></span> <span data-ttu-id="c19b6-121">Ponadto należy wybrać firmę **USMF**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-121">Additionally, you must select the **USMF** legal entity.</span></span> <span data-ttu-id="c19b6-122">Scenariusz korzysta z magazynu *51* znajdującego się w danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="c19b6-122">The scenario uses warehouse *51* from the demo data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c19b6-123">Przed zwolnieniem zleceń do magazynu należy upewnić się, że lokalizacje pobrania mają wystarczającą ilość zapasów dla wszystkich pozycji na wszystkich zamówieniach.</span><span class="sxs-lookup"><span data-stu-id="c19b6-123">Before you release the orders to the warehouse, make sure that the pick locations have enough inventory for all the items on the orders.</span></span>
>
> <span data-ttu-id="c19b6-124">W tym scenariuszu powinny być obsługiwane dane domyślne USMF.</span><span class="sxs-lookup"><span data-stu-id="c19b6-124">Default USMF data should support this scenario.</span></span> <span data-ttu-id="c19b6-125">Jeśli nie korzystasz z danych demonstracyjnych, przejrzyj ustawienie **Dyrektywa lokalizacji**, aby dowiedzieć się, które lokalizacje pobrania są używane do pobrania zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c19b6-125">If you aren't using demo data, review the **Location directive** setting to learn which picking locations are used for sales order picking.</span></span> <span data-ttu-id="c19b6-126">Jeśli konieczne jest skorygowanie zapasów, można ręcznie tworzyć zmiany, skorzystać z uzupełnienia lub skorzystać z dowolnego innego przepływu.</span><span class="sxs-lookup"><span data-stu-id="c19b6-126">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span>

### <a name="set-up-a-mobile-device-menu-item"></a><span data-ttu-id="c19b6-127">Konfigurowanie elementu menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="c19b6-127">Set up a mobile device menu item</span></span>

1. <span data-ttu-id="c19b6-128">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-128">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="c19b6-129">Na liście elementów menu w urządzeniu przenośnym wybierz opcję **Pobieranie sprzedaży – system**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-129">In the list of mobile device menu items, select **Sales Picking – System**.</span></span> <span data-ttu-id="c19b6-130">Wymagany element menu już istnieje.</span><span class="sxs-lookup"><span data-stu-id="c19b6-130">The required menu item should already exist.</span></span> 
1. <span data-ttu-id="c19b6-131">Potwierdź następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="c19b6-131">Confirm the following settings:</span></span>

    - <span data-ttu-id="c19b6-132">Na skróconej karcie **Ogólne**, pole **Sterowane przez** powinno być ustawione na wartość *Sterowane przez system*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-132">On the **General** FastTab, the **Directed by** field should be set to *System directed*.</span></span>
    - <span data-ttu-id="c19b6-133">Skrócona karta **Klasy robocze** powinny zawierać następujące ustawienia.</span><span class="sxs-lookup"><span data-stu-id="c19b6-133">The **Work classes** FastTab should show the following settings.</span></span>

        | <span data-ttu-id="c19b6-134">Identyfikator klasy roboczej</span><span class="sxs-lookup"><span data-stu-id="c19b6-134">Work class ID</span></span> | <span data-ttu-id="c19b6-135">Typ zlecenia</span><span class="sxs-lookup"><span data-stu-id="c19b6-135">Work order type</span></span> |
        |---|---|
        | <span data-ttu-id="c19b6-136">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="c19b6-136">Sales</span></span> | <span data-ttu-id="c19b6-137">Zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c19b6-137">Sales orders</span></span> |
        | <span data-ttu-id="c19b6-138">Pobranie zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c19b6-138">SO Pick</span></span> | <span data-ttu-id="c19b6-139">Zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c19b6-139">Sales orders</span></span> |

1. <span data-ttu-id="c19b6-140">W okienku akcji wybierz opcję **Systemowe zapytania dotyczące sekwencji pracy**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-140">On the Action Pane, select **System directed work sequence queries**.</span></span>
1. <span data-ttu-id="c19b6-141">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-141">Select **Edit**.</span></span>
1. <span data-ttu-id="c19b6-142">Usuń istniejący wiersz, a następnie potwierdź akcję, wybierając **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-142">Delete the existing line, and then confirm the action by selecting **Yes**.</span></span>
1. <span data-ttu-id="c19b6-143">W okienku akcji wybierz opcję **Nowy**, aby utworzyć wiersz.</span><span class="sxs-lookup"><span data-stu-id="c19b6-143">On the Action Pane, select **New** to create a line.</span></span>
1. <span data-ttu-id="c19b6-144">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c19b6-145">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="c19b6-145">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="c19b6-146">**Pole opis:** *Ilość pracy mniejsza niż 20 i spada*</span><span class="sxs-lookup"><span data-stu-id="c19b6-146">**Description field:** *Work quantity less than 20 and Descending*</span></span>

1. <span data-ttu-id="c19b6-147">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-147">Select **Save**.</span></span>
1. <span data-ttu-id="c19b6-148">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-148">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="c19b6-149">Na karcie **Sprzężenia** rozwiń hierarchię sprzężeń, aby wyświetlić tabelę **Wiersze pracy**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-149">On the **Joins** tab, expand the join hierarchy to show the **Work lines** table.</span></span>
1. <span data-ttu-id="c19b6-150">Wybierz sprzężenie tabeli **Wiersze pracy**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-150">Select the **Work lines** table join.</span></span>
1. <span data-ttu-id="c19b6-151">Wybierz pozycję **Dodaj sprzężenie tabeli**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-151">Select **Add table join**.</span></span>
1. <span data-ttu-id="c19b6-152">Z wyświetlonej listy znajdź i zaznacz wiersz, który ma następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="c19b6-152">In the list that appears, find and select the row that has the following settings:</span></span>

    - <span data-ttu-id="c19b6-153">**Tryb sprzężenia:** *n:1*</span><span class="sxs-lookup"><span data-stu-id="c19b6-153">**Join mode:** *n:1*</span></span>
    - <span data-ttu-id="c19b6-154">**Relacja:** *Lokalizacje (lokalizacja)*</span><span class="sxs-lookup"><span data-stu-id="c19b6-154">**Relation:** *Locations (Location)*</span></span>

1. <span data-ttu-id="c19b6-155">Wybierz pozycję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-155">Select **Select**.</span></span>

    <span data-ttu-id="c19b6-156">Do tabeli sprzężenia dodawane są lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="c19b6-156">Locations are added to the table join.</span></span>

1. <span data-ttu-id="c19b6-157">Na karcie **Sortowanie** wybierz opcję **Dodaj**, aby dodać wiersz.</span><span class="sxs-lookup"><span data-stu-id="c19b6-157">On the **Sorting** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="c19b6-158">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c19b6-159">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="c19b6-159">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c19b6-160">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="c19b6-160">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c19b6-161">**Pole:** *Ilość pracy* (w wyświetlonym oknie komunikatu wybierz opcję **Tak**, aby dodać funkcję sortowania do tego pola).</span><span class="sxs-lookup"><span data-stu-id="c19b6-161">**Field:** *Work quantity* (In the message box that appears, select **Yes** to add sorting to this field.)</span></span>
    - <span data-ttu-id="c19b6-162">**Kierunek sortowania:** *Malejąco*</span><span class="sxs-lookup"><span data-stu-id="c19b6-162">**Search direction:** *Descending*</span></span>

1. <span data-ttu-id="c19b6-163">Kliknij kartę **Zakres**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-163">Select the **Range** tab.</span></span>

    <span data-ttu-id="c19b6-164">Jeśli w sekwencjonowaniu powinny być uwzględnione tylko określone kryteria pracy, można je określić korzystając z karty **Zakres**. W tym przykładzie należy skorzystać z zadań, w których ilość jest mniejsza niż 20 ea (najniższa jednostka miary).</span><span class="sxs-lookup"><span data-stu-id="c19b6-164">If only specific work criteria should be included in the sequencing, you can specify them on the **Range** tab. In this example, you want to include only work where the quantity is less than 20 ea (the lowest unit of measure).</span></span>

    <span data-ttu-id="c19b6-165">Zauważ, że niektóre wiersze są już uwzględnione.</span><span class="sxs-lookup"><span data-stu-id="c19b6-165">Notice that some lines are already included.</span></span> <span data-ttu-id="c19b6-166">Tych wierszy nie należy usuwać.</span><span class="sxs-lookup"><span data-stu-id="c19b6-166">Those lines should not be removed.</span></span>

1. <span data-ttu-id="c19b6-167">Wybierz pozycję **Dodaj**, aby dodać drugi wiersz.</span><span class="sxs-lookup"><span data-stu-id="c19b6-167">Select **Add** to add a line.</span></span>
1. <span data-ttu-id="c19b6-168">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-168">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c19b6-169">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="c19b6-169">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c19b6-170">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="c19b6-170">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c19b6-171">**Pole:** *Ilość pracy w magazynie*</span><span class="sxs-lookup"><span data-stu-id="c19b6-171">**Field:** *Inventory work quantity*</span></span>
    - <span data-ttu-id="c19b6-172">**Kryteria:** *\<20* (mniej niż 20)</span><span class="sxs-lookup"><span data-stu-id="c19b6-172">**Criteria:** *\<20* (less than 20)</span></span>

1. <span data-ttu-id="c19b6-173">Wybierz pozycję **Dodaj**, aby dodać kolejny wiersz.</span><span class="sxs-lookup"><span data-stu-id="c19b6-173">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="c19b6-174">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c19b6-175">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="c19b6-175">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c19b6-176">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="c19b6-176">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c19b6-177">**Pole:** *Typ pracy*</span><span class="sxs-lookup"><span data-stu-id="c19b6-177">**Field:** *Work type*</span></span>
    - <span data-ttu-id="c19b6-178">**Kryteria:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="c19b6-178">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="c19b6-179">Wybierz pozycję **Dodaj**, aby dodać kolejny wiersz.</span><span class="sxs-lookup"><span data-stu-id="c19b6-179">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="c19b6-180">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c19b6-181">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="c19b6-181">**Table:** *Locations*</span></span>
    - <span data-ttu-id="c19b6-182">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="c19b6-182">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="c19b6-183">**Pole:** *Identyfikator profilu lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="c19b6-183">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="c19b6-184">**Kryteria:** *!STAGE*</span><span class="sxs-lookup"><span data-stu-id="c19b6-184">**Criteria:** *!STAGE*</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="c19b6-185">Pamiętaj, aby umieścić wykrzyknik (*!*) przed *ETAP*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-185">Be sure to include the exclamation point (*!*) in front of *STAGE*.</span></span>

1. <span data-ttu-id="c19b6-186">Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć je.</span><span class="sxs-lookup"><span data-stu-id="c19b6-186">Select **OK** to save and close the query.</span></span>
1. <span data-ttu-id="c19b6-187">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-187">Select **Save**.</span></span>
1. <span data-ttu-id="c19b6-188">Zamknij stronę, aby powrócić do strony **Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-188">Close the page to return to the **Mobile device menu items** page.</span></span>

> [!NOTE]
> <span data-ttu-id="c19b6-189">Ta konfiguracja definiuje kryteria, które będą używane w celu podawania kwalifikujących się elementów pracy do elementu menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="c19b6-189">This setup defines the criteria that will be used to feed eligible work to the mobile device menu item.</span></span> <span data-ttu-id="c19b6-190">Jeśli do zapytania zostanie dodanych kilka wierszy kryteriów, system najpierw użyje tego wiersza zapytania, który ma najniższy numer sekwencyjny.</span><span class="sxs-lookup"><span data-stu-id="c19b6-190">If you add more criteria lines to the query, the system will use the query line that has lowest sequence number first.</span></span> <span data-ttu-id="c19b6-191">Innymi słowy, wszystkie zakwalifikowane elementy z harmonogramu nr 1 zostaną przedstawione użytkownikowi jako pierwsze, a następnie procedura zostanie powtórzona dla harmonogramu o numerze 2.</span><span class="sxs-lookup"><span data-stu-id="c19b6-191">In other words, all eligible work for sequence number 1 will be presented to the user first, and then all work for sequence number 2.</span></span> <span data-ttu-id="c19b6-192">Jeśli muszą zostać zastosowane razem określony zakres i sortowani, należy je określić w tym samym zapytaniu harmonogramu prac sterowanym przez system.</span><span class="sxs-lookup"><span data-stu-id="c19b6-192">Therefore, if a specific range and sorting must be used together, they should be specified in the same system-directed work sequence query.</span></span>
>
> <span data-ttu-id="c19b6-193">Ta konfiguracja spowoduje przechwycenie elementu pracy, który ma co najmniej jeden wiersz o ilości mniejszej niż 20 ea.</span><span class="sxs-lookup"><span data-stu-id="c19b6-193">This setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="c19b6-194">Dlatego jeśli w elemencie pracy znajduje się wiersz, w którym ilość wynosi dokładnie 20 lub więcej niż 20 ea, będzie uznany za prawidłowy, pod warunkiem, że ma co najmniej jeden wiersz, w którym ilość jest mniejsza niż 20 ea.</span><span class="sxs-lookup"><span data-stu-id="c19b6-194">Therefore, if the work has a line where the quantity is exactly 20 ea or more than 20 ea, it will be valid, provided that it also has at least one line where the quantity is less than 20 ea.</span></span>

### <a name="location-directives"></a><span data-ttu-id="c19b6-195">Dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="c19b6-195">Location directives</span></span>

<span data-ttu-id="c19b6-196">Jeśli są używane domyślne dane firmy Contoso, w zapytaniu dot. dyrektywy lokalizacji nie są wymagane żadne zmiany.</span><span class="sxs-lookup"><span data-stu-id="c19b6-196">If you're using default Contoso data, the query for the location directive action won't require changes.</span></span> <span data-ttu-id="c19b6-197">Aby jednak upewnić się, że w dyrektywach lokalizacji są przechwytywane towary znajdujące się w zamówieniach sprzedaży, po zastosowaniu tej funkcji w środowisku firmy innej niż Contoso, należy utworzyć nową dyrektywę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c19b6-197">However, to make sure that the location directives will capture the items on the sales orders when you apply the feature in a non-Contoso environment, create a new location directive.</span></span> <span data-ttu-id="c19b6-198">Aby sprawdzić ustawienia w środowisku demonstracyjnym, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c19b6-198">To verify the settings in the demo environment, follow these steps.</span></span>

1. <span data-ttu-id="c19b6-199">Przejdź kolejno do pozycji **Zarządzanie magazynem** \> **Ustawienia** \> **Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-199">Go to **Warehouse management** \> **Setup** \> **Location directives**.</span></span>
1. <span data-ttu-id="c19b6-200">W polu **Typ zlecenia pracy** wybierz opcję *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-200">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="c19b6-201">Wybierz dyrektywę lokalizacji o nazwie *Pobranie 51*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-201">Select the location directive that is named *51 Pick*.</span></span>
1. <span data-ttu-id="c19b6-202">Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz wiersz dla akcji **Pobrania**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-202">On the **Location Directive Actions** FastTab, select the line for the **Pick** action.</span></span>
1. <span data-ttu-id="c19b6-203">Wybierz opcję **Edytuj zapytanie** znajdującą się powyżej siatki.</span><span class="sxs-lookup"><span data-stu-id="c19b6-203">Select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="c19b6-204">Przejrzyj zapytanie **Zakres**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-204">Review the **Range** query.</span></span>

    1. <span data-ttu-id="c19b6-205">Znajdź wiersz, w którym pole o nazwie **Pole** ma wartość *Lokalizacja*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-205">Find the line where the **Field** field is set to *Location*.</span></span>
    2. <span data-ttu-id="c19b6-206">Upewnij się, że pole **Kryteria** jest puste (to znaczy, że nie ma wybranych żadnych ograniczeń).</span><span class="sxs-lookup"><span data-stu-id="c19b6-206">Make sure that the **Criteria** field is blank (that is, there are no restrictions).</span></span>

## <a name="scenario"></a><span data-ttu-id="c19b6-207">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="c19b6-207">Scenario</span></span>

### <a name="create-sales-order-picking-work"></a><span data-ttu-id="c19b6-208">Tworzenie zlecenia pracy dot. pobierania zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c19b6-208">Create sales order picking work</span></span>

<span data-ttu-id="c19b6-209">Przed uruchomieniem pobierania kierowanego przez system powinny zostać utworzone niektóre prace wychodzące.</span><span class="sxs-lookup"><span data-stu-id="c19b6-209">Before system-directed picking is run, some outbound work should be created.</span></span> <span data-ttu-id="c19b6-210">W tym scenariuszu zostaną utworzone cztery zamówienia sprzedaży oparte na określonych zapytaniach systemowych dot. sekwencji pracy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-210">For this scenario, you will create four sales orders that are based on the specified system-directed work sequence queries.</span></span>

<span data-ttu-id="c19b6-211">Ilości zapasów dla każdego zamówienia sprzedaży zostaną rezerwowane.</span><span class="sxs-lookup"><span data-stu-id="c19b6-211">You will reserve inventory quantities for each sales order.</span></span> <span data-ttu-id="c19b6-212">Oznacza to, że zarezerwowane zapasy nie mogą być wycofywane z magazynu dla innych zamówień, chyba że rezerwacja lub część rezerwacji zostanie anulowana.</span><span class="sxs-lookup"><span data-stu-id="c19b6-212">Therefore, reserved inventory can't be withdrawn from the warehouse for other orders unless the inventory reservation, or part of the inventory reservation, is canceled.</span></span>

<span data-ttu-id="c19b6-213">Następnie należy zwolnić poszczególne zamówienia sprzedaży do magazynu w celu utworzenia pracy wychodzącej.</span><span class="sxs-lookup"><span data-stu-id="c19b6-213">You will then release each sales order to the warehouse to create the outbound work.</span></span>

#### <a name="sales-order-1"></a><span data-ttu-id="c19b6-214">Zamówienie sprzedaży 1</span><span class="sxs-lookup"><span data-stu-id="c19b6-214">Sales order 1</span></span>

1. <span data-ttu-id="c19b6-215">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-215">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="c19b6-216">W okienku akcji wybierz opcję **Nowe**, aby utworzyć zamówienie sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="c19b6-216">On the Action Pane, select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="c19b6-217">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-217">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c19b6-218">W sekcji **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-004*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-218">In the **Customer** section, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="c19b6-219">W sekcji **Ogólne** w polu **Magazyn** wybierz wartość *51*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-219">In the **General** section, set the **Warehouse** field to *51*.</span></span>

1. <span data-ttu-id="c19b6-220">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c19b6-220">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="c19b6-221">Zanotuj numer zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c19b6-221">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="c19b6-222">Dodaj wiersz do nowego zamówienia sprzedaży i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-222">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="c19b6-223">**Numer pozycji:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="c19b6-223">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="c19b6-224">**Ilość:** *20*</span><span class="sxs-lookup"><span data-stu-id="c19b6-224">**Quantity:** *20*</span></span>

1. <span data-ttu-id="c19b6-225">W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-225">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="c19b6-226">Na stronie **Rezerwacja** wybierz **Rezerwacja partii** w celu zarezerwowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="c19b6-226">On the **Reservation** page, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="c19b6-227">Zamknij stronę **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-227">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="c19b6-228">W okienku akcji na karcie **Magazyn** wybierz pozycję Akcje **Zwolnij do magazynu**, aby utworzyć zlecenie pracy dla magazynu.</span><span class="sxs-lookup"><span data-stu-id="c19b6-228">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse** to create work for the warehouse.</span></span>

    <span data-ttu-id="c19b6-229">Użytkownik otrzymuje komunikaty informacyjne, które zawierają identyfikator grupy czynności oraz identyfikatory wysyłki utworzone dla zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c19b6-229">You receive informational messages that show the wave ID and shipment IDs that were created for the sales order.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="c19b6-230">Zamówienie sprzedaży 2</span><span class="sxs-lookup"><span data-stu-id="c19b6-230">Sales order 2</span></span>

1. <span data-ttu-id="c19b6-231">W okienku akcji wybierz opcję **Nowe**, aby utworzyć zamówienie sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="c19b6-231">On the Action Pane, select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="c19b6-232">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-232">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c19b6-233">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="c19b6-233">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="c19b6-234">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="c19b6-234">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="c19b6-235">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c19b6-235">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="c19b6-236">Zanotuj numer zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c19b6-236">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="c19b6-237">Dodaj wiersz do nowego zamówienia sprzedaży i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-237">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="c19b6-238">**Numer pozycji:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="c19b6-238">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="c19b6-239">**Ilość:** *5*</span><span class="sxs-lookup"><span data-stu-id="c19b6-239">**Quantity:** *5*</span></span>

1. <span data-ttu-id="c19b6-240">Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-240">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="c19b6-241">**Numer pozycji:** *M9201*</span><span class="sxs-lookup"><span data-stu-id="c19b6-241">**Item number:** *M9201*</span></span>
    - <span data-ttu-id="c19b6-242">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="c19b6-242">**Quantity:** *1*</span></span>

1. <span data-ttu-id="c19b6-243">Zarezerwuj zapasy dla obu wierszy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-243">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="c19b6-244">Zwolnij zamówienie do magazynu.</span><span class="sxs-lookup"><span data-stu-id="c19b6-244">Release the order to the warehouse.</span></span>

#### <a name="sales-order-3"></a><span data-ttu-id="c19b6-245">Zamówienie sprzedaży 3</span><span class="sxs-lookup"><span data-stu-id="c19b6-245">Sales order 3</span></span>

1. <span data-ttu-id="c19b6-246">W okienku akcji wybierz opcję **Nowe**, aby utworzyć zamówienie sprzedaży 3.</span><span class="sxs-lookup"><span data-stu-id="c19b6-246">On the Action Pane, select **New** to create sales order 3.</span></span>
1. <span data-ttu-id="c19b6-247">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-247">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c19b6-248">**Konto odbiorcy:** *US-009*</span><span class="sxs-lookup"><span data-stu-id="c19b6-248">**Customer account:** *US-009*</span></span>
    - <span data-ttu-id="c19b6-249">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="c19b6-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="c19b6-250">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c19b6-250">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="c19b6-251">Zanotuj numer zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c19b6-251">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="c19b6-252">Dodaj wiersz do nowego zamówienia sprzedaży i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-252">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="c19b6-253">**Numer pozycji:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="c19b6-253">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="c19b6-254">**Ilość:** *7*</span><span class="sxs-lookup"><span data-stu-id="c19b6-254">**Quantity:** *7*</span></span>

1. <span data-ttu-id="c19b6-255">Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-255">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="c19b6-256">**Numer pozycji:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="c19b6-256">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="c19b6-257">**Ilość:** *8*</span><span class="sxs-lookup"><span data-stu-id="c19b6-257">**Quantity:** *8*</span></span>

1. <span data-ttu-id="c19b6-258">Zarezerwuj zapasy dla obu wierszy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-258">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="c19b6-259">Zwolnij zamówienie do magazynu.</span><span class="sxs-lookup"><span data-stu-id="c19b6-259">Release the order to the warehouse.</span></span>

#### <a name="sales-order-4"></a><span data-ttu-id="c19b6-260">Zamówienie sprzedaży 4</span><span class="sxs-lookup"><span data-stu-id="c19b6-260">Sales order 4</span></span>

1. <span data-ttu-id="c19b6-261">W okienku akcji wybierz opcję **Nowe**, aby utworzyć zamówienie sprzedaży 4.</span><span class="sxs-lookup"><span data-stu-id="c19b6-261">On the Action Pane, select **New** to create sales order 4.</span></span>
1. <span data-ttu-id="c19b6-262">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-262">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c19b6-263">**Konto odbiorcy:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="c19b6-263">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="c19b6-264">**Magazyn:** *51*</span><span class="sxs-lookup"><span data-stu-id="c19b6-264">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="c19b6-265">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c19b6-265">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="c19b6-266">Zanotuj numer zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c19b6-266">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="c19b6-267">Dodaj wiersz do nowego zamówienia sprzedaży i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-267">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="c19b6-268">**Numer pozycji:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="c19b6-268">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="c19b6-269">**Ilość:** *25*</span><span class="sxs-lookup"><span data-stu-id="c19b6-269">**Quantity:** *25*</span></span>

1. <span data-ttu-id="c19b6-270">Wybierz polecenie **Dodaj wiersz** i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c19b6-270">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="c19b6-271">**Numer pozycji:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="c19b6-271">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="c19b6-272">**Ilość:** *10*</span><span class="sxs-lookup"><span data-stu-id="c19b6-272">**Quantity:** *10*</span></span>

1. <span data-ttu-id="c19b6-273">Zarezerwuj zapasy dla obu wierszy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-273">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="c19b6-274">Zwolnij zamówienie do magazynu.</span><span class="sxs-lookup"><span data-stu-id="c19b6-274">Release the order to the warehouse.</span></span>

### <a name="get-work-ids-for-the-work-that-was-created"></a><span data-ttu-id="c19b6-275">Pobierz identyfikatory pracy dla utworzonej pracy</span><span class="sxs-lookup"><span data-stu-id="c19b6-275">Get work IDs for the work that was created</span></span>

1. <span data-ttu-id="c19b6-276">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-276">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="c19b6-277">Odfiltruj dane w polu **Magazyn**, aby wyświetlić tylko pracę dla magazynu *51*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-277">Filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="c19b6-278">Powinny być wyświetlone cztery identyfikatory pracy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-278">Four work IDs should have been created.</span></span> <span data-ttu-id="c19b6-279">Zapisz identyfikatory pracy dla każdego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c19b6-279">Make a note of the work ID for each sales order.</span></span>

    | <span data-ttu-id="c19b6-280">Identyfikator zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c19b6-280">Sales order ID</span></span> | <span data-ttu-id="c19b6-281">Identyfikator pracy</span><span class="sxs-lookup"><span data-stu-id="c19b6-281">Work ID</span></span> | <span data-ttu-id="c19b6-282">Ilość pracy</span><span class="sxs-lookup"><span data-stu-id="c19b6-282">Work quantity</span></span> |
    |---|---|---|
    | <span data-ttu-id="c19b6-283">Zamówienie sprzedaży 1</span><span class="sxs-lookup"><span data-stu-id="c19b6-283">Sales Order 1</span></span> | <span data-ttu-id="c19b6-284">Identyfikator pracy 1</span><span class="sxs-lookup"><span data-stu-id="c19b6-284">Work ID 1</span></span> | <span data-ttu-id="c19b6-285">20 każdy</span><span class="sxs-lookup"><span data-stu-id="c19b6-285">20 ea</span></span> |
    | <span data-ttu-id="c19b6-286">Zamówienie sprzedaży 2</span><span class="sxs-lookup"><span data-stu-id="c19b6-286">Sales Order 2</span></span> | <span data-ttu-id="c19b6-287">Identyfikator pracy 2</span><span class="sxs-lookup"><span data-stu-id="c19b6-287">Work ID 2</span></span> | <span data-ttu-id="c19b6-288">6 każdy (suma obu wierszy)</span><span class="sxs-lookup"><span data-stu-id="c19b6-288">6 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="c19b6-289">Zamówienie sprzedaży 3</span><span class="sxs-lookup"><span data-stu-id="c19b6-289">Sales Order 3</span></span> | <span data-ttu-id="c19b6-290">Identyfikator pracy 3</span><span class="sxs-lookup"><span data-stu-id="c19b6-290">Work ID 3</span></span> | <span data-ttu-id="c19b6-291">15 każdy (suma obu wierszy)</span><span class="sxs-lookup"><span data-stu-id="c19b6-291">15 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="c19b6-292">Zamówienie sprzedaży 4</span><span class="sxs-lookup"><span data-stu-id="c19b6-292">Sales Order 4</span></span> | <span data-ttu-id="c19b6-293">Identyfikator pracy 4</span><span class="sxs-lookup"><span data-stu-id="c19b6-293">Work ID 4</span></span> | <span data-ttu-id="c19b6-294">35 każdy (suma obu wierszy)</span><span class="sxs-lookup"><span data-stu-id="c19b6-294">35 ea (sum of both lines)</span></span> |

<span data-ttu-id="c19b6-295">Przed uruchomieniem przepływu na urządzeniu przenośnym należy upewnić się, że tylko utworzone zadanie ma stan *Otwarte* dla magazynu *51*, oraz że ma nadany typ pracy *Zamówienie sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-295">Before you run the flow on the mobile device, make sure that only the work that you just created is in *Open* status for warehouse *51* and the *Sales order* work order type.</span></span> <span data-ttu-id="c19b6-296">W przeciwnym razie wyniki testu mogą się różnić, ponieważ Pobieranie bezpośrednie przez system będzie obejmowało całą kwalifikującą się pracę.</span><span class="sxs-lookup"><span data-stu-id="c19b6-296">Otherwise, the results of the test might vary, because the system-direct picking will include all eligible work.</span></span>

1. <span data-ttu-id="c19b6-297">Przejdź do **Zarządzanie magazynem \> Praca \> Wychodzące \> Otwarte zlecenia pracy sprzedażowej**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-297">Go to **Warehouse management \> Work \> Outbound \> Open sales work**.</span></span>
1. <span data-ttu-id="c19b6-298">W siatce **Otwarte zlecenia pracy sprzedażowej** odfiltruj wartości w polu **Magazyn**, aby widoczna była tylko praca dla magazynu *51*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-298">In the **Open sales work** grid, filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="c19b6-299">Upewnij się, że zostały wyświetlone tylko cztery identyfikatory pracy, które zostały wcześniej utworzone.</span><span class="sxs-lookup"><span data-stu-id="c19b6-299">Confirm that only the four work IDs that you created earlier are shown.</span></span>
1. <span data-ttu-id="c19b6-300">Zamknij stronę **Praca**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-300">Close the **Work** page.</span></span>

### <a name="mobile-device-flow-execution"></a><span data-ttu-id="c19b6-301">Wykonanie przepływu na urządzeniu przenośnym</span><span class="sxs-lookup"><span data-stu-id="c19b6-301">Mobile device flow execution</span></span>

<span data-ttu-id="c19b6-302">Na podstawie ustawień system będzie przesyłać użytkownikowi informacje o pracy, która jest posortowana od najwyższej ilości w wierszu pracy do najniższej.</span><span class="sxs-lookup"><span data-stu-id="c19b6-302">Based on the setup, the system will feed the user work that is sorted from the highest work line quantity to the lowest.</span></span> <span data-ttu-id="c19b6-303">Ilość w każdym wierszu będzie mniejsza niż 20 ea.</span><span class="sxs-lookup"><span data-stu-id="c19b6-303">The quantity on every line will be less than 20 ea.</span></span>

<span data-ttu-id="c19b6-304">Należy pamiętać, że ta konfiguracja spowoduje przechwycenie elementu pracy, który ma co najmniej jeden wiersz o ilości mniejszej niż 20 ea.</span><span class="sxs-lookup"><span data-stu-id="c19b6-304">Remember that this setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="c19b6-305">Jeśli więc praca ma inny wiersz, w którym ilość wynosi dokładnie 20 ea lub więcej, będzie ona również uznana za prawidłową.</span><span class="sxs-lookup"><span data-stu-id="c19b6-305">Therefore, if the work has another line where the quantity is exactly 20 ea or more than 20 ea, it will also be valid.</span></span>

#### <a name="mobile-app"></a><span data-ttu-id="c19b6-306">Aplikacja mobilna</span><span class="sxs-lookup"><span data-stu-id="c19b6-306">Mobile app</span></span>

1. <span data-ttu-id="c19b6-307">Zaloguj się do aplikacji magazynowania jako użytkownik w magazynie *51*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-307">Sign in to the warehousing app as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="c19b6-308">Przejdź do **Wychodzące \> Pobieranie sprzedaży – system**.</span><span class="sxs-lookup"><span data-stu-id="c19b6-308">Go to **Outbound \> Sales Picking - System**.</span></span>

    <span data-ttu-id="c19b6-309">Przedstawiony jest krok pobrania dla identyfikatora pracy o numerze *4*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-309">The pick step for work ID *4* is presented.</span></span> <span data-ttu-id="c19b6-310">Ten identyfikator pracy jest przedstawiany jako pierwszy z powodu korzystania z konfiguracji zapytań sterowanych przez system, w której określono, że praca powinna być sekwencjonowana na podstawie ilości w wierszu pracy – malejąco.</span><span class="sxs-lookup"><span data-stu-id="c19b6-310">This work ID is presented first because of the setup of the system-directed query order, where you specified that work should be sequenced based on descending work line quantity.</span></span>

1. <span data-ttu-id="c19b6-311">Zakończ wymagane pobranie i zamknij dany identyfikator pracy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-311">Complete the required pick and put to close the work ID.</span></span>

    <span data-ttu-id="c19b6-312">Następnie prezentowany jest identyfikator pracy *3*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-312">Next, work ID *3* is presented.</span></span> <span data-ttu-id="c19b6-313">Jeden ze znajdujących się w nim wierszy jest wybrany jako następny w sekwencji na podstawie ilości w wierszu pracy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-313">One of its work lines is next in the sequence, based on the work line quantity.</span></span>

1. <span data-ttu-id="c19b6-314">Zakończ pobranie i zamknij dany identyfikator pracy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-314">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="c19b6-315">Następnie prezentowany jest identyfikator pracy *2*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-315">Next, work ID *2* is presented.</span></span> <span data-ttu-id="c19b6-316">Wiersz pobrania tego działania jest następny w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="c19b6-316">This work's pick line is next in the sequence.</span></span>

1. <span data-ttu-id="c19b6-317">Zakończ pobranie i zamknij dany identyfikator pracy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-317">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="c19b6-318">Żadne więcej zlecenia pracy nie powinny być wyświetlane użytkownikowi.</span><span class="sxs-lookup"><span data-stu-id="c19b6-318">No further work should be presented to you.</span></span> <span data-ttu-id="c19b6-319">Identyfikator pracy *1* nie kwalifikuje się do tego elementu menu urządzenia przenośnego, ponieważ zapytanie określa, że nagłówki pracy są uwzględniane tylko wtedy, gdy ilość w wierszach pracy ma wartość mniejszą niż 20 ea.</span><span class="sxs-lookup"><span data-stu-id="c19b6-319">Work ID *1* isn't eligible for this mobile device menu item, because the query specifies that work headers are considered only if the quantity on the work lines is less than 20 ea.</span></span>

## <a name="tips"></a><span data-ttu-id="c19b6-320">Porady</span><span class="sxs-lookup"><span data-stu-id="c19b6-320">Tips</span></span>

<span data-ttu-id="c19b6-321">Zapytanie dotyczące sekwencji pracy sterowanej przez system ma wartość *zawierająca*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-321">The system-directed work sequence queries are *inclusive*.</span></span> <span data-ttu-id="c19b6-322">Ważne jest, aby pamiętać o tym fakcie w przypadku niektórych konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c19b6-322">It's important that you remember this fact for some setups.</span></span> <span data-ttu-id="c19b6-323">Można na przykład określić, że określony element menu ma przetwarzać tylko pracę, w której jednostka pracy ma wartość *ea* – ograniczenie to jest określane na karcie **Zakres** w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="c19b6-323">For example, you want a specific menu item to process only work where the work unit is *ea*, and you specify that restriction on the **Range** tab of the query.</span></span> <span data-ttu-id="c19b6-324">W tym przypadku wszystkie elementy pracy, w której co najmniej jeden wiersz pracy ma ustawioną jednostkę roboczą na wartość *ea* zostanie przekazana pracownikowi.</span><span class="sxs-lookup"><span data-stu-id="c19b6-324">In this case, all work where at least one work line has the work unit set to *ea* will be fed to the worker.</span></span> <span data-ttu-id="c19b6-325">Dlatego to zadanie może również obejmować pracę, w której wiersze pracy mają jednostkę roboczą inną niż *ea* (np *pudełko* lub *paleta*).</span><span class="sxs-lookup"><span data-stu-id="c19b6-325">Therefore, this work might also include work where work lines have a work unit other than *ea* (such as *box* or *pallet*).</span></span> <span data-ttu-id="c19b6-326">Zapytanie wykluczy tylko te elementy, w których żaden wiersz pracy nie ma jednostki roboczej ustawionej na wartość *ea*.</span><span class="sxs-lookup"><span data-stu-id="c19b6-326">The query will exclude only work where no work line has the work unit set to *ea*.</span></span>

<span data-ttu-id="c19b6-327">Dlatego w przykładzie z tego scenariusza identyfikator pracy *4* również został wyświetlony w ramach zapytania.</span><span class="sxs-lookup"><span data-stu-id="c19b6-327">Therefore, in the example from this scenario, work ID *4* was also captured by the query.</span></span> <span data-ttu-id="c19b6-328">Po jego utworzeniu dodano dwa wiersze: jeden dla 25 ea, a drugi dla 10 ea.</span><span class="sxs-lookup"><span data-stu-id="c19b6-328">When it was created, two lines were added: one for 25 ea and another for 10 ea.</span></span> <span data-ttu-id="c19b6-329">Praca została przekazana użytkownikowi, ponieważ co najmniej jeden wiersz pracy miał ilość mniejszą niż 20 ea.</span><span class="sxs-lookup"><span data-stu-id="c19b6-329">The work was still presented to the user, because at least one work line has a quantity of less than 20 ea.</span></span>

<span data-ttu-id="c19b6-330">W zależności od scenariusza można uniknąć takiego zachowania, korzystając z podziału pracy.</span><span class="sxs-lookup"><span data-stu-id="c19b6-330">Depending on the scenario, you can prevent this behavior by using work breaks.</span></span>
