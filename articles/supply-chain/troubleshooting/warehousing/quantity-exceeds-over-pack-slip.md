---
title: Ilość przekracza procent nadwyżki w dostawie podczas generowania dokumentu dostawy
description: Podczas generowania dokumentu pakowania ładunek wychodzący zawiera ilość przekraczającą wartość procentową nadwyżki dostawy.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1106322cc3772c1b671b7fa82fb74039c028ba35
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249154"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="e417c-103">Ilość przekracza procent nadwyżki w dostawie podczas generowania dokumentu dostawy</span><span class="sxs-lookup"><span data-stu-id="e417c-103">Quantity exceeds over-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="e417c-104">Kod błędu: SYS24920</span><span class="sxs-lookup"><span data-stu-id="e417c-104">Error code: SYS24920</span></span>

## <a name="symptoms"></a><span data-ttu-id="e417c-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="e417c-105">Symptoms</span></span>

<span data-ttu-id="e417c-106">Podczas generowania dokumentu pakowania ładunek wychodzący zawiera ilość przekraczającą wartość procentową nadwyżki dostawy.</span><span class="sxs-lookup"><span data-stu-id="e417c-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the over-delivery percentage.</span></span>

<span data-ttu-id="e417c-107">Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="e417c-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="e417c-108">Nadwyżka w dostawie w wierszu wynosi %1 procent, a dopuszczalny poziom to tylko %2 procent.</span><span class="sxs-lookup"><span data-stu-id="e417c-108">Overdelivery of line is %1 percent, but the allowed overdelivery is only %2 percent.</span></span>

<span data-ttu-id="e417c-109">Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="e417c-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="e417c-110">Powód</span><span class="sxs-lookup"><span data-stu-id="e417c-110">Cause</span></span>

<span data-ttu-id="e417c-111">Ilość pobrana dla ładunku lub przesyłki jest większa niż ilość zamówiona i nie mieści się w zakresie wartości procentowej nadwyżki dostawy.</span><span class="sxs-lookup"><span data-stu-id="e417c-111">The picked quantity for the load or shipment is more than the ordered quantity and isn't within the range of the over-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="e417c-112">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="e417c-112">Resolution</span></span>

<span data-ttu-id="e417c-113">Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="e417c-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="e417c-114">Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="e417c-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="e417c-115">Dostosuj ilość w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="e417c-115">Adjust the load line quantity.</span></span>
- <span data-ttu-id="e417c-116">Dostosuj wartość procentową nadwyżki dostawy.</span><span class="sxs-lookup"><span data-stu-id="e417c-116">Adjust the over-delivery percentage.</span></span>
- <span data-ttu-id="e417c-117">Odwróć i dokonaj korekt.</span><span class="sxs-lookup"><span data-stu-id="e417c-117">Reverse and make adjustments.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="e417c-118">Dostosuj ilość w wierszu ładunku</span><span class="sxs-lookup"><span data-stu-id="e417c-118">Adjust the load line quantity</span></span>

<span data-ttu-id="e417c-119">Do regulacji ilości przewodu ładunkowego należy użyć następującej procedury.</span><span class="sxs-lookup"><span data-stu-id="e417c-119">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="e417c-120">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="e417c-120">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e417c-121">Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="e417c-121">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="e417c-122">Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="e417c-122">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="e417c-123">Na karcie  **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent nadwyżki w dostawie.</span><span class="sxs-lookup"><span data-stu-id="e417c-123">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="e417c-124">Wybierz pozycję **Zmniejsz pobraną ilość**, aby dostosować pobraną ilość.</span><span class="sxs-lookup"><span data-stu-id="e417c-124">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="e417c-125">Na karcie  **Szczegóły wiersza** wybierz **Zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="e417c-125">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="e417c-126">Ustaw pole **Ilość** na ilość pobraną (czyli wartość pola **Ilość utworzona**), aby można było rozpocząć generowanie kartonu.</span><span class="sxs-lookup"><span data-stu-id="e417c-126">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="adjust-the-over-delivery-percentage"></a><span data-ttu-id="e417c-127">Dostosuj wartość procentową nadwyżki dostawy</span><span class="sxs-lookup"><span data-stu-id="e417c-127">Adjust the over-delivery percentage</span></span>

<span data-ttu-id="e417c-128">Aby dostosować wartość procentową nadwyżki dostawy, należy skorzystać z poniższej procedury.</span><span class="sxs-lookup"><span data-stu-id="e417c-128">Use the following procedure to adjust the over-delivery percentage.</span></span>

1. <span data-ttu-id="e417c-129">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="e417c-129">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="e417c-130">Wybierz zlecenie sprzedaży, dla którego nie można wysłać dokumentu pakowania dla ładunku.</span><span class="sxs-lookup"><span data-stu-id="e417c-130">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="e417c-131">Na karcie  **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży dla pozycji, która przekracza procent nadwyżki w dostawie.</span><span class="sxs-lookup"><span data-stu-id="e417c-131">On the **Sales order lines** tab, select the sales order line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="e417c-132">Na karcie  **Szczegóły wiersza** wybierz **Dostawa**.</span><span class="sxs-lookup"><span data-stu-id="e417c-132">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="e417c-133">W polu **Nadwyżka w dostawie** ustaw większą wartość procentową, która mieści się w ilości pobrania w stosunku do ilości ładunku, aby było można przejść dalej w sprawie dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="e417c-133">Set the **Overdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="e417c-134">Odwróć i dokonaj korekt</span><span class="sxs-lookup"><span data-stu-id="e417c-134">Reverse and make adjustments</span></span>

<span data-ttu-id="e417c-135">Odwróć wszystko, co zostało zaksięgowane dla danego ładunku (na przykład dowód pakowania, potwierdzenie wysyłki i pracę), dokonaj korekty zamówienia sprzedaży, ponownie zwolnij zamówienie do magazynu i zakończ procedurę wysyłki.</span><span class="sxs-lookup"><span data-stu-id="e417c-135">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="e417c-136">Poniższa procedura służy do anulowania dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="e417c-136">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="e417c-137">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="e417c-137">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e417c-138">Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Kasowanie dokumentu dostawy**.</span><span class="sxs-lookup"><span data-stu-id="e417c-138">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="e417c-139">Poniższa procedura umożliwia cofnięcie potwierdzenia wysyłki.</span><span class="sxs-lookup"><span data-stu-id="e417c-139">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="e417c-140">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="e417c-140">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e417c-141">Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="e417c-141">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="e417c-142">W celu odwrócenia pracy należy zastosować następującą procedurę.</span><span class="sxs-lookup"><span data-stu-id="e417c-142">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="e417c-143">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="e417c-143">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e417c-144">W okienku akcji, na karcie  **Ładunek**, w grupie  **Praca** wybierz pozycję  **Cofnięcie pracy**.</span><span class="sxs-lookup"><span data-stu-id="e417c-144">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
