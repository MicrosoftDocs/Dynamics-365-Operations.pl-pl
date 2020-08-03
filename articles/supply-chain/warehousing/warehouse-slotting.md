---
title: Rozpisywanie na przedziały w magazynie
description: Ten temat zawiera informacje o rozpisywaniu na przedziały w magazynie. Rozpisywanie na przedziały umożliwia konsolidowanie popytu według towarów i jednostki miary z zamówień o stanie Zamówione, Zarezerwowane lub Zwolnione. Ułatwia to kierownikom magazynów zaplanowanie lokalizacji pobrania przed zwolnieniem zamówień do magazynu i utworzenie pracy pobrania.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: f6764f8bc082962af37d4775b6fe53d8704658eb
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597465"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="231e4-105">Rozpisywanie na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="231e4-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="231e4-106">Rozpisywanie na przedziały umożliwia konsolidowanie popytu według towarów i jednostki miary z zamówień o stanie *Zamówione*, *Zarezerwowane* lub *Zwolnione*.</span><span class="sxs-lookup"><span data-stu-id="231e4-106">Warehouse slotting lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="231e4-107">Wygenerowane zapotrzebowanie może być następnie stosowane do lokalizacji, które będą używane do pobierania, na podstawie ilości, jednostki, wymiarów fizycznych, stałych lokalizacji itd.</span><span class="sxs-lookup"><span data-stu-id="231e4-107">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="231e4-108">Po ustaleniu planu rozpisania na przedziały można utworzyć pracę uzupełniającą w celu przeniesienia odpowiedniej ilości zapasów do poszczególnych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="231e4-108">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="231e4-109">Ta funkcjonalność ułatwia kierownikom magazynów zaplanowanie lokalizacji pobrania przed zwolnieniem zamówień do magazynu i utworzenie pracy pobrania.</span><span class="sxs-lookup"><span data-stu-id="231e4-109">This functionality helps warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

## <a name="turn-on-the-warehouse-slotting-feature"></a><span data-ttu-id="231e4-110">Włącz funkcję rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="231e4-110">Turn on the warehouse slotting feature</span></span>

<span data-ttu-id="231e4-111">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="231e4-111">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="231e4-112">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="231e4-112">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="231e4-113">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="231e4-113">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="231e4-114">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="231e4-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="231e4-115">**Nazwa funkcji:** *Rozpisywanie na przedziały w magazynie*</span><span class="sxs-lookup"><span data-stu-id="231e4-115">**Feature name:** *Warehouse slotting feature*</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="231e4-116">Konfigurowanie rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="231e4-116">Set up warehouse slotting</span></span>

<span data-ttu-id="231e4-117">Aby można było skorzystać z tej funkcji, należy skonfigurować następujące elementy w systemie.</span><span class="sxs-lookup"><span data-stu-id="231e4-117">To use warehouse slotting, you must set up the following elements in your system.</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="231e4-118">Utwórz warstwy jednostki miary dla rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="231e4-118">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="231e4-119">Warstwy jednostek miary umożliwiają zgrupowanie wielu jednostek miary w celach rozpisywania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="231e4-119">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="231e4-120">Na przykład, jeśli wiele pudełek jest pobieranych z tego samego obszaru pobrania, można utworzyć jedną warstwę dla wszystkich rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="231e4-120">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="231e4-121">**Należy utworzyć wiersz dla każdej jednostki miary, która powinna być częścią warstwy.**</span><span class="sxs-lookup"><span data-stu-id="231e4-121">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="231e4-122">Przejdź do **Ustawień zarządzania \> Konfiguracji \> Uzupełniania \> Warstwa jednostki miary – rozpisywanie na przedziały w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="231e4-122">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="231e4-123">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="231e4-123">Select **New**.</span></span>
1. <span data-ttu-id="231e4-124">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-124">In the header, set the following values:</span></span>

    - <span data-ttu-id="231e4-125">**Warstwa jednostki miary:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="231e4-125">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="231e4-126">**Opis:** *Każde pudełko paleta*</span><span class="sxs-lookup"><span data-stu-id="231e4-126">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="231e4-127">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="231e4-127">Select **Save**.</span></span>
1. <span data-ttu-id="231e4-128">Na skróconej karcie **Jednostki miary** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="231e4-128">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="231e4-129">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-129">On the new line, set the following values:</span></span>

    - <span data-ttu-id="231e4-130">**Jednostka:** *Pudełko*</span><span class="sxs-lookup"><span data-stu-id="231e4-130">**Unit:** *Box*</span></span>
    - <span data-ttu-id="231e4-131">**Opis:** – zostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="231e4-131">**Description:** Leave this field blank.</span></span> <span data-ttu-id="231e4-132">Zostanie ono wypełnione automatycznie po zapisaniu zmian.</span><span class="sxs-lookup"><span data-stu-id="231e4-132">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="231e4-133">**Klasa jednostek:** *Ilość*</span><span class="sxs-lookup"><span data-stu-id="231e4-133">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="231e4-134">Kliknij przycisk **Nowe**, aby dodać drugi wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="231e4-134">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="231e4-135">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="231e4-136">**Jednostka:** *EA*</span><span class="sxs-lookup"><span data-stu-id="231e4-136">**Unit:** *ea*</span></span>
    - <span data-ttu-id="231e4-137">**Opis:** – zostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="231e4-137">**Description:** Leave this field blank.</span></span> <span data-ttu-id="231e4-138">Zostanie ono wypełnione automatycznie po zapisaniu zmian.</span><span class="sxs-lookup"><span data-stu-id="231e4-138">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="231e4-139">**Klasa jednostek:** *Ilość*</span><span class="sxs-lookup"><span data-stu-id="231e4-139">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="231e4-140">Kliknij przycisk **Nowe**, aby dodać trzeci wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="231e4-140">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="231e4-141">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="231e4-142">**Jednostka:** *PL*</span><span class="sxs-lookup"><span data-stu-id="231e4-142">**Unit:** *PL*</span></span>
    - <span data-ttu-id="231e4-143">**Opis:** – zostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="231e4-143">**Description:** Leave this field blank.</span></span> <span data-ttu-id="231e4-144">Zostanie ono wypełnione automatycznie po zapisaniu zmian.</span><span class="sxs-lookup"><span data-stu-id="231e4-144">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="231e4-145">**Klasa jednostek:** *Ilość*</span><span class="sxs-lookup"><span data-stu-id="231e4-145">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="231e4-146">Wybierz **Zapisz**, aby zapisać warstwę.</span><span class="sxs-lookup"><span data-stu-id="231e4-146">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="231e4-147">Utwórz kod dyrektywy dla rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="231e4-147">Create a directive code for slotting</span></span>

<span data-ttu-id="231e4-148">Należy wybrać kod dyrektywy, który powinien być skojarzony z szablonem.</span><span class="sxs-lookup"><span data-stu-id="231e4-148">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="231e4-149">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kody dyrektyw**.</span><span class="sxs-lookup"><span data-stu-id="231e4-149">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="231e4-150">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="231e4-150">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="231e4-151">W polu **Kod dyrektywy** wprowadź *Rozpisywanie na przedziały w magazynie*.</span><span class="sxs-lookup"><span data-stu-id="231e4-151">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="231e4-152">W polu **Opis dyrektywy** wprowadź *Rozpisywanie na przedziały w magazynie*.</span><span class="sxs-lookup"><span data-stu-id="231e4-152">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="231e4-153">Skonfiguruj szablony rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="231e4-153">Set up slotting templates</span></span>

<span data-ttu-id="231e4-154">Każdy szablon rozpisywania na przedziały w magazynie służy do sterowania sposobem przypisywania zapasów do lokalizacji dla określonego magazynu.</span><span class="sxs-lookup"><span data-stu-id="231e4-154">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="231e4-155">Każdy szablon musi zawierać wiersz dla każdej specyfikacji rozpisywania na przedziały w magazynie.</span><span class="sxs-lookup"><span data-stu-id="231e4-155">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="231e4-156">Procedury przedstawione w tej sekcji służą do konfigurowania szablonów rozpisywania na przedziały w magazynie.</span><span class="sxs-lookup"><span data-stu-id="231e4-156">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="231e4-157">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony rozpisywania na przedziały w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="231e4-157">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="231e4-158">Wybierz pozycję **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="231e4-158">Select **New** to create a template.</span></span>

<span data-ttu-id="231e4-159">Następnie należy ustawić nagłówek szablonu, specyfikacje rozpisywania na przedziały w magazynie oraz dyrektywy lokalizacji, jak wyjaśniono w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="231e4-159">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span>

#### <a name="set-up-a-slotting-template-header"></a><span data-ttu-id="231e4-160">Konfigurowanie nagłówka szablonu rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="231e4-160">Set up a slotting template header</span></span>

1. <span data-ttu-id="231e4-161">W nagłówku szablonu określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-161">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="231e4-162">**Szablon rozpisywania na przedziały w magazynie:** _61_</span><span class="sxs-lookup"><span data-stu-id="231e4-162">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="231e4-163">**Opis:** _61_</span><span class="sxs-lookup"><span data-stu-id="231e4-163">**Description:** _61_</span></span>
    - <span data-ttu-id="231e4-164">**Typ popytu:** *Zamówienie sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="231e4-164">**Demand type:** *Sales order*</span></span>

        <span data-ttu-id="231e4-165">Obecnie jedynym obsługiwanym typem popytu jest *Zamówienie sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="231e4-165">Currently, *Sales order* is the only demand type that is supported.</span></span>

    - <span data-ttu-id="231e4-166">**Strategia popytu:** _Zamówione_</span><span class="sxs-lookup"><span data-stu-id="231e4-166">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="231e4-167">Dostępne do konfiguracji w tym polu są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-167">The following values are available in this field:</span></span>

        - <span data-ttu-id="231e4-168">**Zamówione** – pełna zamówiona ilość na zamówieniu sprzedaży powinna być traktowana jako zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="231e4-168">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="231e4-169">**Zarezerwowane** – należy brać pod uwagę zapotrzebowanie tylko dla wierszy zamówienia sprzedaży, które są zarezerwowane (fizyczne i zamówione).</span><span class="sxs-lookup"><span data-stu-id="231e4-169">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>

    - <span data-ttu-id="231e4-170">**Magazyn:** _61_</span><span class="sxs-lookup"><span data-stu-id="231e4-170">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="231e4-171">**Zezwalaj, aby żądania w ramach grupy czynności korzystały z niezarezerwowanych ilości:** _Tak_</span><span class="sxs-lookup"><span data-stu-id="231e4-171">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="231e4-172">Można również określić kwerendę, aby zawęzić zakres ocenianych popytów.</span><span class="sxs-lookup"><span data-stu-id="231e4-172">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="231e4-173">Ustaw rozpisywanie na przedziały w magazynie dla każdego szablonu</span><span class="sxs-lookup"><span data-stu-id="231e4-173">Set up slotting specifications for each template</span></span>

<span data-ttu-id="231e4-174">Dla każdego tworzonego szablonu należy wykonać poniższe kroki, aby dodać wiersz dla każdej specyfikacji rozpisywania na przedziały w magazynie.</span><span class="sxs-lookup"><span data-stu-id="231e4-174">For each template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="231e4-175">Na skróconej karcie **Szczegółów dot. szablonu rozpisywania na przedziały w magazynie** wybierz opcję **Nowy**, aby utworzyć wiersz szablonu.</span><span class="sxs-lookup"><span data-stu-id="231e4-175">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="231e4-176">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-176">On the new line, set the following values:</span></span>

    - <span data-ttu-id="231e4-177">**Sekwencja:** _1_</span><span class="sxs-lookup"><span data-stu-id="231e4-177">**Sequence:** _1_</span></span>
    - <span data-ttu-id="231e4-178">**Opis:** _stała lokalizacja_</span><span class="sxs-lookup"><span data-stu-id="231e4-178">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="231e4-179">**Ilość minimalna:** _1_</span><span class="sxs-lookup"><span data-stu-id="231e4-179">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="231e4-180">To pole określa minimalną ilość zapotrzebowania wymaganą dla danego wiersza.</span><span class="sxs-lookup"><span data-stu-id="231e4-180">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="231e4-181">**Ilość maksymalna:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="231e4-181">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="231e4-182">To pole określa maksymalna ilość zapotrzebowania, która jest prawidłowa dla danego wiersza.</span><span class="sxs-lookup"><span data-stu-id="231e4-182">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="231e4-183">**Jednostka:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="231e4-183">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="231e4-184">To pole definiuje jednostkę miary, do której odnoszą się ilości minimalne i maksymalne.</span><span class="sxs-lookup"><span data-stu-id="231e4-184">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="231e4-185">**Warstwa jednostki miary:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="231e4-185">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="231e4-186">To pole określa liczbę jednostek miary popytu, która jest prawidłowa dla danego wiersza.</span><span class="sxs-lookup"><span data-stu-id="231e4-186">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="231e4-187">(Aby uzyskać więcej informacji, zobacz sekcję [Konwersje jednostki miary dla wariantów produktów](#unit-tiers) w tym temacie).</span><span class="sxs-lookup"><span data-stu-id="231e4-187">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="231e4-188">**Przypisz kryteria przedziału:** _Rozważona ilość_</span><span class="sxs-lookup"><span data-stu-id="231e4-188">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="231e4-189">Dostępne do konfiguracji w tym polu są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-189">The following values are available in this field:</span></span>

        - <span data-ttu-id="231e4-190">**Przyjmij wartość pustą** – system powinien założyć, że wszystkie lokalizacje w obszarze pobrania są puste i nie powinny sprawdzać tych lokalizacji w magazynie.</span><span class="sxs-lookup"><span data-stu-id="231e4-190">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="231e4-191">**Przyjmij ilość** – system powinien sprawdzić, czy lokalizacje w obszarze pobrania są puste i powinien przeskoczyć wszystkie lokalizacje, które nie są puste.</span><span class="sxs-lookup"><span data-stu-id="231e4-191">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>

    - <span data-ttu-id="231e4-192">**Kod dyrektywy:** _Rozpisywanie na przedziały_</span><span class="sxs-lookup"><span data-stu-id="231e4-192">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="231e4-193">To pole określa dyrektywę lokalizacji, która służy do wyszukiwania lokalizacji pobrania dla pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="231e4-193">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="231e4-194">**Lokalizacja przepełnienia:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="231e4-194">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="231e4-195">To pole służy do definiowania lokalizacji, do której mają być przemieszczone zapasy, jeśli nie można odnaleźć lokalizacji dla ilości w trakcie przetwarzania wiersza.</span><span class="sxs-lookup"><span data-stu-id="231e4-195">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="231e4-196">**Zezwalaj na przeniesienie:** _Tak_</span><span class="sxs-lookup"><span data-stu-id="231e4-196">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="231e4-197">Jeśli ta opcja jest ustawiona na *Tak*, to w przypadku, gdy nie można rozpisać popytu na przedziały, zostanie utworzone zlecenie pracy przeniesienia zapasów z lokalizacji, w której się znajdują, ale gdzie nic nie było rozpisane.</span><span class="sxs-lookup"><span data-stu-id="231e4-197">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="231e4-198">Następnie szablon zostanie uruchomiony ponownie.</span><span class="sxs-lookup"><span data-stu-id="231e4-198">The template is then run again.</span></span> <span data-ttu-id="231e4-199">Tym razem system ignoruje zapasy w lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="231e4-199">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="231e4-200">Ta funkcja działa najlepiej, gdy w polu **Przypisz kryterium przedziału** jest ustawiona wartość _Rozważ ilość_.</span><span class="sxs-lookup"><span data-stu-id="231e4-200">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="231e4-201">**Stałe użycie lokalizacji:** _Tylko stałe lokalizacje produktu_</span><span class="sxs-lookup"><span data-stu-id="231e4-201">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="231e4-202">Dostępne do konfiguracji w tym polu są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-202">The following values are available in this field:</span></span>

        - <span data-ttu-id="231e4-203">**Lokalizacje stałe i niestałe** – system nie powinien ograniczać się do używania tylko stałych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="231e4-203">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="231e4-204">**Tylko stałe lokalizacje produktu** – system powinien rozważać tylko lokalizacje, które są stałymi lokalizacjami produktu.</span><span class="sxs-lookup"><span data-stu-id="231e4-204">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="231e4-205">**Tylko stałe lokalizacje wariantu produktu** – system powinien rozważać tylko lokalizacje, które są stałymi lokalizacjami wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="231e4-205">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

1. <span data-ttu-id="231e4-206">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="231e4-206">Select **Save**.</span></span>
1. <span data-ttu-id="231e4-207">Wybierz **Nowe**, aby utworzyć drugi wiersz szablonu.</span><span class="sxs-lookup"><span data-stu-id="231e4-207">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="231e4-208">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="231e4-209">**Sekwencja:** _2_</span><span class="sxs-lookup"><span data-stu-id="231e4-209">**Sequence:** _2_</span></span>
    - <span data-ttu-id="231e4-210">**Opis:** _Inne_</span><span class="sxs-lookup"><span data-stu-id="231e4-210">**Description:** _Other_</span></span>
    - <span data-ttu-id="231e4-211">**Ilość minimalna:** _1_</span><span class="sxs-lookup"><span data-stu-id="231e4-211">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="231e4-212">**Ilość maksymalna:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="231e4-212">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="231e4-213">**Jednostka:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="231e4-213">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="231e4-214">**Warstwa jednostki miary:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="231e4-214">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="231e4-215">**Przypisz kryteria przedziału:** _Rozważona ilość_</span><span class="sxs-lookup"><span data-stu-id="231e4-215">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="231e4-216">**Kod dyrektywy:** _Rozpisywanie na przedziały_</span><span class="sxs-lookup"><span data-stu-id="231e4-216">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="231e4-217">**Lokalizacja przepełnienia:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="231e4-217">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="231e4-218">**Zezwalaj na przeniesienie:** _Tak_</span><span class="sxs-lookup"><span data-stu-id="231e4-218">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="231e4-219">**Korzystaj ze stałych lokalizacji:** _Stałe i niestałe lokalizacje_</span><span class="sxs-lookup"><span data-stu-id="231e4-219">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="231e4-220">W kwerendzie dla drugiego wiersza zostaną teraz określone kryteria, które zostaną użyte do określenia lokalizacji, do których można przekierować popyt na dany wiersz.</span><span class="sxs-lookup"><span data-stu-id="231e4-220">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="231e4-221">Znajdź wiersz, w którym pole o nazwie **Sekwencja** ma wartość *2*.</span><span class="sxs-lookup"><span data-stu-id="231e4-221">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="231e4-222">Wybierz **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="231e4-222">Select **Edit query**.</span></span>
1. <span data-ttu-id="231e4-223">Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="231e4-223">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="231e4-224">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-224">On the new line, set the following values:</span></span>

    - <span data-ttu-id="231e4-225">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="231e4-225">**Table:** *Locations*</span></span>
    - <span data-ttu-id="231e4-226">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="231e4-226">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="231e4-227">**Pole:** *Identyfikator profilu lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="231e4-227">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="231e4-228">**Kryteria:** *Pick-06* (wybierz podwójny znak plus \[**++**\] w polu, aby rozwinąć listę, a następnie wybierz opcję *Pick-06* - *Miejsce pobrania 6*).</span><span class="sxs-lookup"><span data-stu-id="231e4-228">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="231e4-229">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="231e4-229">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="231e4-230">Ustaw dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="231e4-230">Set up location directives</span></span>

<span data-ttu-id="231e4-231">Co najmniej jedna dyrektywa lokalizacji musi być skonfigurowana tak, aby obsługiwała pobrania rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="231e4-231">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="231e4-232">Procedury przedstawione w tej sekcji służą do skonfigurowania nowej *dyrektywy lokalizacji uzupełnienia* dla pobrań rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="231e4-232">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="231e4-233">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="231e4-233">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="231e4-234">W lewym panelu, w polu **Typ zlecenia pracy** zaznacz opcję *Uzupełnienia*.</span><span class="sxs-lookup"><span data-stu-id="231e4-234">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="231e4-235">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="231e4-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="231e4-236">W nagłówku nowej dyrektywy lokalizacji w polu **Nazwa** wprowadź wartość *Przedział pobrania 61*.</span><span class="sxs-lookup"><span data-stu-id="231e4-236">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="231e4-237">Skonfiguruj skróconą kartę dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="231e4-237">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="231e4-238">Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="231e4-238">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="231e4-239">Zaakceptuj wartość domyślną we wszystkich pozostałych polach.</span><span class="sxs-lookup"><span data-stu-id="231e4-239">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="231e4-240">**Typ pracy:** _Pobranie_</span><span class="sxs-lookup"><span data-stu-id="231e4-240">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="231e4-241">**Oddział:** _6_</span><span class="sxs-lookup"><span data-stu-id="231e4-241">**Site:** _6_</span></span>
    - <span data-ttu-id="231e4-242">**Magazyn:** _61_</span><span class="sxs-lookup"><span data-stu-id="231e4-242">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="231e4-243">**Kod dyrektywy:** _Rozpisywanie na przedziały_</span><span class="sxs-lookup"><span data-stu-id="231e4-243">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="231e4-244">Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="231e4-244">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="231e4-245">Skonfiguruj skróconą kartę Wiersze</span><span class="sxs-lookup"><span data-stu-id="231e4-245">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="231e4-246">Na skróconej karcie **Wiersze** kliknij przycisk **Nowe**, aby utworzyć nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="231e4-246">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="231e4-247">W nowym wierszu ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="231e4-247">On the new line, set the following values.</span></span> <span data-ttu-id="231e4-248">Zaakceptuj wartość domyślną we wszystkich pozostałych polach.</span><span class="sxs-lookup"><span data-stu-id="231e4-248">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="231e4-249">**Od ilości:** _0_</span><span class="sxs-lookup"><span data-stu-id="231e4-249">**From quantity:** _0_</span></span>
    - <span data-ttu-id="231e4-250">**Do ilości:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="231e4-250">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="231e4-251">Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="231e4-251">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="231e4-252">Skonfiguruj skróconą kartę Dyrektywy akcji</span><span class="sxs-lookup"><span data-stu-id="231e4-252">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="231e4-253">Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby utworzyć wiersz.</span><span class="sxs-lookup"><span data-stu-id="231e4-253">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="231e4-254">W nowym wierszu ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="231e4-254">On the new line, set the following values.</span></span> <span data-ttu-id="231e4-255">Zaakceptuj wartość domyślną we wszystkich pozostałych polach.</span><span class="sxs-lookup"><span data-stu-id="231e4-255">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="231e4-256">**Nazwa:** _Bulk_</span><span class="sxs-lookup"><span data-stu-id="231e4-256">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="231e4-257">**Strategia:** _Brak_</span><span class="sxs-lookup"><span data-stu-id="231e4-257">**Strategy:** _None_</span></span>

1. <span data-ttu-id="231e4-258">Wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="231e4-258">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="231e4-259">Edytuj kwerendę</span><span class="sxs-lookup"><span data-stu-id="231e4-259">Edit the query</span></span>

1. <span data-ttu-id="231e4-260">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="231e4-260">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="231e4-261">Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="231e4-261">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="231e4-262">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-262">On the new line, set the following values:</span></span>

    - <span data-ttu-id="231e4-263">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="231e4-263">**Table:** *Locations*</span></span>
    - <span data-ttu-id="231e4-264">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="231e4-264">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="231e4-265">**Pole:** *Identyfikator strefy*</span><span class="sxs-lookup"><span data-stu-id="231e4-265">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="231e4-266">**Kryteria:** *Bulk* (wybierz podwójny znak plus \[**++**\] w polu, aby rozwinąć listę, a następnie wybierz opcję *Bulk*).</span><span class="sxs-lookup"><span data-stu-id="231e4-266">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="231e4-267">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="231e4-267">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="231e4-268">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="231e4-268">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="231e4-269">Konfiguracja scenariusza</span><span class="sxs-lookup"><span data-stu-id="231e4-269">Set up the scenario</span></span>

<span data-ttu-id="231e4-270">W tym scenariuszu należy skorzystać z wbudowanych danych przykładowych i utworzyć rekordy opisane w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="231e4-270">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="231e4-271">Skorzystaj z przykładowych danych USMF</span><span class="sxs-lookup"><span data-stu-id="231e4-271">Use the USMF sample data</span></span>

<span data-ttu-id="231e4-272">Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="231e4-272">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="231e4-273">Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="231e4-273">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="231e4-274">Utwórz popyt</span><span class="sxs-lookup"><span data-stu-id="231e4-274">Create demand</span></span>

<span data-ttu-id="231e4-275">Wykonaj poniższe kroki, aby utworzyć zapotrzebowanie, do którego będzie stosowane rozpisanie na przedziały.</span><span class="sxs-lookup"><span data-stu-id="231e4-275">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="231e4-276">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="231e4-276">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="231e4-277">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="231e4-277">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="231e4-278">W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz _US-007_.</span><span class="sxs-lookup"><span data-stu-id="231e4-278">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="231e4-279">W polu **Magazyn** wybierz wartość _61_.</span><span class="sxs-lookup"><span data-stu-id="231e4-279">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="231e4-280">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="231e4-280">Select **OK**.</span></span>
1. <span data-ttu-id="231e4-281">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="231e4-281">The new sales order is opened.</span></span> <span data-ttu-id="231e4-282">Zawiera pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="231e4-282">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="231e4-283">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-283">On this line, set the following values:</span></span>

    - <span data-ttu-id="231e4-284">**Pozycja:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="231e4-284">**Item:** _L0101_</span></span>
    - <span data-ttu-id="231e4-285">**Ilość:** _20_</span><span class="sxs-lookup"><span data-stu-id="231e4-285">**Quantity:** _20_</span></span>

1. <span data-ttu-id="231e4-286">Wybierz polecenie **Dodaj wiersz**, aby dodać nowy wiersz i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-286">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="231e4-287">**Pozycja:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="231e4-287">**Item:** _T0100_</span></span>
    - <span data-ttu-id="231e4-288">**Ilość:** _8_</span><span class="sxs-lookup"><span data-stu-id="231e4-288">**Quantity:** _8_</span></span>

1. <span data-ttu-id="231e4-289">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="231e4-289">Select **Save**.</span></span>
1. <span data-ttu-id="231e4-290">Wybierz pozycję **Nowe**, aby utworzyć drugie zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="231e4-290">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="231e4-291">W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz _US-008_.</span><span class="sxs-lookup"><span data-stu-id="231e4-291">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="231e4-292">W polu **Magazyn** wybierz wartość _61_.</span><span class="sxs-lookup"><span data-stu-id="231e4-292">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="231e4-293">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="231e4-293">The new sales order is opened.</span></span> <span data-ttu-id="231e4-294">Zawiera pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="231e4-294">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="231e4-295">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="231e4-295">On this line, set the following values:</span></span>

    - <span data-ttu-id="231e4-296">**Pozycja:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="231e4-296">**Item:** _T0100_</span></span>
    - <span data-ttu-id="231e4-297">**Ilość:** _1_</span><span class="sxs-lookup"><span data-stu-id="231e4-297">**Quantity:** _1_</span></span>

1. <span data-ttu-id="231e4-298">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="231e4-298">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="231e4-299">Przechodzenie przez typowy scenariusz rozpisania na przedziały</span><span class="sxs-lookup"><span data-stu-id="231e4-299">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="231e4-300">Po wykonaniu wszystkich wstępnie wymaganych elementów, zgodnie z opisem w poprzedniej sekcji, można wypróbować tę funkcję, wykonując poszczególne działania w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="231e4-300">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="231e4-301">Generuj popyt</span><span class="sxs-lookup"><span data-stu-id="231e4-301">Generate demand</span></span>

1. <span data-ttu-id="231e4-302">Przejdź do **Zarządzanie magazynem \> Ustawienia \> Uzupełnianie \> Szablony rozpisania na przedziały**, a następnie wybierz szablon rozpisania na przedziały, który został wcześniej utworzony.</span><span class="sxs-lookup"><span data-stu-id="231e4-302">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="231e4-303">W okienku akcji wybierz pozycję **Utwórz popyt**.</span><span class="sxs-lookup"><span data-stu-id="231e4-303">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="231e4-304">To polecenie ocenia cały popyt w systemie, który odpowiada kwerendzie szablonu rozpisanie na przedziały.</span><span class="sxs-lookup"><span data-stu-id="231e4-304">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="231e4-305">Łączne zapotrzebowanie dla wszystkich zamówień jest następnie konsolidowane w jeden wiersz na ilość/jednostka miary.</span><span class="sxs-lookup"><span data-stu-id="231e4-305">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="231e4-306">Po zakończeniu procesu pojawi się komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="231e4-306">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="231e4-307">Popyt rozpisywany na przedziały</span><span class="sxs-lookup"><span data-stu-id="231e4-307">Slotting demand</span></span>

<span data-ttu-id="231e4-308">*Żądanie rozpisania na przedziały* pokazuje wyniki generowania popytu na podstawie konfiguracji szablonu rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="231e4-308">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="231e4-309">W okienku akcji wybierz opcję **Rozpisania na przedziały**, aby wyświetlić wyniki polecenia **Generuj popyt**.</span><span class="sxs-lookup"><span data-stu-id="231e4-309">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="231e4-310">Można edytować wiersze popytu rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="231e4-310">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="231e4-311">Istnieje możliwość usunięcia wiersza, dodania nowego wiersza lub edytowania szczegółów.</span><span class="sxs-lookup"><span data-stu-id="231e4-311">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="231e4-312">Popyt można edytować ręcznie lub można go zaimportować z systemu zewnętrznego za pomocą funkcji zarządzania danymi.</span><span class="sxs-lookup"><span data-stu-id="231e4-312">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="231e4-313">Wszystko, co znajduje się w popycie rozpisania na przedziały, będzie używane w następnym kroku, niezależnie od pochodzenia.</span><span class="sxs-lookup"><span data-stu-id="231e4-313">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="231e4-314">Lokalizuj popyt</span><span class="sxs-lookup"><span data-stu-id="231e4-314">Locate demand</span></span>

<span data-ttu-id="231e4-315">Po wygenerowaniu popytu musisz skorzystać z polecenia **Znajdź żądanie** w celu wygenerowania *planu rozpisania na przedziały*.</span><span class="sxs-lookup"><span data-stu-id="231e4-315">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="231e4-316">W okienku akcji wybierz pozycję **Zlokalizuj popyt**.</span><span class="sxs-lookup"><span data-stu-id="231e4-316">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="231e4-317">Proces rozpisania na przedziały jest uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="231e4-317">The slotting process runs.</span></span> <span data-ttu-id="231e4-318">Po zakończeniu procesu pojawi się komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="231e4-318">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="231e4-319">Plan rozpisywania na przedziały</span><span class="sxs-lookup"><span data-stu-id="231e4-319">Slotting plan</span></span>

<span data-ttu-id="231e4-320">W planie rozpisania na przedziały jest wyświetlana lokalizacja, do której przypisano każdy towar/ilość, niezależnie od tego, czy zastosowano przepełnienie, czy utworzono pracę i niezależnie od wiersza szablonu, który został użyty.</span><span class="sxs-lookup"><span data-stu-id="231e4-320">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="231e4-321">**Popyt, którego nie udało się rozpisać, jest wyróżniony kolorem czerwonym.**</span><span class="sxs-lookup"><span data-stu-id="231e4-321">**Any demand that could not be slotted is highlighted in red.**</span></span>

- <span data-ttu-id="231e4-322">W okienku akcji wybierz opcję **Plan rozpisania na przedziały**, aby wyświetlić wyniki.</span><span class="sxs-lookup"><span data-stu-id="231e4-322">On the Action Pane, select **Slotting plan** to view the results.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="231e4-323">Uzupełnianie zapasów – skrzynie</span><span class="sxs-lookup"><span data-stu-id="231e4-323">Create replenishment</span></span>

<span data-ttu-id="231e4-324">Po utworzeniu planu rozpisania na przedziały należy utworzyć *Pracę uzupełniania zapasów* opartą na tym planie.</span><span class="sxs-lookup"><span data-stu-id="231e4-324">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="231e4-325">W okienku akcji wybierz opcję **Uruchom uzupełnianie**.</span><span class="sxs-lookup"><span data-stu-id="231e4-325">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="231e4-326">Po zakończeniu procesu pojawi się komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="231e4-326">An informational message appears when the process is completed.</span></span> <span data-ttu-id="231e4-327">Ten komunikat wskazuje liczbę nagłówków utworzonych dla identyfikatora kompilacji pracy.</span><span class="sxs-lookup"><span data-stu-id="231e4-327">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="231e4-328">Dyrektywy lokalizacji, które będą używane, są identyfikowane na podstawie kodu dyrektywy określonego w każdym wierszu szablonu.</span><span class="sxs-lookup"><span data-stu-id="231e4-328">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="231e4-329">Porady</span><span class="sxs-lookup"><span data-stu-id="231e4-329">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="231e4-330">Ustawienie automatycznego rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="231e4-330">Set up automatic slotting</span></span>

<span data-ttu-id="231e4-331">Po umieszczeniu wszystkich wymaganych elementów można skonfigurować rozpisanie na przedziały do automatycznego uruchamiania, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="231e4-331">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="231e4-332">Wybierz kolejno opcje **Zarządzanie magazynem \> Uzupełnienie \> Uruchomieni rozpisania na przedziały**.</span><span class="sxs-lookup"><span data-stu-id="231e4-332">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="231e4-333">Określ kroki rozpisania na przedziały, które mają być uruchomione.</span><span class="sxs-lookup"><span data-stu-id="231e4-333">Specify the slotting steps to run.</span></span> <span data-ttu-id="231e4-334">Wybierz co najmniej jeden z następujących kroków rozpisania na przedziały:</span><span class="sxs-lookup"><span data-stu-id="231e4-334">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="231e4-335">Generuj popyt</span><span class="sxs-lookup"><span data-stu-id="231e4-335">Generate demand</span></span>
    - <span data-ttu-id="231e4-336">Lokalizuj popyt</span><span class="sxs-lookup"><span data-stu-id="231e4-336">Locate demand</span></span>
    - <span data-ttu-id="231e4-337">Utwórz pracę uzupełniania zapasów</span><span class="sxs-lookup"><span data-stu-id="231e4-337">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="231e4-338">Kroki rozpisania na przedziały są wykonywane stopniowo.</span><span class="sxs-lookup"><span data-stu-id="231e4-338">The slotting steps are progressive.</span></span> <span data-ttu-id="231e4-339">Jeśli chcesz wybrać opcję *Znajdź żądanie*, musisz najpierw wybrać opcję *Generuj popyt*.</span><span class="sxs-lookup"><span data-stu-id="231e4-339">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="231e4-340">Określ szablon rozpisania na przedziały, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="231e4-340">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="231e4-341">Wybierz cykliczność powtarzania automatycznego.</span><span class="sxs-lookup"><span data-stu-id="231e4-341">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="231e4-342">W przypadku ćwiczeń w tym scenariuszu **nie należy** ustawiać automatycznego rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="231e4-342">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
