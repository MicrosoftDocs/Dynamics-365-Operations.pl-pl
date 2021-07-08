---
title: Strategie pakowania kontenerów
description: W tym temacie opisano różnice między strategiami pakowania kontenerów i podano przykłady.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292768"
---
# <a name="container-packing-strategies"></a><span data-ttu-id="7ff3f-103">Strategie pakowania kontenerów</span><span class="sxs-lookup"><span data-stu-id="7ff3f-103">Container packing strategies</span></span>

<span data-ttu-id="7ff3f-104">*Strategia pakowania kontenerów* to strategia, która umożliwia definiowanie alokacji towarów między kontenerami.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-104">A *container packing strategy* is a strategy that you can use to define item allocations across containers.</span></span> <span data-ttu-id="7ff3f-105">W tym temacie wyjaśniono różnice pomiędzy strategiami *Pakowaniem do wszystkich otwartych pojemników* i *Pakowaniem tylko do bieżącego pojemnika*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-105">This topic explains the differences between the *Pack into all open containers* and *Pack into current container only* strategies.</span></span>

- <span data-ttu-id="7ff3f-106">**Zapakuj we wszystkie otwarte kontenery** — system musi sprawdzić wszystkie otwarte kontenery, które zostały już utworzone podczas cyklu konteneryzacji, aby upewnić się, że towar dopasuje się do jednego z nich.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-106">**Pack into all open containers** – The system must check all open containers that have already been created during the containerization cycle, to make sure that the item will fit into one of them.</span></span> <span data-ttu-id="7ff3f-107">Podczas pakowania system sprawdza każdy towar w celu określenia, czy zmieści się w dowolnym z wcześniej utworzonych kontenerów.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-107">During packing, the system checks each item to determine whether it will fit into any of the previously created containers.</span></span> <span data-ttu-id="7ff3f-108">Jeśli przedmiot nie mieści się w istniejącym pojemniku, system tworzy nowy pojemnik i kontynuuje pracę aż do zakończenia pakowania całego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-108">If the item won't fit into an existing container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="7ff3f-109">Na przykład *n* zamówionych towarów wymaga konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-109">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="7ff3f-110">W najgorszym przypadku, za każdym razem, gdy system przetwarza element, który nie pasuje do żadnego istniejącego pojemnika, wykona łącznie (\[(*n* – 1) × (*n* + 1)\] ÷ 2) sprawdzeń, aby ocenić, czy element pasuje do istniejących pojemników.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-110">In the worst case, every time that the system processes an item that doesn't fit into any existing container, it will do a total of (\[(*n* – 1) × (*n* + 1)\] ÷ 2) checks to evaluate whether the item fits into the existing containers.</span></span>

- <span data-ttu-id="7ff3f-111">**Zapakuj tylko do obecnego kontenera** — system musi sprawdzić tylko ostatnio utworzony pojemnik, aby upewnić się, że element się w nim zmieści.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-111">**Pack into current container only** – The system must check only the most recently created container to make sure that the item will fit into it.</span></span> <span data-ttu-id="7ff3f-112">Podczas pakowania system sprawdza każdy element, aby określić, czy zmieści się do ostatnio utworzonego pojemnika.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-112">During packing, the system checks each item to determine whether it will fit into the most recently created container.</span></span> <span data-ttu-id="7ff3f-113">Jeśli przedmiot nie mieści się w istniejącym pojemniku, system tworzy nowy pojemnik i kontynuuje pracę aż do zakończenia pakowania całego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-113">If the item won't fit into that container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="7ff3f-114">Na przykład *n* zamówionych towarów wymaga konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-114">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="7ff3f-115">W takim przypadku system będzie sprawdzać łącznie (*n* – 1) w celu sprawdzenia, czy towar mieści się w kontenerach.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-115">In the worst case, the system will do a total of (*n* – 1) checks to evaluate whether the item fits into the containers.</span></span>

## <a name="example-of-the-flow-for-container-packing-strategies"></a><span data-ttu-id="7ff3f-116">Przykład przepływu strategii pakowania kontenerów</span><span class="sxs-lookup"><span data-stu-id="7ff3f-116">Example of the flow for container packing strategies</span></span>

<span data-ttu-id="7ff3f-117">Ustawiono następujące elementy do konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-117">You set up the following items for containerization.</span></span>

| <span data-ttu-id="7ff3f-118">Pozycja</span><span class="sxs-lookup"><span data-stu-id="7ff3f-118">Item</span></span> | <span data-ttu-id="7ff3f-119">Wymiary fizyczne (szerokość × wysokości × wysokości)</span><span class="sxs-lookup"><span data-stu-id="7ff3f-119">Physical dimensions (width × depth × height)</span></span> | <span data-ttu-id="7ff3f-120">Masa</span><span class="sxs-lookup"><span data-stu-id="7ff3f-120">Weight</span></span> |
|---|---|---|
| <span data-ttu-id="7ff3f-121">Kabel HDMI 6'</span><span class="sxs-lookup"><span data-stu-id="7ff3f-121">HDMI Cable 6'</span></span> | <span data-ttu-id="7ff3f-122">1 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="7ff3f-122">1 × 1 × 1</span></span> | <span data-ttu-id="7ff3f-123">1</span><span class="sxs-lookup"><span data-stu-id="7ff3f-123">1</span></span> |
| <span data-ttu-id="7ff3f-124">Kabel HDMI 12'</span><span class="sxs-lookup"><span data-stu-id="7ff3f-124">HDMI Cable 12'</span></span> | <span data-ttu-id="7ff3f-125">2 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="7ff3f-125">2 × 1 × 1</span></span> | <span data-ttu-id="7ff3f-126">1</span><span class="sxs-lookup"><span data-stu-id="7ff3f-126">1</span></span> |
| <span data-ttu-id="7ff3f-127">Kabel HDMI 18'</span><span class="sxs-lookup"><span data-stu-id="7ff3f-127">HDMI Cable 18'</span></span> | <span data-ttu-id="7ff3f-128">3 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="7ff3f-128">3 × 1 × 1</span></span> | <span data-ttu-id="7ff3f-129">2</span><span class="sxs-lookup"><span data-stu-id="7ff3f-129">2</span></span> |

<span data-ttu-id="7ff3f-130">Można również skonfigurować następujące pole, które będzie używane do pakowania.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-130">You also set up the following box that will be used for packaging.</span></span>

| <span data-ttu-id="7ff3f-131">Kontener</span><span class="sxs-lookup"><span data-stu-id="7ff3f-131">Container</span></span> | <span data-ttu-id="7ff3f-132">Wymiary fizyczne (długość × szerokość × wysokość)</span><span class="sxs-lookup"><span data-stu-id="7ff3f-132">Physical dimensions (length × width × height)</span></span> | <span data-ttu-id="7ff3f-133">Masa</span><span class="sxs-lookup"><span data-stu-id="7ff3f-133">Weight</span></span> | <span data-ttu-id="7ff3f-134">Objętość</span><span class="sxs-lookup"><span data-stu-id="7ff3f-134">Volume</span></span> |
|---|---|---|---|
| <span data-ttu-id="7ff3f-135">Średnie pudełko</span><span class="sxs-lookup"><span data-stu-id="7ff3f-135">Medium Box</span></span> | <span data-ttu-id="7ff3f-136">6 × 3 × 2</span><span class="sxs-lookup"><span data-stu-id="7ff3f-136">6 × 3 × 2</span></span> | <span data-ttu-id="7ff3f-137">10</span><span class="sxs-lookup"><span data-stu-id="7ff3f-137">10</span></span> | <span data-ttu-id="7ff3f-138">100</span><span class="sxs-lookup"><span data-stu-id="7ff3f-138">100</span></span> |

<span data-ttu-id="7ff3f-139">Na koniec można skonfigurować zamówienie, które ma następujące produkty i ilości.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-139">Finally, you set up an order that has the following products and quantities.</span></span>

| <span data-ttu-id="7ff3f-140">Wiersz zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="7ff3f-140">Sales order line</span></span> | <span data-ttu-id="7ff3f-141">Ilość</span><span class="sxs-lookup"><span data-stu-id="7ff3f-141">Quantity</span></span> |
|---|---|
| <span data-ttu-id="7ff3f-142">Kabel HDMI 12'</span><span class="sxs-lookup"><span data-stu-id="7ff3f-142">HDMI Cable 12'</span></span> | <span data-ttu-id="7ff3f-143">9</span><span class="sxs-lookup"><span data-stu-id="7ff3f-143">9</span></span> |
| <span data-ttu-id="7ff3f-144">Kabel HDMI 18'</span><span class="sxs-lookup"><span data-stu-id="7ff3f-144">HDMI Cable 18'</span></span> | <span data-ttu-id="7ff3f-145">8</span><span class="sxs-lookup"><span data-stu-id="7ff3f-145">8</span></span> |
| <span data-ttu-id="7ff3f-146">Kabel HDMI 6'</span><span class="sxs-lookup"><span data-stu-id="7ff3f-146">HDMI Cable 6'</span></span> | <span data-ttu-id="7ff3f-147">13</span><span class="sxs-lookup"><span data-stu-id="7ff3f-147">13</span></span> |

<span data-ttu-id="7ff3f-148">Poniższa tabela podsumowuje działanie konteneryzacji w przypadku użycia strategii *Pakuj do wszystkich otwartych kontenerów* oraz strategii *Pakuj tylko do bieżącego kontenera*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-148">The following table summarizes how containerization works when you use the *Pack into all open containers* strategy and when you use the *Pack into current container only* strategy.</span></span>

| <span data-ttu-id="7ff3f-149">Zapakuj we wszystkie otwarte kontenery</span><span class="sxs-lookup"><span data-stu-id="7ff3f-149">Pack into all open containers</span></span> | <span data-ttu-id="7ff3f-150">Zapakuj do bieżącego kontenera</span><span class="sxs-lookup"><span data-stu-id="7ff3f-150">Pack into current container</span></span> |
|---|---|
| <p><span data-ttu-id="7ff3f-151">Kabel HDMI 12':</span><span class="sxs-lookup"><span data-stu-id="7ff3f-151">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="7ff3f-152">Tworzenie nowego typu kontenera, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-152">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="7ff3f-153">Umieść 9 ea w kontenerze CONT0001.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-153">Put 9 ea into container CONT0001.</span></span></li></ol> | <p><span data-ttu-id="7ff3f-154">Kabel HDMI 12':</span><span class="sxs-lookup"><span data-stu-id="7ff3f-154">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="7ff3f-155">Tworzenie nowego typu kontenera, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-155">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="7ff3f-156">Umieść 9 ea w kontenerze CONT0001.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-156">Put 9 ea into container CONT0001.</span></span></li></ol> |
| <p><span data-ttu-id="7ff3f-157">Kabel HDMI 18':</span><span class="sxs-lookup"><span data-stu-id="7ff3f-157">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="7ff3f-158">Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0001.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-158">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="7ff3f-159">Tworzenie nowego typu kontenera, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-159">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="7ff3f-160">Umieść 5 ea w kontenerze CONT0002.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-160">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="7ff3f-161">Tworzenie nowego typu kontenera, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-161">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="7ff3f-162">Umieść 3 ea w kontenerze CONT0003.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-162">Put 3 ea into container CONT0003.</span></span></li></ol> | <p><span data-ttu-id="7ff3f-163">Kabel HDMI 18':</span><span class="sxs-lookup"><span data-stu-id="7ff3f-163">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="7ff3f-164">Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0001.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-164">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="7ff3f-165">Tworzenie nowego typu kontenera, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-165">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="7ff3f-166">Umieść 5 ea w kontenerze CONT0002.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-166">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="7ff3f-167">Tworzenie nowego typu kontenera, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-167">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="7ff3f-168">Umieść 3 ea w kontenerze CONT0003.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-168">Put 3 ea into container CONT0003.</span></span></li></ol> |
| <p><span data-ttu-id="7ff3f-169">Kabel HDMI 6':</span><span class="sxs-lookup"><span data-stu-id="7ff3f-169">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="7ff3f-170">Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0001.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-170">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="7ff3f-171">Umieść 1 ea w kontenerze CONT0001.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-171">Put 1 ea into container CONT0001.</span></span></li><li><span data-ttu-id="7ff3f-172">Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0002.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-172">Check whether the item can fit into container CONT0002.</span></span></li><li><span data-ttu-id="7ff3f-173">Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0003.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-173">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="7ff3f-174">Umieść 4 ea w kontenerze CONT0003.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-174">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="7ff3f-175">Tworzenie nowego typu kontenera, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-175">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="7ff3f-176">Umieść 8 ea w kontenerze CONT0004.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-176">Put 8 ea into container CONT0004.</span></span></li></ol> | <p><span data-ttu-id="7ff3f-177">Kabel HDMI 6':</span><span class="sxs-lookup"><span data-stu-id="7ff3f-177">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="7ff3f-178">Sprawdź, czy pozycja może się zmieścić w kontenerze CONT0003.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-178">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="7ff3f-179">Umieść 4 ea w kontenerze CONT0003.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-179">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="7ff3f-180">Tworzenie nowego typu kontenera, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-180">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="7ff3f-181">Umieść 9 ea w kontenerze CONT0004.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-181">Put 9 ea into container CONT0004.</span></span></li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a><span data-ttu-id="7ff3f-182">Przykładowy scenariusz: Pakowanie pojedynczych zamówień do jednego pojemnika</span><span class="sxs-lookup"><span data-stu-id="7ff3f-182">Example scenario: Pack single orders per container</span></span>

<span data-ttu-id="7ff3f-183">W tej sekcji przedstawiono scenariusz, w którym system jest skonfigurowany do konsolidacji wielu zamówień w jedną przesyłkę.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-183">This section presents a scenario where the system is set up to consolidate multiple orders into one shipment.</span></span> <span data-ttu-id="7ff3f-184">Dlatego konteneryzacja będzie wykonywana z poziomu zamówienia sprzedaży, aby zapewnić, że każde zamówienie zawierające wiele produktów jest pakowane do własnego pojemnika.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-184">Therefore, containerization will be done from the sales order to ensure that every order that contains multiple products is packed into its own container.</span></span>

<span data-ttu-id="7ff3f-185">Funkcja ta pozwala na obsługę scenariuszy, w których do każdego pojemnika należy zapakować tylko jedno zamówienie sprzedaży, tak aby centrum dystrybucyjne mogło przeładowywać pełne pojemniki pomiędzy sklepami detalicznymi.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-185">This functionality lets you handle scenarios where you must pack only one sales order into each container, so that the distribution center can cross-dock full containers between retail stores.</span></span> <span data-ttu-id="7ff3f-186">Oprócz scenariuszy dla handlu detalicznego (zamówienie na sklep detaliczny i wysyłka do centrum dystrybucji w celu cross-dockingu) technika ta jest również powszechnie stosowana w szczupłych łańcuchach dostaw (zamówienie sprzedaży na linię produkcyjną just-in-time).</span><span class="sxs-lookup"><span data-stu-id="7ff3f-186">In addition to the retail scenarios (order per retail store and shipping to a distribution center for cross-docking) this technique is also commonly used in lean supply chains (sales order per just-in-time production line).</span></span>

<span data-ttu-id="7ff3f-187">Ten scenariusz pokazuje, jak można zmniejszyć liczbę pojemników, które są oceniane podczas pakowania, używając strategii *Pakować tylko do aktualnego kontenera* dla konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-187">This scenario shows how you can decrease the number of containers that are evaluated during packing by using the *Pack into current container only* strategy for containerization.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="7ff3f-188">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="7ff3f-188">Prerequisites</span></span>

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a><span data-ttu-id="7ff3f-189">Włącz funkcję Konsoliduj wysyłki w systemie</span><span class="sxs-lookup"><span data-stu-id="7ff3f-189">Turn on the Consolidate shipments feature in your system</span></span>

<span data-ttu-id="7ff3f-190">W tym scenariuszu jest używana funkcja *Konsoliduj wysyłki*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-190">This scenario uses the *Consolidate shipments* feature.</span></span> <span data-ttu-id="7ff3f-191">Jeśli ta funkcja nie jest jeszcze dostępna w systemie, należy ją włączyć za pomocą [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7ff3f-191">If that feature isn't already available in your system, you must turn it on by using [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

#### <a name="make-demo-data-available"></a><span data-ttu-id="7ff3f-192">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="7ff3f-192">Make demo data available</span></span>

<span data-ttu-id="7ff3f-193">Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-193">This scenario references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="7ff3f-194">Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-194">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

### <a name="inspect-or-create-container-types"></a><span data-ttu-id="7ff3f-195">Sprawdzanie lub tworzenie typów kontenerów</span><span class="sxs-lookup"><span data-stu-id="7ff3f-195">Inspect or create container types</span></span>

<span data-ttu-id="7ff3f-196">Aby sprawdzić typy kontenerów lub utworzyć w razie potrzeby nowe typy kontenerów, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-196">To inspect your container types, or to create new container types if they are required, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-197">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Kontenery** \> **Typy kontenerów**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-197">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>
1. <span data-ttu-id="7ff3f-198">Upewnij się, że każdy z poniższych typów kontenerów jest dostępny w danych demo.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-198">Make sure that each of the following container types is available in your demo data.</span></span> <span data-ttu-id="7ff3f-199">W razie potrzeby edytuj lub utwórz typy kontenerów.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-199">Edit or create container types as required.</span></span>

    - <span data-ttu-id="7ff3f-200">Typ kontenera 1:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-200">Container type 1:</span></span>

        - <span data-ttu-id="7ff3f-201">**Kod typu kontenera:** *Pudełko-duże*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-201">**Container type code:** *Box-Large*</span></span>
        - <span data-ttu-id="7ff3f-202">**Opis:** *duże pudełko*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-202">**Description:** *Large Box*</span></span>
        - <span data-ttu-id="7ff3f-203">**Maksymalna waga netto:** *100*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-203">**Maximum net weight:** *100*</span></span>
        - <span data-ttu-id="7ff3f-204">**Objętość:** *400*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-204">**Volume:** *400*</span></span>
        - <span data-ttu-id="7ff3f-205">**Długość:** *4*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-205">**Length:** *4*</span></span>
        - <span data-ttu-id="7ff3f-206">**Szerokość:** *10*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-206">**Width:** *10*</span></span>
        - <span data-ttu-id="7ff3f-207">**Wysokość:** *10*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-207">**Height:** *10*</span></span>

    - <span data-ttu-id="7ff3f-208">Typ kontenera 2:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-208">Container type 2:</span></span>

        - <span data-ttu-id="7ff3f-209">**Kod typu kontenera:** *Pudełko-średnie*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-209">**Container type code:** *Box-Medium*</span></span>
        - <span data-ttu-id="7ff3f-210">**Opis:** *średnie pudełko*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-210">**Description:** *Medium Box*</span></span>
        - <span data-ttu-id="7ff3f-211">**Maksymalna waga netto:** *50*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-211">**Maximum net weight:** *50*</span></span>
        - <span data-ttu-id="7ff3f-212">**Objętość:** *200*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-212">**Volume:** *200*</span></span>
        - <span data-ttu-id="7ff3f-213">**Długość:** *2*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-213">**Length:** *2*</span></span>
        - <span data-ttu-id="7ff3f-214">**Szerokość:** *10*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-214">**Width:** *10*</span></span>
        - <span data-ttu-id="7ff3f-215">**Wysokość:** *10*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-215">**Height:** *10*</span></span>

    - <span data-ttu-id="7ff3f-216">Typ kontenera 3:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-216">Container type 3:</span></span>

        - <span data-ttu-id="7ff3f-217">**Kod typu kontenera:** *Pudełko-małe*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-217">**Container type code:** *Box-Small*</span></span>
        - <span data-ttu-id="7ff3f-218">**Opis:** *małe pudełko*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-218">**Description:** *Small Box*</span></span>
        - <span data-ttu-id="7ff3f-219">**Maksymalna waga netto:** *20*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-219">**Maximum net weight:** *20*</span></span>
        - <span data-ttu-id="7ff3f-220">**Objętość:** *100*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-220">**Volume:** *100*</span></span>
        - <span data-ttu-id="7ff3f-221">**Długość:** *1*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-221">**Length:** *1*</span></span>
        - <span data-ttu-id="7ff3f-222">**Szerokość:** *10*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-222">**Width:** *10*</span></span>
        - <span data-ttu-id="7ff3f-223">**Wysokość:** *10*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-223">**Height:** *10*</span></span>

### <a name="inspect-or-create-container-groups"></a><span data-ttu-id="7ff3f-224">Sprawdzanie lub tworzenie grup kontenerów</span><span class="sxs-lookup"><span data-stu-id="7ff3f-224">Inspect or create container groups</span></span>

<span data-ttu-id="7ff3f-225">Aby sprawdzić grupy kontenerów lub utworzyć w razie potrzeby nowe grupy kontenerów, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-225">To inspect your container groups, or to create new container groups if they are required, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-226">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Kontenery** \> **Grupy kontenerów**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-226">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**.</span></span>
1. <span data-ttu-id="7ff3f-227">Upewnij się, że każda z poniższych grup kontenerów jest dostępna w danych demo.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-227">Make sure that the following container group is available in your demo data.</span></span> <span data-ttu-id="7ff3f-228">Jeśli nie jest dostępna, wybierz pozycję **Nowa**, aby ją utworzyć.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-228">If it isn't available, select **New** to create it.</span></span>

    - <span data-ttu-id="7ff3f-229">**Identyfikator grupy kontenerów:** *Pudełka*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-229">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="7ff3f-230">**Opis:** *rozmiary pudełek*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-230">**Description:** *Box sizes*</span></span>

1. <span data-ttu-id="7ff3f-231">Na skróconej karcie **Szczegóły** dotyczącej grupy kontenerów *pudełek* upewnij się, że istnieją następujące wiersze.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-231">On the **Details** FastTab for the *Boxes* container group, make sure that the following lines exist.</span></span> <span data-ttu-id="7ff3f-232">Jeśli nie, wybierz przycisk **Nowy**, aby go dodać.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-232">If they don't, select **New** to add them.</span></span>

    - <span data-ttu-id="7ff3f-233">Wiersz 1:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-233">Line 1:</span></span>

        - <span data-ttu-id="7ff3f-234">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-234">**Sequence number:** *1*</span></span>
        - <span data-ttu-id="7ff3f-235">**Typ kontenera:** *Pudełko-duże*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-235">**Container type:** *Box-Large*</span></span>
        - <span data-ttu-id="7ff3f-236">**Procent wykorzystania kontenera:** *100*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-236">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="7ff3f-237">Wiersz 2:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-237">Line 2:</span></span>

        - <span data-ttu-id="7ff3f-238">**Numer sekwencyjny:** *2*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-238">**Sequence number:** *2*</span></span>
        - <span data-ttu-id="7ff3f-239">**Typ kontenera:** *Pudełko-średnie*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-239">**Container type:** *Box-Medium*</span></span>
        - <span data-ttu-id="7ff3f-240">**Procent wykorzystania kontenera:** *100*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-240">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="7ff3f-241">Wiersz 3:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-241">Line 3:</span></span>

        - <span data-ttu-id="7ff3f-242">**Numer sekwencyjny:** *3*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-242">**Sequence number:** *3*</span></span>
        - <span data-ttu-id="7ff3f-243">**Typ kontenera:** *Pudełko-małe*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-243">**Container type:** *Box-Small*</span></span>
        - <span data-ttu-id="7ff3f-244">**Procent wykorzystania kontenera:** *100*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-244">**Container utilization percentage:** *100*</span></span>

### <a name="create-a-new-container-build-template"></a><span data-ttu-id="7ff3f-245">Utwórz nowy szablon kompilacji kontenera</span><span class="sxs-lookup"><span data-stu-id="7ff3f-245">Create a new container build template</span></span>

<span data-ttu-id="7ff3f-246">Aby utworzyć nowy szablon budowy kontenera, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-246">To create a new container build template, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-247">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Kontenery** \> **Szablony kompilacji kontenerów**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-247">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container build template**.</span></span>
1. <span data-ttu-id="7ff3f-248">Wybierz opcję **Nowy**, aby utworzyć szablon kompilacji kontenera, który ma następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-248">Select **New** to create a container build template that has the following settings:</span></span>

    - <span data-ttu-id="7ff3f-249">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-249">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="7ff3f-250">**Identyfikator szablonu kontenera:** *pudełko*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-250">**Container template ID:** *Box*</span></span>
    - <span data-ttu-id="7ff3f-251">**Identyfikator grupy kontenerów:** *Pudełka*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-251">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="7ff3f-252">**Typy kwerend podstawowych:** *wiersz alokacji sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-252">**Base query types:** *Sales allocation line*</span></span>
    - <span data-ttu-id="7ff3f-253">**Kod kroku grupy czynności:** *234*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-253">**Wave step code:** *234*</span></span>
    - <span data-ttu-id="7ff3f-254">**Zezwalaj na dzielenie pobrania:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-254">**Allow split picks:** *Yes*</span></span>
    - <span data-ttu-id="7ff3f-255">**Strategia pakowania kontenerów:** *Pakowanie tylko do bieżącego kontenera*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-255">**Container packing strategy:** *Pack into current container only*</span></span>
    - <span data-ttu-id="7ff3f-256">**Pakuj według jednostki dyrektywy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-256">**Pack by directive unit:** *No*</span></span>

1. <span data-ttu-id="7ff3f-257">Gdy wiersz dla nowego szablonu jest nadal zaznaczony, wybierz **Edytuj zapytanie** w oknie akcji.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-257">While the row for the new template is still selected, select **Edit query** on the Action Pane.</span></span>
1. <span data-ttu-id="7ff3f-258">Zostanie wyświetlone standardowe okno dialogowe edycji zapytania.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-258">A standard query editor dialog box appears.</span></span> <span data-ttu-id="7ff3f-259">Na karcie **Sortowanie** wybierz przycisk **Dodaj**, aby dodać wiersz zawierający następujące ustawienia do siatki:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-259">On the **Sorting** tab, select **Add** to add a row that has the following settings:</span></span>

    - <span data-ttu-id="7ff3f-260">**Tabela:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-260">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="7ff3f-261">**Tabela pochodna:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-261">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="7ff3f-262">**Pole:** *Numer zamówienia*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-262">**Field:** *Order number*</span></span>
    - <span data-ttu-id="7ff3f-263">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-263">**Search direction:** *Ascending*</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7ff3f-264">Aby uniknąć przechodzenia cyklicznie przez wszystkie pozostałe otwarte pojemniki i przyspieszyć proces sprawdzania jednego pojemnika na raz, oprócz sortowania według numeru porządkowego należy zastosować strategię *Pakuj tylko do bieżącego kontenera*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-264">To avoid cycling over all the other open containers, and to speed up the process by checking one container at a time, use the *Pack into current container only* strategy in addition to sorting by order number.</span></span> <span data-ttu-id="7ff3f-265">Ta kombinacja działa jak przerwa w szablonie pracy.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-265">This combination will work like a work break on a work template.</span></span>

1. <span data-ttu-id="7ff3f-266">Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-266">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="7ff3f-267">Gdy wiersz dla nowego szablonu jest nadal zaznaczony, wybierz **Ograniczenia dotyczące mieszania kontenerów** w oknie akcji.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-267">While the row for the new template is still selected, select **Container mixing constraints** on the Action Pane.</span></span>

    <span data-ttu-id="7ff3f-268">Dodasz teraz ograniczenie, które umieści elementy z jednego zamówienia w jednym kontenerze.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-268">You will now add a constraint that puts items from a single order into a single container.</span></span> <span data-ttu-id="7ff3f-269">Przedmioty z innego zamówienia zostaną umieszczone w osobnym kontenerze.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-269">Items from any other order will be put into a separate container.</span></span>

1. <span data-ttu-id="7ff3f-270">Wybierz opcję **Nowy**, aby utworzyć ograniczenie mieszania, które ma następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-270">Select **New** to create a mixing constraint that has the following settings:</span></span>

    - <span data-ttu-id="7ff3f-271">**Tabela:** *Zamówienia sprzedaży*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-271">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="7ff3f-272">**Wybierz pole:** *SalesId* (pole będzie wyświetlane w siatce jako *zamówienie sprzedaży*)</span><span class="sxs-lookup"><span data-stu-id="7ff3f-272">**Field select:** *SalesId* (The field will appear as *Sales order* in the grid.)</span></span>

1. <span data-ttu-id="7ff3f-273">Wybierz przycisk **OK**, aby dodać ograniczenie.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-273">Select **OK** to add the constraint.</span></span>
1. <span data-ttu-id="7ff3f-274">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-274">Close the page.</span></span>

### <a name="set-up-a-wave-template-for-containerization"></a><span data-ttu-id="7ff3f-275">Konfigurowanie szablonu grupy czynności dla konteneryzacji</span><span class="sxs-lookup"><span data-stu-id="7ff3f-275">Set up a wave template for containerization</span></span>

<span data-ttu-id="7ff3f-276">Aby skonfigurować szablon grupy czynności, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-276">To set up a wave template, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-277">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-277">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="7ff3f-278">W okienku listy w polu **Typ szablonu grupy czynności** ustaw wartość na *Wysyłka*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-278">In the list pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="7ff3f-279">Wybierz szablon **Konteneryzacji 63** na liście.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-279">Select the **63 Containerization** template in the list.</span></span>
1. <span data-ttu-id="7ff3f-280">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-280">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="7ff3f-281">Na skróconej karcie **Metody** w kolumnie **Wybrane metody** znajdź następujący wiersz:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-281">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="7ff3f-282">**Nazwa metody:** *konteneryzacja*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-282">**Method name:** *containerization*</span></span>
    - <span data-ttu-id="7ff3f-283">**Nazwa:** *Konteneryzacja*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-283">**Name:** *Containerization*</span></span>

1. <span data-ttu-id="7ff3f-284">Umożliwia ustawienie pola **Kodu kroku grupy czynności** dla tego wiersza na *234*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-284">Set the **Wave step code** field for the line to *234*.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="7ff3f-285">Konfigurowanie szablonów pracy</span><span class="sxs-lookup"><span data-stu-id="7ff3f-285">Set up a work template</span></span>

<span data-ttu-id="7ff3f-286">Aby skonfigurować szablon pracy, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-286">To set up a work template, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-287">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-287">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="7ff3f-288">Ustaw pole **Typ zlecenia pracy** na *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-288">Set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="7ff3f-289">W siatce **Omówienie** znajdź i wybierz szablon roboczy, który powinien być użyty do pakowania pojedynczych zamówień na pojemnik.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-289">In the **Overview** grid, find and select the work template that should be used for packing single orders per container.</span></span> <span data-ttu-id="7ff3f-290">W tym scenariuszu wybierz szablon **63 Pobranie do kontenera**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-290">For this scenario, select the **63 Pick to container** template.</span></span>
1. <span data-ttu-id="7ff3f-291">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-291">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="7ff3f-292">Zostanie wyświetlone standardowe okno dialogowe edycji zapytania.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-292">A standard query editor dialog box appears.</span></span> <span data-ttu-id="7ff3f-293">Dodaj następujące wiersze na karcie **Sortowanie**:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-293">On the **Sorting** tab, add the following lines:</span></span>

    - <span data-ttu-id="7ff3f-294">Wiersz 1:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-294">Line 1:</span></span>

        - <span data-ttu-id="7ff3f-295">**Tabela:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-295">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="7ff3f-296">**Tabela pochodna:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-296">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="7ff3f-297">**Pole:** *Identyfikator wysyłki*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-297">**Field:** *Shipment ID*</span></span>
        - <span data-ttu-id="7ff3f-298">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-298">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="7ff3f-299">Wiersz 2:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-299">Line 2:</span></span>

        - <span data-ttu-id="7ff3f-300">**Tabela:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-300">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="7ff3f-301">**Tabela pochodna:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-301">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="7ff3f-302">**Pole:** *Numer zamówienia*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-302">**Field:** *Order number*</span></span>
        - <span data-ttu-id="7ff3f-303">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-303">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="7ff3f-304">Wiersz 3:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-304">Line 3:</span></span>

        - <span data-ttu-id="7ff3f-305">**Tabela:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-305">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="7ff3f-306">**Tabela pochodna:** *Tymczasowe transakcje pracy*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-306">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="7ff3f-307">**Pole:** *Identyfikator kontenera*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-307">**Field:** *Container ID*</span></span>
        - <span data-ttu-id="7ff3f-308">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-308">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="7ff3f-309">Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-309">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="7ff3f-310">Zostanie wyświetlony następujący komunikat: „Grupowanie zostanie zresetowane, czy chcesz kontynuować?”</span><span class="sxs-lookup"><span data-stu-id="7ff3f-310">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="7ff3f-311">Wybierz przycisk **Tak**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-311">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="7ff3f-312">Gdy szablon **63 Pobierz do kontenera** jest nadal zaznaczony, wybierz **Nowe wiersze nagłówka roboczego** na panelu akcji.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-312">While the **63 Pick to container** template is still selected, select **Work header breaks** on the Action Pane.</span></span>

    <span data-ttu-id="7ff3f-313">Teraz zastosujesz ustawienia, aby podzielić pracę w taki sposób, aby każdy pojemnik w zamówieniu był powiązany z jednym zleceniem roboczym.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-313">You will now apply settings to break the work so that each container in the order is linked to one work order.</span></span>

1. <span data-ttu-id="7ff3f-314">Zaznacz pole wyboru **Grupuj według tego pola** dla każdego wiersza na stronie **podziału nagłówka pracy** (**Identyfikator wysyłki**, **Numer zamówienia** i **Identyfikator kontenera**).</span><span class="sxs-lookup"><span data-stu-id="7ff3f-314">Select the **Group by this field** checkbox for each row on the **Work header breaks** page (**Shipment ID**, **Order number**, and **Container ID**).</span></span>
1. <span data-ttu-id="7ff3f-315">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-315">Close the page.</span></span>

### <a name="set-up-shipment-consolidation-policies"></a><span data-ttu-id="7ff3f-316">Ustanowienie zasad konsolidacji przesyłek</span><span class="sxs-lookup"><span data-stu-id="7ff3f-316">Set up shipment consolidation policies</span></span>

<span data-ttu-id="7ff3f-317">Aby skonfigurować zasady konsolidacji przesyłek, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-317">To set up a shipment consolidation policy, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-318">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Zwolnij do magazynu \> Zasady konsolidacji wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-318">Go to **Warehouse management \> Setup \> Release to warehouse \> Shipment consolidation policies**.</span></span>
1. <span data-ttu-id="7ff3f-319">W oknie listy w polu **Typ zasady** na *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-319">In the list pane, set the **Policy type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="7ff3f-320">Na liście zaznacz **Domyślną** zasadę.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-320">Select the **Default** policy in the list.</span></span>
1. <span data-ttu-id="7ff3f-321">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-321">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="7ff3f-322">Na skróconej karcie **Pola konsolidacji** na liście **Wybrane pola** wybierz wiersz, w którym pole **Nazwa pola** ma wartość *Numer zamówienia*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-322">On the **Consolidation fields** FastTab, in the **Selected fields** list, select the row where the **Field name** field is set to *Order number*.</span></span>
1. <span data-ttu-id="7ff3f-323">Wybierz przycisk **usuń** ![Strzałka w lewo](media/backward-button.png), aby przenieść pole na listę **Pozostałe pola**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-323">Select the **Remove** button ![Left arrow](media/backward-button.png) to move the field to the **Remaining fields** list.</span></span>
1. <span data-ttu-id="7ff3f-324">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-324">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-physical-dimensions-for-the-product"></a><span data-ttu-id="7ff3f-325">Ustaw fizyczne wymiary produktu</span><span class="sxs-lookup"><span data-stu-id="7ff3f-325">Set up physical dimensions for the product</span></span>

<span data-ttu-id="7ff3f-326">Aby skonfigurować wymiary fizyczne dla produktów, które będą używane w tym scenariuszu, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-326">To set up physical dimensions for the products that will be used in this scenario, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-327">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-327">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="7ff3f-328">Wybierz produkt, dla którego pole **Kod pozycji** ma wartość *A0001*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-328">Select the product where the **Item number** field is set to *A0001*.</span></span>
1. <span data-ttu-id="7ff3f-329">W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Magazyn** wybierz **Wymiary fizyczne**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-329">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="7ff3f-330">Na stronie **Wymiary fizyczne** powinien być wyświetlony następujący wiersz w siatce:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-330">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="7ff3f-331">**Jednostka:** *pcs*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-331">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="7ff3f-332">**Waga brutto:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-332">**Gross weight:** *3.00*</span></span>
    - <span data-ttu-id="7ff3f-333">**Szerokość:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-333">**Width:** *2.00*</span></span>
    - <span data-ttu-id="7ff3f-334">**Głębokość:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-334">**Depth:** *2.00*</span></span>
    - <span data-ttu-id="7ff3f-335">**Wysokość:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-335">**Height:** *4.00*</span></span>
    - <span data-ttu-id="7ff3f-336">**Objętość:** *16,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-336">**Volume:** *16.00*</span></span>

1. <span data-ttu-id="7ff3f-337">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-337">Close the page.</span></span>
1. <span data-ttu-id="7ff3f-338">Wybierz produkt, dla którego pole **Kod pozycji** ma wartość *A0002*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-338">Select the product where the **Item number** field is set to *A0002*.</span></span>
1. <span data-ttu-id="7ff3f-339">W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Magazyn** wybierz **Wymiary fizyczne**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-339">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="7ff3f-340">Na stronie **Wymiary fizyczne** powinien być wyświetlony następujący wiersz w siatce:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-340">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="7ff3f-341">**Jednostka:** *pcs*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-341">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="7ff3f-342">**Waga brutto:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-342">**Gross weight:** *4.00*</span></span>
    - <span data-ttu-id="7ff3f-343">**Szerokość:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-343">**Width:** *3.00*</span></span>
    - <span data-ttu-id="7ff3f-344">**Głębokość:** *1,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-344">**Depth:** *1.00*</span></span>
    - <span data-ttu-id="7ff3f-345">**Wysokość:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-345">**Height:** *3.00*</span></span>
    - <span data-ttu-id="7ff3f-346">**Objętość:** *9,00*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-346">**Volume:** *9.00*</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="7ff3f-347">Utwórz zamówienie sprzedaży 1</span><span class="sxs-lookup"><span data-stu-id="7ff3f-347">Create sales order 1</span></span>

<span data-ttu-id="7ff3f-348">Aby utworzyć zamówienie sprzedaży, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-348">To create a sales order, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-349">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-349">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="7ff3f-350">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-350">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7ff3f-351">Pojawia się okno dialogowe do tworzenia nowego zlecenia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-351">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="7ff3f-352">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-352">Set the following values:</span></span>

    - <span data-ttu-id="7ff3f-353">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-353">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="7ff3f-354">**Magazyn:** *63*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-354">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="7ff3f-355">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-355">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="7ff3f-356">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-356">The new sales order is opened.</span></span> <span data-ttu-id="7ff3f-357">Na skróconej karcie **Wiersze zamówienia sprzedaży** dodaj sześć następujących wierszy sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-357">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="7ff3f-358">Wiersz 1:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-358">Line 1:</span></span>

        - <span data-ttu-id="7ff3f-359">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-359">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="7ff3f-360">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-360">**Quantity:** *2*</span></span>

    - <span data-ttu-id="7ff3f-361">Wiersz 2:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-361">Line 2:</span></span>

        - <span data-ttu-id="7ff3f-362">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-362">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="7ff3f-363">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-363">**Quantity:** *2*</span></span>

1. <span data-ttu-id="7ff3f-364">Wybierz pierwszy wiersz, a następnie wybierz opcję **Zapasy \> Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-364">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="7ff3f-365">Na stronie **Rezerwacje** wybierz **Rezerwacja partii**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-365">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="7ff3f-366">Następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-366">Then close the page.</span></span>
1. <span data-ttu-id="7ff3f-367">Powtórz poprzednie dwa kroki dla drugiego wiersza.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-367">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="7ff3f-368">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-368">Close the page.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="7ff3f-369">Utwórz zamówienie sprzedaży 2</span><span class="sxs-lookup"><span data-stu-id="7ff3f-369">Create sales order 2</span></span>

<span data-ttu-id="7ff3f-370">Aby utworzyć drugie zlecenie sprzedaży, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-370">To create a second sales order, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-371">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-371">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="7ff3f-372">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-372">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7ff3f-373">Pojawia się okno dialogowe do tworzenia nowego zlecenia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-373">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="7ff3f-374">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-374">Set the following values:</span></span>

    - <span data-ttu-id="7ff3f-375">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-375">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="7ff3f-376">**Magazyn:** *63*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-376">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="7ff3f-377">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-377">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="7ff3f-378">Nowe zamówienie zakupu (PO) zostało otwarte.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-378">The new sales order is opened.</span></span> <span data-ttu-id="7ff3f-379">Na skróconej karcie **Wiersze zamówienia sprzedaży** dodaj sześć następujących wierszy sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-379">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="7ff3f-380">Wiersz 1:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-380">Line 1:</span></span>

        - <span data-ttu-id="7ff3f-381">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-381">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="7ff3f-382">**Ilość:** *4*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-382">**Quantity:** *4*</span></span>

    - <span data-ttu-id="7ff3f-383">Wiersz 2:</span><span class="sxs-lookup"><span data-stu-id="7ff3f-383">Line 2:</span></span>

        - <span data-ttu-id="7ff3f-384">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-384">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="7ff3f-385">**Ilość:** *4*</span><span class="sxs-lookup"><span data-stu-id="7ff3f-385">**Quantity:** *4*</span></span>

1. <span data-ttu-id="7ff3f-386">Wybierz pierwszy wiersz, a następnie wybierz opcję **Zapasy \> Rezerwacja**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-386">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="7ff3f-387">Na stronie **Rezerwacje** wybierz **Rezerwacja partii**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-387">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="7ff3f-388">Następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-388">Then close the page.</span></span>
1. <span data-ttu-id="7ff3f-389">Powtórz poprzednie dwa kroki dla drugiego wiersza.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-389">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="7ff3f-390">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-390">Close the page.</span></span>

### <a name="create-the-load"></a><span data-ttu-id="7ff3f-391">Tworzenie obciążenia</span><span class="sxs-lookup"><span data-stu-id="7ff3f-391">Create the load</span></span>

<span data-ttu-id="7ff3f-392">Aby utworzyć obciążenie dla każdego zamówienia utworzonego w tym scenariuszu, a następnie zwolnić je do magazynu, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-392">To create a load for each order that you created for this scenario and then release it to the warehouse, follow these steps.</span></span>

1. <span data-ttu-id="7ff3f-393">Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-393">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="7ff3f-394">Na karcie **Wiersze sprzedaży** znajdź i wybierz wszystkie wiersze zamówienia sprzedaży w jednym z zamówień utworzonych dla tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-394">On the **Sales lines** tab, find and select all the sales order lines from the sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="7ff3f-395">W okienku akcji na karcie **Popyt i podaż** w grupie **Dodaj** kliknij opcję **Do nowego transportu**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-395">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span> <span data-ttu-id="7ff3f-396">Wybrane linie zleceń są dodawane do nowego ładunku.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-396">The selected order lines are added to a new load.</span></span>
1. <span data-ttu-id="7ff3f-397">W oknie dialogowym **Przypisanie szablonu ładunku** w polu **Identyfikator szablonu ładunku** wybierz szablon ładunku, na przykład *Kontener 40'*.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-397">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *40' Container*.</span></span>
1. <span data-ttu-id="7ff3f-398">Kliknij przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-398">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="7ff3f-399">W sekcji **Ładunki** znajdź i wybierz właśnie utworzony ładunek.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-399">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="7ff3f-400">Wybierz **Zwolnienie \> Zwolnij do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-400">Select **Release \> Release to warehouse**.</span></span>
1. <span data-ttu-id="7ff3f-401">Wybierz **OK** w oknie **Zwolnij do magazynu**, aby zwolnić wybrany ładunek do magazynu.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-401">In the **Release to warehouse** dialog box, select **OK** to release the selected load to the warehouse.</span></span>

### <a name="verify-the-shipments-and-containers"></a><span data-ttu-id="7ff3f-402">Weryfikowanie wysyłek i kontenerów</span><span class="sxs-lookup"><span data-stu-id="7ff3f-402">Verify the shipments and containers</span></span>

<span data-ttu-id="7ff3f-403">Następująca procedura umożliwia sprawdzenie utworzonych wysyłek.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-403">The following procedure lets you verify the shipments that have been created.</span></span> <span data-ttu-id="7ff3f-404">Użyj go do przejrzenia zamówienia, które utworzyłeś dla tego scenariusza, aby upewnić się, że uzyskałeś oczekiwane rezultaty.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-404">Use it to review the order that you created for this scenario, to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="7ff3f-405">Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-405">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="7ff3f-406">Znajdź i wybierz wysyłkę utworzoną dla ładunku, który właśnie został zwolniony.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-406">Find and select the shipment that was created for the load that you just released.</span></span>
1. <span data-ttu-id="7ff3f-407">W okienku akcji otwórz kartę **Transport** i wybierz opcję **Wyświetl kontenery**.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-407">On the Action Pane, on the **Transportation** tab, select **View containers**.</span></span>
1. <span data-ttu-id="7ff3f-408">Potwierdź, że pozycje z zamówień sprzedaży zostały skonteneryzowane do dwóch różnych pojemników.</span><span class="sxs-lookup"><span data-stu-id="7ff3f-408">Confirm that the items from the sales orders were containerized into two different containers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ff3f-409">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7ff3f-409">Additional resources</span></span>

- [<span data-ttu-id="7ff3f-410">Konteneryzacja</span><span class="sxs-lookup"><span data-stu-id="7ff3f-410">Containerization</span></span>](wave-containerization.md)
