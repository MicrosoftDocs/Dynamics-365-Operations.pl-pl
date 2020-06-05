---
title: Konsolidowanie wysyłek przy użyciu pulpitu konsolidacji wysyłki
description: W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu, a później konsolidowanych w ramach wysyłek przy użyciu pulpitu konsolidacji wysyłki.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b1a2c9506b4444fc98a9e4f0389cbd69db4ce052
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383841"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="315fa-103">Konsolidowanie wysyłek przy użyciu pulpitu konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="315fa-103">Consolidate shipments by using the shipment consolidation workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="315fa-104">W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu, a później konsolidowanych w ramach wysyłek przy użyciu pulpitu konsolidacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="315fa-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated into shipments later by using the shipment consolidation workbench.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="315fa-105">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="315fa-105">Make demo data available</span></span>

<span data-ttu-id="315fa-106">Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="315fa-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="315fa-107">Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.</span><span class="sxs-lookup"><span data-stu-id="315fa-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="315fa-108">Konfigurowanie zasad konsolidacji wysyłki i filtrów produktów</span><span class="sxs-lookup"><span data-stu-id="315fa-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="315fa-109">W opisanym poniżej scenariuszu przyjęto założenie, że użytkownik już włączył funkcję, wykonał ćwiczenia z tematu [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md) i utworzył zasady oraz inne opisane w nim rekordy.</span><span class="sxs-lookup"><span data-stu-id="315fa-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="315fa-110">Przed kontynuowaniem tego scenariusza pamiętaj o wykonaniu poniższych ćwiczeń.</span><span class="sxs-lookup"><span data-stu-id="315fa-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a><span data-ttu-id="315fa-111">Włączanie funkcji ręcznej konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="315fa-111">Turn on the manual shipment consolidation feature</span></span>

<span data-ttu-id="315fa-112">Aby można było skorzystać z funkcji *ręcznej konsolidacji wysyłki*, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="315fa-112">Before you can use the *Manual shipment consolidation* feature, you must turn it on in your system.</span></span> <span data-ttu-id="315fa-113">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją.</span><span class="sxs-lookup"><span data-stu-id="315fa-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="315fa-114">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="315fa-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="315fa-115">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="315fa-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="315fa-116">**Nazwa funkcji:** *Ręczna konsolidacja wysyłki*</span><span class="sxs-lookup"><span data-stu-id="315fa-116">**Feature name:** *Manual shipment consolidation*</span></span>

<span data-ttu-id="315fa-117">Jak wspomniano w temacie [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md), przed rozpoczęciem tworzenia zasad należy również włączyć funkcję *konsolidowania wysyłki*.</span><span class="sxs-lookup"><span data-stu-id="315fa-117">As was mentioned in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), you must also turn on the *Consolidate shipment* feature before you can create policies.</span></span> <span data-ttu-id="315fa-118">Ten krok został już jednak prawdopodobnie wykonany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="315fa-118">However, you should already have completed that step.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="315fa-119">Tworzenie zamówień sprzedaży dla tego scenariusza</span><span class="sxs-lookup"><span data-stu-id="315fa-119">Create the sales orders for this scenario</span></span>

<span data-ttu-id="315fa-120">Rozpocznij od utworzenia kolekcji zamówień sprzedaży, z którymi możesz pracować.</span><span class="sxs-lookup"><span data-stu-id="315fa-120">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="315fa-121">Musisz pracować z magazynem, w którym włączono obsługę zaawansowanych procesów magazynu (WMS).</span><span class="sxs-lookup"><span data-stu-id="315fa-121">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="315fa-122">O ile inny magazyn nie został wyraźnie wskazany, ten sam magazyn musi być używany dla każdego z poniższych zestawów zamówień.</span><span class="sxs-lookup"><span data-stu-id="315fa-122">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="315fa-123">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży** i utwórz kolekcję zamówień sprzedaży z ustawieniami opisanymi w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="315fa-123">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="315fa-124">Tworzenie zestawu zamówień 1</span><span class="sxs-lookup"><span data-stu-id="315fa-124">Create order set 1</span></span>

#### <a name="sales-orders-1-1-and-1-2"></a><span data-ttu-id="315fa-125">Zamówienia sprzedaży 1-1 i 1-2</span><span class="sxs-lookup"><span data-stu-id="315fa-125">Sales orders 1-1 and 1-2</span></span>

1. <span data-ttu-id="315fa-126">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-126">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="315fa-127">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="315fa-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="315fa-128">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="315fa-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="315fa-129">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-130">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="315fa-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="315fa-131">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="315fa-132">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="315fa-133">Zamówienie sprzedaży 1-3</span><span class="sxs-lookup"><span data-stu-id="315fa-133">Sales order 1-3</span></span>

1. <span data-ttu-id="315fa-134">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="315fa-135">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="315fa-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="315fa-136">**Metoda dostawy:** *10*</span><span class="sxs-lookup"><span data-stu-id="315fa-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="315fa-137">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-138">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="315fa-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="315fa-139">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="315fa-140">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="315fa-141">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-142">**Kod pozycji:** *A0002* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="315fa-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="315fa-143">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="315fa-144">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="315fa-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="315fa-145">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować drugi wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="315fa-146">Tworzenie zestawu zamówień 2</span><span class="sxs-lookup"><span data-stu-id="315fa-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="315fa-147">Zamówienia sprzedaży 2-1 i 2-2</span><span class="sxs-lookup"><span data-stu-id="315fa-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="315fa-148">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="315fa-149">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="315fa-149">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="315fa-150">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="315fa-150">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="315fa-151">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-151">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-152">**Kod pozycji:** *M9200* (pozycja, dla której filtr **Kod 4** został ustawiony na *Łatwopalne*)</span><span class="sxs-lookup"><span data-stu-id="315fa-152">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="315fa-153">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-153">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="315fa-154">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-154">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="315fa-155">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-155">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-156">**Kod pozycji:** *M9201* (pozycja, dla której filtr **Kod 4** został ustawiony na *Materiały wybuchowe*)</span><span class="sxs-lookup"><span data-stu-id="315fa-156">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="315fa-157">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-157">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="315fa-158">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="315fa-158">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="315fa-159">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować drugi wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-159">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="315fa-160">Tworzenie zestawu zamówień 3</span><span class="sxs-lookup"><span data-stu-id="315fa-160">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="315fa-161">Zamówienia sprzedaży 3-1 i 3-2</span><span class="sxs-lookup"><span data-stu-id="315fa-161">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="315fa-162">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-162">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="315fa-163">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="315fa-163">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="315fa-164">**Zapotrzebowanie odbiorcy:** *1*</span><span class="sxs-lookup"><span data-stu-id="315fa-164">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="315fa-165">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-165">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-166">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="315fa-166">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="315fa-167">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-167">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="315fa-168">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-168">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="315fa-169">Zamówienia sprzedaży 3-3 i 3-4</span><span class="sxs-lookup"><span data-stu-id="315fa-169">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="315fa-170">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-170">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="315fa-171">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="315fa-171">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="315fa-172">**Zapotrzebowanie odbiorcy:** *2*</span><span class="sxs-lookup"><span data-stu-id="315fa-172">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="315fa-173">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-173">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-174">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="315fa-174">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="315fa-175">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-175">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="315fa-176">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-176">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="315fa-177">Tworzenie zestawu zamówień 4</span><span class="sxs-lookup"><span data-stu-id="315fa-177">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="315fa-178">Zamówienia sprzedaży 4-1 i 4-2</span><span class="sxs-lookup"><span data-stu-id="315fa-178">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="315fa-179">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="315fa-180">**Konto odbiorcy:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="315fa-180">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="315fa-181">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-181">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-182">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="315fa-182">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="315fa-183">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-183">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="315fa-184">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-184">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="315fa-185">Zamówienia sprzedaży 4-3 i 4-4</span><span class="sxs-lookup"><span data-stu-id="315fa-185">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="315fa-186">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-186">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="315fa-187">**Konto odbiorcy:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="315fa-187">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="315fa-188">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-188">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-189">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="315fa-189">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="315fa-190">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-190">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="315fa-191">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-191">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="315fa-192">Zamówienia sprzedaży 4-5 i 4-6</span><span class="sxs-lookup"><span data-stu-id="315fa-192">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="315fa-193">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-193">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="315fa-194">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="315fa-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="315fa-195">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="315fa-195">**Site:** *6*</span></span>
    - <span data-ttu-id="315fa-196">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="315fa-196">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="315fa-197">**Pula:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="315fa-197">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="315fa-198">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-198">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-199">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="315fa-199">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="315fa-200">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-200">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="315fa-201">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-201">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="315fa-202">Zamówienia sprzedaży 4-7 i 4-8</span><span class="sxs-lookup"><span data-stu-id="315fa-202">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="315fa-203">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-203">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="315fa-204">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="315fa-204">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="315fa-205">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="315fa-205">**Site:** *6*</span></span>
    - <span data-ttu-id="315fa-206">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="315fa-206">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="315fa-207">**Pula:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="315fa-207">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="315fa-208">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="315fa-208">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="315fa-209">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="315fa-209">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="315fa-210">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="315fa-210">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="315fa-211">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-211">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="315fa-212">Zwalnianie zamówień do magazynu</span><span class="sxs-lookup"><span data-stu-id="315fa-212">Release the orders to the warehouse</span></span>

<span data-ttu-id="315fa-213">Wykonaj poniższe kroki, aby zwolnić każde zamówienie sprzedaży utworzone dla tego scenariusza do magazynu.</span><span class="sxs-lookup"><span data-stu-id="315fa-213">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="315fa-214">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="315fa-214">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="315fa-215">Znajdź i zaznacz zamówienie sprzedaży do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="315fa-215">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="315fa-216">W okienku akcji na karcie **Magazyn** wybierz pozycję **Akcje \> Zwolnij do magazynu**, aby zwolnić wybrane zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="315fa-216">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="315fa-217">Powtórz tę procedurę dla wszystkich zamówień sprzedaży utworzonych dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="315fa-217">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="315fa-218">Konsolidowanie wysyłek przy użyciu pulpitu konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="315fa-218">Consolidate the shipments by using the shipment consolidation workbench</span></span>

1. <span data-ttu-id="315fa-219">Przejdź do pozycji **Zarządzanie magazynem \> Zwolnij do magazynu \> Pulpit konsolidacji wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="315fa-219">Go to **Warehouse management \> Release to warehouse \> Shipment consolidation workbench**.</span></span>
1. <span data-ttu-id="315fa-220">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="315fa-220">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="315fa-221">W oknie dialogowym edytora zapytań na karcie **Zakres** wybierz przycisk **Dodaj**, aby dodać wiersz zawierający następujące ustawienia do siatki:</span><span class="sxs-lookup"><span data-stu-id="315fa-221">In the query editor dialog box, on the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="315fa-222">**Tabela:** *Zamówienia sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="315fa-222">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="315fa-223">**Pole:** *Zamówienie sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="315fa-223">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="315fa-224">**Kryteria:** wprowadź rozdzielaną przecinkami listę numerów zamówień sprzedaży dla poszczególnych zestawów zamówień utworzonych dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="315fa-224">**Criteria:** Enter a comma-separated list of the sales order numbers for each order set that you created for this scenario.</span></span>

1. <span data-ttu-id="315fa-225">Wybierz przycisk **OK**, aby zapisać zapytanie i zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="315fa-225">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="315fa-226">W okienku akcji wybierz pozycję **Konsoliduj wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="315fa-226">On the Action Pane, select **Consolidate shipments**.</span></span>
1. <span data-ttu-id="315fa-227">Wybierz wszystkie wysyłki, a następnie w okienku akcji wybierz pozycję **Konsoliduj**.</span><span class="sxs-lookup"><span data-stu-id="315fa-227">Select all the shipments, and then, on the Action Pane, select **Consolidate**.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="315fa-228">Weryfikowanie wysyłek</span><span class="sxs-lookup"><span data-stu-id="315fa-228">Verify the shipments</span></span>

<span data-ttu-id="315fa-229">Poniższa procedura umożliwia zweryfikowanie, czy wysyłki zostały utworzone lub zaktualizowane w wyniku konsolidacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="315fa-229">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="315fa-230">Przy jej użyciu można przejrzeć wszystkie zestawy zamówień utworzone dla tego scenariusza, a następnie przejrzeć kolejne podsekcje, aby upewnić się, że otrzymano oczekiwane wyniki.</span><span class="sxs-lookup"><span data-stu-id="315fa-230">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="315fa-231">Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="315fa-231">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="315fa-232">Znajdź i wybierz wymaganą wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="315fa-232">Find and select the required shipment.</span></span>
1. <span data-ttu-id="315fa-233">Jeśli podczas tworzenia lub aktualizowania wysyłki użyto zasad konsolidacji, powinny być one widoczne w polu **Zasady konsolidacji wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="315fa-233">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="related-shipments-for-order-set-1"></a><span data-ttu-id="315fa-234">Powiązane wysyłki dla zestawu zamówień 1</span><span class="sxs-lookup"><span data-stu-id="315fa-234">Related shipments for order set 1</span></span>

<span data-ttu-id="315fa-235">Powinny zostać utworzone dwie następujące wysyłki:</span><span class="sxs-lookup"><span data-stu-id="315fa-235">Two shipments should have been created:</span></span>

- <span data-ttu-id="315fa-236">Pierwsza wysyłka zawiera trzy wiersze i została utworzona za pomocą zasad konsolidacji wysyłki *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="315fa-236">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="315fa-237">Druga wysyłka, która nie korzysta z metody dostawy *Trasy lotnicze*, została utworzona przy użyciu zasad konsolidacji wysyłki *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="315fa-237">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="related-shipments-for-order-set-2"></a><span data-ttu-id="315fa-238">Powiązane wysyłki dla zestawu zamówień 2</span><span class="sxs-lookup"><span data-stu-id="315fa-238">Related shipments for order set 2</span></span>

<span data-ttu-id="315fa-239">Powinny zostać utworzone trzy następujące wysyłki:</span><span class="sxs-lookup"><span data-stu-id="315fa-239">Three shipments should have been created:</span></span>

- <span data-ttu-id="315fa-240">Pierwsza wysyłka zawiera pozycję typu *Łatwopalne*.</span><span class="sxs-lookup"><span data-stu-id="315fa-240">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="315fa-241">Każda z dwóch pozostałych wysyłek zawiera jeden wiersz pozycji typu *Materiały wybuchowe*.</span><span class="sxs-lookup"><span data-stu-id="315fa-241">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="related-shipments-for-order-set-3"></a><span data-ttu-id="315fa-242">Powiązane wysyłki dla zestawu zamówień 3</span><span class="sxs-lookup"><span data-stu-id="315fa-242">Related shipments for order set 3</span></span>

<span data-ttu-id="315fa-243">Powinny zostać utworzone dwie następujące wysyłki:</span><span class="sxs-lookup"><span data-stu-id="315fa-243">Two shipments should have been created:</span></span>

- <span data-ttu-id="315fa-244">Pierwsza wysyłka zawiera wiersze zamówienia z zamówienia sprzedaży, w którym pole **Zapotrzebowanie odbiorcy** zostało ustawione na wartość *1*.</span><span class="sxs-lookup"><span data-stu-id="315fa-244">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="315fa-245">Druga wysyłka zawiera wiersze zamówienia z zamówienia sprzedaży, w którym pole **Zapotrzebowanie odbiorcy** zostało ustawione na wartość *2*.</span><span class="sxs-lookup"><span data-stu-id="315fa-245">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="related-shipments-for-order-set-4"></a><span data-ttu-id="315fa-246">Powiązane wysyłki dla zestawu zamówień 4</span><span class="sxs-lookup"><span data-stu-id="315fa-246">Related shipments for order set 4</span></span>

<span data-ttu-id="315fa-247">Powinny zostać utworzone cztery następujące wysyłki:</span><span class="sxs-lookup"><span data-stu-id="315fa-247">Four shipments should have been created:</span></span>

- <span data-ttu-id="315fa-248">Wiersze z dwóch zamówień dla odbiorcy *US-003* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="315fa-248">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="315fa-249">Wiersze z dwóch zamówień dla odbiorcy *US-004* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="315fa-249">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="315fa-250">Wiersze z zamówień sprzedaży 4-5 i 4-6 dla odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="315fa-250">Lines from sales orders 4-5 and 4-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="315fa-251">Wiersze z zamówień sprzedaży 4-7 i 4-8 dla odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="315fa-251">Lines from sales orders 4-7 and 4-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="315fa-252">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="315fa-252">Additional resources</span></span>

- [<span data-ttu-id="315fa-253">Zasady konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="315fa-253">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="315fa-254">Konfigurowanie zasad konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="315fa-254">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
