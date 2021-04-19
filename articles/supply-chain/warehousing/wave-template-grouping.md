---
title: Grupowanie szablonów grup czynności
description: Grupowanie szablonów grupy czynności umożliwia systemowi korzystanie z ustawień szablonu grupy czynności w celu określenia, na podstawie zdefiniowanych kryteriów, sposobu podziału zwolnionych wierszy i przypisania ich do nowych lub istniejących grup czynności. Ta funkcja może być przydatna w magazynach, w których grupy czynności są tworzone na podstawie określonych kryteriów, w przypadku gdy kierownicy preferują automatyczne, a nie ręczne, tworzenie grup czynności.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: a591624f6611148abe4888e67d8d3a9bbea9cd27
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838041"
---
# <a name="wave-template-grouping"></a><span data-ttu-id="19124-104">Grupowanie szablonów grup czynności</span><span class="sxs-lookup"><span data-stu-id="19124-104">Wave template grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19124-105">Grupowanie szablonów grupy czynności umożliwia systemowi korzystanie z ustawień [szablonu grupy czynności](tasks/configure-wave-processing.md) w celu określenia, na podstawie zdefiniowanych kryteriów, sposobu podziału zwolnionych wierszy i przypisania ich do nowych lub istniejących grup czynności.</span><span class="sxs-lookup"><span data-stu-id="19124-105">Wave template grouping enables the system to use [wave template](tasks/configure-wave-processing.md) setups to determine, based on criteria that you define, how it should split released lines and assign them to new or existing waves.</span></span> <span data-ttu-id="19124-106">Ta funkcja może być przydatna w magazynach, w których grupy czynności są tworzone na podstawie określonych kryteriów, w przypadku gdy kierownicy preferują automatyczne, a nie ręczne, tworzenie grup czynności.</span><span class="sxs-lookup"><span data-stu-id="19124-106">This feature can be useful in warehouses where waves are created based on specific criteria, but where managers prefer to create waves automatically instead of manually.</span></span> <span data-ttu-id="19124-107">Umożliwia systemowi dodanie każdej nowo zwolnionej wysyłki do pierwszej grupy czynności, która ma odpowiednie wartości pól grupowania.</span><span class="sxs-lookup"><span data-stu-id="19124-107">It enables the system to add each newly released shipment to the first wave that it finds that has matching grouping field values.</span></span> <span data-ttu-id="19124-108">Jeśli nie zostanie znaleziony żadne trafienie, system utworzy nową podstawę dla nowej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="19124-108">If no match is found, the system creates a new wave for the new shipment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19124-109">Grupowanie szablonów grupy czynności nie jest obsługiwane w przypadku typów pracy *pobieranie surowca produkcyjnego* lub *pobieranie Kanban*.</span><span class="sxs-lookup"><span data-stu-id="19124-109">Wave template grouping isn't supported for the work types *production raw material picking* or *Kanban picking*.</span></span> <span data-ttu-id="19124-110">Jest to spowodowane tym, że grupowanie grupy czynności jest oparte na wysyłkach, a te typy prac nie używają wysyłek.</span><span class="sxs-lookup"><span data-stu-id="19124-110">This is because wave grouping is based on shipments and these work types don't use shipments.</span></span>

## <a name="turn-on-the-wave-template-grouping-feature"></a><span data-ttu-id="19124-111">Włączanie funkcji grupowania szablonów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="19124-111">Turn on the Wave template grouping feature</span></span>

<span data-ttu-id="19124-112">Aby móc używać funkcji *Grupowania szablonów grupy czynności*, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="19124-112">Before you can use the *Wave template grouping* feature, it must be turned on in your system.</span></span> <span data-ttu-id="19124-113">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="19124-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="19124-114">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="19124-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="19124-115">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="19124-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="19124-116">**Nazwa funkcji:** *Grupowania szablonów grupy czynności*</span><span class="sxs-lookup"><span data-stu-id="19124-116">**Feature name:** *Wave template grouping*</span></span>

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a><span data-ttu-id="19124-117">Ustawienie szablonu grupy czynności do korzystania z szablonu grupowania grupy czynności</span><span class="sxs-lookup"><span data-stu-id="19124-117">Set a wave template to use wave template grouping</span></span>

<span data-ttu-id="19124-118">Aby udostępnić grupowanie szablonów grupy czynności, należy wykonać poniższe kroki w celu skonfigurowania [szablonu grupy czynności](tasks/configure-wave-processing.md).</span><span class="sxs-lookup"><span data-stu-id="19124-118">To make wave template grouping available, follow these steps to set up your [wave template](tasks/configure-wave-processing.md).</span></span>

1. <span data-ttu-id="19124-119">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="19124-119">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="19124-120">W lewym okienku wybierz szablon grupy czynności do ustawienia.</span><span class="sxs-lookup"><span data-stu-id="19124-120">In the left pane, select the wave template to set up.</span></span> <span data-ttu-id="19124-121">Jeśli chcesz później przejść przez scenariusz w tym temacie korzystając z danych demonstracyjnych, wybierz szablon **62 Domyślna wysyłka**.</span><span class="sxs-lookup"><span data-stu-id="19124-121">If you're preparing to work through the scenario later in this topic by using demo data, select the **62 Shipping default** template.</span></span>
1. <span data-ttu-id="19124-122">Wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.</span><span class="sxs-lookup"><span data-stu-id="19124-122">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="19124-123">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-123">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="19124-124">**Automatyczne tworzenie grupy czynności:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="19124-124">**Automate wave creation:** *Yes*</span></span>
    - <span data-ttu-id="19124-125">**Przypisz do otwartych grup czynności:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="19124-125">**Assign to open waves:** *Yes*</span></span>
    - <span data-ttu-id="19124-126">**Przetwarzanie grupy czynności w czasie uwalniania jej do magazynu:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="19124-126">**Process wave at release to warehouse:** *No*</span></span>

1. <span data-ttu-id="19124-127">W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe kwerendy.</span><span class="sxs-lookup"><span data-stu-id="19124-127">On the Action Pane, select **Edit query** to open the query dialog box.</span></span>
1. <span data-ttu-id="19124-128">W oknie dialogowym kwerenda, na karcie **Sortowanie**, przejrzyj kryteria sortowania i upewnij się, że istnieje reguła obejmująca pole, którego chcesz użyć do grupowania grup czynności.</span><span class="sxs-lookup"><span data-stu-id="19124-128">In the query dialog box, on the **Sorting** tab, review the sorting criteria, and make sure that there is a rule that includes the field that you want to use to group your waves.</span></span>

    <span data-ttu-id="19124-129">Jeśli pracujesz przy użyciu danych demonstracyjnych w ramach scenariusza, należy dodać wiersz o następujących wartościach:</span><span class="sxs-lookup"><span data-stu-id="19124-129">If you're preparing to work through the scenario by using demo data, add a row that has the following values:</span></span>

    - <span data-ttu-id="19124-130">**Tabela:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="19124-130">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="19124-131">**Tabela pochodna:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="19124-131">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="19124-132">**Pole:** *Usługa przewozowa*</span><span class="sxs-lookup"><span data-stu-id="19124-132">**Field:** *Carrier service*</span></span>

        > [!NOTE]
        > <span data-ttu-id="19124-133">Po wybraniu tej wartości może zostać wyświetlony następujący komunikat: „Usługa przewoźnika nie jest polem indeksu.</span><span class="sxs-lookup"><span data-stu-id="19124-133">After you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="19124-134">Czy na pewno chcesz dodać sortowanie według tego kryterium?”</span><span class="sxs-lookup"><span data-stu-id="19124-134">Do you want to add sorting on this?"</span></span> <span data-ttu-id="19124-135">Wybierz opcję **Tak**, aby dodać sortowanie.</span><span class="sxs-lookup"><span data-stu-id="19124-135">Select **Yes** to add sorting.</span></span>

    - <span data-ttu-id="19124-136">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="19124-136">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="19124-137">Wybierz przycisk **OK**, aby zapisać zmiany i zamknąć okno dialogowe kwerendy.</span><span class="sxs-lookup"><span data-stu-id="19124-137">Select **OK** to save your changes and close the query dialog box.</span></span>
1. <span data-ttu-id="19124-138">W okienku akcji wybierz opcję **Grupowanie szablonu grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="19124-138">On the Action Pane, select **Wave template grouping**.</span></span>
1. <span data-ttu-id="19124-139">Na stronie **Grupowanie szablonów grupy czynności** zaznacz pole wyboru **Grupuj według** dla każdego wiersza, który ma być używany do grupowania wierszy zamówienia w grupy zamówień w zależności od potrzeb.</span><span class="sxs-lookup"><span data-stu-id="19124-139">On the **Wave template grouping** page, select the **Group by** check box for each row that you want to use to group your order lines into waves, as required.</span></span> <span data-ttu-id="19124-140">Jeśli przygotowujesz się do pracy w ramach scenariusza przy użyciu danych demonstracyjnych, zaznacz pole wyboru **Grupuj według** dla wiersza *Usługi przewoźnika*.</span><span class="sxs-lookup"><span data-stu-id="19124-140">If you're preparing to work through the scenario by using demo data, select the **Group by** check box for the *Carrier service* row.</span></span>
1. <span data-ttu-id="19124-141">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="19124-141">Select **Save**.</span></span>
1. <span data-ttu-id="19124-142">Zamknij stronę **Grupowanie szablonów grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="19124-142">Close the **Wave template grouping** page.</span></span>
1. <span data-ttu-id="19124-143">Wybierz **Zapisz**, żeby zapisać szablon.</span><span class="sxs-lookup"><span data-stu-id="19124-143">Select **Save** to save your template.</span></span>

## <a name="scenario"></a><span data-ttu-id="19124-144">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="19124-144">Scenario</span></span>

<span data-ttu-id="19124-145">Ta sekcja zawiera skrypt, z którego można się dowiedzieć, jak działa ta funkcja i jak jej używać.</span><span class="sxs-lookup"><span data-stu-id="19124-145">This section provides a script that you can work through to learn what this feature does and how to work with it.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="19124-146">Udostępnianie danych pokazowych</span><span class="sxs-lookup"><span data-stu-id="19124-146">Make sample data available</span></span>

<span data-ttu-id="19124-147">Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="19124-147">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="19124-148">Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="19124-148">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="19124-149">Tego scenariusza można również używać jako wskazówek dotyczących danej funkcji podczas pracy w produkcji.</span><span class="sxs-lookup"><span data-stu-id="19124-149">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="19124-150">Jednak w takim przypadku trzeba podstawiać własne wartości i w niektórych przypadkach może brakować pewnych typów wymaganych rekordów, które są dostępne w standardowych danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="19124-150">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="scenario-wave-template-grouping"></a><span data-ttu-id="19124-151">Scenariusz: Grupowanie szablonów grup czynności</span><span class="sxs-lookup"><span data-stu-id="19124-151">Scenario: Wave template grouping</span></span>

<span data-ttu-id="19124-152">W tym scenariuszu przedstawiono sposób użycia grupowania szablonów grupy czynności w celu automatycznego tworzenia wielu grup czynności na podstawie kryteriów grupowania zdefiniowanych w szablonie grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="19124-152">This scenario shows how to use wave template grouping to automatically create multiple waves, based on grouping criteria that are defined in a wave template.</span></span> <span data-ttu-id="19124-153">W tym scenariuszu szablon grupy czynności jest konfigurowany w systemie w celu utworzenia jednej grupy czynności dla każdej usługi przewozowej.</span><span class="sxs-lookup"><span data-stu-id="19124-153">In this scenario, the wave template is set up in the system to create one wave per carrier service.</span></span>

<span data-ttu-id="19124-154">Przed rozpoczęciem Przygotuj szablon grupy czynności, tak jak opisano to sekcji [Konfigurowanie szablonu grupy czynności, aby korzystać z funkcji grupowania szablonów grup czynności](#set-up-template) wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="19124-154">Before you begin, prepare your wave template as described in the [Set a wave template to use wave template grouping](#set-up-template) section earlier in this topic.</span></span> <span data-ttu-id="19124-155">Jeśli użytkownik będzie pracować z danymi demonstracyjnymi w tym scenariuszu, należy pamiętać o użyciu wartości danych demonstracyjnych, które są sugerowane w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="19124-155">If you will be working with demo data for this scenario, be sure to use the demo data values that are suggested in that procedure.</span></span> <span data-ttu-id="19124-156">Ta konfiguracja umożliwia grupowanie grup czynności zgodnie z usługą przewoźnika ustawioną dla każdego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-156">This setup will group your waves according to the carrier service that is set for each sales order.</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="19124-157">Utwórz zamówienie sprzedaży 1</span><span class="sxs-lookup"><span data-stu-id="19124-157">Create sales order 1</span></span>

1. <span data-ttu-id="19124-158">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="19124-158">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="19124-159">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-159">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="19124-160">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-160">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="19124-161">Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-004*.</span><span class="sxs-lookup"><span data-stu-id="19124-161">On the **Customer** FastTab, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="19124-162">Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość *62*.</span><span class="sxs-lookup"><span data-stu-id="19124-162">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="19124-163">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i zamknąć okno dialogowe **Utwórz zamówienie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="19124-163">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="19124-164">Nowe zamówienie sprzedaży jest otwierane w widoku **Wiersza**.</span><span class="sxs-lookup"><span data-stu-id="19124-164">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="19124-165">Zanotuj numer zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-165">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="19124-166">Przełącz do widoku **nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="19124-166">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="19124-167">Na skróconej karcie **Dostawa** w sekcji **Transport** należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-167">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="19124-168">**Przewoźnik:** *Transport lotniczy*</span><span class="sxs-lookup"><span data-stu-id="19124-168">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="19124-169">**Usługa przewozowa:** *Lotnicza*</span><span class="sxs-lookup"><span data-stu-id="19124-169">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="19124-170">Przełącz się z powrotem do widoku **Wiersz**.</span><span class="sxs-lookup"><span data-stu-id="19124-170">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="19124-171">W sekcji **Wiersze zamówienia sprzedaży** kliknij przycisk **Dodaj wiersze**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="19124-171">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="19124-172">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-172">On the new line, set the following values:</span></span>

    - <span data-ttu-id="19124-173">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="19124-173">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="19124-174">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="19124-174">**Quantity:** *2*</span></span>

1. <span data-ttu-id="19124-175">Zaznacz nowy wiersz zamówienia, a następnie w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="19124-175">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="19124-176">Na stronie **Rezerwacja**, w okienku akcji wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="19124-176">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="19124-177">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-177">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="19124-178">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="19124-178">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="19124-179">Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="19124-179">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="19124-180">Należy zanotować numer identyfikacyjny grupy czynności oraz wysyłki.</span><span class="sxs-lookup"><span data-stu-id="19124-180">Make a note of the wave ID number and the shipment ID numbers.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a><span data-ttu-id="19124-181">Wyświetl grupę czynności, która została utworzona na podstawie zamówienia sprzedaży 1</span><span class="sxs-lookup"><span data-stu-id="19124-181">View the wave that was created from sales order 1</span></span>

1. <span data-ttu-id="19124-182">Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="19124-182">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="19124-183">Wybierz identyfikator grupy czynności, która została utworzona na podstawie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-183">Select the wave ID that was created from the sales order.</span></span>
1. <span data-ttu-id="19124-184">Wybierz łącze identyfikatora grupy czynności, aby otworzyć stronę szczegółów.</span><span class="sxs-lookup"><span data-stu-id="19124-184">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="19124-185">Należy zauważyć, że wysyłka została dodana do skróconej karty **Wierszy grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="19124-185">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="19124-186">Utwórz zamówienie sprzedaży 2</span><span class="sxs-lookup"><span data-stu-id="19124-186">Create sales order 2</span></span>

1. <span data-ttu-id="19124-187">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="19124-187">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="19124-188">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-188">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="19124-189">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="19124-190">Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-005*.</span><span class="sxs-lookup"><span data-stu-id="19124-190">On the **Customer** FastTab, set the **Customer account** field to *US-005*.</span></span>
    - <span data-ttu-id="19124-191">Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość *62*.</span><span class="sxs-lookup"><span data-stu-id="19124-191">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="19124-192">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i zamknąć okno dialogowe **Utwórz zamówienie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="19124-192">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="19124-193">Nowe zamówienie sprzedaży jest otwierane w widoku **Wiersza**.</span><span class="sxs-lookup"><span data-stu-id="19124-193">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="19124-194">Zanotuj numer zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-194">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="19124-195">Przełącz do widoku **nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="19124-195">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="19124-196">Na skróconej karcie **Dostawa** w sekcji **Transport** należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-196">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="19124-197">**Przewoźnik:** *Przenoszenie kwiatów*</span><span class="sxs-lookup"><span data-stu-id="19124-197">**Shipping carrier:** *Flower moving*</span></span>
    - <span data-ttu-id="19124-198">**Usługa przewozowa:** *Standard*</span><span class="sxs-lookup"><span data-stu-id="19124-198">**Carrier service:** *Std*</span></span>

1. <span data-ttu-id="19124-199">Przełącz się z powrotem do widoku **Wiersz**.</span><span class="sxs-lookup"><span data-stu-id="19124-199">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="19124-200">W sekcji **Wiersze zamówienia sprzedaży** kliknij przycisk **Dodaj wiersze**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="19124-200">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="19124-201">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-201">On the new line, set the following values:</span></span>

    - <span data-ttu-id="19124-202">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="19124-202">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="19124-203">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="19124-203">**Quantity:** *1*</span></span>

1. <span data-ttu-id="19124-204">Zaznacz nowy wiersz zamówienia, a następnie w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="19124-204">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="19124-205">Na stronie **Rezerwacja**, w okienku akcji wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="19124-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="19124-206">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-206">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="19124-207">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="19124-207">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="19124-208">Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="19124-208">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="19124-209">Należy zanotować numer identyfikacyjny grupy czynności oraz wysyłki.</span><span class="sxs-lookup"><span data-stu-id="19124-209">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="19124-210">Zauważ, że identyfikator grupy czynności jest różny od identyfikatora grupy czynności dla pierwszego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-210">Notice that the wave ID differs from the wave ID of the first sales order.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a><span data-ttu-id="19124-211">Wyświetl grupę czynności, która została utworzona na podstawie zamówienia sprzedaży 2</span><span class="sxs-lookup"><span data-stu-id="19124-211">View the wave that was created from sales order 2</span></span>

1. <span data-ttu-id="19124-212">Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="19124-212">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="19124-213">Wybierz identyfikator grupy czynności, która została utworzona na podstawie drugiego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-213">Select the wave ID that was created from the second sales order.</span></span>
1. <span data-ttu-id="19124-214">Wybierz łącze identyfikatora grupy czynności, aby otworzyć stronę szczegółów.</span><span class="sxs-lookup"><span data-stu-id="19124-214">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="19124-215">Należy zauważyć, że wysyłka została dodana do skróconej karty **Wierszy grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="19124-215">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

<span data-ttu-id="19124-216">Dla tej wysyłki utworzono nową grupę czynności, ponieważ używa ona innej usługi przewozowej niż pierwsze zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-216">A new wave was created for this shipment, because it uses a different carrier service than the first sales order.</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="19124-217">Utwórz zamówienie sprzedaży 3</span><span class="sxs-lookup"><span data-stu-id="19124-217">Create sales order 3</span></span>

1. <span data-ttu-id="19124-218">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="19124-218">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="19124-219">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-219">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="19124-220">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-220">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="19124-221">Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-006*.</span><span class="sxs-lookup"><span data-stu-id="19124-221">On the **Customer** FastTab, set the **Customer account** field to *US-006*.</span></span>
    - <span data-ttu-id="19124-222">Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość *62*.</span><span class="sxs-lookup"><span data-stu-id="19124-222">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="19124-223">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i zamknąć okno dialogowe **Utwórz zamówienie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="19124-223">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="19124-224">Nowe zamówienie sprzedaży jest otwierane w widoku **Wiersza**.</span><span class="sxs-lookup"><span data-stu-id="19124-224">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="19124-225">Zanotuj numer zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-225">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="19124-226">Przełącz do widoku **nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="19124-226">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="19124-227">Na skróconej karcie **Dostawa** w sekcji **Transport** należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-227">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="19124-228">**Przewoźnik:** *Transport lotniczy*</span><span class="sxs-lookup"><span data-stu-id="19124-228">**Shipping carrier:** *Air Cargo*</span></span>
    - <span data-ttu-id="19124-229">**Usługa przewozowa:** *Lotnicza*</span><span class="sxs-lookup"><span data-stu-id="19124-229">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="19124-230">Przełącz się z powrotem do widoku **Wiersz**.</span><span class="sxs-lookup"><span data-stu-id="19124-230">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="19124-231">W sekcji **Wiersze zamówienia sprzedaży** kliknij przycisk **Dodaj wiersze**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="19124-231">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="19124-232">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="19124-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="19124-233">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="19124-233">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="19124-234">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="19124-234">**Quantity:** *1*</span></span>

1. <span data-ttu-id="19124-235">Zaznacz nowy wiersz zamówienia, a następnie w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="19124-235">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="19124-236">Na stronie **Rezerwacja**, w okienku akcji wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.</span><span class="sxs-lookup"><span data-stu-id="19124-236">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="19124-237">Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-237">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="19124-238">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="19124-238">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="19124-239">Wyświetlany jest komunikat informacyjny, który pokazuje wysyłkę i wyciągi z tego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="19124-239">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="19124-240">Należy zanotować numer identyfikacyjny grupy czynności oraz wysyłki.</span><span class="sxs-lookup"><span data-stu-id="19124-240">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="19124-241">Wysyłka została przypisana do istniejącej grupy czynności w pierwszym zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-241">The shipment has been assigned to the existing wave from the first sales order.</span></span>

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a><span data-ttu-id="19124-242">Wyświetl grupy czynności dla zamówień sprzedaży 1 i 3</span><span class="sxs-lookup"><span data-stu-id="19124-242">View the wave for sales orders 1 and 3</span></span>

1. <span data-ttu-id="19124-243">Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="19124-243">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="19124-244">Wybierz identyfikator grupy czynności, która została utworzona na podstawie trzeciego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-244">Select the wave ID that was created from the third sales order.</span></span>
1. <span data-ttu-id="19124-245">Wybierz łącze identyfikatora grupy czynności, aby otworzyć stronę szczegółów.</span><span class="sxs-lookup"><span data-stu-id="19124-245">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="19124-246">Należy zauważyć, że wysyłka została dodana do skróconej karty **Wierszy grupy czynności** wraz z wysyłką dla pierwszego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19124-246">Notice that the shipment has been added to the **Wave lines** FastTab, together with the shipment for the first sales order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]