---
title: Ilość przekracza procent niedoboru w dostawie podczas generowania dokumentu dostawy
description: Podczas generowania dokumentu pakowania ładunek wychodzący zawiera ilość przekraczającą wartość procentową niedoboru dostawy.
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
ms.openlocfilehash: ecdd377d12faf40f64736e93671dcf42ff132403
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249152"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="bdab4-103">Ilość przekracza procent niedoboru w dostawie podczas generowania dokumentu dostawy</span><span class="sxs-lookup"><span data-stu-id="bdab4-103">Quantity exceeds under-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="bdab4-104">Kod błędu: SYS24921</span><span class="sxs-lookup"><span data-stu-id="bdab4-104">Error code: SYS24921</span></span>

## <a name="symptoms"></a><span data-ttu-id="bdab4-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="bdab4-105">Symptoms</span></span>

<span data-ttu-id="bdab4-106">Podczas generowania dokumentu pakowania ładunek wychodzący zawiera ilość przekraczającą wartość procentową niedoboru dostawy.</span><span class="sxs-lookup"><span data-stu-id="bdab4-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the under-delivery percentage.</span></span>

<span data-ttu-id="bdab4-107">Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="bdab4-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="bdab4-108">Niedobór w dostawie w wierszu wynosi %1 procent, a dopuszczalny poziom to tylko %2 procent.</span><span class="sxs-lookup"><span data-stu-id="bdab4-108">Underdelivery of line is %1 percent, but the allowed underdelivery is only %2 percent.</span></span>

<span data-ttu-id="bdab4-109">Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="bdab4-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="bdab4-110">Powód</span><span class="sxs-lookup"><span data-stu-id="bdab4-110">Cause</span></span>

<span data-ttu-id="bdab4-111">Ilość pobrana dla ładunku lub przesyłki jest mniejsza niż ilość zamówiona i nie mieści się w zakresie wartości procentowej niedoboru dostawy.</span><span class="sxs-lookup"><span data-stu-id="bdab4-111">The picked quantity for the load or shipment is less than the ordered quantity and isn't within the range of the under-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="bdab4-112">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="bdab4-112">Resolution</span></span>

<span data-ttu-id="bdab4-113">Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="bdab4-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="bdab4-114">Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="bdab4-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="bdab4-115">Dostosuj wartość procentową niedoboru dostawy.</span><span class="sxs-lookup"><span data-stu-id="bdab4-115">Adjust the under-delivery percentage.</span></span>
- <span data-ttu-id="bdab4-116">Odwróć i dokonaj korekt.</span><span class="sxs-lookup"><span data-stu-id="bdab4-116">Reverse and make adjustments.</span></span>

### <a name="adjust-the-under-delivery-percentage"></a><span data-ttu-id="bdab4-117">Dostosuj wartość procentową niedoboru dostawy</span><span class="sxs-lookup"><span data-stu-id="bdab4-117">Adjust the under-delivery percentage</span></span>

<span data-ttu-id="bdab4-118">Aby dostosować wartość procentową niedoboru dostawy, należy skorzystać z poniższej procedury.</span><span class="sxs-lookup"><span data-stu-id="bdab4-118">Use the following procedure to adjust the under-delivery percentage.</span></span>

1. <span data-ttu-id="bdab4-119">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="bdab4-119">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="bdab4-120">Wybierz zlecenie sprzedaży, dla którego nie można wysłać dokumentu pakowania dla ładunku.</span><span class="sxs-lookup"><span data-stu-id="bdab4-120">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="bdab4-121">Na karcie  **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży dla pozycji, która przekracza procent niedoboru w dostawie.</span><span class="sxs-lookup"><span data-stu-id="bdab4-121">On the **Sales order lines** tab, select the sales order line for the item that exceeds the under-delivery percentage.</span></span>
1. <span data-ttu-id="bdab4-122">Na karcie  **Szczegóły wiersza** wybierz **Dostawa**.</span><span class="sxs-lookup"><span data-stu-id="bdab4-122">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="bdab4-123">W polu **Niedobór w dostawie** ustaw większą wartość procentową, która mieści się w ilości pobrania w stosunku do ilości ładunku, aby było można przejść dalej w sprawie dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="bdab4-123">Set the **Underdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="bdab4-124">Odwróć i dokonaj korekt</span><span class="sxs-lookup"><span data-stu-id="bdab4-124">Reverse and make adjustments</span></span>

<span data-ttu-id="bdab4-125">Odwróć wszystko, co zostało zaksięgowane dla danego ładunku (na przykład dowód pakowania, potwierdzenie wysyłki i pracę), dokonaj korekty zamówienia sprzedaży, ponownie zwolnij zamówienie do magazynu i zakończ procedurę wysyłki.</span><span class="sxs-lookup"><span data-stu-id="bdab4-125">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="bdab4-126">Poniższa procedura służy do anulowania dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="bdab4-126">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="bdab4-127">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="bdab4-127">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="bdab4-128">Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Kasowanie dokumentu dostawy**.</span><span class="sxs-lookup"><span data-stu-id="bdab4-128">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="bdab4-129">Poniższa procedura umożliwia cofnięcie potwierdzenia wysyłki.</span><span class="sxs-lookup"><span data-stu-id="bdab4-129">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="bdab4-130">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="bdab4-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="bdab4-131">Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="bdab4-131">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="bdab4-132">W celu odwrócenia pracy należy zastosować następującą procedurę.</span><span class="sxs-lookup"><span data-stu-id="bdab4-132">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="bdab4-133">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="bdab4-133">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="bdab4-134">W okienku akcji, na karcie  **Ładunek**, w grupie  **Praca** wybierz pozycję  **Cofnięcie pracy**.</span><span class="sxs-lookup"><span data-stu-id="bdab4-134">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
