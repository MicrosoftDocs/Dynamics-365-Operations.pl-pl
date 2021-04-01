---
title: Konsolidowanie wysyłek przy użyciu polecenia Zwolnij do magazynu z pulpitu planowania wysyłki ładunku
description: W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu w ramach tego samego ładunku, a następnie automatycznie konsolidowanych w ramach wysyłek.
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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 2fd13c2ceb8843b79b9dbc87acf77f219f0244f5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5242260"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a><span data-ttu-id="020ed-103">Konsolidowanie wysyłek przy użyciu polecenia Zwolnij do magazynu z pulpitu planowania wysyłki ładunku</span><span class="sxs-lookup"><span data-stu-id="020ed-103">Consolidate shipments by using Release to warehouse from the load planning workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="020ed-104">W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu w ramach tego samego ładunku, a następnie automatycznie konsolidowanych w ramach wysyłek.</span><span class="sxs-lookup"><span data-stu-id="020ed-104">This topic presents a scenario where multiple orders are released to the warehouse in the same load and are then automatically consolidated into shipments.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="020ed-105">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="020ed-105">Make demo data available</span></span>

<span data-ttu-id="020ed-106">Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="020ed-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="020ed-107">Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.</span><span class="sxs-lookup"><span data-stu-id="020ed-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="020ed-108">Konfigurowanie zasad konsolidacji wysyłki i filtrów produktów</span><span class="sxs-lookup"><span data-stu-id="020ed-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="020ed-109">W opisanym poniżej scenariuszu przyjęto założenie, że użytkownik już włączył funkcję, wykonał ćwiczenia z tematu [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md) i utworzył zasady oraz inne opisane w nim rekordy.</span><span class="sxs-lookup"><span data-stu-id="020ed-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="020ed-110">Przed kontynuowaniem tego scenariusza pamiętaj o wykonaniu poniższych ćwiczeń.</span><span class="sxs-lookup"><span data-stu-id="020ed-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="020ed-111">Tworzenie zamówień sprzedaży dla tego scenariusza</span><span class="sxs-lookup"><span data-stu-id="020ed-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="020ed-112">Rozpocznij od utworzenia kolekcji zamówień sprzedaży, z którymi możesz pracować.</span><span class="sxs-lookup"><span data-stu-id="020ed-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="020ed-113">Musisz pracować z magazynem, w którym włączono obsługę zaawansowanych procesów magazynu (WMS).</span><span class="sxs-lookup"><span data-stu-id="020ed-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="020ed-114">O ile inny magazyn nie został wyraźnie wskazany, ten sam magazyn musi być używany dla każdego z poniższych zestawów zamówień.</span><span class="sxs-lookup"><span data-stu-id="020ed-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="020ed-115">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży** i utwórz kolekcję zamówień sprzedaży z ustawieniami opisanymi w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="020ed-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="020ed-116">Tworzenie zestawu zamówień 1</span><span class="sxs-lookup"><span data-stu-id="020ed-116">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="020ed-117">Zamówienie sprzedaży 1-1</span><span class="sxs-lookup"><span data-stu-id="020ed-117">Sales order 1-1</span></span>

1. <span data-ttu-id="020ed-118">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-118">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="020ed-119">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="020ed-119">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="020ed-120">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="020ed-120">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="020ed-121">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-121">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-122">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-122">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-123">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-123">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-124">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-124">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="020ed-125">Zamówienie sprzedaży 1-2</span><span class="sxs-lookup"><span data-stu-id="020ed-125">Sales order 1-2</span></span>

1. <span data-ttu-id="020ed-126">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-126">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="020ed-127">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="020ed-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="020ed-128">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="020ed-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="020ed-129">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-130">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-131">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-132">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="020ed-133">Zamówienie sprzedaży 1-3</span><span class="sxs-lookup"><span data-stu-id="020ed-133">Sales order 1-3</span></span>

1. <span data-ttu-id="020ed-134">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="020ed-135">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="020ed-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="020ed-136">**Metoda dostawy:** *10*</span><span class="sxs-lookup"><span data-stu-id="020ed-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="020ed-137">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-138">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-139">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-140">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="020ed-141">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-142">**Kod pozycji:** *A0002* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-143">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="020ed-144">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="020ed-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="020ed-145">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować drugi wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="020ed-146">Tworzenie zestawu zamówień 2</span><span class="sxs-lookup"><span data-stu-id="020ed-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="020ed-147">Zamówienia sprzedaży 2-1 i 2-2</span><span class="sxs-lookup"><span data-stu-id="020ed-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="020ed-148">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="020ed-149">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="020ed-149">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="020ed-150">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-150">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-151">**Kod pozycji:** *M9200* (pozycja, dla której filtr **Kod 4** został ustawiony na *Łatwopalne*)</span><span class="sxs-lookup"><span data-stu-id="020ed-151">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="020ed-152">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-152">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-153">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-153">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="020ed-154">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-154">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-155">**Kod pozycji:** *M9201* (pozycja, dla której filtr **Kod 4** został ustawiony na *Materiały wybuchowe*)</span><span class="sxs-lookup"><span data-stu-id="020ed-155">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="020ed-156">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-156">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="020ed-157">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="020ed-157">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="020ed-158">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować drugi wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-158">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="020ed-159">Tworzenie zestawu zamówień 3</span><span class="sxs-lookup"><span data-stu-id="020ed-159">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="020ed-160">Zamówienia sprzedaży 3-1 i 3-2</span><span class="sxs-lookup"><span data-stu-id="020ed-160">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="020ed-161">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-161">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="020ed-162">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="020ed-162">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="020ed-163">**Zapotrzebowanie odbiorcy:** *1*</span><span class="sxs-lookup"><span data-stu-id="020ed-163">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="020ed-164">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-164">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-165">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-165">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-166">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-166">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-167">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-167">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="020ed-168">Zamówienia sprzedaży 3-3 i 3-4</span><span class="sxs-lookup"><span data-stu-id="020ed-168">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="020ed-169">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-169">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="020ed-170">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="020ed-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="020ed-171">**Zapotrzebowanie odbiorcy:** *2*</span><span class="sxs-lookup"><span data-stu-id="020ed-171">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="020ed-172">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-172">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-173">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-173">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-174">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-174">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-175">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-175">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="020ed-176">Tworzenie zestawu zamówień 4</span><span class="sxs-lookup"><span data-stu-id="020ed-176">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="020ed-177">Zamówienia sprzedaży 4-1 i 4-2</span><span class="sxs-lookup"><span data-stu-id="020ed-177">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="020ed-178">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-178">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="020ed-179">**Konto odbiorcy:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="020ed-179">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="020ed-180">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-180">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-181">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-181">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-182">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-182">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-183">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-183">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="020ed-184">Zamówienia sprzedaży 4-3 i 4-4</span><span class="sxs-lookup"><span data-stu-id="020ed-184">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="020ed-185">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-185">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="020ed-186">**Konto odbiorcy:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="020ed-186">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="020ed-187">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-187">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-188">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-188">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-189">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-189">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-190">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-190">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="020ed-191">Zamówienia sprzedaży 4-5 i 4-6</span><span class="sxs-lookup"><span data-stu-id="020ed-191">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="020ed-192">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-192">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="020ed-193">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="020ed-193">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="020ed-194">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="020ed-194">**Site:** *6*</span></span>
    - <span data-ttu-id="020ed-195">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="020ed-195">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="020ed-196">**Pula:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="020ed-196">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="020ed-197">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-198">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-199">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-199">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-200">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-200">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="020ed-201">Zamówienia sprzedaży 4-7 i 4-8</span><span class="sxs-lookup"><span data-stu-id="020ed-201">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="020ed-202">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-202">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="020ed-203">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="020ed-203">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="020ed-204">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="020ed-204">**Site:** *6*</span></span>
    - <span data-ttu-id="020ed-205">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="020ed-205">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="020ed-206">**Pula:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="020ed-206">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="020ed-207">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="020ed-207">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="020ed-208">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="020ed-208">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="020ed-209">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="020ed-209">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="020ed-210">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="020ed-210">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a><span data-ttu-id="020ed-211">Tworzenie ładunków i zwalnianie ich do magazynu przy użyciu pulpitu planowania wysyłki ładunku</span><span class="sxs-lookup"><span data-stu-id="020ed-211">Use the load planning workbench to create loads and release them to the warehouse</span></span>

<span data-ttu-id="020ed-212">Wykonaj poniższe kroki, aby utworzyć ładunek dla każdego zestawu zamówień utworzonego dla tego scenariusza, a następnie zwolnić go do magazynu.</span><span class="sxs-lookup"><span data-stu-id="020ed-212">Follow these steps to create a load for each order set that you created for this scenario and then release it to the warehouse.</span></span>

1. <span data-ttu-id="020ed-213">Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.</span><span class="sxs-lookup"><span data-stu-id="020ed-213">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="020ed-214">Na karcie **Wiersze sprzedaży** znajdź i wybierz wszystkie wiersze zamówienia sprzedaży w jednym z zestawów zamówień utworzonych dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="020ed-214">On the **Sales lines** tab, find and select all the sales order lines from one of the order sets that you created for this scenario.</span></span>
1. <span data-ttu-id="020ed-215">W okienku akcji na karcie **Popyt i podaż** wybierz pozycję **Dodaj \> Do nowego ładunku**, aby dodać wybrane wiersze zamówienia do nowego ładunku.</span><span class="sxs-lookup"><span data-stu-id="020ed-215">On the Action Pane, on the **Supply and demand** tab, select **Add \> To new load** to add the selected order lines to a new Load.</span></span>
1. <span data-ttu-id="020ed-216">W oknie dialogowym **Przypisanie szablonu ładunku** w polu **Identyfikator szablonu ładunku** wybierz szablon ładunku, na przykład *Standardowy szablon ładunku*.</span><span class="sxs-lookup"><span data-stu-id="020ed-216">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *Stnd Load Template*.</span></span>
1. <span data-ttu-id="020ed-217">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="020ed-217">Select **OK** to close the dialog box.</span></span> 
1. <span data-ttu-id="020ed-218">W sekcji **Ładunki** znajdź i wybierz właśnie utworzony ładunek.</span><span class="sxs-lookup"><span data-stu-id="020ed-218">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="020ed-219">Wybierz pozycję **Zwolnij \> Zwolnij do magazynu**, aby zwolnić wybrany ładunek do magazynu.</span><span class="sxs-lookup"><span data-stu-id="020ed-219">Select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="020ed-220">Powtórz tę procedurę dla trzech pozostałych zestawów zamówień utworzonych dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="020ed-220">Repeat this procedure for the other three order sets that you created for this scenario.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="020ed-221">Weryfikowanie wysyłek</span><span class="sxs-lookup"><span data-stu-id="020ed-221">Verify the shipments</span></span>

<span data-ttu-id="020ed-222">Poniższa procedura umożliwia zweryfikowanie, czy wysyłki zostały utworzone lub zaktualizowane w wyniku konsolidacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="020ed-222">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="020ed-223">Przy jej użyciu można przejrzeć wszystkie zestawy zamówień utworzone dla tego scenariusza, a następnie przejrzeć kolejne podsekcje, aby upewnić się, że otrzymano oczekiwane wyniki.</span><span class="sxs-lookup"><span data-stu-id="020ed-223">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="020ed-224">Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="020ed-224">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="020ed-225">Znajdź i wybierz wymaganą wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="020ed-225">Find and select the required shipment.</span></span>
1. <span data-ttu-id="020ed-226">Jeśli podczas tworzenia lub aktualizowania wysyłki użyto zasad konsolidacji, powinny być one widoczne w polu **Zasady konsolidacji wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="020ed-226">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-order-set-1-in-one-load"></a><span data-ttu-id="020ed-227">Zwalnianie zestawu zamówień 1 w jednym ładunku</span><span class="sxs-lookup"><span data-stu-id="020ed-227">Release order set 1 in one load</span></span>

<span data-ttu-id="020ed-228">Powinny zostać utworzone dwie następujące wysyłki:</span><span class="sxs-lookup"><span data-stu-id="020ed-228">Two shipments should have been created:</span></span>

- <span data-ttu-id="020ed-229">Pierwsza wysyłka zawiera trzy wiersze i została utworzona za pomocą zasad konsolidacji wysyłki *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="020ed-229">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="020ed-230">Druga wysyłka, która nie korzysta z metody dostawy *Trasy lotnicze*, została utworzona przy użyciu zasad konsolidacji wysyłki *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="020ed-230">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-order-set-2-in-one-load"></a><span data-ttu-id="020ed-231">Zwalnianie zestawu zamówień 2 w jednym ładunku</span><span class="sxs-lookup"><span data-stu-id="020ed-231">Release order set 2 in one load</span></span>

<span data-ttu-id="020ed-232">Powinny zostać utworzone trzy następujące wysyłki:</span><span class="sxs-lookup"><span data-stu-id="020ed-232">Three shipments should have been created:</span></span>

- <span data-ttu-id="020ed-233">Pierwsza wysyłka zawiera pozycję typu *Łatwopalne*.</span><span class="sxs-lookup"><span data-stu-id="020ed-233">The first shipment contains the *Flammable* items.</span></span>
- <span data-ttu-id="020ed-234">Każda z dwóch pozostałych wysyłek zawiera jeden wiersz pozycji typu *Materiały wybuchowe*.</span><span class="sxs-lookup"><span data-stu-id="020ed-234">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-order-set-3-in-one-load"></a><span data-ttu-id="020ed-235">Zwalnianie zestawu zamówień 3 w jednym ładunku</span><span class="sxs-lookup"><span data-stu-id="020ed-235">Release order set 3 in one load</span></span>

<span data-ttu-id="020ed-236">Powinny zostać utworzone dwie następujące wysyłki:</span><span class="sxs-lookup"><span data-stu-id="020ed-236">Two shipments should have been created:</span></span>

- <span data-ttu-id="020ed-237">Pierwsza wysyłka zawiera wiersze zamówienia z zamówienia sprzedaży, w którym pole **Zapotrzebowanie odbiorcy** zostało ustawione na wartość *1*.</span><span class="sxs-lookup"><span data-stu-id="020ed-237">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="020ed-238">Druga wysyłka zawiera wiersze zamówienia z zamówienia sprzedaży, w którym pole **Zapotrzebowanie odbiorcy** zostało ustawione na wartość *2*.</span><span class="sxs-lookup"><span data-stu-id="020ed-238">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="release-order-set-4-in-one-load"></a><span data-ttu-id="020ed-239">Zwalnianie zestawu zamówień 4 w jednym ładunku</span><span class="sxs-lookup"><span data-stu-id="020ed-239">Release order set 4 in one load</span></span>

<span data-ttu-id="020ed-240">Powinny zostać utworzone cztery następujące wysyłki:</span><span class="sxs-lookup"><span data-stu-id="020ed-240">Four shipments should have been created:</span></span>

- <span data-ttu-id="020ed-241">Wiersze z dwóch zamówień dla konta odbiorcy *US-003* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="020ed-241">Lines from two orders for customer account *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="020ed-242">Wiersze z dwóch zamówień dla konta odbiorcy *US-004* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="020ed-242">Lines from two orders for customer account *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="020ed-243">Wiersze z zamówień sprzedaży 4-5 i 4-6 dla konta odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="020ed-243">Lines from sales orders 4-5 and 4-6 for customer account *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="020ed-244">Wiersze z zamówień sprzedaży 4-7 i 4-8 dla konta odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="020ed-244">Lines from sales orders 4-7 and 4-8 for customer account *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="020ed-245">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="020ed-245">Additional resources</span></span>

- [<span data-ttu-id="020ed-246">Zasady konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="020ed-246">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="020ed-247">Konfigurowanie zasad konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="020ed-247">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]