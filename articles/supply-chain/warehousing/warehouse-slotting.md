---
title: Rozpisywanie na przedziały w magazynie
description: Ten temat zawiera informacje o rozpisywaniu na przedziały w magazynie. Rozpisywanie na przedziały umożliwia konsolidowanie popytu według towarów i jednostki miary z zamówień o stanie Zamówione, Zarezerwowane lub Zwolnione. Ułatwia to kierownikom magazynów zaplanowanie lokalizacji pobrania przed zwolnieniem zamówień do magazynu i utworzenie pracy pobrania.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 31b86837735ca16610a1d304eab611b12a6aceeb
ms.sourcegitcommit: be4b9d557511bbb43e71a93f2c3b23b5f1a4669d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "4627756"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="9cf14-105">Rozpisywanie na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="9cf14-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9cf14-106">Funkcje rozpisywania na przedziały w kilku magazynach ułatwia kierownikom magazynów zaplanowanie lokalizacji pobrania przed zwolnieniem zamówień do magazynu i utworzenie pracy pobrania.</span><span class="sxs-lookup"><span data-stu-id="9cf14-106">Several warehouse slotting features are available to help warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

<span data-ttu-id="9cf14-107">*Funkcja Rozpisywanie na przedziały* umożliwia konsolidowanie popytu według towarów i jednostki miary z zamówień o stanie *Zamówione*, *Zarezerwowane* lub *Zwolnione*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-107">The *Warehouse slotting feature* lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="9cf14-108">Wygenerowane zapotrzebowanie może być następnie stosowane do lokalizacji, które będą używane do pobierania, na podstawie ilości, jednostki, wymiarów fizycznych, stałych lokalizacji itd.</span><span class="sxs-lookup"><span data-stu-id="9cf14-108">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="9cf14-109">Po ustaleniu planu rozpisania na przedziały można utworzyć pracę uzupełniającą w celu przeniesienia odpowiedniej ilości zapasów do poszczególnych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="9cf14-109">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="9cf14-110">Funkcja *Rozpisywanie na przedziały dla zamówień przeniesienia* umożliwia menedżerom magazynowym uzupełnianie lokalizacji pobrań na podstawie popytu na zamówieniach przeniesienia, które nie zostały jeszcze zwolnione do magazynu.</span><span class="sxs-lookup"><span data-stu-id="9cf14-110">The *Warehouse slotting for transfer orders* feature lets warehouse managers replenish picking locations, based on demand from transfer orders that aren't yet released to the warehouse.</span></span> <span data-ttu-id="9cf14-111">Dzięki temu lokalizacje pobrania będą obejmowały wszystkie towary wymagane dla zamówień przeniesienia po ich zwolnieniu do magazynu.</span><span class="sxs-lookup"><span data-stu-id="9cf14-111">It ensures that picking locations will include all the items that are required for the transfer orders after they are released to warehouse.</span></span> <span data-ttu-id="9cf14-112">Ta funkcja wymaga również włączenia funkcji *Rozpisywania na przedziały w magazynie*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-112">This feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span>

<span data-ttu-id="9cf14-113">Funkcja *Udoskonaleń alokacji rozpisywania na przedziały w magazynie* umożliwia dodanie opcji dla wierszy szablonu używanych przez funkcję *Rozpisywanie na przedziały w magazynie*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-113">The *Warehouse slotting allocation enhancements* feature adds an option for the template lines that are used by the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="9cf14-114">Opcja pozwala systemowi na uwzględnienie istniejących dostępnych zapasów w lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="9cf14-114">The option enables the system to consider existing on-hand inventory at a target location.</span></span> <span data-ttu-id="9cf14-115">W związku z tym dla rozpisywania na przedziały w magazynie może zostać wygenerowanych mniej uzupełnień zapasów.</span><span class="sxs-lookup"><span data-stu-id="9cf14-115">Therefore, fewer replenishments might be generated for slotting.</span></span> <span data-ttu-id="9cf14-116">Funkcja *Udoskonaleń alokacji rozpisywania na przedziały w magazynie* wymaga także włączenia funkcji *Rozpisywanie na przedziały w magazynie*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-116">The *Warehouse slotting allocation enhancements* feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="9cf14-117">Może być opcjonalnie używany z funkcją *Rozpisywanie na przedziały w magazynie dla zamówień przeniesienia*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-117">It can optionally be used together with the *Warehouse slotting for transfer orders* feature.</span></span>

## <a name="turn-on-the-warehouse-slotting-features"></a><span data-ttu-id="9cf14-118">Włącz funkcje rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="9cf14-118">Turn on the warehouse slotting features</span></span>

<span data-ttu-id="9cf14-119">Aby móc używać tych funkcji, należy je włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-119">Before you can use these features, they must be turned on in your system.</span></span> <span data-ttu-id="9cf14-120">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć je, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="9cf14-120">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="9cf14-121">W razie potrzeby włącz następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="9cf14-121">Turn on the following features as required:</span></span>

- <span data-ttu-id="9cf14-122">Funkcja rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="9cf14-122">Warehouse slotting feature</span></span>
- <span data-ttu-id="9cf14-123">Rozpisywanie na przedziały w magazynie dla zamówień przeniesienia</span><span class="sxs-lookup"><span data-stu-id="9cf14-123">Warehouse slotting for transfer orders</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9cf14-124">Aby ta funkcja była włączona, należy włączyć funkcję *Funkcja rozpisywania na przedziały w magazynie*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-124">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

- <span data-ttu-id="9cf14-125">Ulepszenia alokacji rozpisywania na przedziały dla magazynu</span><span class="sxs-lookup"><span data-stu-id="9cf14-125">Warehouse slotting allocation enhancements</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9cf14-126">Aby ta funkcja była włączona, należy włączyć funkcję *Funkcja rozpisywania na przedziały w magazynie*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-126">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="9cf14-127">Konfigurowanie rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="9cf14-127">Set up warehouse slotting</span></span>

<span data-ttu-id="9cf14-128">Aby można było skorzystać z tej funkcji, należy skonfigurować następujące elementy w systemie:</span><span class="sxs-lookup"><span data-stu-id="9cf14-128">To use warehouse slotting, you must set up the following elements in your system:</span></span>

- <span data-ttu-id="9cf14-129">Warstwy jednostek miary rozpisywania na przedziały</span><span class="sxs-lookup"><span data-stu-id="9cf14-129">Slotting unit of measure tiers</span></span>
- <span data-ttu-id="9cf14-130">Kody dyrektyw</span><span class="sxs-lookup"><span data-stu-id="9cf14-130">Directive codes</span></span>
- <span data-ttu-id="9cf14-131">Szablony rozpisywania na przedziały</span><span class="sxs-lookup"><span data-stu-id="9cf14-131">Slotting templates</span></span>
- <span data-ttu-id="9cf14-132">Dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="9cf14-132">Location directives</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="9cf14-133">Utwórz warstwy jednostki miary dla rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="9cf14-133">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="9cf14-134">Warstwy jednostek miary umożliwiają zgrupowanie wielu jednostek miary w celach rozpisywania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="9cf14-134">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="9cf14-135">Na przykład, jeśli wiele pudełek jest pobieranych z tego samego obszaru pobrania, można utworzyć jedną warstwę dla wszystkich rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="9cf14-135">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="9cf14-136">**Należy utworzyć wiersz dla każdej jednostki miary, która powinna być częścią warstwy.**</span><span class="sxs-lookup"><span data-stu-id="9cf14-136">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="9cf14-137">Przejdź do **Ustawień zarządzania \> Konfiguracji \> Uzupełniania \> Warstwa jednostki miary – rozpisywanie na przedziały w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-137">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="9cf14-138">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-138">Select **New**.</span></span>
1. <span data-ttu-id="9cf14-139">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-139">In the header, set the following values:</span></span>

    - <span data-ttu-id="9cf14-140">**Warstwa jednostki miary:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="9cf14-140">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="9cf14-141">**Opis:** *Każde pudełko paleta*</span><span class="sxs-lookup"><span data-stu-id="9cf14-141">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="9cf14-142">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-142">Select **Save**.</span></span>
1. <span data-ttu-id="9cf14-143">Na skróconej karcie **Jednostki miary** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="9cf14-143">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="9cf14-144">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9cf14-145">**Jednostka:** *Pudełko*</span><span class="sxs-lookup"><span data-stu-id="9cf14-145">**Unit:** *Box*</span></span>
    - <span data-ttu-id="9cf14-146">**Opis:** – zostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="9cf14-146">**Description:** Leave this field blank.</span></span> <span data-ttu-id="9cf14-147">Zostanie ono wypełnione automatycznie po zapisaniu zmian.</span><span class="sxs-lookup"><span data-stu-id="9cf14-147">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="9cf14-148">**Klasa jednostek:** *Ilość*</span><span class="sxs-lookup"><span data-stu-id="9cf14-148">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="9cf14-149">Kliknij przycisk **Nowe**, aby dodać drugi wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="9cf14-149">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="9cf14-150">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-150">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9cf14-151">**Jednostka:** *EA*</span><span class="sxs-lookup"><span data-stu-id="9cf14-151">**Unit:** *ea*</span></span>
    - <span data-ttu-id="9cf14-152">**Opis:** – zostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="9cf14-152">**Description:** Leave this field blank.</span></span> <span data-ttu-id="9cf14-153">Zostanie ono wypełnione automatycznie po zapisaniu zmian.</span><span class="sxs-lookup"><span data-stu-id="9cf14-153">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="9cf14-154">**Klasa jednostek:** *Ilość*</span><span class="sxs-lookup"><span data-stu-id="9cf14-154">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="9cf14-155">Kliknij przycisk **Nowe**, aby dodać trzeci wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="9cf14-155">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="9cf14-156">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-156">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9cf14-157">**Jednostka:** *PL*</span><span class="sxs-lookup"><span data-stu-id="9cf14-157">**Unit:** *PL*</span></span>
    - <span data-ttu-id="9cf14-158">**Opis:** – zostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="9cf14-158">**Description:** Leave this field blank.</span></span> <span data-ttu-id="9cf14-159">Zostanie ono wypełnione automatycznie po zapisaniu zmian.</span><span class="sxs-lookup"><span data-stu-id="9cf14-159">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="9cf14-160">**Klasa jednostek:** *Ilość*</span><span class="sxs-lookup"><span data-stu-id="9cf14-160">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="9cf14-161">Wybierz **Zapisz**, aby zapisać warstwę.</span><span class="sxs-lookup"><span data-stu-id="9cf14-161">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="9cf14-162">Utwórz kod dyrektywy dla rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="9cf14-162">Create a directive code for slotting</span></span>

<span data-ttu-id="9cf14-163">Należy wybrać kod dyrektywy, który powinien być skojarzony z szablonem.</span><span class="sxs-lookup"><span data-stu-id="9cf14-163">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="9cf14-164">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kody dyrektyw**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-164">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="9cf14-165">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-165">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9cf14-166">W polu **Kod dyrektywy** wprowadź *Rozpisywanie na przedziały w magazynie*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-166">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="9cf14-167">W polu **Opis dyrektywy** wprowadź *Rozpisywanie na przedziały w magazynie*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-167">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="9cf14-168">Skonfiguruj szablony rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="9cf14-168">Set up slotting templates</span></span>

<span data-ttu-id="9cf14-169">Każdy szablon rozpisywania na przedziały w magazynie służy do sterowania sposobem przypisywania zapasów do lokalizacji dla określonego magazynu.</span><span class="sxs-lookup"><span data-stu-id="9cf14-169">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="9cf14-170">Każdy szablon musi zawierać wiersz dla każdej specyfikacji rozpisywania na przedziały w magazynie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-170">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="9cf14-171">Procedury przedstawione w tej sekcji służą do konfigurowania szablonów rozpisywania na przedziały w magazynie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-171">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="9cf14-172">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony rozpisywania na przedziały w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-172">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="9cf14-173">Wybierz pozycję **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="9cf14-173">Select **New** to create a template.</span></span>

<span data-ttu-id="9cf14-174">Następnie należy ustawić nagłówek szablonu, specyfikacje rozpisywania na przedziały w magazynie oraz dyrektywy lokalizacji, jak wyjaśniono w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="9cf14-174">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span> <span data-ttu-id="9cf14-175">Konfiguracja rozpisywania na przedziały dla zamówień przeniesienia przypomina konfigurację rozpisywania na przedziały dla zamówień sprzedaży, ale w polu **Typ zapotrzebowania** jest ustawiana wartość *Zamówienia przeniesienia*, a nie *Zamówienie sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-175">The setup for slotting for transfer orders resembles the setup for slotting for sales orders, but the **Demand type** field is set *Transfer orders* instead of *Sales order*.</span></span>

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a><span data-ttu-id="9cf14-176">Konfigurowanie nagłówka dla szablonu Rozpisywanie na przedziały dla zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9cf14-176">Set up the header for a sales order slotting template</span></span>

1. <span data-ttu-id="9cf14-177">W nagłówku szablonu określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-177">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="9cf14-178">**Szablon rozpisywania na przedziały w magazynie:** _61_</span><span class="sxs-lookup"><span data-stu-id="9cf14-178">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="9cf14-179">**Opis:** _61_</span><span class="sxs-lookup"><span data-stu-id="9cf14-179">**Description:** _61_</span></span>
    - <span data-ttu-id="9cf14-180">**Typ popytu:** *Zamówienie sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="9cf14-180">**Demand type:** *Sales order*</span></span>

        > [!NOTE]
        > <span data-ttu-id="9cf14-181">Obecnie *Zamówienia sprzedaży* i *Zamówienia przeniesienia* są jedynymi obsługiwanymi typami popytu.</span><span class="sxs-lookup"><span data-stu-id="9cf14-181">Currently, *Sales orders* and *Transfer orders* are the only demand types that are supported.</span></span> <span data-ttu-id="9cf14-182">*Zamówienia przeniesienia* może wybrać tylko wtedy, gdy jest włączona funkcja *Rozpisywanie na przedziały w magazynie dla zamówień przeniesienia*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-182">You can select *Transfer orders* only if the *Warehouse Slotting for transfer orders* feature is turned on.</span></span>

    - <span data-ttu-id="9cf14-183">**Strategia popytu:** _Zamówione_</span><span class="sxs-lookup"><span data-stu-id="9cf14-183">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="9cf14-184">Dostępne do konfiguracji w tym polu są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-184">The following values are available in this field:</span></span>

        - <span data-ttu-id="9cf14-185">**Zamówione** – pełna zamówiona ilość na zamówieniu sprzedaży powinna być traktowana jako zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-185">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="9cf14-186">**Zarezerwowane** – należy brać pod uwagę zapotrzebowanie tylko dla wierszy zamówienia sprzedaży, które są zarezerwowane (fizyczne i zamówione).</span><span class="sxs-lookup"><span data-stu-id="9cf14-186">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>
        - <span data-ttu-id="9cf14-187">**Zwolnione** — ilość zwolniona powinna być uznana za zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-187">**Released** – The released quantity should be considered demand.</span></span>

    - <span data-ttu-id="9cf14-188">**Magazyn:** _61_</span><span class="sxs-lookup"><span data-stu-id="9cf14-188">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="9cf14-189">**Zezwalaj, aby żądania w ramach grupy czynności korzystały z niezarezerwowanych ilości:** _Tak_</span><span class="sxs-lookup"><span data-stu-id="9cf14-189">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="9cf14-190">Można również określić kwerendę, aby zawęzić zakres ocenianych popytów.</span><span class="sxs-lookup"><span data-stu-id="9cf14-190">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="9cf14-191">Ustaw rozpisywanie na przedziały w magazynie dla każdego szablonu</span><span class="sxs-lookup"><span data-stu-id="9cf14-191">Set up slotting specifications for each template</span></span>

<span data-ttu-id="9cf14-192">Dla każdego tworzonego szablonu zamówienia sprzedaży należy wykonać poniższe kroki, aby dodać wiersz dla każdej specyfikacji rozpisywania na przedziały w magazynie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-192">For each sales order template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="9cf14-193">Na skróconej karcie **Szczegółów dot. szablonu rozpisywania na przedziały w magazynie** wybierz opcję **Nowy**, aby utworzyć wiersz szablonu.</span><span class="sxs-lookup"><span data-stu-id="9cf14-193">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="9cf14-194">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-194">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9cf14-195">**Sekwencja:** _1_</span><span class="sxs-lookup"><span data-stu-id="9cf14-195">**Sequence:** _1_</span></span>
    - <span data-ttu-id="9cf14-196">**Opis:** _stała lokalizacja_</span><span class="sxs-lookup"><span data-stu-id="9cf14-196">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="9cf14-197">**Ilość minimalna:** _1_</span><span class="sxs-lookup"><span data-stu-id="9cf14-197">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="9cf14-198">To pole określa minimalną ilość zapotrzebowania wymaganą dla danego wiersza.</span><span class="sxs-lookup"><span data-stu-id="9cf14-198">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="9cf14-199">**Ilość maksymalna:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="9cf14-199">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="9cf14-200">To pole określa maksymalna ilość zapotrzebowania, która jest prawidłowa dla danego wiersza.</span><span class="sxs-lookup"><span data-stu-id="9cf14-200">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="9cf14-201">**Jednostka:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="9cf14-201">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="9cf14-202">To pole definiuje jednostkę miary, do której odnoszą się ilości minimalne i maksymalne.</span><span class="sxs-lookup"><span data-stu-id="9cf14-202">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="9cf14-203">**Warstwa jednostki miary:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="9cf14-203">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="9cf14-204">To pole określa liczbę jednostek miary popytu, która jest prawidłowa dla danego wiersza.</span><span class="sxs-lookup"><span data-stu-id="9cf14-204">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="9cf14-205">(Aby uzyskać więcej informacji, zobacz sekcję [Konwersje jednostki miary dla wariantów produktów](#unit-tiers) w tym temacie).</span><span class="sxs-lookup"><span data-stu-id="9cf14-205">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="9cf14-206">**Przypisz kryteria przedziału:** _Rozważona ilość_</span><span class="sxs-lookup"><span data-stu-id="9cf14-206">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="9cf14-207">Dostępne do konfiguracji w tym polu są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-207">The following values are available in this field:</span></span>

        - <span data-ttu-id="9cf14-208">**Przyjmij wartość pustą** – system powinien założyć, że wszystkie lokalizacje w obszarze pobrania są puste i nie powinny sprawdzać tych lokalizacji w magazynie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-208">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="9cf14-209">**Przyjmij ilość** – system powinien sprawdzić, czy lokalizacje w obszarze pobrania są puste i powinien przeskoczyć wszystkie lokalizacje, które nie są puste.</span><span class="sxs-lookup"><span data-stu-id="9cf14-209">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>
        - <span data-ttu-id="9cf14-210">**Uwzględnić dostępne zapasy** — system powinien sprawdzać, czy dowolna lokalizacja docelowa zawiera niezarezerwowane ilości pozycji w wierszu zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="9cf14-210">**Consider on-hand** – The system should check whether any target location contains unreserved quantities for the item on the demand line.</span></span> <span data-ttu-id="9cf14-211">Jeśli ilość jest dostatecznie duża, aby zaspokoić co najmniej jedną jednostkę wiersza popytu, wygenerowany rekord planu rozpisywania na przedziały jest redukowany o dostępną ilość.</span><span class="sxs-lookup"><span data-stu-id="9cf14-211">If the quantity is large enough to satisfy at least one unit of the demand line, the generated slotting plan record is reduced by the available amount.</span></span> <span data-ttu-id="9cf14-212">Na przykład, jeśli popyt ma wielkość 10 przypadków, a dla jednego przypadku jest dostępny jeden przypadek, to znajdowane zapotrzebowanie będzie miało dziewięć przypadków.</span><span class="sxs-lookup"><span data-stu-id="9cf14-212">For example, if the demand is 10 cases, and one case is on hand, the located demand will be nine cases.</span></span> <span data-ttu-id="9cf14-213">Jeśli popyt ma wielkość 10 przypadków, a każdy jest dostępny, to znajdowane zapotrzebowanie będzie miało 10 przypadków.</span><span class="sxs-lookup"><span data-stu-id="9cf14-213">If the demand is 10 cases, and one each is on hand, the located demand will be 10 cases.</span></span> <span data-ttu-id="9cf14-214">Ta wartość jest dostępna tylko wtedy, gdy jest włączona funkcja *Ulepszenia alokacji rozpisywania na przedziały dla magazynu*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-214">This value is available only when the *Warehouse slotting allocation enhancements* feature is turned on.</span></span>

    - <span data-ttu-id="9cf14-215">**Kod dyrektywy:** _Rozpisywanie na przedziały_</span><span class="sxs-lookup"><span data-stu-id="9cf14-215">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="9cf14-216">To pole określa dyrektywę lokalizacji, która służy do wyszukiwania lokalizacji pobrania dla pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="9cf14-216">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="9cf14-217">**Lokalizacja przepełnienia:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="9cf14-217">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="9cf14-218">To pole służy do definiowania lokalizacji, do której mają być przemieszczone zapasy, jeśli nie można odnaleźć lokalizacji dla ilości w trakcie przetwarzania wiersza.</span><span class="sxs-lookup"><span data-stu-id="9cf14-218">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="9cf14-219">**Zezwalaj na przeniesienie:** _Tak_</span><span class="sxs-lookup"><span data-stu-id="9cf14-219">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="9cf14-220">Jeśli ta opcja jest ustawiona na *Tak*, to w przypadku, gdy nie można rozpisać popytu na przedziały, zostanie utworzone zlecenie pracy przeniesienia zapasów z lokalizacji, w której się znajdują, ale gdzie nic nie było rozpisane.</span><span class="sxs-lookup"><span data-stu-id="9cf14-220">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="9cf14-221">Następnie szablon zostanie uruchomiony ponownie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-221">The template is then run again.</span></span> <span data-ttu-id="9cf14-222">Tym razem system ignoruje zapasy w lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="9cf14-222">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="9cf14-223">Ta funkcja działa najlepiej, gdy w polu **Przypisz kryterium przedziału** jest ustawiona wartość _Rozważ ilość_.</span><span class="sxs-lookup"><span data-stu-id="9cf14-223">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="9cf14-224">**Stałe użycie lokalizacji:** _Tylko stałe lokalizacje produktu_</span><span class="sxs-lookup"><span data-stu-id="9cf14-224">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="9cf14-225">Dostępne do konfiguracji w tym polu są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-225">The following values are available in this field:</span></span>

        - <span data-ttu-id="9cf14-226">**Lokalizacje stałe i niestałe** – system nie powinien ograniczać się do używania tylko stałych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="9cf14-226">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="9cf14-227">**Tylko stałe lokalizacje produktu** – system powinien rozważać tylko lokalizacje, które są stałymi lokalizacjami produktu.</span><span class="sxs-lookup"><span data-stu-id="9cf14-227">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="9cf14-228">**Tylko stałe lokalizacje wariantu produktu** – system powinien rozważać tylko lokalizacje, które są stałymi lokalizacjami wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="9cf14-228">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

> [!NOTE]
> <span data-ttu-id="9cf14-229">Jeśli szablon rozpisywania na przedziały zawiera co najmniej jeden wiersz, w którym w polu **Przypisz kryterium gniazda** jest ustawiona wartość *Uwzględnić dostępne zapasy*, prowizje nie są już dozwolone dla żadnego wiersza w szablonie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-229">If the slotting template contains at least one line where the **Assign slot criteria** field is set to *Consider on-hand*, let-ups are no longer allowed for any line in the template.</span></span>

1. <span data-ttu-id="9cf14-230">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-230">Select **Save**.</span></span>
1. <span data-ttu-id="9cf14-231">Wybierz **Nowe**, aby utworzyć drugi wiersz szablonu.</span><span class="sxs-lookup"><span data-stu-id="9cf14-231">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="9cf14-232">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9cf14-233">**Sekwencja:** _2_</span><span class="sxs-lookup"><span data-stu-id="9cf14-233">**Sequence:** _2_</span></span>
    - <span data-ttu-id="9cf14-234">**Opis:** _Inne_</span><span class="sxs-lookup"><span data-stu-id="9cf14-234">**Description:** _Other_</span></span>
    - <span data-ttu-id="9cf14-235">**Ilość minimalna:** _1_</span><span class="sxs-lookup"><span data-stu-id="9cf14-235">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="9cf14-236">**Ilość maksymalna:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="9cf14-236">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="9cf14-237">**Jednostka:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="9cf14-237">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="9cf14-238">**Warstwa jednostki miary:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="9cf14-238">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="9cf14-239">**Przypisz kryteria przedziału:** _Rozważona ilość_</span><span class="sxs-lookup"><span data-stu-id="9cf14-239">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="9cf14-240">**Kod dyrektywy:** _Rozpisywanie na przedziały_</span><span class="sxs-lookup"><span data-stu-id="9cf14-240">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="9cf14-241">**Lokalizacja przepełnienia:** Pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="9cf14-241">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="9cf14-242">**Zezwalaj na przeniesienie:** _Tak_</span><span class="sxs-lookup"><span data-stu-id="9cf14-242">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="9cf14-243">**Korzystaj ze stałych lokalizacji:** _Stałe i niestałe lokalizacje_</span><span class="sxs-lookup"><span data-stu-id="9cf14-243">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="9cf14-244">W kwerendzie dla drugiego wiersza zostaną teraz określone kryteria, które zostaną użyte do określenia lokalizacji, do których można przekierować popyt na dany wiersz.</span><span class="sxs-lookup"><span data-stu-id="9cf14-244">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="9cf14-245">Znajdź wiersz, w którym pole o nazwie **Sekwencja** ma wartość *2*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-245">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="9cf14-246">Wybierz **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-246">Select **Edit query**.</span></span>
1. <span data-ttu-id="9cf14-247">Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="9cf14-247">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="9cf14-248">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-248">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9cf14-249">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="9cf14-249">**Table:** *Locations*</span></span>
    - <span data-ttu-id="9cf14-250">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="9cf14-250">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="9cf14-251">**Pole:** *Identyfikator profilu lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="9cf14-251">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="9cf14-252">**Kryteria:** *Pick-06* (wybierz podwójny znak plus \[**++**\] w polu, aby rozwinąć listę, a następnie wybierz opcję *Pick-06* - *Miejsce pobrania 6*).</span><span class="sxs-lookup"><span data-stu-id="9cf14-252">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="9cf14-253">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-253">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="9cf14-254">Ustaw dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="9cf14-254">Set up location directives</span></span>

<span data-ttu-id="9cf14-255">Co najmniej jedna dyrektywa lokalizacji musi być skonfigurowana tak, aby obsługiwała pobrania rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="9cf14-255">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="9cf14-256">Procedury przedstawione w tej sekcji służą do skonfigurowania nowej *dyrektywy lokalizacji uzupełnienia* dla pobrań rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="9cf14-256">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="9cf14-257">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-257">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="9cf14-258">W lewym panelu, w polu **Typ zlecenia pracy** zaznacz opcję *Uzupełnienia*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-258">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="9cf14-259">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-259">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9cf14-260">W nagłówku nowej dyrektywy lokalizacji w polu **Nazwa** wprowadź wartość *Przedział pobrania 61*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-260">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>
1. <span data-ttu-id="9cf14-261">W polu **Numer sekwencyjny** zaakceptuj wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="9cf14-261">In the **Sequence number** field, accept the default value.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="9cf14-262">Skonfiguruj skróconą kartę dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="9cf14-262">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="9cf14-263">Na skróconej karcie **Dyrektywy lokalizacji** ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="9cf14-263">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="9cf14-264">Zaakceptuj wartość domyślną we wszystkich pozostałych polach.</span><span class="sxs-lookup"><span data-stu-id="9cf14-264">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="9cf14-265">**Typ pracy:** _Pobranie_</span><span class="sxs-lookup"><span data-stu-id="9cf14-265">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="9cf14-266">**Oddział:** _6_</span><span class="sxs-lookup"><span data-stu-id="9cf14-266">**Site:** _6_</span></span>
    - <span data-ttu-id="9cf14-267">**Magazyn:** _61_</span><span class="sxs-lookup"><span data-stu-id="9cf14-267">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="9cf14-268">**Kod dyrektywy:** _Rozpisywanie na przedziały_</span><span class="sxs-lookup"><span data-stu-id="9cf14-268">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="9cf14-269">Wybierz opcję **Zapisz**, aby skrócona karta **Wiersze** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="9cf14-269">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="9cf14-270">Skonfiguruj skróconą kartę Wiersze</span><span class="sxs-lookup"><span data-stu-id="9cf14-270">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="9cf14-271">Na skróconej karcie **Wiersze** kliknij przycisk **Nowe**, aby utworzyć nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="9cf14-271">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="9cf14-272">W nowym wierszu ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="9cf14-272">On the new line, set the following values.</span></span>

    - <span data-ttu-id="9cf14-273">**Od ilości:** _0_</span><span class="sxs-lookup"><span data-stu-id="9cf14-273">**From quantity:** _0_</span></span>
    - <span data-ttu-id="9cf14-274">**Do ilości:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="9cf14-274">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="9cf14-275">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="9cf14-275">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="9cf14-276">Wybierz opcję **Zapisz**, aby skrócona karta **Dyrektywy akcji lokalizacji** stała się dostępna.</span><span class="sxs-lookup"><span data-stu-id="9cf14-276">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="9cf14-277">Skonfiguruj skróconą kartę Dyrektywy akcji</span><span class="sxs-lookup"><span data-stu-id="9cf14-277">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="9cf14-278">Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby utworzyć wiersz.</span><span class="sxs-lookup"><span data-stu-id="9cf14-278">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="9cf14-279">W nowym wierszu ustaw następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="9cf14-279">On the new line, set the following values.</span></span> <span data-ttu-id="9cf14-280">Zaakceptuj wartość domyślną we wszystkich pozostałych polach.</span><span class="sxs-lookup"><span data-stu-id="9cf14-280">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="9cf14-281">**Numer sekwencyjny:** Zaakceptuj wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="9cf14-281">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="9cf14-282">**Nazwa:** _Bulk_</span><span class="sxs-lookup"><span data-stu-id="9cf14-282">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="9cf14-283">**Strategia:** _Brak_</span><span class="sxs-lookup"><span data-stu-id="9cf14-283">**Strategy:** _None_</span></span>

1. <span data-ttu-id="9cf14-284">Zaakceptuj wartość domyślną dla wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="9cf14-284">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="9cf14-285">Wybierz opcję **Zapisz**, aby udostępnić przycisk **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-285">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="9cf14-286">Edytuj kwerendę</span><span class="sxs-lookup"><span data-stu-id="9cf14-286">Edit the query</span></span>

1. <span data-ttu-id="9cf14-287">Na skróconej karcie **Akcje dyrektywy lokalizacji** wybierz pozycję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-287">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="9cf14-288">Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="9cf14-288">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="9cf14-289">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-289">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9cf14-290">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="9cf14-290">**Table:** *Locations*</span></span>
    - <span data-ttu-id="9cf14-291">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="9cf14-291">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="9cf14-292">**Pole:** *Identyfikator strefy*</span><span class="sxs-lookup"><span data-stu-id="9cf14-292">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="9cf14-293">**Kryteria:** *Bulk* (wybierz podwójny znak plus \[**++**\] w polu, aby rozwinąć listę, a następnie wybierz opcję *Bulk*).</span><span class="sxs-lookup"><span data-stu-id="9cf14-293">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="9cf14-294">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-294">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="9cf14-295">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="9cf14-295">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="9cf14-296">Konfiguracja scenariusza</span><span class="sxs-lookup"><span data-stu-id="9cf14-296">Set up the scenario</span></span>

<span data-ttu-id="9cf14-297">W tym scenariuszu należy skorzystać z wbudowanych danych przykładowych i utworzyć rekordy opisane w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="9cf14-297">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="9cf14-298">Skorzystaj z przykładowych danych USMF</span><span class="sxs-lookup"><span data-stu-id="9cf14-298">Use the USMF sample data</span></span>

<span data-ttu-id="9cf14-299">Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9cf14-299">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="9cf14-300">Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="9cf14-300">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="9cf14-301">Utwórz popyt</span><span class="sxs-lookup"><span data-stu-id="9cf14-301">Create demand</span></span>

<span data-ttu-id="9cf14-302">Wykonaj poniższe kroki, aby utworzyć zapotrzebowanie, do którego będzie stosowane rozpisanie na przedziały.</span><span class="sxs-lookup"><span data-stu-id="9cf14-302">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="9cf14-303">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-303">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="9cf14-304">Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9cf14-304">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="9cf14-305">W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz _US-007_.</span><span class="sxs-lookup"><span data-stu-id="9cf14-305">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="9cf14-306">W polu **Magazyn** wybierz wartość _61_.</span><span class="sxs-lookup"><span data-stu-id="9cf14-306">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="9cf14-307">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-307">Select **OK**.</span></span>
1. <span data-ttu-id="9cf14-308">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="9cf14-308">The new sales order is opened.</span></span> <span data-ttu-id="9cf14-309">Zawiera pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-309">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="9cf14-310">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-310">On this line, set the following values:</span></span>

    - <span data-ttu-id="9cf14-311">**Pozycja:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="9cf14-311">**Item:** _L0101_</span></span>
    - <span data-ttu-id="9cf14-312">**Ilość:** _20_</span><span class="sxs-lookup"><span data-stu-id="9cf14-312">**Quantity:** _20_</span></span>

1. <span data-ttu-id="9cf14-313">Wybierz polecenie **Dodaj wiersz**, aby dodać nowy wiersz i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-313">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="9cf14-314">**Pozycja:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="9cf14-314">**Item:** _T0100_</span></span>
    - <span data-ttu-id="9cf14-315">**Ilość:** _8_</span><span class="sxs-lookup"><span data-stu-id="9cf14-315">**Quantity:** _8_</span></span>

1. <span data-ttu-id="9cf14-316">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-316">Select **Save**.</span></span>
1. <span data-ttu-id="9cf14-317">Wybierz pozycję **Nowe**, aby utworzyć drugie zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9cf14-317">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="9cf14-318">W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz _US-008_.</span><span class="sxs-lookup"><span data-stu-id="9cf14-318">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="9cf14-319">W polu **Magazyn** wybierz wartość _61_.</span><span class="sxs-lookup"><span data-stu-id="9cf14-319">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="9cf14-320">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="9cf14-320">The new sales order is opened.</span></span> <span data-ttu-id="9cf14-321">Zawiera pusty wiersz na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-321">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="9cf14-322">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9cf14-322">On this line, set the following values:</span></span>

    - <span data-ttu-id="9cf14-323">**Pozycja:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="9cf14-323">**Item:** _T0100_</span></span>
    - <span data-ttu-id="9cf14-324">**Ilość:** _1_</span><span class="sxs-lookup"><span data-stu-id="9cf14-324">**Quantity:** _1_</span></span>

1. <span data-ttu-id="9cf14-325">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-325">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="9cf14-326">Przechodzenie przez typowy scenariusz rozpisania na przedziały</span><span class="sxs-lookup"><span data-stu-id="9cf14-326">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="9cf14-327">Po wykonaniu wszystkich wstępnie wymaganych elementów, zgodnie z opisem w poprzedniej sekcji, można wypróbować tę funkcję, wykonując poszczególne działania w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="9cf14-327">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="9cf14-328">Generuj popyt</span><span class="sxs-lookup"><span data-stu-id="9cf14-328">Generate demand</span></span>

1. <span data-ttu-id="9cf14-329">Przejdź do **Zarządzanie magazynem \> Ustawienia \> Uzupełnianie \> Szablony rozpisania na przedziały**, a następnie wybierz szablon rozpisania na przedziały, który został wcześniej utworzony.</span><span class="sxs-lookup"><span data-stu-id="9cf14-329">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="9cf14-330">W okienku akcji wybierz pozycję **Utwórz popyt**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-330">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="9cf14-331">To polecenie ocenia cały popyt w systemie, który odpowiada kwerendzie szablonu rozpisanie na przedziały.</span><span class="sxs-lookup"><span data-stu-id="9cf14-331">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="9cf14-332">Łączne zapotrzebowanie dla wszystkich zamówień jest następnie konsolidowane w jeden wiersz na ilość/jednostka miary.</span><span class="sxs-lookup"><span data-stu-id="9cf14-332">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="9cf14-333">Po zakończeniu procesu pojawi się komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="9cf14-333">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="9cf14-334">Popyt rozpisywany na przedziały</span><span class="sxs-lookup"><span data-stu-id="9cf14-334">Slotting demand</span></span>

<span data-ttu-id="9cf14-335">*Żądanie rozpisania na przedziały* pokazuje wyniki generowania popytu na podstawie konfiguracji szablonu rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="9cf14-335">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="9cf14-336">W okienku akcji wybierz opcję **Rozpisania na przedziały**, aby wyświetlić wyniki polecenia **Generuj popyt**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-336">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="9cf14-337">Można edytować wiersze popytu rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="9cf14-337">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="9cf14-338">Istnieje możliwość usunięcia wiersza, dodania nowego wiersza lub edytowania szczegółów.</span><span class="sxs-lookup"><span data-stu-id="9cf14-338">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="9cf14-339">Popyt można edytować ręcznie lub można go zaimportować z systemu zewnętrznego za pomocą funkcji zarządzania danymi.</span><span class="sxs-lookup"><span data-stu-id="9cf14-339">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="9cf14-340">Wszystko, co znajduje się w popycie rozpisania na przedziały, będzie używane w następnym kroku, niezależnie od pochodzenia.</span><span class="sxs-lookup"><span data-stu-id="9cf14-340">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="9cf14-341">Lokalizuj popyt</span><span class="sxs-lookup"><span data-stu-id="9cf14-341">Locate demand</span></span>

<span data-ttu-id="9cf14-342">Po wygenerowaniu popytu musisz skorzystać z polecenia **Znajdź żądanie** w celu wygenerowania *planu rozpisania na przedziały*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-342">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="9cf14-343">W okienku akcji wybierz pozycję **Zlokalizuj popyt**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-343">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="9cf14-344">Proces rozpisania na przedziały jest uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="9cf14-344">The slotting process runs.</span></span> <span data-ttu-id="9cf14-345">Po zakończeniu procesu pojawi się komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="9cf14-345">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="9cf14-346">Plan rozpisywania na przedziały</span><span class="sxs-lookup"><span data-stu-id="9cf14-346">Slotting plan</span></span>

<span data-ttu-id="9cf14-347">W planie rozpisania na przedziały jest wyświetlana lokalizacja, do której przypisano każdy towar/ilość, niezależnie od tego, czy zastosowano przepełnienie, czy utworzono pracę i niezależnie od wiersza szablonu, który został użyty.</span><span class="sxs-lookup"><span data-stu-id="9cf14-347">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="9cf14-348">*Popyt, którego nie udało się rozpisać, jest wyróżniony kolorem czerwonym.*</span><span class="sxs-lookup"><span data-stu-id="9cf14-348">*Any demand that could not be slotted is highlighted in red.*</span></span>

- <span data-ttu-id="9cf14-349">W okienku akcji wybierz opcję **Plan rozpisania na przedziały**, aby wyświetlić wyniki.</span><span class="sxs-lookup"><span data-stu-id="9cf14-349">On the Action Pane, select **Slotting plan** to view the results.</span></span>

> [!NOTE]
> - <span data-ttu-id="9cf14-350">Procesy **Generuj popyt**, **Lokalizuj popyt** i **Wykonaj uzupełnianie zapasów** są teraz uruchamiane w piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="9cf14-350">The **Generate demand**, **Locate demand**, and **Run replenishment** processes are now run in a sandbox.</span></span> <span data-ttu-id="9cf14-351">(Te procesy są dostępne w okienku akcji na stronie **Szablony rozpisywania na przedziały**.)</span><span class="sxs-lookup"><span data-stu-id="9cf14-351">(These processes are available from the Action Pane on the **Slotting templates** page.)</span></span>
> - <span data-ttu-id="9cf14-352">Procesy **Generuj popyt**, **Lokalizuj popyt** i **Wykonaj uzupełnianie zapasów** mają blokadę, aby upewnić się, że nie można ich zainicjować w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-352">The **Generate demand**, **Locate demand**, and **Run replenishment** processes have a lock to ensure that they can't be triggered at the same time.</span></span> <span data-ttu-id="9cf14-353">W przeciwnym razie można usunąć używane dane.</span><span class="sxs-lookup"><span data-stu-id="9cf14-353">Otherwise, the data that is used could be deleted.</span></span>
> - <span data-ttu-id="9cf14-354">Procesy **Generuj popyt** i **Lokalizuj popyt** wyświetlają ostrzeżenie, jeśli w wyniku uruchomienia nie zostały wygenerowane rekordy lub w rekordach brakuje informacji.</span><span class="sxs-lookup"><span data-stu-id="9cf14-354">The **Generate demand** and **Locate demand** processes show a warning if the run didn't generate records, or if the records are missing information.</span></span>
> - <span data-ttu-id="9cf14-355">Po wybraniu opcji **Plan rozpisywania na przedziały**, strona nie zawiera przycisków **Nowy**, **Edytuj** i **Usuń** w okienku akcji, ponieważ nie można edytować źródła danych.</span><span class="sxs-lookup"><span data-stu-id="9cf14-355">When you select **Slotting plan**, the page doesn't have **New**, **Edit**, or **Delete** buttons on the Action Pane, because the data source can't be edited.</span></span>
> - <span data-ttu-id="9cf14-356">Po wybraniu opcji **Uruchom uzupełnienie** system sprawdza poprawność wybranego szablonu rozpisywania i procesów.</span><span class="sxs-lookup"><span data-stu-id="9cf14-356">When you select **Run replenishment**, the system validates the selected slot template and processes.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="9cf14-357">Uzupełnianie zapasów – skrzynie</span><span class="sxs-lookup"><span data-stu-id="9cf14-357">Create replenishment</span></span>

<span data-ttu-id="9cf14-358">Po utworzeniu planu rozpisania na przedziały należy utworzyć *Pracę uzupełniania zapasów* opartą na tym planie.</span><span class="sxs-lookup"><span data-stu-id="9cf14-358">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="9cf14-359">W okienku akcji wybierz opcję **Uruchom uzupełnianie**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-359">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="9cf14-360">Po zakończeniu procesu pojawi się komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="9cf14-360">An informational message appears when the process is completed.</span></span> <span data-ttu-id="9cf14-361">Ten komunikat wskazuje liczbę nagłówków utworzonych dla identyfikatora kompilacji pracy.</span><span class="sxs-lookup"><span data-stu-id="9cf14-361">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="9cf14-362">Dyrektywy lokalizacji, które będą używane, są identyfikowane na podstawie kodu dyrektywy określonego w każdym wierszu szablonu.</span><span class="sxs-lookup"><span data-stu-id="9cf14-362">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="9cf14-363">Porady</span><span class="sxs-lookup"><span data-stu-id="9cf14-363">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="9cf14-364">Ustawienie automatycznego rozpisywania na przedziały w magazynie</span><span class="sxs-lookup"><span data-stu-id="9cf14-364">Set up automatic slotting</span></span>

<span data-ttu-id="9cf14-365">Po umieszczeniu wszystkich wymaganych elementów można skonfigurować rozpisanie na przedziały do automatycznego uruchamiania, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="9cf14-365">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="9cf14-366">Wybierz kolejno opcje **Zarządzanie magazynem \> Uzupełnienie \> Uruchomieni rozpisania na przedziały**.</span><span class="sxs-lookup"><span data-stu-id="9cf14-366">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="9cf14-367">Określ kroki rozpisania na przedziały, które mają być uruchomione.</span><span class="sxs-lookup"><span data-stu-id="9cf14-367">Specify the slotting steps to run.</span></span> <span data-ttu-id="9cf14-368">Wybierz co najmniej jeden z następujących kroków rozpisania na przedziały:</span><span class="sxs-lookup"><span data-stu-id="9cf14-368">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="9cf14-369">Generuj popyt</span><span class="sxs-lookup"><span data-stu-id="9cf14-369">Generate demand</span></span>
    - <span data-ttu-id="9cf14-370">Lokalizuj popyt</span><span class="sxs-lookup"><span data-stu-id="9cf14-370">Locate demand</span></span>
    - <span data-ttu-id="9cf14-371">Utwórz pracę uzupełniania zapasów</span><span class="sxs-lookup"><span data-stu-id="9cf14-371">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="9cf14-372">Kroki rozpisania na przedziały są wykonywane stopniowo.</span><span class="sxs-lookup"><span data-stu-id="9cf14-372">The slotting steps are progressive.</span></span> <span data-ttu-id="9cf14-373">Jeśli chcesz wybrać opcję *Znajdź żądanie*, musisz najpierw wybrać opcję *Generuj popyt*.</span><span class="sxs-lookup"><span data-stu-id="9cf14-373">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="9cf14-374">Określ szablon rozpisania na przedziały, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="9cf14-374">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="9cf14-375">Wybierz cykliczność powtarzania automatycznego.</span><span class="sxs-lookup"><span data-stu-id="9cf14-375">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="9cf14-376">W przypadku ćwiczeń w tym scenariuszu **nie należy** ustawiać automatycznego rozpisania na przedziały.</span><span class="sxs-lookup"><span data-stu-id="9cf14-376">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
