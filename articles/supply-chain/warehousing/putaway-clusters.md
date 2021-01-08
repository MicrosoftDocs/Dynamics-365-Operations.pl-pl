---
title: Grupy odłożenia
description: Grupy odłożenia umożliwiają w tym samym czasie pobieranie wielu numerów identyfikacyjnych, a następnie ich odłożenie w różnych lokalizacjach. Mogą być bardzo przydatne w firmach detalicznych, w których numery identyfikacyjne zazwyczaj nie są pełnymi paletami zapasów.
author: Mirzaab
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a330ddccbd17c92443232fc8488e36a59235773
ms.sourcegitcommit: cfd84321fba38e02e270d361df369a536a48efa3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "4512337"
---
# <a name="putaway-clusters"></a><span data-ttu-id="6a5c9-104">Grupy odłożenia</span><span class="sxs-lookup"><span data-stu-id="6a5c9-104">Putaway clusters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6a5c9-105">Grupy odłożenia umożliwiają w tym samym czasie pobieranie wielu numerów identyfikacyjnych, a następnie ich odłożenie w różnych lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-105">Putaway clusters offer a way to pick multiple license plates at the same time and then take them for putaway in different locations.</span></span> <span data-ttu-id="6a5c9-106">Ten proces jest często nazywany *trasą objazdową*.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-106">This process is often referred to as a *milk run*.</span></span> <span data-ttu-id="6a5c9-107">Grupy odłożenia mogą być bardzo przydatne w firmach detalicznych, w których numery identyfikacyjne zazwyczaj nie są pełnymi paletami zapasów.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-107">Putaway clusters can be very useful for retail businesses, where license plates typically aren't full pallets of inventory.</span></span> 

## <a name="turn-on-the-cluster-putaway-feature"></a><span data-ttu-id="6a5c9-108">Włącz funkcję grup odłożenia</span><span class="sxs-lookup"><span data-stu-id="6a5c9-108">Turn on the cluster putaway feature</span></span>

<span data-ttu-id="6a5c9-109">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-109">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="6a5c9-110">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6a5c9-111">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6a5c9-112">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6a5c9-113">**Nazwa funkcji:** *Funkcja grup odłożenia*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-113">**Feature name:** *Cluster putaway feature*</span></span>

## <a name="setup-for-the-example-scenario"></a><span data-ttu-id="6a5c9-114">Konfiguracja scenariusza przykładowego</span><span class="sxs-lookup"><span data-stu-id="6a5c9-114">Setup for the example scenario</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="6a5c9-115">Profile grup</span><span class="sxs-lookup"><span data-stu-id="6a5c9-115">Cluster profiles</span></span>

<span data-ttu-id="6a5c9-116">Profil grupy odłożenia określa miejsce, do którego trafia towar, na podstawie lokalizacji przypisanej do towaru w momencie przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-116">The putaway cluster profile determines where an item will go, based on the location that is assigned to the item at the time of receipt.</span></span> <span data-ttu-id="6a5c9-117">Jeśli wymagane są różne grupy, dla każdego elementu menu urządzenia przenośnego należy utworzyć inne grupy odłożenia.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-117">If different clusters are required, different putaway clusters should be created, one for each mobile device menu item.</span></span>

1. <span data-ttu-id="6a5c9-118">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Profile grup**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-118">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="6a5c9-119">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-119">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6a5c9-120">W widoku **Nagłówek** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-120">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="6a5c9-121">**Identyfikator profilu grupy odłożenia:** *Grupa odłożenia*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-121">**Putaway cluster profile ID:** *Cluster putaway*</span></span>
    - <span data-ttu-id="6a5c9-122">**Nazwa identyfikacyjna profilu grupy odłożenia:** *Grupa odłożenia*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-122">**Putaway cluster profile ID Name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="6a5c9-123">**Typ grupy:** *Odłożenie*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-123">**Cluster type:** *Putaway*</span></span>
    - <span data-ttu-id="6a5c9-124">**Numer sekwencyjny:** Zaakceptuj wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-124">**Sequence number:** Accept the default value.</span></span>

1. <span data-ttu-id="6a5c9-125">Wybierz opcję **Zapisz**, aby wymagane pola na skróconej karcie **Ogólne** stały się dostępne.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-125">Select **Save** to make the required fields on the **General** FastTab available.</span></span>
1. <span data-ttu-id="6a5c9-126">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-126">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6a5c9-127">**Czas przypisania grupy:** *Przy odbiorze*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-127">**Cluster assignment timing:** *At receipt*</span></span>

        <span data-ttu-id="6a5c9-128">To pole określa, czy grupa odkładania powinna być przypisywana natychmiast po odebraniu zapasów, czy też powinna być posortowana później.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-128">This field defines whether the putaway cluster should be assigned immediately when the inventory is received, or whether it should be sorted later.</span></span>

    - <span data-ttu-id="6a5c9-129">**Reguła przypisania grupy:** *Ręcznie*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-129">**Cluster assignment rule:** *Manual*</span></span>

        <span data-ttu-id="6a5c9-130">To pole określa, czy przypisanie klastra powinno być określone automatycznie przez system, czy ręcznie przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-130">This field defines whether the cluster assignment should be determined automatically by the system or manually by the user.</span></span>

    - <span data-ttu-id="6a5c9-131">Pole **Kod dyrektywy:** należy pozostawić puste.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-131">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="6a5c9-132">**Lokalizowanie grupy odłożenia:** *Odbiór*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-132">**Putaway cluster locate:** *Receipt*</span></span>

        <span data-ttu-id="6a5c9-133">Dostępne są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-133">The following values are available:</span></span>

        - <span data-ttu-id="6a5c9-134">**Odbiór** – Lokalizacja jest znajdowana natychmiast po odbiorze.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-134">**Receipt** – A location is found immediately during receipt.</span></span>
        - <span data-ttu-id="6a5c9-135">**Zamknięcie grupy** — po zamknięciu grupy zostanie wyszukana lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-135">**Cluster close** – A location is found when the cluster is closed.</span></span>
        - <span data-ttu-id="6a5c9-136">**Sterowane przez użytkownika** — lokalizacja jest znajdowana, gdy numer identyfikacyjny jest pobierany z grupy do odłożenia.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-136">**User directed** – A location is found when the license plate is picked from the cluster for putaway.</span></span> <span data-ttu-id="6a5c9-137">W takim przypadku podczas tworzenia pracy odłożenia nie jest określana żadna lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-137">In this case, no location is specified when the putaway work is created.</span></span> <span data-ttu-id="6a5c9-138">Podczas samego odkładania użytkownik musi zeskanować numer identyfikacyjny lub identyfikator pracy, aby zainicjować krok odkładania.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-138">During the putaway itself, the user must scan the license plate or work ID to initiate the put step.</span></span> <span data-ttu-id="6a5c9-139">Następnie system znajduje ponownie lokalizację odkładania i informuje użytkownika, gdzie ma zostać umieszczona pobrana ilość.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-139">The system then finds the put location again and tells the user where to put the picked quantity.</span></span>

    - <span data-ttu-id="6a5c9-140">**Grupa odkładania na użytkownika:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-140">**Putaway cluster per user:** *No*</span></span>

        <span data-ttu-id="6a5c9-141">To pole określa, czy każda grupa powinna być unikalna dla użytkownika, gdy grupy są przypisywane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-141">This field defines whether each cluster should be unique per user when clusters are automatically assigned.</span></span> <span data-ttu-id="6a5c9-142">Jest dostępna tylko wtedy, gdy w polu **Reguła przypisania grupy** ustawiono wartość *Automatyczna*.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-142">It's available only when the **Cluster assignment rule** field is set to *Automatic*.</span></span>

    - <span data-ttu-id="6a5c9-143">**Ograniczenie jednostki:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-143">**Unit restriction:** Leave this field blank.</span></span>

        <span data-ttu-id="6a5c9-144">To pole określa jednostkę, która musi zostać odebrana, aby profil był ważny.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-144">This field defines the unit that must be received for the profile to be valid.</span></span> <span data-ttu-id="6a5c9-145">Jeśli pole pozostanie puste, wszystkie jednostki będą obowiązywały.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-145">If it's left blank, all units are valid.</span></span>

    - <span data-ttu-id="6a5c9-146">**Przerwa jednostki roboczej**: *Pojedyncza*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-146">**Work unit break:** *Individual*</span></span>

        <span data-ttu-id="6a5c9-147">To pole określa, czy wszystkie zapasy powinny być konsolidowane (przy użyciu identyfikatora grupy i numeru identyfikacyjnego) na jeden numer identyfikacyjny, gdy grupa jest zamknięta, a także czy powinny być odłożone jako pojedynczy numer identyfikacyjny, czy też zostać odłączone od otrzymanych numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-147">This field defines whether all inventory should be consolidated (by using the cluster ID and the license plate) onto one license plate when a cluster is closed, and whether it should be put away as a single license plate or separately on the license plates that were received.</span></span> <span data-ttu-id="6a5c9-148">To pole jest niedostępne, jeśli w polu **Znajdź grupę odłożenia** jest ustawiona wartość *Odbiór*.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-148">This field is unavailable when the **Putaway cluster locate** field is set to *Receipt*.</span></span>

    - <span data-ttu-id="6a5c9-149">**Grupa pozostaje jako nadrzędny numer identyfikacyjny:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-149">**Cluster persists as Parent License Plate:** *No*</span></span>

        <span data-ttu-id="6a5c9-150">Jeśli ta opcja jest ustawiona na wartość *Tak*, po zakończeniu kroku wstawiania identyfikator klastra stanie się nadrzędną tablicą rejestracyjną, a wszystkie elementy w identyfikatorze klastra zostaną połączone z tym nadrzędnym numerem rejestracyjnym.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-150">If this option is set to *Yes*, when the put step is completed, the cluster ID will become a parent license plate, and all items on the cluster ID will be linked to that parent license plate.</span></span>

1. <span data-ttu-id="6a5c9-151">Na skróconej karcie **Sortowanie grup** można definiować kryteria sortowania odkładania.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-151">On the **Cluster sorting** FastTab, you can define putaway sorting criteria.</span></span> <span data-ttu-id="6a5c9-152">Wybierz na pasku narzędzi **Nowe** i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-152">Select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="6a5c9-153">**Numer sekwencyjny:** Zaakceptuj wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-153">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="6a5c9-154">**Nazwa pola:** *WMSLocationId*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-154">**Field name:** *WMSLocationId*</span></span>

        <span data-ttu-id="6a5c9-155">To pole definiuje pole, które ma być używane przez ten wiersz jako kryterium sortowania.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-155">This field defines the field that this line should use as a sorting criterion.</span></span>

    - <span data-ttu-id="6a5c9-156">**Sortowanie:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-156">**Sorting:** *Ascending*</span></span>

        <span data-ttu-id="6a5c9-157">To pole określa, czy sortowanie powinno odbywać się w porządku rosnącym czy malejącym.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-157">This field defines whether sorting should be done in ascending or descending order.</span></span>

1. <span data-ttu-id="6a5c9-158">Na skróconej karcie **Szablon grupy pracy** wybierz opcję **Nowy** na pasku narzędzi, aby dodać wiersz, a następnie określ dla niego następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-158">On the **Cluster work template** FastTab, select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="6a5c9-159">**Typ zlecenia pracy:** *Zamówienie zakupu*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-159">**Work order type:** *Purchase orders*</span></span>
    - <span data-ttu-id="6a5c9-160">**Szablon pracy:** *61 bezpośrednie zamówienie zakupu*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-160">**Work template:** *61 PO Direct*</span></span>

1. <span data-ttu-id="6a5c9-161">W okienku akcji wybierz opcję **Zapisz**, a następnie wybierz opcję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-161">On the Action Pane, select **Save**, and then select **Edit query**.</span></span>
1. <span data-ttu-id="6a5c9-162">W oknie dialogowym **Grupa odłożenia**, na karcie **Zakres** wybierz **Dodaj**, aby dodać drugą linię do zapytania.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-162">In the **Cluster putaway** dialog box, on the **Range** tab, select **Add** to add a second line to the query.</span></span> <span data-ttu-id="6a5c9-163">Następnie zaktualizuj wiersze zapytania, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-163">Then update the query lines as shown in the following table.</span></span>

    | <span data-ttu-id="6a5c9-164">Tabela</span><span class="sxs-lookup"><span data-stu-id="6a5c9-164">Table</span></span> | <span data-ttu-id="6a5c9-165">Tabela pochodna</span><span class="sxs-lookup"><span data-stu-id="6a5c9-165">Derived table</span></span> | <span data-ttu-id="6a5c9-166">Pole</span><span class="sxs-lookup"><span data-stu-id="6a5c9-166">Field</span></span> | <span data-ttu-id="6a5c9-167">Kryterium</span><span class="sxs-lookup"><span data-stu-id="6a5c9-167">Criteria</span></span> |
    |---|---|---|---|
    | <span data-ttu-id="6a5c9-168">Roboczy</span><span class="sxs-lookup"><span data-stu-id="6a5c9-168">Work</span></span> | <span data-ttu-id="6a5c9-169">Roboczy</span><span class="sxs-lookup"><span data-stu-id="6a5c9-169">Work</span></span> | <span data-ttu-id="6a5c9-170">Magazyn</span><span class="sxs-lookup"><span data-stu-id="6a5c9-170">Warehouse</span></span> | <span data-ttu-id="6a5c9-171">*61*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-171">*61*</span></span> |
    | <span data-ttu-id="6a5c9-172">Roboczy</span><span class="sxs-lookup"><span data-stu-id="6a5c9-172">Work</span></span> | <span data-ttu-id="6a5c9-173">Roboczy</span><span class="sxs-lookup"><span data-stu-id="6a5c9-173">Work</span></span> | <span data-ttu-id="6a5c9-174">Identyfikator pracy</span><span class="sxs-lookup"><span data-stu-id="6a5c9-174">Work ID</span></span> | <span data-ttu-id="6a5c9-175">To pole należy pozostawić puste.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-175">Leave this field blank.</span></span> |

1. <span data-ttu-id="6a5c9-176">Wybierz **OK**, zapisać kwerendę i zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-176">Select **OK** to save the query and close the dialog box.</span></span>
1. <span data-ttu-id="6a5c9-177">W okienku akcji wybierz **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-177">On the Action Pane, select **Save**, and close the page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a5c9-178">Pola w profilu grupy, które są przyciemniane, gdy **Generuj identyfikator grupy** ma wartość *Tak*, są niedostępne i nie będą brane pod uwagę, gdy używana jest ta funkcja.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-178">Fields in the cluster profile that appear dimmed when **Generate cluster ID** is set to *Yes* are unavailable and won't be considered when this feature is used.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="6a5c9-179">Elementy menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="6a5c9-179">Mobile device menu items</span></span>

<span data-ttu-id="6a5c9-180">Dla tej funkcji są dostępne dwa nowe elementy menu urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-180">Two new mobile device menu items are available for this feature.</span></span> <span data-ttu-id="6a5c9-181">Element menu **Odbiór i sortowanie grupy** jest używany do sortowania odebranych zapasów w grupie odłożenia po otrzymaniu.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-181">The **Receive and sort cluster** menu item is used to sort the received inventory into a putaway cluster upon receipt.</span></span> <span data-ttu-id="6a5c9-182">Element menu **Grupa odłożenia** jest używany do odłożenia grupy po jej przypisaniu.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-182">The **Cluster putaway** menu item is used to put the cluster away after it has been assigned.</span></span>

#### <a name="receive-and-sort-cluster"></a><span data-ttu-id="6a5c9-183">Odbiór i sortowanie grupy</span><span class="sxs-lookup"><span data-stu-id="6a5c9-183">Receive and sort cluster</span></span>

<span data-ttu-id="6a5c9-184">Umożliwia utworzenie nowego elementu menu urządzenia przenośnego służącego do odbierania zapasów i sortowania do grupy.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-184">Create a new mobile device menu item for receiving inventory and sorting into a cluster.</span></span> <span data-ttu-id="6a5c9-185">Ta pozycja menu utworzy pracę przychodzącą po otrzymaniu zapasów, co oznacza, że pozycja menu odbioru będzie używana dla grup odkładania.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-185">This menu item will create inbound work after inventory is received, which indicates that the receiving menu item will be used for putaway clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="6a5c9-186">Element menu **Odbiór i sortowanie grupy** można używać z następującymi elementami menu odbioru:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-186">The **Receive and sort cluster** menu item can be used with the following receiving menu items:</span></span>
>
> - <span data-ttu-id="6a5c9-187">Przyjęcie wiersza zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="6a5c9-187">Purchase order line receiving</span></span>
> - <span data-ttu-id="6a5c9-188">Przyjęcie pozycji z zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="6a5c9-188">Purchase order item receiving</span></span>
> - <span data-ttu-id="6a5c9-189">Odbierana pozycja ładunku</span><span class="sxs-lookup"><span data-stu-id="6a5c9-189">Load item receiving</span></span>

1. <span data-ttu-id="6a5c9-190">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-190">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6a5c9-191">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-191">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6a5c9-192">W widoku **Nagłówek** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-192">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="6a5c9-193">**Nazwa elementu menu:** *Odbiór i sortowanie grupy*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-193">**Menu item name:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="6a5c9-194">**Nazwa:** *Odbiór i sortowanie grupy*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-194">**Title:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="6a5c9-195">**Tryb:** *Praca*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-195">**Mode:** *Work*</span></span>
    - <span data-ttu-id="6a5c9-196">**Używanie istniejącej pracy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-196">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="6a5c9-197">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-197">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6a5c9-198">**Proces tworzenia pracy:** *Przyjęcie pozycji z zamówienia zakupu*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-198">**Work creation process:** *Purchase order item receiving*</span></span>
    - <span data-ttu-id="6a5c9-199">**Generuj numer identyfikacyjny:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-199">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="6a5c9-200">**Przypisz grupę odłożenia** *Tak*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-200">**Assign putaway cluster:** *Yes*</span></span>

        > [!NOTE]
        > <span data-ttu-id="6a5c9-201">Opcja **Przypisz grupę odłożenia** jest dostępna tylko dla jednoetapowego działania *Proces tworzenia pracy* w celu odbioru.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-201">The **Assign putaway cluster** option is available only for the one-step *Work creation process* activity for receiving.</span></span>

    <span data-ttu-id="6a5c9-202">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-202">Accept the default values for the remaining fields.</span></span>

1. <span data-ttu-id="6a5c9-203">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-203">On the Action Pane, select **Save**.</span></span>

#### <a name="cluster-putaway"></a><span data-ttu-id="6a5c9-204">Odłożenie klastra</span><span class="sxs-lookup"><span data-stu-id="6a5c9-204">Cluster putaway</span></span>

<span data-ttu-id="6a5c9-205">Utwórz nowy element menu urządzenia przenośnego, aby umieścić grupę po jej przypisaniu.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-205">Create a new mobile device menu item for putting the cluster away after it has been assigned.</span></span>

1. <span data-ttu-id="6a5c9-206">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6a5c9-207">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-207">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6a5c9-208">W widoku **Nagłówek** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-208">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="6a5c9-209">**Nazwa elementu menu:** *Grupa odłożenia*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-209">**Menu item name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="6a5c9-210">**Nazwa:** *Grupa odłożenia*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-210">**Title:** *Cluster putaway*</span></span>
    - <span data-ttu-id="6a5c9-211">**Tryb:** *Praca*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-211">**Mode:** *Work*</span></span>
    - <span data-ttu-id="6a5c9-212">**Używanie istniejącej pracy:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-212">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="6a5c9-213">Na skróconej karcie **Ogólne**, pole **Sterowane przez** powinno być ustawione na wartość *Grupa odłożenia*.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-213">On the **General** FastTab, set the **Directed by** field to *Cluster putaway*.</span></span> <span data-ttu-id="6a5c9-214">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-214">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="6a5c9-215">Na skróconej karcie **Klasy pracy** skonfiguruj prawidłową klasę roboczą dla tego elementu menu urządzenia przenośnego:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-215">On the **Work classes** FastTab, set up the valid work class for this mobile device menu item:</span></span>

    - <span data-ttu-id="6a5c9-216">**Identyfikator klasy roboczej:** *Zakup*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-216">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="6a5c9-217">**Typ zlecenia pracy:** *Zamówienie zakupu*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-217">**Work order type:** *Purchase orders*</span></span>

1. <span data-ttu-id="6a5c9-218">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-218">On the Action Pane, select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="6a5c9-219">Menu urządzeń przenośnych</span><span class="sxs-lookup"><span data-stu-id="6a5c9-219">Mobile device menu</span></span>

<span data-ttu-id="6a5c9-220">Dodaj właśnie utworzone pozycje menu do menu przychodzącego aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-220">Add the menu items that you just created to the inbound menu of the mobile app.</span></span>

1. <span data-ttu-id="6a5c9-221">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-221">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="6a5c9-222">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-222">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="6a5c9-223">Z listy menu wybierz opcję **Przychodzące**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-223">In the menu list, select **Inbound**.</span></span>
1. <span data-ttu-id="6a5c9-224">Na liście **Dostępne menu i elementy menu** znajdź i zaznacz element menu **Odbiór i sortowanie grupy**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-224">In the **Available menus and menu items** list, find and select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="6a5c9-225">Wybierz przycisk strzałki w prawo, aby przenieść wybraną pozycję menu na listę **Struktura menu**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-225">Select the right arrow button to move the selected menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="6a5c9-226">Za pomocą przycisku strzałki w górę lub w dół przenieś element menu w żądane miejsce w menu.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-226">Use the up arrow or down arrow button to move the menu item into the desired position in the menu.</span></span>
1. <span data-ttu-id="6a5c9-227">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-227">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6a5c9-228">Powtórz kroki od 4 do 7, aby dodać pozostałe elementy menu:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-228">Repeat steps 4 through 7 to add the remaining menu items:</span></span>

    - <span data-ttu-id="6a5c9-229">Przypisz grupę</span><span class="sxs-lookup"><span data-stu-id="6a5c9-229">Assign cluster</span></span>
    - <span data-ttu-id="6a5c9-230">Odłożenie klastra</span><span class="sxs-lookup"><span data-stu-id="6a5c9-230">Cluster putaway</span></span>

## <a name="example-scenario"></a><span data-ttu-id="6a5c9-231">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="6a5c9-231">Example scenario</span></span>

<span data-ttu-id="6a5c9-232">Ten scenariusz symuluje przetwarzanie grupy odłożenia.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-232">This scenario simulates putaway cluster processing.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="6a5c9-233">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="6a5c9-233">Create a purchase order</span></span>

1. <span data-ttu-id="6a5c9-234">Wybierz kolejno opcje **Rozrachunki z dostawcami \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-234">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="6a5c9-235">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6a5c9-236">W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-236">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6a5c9-237">**Konto dostawcy:** *1001*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-237">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="6a5c9-238">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-238">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="6a5c9-239">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-239">Select **OK**.</span></span>

    <span data-ttu-id="6a5c9-240">Wyświetli się **Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-240">The **All purchase orders** page appears.</span></span>

1. <span data-ttu-id="6a5c9-241">Na stronie **Wszystkie zamówienia zakupu** na skróconej karcie **Wiersze zamówienia zakupu** użyj przycisku **Dodaj wiersz**, aby dodać następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-241">On the **All purchase orders** page, on the **Purchase order lines** FastTab, use the **Add line** button to add the following lines:</span></span>

    - <span data-ttu-id="6a5c9-242">Wiersz zamówienia zakupu 1:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-242">Purchase order line 1:</span></span>

        - <span data-ttu-id="6a5c9-243">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-243">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="6a5c9-244">**Ilość:** *10*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-244">**Quantity:** *10*</span></span>

    - <span data-ttu-id="6a5c9-245">Wiersz zamówienia zakupu 2:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-245">Purchase order line 2:</span></span>

        - <span data-ttu-id="6a5c9-246">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-246">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="6a5c9-247">**Ilość:** *20*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-247">**Quantity:** *20*</span></span>

    - <span data-ttu-id="6a5c9-248">Wiersz zamówienia zakupu 3:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-248">Purchase order line 3:</span></span>

        - <span data-ttu-id="6a5c9-249">**Numer pozycji:** *M9215*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-249">**Item number:** *M9215*</span></span>
        - <span data-ttu-id="6a5c9-250">**Ilość:** *30*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-250">**Quantity:** *30*</span></span>

1. <span data-ttu-id="6a5c9-251">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-251">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6a5c9-252">Zanotuj numer zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-252">Make a note of the purchase order number.</span></span>

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a><span data-ttu-id="6a5c9-253">Odbierz zapasy i odłóż je z urządzenia mobilnego</span><span class="sxs-lookup"><span data-stu-id="6a5c9-253">Receive inventory and put it away from the mobile device</span></span>

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a><span data-ttu-id="6a5c9-254">Przyjmowanie i sortowanie zapasów w grupie</span><span class="sxs-lookup"><span data-stu-id="6a5c9-254">Receive and sort the inventory into a cluster</span></span>

1. <span data-ttu-id="6a5c9-255">Zaloguj się do aplikacji magazynowej jako użytkownik, który jest skonfigurowany dla magazynu *61*.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-255">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="6a5c9-256">W menu głównym wybierz opcję **Przychodzące**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-256">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="6a5c9-257">W menu **Przychodzące** wybierz opcję **Odbiór i sortowanie grupy**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-257">On the **Inbound** menu, select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="6a5c9-258">W polu **Ponum** wprowadź numer zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-258">In the **Ponum** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="6a5c9-259">Wybierz **OK** (symbol znacznika wyboru).</span><span class="sxs-lookup"><span data-stu-id="6a5c9-259">Select **OK** (the check mark button).</span></span>
1. <span data-ttu-id="6a5c9-260">Zaznacz pole **Pozycja**, a następnie wprowadź numer pozycji *A0001*, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-260">Select the **Item** field, enter item number *A0001*, and then select **OK**.</span></span>
1. <span data-ttu-id="6a5c9-261">Zaznacz pole **Ilość**, wprowadź wartość *10* za pomocą klawiatury numerycznej, a następnie zaznacz przycisk znacznik wyboru.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-261">Select the **Qty** field, enter *10* by using the number pad, and then select the check mark button.</span></span>
1. <span data-ttu-id="6a5c9-262">Na stronie zadania **Ilość** wybierz **OK** (przycisk ze znakiem wyboru), aby potwierdzić wprowadzoną ilość.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-262">On the **Qty** task page, select **OK** (the check mark button) to confirm the quantity that you entered.</span></span>
1. <span data-ttu-id="6a5c9-263">Na stronie zadanie **Pozycja** wybierz przycisk **OK**, aby potwierdzić, że została wprowadzona pozycja *A0001*.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-263">On the **Item** task page, select **OK** to confirm that item *A0001* was entered.</span></span>
1. <span data-ttu-id="6a5c9-264">Zaznacz pole **Identyfikator grupy** i wprowadź wartość, aby przypisać identyfikator tworzonej grupy.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-264">Select the **Cluster ID** field, and enter a value to assign an ID for the cluster that you're creating.</span></span>

    <span data-ttu-id="6a5c9-265">Wprowadzony tutaj identyfikator będzie używany po otrzymaniu dwóch pozostałych pozycji na zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-265">The ID that you enter here will be used when the two remaining items on the purchase order are received.</span></span>

1. <span data-ttu-id="6a5c9-266">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-266">Select **OK**.</span></span>

    <span data-ttu-id="6a5c9-267">Zostanie wyświetlona strona zadania **Ponum** z komunikatem „Praca zakończona”.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-267">The **Ponum** task page appears and shows a "Work completed" message.</span></span>

    <span data-ttu-id="6a5c9-268">Pozycja *A0001* została odebrana w lokalizacji *RECV* i przypisana do identyfikatora grupy wprowadzonego w kroku 10.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-268">Item *A0001* has now been received into the *RECV* location and assigned to the cluster ID that you entered in step 10.</span></span>

1. <span data-ttu-id="6a5c9-269">Powtórz kroki od 4 do 11, aby otrzymać pozostałe dwa elementy z zamówienia i przypisz je do identyfikatora klastra:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-269">Repeat steps 4 through 11 to receive the remaining two items from the purchase order and assign them to the cluster ID:</span></span>

    - <span data-ttu-id="6a5c9-270">Ilość *20* dla pozycji *A0002*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-270">A quantity of *20* for item *A0002*</span></span>
    - <span data-ttu-id="6a5c9-271">Ilość *30* dla pozycji *M9215*</span><span class="sxs-lookup"><span data-stu-id="6a5c9-271">A quantity of *30* for item *M9215*</span></span>

#### <a name="close-the-cluster"></a><span data-ttu-id="6a5c9-272">Zamknij grupę</span><span class="sxs-lookup"><span data-stu-id="6a5c9-272">Close the cluster</span></span>

<span data-ttu-id="6a5c9-273">Aby możliwe było odłożenie elementów w grupie, należy zamknąć grupę.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-273">Before the items in the cluster can be put away, the cluster must be closed.</span></span>

1. <span data-ttu-id="6a5c9-274">W Supply Chain Management, przejdź do **Zarządzanie magazynem \> Praca \> Wychodzące \> Grupy pracy**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-274">In Supply Chain Management, go to **Warehouse management \> Work \> Outbound \> Work clusters**.</span></span>
1. <span data-ttu-id="6a5c9-275">Na stronie **Grupy pracy** w sekcji **Grupa pracy** wyszukaj pole **Identyfikator grupy** odpowiadające wprowadzonemu wcześniej identyfikatorowi grupy.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-275">On the **Work clusters** page, in the **Work cluster** section, search the **Cluster ID** field for the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="6a5c9-276">Jeśli grupa nie jest wyświetlana, być może została już zamknięta.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-276">If the cluster isn't shown, it might already have been closed.</span></span> <span data-ttu-id="6a5c9-277">Aby ustalić, czy grupa została zamknięta, zaznacz pole wyboru **Pokaż zamkniętą pracę** i wyszukaj wprowadzony wcześniej identyfikator grupy.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-277">To determine whether the cluster was closed, select the **Show closed work** check box, and search for the cluster ID that you entered earlier.</span></span> <span data-ttu-id="6a5c9-278">Następnie wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="6a5c9-278">Then follow one of these steps:</span></span>

    - <span data-ttu-id="6a5c9-279">Jeśli grupa została zamknięta, pomiń pozostałe kroki tej procedury i przejdź do następnej procedury, [Odłóż grupę](#put-the-cluster-away).</span><span class="sxs-lookup"><span data-stu-id="6a5c9-279">If the cluster has been closed, skip the remaining steps of this procedure, and move on to the next procedure, [Put the cluster away](#put-the-cluster-away).</span></span>
    - <span data-ttu-id="6a5c9-280">Jeśli grupa nie została zamknięta, wykonaj pozostałe kroki tej procedury, aby ręcznie zamknąć grupę.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-280">If the cluster hasn't been closed, follow the remaining steps of this procedure to manually close the cluster.</span></span> <span data-ttu-id="6a5c9-281">Następnie należy przejść do następujące sekcji.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-281">Then move on to the next procedure.</span></span>

1. <span data-ttu-id="6a5c9-282">W sekcji **Grupa pracy** wybierz wcześniej wprowadzony identyfikator grupy.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-282">In the **Work cluster** section, select the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="6a5c9-283">W okienku akcji wybierz opcję **Zamknij grupę**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-283">On the Action Pane, select **Close cluster**.</span></span>

    <span data-ttu-id="6a5c9-284">Po zamknięciu grupy nie jest już wyświetlana w sekcji **Grupa pracy** (chyba że zaznaczono pole wyboru **Pokaż zamkniętą pracę**).</span><span class="sxs-lookup"><span data-stu-id="6a5c9-284">After the cluster has been closed, it's no longer shown in the **Work cluster** section (unless the **Show closed work** check box is selected).</span></span>

#### <a name="put-the-cluster-away"></a><span data-ttu-id="6a5c9-285">Odłóż grupę</span><span class="sxs-lookup"><span data-stu-id="6a5c9-285">Put the cluster away</span></span>

1. <span data-ttu-id="6a5c9-286">Zaloguj się do aplikacji magazynowej jako użytkownik, który jest skonfigurowany dla magazynu *61*.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-286">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="6a5c9-287">W menu głównym wybierz opcję **Przychodzące**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-287">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="6a5c9-288">W menu **Przychodzące** wybierz **Grupa odłożenia**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-288">On the **Inbound** menu, select **Cluster putaway**.</span></span>
1. <span data-ttu-id="6a5c9-289">Wybierz **Identyfikator grupy** i wprowadź identyfikator grupy, który został wprowadzony wcześniej dla zamkniętej grupy.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-289">Select **Cluster ID**, and enter the cluster ID that you entered earlier for the closed cluster.</span></span>
1. <span data-ttu-id="6a5c9-290">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-290">Select **OK**.</span></span>

    <span data-ttu-id="6a5c9-291">Zostanie wyświetlona strona **Grupa odłożenia: Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-291">The **Cluster putaway: Pick** page appears.</span></span> <span data-ttu-id="6a5c9-292">Pokazuje identyfikator grupy, lokalizację pobrania, elementy (zostanie wyświetlona wartość *Wiele*) oraz całkowitą ilość w grupie, która musi zostać pobrana.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-292">It shows the cluster ID, the picking location, the items (the value *Multiple* will be shown), and the total quantity in the cluster that must be picked.</span></span>

1. <span data-ttu-id="6a5c9-293">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-293">Select **OK**.</span></span>

    <span data-ttu-id="6a5c9-294">Zostanie wyświetlona strona **Grupa odłożenia: Odłóż**.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-294">The **Cluster putaway: Put** page appears.</span></span> <span data-ttu-id="6a5c9-295">Instrukcje **Odłóż** identyfikują identyfikator grupy, lokalizację odłożenia, pozycje, ilość całkowitą oraz identyfikatory numerów identyfikacyjnych dla pozycji, które zostały odebrane w grupie.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-295">The **Put** instructions identify the cluster ID, the put location, the items, the total quantity, and the license plate IDs for the items that have been received on the cluster.</span></span>

    <span data-ttu-id="6a5c9-296">Masz standardowe opcje zastąpienia lub przejścia tego kroku.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-296">You have the standard options to override or pass this step.</span></span>

    <span data-ttu-id="6a5c9-297">![Strona Grupa odłożenia: Odłożenie](media/Cluster_putaway-Put.png "Strona Grupa odłożenia: Odłożenie")</span><span class="sxs-lookup"><span data-stu-id="6a5c9-297">![Cluster putaway: Put page](media/Cluster_putaway-Put.png "Cluster putaway: Put page")</span></span>

1. <span data-ttu-id="6a5c9-298">Wybierz **OK**, aby potwierdzić odłożenie grupy.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-298">Select **OK** to confirm the putaway of the cluster.</span></span>

    <span data-ttu-id="6a5c9-299">Wyświetlany jest komunikat „Grupa zakończona”.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-299">A "Cluster completed" message is shown.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="6a5c9-300">Notatki i porady</span><span class="sxs-lookup"><span data-stu-id="6a5c9-300">Notes and tips</span></span>

<span data-ttu-id="6a5c9-301">W przypadku, gdy identyfikator grupy staje się nadrzędnym numerem identyfikacyjnym dla zagnieżdżonej palety, pozycja jest automatycznie podawana podczas skanowania identyfikatora grupy.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-301">For cases where the cluster ID becomes the parent license plate for a nested pallet, the put position is automatically given when the cluster ID is scanned.</span></span> <span data-ttu-id="6a5c9-302">Nie trzeba skanować kolejnych numerów identyfikacyjnych, nawet jeśli dla generowania numerów identyfikacyjnych jest ustawiona wartość ręczna.</span><span class="sxs-lookup"><span data-stu-id="6a5c9-302">No further license plate must be scanned, even if license plate generation is set to manual.</span></span>
