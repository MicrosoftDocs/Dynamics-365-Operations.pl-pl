---
title: Korekta zapasów w magazynie
description: Ten temat zawiera informacje dotyczące arkusza korekt zapasów magazynowych i przetwarzania w przypadku używania jednostek skalowania.
author: perlynne
manager: tfehr
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: be386539ea7addf20256ac2b1f8a2a72736fcbec
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938233"
---
# <a name="warehouse-inventory-adjustment"></a><span data-ttu-id="95876-103">Korekta zapasów w magazynie</span><span class="sxs-lookup"><span data-stu-id="95876-103">Warehouse inventory adjustment</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="95876-104">Funkcja korygowania zapasów magazynowych jest używana podczas uruchamiania jednostek skalowania chmury i urządzenia brzegowego w przypadku [obciążeń produkcyjnych](cloud-edge-workload-manufacturing.md) oraz [obciążeń zarządzania magazynu](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="95876-104">The Warehouse inventory adjustment feature is used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="95876-105">Jeśli pracownik wykonuje korektę zapasów za pomocą aplikacji magazynu na obciążeniu zarządzania magazynem jednostek skalowania, fizyczna aktualizacja dostępnych zapasów musi zostać przetworzona przez zadanie wsadowe **Arkusz korekt zapasów magazynowych**, które uruchamia się i planuje, wybierając pozycję **Zarządzanie magazynem > Zadania okresowe > Arkusz korekt zapasów magazynowych**.</span><span class="sxs-lookup"><span data-stu-id="95876-105">When a worker does an inventory adjustment using the warehouse app against a scale unit warehouse management workload, the physical on-hand update must be processed by the **Warehouse inventory adjustment journal** batch job, which you run and schedule by going to **Warehouse management > Periodic tasks > Warehouse inventory adjustment journal**.</span></span>

<span data-ttu-id="95876-106">W następujących procesach pracy w aplikacji magazynowej jest obecnie dostępny **arkusz korekt zapasów magazynowych** na obciążeniach pracą jednostek skalowania:</span><span class="sxs-lookup"><span data-stu-id="95876-106">The following warehouse app work processes currently use the **Warehouse inventory adjustment journal** on scale unit workloads:</span></span>

- <span data-ttu-id="95876-107">Korekta wewnętrzna/zewnętrzna</span><span class="sxs-lookup"><span data-stu-id="95876-107">Adjustment in/out</span></span>
- <span data-ttu-id="95876-108">Inwentaryzacja ciągła</span><span class="sxs-lookup"><span data-stu-id="95876-108">Cycle counting</span></span>
- <span data-ttu-id="95876-109">Ładowanie numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="95876-109">License plate loading</span></span>

<span data-ttu-id="95876-110">Niektóre transakcje magazynowe są tworzone jako część procesu korekty zapasów w chmurze i urządzeniach brzegowych, ponieważ wdrożenia centrum i jednostki skalowania mają wspólne rekordy zapasów.</span><span class="sxs-lookup"><span data-stu-id="95876-110">Several inventory transactions are created as part of cloud and edge an inventory adjustment process because the hub and scale unit deployments share the inventory records.</span></span>

## <a name="inventory-adjustment-example"></a><span data-ttu-id="95876-111">Przykład korekty zapasów</span><span class="sxs-lookup"><span data-stu-id="95876-111">Inventory adjustment example</span></span>

<span data-ttu-id="95876-112">W tym przykładzie pracownik magazynu używa aplikacji magazynu do zarejestrowania dodania dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="95876-112">In this example, a warehouse worker has used the warehouse app to register the adding of on-hand inventory.</span></span>

<span data-ttu-id="95876-113">Najpierw obciążenie pracą jednostki skalowania powoduje utworzenie transakcji korekty zapasów magazynowych dodatniej korekty fizycznej, która jest następnie synchronizowana z centrum i powoduje zwiększenie dostępnych zapasów w centrum.</span><span class="sxs-lookup"><span data-stu-id="95876-113">First, the scale unit workload creates a warehouse inventory adjustment transaction for the positive physical adjustment, which is then synchronized to the hub and results in an increase of the on-hand inventory on the hub.</span></span>

| <span data-ttu-id="95876-114">Typ</span><span class="sxs-lookup"><span data-stu-id="95876-114">Type</span></span>                                    | <span data-ttu-id="95876-115">Jednostka skalowania</span><span class="sxs-lookup"><span data-stu-id="95876-115">Scale unit</span></span> | <span data-ttu-id="95876-116">Kierunek</span><span class="sxs-lookup"><span data-stu-id="95876-116">Direction</span></span> | <span data-ttu-id="95876-117">Piasta</span><span class="sxs-lookup"><span data-stu-id="95876-117">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="95876-118">Korekta zapasów w magazynie</span><span class="sxs-lookup"><span data-stu-id="95876-118">Warehouse inventory adjustment</span></span>          | <span data-ttu-id="95876-119">+1</span><span class="sxs-lookup"><span data-stu-id="95876-119">+1</span></span>         | ->        | <span data-ttu-id="95876-120">+1</span><span class="sxs-lookup"><span data-stu-id="95876-120">+1</span></span>  |

<span data-ttu-id="95876-121">Następnie centrum przetwarza księgowanie arkusza inwentaryzacji odbierane za pomocą [komunikatów procesora komunikatów](cloud-edge-message-processor-messages.md).</span><span class="sxs-lookup"><span data-stu-id="95876-121">The hub then processes a counting journal posting, which is received through [message processor messages](cloud-edge-message-processor-messages.md).</span></span> <span data-ttu-id="95876-122">W ten sposób są automatycznie aktualizowane dodatkowe dostępne zapasy.</span><span class="sxs-lookup"><span data-stu-id="95876-122">This updates the additional inventory on hand.</span></span> <span data-ttu-id="95876-123">Aby uniknąć podwójnego stanu dostępnych zapasów, centrum tworzy w ramach tego procesu transakcję przeciwstawną i usuwa poprzednio zarejestrowane dane o dostępnych zapasach, które są związane z korektą zapasów w magazynie.</span><span class="sxs-lookup"><span data-stu-id="95876-123">To prevent double inventory on hand, the hub creates an offset transaction as part of this process and removes the previously recorded on-hand inventory that is related to the warehouse inventory adjustment.</span></span>

| <span data-ttu-id="95876-124">Typ</span><span class="sxs-lookup"><span data-stu-id="95876-124">Type</span></span>                                    | <span data-ttu-id="95876-125">Jednostka skalowania</span><span class="sxs-lookup"><span data-stu-id="95876-125">Scale unit</span></span> | <span data-ttu-id="95876-126">Kierunek</span><span class="sxs-lookup"><span data-stu-id="95876-126">Direction</span></span> | <span data-ttu-id="95876-127">Piasta</span><span class="sxs-lookup"><span data-stu-id="95876-127">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="95876-128">Inwentaryzacja</span><span class="sxs-lookup"><span data-stu-id="95876-128">Counting</span></span>                                | <span data-ttu-id="95876-129">+1</span><span class="sxs-lookup"><span data-stu-id="95876-129">+1</span></span>         | <-        | <span data-ttu-id="95876-130">+1</span><span class="sxs-lookup"><span data-stu-id="95876-130">+1</span></span>  |
| <span data-ttu-id="95876-131">Korekta zapasów w magazynie (przeciwstawna)</span><span class="sxs-lookup"><span data-stu-id="95876-131">Warehouse inventory adjustment (Offset)</span></span> | <span data-ttu-id="95876-132">-1</span><span class="sxs-lookup"><span data-stu-id="95876-132">-1</span></span>         | <-        | <span data-ttu-id="95876-133">-1</span><span class="sxs-lookup"><span data-stu-id="95876-133">-1</span></span>  |

<span data-ttu-id="95876-134">Po utworzeniu **arkusza korekty zapasów magazynowych** centrum przez jednostkę skalowania można przeglądać zarówno **arkusz inwentaryzacji**, jak i **arkusz przeciwstawny**, które są tworzone przez centrum w procesie korekty.</span><span class="sxs-lookup"><span data-stu-id="95876-134">After a scale unit has created a **Warehouse inventory adjustment journal** on the hub, you can review both the **Counting journal** and the **Offset journal**, which are created by the hub as part of the adjustment process.</span></span>

<span data-ttu-id="95876-135">Aby przejrzeć te wpisy arkusza i transakcję w Supply Chain Management, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="95876-135">You can review each of these journal entries and transaction in Supply Chain Management by doing the following steps:</span></span>

1. <span data-ttu-id="95876-136">Zaloguj się do jednostki skalowania.</span><span class="sxs-lookup"><span data-stu-id="95876-136">Sign in on the scale unit.</span></span>
1. <span data-ttu-id="95876-137">Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Arkusz korekty zapasów w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="95876-137">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="95876-138">Na stronie **Arkusz korekt zapasów w magazynie** znajdź i otwórz arkusz, w których zanotowana jest zmiana dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="95876-138">On the **Warehouse inventory adjustment journal** page, find and open the journal that recorded the on-hand inventory change.</span></span> <span data-ttu-id="95876-139">Sekcja **Wiersze arkusza** zawiera poszczególne korekty zarejestrowane przez ten arkusz.</span><span class="sxs-lookup"><span data-stu-id="95876-139">The **Journal lines** section shows each adjustment recorded by this journal.</span></span>
1. <span data-ttu-id="95876-140">Zaloguj się do centrum.</span><span class="sxs-lookup"><span data-stu-id="95876-140">Sign in on the hub.</span></span>
1. <span data-ttu-id="95876-141">Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Arkusz korekty zapasów w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="95876-141">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="95876-142">Na stronie **Arkusz korekt zapasów w magazynie** powinien być wyświetlony ten sam arkusz, jeśli centrum i jednostka skalowania zostały zsynchronizowane.</span><span class="sxs-lookup"><span data-stu-id="95876-142">On the **Warehouse inventory adjustment journal** page, you should see the same journal listed if the hub and scale unit have synced.</span></span>
1. <span data-ttu-id="95876-143">Otwórz arkusz.</span><span class="sxs-lookup"><span data-stu-id="95876-143">Open the journal.</span></span> <span data-ttu-id="95876-144">Jeśli [komunikaty procesora komunikatów](cloud-edge-message-processor-messages.md) zostały przetworzone, w nagłówku będą wyświetlane łącza do **arkusza inwentaryzacji** i **arkusza przeciwstawnego**.</span><span class="sxs-lookup"><span data-stu-id="95876-144">If the [message processor messages](cloud-edge-message-processor-messages.md) have been processed, you will see links to the **Counting journal** and the **Offset journal** in the header.</span></span>
    - <span data-ttu-id="95876-145">**Arkusz inwentaryzacji** powinien mieć takie same wartości wymiarów jak wiersze arkusza.</span><span class="sxs-lookup"><span data-stu-id="95876-145">The **Counting journal** should show the same dimension values as the journal lines.</span></span>
    - <span data-ttu-id="95876-146">**Arkusz przeciwstawny** powinien wyświetlać transakcję przeciwstawną, która usuwa podwójną korektę zapasów.</span><span class="sxs-lookup"><span data-stu-id="95876-146">The **Offset journal** should show the offset, which removes the double inventory adjustment.</span></span>
    > [!NOTE]
    > <span data-ttu-id="95876-147">Po zakończeniu całej synchronizacji i przetwarzania **arkusz inwentaryzacji** i **arkusz przeciwstawny** są synchronizowane z powrotem z jednostką skalowania.</span><span class="sxs-lookup"><span data-stu-id="95876-147">When all syncing and processing is complete, the **Counting journal** and the **Offset journal** are synced back to the scale unit.</span></span> <span data-ttu-id="95876-148">Można je również wyświetlić ze odpowiedniej strony **Arkusz korekt zapasów magazynowych**.</span><span class="sxs-lookup"><span data-stu-id="95876-148">These can also be viewed from the relevant **Warehouse inventory adjustment journal** page.</span></span>
