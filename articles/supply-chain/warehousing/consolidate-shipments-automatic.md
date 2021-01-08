---
title: Konsolidowanie wysyłek podczas zwalniania ich do magazynu przy użyciu automatycznego zwalniania zamówień sprzedaży
description: W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu w ramach tej samej zautomatyzowanej okresowej procedury zwalniania do magazynu.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: ac3ab25dc1355ee15e1209950ff0f3b3933b7095
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435566"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a><span data-ttu-id="d6018-103">Konsolidowanie wysyłek podczas zwalniania ich do magazynu przy użyciu automatycznego zwalniania zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d6018-103">Consolidate shipments when they are released to the warehouse by using Automatic release of sales orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d6018-104">W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu w ramach tej samej zautomatyzowanej okresowej procedury zwalniania do magazynu.</span><span class="sxs-lookup"><span data-stu-id="d6018-104">This topic presents a scenario where multiple orders are released to the warehouse in the same automated release-to-warehouse periodic procedure.</span></span> <span data-ttu-id="d6018-105">Zamówienia będą automatycznie konsolidowane w wysyłki na podstawie reguł zdefiniowanych jako zasady konsolidacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="d6018-105">The orders will automatically be consolidated into shipments, based on rules that are defined as shipment consolidation policies.</span></span>

<span data-ttu-id="d6018-106">W tym scenariuszu utworzysz zestawy zamówień sprzedaży i zwolnisz poszczególne zestawy do magazynu.</span><span class="sxs-lookup"><span data-stu-id="d6018-106">During the scenario, you will create sets of sales orders and release each set to the warehouse.</span></span> <span data-ttu-id="d6018-107">Następnie przejrzysz wysyłki utworzone lub zaktualizowane podczas konsolidowania wysyłki na podstawie skonfigurowanych zasad.</span><span class="sxs-lookup"><span data-stu-id="d6018-107">You will then review the shipments that are created or updated during shipment consolidation, based on the configured policies.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="d6018-108">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="d6018-108">Make demo data available</span></span>

<span data-ttu-id="d6018-109">Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d6018-109">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d6018-110">Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.</span><span class="sxs-lookup"><span data-stu-id="d6018-110">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="d6018-111">Konfigurowanie zasad konsolidacji wysyłki i filtrów produktów</span><span class="sxs-lookup"><span data-stu-id="d6018-111">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="d6018-112">W opisanym poniżej scenariuszu przyjęto założenie, że użytkownik już włączył funkcję, wykonał ćwiczenia z tematu [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md) i utworzył zasady oraz inne opisane w nim rekordy.</span><span class="sxs-lookup"><span data-stu-id="d6018-112">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="d6018-113">Przed kontynuowaniem tego scenariusza pamiętaj o wykonaniu poniższych ćwiczeń.</span><span class="sxs-lookup"><span data-stu-id="d6018-113">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="d6018-114">Tworzenie zamówień sprzedaży dla tego scenariusza</span><span class="sxs-lookup"><span data-stu-id="d6018-114">Create the sales orders for this scenario</span></span>

<span data-ttu-id="d6018-115">Rozpocznij od utworzenia kolekcji zamówień sprzedaży, z którymi możesz pracować.</span><span class="sxs-lookup"><span data-stu-id="d6018-115">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="d6018-116">Musisz pracować z magazynem, w którym włączono obsługę zaawansowanych procesów magazynu (WMS).</span><span class="sxs-lookup"><span data-stu-id="d6018-116">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="d6018-117">O ile inny magazyn nie został wyraźnie wskazany, ten sam magazyn musi być używany dla każdego z poniższych zestawów zamówień.</span><span class="sxs-lookup"><span data-stu-id="d6018-117">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="d6018-118">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży** i utwórz kolekcję zamówień sprzedaży z ustawieniami opisanymi w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="d6018-118">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="d6018-119">Tworzenie zestawu zamówień 1</span><span class="sxs-lookup"><span data-stu-id="d6018-119">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="d6018-120">Zamówienie sprzedaży 1-1</span><span class="sxs-lookup"><span data-stu-id="d6018-120">Sales order 1-1</span></span>

1. <span data-ttu-id="d6018-121">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-121">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="d6018-122">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d6018-122">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d6018-123">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="d6018-123">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="d6018-124">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-124">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-125">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-125">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-126">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-126">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="d6018-127">Zamówienie sprzedaży 1-2</span><span class="sxs-lookup"><span data-stu-id="d6018-127">Sales order 1-2</span></span>

1. <span data-ttu-id="d6018-128">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-128">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="d6018-129">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d6018-129">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d6018-130">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="d6018-130">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="d6018-131">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-131">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-132">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-132">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-133">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-133">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="d6018-134">Zamówienie sprzedaży 1-3</span><span class="sxs-lookup"><span data-stu-id="d6018-134">Sales order 1-3</span></span>

1. <span data-ttu-id="d6018-135">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-135">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="d6018-136">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d6018-136">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d6018-137">**Metoda dostawy:** *10*</span><span class="sxs-lookup"><span data-stu-id="d6018-137">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="d6018-138">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-138">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-139">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-139">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-140">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-140">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d6018-141">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-142">**Kod pozycji:** *A0002* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-143">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="d6018-144">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="d6018-144">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="d6018-145">Tworzenie zestawu zamówień 2</span><span class="sxs-lookup"><span data-stu-id="d6018-145">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="d6018-146">Zamówienia sprzedaży 2-1 i 2-2</span><span class="sxs-lookup"><span data-stu-id="d6018-146">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="d6018-147">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-147">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d6018-148">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="d6018-148">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="d6018-149">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-149">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-150">**Kod pozycji:** *M9200* (pozycja, dla której filtr **Kod 4** został ustawiony na *Łatwopalne*)</span><span class="sxs-lookup"><span data-stu-id="d6018-150">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="d6018-151">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-151">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d6018-152">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-152">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-153">**Kod pozycji:** *M9201* (pozycja, dla której filtr **Kod 4** został ustawiony na *Materiały wybuchowe*)</span><span class="sxs-lookup"><span data-stu-id="d6018-153">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="d6018-154">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-154">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="d6018-155">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="d6018-155">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="d6018-156">Tworzenie zestawu zamówień 3</span><span class="sxs-lookup"><span data-stu-id="d6018-156">Create order set 3</span></span>

#### <a name="sales-order-3-1"></a><span data-ttu-id="d6018-157">Zamówienie sprzedaży 3-1</span><span class="sxs-lookup"><span data-stu-id="d6018-157">Sales order 3-1</span></span>

1. <span data-ttu-id="d6018-158">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-158">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="d6018-159">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="d6018-159">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="d6018-160">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-160">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-161">**Kod pozycji:** *M9200* (pozycja, dla której filtr **Kod 4** został ustawiony na *Łatwopalne*)</span><span class="sxs-lookup"><span data-stu-id="d6018-161">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="d6018-162">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-162">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d6018-163">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-163">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-164">**Kod pozycji:** *M9201* (pozycja, dla której filtr **Kod 4** został ustawiony na *Materiały wybuchowe*)</span><span class="sxs-lookup"><span data-stu-id="d6018-164">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="d6018-165">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-165">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="d6018-166">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="d6018-166">**Mode of delivery:** *Airwa-Air*</span></span>

> [!NOTE]
> <span data-ttu-id="d6018-167">To zamówienie jest identyczne jak dwa zamówienia utworzone dla zestawu zamówień 2.</span><span class="sxs-lookup"><span data-stu-id="d6018-167">This order is identical to the two orders that you created for order set 2.</span></span> <span data-ttu-id="d6018-168">Jest ono jednak wymienione jako oddzielny zestaw zamówień, ponieważ w tym scenariuszu zostanie zwolnione osobno w późniejszym czasie.</span><span class="sxs-lookup"><span data-stu-id="d6018-168">However, it's listed as its own order set because you will release it separately later in this scenario.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="d6018-169">Tworzenie zestawu zamówień 4</span><span class="sxs-lookup"><span data-stu-id="d6018-169">Create order set 4</span></span>

#### <a name="sales-order-4-1"></a><span data-ttu-id="d6018-170">Zamówienie sprzedaży 4-1</span><span class="sxs-lookup"><span data-stu-id="d6018-170">Sales order 4-1</span></span>

1. <span data-ttu-id="d6018-171">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-171">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="d6018-172">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d6018-172">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d6018-173">**Zapotrzebowanie odbiorcy:** *1*</span><span class="sxs-lookup"><span data-stu-id="d6018-173">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="d6018-174">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-174">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-175">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-175">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-176">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-176">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-5"></a><span data-ttu-id="d6018-177">Tworzenie zestawu zamówień 5</span><span class="sxs-lookup"><span data-stu-id="d6018-177">Create order set 5</span></span>

#### <a name="sales-orders-5-1-and-5-2"></a><span data-ttu-id="d6018-178">Zamówienia sprzedaży 5-1 i 5-2</span><span class="sxs-lookup"><span data-stu-id="d6018-178">Sales orders 5-1 and 5-2</span></span>

1. <span data-ttu-id="d6018-179">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d6018-180">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d6018-180">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d6018-181">**Zapotrzebowanie odbiorcy:** *2*</span><span class="sxs-lookup"><span data-stu-id="d6018-181">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="d6018-182">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-182">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-183">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-183">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-184">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-184">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-5-3"></a><span data-ttu-id="d6018-185">Zamówienie sprzedaży 5-3</span><span class="sxs-lookup"><span data-stu-id="d6018-185">Sales order 5-3</span></span>

1. <span data-ttu-id="d6018-186">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-186">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="d6018-187">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d6018-187">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d6018-188">**Zapotrzebowanie odbiorcy:** *1*</span><span class="sxs-lookup"><span data-stu-id="d6018-188">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="d6018-189">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-189">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-190">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-190">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-191">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-191">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-6"></a><span data-ttu-id="d6018-192">Tworzenie zestawu zamówień 6</span><span class="sxs-lookup"><span data-stu-id="d6018-192">Create order set 6</span></span>

#### <a name="sales-orders-6-1-and-6-2"></a><span data-ttu-id="d6018-193">Zamówienia sprzedaży 6-1 i 6-2</span><span class="sxs-lookup"><span data-stu-id="d6018-193">Sales orders 6-1 and 6-2</span></span>

1. <span data-ttu-id="d6018-194">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-194">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d6018-195">**Konto odbiorcy:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="d6018-195">**Customer account:** *US-003*</span></span>
    - <span data-ttu-id="d6018-196">**Zapotrzebowanie odbiorcy:** *2*</span><span class="sxs-lookup"><span data-stu-id="d6018-196">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="d6018-197">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-198">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-199">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-199">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-3-and-6-4"></a><span data-ttu-id="d6018-200">Zamówienia sprzedaży 6-3 i 6-4</span><span class="sxs-lookup"><span data-stu-id="d6018-200">Sales orders 6-3 and 6-4</span></span>

1. <span data-ttu-id="d6018-201">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-201">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d6018-202">**Konto odbiorcy:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="d6018-202">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="d6018-203">**Zapotrzebowanie odbiorcy:** *1*</span><span class="sxs-lookup"><span data-stu-id="d6018-203">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="d6018-204">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-204">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-205">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-205">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-206">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-206">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-5-and-6-6"></a><span data-ttu-id="d6018-207">Zamówienia sprzedaży 6-5 i 6-6</span><span class="sxs-lookup"><span data-stu-id="d6018-207">Sales orders 6-5 and 6-6</span></span>

1. <span data-ttu-id="d6018-208">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-208">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d6018-209">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="d6018-209">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="d6018-210">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="d6018-210">**Site:** *6*</span></span>
    - <span data-ttu-id="d6018-211">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="d6018-211">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="d6018-212">**Pula:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="d6018-212">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="d6018-213">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-213">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-214">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-214">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-215">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-215">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-7-and-6-8"></a><span data-ttu-id="d6018-216">Zamówienia sprzedaży 6-7 i 6-8</span><span class="sxs-lookup"><span data-stu-id="d6018-216">Sales orders 6-7 and 6-8</span></span>

1. <span data-ttu-id="d6018-217">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-217">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d6018-218">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="d6018-218">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="d6018-219">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="d6018-219">**Site:** *6*</span></span>
    - <span data-ttu-id="d6018-220">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="d6018-220">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="d6018-221">**Pula:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="d6018-221">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="d6018-222">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="d6018-222">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d6018-223">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="d6018-223">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d6018-224">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d6018-224">**Quantity:** *1.00*</span></span>

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a><span data-ttu-id="d6018-225">Automatyczne zwalnianie zamówień sprzedaży do magazynu</span><span class="sxs-lookup"><span data-stu-id="d6018-225">Automatic release of sales orders to the warehouse</span></span>

<span data-ttu-id="d6018-226">Dla każdego utworzonego wcześniej zestawu zamówień sprzedaży zostanie wykonana procedura automatycznego zwalniania do magazynu.</span><span class="sxs-lookup"><span data-stu-id="d6018-226">For each set of sales orders that you created earlier, you will complete a procedure for automatic release to the warehouse.</span></span> <span data-ttu-id="d6018-227">W każdym przypadku będziesz korzystać z [podstawowej procedury zwalniania do magazynu](#release-procedure), opisanej w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="d6018-227">In each case, you will work through the [basic release-to-warehouse procedure](#release-procedure) that is provided here.</span></span>

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a><span data-ttu-id="d6018-228">Podstawowa procedura zwalniania do magazynu</span><span class="sxs-lookup"><span data-stu-id="d6018-228">Basic release-to-warehouse procedure</span></span>

<span data-ttu-id="d6018-229">Dla każdego utworzonego wcześniej zestawu zamówień sprzedaży wykonasz trzy procedury opisane w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="d6018-229">For each set of sales orders that you created earlier, you will complete the three procedures that are outlined in the following subsections.</span></span>

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a><span data-ttu-id="d6018-230">Aktualizowanie szablonu grupy czynności, który będzie używany podczas zwalniania</span><span class="sxs-lookup"><span data-stu-id="d6018-230">Update the wave template that will be used during release</span></span>

1. <span data-ttu-id="d6018-231">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="d6018-231">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="d6018-232">Ustaw pole **Typ szablonu grupy czynności** na *Wysyłka*.</span><span class="sxs-lookup"><span data-stu-id="d6018-232">Set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="d6018-233">Znajdź i wybierz szablon grupy czynności skojarzony z magazynem, który został użyty w zestawach zamówień utworzonych dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="d6018-233">Find and select the wave template that is associated with the warehouse that you used in the order sets that you created for this scenario.</span></span> <span data-ttu-id="d6018-234">Jeśli na przykład użyto magazynu *24*, wybierz szablon grupy czynności **24 — wysyłka domyślna**.</span><span class="sxs-lookup"><span data-stu-id="d6018-234">For example, if you used warehouse *24*, select the **24 Shipping Default** wave template.</span></span> <span data-ttu-id="d6018-235">Jeśli użyto magazynu *61*, wybierz szablon grupy czynności **61 — wysyłka**.</span><span class="sxs-lookup"><span data-stu-id="d6018-235">If you used warehouse *61*, select the **61 Shipping** wave template.</span></span>
1. <span data-ttu-id="d6018-236">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="d6018-236">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="d6018-237">Ustaw opcję **Przetwarza grupę czynności w czasie uwalniania jej do magazynu** na wartość *Nie*.</span><span class="sxs-lookup"><span data-stu-id="d6018-237">Set the **Process wave at release to warehouse** option to *No*.</span></span>

#### <a name="release-to-the-warehouse"></a><span data-ttu-id="d6018-238">Zwalnianie do magazynu</span><span class="sxs-lookup"><span data-stu-id="d6018-238">Release to the warehouse</span></span>

1. <span data-ttu-id="d6018-239">Przejdź do pozycji **Zarządzanie magazynem \> Zwolnij do magazynu \> Automatyczne zwalnianie zamówień sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="d6018-239">Go to **Warehouse management \> Release to warehouse \> Automatic release of sales orders**.</span></span>
1. <span data-ttu-id="d6018-240">Ustaw pole **Ilość do zwolnienia** na wartość *Wszystko*.</span><span class="sxs-lookup"><span data-stu-id="d6018-240">Set the **Quantity to release** field to *All*.</span></span>
1. <span data-ttu-id="d6018-241">Na skróconej karcie **Rekordy do uwzględnienia** wybierz pozycję **Filtr**, aby otworzyć okno dialogowe zapytania.</span><span class="sxs-lookup"><span data-stu-id="d6018-241">On the **Records to include** FastTab, select **Filter** to open the query dialog box.</span></span>
1. <span data-ttu-id="d6018-242">Na karcie **Zakres** wybierz przycisk **Dodaj**, aby dodać wiersz zawierający następujące ustawienia do siatki:</span><span class="sxs-lookup"><span data-stu-id="d6018-242">On the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="d6018-243">**Tabela:** *Zamówienie sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="d6018-243">**Table:** *Sales order*</span></span>
    - <span data-ttu-id="d6018-244">**Tabela pochodna:** *Zamówienie sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="d6018-244">**Derived table:** *Sales order*</span></span>
    - <span data-ttu-id="d6018-245">**Pole:** *Zamówienie sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="d6018-245">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="d6018-246">**Kryteria:** wprowadź rozdzielaną przecinkami listę numerów zamówień sprzedaży z żądanego zestawu zamówień.</span><span class="sxs-lookup"><span data-stu-id="d6018-246">**Criteria:** Enter a comma-separated list of the sales order numbers from the desired order set.</span></span>

1. <span data-ttu-id="d6018-247">Wybierz przycisk **OK**, aby zapisać zapytanie.</span><span class="sxs-lookup"><span data-stu-id="d6018-247">Select **OK** to save your query.</span></span>
1. <span data-ttu-id="d6018-248">Wybierz przycisk **OK**, aby rozpocząć procedurę *automatycznego zwalniania do magazynu*.</span><span class="sxs-lookup"><span data-stu-id="d6018-248">Select **OK** to start the *Automatic release to warehouse* procedure.</span></span>

#### <a name="review-the-shipment-that-is-created-or-updated"></a><span data-ttu-id="d6018-249">Przeglądanie utworzonej lub zaktualizowanej wysyłki</span><span class="sxs-lookup"><span data-stu-id="d6018-249">Review the shipment that is created or updated</span></span>

1. <span data-ttu-id="d6018-250">Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="d6018-250">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="d6018-251">Znajdź i wybierz wymaganą wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="d6018-251">Find and select the required shipment.</span></span>
1. <span data-ttu-id="d6018-252">Jeśli podczas tworzenia lub aktualizowania wysyłki użyto zasad konsolidacji, powinny być one widoczne w polu **Zasady konsolidacji wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="d6018-252">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-sales-orders-from-order-set-1"></a><span data-ttu-id="d6018-253">Zwalnianie zamówień sprzedaży z zestawu zamówień 1</span><span class="sxs-lookup"><span data-stu-id="d6018-253">Release sales orders from order set 1</span></span>

<span data-ttu-id="d6018-254">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 1.</span><span class="sxs-lookup"><span data-stu-id="d6018-254">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 1.</span></span>

<span data-ttu-id="d6018-255">Po zakończeniu powinny być widoczne dwie utworzone wysyłki:</span><span class="sxs-lookup"><span data-stu-id="d6018-255">When you've finished, you should see that two shipments were created:</span></span>

- <span data-ttu-id="d6018-256">Pierwsza wysyłka zawiera trzy wiersze i została utworzona za pomocą zasad konsolidacji wysyłki *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="d6018-256">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="d6018-257">Druga wysyłka, która nie korzysta z metody dostawy *Trasy lotnicze*, została utworzona przy użyciu zasad konsolidacji wysyłki *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="d6018-257">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-sales-orders-from-order-set-2"></a><span data-ttu-id="d6018-258">Zwalnianie zamówień sprzedaży z zestawu zamówień 2</span><span class="sxs-lookup"><span data-stu-id="d6018-258">Release sales orders from order set 2</span></span>

<span data-ttu-id="d6018-259">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 2.</span><span class="sxs-lookup"><span data-stu-id="d6018-259">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 2.</span></span>

<span data-ttu-id="d6018-260">Po zakończeniu powinny być widoczne trzy utworzone wysyłki:</span><span class="sxs-lookup"><span data-stu-id="d6018-260">When you've finished, you should see that three shipments were created:</span></span>

- <span data-ttu-id="d6018-261">Pierwsza wysyłka zawiera pozycję typu *Łatwopalne*.</span><span class="sxs-lookup"><span data-stu-id="d6018-261">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="d6018-262">Każda z dwóch pozostałych wysyłek zawiera jeden wiersz pozycji typu *Materiały wybuchowe*.</span><span class="sxs-lookup"><span data-stu-id="d6018-262">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-3"></a><span data-ttu-id="d6018-263">Zwalnianie zamówień sprzedaży z zestawu zamówień 3</span><span class="sxs-lookup"><span data-stu-id="d6018-263">Release sales orders from order set 3</span></span>

<span data-ttu-id="d6018-264">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 3.</span><span class="sxs-lookup"><span data-stu-id="d6018-264">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 3.</span></span>

<span data-ttu-id="d6018-265">Po zakończeniu powinny być widoczne następujące wykonane akcje:</span><span class="sxs-lookup"><span data-stu-id="d6018-265">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="d6018-266">Zaktualizowano jedną istniejącą wysyłkę (wysyłkę utworzoną po zwolnieniu zestawu zamówień 2 do magazynu).</span><span class="sxs-lookup"><span data-stu-id="d6018-266">One existing shipment (the shipment that was created when order set 2 was released to the warehouse) was updated.</span></span> <span data-ttu-id="d6018-267">Dodano wiersz z pozycją typu *Łatwopalne*.</span><span class="sxs-lookup"><span data-stu-id="d6018-267">A line that has the *Flammable* item was added.</span></span>
- <span data-ttu-id="d6018-268">Utworzono jedną nową wysyłkę zawierającą pozycję typu *Materiały wybuchowe*.</span><span class="sxs-lookup"><span data-stu-id="d6018-268">One new shipment was created that contains the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-4"></a><span data-ttu-id="d6018-269">Zwalnianie zamówień sprzedaży z zestawu zamówień 4</span><span class="sxs-lookup"><span data-stu-id="d6018-269">Release sales orders from order set 4</span></span>

<span data-ttu-id="d6018-270">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 4.</span><span class="sxs-lookup"><span data-stu-id="d6018-270">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 4.</span></span>

<span data-ttu-id="d6018-271">Po zakończeniu powinna być widoczna jedna zaktualizowana istniejąca wysyłka (w której pole **Zapotrzebowanie odbiorcy** ma wartość *1*).</span><span class="sxs-lookup"><span data-stu-id="d6018-271">When you've finished, you should see that one existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="d6018-272">Dodano do niej jeden nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="d6018-272">One new line was added to it.</span></span>

### <a name="release-sales-orders-from-order-set-5"></a><span data-ttu-id="d6018-273">Zwalnianie zamówień sprzedaży z zestawu zamówień 5</span><span class="sxs-lookup"><span data-stu-id="d6018-273">Release sales orders from order set 5</span></span>

<span data-ttu-id="d6018-274">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 5.</span><span class="sxs-lookup"><span data-stu-id="d6018-274">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 5.</span></span>

<span data-ttu-id="d6018-275">Po zakończeniu powinny być widoczne następujące wykonane akcje:</span><span class="sxs-lookup"><span data-stu-id="d6018-275">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="d6018-276">Zaktualizowano jedną istniejącą wysyłkę (w której pole **Zapotrzebowanie odbiorcy** ma wartość *1*).</span><span class="sxs-lookup"><span data-stu-id="d6018-276">One existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="d6018-277">Dodano do niej wiersz z zamówienia sprzedaży 5-3 (w którym pole **Zapotrzebowanie odbiorcy** ma wartość *1*).</span><span class="sxs-lookup"><span data-stu-id="d6018-277">A line from sales order 5-3 (where the **Customer requisition** field is set to *1*) was added to it.</span></span>
- <span data-ttu-id="d6018-278">Utworzono jedną nową wysyłkę, w której wiersze z zamówień sprzedaży 5-1 i 5-2 są pogrupowane w ramach jednej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="d6018-278">One new shipment was created, where lines from sales orders 5-1 and 5-2 are grouped into one shipment.</span></span>

### <a name="release-sales-orders-from-order-set-6"></a><span data-ttu-id="d6018-279">Zwalnianie zamówień sprzedaży z zestawu zamówień 6</span><span class="sxs-lookup"><span data-stu-id="d6018-279">Release sales orders from order set 6</span></span>

<span data-ttu-id="d6018-280">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 6.</span><span class="sxs-lookup"><span data-stu-id="d6018-280">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 6.</span></span>

<span data-ttu-id="d6018-281">Po zakończeniu powinny być widoczne cztery utworzone wysyłki:</span><span class="sxs-lookup"><span data-stu-id="d6018-281">When you've finished, you should see that four shipments were created:</span></span>

- <span data-ttu-id="d6018-282">Wiersze z dwóch zamówień dla odbiorcy *US-003* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="d6018-282">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="d6018-283">Wiersze z dwóch zamówień dla odbiorcy *US-004* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="d6018-283">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="d6018-284">Wiersze z zamówień sprzedaży 6-5 i 6-6 dla odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="d6018-284">Lines from sales orders 6-5 and 6-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="d6018-285">Wiersze z zamówień sprzedaży 6-7 i 6-8 dla odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="d6018-285">Lines from sales orders 6-7 and 6-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d6018-286">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d6018-286">Additional resources</span></span>

- [<span data-ttu-id="d6018-287">Zasady konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="d6018-287">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="d6018-288">Konfigurowanie zasad konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="d6018-288">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
