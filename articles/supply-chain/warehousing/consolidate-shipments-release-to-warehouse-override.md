---
title: Konsolidowanie wysyłek, gdy zasady konsolidacji wysyłki są zastąpione na stronie zwalniania do magazynu
description: W tym temacie przedstawiono scenariusz, w którym co najmniej jeden wiersz sprzedaży musi zostać ręcznie zwolniony do magazynu z poziomu strony zwalniania do magazynu, a zasady konsolidacji wysyłki zdefiniowane w systemie muszą zostać zastąpione przed zwolnieniem.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 96f994e9f3440721105545f96d7d8475fcab2b6b
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016800"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a><span data-ttu-id="25666-103">Konsolidowanie wysyłek, gdy zasady konsolidacji wysyłki są zastąpione na stronie zwalniania do magazynu</span><span class="sxs-lookup"><span data-stu-id="25666-103">Consolidate shipments when the shipment consolidation policy is overridden from the Release to warehouse page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25666-104">W tym temacie przedstawiono scenariusz, w którym co najmniej jeden wiersz sprzedaży musi zostać ręcznie zwolniony do magazynu z poziomu strony **zwalniania do magazynu** , a zasady konsolidacji wysyłki zdefiniowane w systemie muszą zostać zastąpione przed zwolnieniem.</span><span class="sxs-lookup"><span data-stu-id="25666-104">This topic presents a scenario where one or more sales lines must be manually released to the warehouse from the **Release to warehouse** page, and the system-defined shipment consolidation policy must be overridden before the release.</span></span> <span data-ttu-id="25666-105">Zastąpienie zasady konsolidacji wysyłki może być wymagane, jeśli na przykład zamówienie, które nie jest zwykle skonsolidowane w przypadku otwartych wysyłek, musi zostać skonsolidowane z otwartymi wysyłkami.</span><span class="sxs-lookup"><span data-stu-id="25666-105">An override of the shipment consolidation policy might be required if, for example, an order that isn't usually consolidated with open shipments must be consolidated with open shipments.</span></span>

<span data-ttu-id="25666-106">W trakcie tego scenariusza utworzysz zestaw zamówień sprzedaży, a następnie zastąpi domyślne zasady konsolidacji wysyłki przed zwolnieniem zamówień do magazynu.</span><span class="sxs-lookup"><span data-stu-id="25666-106">During the scenario, you will create a set of sales orders and then override the default shipment consolidation policy before you release the orders to the warehouse.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="25666-107">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="25666-107">Make demo data available</span></span>

<span data-ttu-id="25666-108">Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="25666-108">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="25666-109">Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.</span><span class="sxs-lookup"><span data-stu-id="25666-109">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="25666-110">Konfigurowanie zasad konsolidacji wysyłki i filtrów produktów</span><span class="sxs-lookup"><span data-stu-id="25666-110">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="25666-111">W opisanym poniżej scenariuszu przyjęto założenie, że użytkownik już włączył funkcję, wykonał ćwiczenia z tematu [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md) i utworzył zasady oraz inne opisane w nim rekordy.</span><span class="sxs-lookup"><span data-stu-id="25666-111">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="25666-112">Przed kontynuowaniem tego scenariusza pamiętaj o wykonaniu poniższych ćwiczeń.</span><span class="sxs-lookup"><span data-stu-id="25666-112">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="25666-113">Tworzenie zamówień sprzedaży dla tego scenariusza</span><span class="sxs-lookup"><span data-stu-id="25666-113">Create the sales orders for this scenario</span></span>

1. <span data-ttu-id="25666-114">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży** i utwórz trzy identyczne zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="25666-114">Go to **Accounts receivable \> Orders \> All sales orders** , and create three identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="25666-115">**Konto odbiorcy:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="25666-115">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="25666-116">Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="25666-116">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="25666-117">**Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4** )</span><span class="sxs-lookup"><span data-stu-id="25666-117">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="25666-118">**Ilość:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="25666-118">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="25666-119">Wybierz pozycję **Zapasy \> Rezerwacja** , a następnie w okienku akcji wybierz pozycję **Rezerwacja partii** , aby zarezerwować wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="25666-119">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a><span data-ttu-id="25666-120">Zwalnianie zamówień sprzedaży ze strony zwalniania do magazynu</span><span class="sxs-lookup"><span data-stu-id="25666-120">Release the sales orders from the Release to warehouse page</span></span>

<span data-ttu-id="25666-121">Wykonać poniższe kroki, aby zastępować zasady konsolidacji wysyłki podczas zwalniania do magazynu.</span><span class="sxs-lookup"><span data-stu-id="25666-121">Follow these steps to override the shipment consolidation policy during the release to the warehouse.</span></span>

1. <span data-ttu-id="25666-122">Przejdź do pozycji **Zarządzanie magazynem \> Zwolnij do magazynu \> Zwolnij do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="25666-122">Go to **Warehouse management \> Release to warehouse \> Release to warehouse**.</span></span>
1. <span data-ttu-id="25666-123">W górnym okienku wybierz pierwsze zamówienie sprzedaży utworzone dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="25666-123">In the upper pane, select the first sales order that you created for this scenario.</span></span>
1. <span data-ttu-id="25666-124">Wybierz przycisk **Dodaj** , aby dodać wiersz do zwolnienia do magazynu.</span><span class="sxs-lookup"><span data-stu-id="25666-124">Select **Add** to add the line to the release to the warehouse.</span></span> <span data-ttu-id="25666-125">Zauważ, że *domyślne* zasady konsolidacji wysyłki są stosowane w dolnym okienku.</span><span class="sxs-lookup"><span data-stu-id="25666-125">Notice that the *Default* shipment consolidation policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="25666-126">W dolnym okienku wybierz pozycję **Wybierz nowe zasady konsolidacji wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="25666-126">In the bottom pane, select **Select new shipment consolidation policy**.</span></span>
1. <span data-ttu-id="25666-127">Wybierz zasady umożliwiające konsolidację z innymi otwartymi wysyłkami tych samych zasad.</span><span class="sxs-lookup"><span data-stu-id="25666-127">Select a policy that allows for consolidation with other open shipments of the same policy.</span></span> <span data-ttu-id="25666-128">Na przykład wybierz zasady *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="25666-128">For example, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="25666-129">Wybierz pozycję **Zwolnij do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="25666-129">Select **Release to warehouse**.</span></span>
1. <span data-ttu-id="25666-130">Wybierz drugie i trzecie zamówienie sprzedaży utworzone dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="25666-130">Select the second and third sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="25666-131">Wybierz przycisk **Dodaj** , aby dodać wiersze do zwolnienia do magazynu.</span><span class="sxs-lookup"><span data-stu-id="25666-131">Select **Add** to add the lines to the release to the warehouse.</span></span> <span data-ttu-id="25666-132">Zauważ, że *domyślne* zasady są stosowane w dolnym okienku.</span><span class="sxs-lookup"><span data-stu-id="25666-132">Notice that the *Default* policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="25666-133">Wybierz drugi wiersz, a następnie w polu **Wybierz nowe zasady konsolidacji wysyłki** wybierz zasady *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="25666-133">Select the second line, and then, in the **Select new shipment consolidation policy** field, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="25666-134">Wybierz pozycję **Zwolnij do magazynu** dla obu wierszy.</span><span class="sxs-lookup"><span data-stu-id="25666-134">Select **Release to warehouse** for both lines.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="25666-135">Weryfikowanie wysyłek</span><span class="sxs-lookup"><span data-stu-id="25666-135">Verify the shipments</span></span>

<span data-ttu-id="25666-136">Powinny zostać utworzone dwie następujące wysyłki:</span><span class="sxs-lookup"><span data-stu-id="25666-136">Two shipments should have been created:</span></span>

- <span data-ttu-id="25666-137">Pierwsza wysyłka zawiera dwa wiersze i została utworzona za pomocą zasad konsolidacji wysyłki *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="25666-137">The first shipment contains two lines and was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>
- <span data-ttu-id="25666-138">Druga wysyłka zawiera jeden wiersz i została utworzona za pomocą zasad konsolidacji wysyłki *Domyślne*.</span><span class="sxs-lookup"><span data-stu-id="25666-138">The second shipment contains one line and was created by using the *Default* shipment consolidation policy.</span></span>

<span data-ttu-id="25666-139">Aby przejrzeć utworzone wysyłki, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="25666-139">Follow these steps to review the shipments that were created.</span></span>

1. <span data-ttu-id="25666-140">Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="25666-140">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="25666-141">Znajdź i wybierz wymaganą wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="25666-141">Find and select the required shipment.</span></span>
1. <span data-ttu-id="25666-142">W polu **Zasady konsolidacji wysyłki** przejrzyj zasady konsolidacji, które zostały użyte podczas tworzenia wysyłki.</span><span class="sxs-lookup"><span data-stu-id="25666-142">In the **Shipment consolidation policy** field, review the consolidation policy that was used when the shipment was created.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25666-143">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="25666-143">Additional resources</span></span>

- [<span data-ttu-id="25666-144">Zasady konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="25666-144">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="25666-145">Konfigurowanie zasad konsolidacji wysyłki</span><span class="sxs-lookup"><span data-stu-id="25666-145">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
