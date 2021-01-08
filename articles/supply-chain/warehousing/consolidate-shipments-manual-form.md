---
title: Ręczne konsolidowanie wysyłek przy użyciu strony konsolidacji wysyłek
description: W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu, a później konsolidowanych przy użyciu strony konsolidowania wysyłek.
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
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: ac60bef797d8e0bbe0d20f1585d5c3c0163f8788
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434989"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a><span data-ttu-id="1419a-103">Ręczne konsolidowanie wysyłek przy użyciu strony konsolidacji wysyłek</span><span class="sxs-lookup"><span data-stu-id="1419a-103">Consolidate shipments manually by using the Consolidate shipments page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1419a-104">W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu, a później konsolidowanych przy użyciu strony **konsolidowania wysyłek**.</span><span class="sxs-lookup"><span data-stu-id="1419a-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated later by using the **Consolidate shipments** page.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="1419a-105">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="1419a-105">Make demo data available</span></span>

<span data-ttu-id="1419a-106">Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1419a-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="1419a-107">Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.</span><span class="sxs-lookup"><span data-stu-id="1419a-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="1419a-108">Konfigurowanie zasad konsolidacji wysyłki i filtrów produktów</span><span class="sxs-lookup"><span data-stu-id="1419a-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="1419a-109">W opisanym poniżej scenariuszu przyjęto założenie, że użytkownik już włączył funkcję, wykonał ćwiczenia z tematu [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md) i utworzył zasady oraz inne opisane w nim rekordy.</span><span class="sxs-lookup"><span data-stu-id="1419a-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="1419a-110">Przed kontynuowaniem tego scenariusza pamiętaj o wykonaniu poniższych ćwiczeń.</span><span class="sxs-lookup"><span data-stu-id="1419a-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="1419a-111">Tworzenie zamówień sprzedaży dla tego scenariusza</span><span class="sxs-lookup"><span data-stu-id="1419a-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="1419a-112">Rozpocznij od utworzenia kolekcji zamówień sprzedaży, z którymi możesz pracować.</span><span class="sxs-lookup"><span data-stu-id="1419a-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="1419a-113">Musisz pracować z magazynem, w którym włączono obsługę zaawansowanych procesów magazynu (WMS).</span><span class="sxs-lookup"><span data-stu-id="1419a-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="1419a-114">O ile inny magazyn nie został wyraźnie wskazany, ten sam magazyn musi być używany dla każdego z poniższych zestawów zamówień.</span><span class="sxs-lookup"><span data-stu-id="1419a-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="1419a-115">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży** i utwórz kolekcję zamówień sprzedaży z ustawieniami opisanymi w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="1419a-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-sales-orders-1-and-2"></a><span data-ttu-id="1419a-116">Tworzenie zamówień sprzedaży 1 i 2</span><span class="sxs-lookup"><span data-stu-id="1419a-116">Create sales orders 1 and 2</span></span>

1. <span data-ttu-id="1419a-117">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="1419a-117">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="1419a-118">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="1419a-118">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="1419a-119">**Pula:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="1419a-119">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="1419a-120">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="1419a-120">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="1419a-121">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="1419a-121">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="1419a-122">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="1419a-122">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="1419a-123">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="1419a-123">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-sales-orders-3-and-4"></a><span data-ttu-id="1419a-124">Tworzenie zamówień sprzedaży 3 i 4</span><span class="sxs-lookup"><span data-stu-id="1419a-124">Create sales orders 3 and 4</span></span>

1. <span data-ttu-id="1419a-125">Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="1419a-125">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="1419a-126">**Konto odbiorcy:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="1419a-126">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="1419a-127">**Pula:** pozostaw to pole puste.</span><span class="sxs-lookup"><span data-stu-id="1419a-127">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="1419a-128">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="1419a-128">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="1419a-129">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)</span><span class="sxs-lookup"><span data-stu-id="1419a-129">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="1419a-130">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="1419a-130">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="1419a-131">Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="1419a-131">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="1419a-132">Zwalnianie zamówień do magazynu</span><span class="sxs-lookup"><span data-stu-id="1419a-132">Release the orders to the warehouse</span></span>

<span data-ttu-id="1419a-133">Wykonaj poniższe kroki, aby zwolnić każde zamówienie sprzedaży utworzone dla tego scenariusza do magazynu.</span><span class="sxs-lookup"><span data-stu-id="1419a-133">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="1419a-134">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="1419a-134">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="1419a-135">Znajdź i zaznacz zamówienie sprzedaży do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="1419a-135">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="1419a-136">W okienku akcji na karcie **Magazyn** wybierz pozycję **Akcje \> Zwolnij do magazynu**, aby zwolnić wybrane zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="1419a-136">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="1419a-137">Powtórz tę procedurę dla wszystkich zamówień sprzedaży utworzonych dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="1419a-137">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-shipments"></a><span data-ttu-id="1419a-138">Konsoliduj wysyłki</span><span class="sxs-lookup"><span data-stu-id="1419a-138">Consolidate shipments</span></span>

1. <span data-ttu-id="1419a-139">Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="1419a-139">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="1419a-140">Znajdź i wybierz wysyłkę, która została utworzona, gdy zamówienie sprzedaży 1 zostało zwolnione do magazynu.</span><span class="sxs-lookup"><span data-stu-id="1419a-140">Find and select a shipment that was created when sales order 1 was released to the warehouse.</span></span> <span data-ttu-id="1419a-141">(Odpowiednie pole **Zasady konsolidacji wysyłki** powinno być ustawione na wartość *Pula zamówień*).</span><span class="sxs-lookup"><span data-stu-id="1419a-141">(Its **Shipment consolidation policy** field should be set to *Order pool*.)</span></span>
1. <span data-ttu-id="1419a-142">W okienku akcji na karcie **Wysyłki** wybierz pozycję **Wysyłki \> Konsoliduj wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="1419a-142">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="1419a-143">Zweryfikuj wysyłki sugerowane do konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="1419a-143">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="1419a-144">Tylko jedna wysyłka mająca takie same zasady powinna być sugerowana do konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="1419a-144">Only one shipment that has the same policy should be suggested for consolidation.</span></span>
1. <span data-ttu-id="1419a-145">Zamknij stronę **Zasady konsolidacji wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="1419a-145">Close the **Shipment consolidation** page.</span></span>
1. <span data-ttu-id="1419a-146">Znajdź i wybierz wysyłkę, która została utworzona, gdy zamówienie sprzedaży 3 zostało zwolnione do magazynu.</span><span class="sxs-lookup"><span data-stu-id="1419a-146">Find and select a shipment that was created when sales order 3 was released to the warehouse.</span></span> <span data-ttu-id="1419a-147">(Odpowiednie pole **Zasady konsolidacji wysyłki** powinno być ustawione na wartość *Domyślne*).</span><span class="sxs-lookup"><span data-stu-id="1419a-147">(Its **Shipment consolidation policy** field should be set to *Default*.)</span></span>
1. <span data-ttu-id="1419a-148">W okienku akcji na karcie **Wysyłki** wybierz pozycję **Wysyłki \> Konsoliduj wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="1419a-148">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="1419a-149">Upewnij się, że nie wybrano wysyłek sugerowanych do konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="1419a-149">Verify that no shipments are suggested for consolidation.</span></span>
1. <span data-ttu-id="1419a-150">Wybierz pozycję **Pokaż filtry**.</span><span class="sxs-lookup"><span data-stu-id="1419a-150">Select **Show filters**.</span></span>
1. <span data-ttu-id="1419a-151">W okienku **Filtry** usuń filtr **Numer zamówienia**, a następnie wybierz przycisk **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="1419a-151">In the **Filters** pane, remove the **Order number** filter, and then select **Apply**.</span></span>
1. <span data-ttu-id="1419a-152">Zweryfikuj wysyłki sugerowane do konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="1419a-152">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="1419a-153">Tylko jedna wysyłka mająca takie same zasady powinna być sugerowana do konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="1419a-153">Only one shipment that has the same policy should be suggested for consolidation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1419a-154">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1419a-154">Additional resources</span></span>

- [<span data-ttu-id="1419a-155">Zasady konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="1419a-155">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="1419a-156">Konfigurowanie zasad konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="1419a-156">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)