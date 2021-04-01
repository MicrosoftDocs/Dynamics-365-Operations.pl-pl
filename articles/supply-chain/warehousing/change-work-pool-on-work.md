---
title: Zmień pulę pracy w pracy
description: W tym temacie wyjaśniono, jak można używać przycisku Zmień pulę prac dla elementów pracy, aby zmienić pulę pracy istniejącej pracy.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 61b988cf2501812e940f726e02d8fc1bcee2c035
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233062"
---
# <a name="change-work-pool-on-work"></a><span data-ttu-id="e0fb7-103">Zmień pulę pracy w pracy</span><span class="sxs-lookup"><span data-stu-id="e0fb7-103">Change work pool on work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0fb7-104">Można używać puli prac do organizacji pracy w grupy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-104">You can use work pools to organize work into groups.</span></span> <span data-ttu-id="e0fb7-105">Można na przykład utworzyć pulę pracy do sklasyfikowania pracy, która występuje w określonej lokalizacji magazynu.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-105">For example, you can create a work pool to classify work that occurs in a specific warehouse location.</span></span>

<span data-ttu-id="e0fb7-106">Funkcja *Zmień pulę pracy w pracy* powoduje dodanie przycisku **Zmień pulę prac** do okienka akcji dla elementów pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-106">The *Change work pool on work* feature adds a **Change work pool** button to the Action Pane for work items.</span></span> <span data-ttu-id="e0fb7-107">Dlatego Menedżer magazynu może łatwo zmienić pulę pracy istniejącej pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-107">Therefore, warehouse managers can easily change the work pool of existing work.</span></span> <span data-ttu-id="e0fb7-108">Ta funkcja pozwala menedżerom szybko reagować na zmiany w hali produkcyjnej magazynu i pomaga poprawić ich zdolność przystosowania się do zmieniających się sytuacji i konieczności przeniesienia pracy do innej puli pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-108">This feature lets managers react quickly to changes on the warehouse shop floor, and it helps improve their ability to adapt to changing situations and the need to transfer work to another work pool.</span></span>

## <a name="turn-on-the-change-work-pool-on-work-feature"></a><span data-ttu-id="e0fb7-109">Włącz funkcję Zmień pulę pracy dla pracy</span><span class="sxs-lookup"><span data-stu-id="e0fb7-109">Turn on the Change work pool on work feature</span></span>

<span data-ttu-id="e0fb7-110">Przed rozpoczęciem konfigurowania lub używania tej funkcji należy upewnić się, że jest ona dostępna w systemie.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-110">Before you begin to set up or use this feature, you must make sure that it's available in your system.</span></span> <span data-ttu-id="e0fb7-111">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="e0fb7-112">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="e0fb7-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="e0fb7-113">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="e0fb7-114">**Nazwa funkcji:** *Zmień pulę pracy w pracy*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-114">**Feature name:** *Change work pool on work*</span></span>

## <a name="set-up-the-change-work-pool-on-work-feature"></a><span data-ttu-id="e0fb7-115">Ustaw funkcję Zmień pulę pracy dla pracy</span><span class="sxs-lookup"><span data-stu-id="e0fb7-115">Set up the Change work pool on work feature</span></span>

<span data-ttu-id="e0fb7-116">Aby można było korzystać z tej funkcji, muszą być skonfigurowane pule pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-116">To use this feature, you must have some work pools set up.</span></span> <span data-ttu-id="e0fb7-117">Można również skonfigurować szablony pracy, aby automatycznie przypisywać pulę.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-117">You might also set up your work templates so that they automatically assign a pool.</span></span> <span data-ttu-id="e0fb7-118">Jeśli użytkownik chce pracować w przykładowym scenariuszu przedstawionym w dalszej części tego tematu, należy skonfigurować system zgodnie z opisem w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-118">If you want to work through the example scenario that is provided later in this topic, set up your system as described in this section.</span></span>

### <a name="set-up-work-pools"></a><span data-ttu-id="e0fb7-119">Ustawianie pul pracy</span><span class="sxs-lookup"><span data-stu-id="e0fb7-119">Set up work pools</span></span>

<span data-ttu-id="e0fb7-120">Pule pracy umożliwiają organizowanie elementów pracy według typów.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-120">Work pools let you organize work items by type.</span></span> <span data-ttu-id="e0fb7-121">Aby pracować z funkcją *Zmień pulę pracy dla pracy*, trzeba mieć co najmniej dwie dostępne pule pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-121">To work with the *Change work pool on work* feature, you must have at least two work pools available.</span></span> <span data-ttu-id="e0fb7-122">Aby wyświetlić i dodać pule pracy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-122">To view and add work pools, follow these steps.</span></span>

1. <span data-ttu-id="e0fb7-123">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Pule pracy**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-123">Go to **Warehouse management \> Setup \> Work \> Work pools**.</span></span>
1. <span data-ttu-id="e0fb7-124">Jeśli użytkownik pracuje z danymi demonstracyjnymi z firmy **USMF** i w dalszej części tego tematu może współpracować z przykładowym scenariuszem, należy dodać dwie pule pracy o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="e0fb7-124">If you're working with demo data from the **USMF** company and will work through the example scenario later in this topic, add two work pools that have the following settings:</span></span>

    - <span data-ttu-id="e0fb7-125">Pula pracy 1:</span><span class="sxs-lookup"><span data-stu-id="e0fb7-125">Work pool 1:</span></span>

        - <span data-ttu-id="e0fb7-126">**Identyfikator puli pracy:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-126">**Work pool ID:** *Webshop*</span></span>
        - <span data-ttu-id="e0fb7-127">**Opis:** *Sklep internetowy*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-127">**Description:** *Web Shop*</span></span>

    - <span data-ttu-id="e0fb7-128">Pula pracy 2:</span><span class="sxs-lookup"><span data-stu-id="e0fb7-128">Work pool 2:</span></span>

        - <span data-ttu-id="e0fb7-129">**Identyfikator puli pracy:** *CallCenter*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-129">**Work pool ID:** *CallCenter*</span></span>
        - <span data-ttu-id="e0fb7-130">**Opis:** *Call Center*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-130">**Description:** *Call Center*</span></span>

1. <span data-ttu-id="e0fb7-131">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-131">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="e0fb7-132">Ustaw szablony pracy</span><span class="sxs-lookup"><span data-stu-id="e0fb7-132">Set up work templates</span></span>

<span data-ttu-id="e0fb7-133">Dla każdego z szablonów pracy można określić domyślną pulę pracy, stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-133">For each of your work templates, you can set a default work pool, as you require.</span></span> <span data-ttu-id="e0fb7-134">Dla każdego odpowiedniego szablonu należy przypisać pulę pracy w kolumnie **Identyfikator puli pracy**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-134">For each relevant template, you assign a work pool in the **Work pool ID** column.</span></span> <span data-ttu-id="e0fb7-135">W takim przypadku wszystkie elementy pracy wygenerowane za pomocą danego szablonu automatycznie odziedziczą przypisaną pulę pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-135">In this case, all work items that are generated by using a given template automatically inherit the assigned work pool.</span></span> <span data-ttu-id="e0fb7-136">Jeśli użytkownik pracuje z danymi demonstracyjnymi z firmy **USMF** i w dalszej części tego tematu może współpracować z przykładowym scenariuszem, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-136">If you're working with the demo data from the **USMF** company and will work through the example scenario later in this topic, follow these steps.</span></span>

1. <span data-ttu-id="e0fb7-137">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-137">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="e0fb7-138">W okienku akcji wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-138">On the Action Pane, select **Edit** to put the page into editing mode.</span></span>
1. <span data-ttu-id="e0fb7-139">Edytuj szablon, ustawiając następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="e0fb7-139">Edit the template by setting the following values:</span></span>

    - <span data-ttu-id="e0fb7-140">**Szablon pracy:** *62 Pobranie do pakowania*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-140">**Work template:** *62 Pick to pack*</span></span>
    - <span data-ttu-id="e0fb7-141">**Identyfikator puli pracy:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-141">**Work pool ID:** *Webshop*</span></span>

1. <span data-ttu-id="e0fb7-142">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-142">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="e0fb7-143">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="e0fb7-143">Example scenario</span></span>

<span data-ttu-id="e0fb7-144">W tym scenariuszu przedstawiono sposób zmiany strumienia przetwarzania dla istniejącego elementu pracy przez zmianę jego puli pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-144">This scenario shows how to change the stream of processing for an existing work item by changing its work pool.</span></span> <span data-ttu-id="e0fb7-145">Używa on danych demonstracyjnych z firmy **USMF** oraz ustawień, które zostały zasugerowane wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-145">It uses demo data from the **USMF** company and the settings that were suggested earlier in this topic.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="e0fb7-146">Utwórz zamówienie sprzedaży i zwolnij je do magazynu</span><span class="sxs-lookup"><span data-stu-id="e0fb7-146">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="e0fb7-147">Upewnij się, że jest wystarczająca ilość dostępnych zapasów dla pozycji *A0001* i *A0002* w magazynie *62*.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-147">Confirm that there is enough on-hand inventory for items *A0001* and *A0002* in warehouse *62*.</span></span> <span data-ttu-id="e0fb7-148">Przejdź do **Zarządzanie zapasami \> Zapytania i raporty \> Lista dostępnych**, a następnie zmień filtry, tak jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="e0fb7-148">Go to **Inventory management \> Inquiries and reports \> On-hand list**, and edit the filters as shown here:</span></span>

    - <span data-ttu-id="e0fb7-149">Wartość **Magazynu** zaczyna się od *62*.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-149">The **Warehouse** value begins with *62*.</span></span>
    - <span data-ttu-id="e0fb7-150">Wartość **Identyfikator pozycji** to albo *A001* albo *A002*.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-150">The **Item number** value is either *A001* or *A002*.</span></span>

    <span data-ttu-id="e0fb7-151">Dane demonstracyjne powinny zawierać ilość 10 sztuk na każdy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-151">Demo data should have a quantity of 10 each.</span></span>

    <span data-ttu-id="e0fb7-152">Następnie należy utworzyć zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-152">Next, you must create a sales order.</span></span>

1. <span data-ttu-id="e0fb7-153">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-153">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="e0fb7-154">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-154">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e0fb7-155">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="e0fb7-155">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="e0fb7-156">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-156">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="e0fb7-157">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-157">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="e0fb7-158">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-158">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="e0fb7-159">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-159">The new sales order is opened.</span></span> <span data-ttu-id="e0fb7-160">Powinno zawierać pusty wiersz w siatce na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-160">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="e0fb7-161">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="e0fb7-161">On this line, set the following values:</span></span>

    - <span data-ttu-id="e0fb7-162">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-162">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="e0fb7-163">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-163">**Quantity:** *2*</span></span>

1. <span data-ttu-id="e0fb7-164">W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-164">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="e0fb7-165">Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-165">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="e0fb7-166">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-166">Close the page.</span></span>
1. <span data-ttu-id="e0fb7-167">Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kolejny wiersz do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-167">On the **Sales order lines** FastTab, select **Add line** to add another line to your sales order.</span></span> <span data-ttu-id="e0fb7-168">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="e0fb7-168">On this line, set the following values:</span></span>

    - <span data-ttu-id="e0fb7-169">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-169">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="e0fb7-170">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="e0fb7-170">**Quantity:** *2*</span></span>

1. <span data-ttu-id="e0fb7-171">W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-171">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="e0fb7-172">Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-172">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="e0fb7-173">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-173">Close the page.</span></span>
1. <span data-ttu-id="e0fb7-174">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-174">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="e0fb7-175">Użytkownik otrzymuje komunikaty informacyjne, które zawierają identyfikator grupy czynności oraz identyfikator wysyłki utworzony ze zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-175">You receive informational messages that show the wave ID and shipment ID that were created from the release.</span></span> <span data-ttu-id="e0fb7-176">Zanotuj identyfikator grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-176">Make a note of the wave ID.</span></span>

### <a name="review-the-outbound-wave"></a><span data-ttu-id="e0fb7-177">Przegląd wychodzącą grupę czynności</span><span class="sxs-lookup"><span data-stu-id="e0fb7-177">Review the outbound wave</span></span>

1. <span data-ttu-id="e0fb7-178">Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-178">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="e0fb7-179">W siatce wyszukaj identyfikator grupy czynności, który został utworzony na podstawie zwolnienia zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-179">In the grid, search for the wave ID that was created from the release of the sales order.</span></span>
1. <span data-ttu-id="e0fb7-180">Wybierz identyfikator grupy czynności, aby wyświetlić szczegóły.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-180">Select the wave ID to view the details.</span></span>
1. <span data-ttu-id="e0fb7-181">Na skróconej karcie **Wiersze grupy czynności** należy upewnić się, że dla zamówienia sprzedaży jest wyświetlany identyfikator wysyłki.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-181">On the **Wave lines** FastTab, make sure that a shipment ID is shown for the sales order.</span></span>

    > [!TIP]
    > <span data-ttu-id="e0fb7-182">Jeśli opcja **Przetwarzanie grupy czynności w czasie uwalniania jej do magazynu** jest ustawiona na *Nie*, należy ręcznie przetworzyć tę operację, wybierając opcję **Przetwarzaj** z karty **Grupa czynności** w okienku akcji, aby utworzyć pracę.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-182">If the **Process wave at release to warehouse** option is set to *No* in the setup for the shipping wave template, you must manually process the wave by selecting **Process** from the **Wave** tab on the Action Pane to create work.</span></span>

1. <span data-ttu-id="e0fb7-183">Upewnij się, że dana grupa czynności została przetworzona.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-183">Make sure that the wave has been processed.</span></span> <span data-ttu-id="e0fb7-184">To przetwarzanie powoduje utworzenie wymaganej pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-184">This processing creates the required work.</span></span>

### <a name="view-work-details-and-change-the-work-pool"></a><span data-ttu-id="e0fb7-185">Wyświetl szczegóły pracy i zmień pulę pracy</span><span class="sxs-lookup"><span data-stu-id="e0fb7-185">View work details and change the work pool</span></span>

<span data-ttu-id="e0fb7-186">Strona **Szczegóły pracy** służy do wyświetlania pracy, która została utworzona, oraz do zarządzania pulą pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-186">You can use the **Work details** page to view the work that was created and to manage the work pool.</span></span>

1. <span data-ttu-id="e0fb7-187">Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-187">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="e0fb7-188">Umożliwia wybór wiersza dla pracy, która została właśnie utworzona.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-188">Select the row for the work that was just created.</span></span> <span data-ttu-id="e0fb7-189">W kolumnie **Numer zamówienia** zostanie wyświetlony numer zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-189">The **Order number** column will show the sales order number.</span></span>

    <span data-ttu-id="e0fb7-190">W polu **Identyfikator puli pracy** zostanie ustawiony Identyfikator puli pracy, który został ustawiony w szablonie pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-190">The **Work pool ID** field will be set to the work pool ID that was set up in the work template.</span></span>

    > [!TIP]
    > <span data-ttu-id="e0fb7-191">Jeśli pole **Identyfikator puli pracy** nie jest widoczny, dodaj kolumnę do siatki, a następnie odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-191">If you don't see the **Work pool ID** field, add the column to the grid, and then refresh the page.</span></span>

1. <span data-ttu-id="e0fb7-192">Aby zmienić pulę pracy skojarzoną z identyfikatorem pracy, w okienku akcji na karcie **Praca** wybierz opcję **Zmień identyfikator puli pracy**.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-192">To change the work pool that is associated with the work ID, on the Action Pane, on the **Work** tab, select **Change Work pool ID**.</span></span>
1. <span data-ttu-id="e0fb7-193">W oknie dialogowym **Zmień pulę pracy**, na skróconej karcie **Parametry** w polu **Identyfikator puli pracy** wybierz pozycję *CallCenter*.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-193">In the **Change work pool** dialog box, on the **Parameters** FastTab, in the **Work pool ID** field, select *CallCenter*.</span></span>
1. <span data-ttu-id="e0fb7-194">Wybierz **OK**, aby zastosować zmianę.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-194">Select **OK** to apply your change.</span></span>
1. <span data-ttu-id="e0fb7-195">Zauważ, że wartość pola **Identyfikator puli pracy** została zmieniona na *CallCenter*.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-195">Notice that the value of the **Work pool ID** field has now been changed to *CallCenter*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0fb7-196">Po wyświetleniu okna dialogowego **Zmień pulę pracy** pole **Identyfikator puli pracy** może domyślnie być puste</span><span class="sxs-lookup"><span data-stu-id="e0fb7-196">When the **Change work pool** dialog box appears, the **Work pool ID** field might be blank by default.</span></span> <span data-ttu-id="e0fb7-197">Jeśli pole jest puste po wybraniu opcji **OK** w celu zastosowania zmian, Ppula pracy zostanie całkowicie usunięta z pracy.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-197">If the field is blank when you select **OK** to apply changes, you will remove the work pool completely from the work.</span></span>
>
> <span data-ttu-id="e0fb7-198">Oprócz przełączenia pul pracy można skorzystać z tej procedury, aby dodać pulę pracy do dowolnego elementu pracy, który jej nie ma, lub usunąć pulę pracy z dowolnego elementu pracy, który ją posiada.</span><span class="sxs-lookup"><span data-stu-id="e0fb7-198">In addition to switching work pools, you can use this procedure to add a work pool to any work item that doesn't have one, or to remove a work pool from any work item that does have one.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]