---
title: Ustawianie różnych wymiarów pakowania i przechowywania
description: W tym temacie pokazano, jak określić, do którego procesu (pakowanie, przechowywanie lub zagnieżdżone pakowanie) będzie używany każdy określony wymiar.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 004d9b4522335b481b640ef0fe35f4db66e3c9f5
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078298"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a><span data-ttu-id="4f7f6-103">Ustawianie różnych wymiarów pakowania i przechowywania</span><span class="sxs-lookup"><span data-stu-id="4f7f6-103">Set different dimensions for packing and storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f7f6-104">Niektóre towary są pakowane lub przechowywane w taki sposób, że konieczne może być śledzenie wymiarów fizycznych w inny sposób dla każdego z kilku różnych procesów.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-104">Some items are packed or stored in such a way that you may need to track physical dimensions differently for each of several different processes.</span></span> <span data-ttu-id="4f7f6-105">Funkcja *wymiarów produktu do pakowania* umożliwia skonfigurowanie jednego lub kilku typów wymiarów dla każdego produktu.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-105">The *Packaging product dimensions* feature lets you set up one or several types of dimensions for each product.</span></span> <span data-ttu-id="4f7f6-106">Każdy typ wymiaru ma zestaw miar fizycznych (waga, szerokość, głębokość i wysokość) i ustala proces, w którym te wartości miar fizycznych mają zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-106">Each dimension type provides a set of physical measurements (weight, width, depth, and height), and establishes the process where those physical measurement values apply.</span></span> <span data-ttu-id="4f7f6-107">Gdy ta funkcja jest włączona, system obsługuje następujące typy wymiarów:</span><span class="sxs-lookup"><span data-stu-id="4f7f6-107">When this feature is enabled, your system will support the following types of dimensions:</span></span>

- <span data-ttu-id="4f7f6-108">*Przechowywanie* — wymiary magazynowania są używane razem z danymi wolumetrycznymi lokalizacji w celu określenia, ile każdego towaru można przechowywać w różnych lokalizacjach magazynowych.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-108">*Storage* - Storage dimensions are used along with location volumetrics to determine how many of each item can be stored in various warehouse locations.</span></span>
- <span data-ttu-id="4f7f6-109">*Pakowanie* — wymiary pakowania są używane podczas konteneryzacji i ręcznego procesu pakowania w celu określenia, ile każdego towaru dopasuje się do różnych typów kontenerów.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-109">*Packing* - Packing dimensions are used during containerization and the manual packing process to determine how many of each item will fit in various container types.</span></span>
- <span data-ttu-id="4f7f6-110">*Zagnieżdżone pakowanie* — zagnieżdżone wymiary pakowania są używane, gdy proces pakowania zawiera wiele poziomów.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-110">*Nested packing* - Nested packing dimensions are used when the packing process contains multiple levels.</span></span>

<span data-ttu-id="4f7f6-111">Wymiany *magazynowania* są obsługiwane, nawet jeśli funkcja *Wymiary produktu do pakowania* nie jest włączona.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-111">*Storage* dimensions are supported even when the *Packaging product dimensions* feature isn't enabled.</span></span> <span data-ttu-id="4f7f6-112">Te ustawienia są ustawiane za pomocą strony **Wymiar fizyczny** w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-112">You set these up using the **Physical dimension** page in Supply Chain Management.</span></span> <span data-ttu-id="4f7f6-113">Te wymiary są używane przez wszystkie procesy, w których nie określono wymiarów pakowania i zagnieżdżonych wymiarów pakowania.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-113">These dimensions are used by all processes where the packing and nested packing dimensions aren't specified.</span></span>

<span data-ttu-id="4f7f6-114">Wymiary *pakowania* i *zagnieżdżonego pakowania* są ustawiane za pomocą strony **Fizyczne wymiary produktu**, która jest dodawana po włączeniu funkcji *wymiarów produktu do pakowania*.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-114">*Packing* and *nested packing* dimensions are set up using the **Physical product dimensions** page, which is added when you enable the *Packaging product dimensions* feature.</span></span>
<span data-ttu-id="4f7f6-115">Ten temat zawiera scenariusz, który ilustruje sposób używania tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-115">This topic provides a scenario that illustrates how to use this feature.</span></span>

## <a name="turn-on-the-packaging-product-dimensions-feature"></a><span data-ttu-id="4f7f6-116">Włączanie funkcji wymiarów produktu opakowania</span><span class="sxs-lookup"><span data-stu-id="4f7f6-116">Turn on the packaging product dimensions feature</span></span>

<span data-ttu-id="4f7f6-117">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-117">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="4f7f6-118">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-118">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="4f7f6-119">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="4f7f6-119">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="4f7f6-120">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-120">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="4f7f6-121">**Nazwa funkcji:** *Wymiary produktu do pakowania*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-121">**Feature name:** *Packaging product dimensions*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="4f7f6-122">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="4f7f6-122">Example scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="4f7f6-123">Konfiguracja scenariusza</span><span class="sxs-lookup"><span data-stu-id="4f7f6-123">Set up the scenario</span></span>

<span data-ttu-id="4f7f6-124">Przed uruchomieniem przykładowego scenariusza należy przygotować system w sposób opisany w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-124">Before you can run the example scenario, you must prepare your system as described in this section.</span></span>

#### <a name="enable-demo-data"></a><span data-ttu-id="4f7f6-125">Włączanie danych pokazowych</span><span class="sxs-lookup"><span data-stu-id="4f7f6-125">Enable demo data</span></span>

<span data-ttu-id="4f7f6-126">Aby pracować z tym scenariuszem przy użyciu określonych pokazowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane pokazowe](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4f7f6-126">To work through this scenario using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="4f7f6-127">Dodatkowo należy również wybrać firmę *USMF* przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-127">Additionally, you must select the *USMF* legal entity before you begin.</span></span>

#### <a name="add-a-new-physical-dimension-to-a-product"></a><span data-ttu-id="4f7f6-128">Dodawanie nowego wymiaru fizycznego do produktu</span><span class="sxs-lookup"><span data-stu-id="4f7f6-128">Add a new physical dimension to a product</span></span>

<span data-ttu-id="4f7f6-129">Dodaj nowy wymiar fizyczny dla produktu, wykonując następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="4f7f6-129">Add a new physical dimension for a product by doing the following:</span></span>

1. <span data-ttu-id="4f7f6-130">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-130">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="4f7f6-131">Wybierz produkt z **numerem pozycji** *A0001*.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-131">Select the product with **Item number** *A0001*.</span></span>
1. <span data-ttu-id="4f7f6-132">W okienku akcji otwórz kartę **Zarządzaj zapasami** i w grupie **Magazyn** wybierz **Wymiary fizyczne produktu**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-132">On the Action Pane, open the **Manage inventory** tab and, from the **Warehouse** group, select **Physical product dimensions**.</span></span>
1. <span data-ttu-id="4f7f6-133">Zostanie otwarta strona **Wymiary fizyczne produktu**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-133">The **Physical product dimensions** page opens.</span></span> <span data-ttu-id="4f7f6-134">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wymiar do siatki, używając następujących ustawień:</span><span class="sxs-lookup"><span data-stu-id="4f7f6-134">On the Action Pane, select **New** to add a new dimension to the grid with the following settings:</span></span>
    - <span data-ttu-id="4f7f6-135">**Typ wymiaru fizycznego** - *Pakowanie*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-135">**Physical dimension type** - *Packing*</span></span>
    - <span data-ttu-id="4f7f6-136">**Jednostka fizyczna** - *sztuki*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-136">**Physical unit** - *pcs*</span></span>
    - <span data-ttu-id="4f7f6-137">**Waga** - *4*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-137">**Weight** - *4*</span></span>
    - <span data-ttu-id="4f7f6-138">**Jednostka wagi** - *kg*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-138">**Weight unit** - *kg*</span></span>
    - <span data-ttu-id="4f7f6-139">**Długość** - *3*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-139">**Depth** - *3*</span></span>
    - <span data-ttu-id="4f7f6-140">**Wysokość** - *4*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-140">**Height** - *4*</span></span>
    - <span data-ttu-id="4f7f6-141">**Szerokość** - *3*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-141">**Width** - *3*</span></span>
    - <span data-ttu-id="4f7f6-142">**Długość** - *cm*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-142">**Length** - *cm*</span></span>
    - <span data-ttu-id="4f7f6-143">**Jednostka objętości** - *cm3*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-143">**Volume unit** - *cm3*</span></span>

<span data-ttu-id="4f7f6-144">Pole **Objętość** jest obliczane automatycznie na podstawie ustawień **głębokości**, **wysokości** i **szerokości**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-144">The **Volume** field is automatically calculated based on your **Depth**, **Height**, and **Width** settings.</span></span>

#### <a name="create-a-new-container-type"></a><span data-ttu-id="4f7f6-145">Tworzenie nowego typu kontenera</span><span class="sxs-lookup"><span data-stu-id="4f7f6-145">Create a new container type</span></span>

<span data-ttu-id="4f7f6-146">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Typy kontenerów** i utwórz nowy rekord z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="4f7f6-146">Go to **Warehouse management \> Setup \> Containers \> Container types** and create a new record with the following settings:</span></span>

- <span data-ttu-id="4f7f6-147">**Kod typu kontenera** - *Pudełko krótkie*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-147">**Container type code** - *Short Box*</span></span>
- <span data-ttu-id="4f7f6-148">**Opis** - *Pudełko krótkie*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-148">**Description** - *Short Box*</span></span>
- <span data-ttu-id="4f7f6-149">**Maksymalna waga netto** - *50*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-149">**Maximum net weight** - *50*</span></span>
- <span data-ttu-id="4f7f6-150">**Objętość** - *144*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-150">**Volume** - *144*</span></span>
- <span data-ttu-id="4f7f6-151">**Długość** - *6*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-151">**Length** - *6*</span></span>
- <span data-ttu-id="4f7f6-152">**Szerokość** - *6*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-152">**Width** - *6*</span></span>
- <span data-ttu-id="4f7f6-153">**Wysokość** - *4*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-153">**Height** - *4*</span></span>

#### <a name="create-a-container-group"></a><span data-ttu-id="4f7f6-154">Tworzenie grupy kontenerów</span><span class="sxs-lookup"><span data-stu-id="4f7f6-154">Create a container group</span></span>

<span data-ttu-id="4f7f6-155">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Grupy kontenerów** i utwórz nowy rekord z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="4f7f6-155">Go to **Warehouse management \> Setup \> Containers \> Container groups** and create a new record with the following settings:</span></span>

- <span data-ttu-id="4f7f6-156">**Identyfikator grupy kontenerów** - *Pudełko krótkie*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-156">**Container group ID** - *Short Box*</span></span>
- <span data-ttu-id="4f7f6-157">**Opis** - *Pudełko krótkie*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-157">**Description** - *Short Box*</span></span>

<span data-ttu-id="4f7f6-158">Dodaj nowy wiersz do sekcji **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-158">Add a new line to the **Details** section.</span></span> <span data-ttu-id="4f7f6-159">Ustaw **typ kontenera** na *Pudełko krótkie*.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-159">Set the **Container type** to *Short Box*.</span></span>

#### <a name="set-up-a-container-build-template"></a><span data-ttu-id="4f7f6-160">Ustawianie szablonu kompilacji kontenera</span><span class="sxs-lookup"><span data-stu-id="4f7f6-160">Set up a container build template</span></span>

<span data-ttu-id="4f7f6-161">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Szablony kompilacji kontenerów** i wybierz pozycję **Pudełka**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-161">Go to **Warehouse management \> Setup \> Containers \> Container build templates** and select **Boxes**.</span></span> <span data-ttu-id="4f7f6-162">Zmień **identyfikator grupy kontenerów** na *Pudełko krótkie*.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-162">Change the **Container group ID** to *Short Box*.</span></span>

### <a name="run-the-scenario"></a><span data-ttu-id="4f7f6-163">Uruchamianie scenariusza</span><span class="sxs-lookup"><span data-stu-id="4f7f6-163">Run the scenario</span></span>

<span data-ttu-id="4f7f6-164">Po przygotowaniu systemu zgodnie z opisem w poprzedniej sekcji można rozpocząć scenariusz opisany w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-164">After you have prepared your system as described in the previous section, you are ready to run the scenario as described in the next section.</span></span>

#### <a name="create-a-sales-order-and-create-a-shipment"></a><span data-ttu-id="4f7f6-165">Tworzenie zamówienia sprzedaży i tworzenie wysyłki</span><span class="sxs-lookup"><span data-stu-id="4f7f6-165">Create a sales order and create a shipment</span></span>

<span data-ttu-id="4f7f6-166">W tym procesie można utworzyć wysyłkę na podstawie wymiarów *pakowania* towarów, dla których wysokość jest mniejsza niż 3.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-166">In this process you will create a shipment based on the item *packing* dimensions, for which the height is less than 3.</span></span>

1. <span data-ttu-id="4f7f6-167">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-167">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="4f7f6-168">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-168">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="4f7f6-169">W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="4f7f6-169">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="4f7f6-170">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4f7f6-171">**Magazyn:** *63*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-171">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="4f7f6-172">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-172">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="4f7f6-173">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-173">The new sales order is opened.</span></span> <span data-ttu-id="4f7f6-174">Powinno zawierać pusty wiersz w siatce na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-174">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="4f7f6-175">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="4f7f6-175">On this line, set the following values:</span></span>

    - <span data-ttu-id="4f7f6-176">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-176">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="4f7f6-177">**Ilość:** *5*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-177">**Quantity:** *5*</span></span>

1. <span data-ttu-id="4f7f6-178">Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-178">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="4f7f6-179">Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-179">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="4f7f6-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-180">Close the page.</span></span>
1. <span data-ttu-id="4f7f6-181">W okienku akcji otwórz kartę **Magazyn** i wybierz pozycję **Zwolnij do magazynu**, aby utworzyć pracę dla magazynu.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-181">On the Action Pane, open the **Warehouse** tab and select **Release to warehouse** to create work for the warehouse.</span></span>
1. <span data-ttu-id="4f7f6-182">Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Magazyn \> Szczegóły wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-182">On the **Sales order lines** FastTab, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="4f7f6-183">W okienku akcji otwórz kartę **Transport** i wybierz opcję **Wyświetl kontenery**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-183">On the Action Pane, open the **Transportation** tab and select **View containers**.</span></span> <span data-ttu-id="4f7f6-184">Potwierdź, że towar został przeniesiony do dwóch kontenerów *Pudełko krótkie*.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-184">Confirm that the item was containerized into the two *Short Box* containers.</span></span>

#### <a name="place-an-item-into-storage"></a><span data-ttu-id="4f7f6-185">Umieszczanie pozycji w magazynie</span><span class="sxs-lookup"><span data-stu-id="4f7f6-185">Place an item into storage</span></span>

1. <span data-ttu-id="4f7f6-186">Otwórz urządzenie przenośne, zaloguj się do magazynu 63 i przejdź do pozycji **Zapasy \> Dostosuj w**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-186">Open the mobile device, sign in to warehouse 63 and go to **Inventory \> Adjust In**.</span></span>
1. <span data-ttu-id="4f7f6-187">Wprowadź **lokalizację** = *SHORT-01*.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-187">Enter **Loc** = *SHORT-01*.</span></span> <span data-ttu-id="4f7f6-188">Utwórz nowy numer identyfikacyjny z **pozycją** = *A0001* i **ilością** = *1 szt.*</span><span class="sxs-lookup"><span data-stu-id="4f7f6-188">Make a new license plate with **Item** = *A0001* and **Quantity** = *1 pcs*.</span></span>
1. <span data-ttu-id="4f7f6-189">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-189">Select **OK**.</span></span> <span data-ttu-id="4f7f6-190">Pojawi się błąd „Niepowodzenie lokalizacji SHORT-01, pozycja A0001 nie pasuje do wymiarów określonych dla lokalizacji”.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-190">You will receive the error "Location SHORT-01 failed because item A0001 does not fit in location's specified dimensions."</span></span> <span data-ttu-id="4f7f6-191">Wynika to z tego, że wymiary typu *Magazyn* są większe niż wymiary określone w profilu lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="4f7f6-191">This is because the *Storage* type dimensions of the product are larger than the dimensions specified on the location profile.</span></span>
