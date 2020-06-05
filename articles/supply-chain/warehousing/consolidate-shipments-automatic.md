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
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 373b6bf6219ef76bacef3c67a816aec4c084c405
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383839"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a><span data-ttu-id="31a93-103">Konsolidowanie wysyłek podczas zwalniania ich do magazynu przy użyciu automatycznego zwalniania zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="31a93-103">Consolidate shipments when they are released to the warehouse by using Automatic release of sales orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31a93-104">W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu w ramach tej samej zautomatyzowanej okresowej procedury zwalniania do magazynu.</span><span class="sxs-lookup"><span data-stu-id="31a93-104">This topic presents a scenario where multiple orders are released to the warehouse in the same automated release-to-warehouse periodic procedure.</span></span> <span data-ttu-id="31a93-105">Zamówienia będą automatycznie konsolidowane w wysyłki na podstawie reguł zdefiniowanych jako zasady konsolidacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="31a93-105">The orders will automatically be consolidated into shipments, based on rules that are defined as shipment consolidation policies.</span></span>

<span data-ttu-id="31a93-106">W tym scenariuszu utworzysz zestawy zamówień sprzedaży i zwolnisz poszczególne zestawy do magazynu.</span><span class="sxs-lookup"><span data-stu-id="31a93-106">During the scenario, you will create sets of sales orders and release each set to the warehouse.</span></span> <span data-ttu-id="31a93-107">Następnie przejrzysz wysyłki utworzone lub zaktualizowane podczas konsolidowania wysyłki na podstawie skonfigurowanych zasad.</span><span class="sxs-lookup"><span data-stu-id="31a93-107">You will then review the shipments that are created or updated during shipment consolidation, based on the configured policies.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="31a93-108">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="31a93-108">Make demo data available</span></span>

<span data-ttu-id="31a93-109">Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="31a93-109">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="31a93-110">Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.</span><span class="sxs-lookup"><span data-stu-id="31a93-110">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="31a93-111">Konfigurowanie zasad konsolidacji wysyłki i filtrów produktów</span><span class="sxs-lookup"><span data-stu-id="31a93-111">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="31a93-112">W opisanym poniżej scenariuszu przyjęto założenie, że użytkownik już włączył funkcję, wykonał ćwiczenia z tematu [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md) i utworzył zasady oraz inne opisane w nim rekordy.</span><span class="sxs-lookup"><span data-stu-id="31a93-112">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="31a93-113">Przed kontynuowaniem tego scenariusza pamiętaj o wykonaniu poniższych ćwiczeń.</span><span class="sxs-lookup"><span data-stu-id="31a93-113">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="31a93-114">Tworzenie zamówień sprzedaży dla tego scenariusza</span><span class="sxs-lookup"><span data-stu-id="31a93-114">Create the sales orders for this scenario</span></span>

<span data-ttu-id="31a93-115">Rozpocznij od utworzenia kolekcji zamówień sprzedaży, z którymi możesz pracować.</span><span class="sxs-lookup"><span data-stu-id="31a93-115">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="31a93-116">Musisz pracować z magazynem, w którym włączono obsługę zaawansowanych procesów magazynu (WMS).</span><span class="sxs-lookup"><span data-stu-id="31a93-116">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="31a93-117">O ile inny magazyn nie został wyraźnie wskazany, ten sam magazyn musi być używany dla każdego z poniższych zestawów zamówień.</span><span class="sxs-lookup"><span data-stu-id="31a93-117">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="31a93-118">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży** i utwórz kolekcję zamówień sprzedaży z ustawieniami opisanymi w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="31a93-118">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="31a93-119">Tworzenie zestawu zamówień 1</span><span class="sxs-lookup"><span data-stu-id="31a93-119">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="31a93-120">Zamówienie sprzedaży 1-1</span><span class="sxs-lookup"><span data-stu-id="31a93-120">Sales order 1-1</span></span>

1. <span data-ttu-id="31a93-121">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-121">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="31a93-122">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="31a93-122">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="31a93-123">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="31a93-123">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="31a93-124">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-124">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-125">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-125">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-126">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-126">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="31a93-127">Zamówienie sprzedaży 1-2</span><span class="sxs-lookup"><span data-stu-id="31a93-127">Sales order 1-2</span></span>

1. <span data-ttu-id="31a93-128">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-128">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="31a93-129">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="31a93-129">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="31a93-130">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="31a93-130">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="31a93-131">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-131">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-132">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-132">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-133">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-133">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="31a93-134">Zamówienie sprzedaży 1-3</span><span class="sxs-lookup"><span data-stu-id="31a93-134">Sales order 1-3</span></span>

1. <span data-ttu-id="31a93-135">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-135">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="31a93-136">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="31a93-136">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="31a93-137">**Metoda dostawy:** *10*</span><span class="sxs-lookup"><span data-stu-id="31a93-137">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="31a93-138">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-138">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-139">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-139">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-140">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-140">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="31a93-141">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-142">**Kod pozycji:** *A0002* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-143">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="31a93-144">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="31a93-144">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="31a93-145">Tworzenie zestawu zamówień 2</span><span class="sxs-lookup"><span data-stu-id="31a93-145">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="31a93-146">Zamówienia sprzedaży 2-1 i 2-2</span><span class="sxs-lookup"><span data-stu-id="31a93-146">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="31a93-147">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-147">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="31a93-148">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="31a93-148">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="31a93-149">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-149">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-150">**Kod pozycji:** *M9200* (pozycja, dla której filtr **Kod 4** został ustawiony na *Łatwopalne*)</span><span class="sxs-lookup"><span data-stu-id="31a93-150">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="31a93-151">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-151">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="31a93-152">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-152">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-153">**Kod pozycji:** *M9201* (pozycja, dla której filtr **Kod 4** został ustawiony na *Materiały wybuchowe*)</span><span class="sxs-lookup"><span data-stu-id="31a93-153">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="31a93-154">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-154">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="31a93-155">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="31a93-155">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="31a93-156">Tworzenie zestawu zamówień 3</span><span class="sxs-lookup"><span data-stu-id="31a93-156">Create order set 3</span></span>

#### <a name="sales-order-3-1"></a><span data-ttu-id="31a93-157">Zamówienie sprzedaży 3-1</span><span class="sxs-lookup"><span data-stu-id="31a93-157">Sales order 3-1</span></span>

1. <span data-ttu-id="31a93-158">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-158">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="31a93-159">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="31a93-159">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="31a93-160">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-160">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-161">**Kod pozycji:** *M9200* (pozycja, dla której filtr **Kod 4** został ustawiony na *Łatwopalne*)</span><span class="sxs-lookup"><span data-stu-id="31a93-161">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="31a93-162">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-162">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="31a93-163">Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-163">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-164">**Kod pozycji:** *M9201* (pozycja, dla której filtr **Kod 4** został ustawiony na *Materiały wybuchowe*)</span><span class="sxs-lookup"><span data-stu-id="31a93-164">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="31a93-165">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-165">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="31a93-166">**Metoda dostawy:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="31a93-166">**Mode of delivery:** *Airwa-Air*</span></span>

> [!NOTE]
> <span data-ttu-id="31a93-167">To zamówienie jest identyczne jak dwa zamówienia utworzone dla zestawu zamówień 2.</span><span class="sxs-lookup"><span data-stu-id="31a93-167">This order is identical to the two orders that you created for order set 2.</span></span> <span data-ttu-id="31a93-168">Jest ono jednak wymienione jako oddzielny zestaw zamówień, ponieważ w tym scenariuszu zostanie zwolnione osobno w późniejszym czasie.</span><span class="sxs-lookup"><span data-stu-id="31a93-168">However, it's listed as its own order set because you will release it separately later in this scenario.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="31a93-169">Tworzenie zestawu zamówień 4</span><span class="sxs-lookup"><span data-stu-id="31a93-169">Create order set 4</span></span>

#### <a name="sales-order-4-1"></a><span data-ttu-id="31a93-170">Zamówienie sprzedaży 4-1</span><span class="sxs-lookup"><span data-stu-id="31a93-170">Sales order 4-1</span></span>

1. <span data-ttu-id="31a93-171">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-171">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="31a93-172">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="31a93-172">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="31a93-173">**Zapotrzebowanie odbiorcy:** *1*</span><span class="sxs-lookup"><span data-stu-id="31a93-173">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="31a93-174">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-174">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-175">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-175">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-176">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-176">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-5"></a><span data-ttu-id="31a93-177">Tworzenie zestawu zamówień 5</span><span class="sxs-lookup"><span data-stu-id="31a93-177">Create order set 5</span></span>

#### <a name="sales-orders-5-1-and-5-2"></a><span data-ttu-id="31a93-178">Zamówienia sprzedaży 5-1 i 5-2</span><span class="sxs-lookup"><span data-stu-id="31a93-178">Sales orders 5-1 and 5-2</span></span>

1. <span data-ttu-id="31a93-179">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="31a93-180">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="31a93-180">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="31a93-181">**Zapotrzebowanie odbiorcy:** *2*</span><span class="sxs-lookup"><span data-stu-id="31a93-181">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="31a93-182">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-182">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-183">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-183">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-184">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-184">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-5-3"></a><span data-ttu-id="31a93-185">Zamówienie sprzedaży 5-3</span><span class="sxs-lookup"><span data-stu-id="31a93-185">Sales order 5-3</span></span>

1. <span data-ttu-id="31a93-186">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-186">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="31a93-187">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="31a93-187">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="31a93-188">**Zapotrzebowanie odbiorcy:** *1*</span><span class="sxs-lookup"><span data-stu-id="31a93-188">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="31a93-189">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-189">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-190">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-190">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-191">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-191">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-6"></a><span data-ttu-id="31a93-192">Tworzenie zestawu zamówień 6</span><span class="sxs-lookup"><span data-stu-id="31a93-192">Create order set 6</span></span>

#### <a name="sales-orders-6-1-and-6-2"></a><span data-ttu-id="31a93-193">Zamówienia sprzedaży 6-1 i 6-2</span><span class="sxs-lookup"><span data-stu-id="31a93-193">Sales orders 6-1 and 6-2</span></span>

1. <span data-ttu-id="31a93-194">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-194">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="31a93-195">**Konto odbiorcy:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="31a93-195">**Customer account:** *US-003*</span></span>
    - <span data-ttu-id="31a93-196">**Zapotrzebowanie odbiorcy:** *2*</span><span class="sxs-lookup"><span data-stu-id="31a93-196">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="31a93-197">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-198">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-199">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-199">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-3-and-6-4"></a><span data-ttu-id="31a93-200">Zamówienia sprzedaży 6-3 i 6-4</span><span class="sxs-lookup"><span data-stu-id="31a93-200">Sales orders 6-3 and 6-4</span></span>

1. <span data-ttu-id="31a93-201">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-201">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="31a93-202">**Konto odbiorcy:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="31a93-202">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="31a93-203">**Zapotrzebowanie odbiorcy:** *1*</span><span class="sxs-lookup"><span data-stu-id="31a93-203">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="31a93-204">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-204">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-205">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-205">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-206">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-206">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-5-and-6-6"></a><span data-ttu-id="31a93-207">Zamówienia sprzedaży 6-5 i 6-6</span><span class="sxs-lookup"><span data-stu-id="31a93-207">Sales orders 6-5 and 6-6</span></span>

1. <span data-ttu-id="31a93-208">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-208">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="31a93-209">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="31a93-209">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="31a93-210">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="31a93-210">**Site:** *6*</span></span>
    - <span data-ttu-id="31a93-211">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="31a93-211">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="31a93-212">**Pula:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="31a93-212">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="31a93-213">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-213">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-214">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-214">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-215">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-215">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-7-and-6-8"></a><span data-ttu-id="31a93-216">Zamówienia sprzedaży 6-7 i 6-8</span><span class="sxs-lookup"><span data-stu-id="31a93-216">Sales orders 6-7 and 6-8</span></span>

1. <span data-ttu-id="31a93-217">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-217">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="31a93-218">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="31a93-218">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="31a93-219">**Oddział:** *6*</span><span class="sxs-lookup"><span data-stu-id="31a93-219">**Site:** *6*</span></span>
    - <span data-ttu-id="31a93-220">**Magazyn:** *61*</span><span class="sxs-lookup"><span data-stu-id="31a93-220">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="31a93-221">**Pula:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="31a93-221">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="31a93-222">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="31a93-222">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="31a93-223">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="31a93-223">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="31a93-224">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="31a93-224">**Quantity:** *1.00*</span></span>

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a><span data-ttu-id="31a93-225">Automatyczne zwalnianie zamówień sprzedaży do magazynu</span><span class="sxs-lookup"><span data-stu-id="31a93-225">Automatic release of sales orders to the warehouse</span></span>

<span data-ttu-id="31a93-226">Dla każdego utworzonego wcześniej zestawu zamówień sprzedaży zostanie wykonana procedura automatycznego zwalniania do magazynu.</span><span class="sxs-lookup"><span data-stu-id="31a93-226">For each set of sales orders that you created earlier, you will complete a procedure for automatic release to the warehouse.</span></span> <span data-ttu-id="31a93-227">W każdym przypadku będziesz korzystać z [podstawowej procedury zwalniania do magazynu](#release-procedure), opisanej w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="31a93-227">In each case, you will work through the [basic release-to-warehouse procedure](#release-procedure) that is provided here.</span></span>

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a><span data-ttu-id="31a93-228">Podstawowa procedura zwalniania do magazynu</span><span class="sxs-lookup"><span data-stu-id="31a93-228">Basic release-to-warehouse procedure</span></span>

<span data-ttu-id="31a93-229">Dla każdego utworzonego wcześniej zestawu zamówień sprzedaży wykonasz trzy procedury opisane w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="31a93-229">For each set of sales orders that you created earlier, you will complete the three procedures that are outlined in the following subsections.</span></span>

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a><span data-ttu-id="31a93-230">Aktualizowanie szablonu grupy czynności, który będzie używany podczas zwalniania</span><span class="sxs-lookup"><span data-stu-id="31a93-230">Update the wave template that will be used during release</span></span>

1. <span data-ttu-id="31a93-231">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="31a93-231">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="31a93-232">Ustaw pole **Typ szablonu grupy czynności** na *Wysyłka*.</span><span class="sxs-lookup"><span data-stu-id="31a93-232">Set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="31a93-233">Znajdź i wybierz szablon grupy czynności skojarzony z magazynem, który został użyty w zestawach zamówień utworzonych dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="31a93-233">Find and select the wave template that is associated with the warehouse that you used in the order sets that you created for this scenario.</span></span> <span data-ttu-id="31a93-234">Jeśli na przykład użyto magazynu *24*, wybierz szablon grupy czynności **24 — wysyłka domyślna**.</span><span class="sxs-lookup"><span data-stu-id="31a93-234">For example, if you used warehouse *24*, select the **24 Shipping Default** wave template.</span></span> <span data-ttu-id="31a93-235">Jeśli użyto magazynu *61*, wybierz szablon grupy czynności **61 — wysyłka**.</span><span class="sxs-lookup"><span data-stu-id="31a93-235">If you used warehouse *61*, select the **61 Shipping** wave template.</span></span>
1. <span data-ttu-id="31a93-236">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="31a93-236">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="31a93-237">Ustaw opcję **Przetwarza grupę czynności w czasie uwalniania jej do magazynu** na wartość *Nie*.</span><span class="sxs-lookup"><span data-stu-id="31a93-237">Set the **Process wave at release to warehouse** option to *No*.</span></span>

#### <a name="release-to-the-warehouse"></a><span data-ttu-id="31a93-238">Zwalnianie do magazynu</span><span class="sxs-lookup"><span data-stu-id="31a93-238">Release to the warehouse</span></span>

1. <span data-ttu-id="31a93-239">Przejdź do pozycji **Zarządzanie magazynem \> Zwolnij do magazynu \> Automatyczne zwalnianie zamówień sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="31a93-239">Go to **Warehouse management \> Release to warehouse \> Automatic release of sales orders**.</span></span>
1. <span data-ttu-id="31a93-240">Ustaw pole **Ilość do zwolnienia** na wartość *Wszystko*.</span><span class="sxs-lookup"><span data-stu-id="31a93-240">Set the **Quantity to release** field to *All*.</span></span>
1. <span data-ttu-id="31a93-241">Na skróconej karcie **Rekordy do uwzględnienia** wybierz pozycję **Filtr**, aby otworzyć okno dialogowe zapytania.</span><span class="sxs-lookup"><span data-stu-id="31a93-241">On the **Records to include** FastTab, select **Filter** to open the query dialog box.</span></span>
1. <span data-ttu-id="31a93-242">Na karcie **Zakres** wybierz przycisk **Dodaj**, aby dodać wiersz zawierający następujące ustawienia do siatki:</span><span class="sxs-lookup"><span data-stu-id="31a93-242">On the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="31a93-243">**Tabela:** *Zamówienie sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="31a93-243">**Table:** *Sales order*</span></span>
    - <span data-ttu-id="31a93-244">**Tabela pochodna:** *Zamówienie sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="31a93-244">**Derived table:** *Sales order*</span></span>
    - <span data-ttu-id="31a93-245">**Pole:** *Zamówienie sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="31a93-245">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="31a93-246">**Kryteria:** wprowadź rozdzielaną przecinkami listę numerów zamówień sprzedaży z żądanego zestawu zamówień.</span><span class="sxs-lookup"><span data-stu-id="31a93-246">**Criteria:** Enter a comma-separated list of the sales order numbers from the desired order set.</span></span>

1. <span data-ttu-id="31a93-247">Wybierz przycisk **OK**, aby zapisać zapytanie.</span><span class="sxs-lookup"><span data-stu-id="31a93-247">Select **OK** to save your query.</span></span>
1. <span data-ttu-id="31a93-248">Wybierz przycisk **OK**, aby rozpocząć procedurę *automatycznego zwalniania do magazynu*.</span><span class="sxs-lookup"><span data-stu-id="31a93-248">Select **OK** to start the *Automatic release to warehouse* procedure.</span></span>

#### <a name="review-the-shipment-that-is-created-or-updated"></a><span data-ttu-id="31a93-249">Przeglądanie utworzonej lub zaktualizowanej wysyłki</span><span class="sxs-lookup"><span data-stu-id="31a93-249">Review the shipment that is created or updated</span></span>

1. <span data-ttu-id="31a93-250">Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="31a93-250">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="31a93-251">Znajdź i wybierz wymaganą wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="31a93-251">Find and select the required shipment.</span></span>
1. <span data-ttu-id="31a93-252">Jeśli podczas tworzenia lub aktualizowania wysyłki użyto zasad konsolidacji, powinny być one widoczne w polu **Zasady konsolidacji wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="31a93-252">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-sales-orders-from-order-set-1"></a><span data-ttu-id="31a93-253">Zwalnianie zamówień sprzedaży z zestawu zamówień 1</span><span class="sxs-lookup"><span data-stu-id="31a93-253">Release sales orders from order set 1</span></span>

<span data-ttu-id="31a93-254">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 1.</span><span class="sxs-lookup"><span data-stu-id="31a93-254">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 1.</span></span>

<span data-ttu-id="31a93-255">Po zakończeniu powinny być widoczne dwie utworzone wysyłki:</span><span class="sxs-lookup"><span data-stu-id="31a93-255">When you've finished, you should see that two shipments were created:</span></span>

- <span data-ttu-id="31a93-256">Pierwsza wysyłka zawiera trzy wiersze i została utworzona za pomocą zasad konsolidacji wysyłki *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="31a93-256">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="31a93-257">Druga wysyłka, która nie korzysta z metody dostawy *Trasy lotnicze*, została utworzona przy użyciu zasad konsolidacji wysyłki *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="31a93-257">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-sales-orders-from-order-set-2"></a><span data-ttu-id="31a93-258">Zwalnianie zamówień sprzedaży z zestawu zamówień 2</span><span class="sxs-lookup"><span data-stu-id="31a93-258">Release sales orders from order set 2</span></span>

<span data-ttu-id="31a93-259">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 2.</span><span class="sxs-lookup"><span data-stu-id="31a93-259">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 2.</span></span>

<span data-ttu-id="31a93-260">Po zakończeniu powinny być widoczne trzy utworzone wysyłki:</span><span class="sxs-lookup"><span data-stu-id="31a93-260">When you've finished, you should see that three shipments were created:</span></span>

- <span data-ttu-id="31a93-261">Pierwsza wysyłka zawiera pozycję typu *Łatwopalne*.</span><span class="sxs-lookup"><span data-stu-id="31a93-261">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="31a93-262">Każda z dwóch pozostałych wysyłek zawiera jeden wiersz pozycji typu *Materiały wybuchowe*.</span><span class="sxs-lookup"><span data-stu-id="31a93-262">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-3"></a><span data-ttu-id="31a93-263">Zwalnianie zamówień sprzedaży z zestawu zamówień 3</span><span class="sxs-lookup"><span data-stu-id="31a93-263">Release sales orders from order set 3</span></span>

<span data-ttu-id="31a93-264">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 3.</span><span class="sxs-lookup"><span data-stu-id="31a93-264">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 3.</span></span>

<span data-ttu-id="31a93-265">Po zakończeniu powinny być widoczne następujące wykonane akcje:</span><span class="sxs-lookup"><span data-stu-id="31a93-265">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="31a93-266">Zaktualizowano jedną istniejącą wysyłkę (wysyłkę utworzoną po zwolnieniu zestawu zamówień 2 do magazynu).</span><span class="sxs-lookup"><span data-stu-id="31a93-266">One existing shipment (the shipment that was created when order set 2 was released to the warehouse) was updated.</span></span> <span data-ttu-id="31a93-267">Dodano wiersz z pozycją typu *Łatwopalne*.</span><span class="sxs-lookup"><span data-stu-id="31a93-267">A line that has the *Flammable* item was added.</span></span>
- <span data-ttu-id="31a93-268">Utworzono jedną nową wysyłkę zawierającą pozycję typu *Materiały wybuchowe*.</span><span class="sxs-lookup"><span data-stu-id="31a93-268">One new shipment was created that contains the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-4"></a><span data-ttu-id="31a93-269">Zwalnianie zamówień sprzedaży z zestawu zamówień 4</span><span class="sxs-lookup"><span data-stu-id="31a93-269">Release sales orders from order set 4</span></span>

<span data-ttu-id="31a93-270">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 4.</span><span class="sxs-lookup"><span data-stu-id="31a93-270">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 4.</span></span>

<span data-ttu-id="31a93-271">Po zakończeniu powinna być widoczna jedna zaktualizowana istniejąca wysyłka (w której pole **Zapotrzebowanie odbiorcy** ma wartość *1*).</span><span class="sxs-lookup"><span data-stu-id="31a93-271">When you've finished, you should see that one existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="31a93-272">Dodano do niej jeden nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="31a93-272">One new line was added to it.</span></span>

### <a name="release-sales-orders-from-order-set-5"></a><span data-ttu-id="31a93-273">Zwalnianie zamówień sprzedaży z zestawu zamówień 5</span><span class="sxs-lookup"><span data-stu-id="31a93-273">Release sales orders from order set 5</span></span>

<span data-ttu-id="31a93-274">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 5.</span><span class="sxs-lookup"><span data-stu-id="31a93-274">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 5.</span></span>

<span data-ttu-id="31a93-275">Po zakończeniu powinny być widoczne następujące wykonane akcje:</span><span class="sxs-lookup"><span data-stu-id="31a93-275">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="31a93-276">Zaktualizowano jedną istniejącą wysyłkę (w której pole **Zapotrzebowanie odbiorcy** ma wartość *1*).</span><span class="sxs-lookup"><span data-stu-id="31a93-276">One existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="31a93-277">Dodano do niej wiersz z zamówienia sprzedaży 5-3 (w którym pole **Zapotrzebowanie odbiorcy** ma wartość *1*).</span><span class="sxs-lookup"><span data-stu-id="31a93-277">A line from sales order 5-3 (where the **Customer requisition** field is set to *1*) was added to it.</span></span>
- <span data-ttu-id="31a93-278">Utworzono jedną nową wysyłkę, w której wiersze z zamówień sprzedaży 5-1 i 5-2 są pogrupowane w ramach jednej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="31a93-278">One new shipment was created, where lines from sales orders 5-1 and 5-2 are grouped into one shipment.</span></span>

### <a name="release-sales-orders-from-order-set-6"></a><span data-ttu-id="31a93-279">Zwalnianie zamówień sprzedaży z zestawu zamówień 6</span><span class="sxs-lookup"><span data-stu-id="31a93-279">Release sales orders from order set 6</span></span>

<span data-ttu-id="31a93-280">Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 6.</span><span class="sxs-lookup"><span data-stu-id="31a93-280">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 6.</span></span>

<span data-ttu-id="31a93-281">Po zakończeniu powinny być widoczne cztery utworzone wysyłki:</span><span class="sxs-lookup"><span data-stu-id="31a93-281">When you've finished, you should see that four shipments were created:</span></span>

- <span data-ttu-id="31a93-282">Wiersze z dwóch zamówień dla odbiorcy *US-003* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="31a93-282">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="31a93-283">Wiersze z dwóch zamówień dla odbiorcy *US-004* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="31a93-283">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="31a93-284">Wiersze z zamówień sprzedaży 6-5 i 6-6 dla odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *Pula zamówień*.</span><span class="sxs-lookup"><span data-stu-id="31a93-284">Lines from sales orders 6-5 and 6-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="31a93-285">Wiersze z zamówień sprzedaży 6-7 i 6-8 dla odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="31a93-285">Lines from sales orders 6-7 and 6-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31a93-286">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="31a93-286">Additional resources</span></span>

- [<span data-ttu-id="31a93-287">Zasady konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="31a93-287">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="31a93-288">Konfigurowanie zasad konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="31a93-288">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
