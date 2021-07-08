---
title: Ilość, która próbujesz zaktualizować, przekracza ilość otrzymaną/dostarczoną.
description: Podczas generowania dowodu pakowania ładunek wychodzący zawiera ilość przekraczającą ilość roboczą, która została pobrana i zarezerwowana dla zamówienia sprzedaży.
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
ms.openlocfilehash: 66d9cd80cc61e00d1d88ab4f59d03054d746cdd9
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249157"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a><span data-ttu-id="2053d-103">Ilość, która próbujesz zaktualizować, przekracza ilość otrzymaną/dostarczoną</span><span class="sxs-lookup"><span data-stu-id="2053d-103">Quantity that you're trying to update exceeds the received/delivered quantity</span></span>

<span data-ttu-id="2053d-104">Kod błędu: SYS7676</span><span class="sxs-lookup"><span data-stu-id="2053d-104">Error code: SYS7676</span></span>

## <a name="symptoms"></a><span data-ttu-id="2053d-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="2053d-105">Symptoms</span></span>

<span data-ttu-id="2053d-106">Podczas generowania dowodu pakowania ładunek wychodzący zawiera ilość przekraczającą ilość roboczą, która została pobrana i zarezerwowana dla zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2053d-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the work quantity that was picked and reserved for the sales order.</span></span>

<span data-ttu-id="2053d-107">Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="2053d-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="2053d-108">Ilość, którą próbujesz zaktualizować, przekracza ilość przyjętą/dostarczoną.</span><span class="sxs-lookup"><span data-stu-id="2053d-108">The quantity that you are trying to update exceeds the quantity received/delivered.</span></span>

<span data-ttu-id="2053d-109">Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="2053d-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="2053d-110">Powód</span><span class="sxs-lookup"><span data-stu-id="2053d-110">Cause</span></span>

<span data-ttu-id="2053d-111">Ilość pobrania pracy nie odpowiada utworzonej ilości pracy w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="2053d-111">The picked work quantity doesn't match the created work quantity on the load line.</span></span> <span data-ttu-id="2053d-112">Na przykład problem ten może wystąpić, gdy ilość linii ładunkowej, ilość utworzona lub ilość pobrana nie jest dokładna.</span><span class="sxs-lookup"><span data-stu-id="2053d-112">For example, this issue might occur if the load line quantity, work created quantity, or picked quantity isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="2053d-113">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="2053d-113">Resolution</span></span>

<span data-ttu-id="2053d-114">Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="2053d-114">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="2053d-115">Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="2053d-115">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="2053d-116">Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.</span><span class="sxs-lookup"><span data-stu-id="2053d-116">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="2053d-117">Dostosuj ilość w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="2053d-117">Adjust the load line quantity.</span></span>
- <span data-ttu-id="2053d-118">Cofnąć wszystkie rejestracje kompletacji i powtórzyć kompletację.</span><span class="sxs-lookup"><span data-stu-id="2053d-118">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="2053d-119">Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają</span><span class="sxs-lookup"><span data-stu-id="2053d-119">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="2053d-120">Poniższa procedura służy do przeglądu linii ładunkowych i upewnienia się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.</span><span class="sxs-lookup"><span data-stu-id="2053d-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="2053d-121">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="2053d-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="2053d-122">Wybierz ładunek, dla którego wysyłka nie może zostać wygenerowana.</span><span class="sxs-lookup"><span data-stu-id="2053d-122">Select the load that the shipment can't be generated for.</span></span>
1. <span data-ttu-id="2053d-123">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.</span><span class="sxs-lookup"><span data-stu-id="2053d-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="2053d-124">Zanotuj wartość pola **Ilość stworzonych prac**.</span><span class="sxs-lookup"><span data-stu-id="2053d-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="2053d-125">W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.</span><span class="sxs-lookup"><span data-stu-id="2053d-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="2053d-126">Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="2053d-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="2053d-127">Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.</span><span class="sxs-lookup"><span data-stu-id="2053d-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="2053d-128">Dostosuj ilość w wierszu ładunku</span><span class="sxs-lookup"><span data-stu-id="2053d-128">Adjust the load line quantity</span></span>

<span data-ttu-id="2053d-129">Do regulacji ilości przewodu ładunkowego należy użyć następującej procedury.</span><span class="sxs-lookup"><span data-stu-id="2053d-129">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="2053d-130">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="2053d-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="2053d-131">Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="2053d-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="2053d-132">Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="2053d-132">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="2053d-133">Na karcie  **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która powoduje problem.</span><span class="sxs-lookup"><span data-stu-id="2053d-133">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="2053d-134">Wybierz pozycję **Zmniejsz pobraną ilość**, aby dostosować pobraną ilość.</span><span class="sxs-lookup"><span data-stu-id="2053d-134">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="2053d-135">Ustaw pole **Zmniejsz wiersz ładunku**, aby odzwierciedlić dopasowania w linii obciążenia.</span><span class="sxs-lookup"><span data-stu-id="2053d-135">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="2053d-136">Cofnąć wszystkie rejestracje kompletacji i powtórzyć kompletację</span><span class="sxs-lookup"><span data-stu-id="2053d-136">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="2053d-137">Jeśli ktoś użył rejestracji kompletacji do zamknięcia linii ładunkowej bez pracy, może wystąpić rozbieżność między ilością w linii ładunkowej a ilością pobraną.</span><span class="sxs-lookup"><span data-stu-id="2053d-137">If someone used pick registration to close a load line without work, a discrepancy can occur between the load line quantity and the picked quantity.</span></span> <span data-ttu-id="2053d-138">W takim przypadku ręczna rejestracja kompletacji musi zostać cofnięta, a kompletacja musi zostać zakończona za pomocą aplikacji mobilnej Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="2053d-138">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="2053d-139">Aby odwrócić rejestrację frezów, należy postępować w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="2053d-139">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="2053d-140">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="2053d-140">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="2053d-141">Wybierz zlecenie sprzedaży, dla którego nie można wysłać dokumentu pakowania dla ładunku.</span><span class="sxs-lookup"><span data-stu-id="2053d-141">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="2053d-142">Na karcie  **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży, dla których została wykonana rejestracja pobrania.</span><span class="sxs-lookup"><span data-stu-id="2053d-142">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="2053d-143">Wybierz pozycję **Aktualizuj wiersz \> Pobierz**, aby odebrać elementy.</span><span class="sxs-lookup"><span data-stu-id="2053d-143">Select **Update line \> Pick** to unpick the items.</span></span>
