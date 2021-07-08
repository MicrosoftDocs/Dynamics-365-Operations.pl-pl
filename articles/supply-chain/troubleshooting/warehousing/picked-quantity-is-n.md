---
title: Ilość pobrania nie jest wystarczająca podczas generowania dokumentu dostawy
description: Podczas generowania dowodu pakowania ładunek wychodzący zawiera pobraną ilość, która nie pasuje do utworzonej ilości roboczej na linii ładunkowej.
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
ms.openlocfilehash: fa6054dc26e4306ec16e37b0e6c320342ed40fe0
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249156"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a><span data-ttu-id="2a639-103">Ilość pobrania nie jest wystarczająca podczas generowania dokumentu dostawy</span><span class="sxs-lookup"><span data-stu-id="2a639-103">Picked quantity isn't sufficient during packing slip generation</span></span>

<span data-ttu-id="2a639-104">Kod błędu: SYS54073</span><span class="sxs-lookup"><span data-stu-id="2a639-104">Error code: SYS54073</span></span>

## <a name="symptoms"></a><span data-ttu-id="2a639-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="2a639-105">Symptoms</span></span>

<span data-ttu-id="2a639-106">Podczas generowania dowodu pakowania ładunek wychodzący zawiera pobraną ilość, która nie pasuje do utworzonej ilości roboczej na linii ładunkowej.</span><span class="sxs-lookup"><span data-stu-id="2a639-106">When you generate a packing slip, the outbound load contains a picked quantity that doesn't match the created work quantity on the load line.</span></span>

<span data-ttu-id="2a639-107">Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="2a639-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="2a639-108">%1 zostało pobrane, niewystarczający poziom zapasów do aktualizacji %2 - ilość pozostałych musi wynosić %3.</span><span class="sxs-lookup"><span data-stu-id="2a639-108">As %1 have been picked, it is not sufficient to update %2, when, subsequently, the remainder must be %3.</span></span>

<span data-ttu-id="2a639-109">Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="2a639-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="2a639-110">Powód</span><span class="sxs-lookup"><span data-stu-id="2a639-110">Cause</span></span>

<span data-ttu-id="2a639-111">Dokument dostawy nie może zostać wygenerowany w obecnym stanie, ponieważ może wystąpić jeden z poniższych warunków:</span><span class="sxs-lookup"><span data-stu-id="2a639-111">The packing slip can't be generated in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="2a639-112">Powiązana praca nie została jeszcze pobrana i przeniesiona do końcowej lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="2a639-112">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="2a639-113">Ilość pobrania pracy nie odpowiada utworzonej ilości pracy w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="2a639-113">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="2a639-114">Ilość wiersza załadunku, utworzona ilość pracy i pobrana ilość nie zgadzają się.</span><span class="sxs-lookup"><span data-stu-id="2a639-114">The load line quantity, work created quantity, and picked quantity don't match.</span></span>

## <a name="resolution"></a><span data-ttu-id="2a639-115">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="2a639-115">Resolution</span></span>

<span data-ttu-id="2a639-116">Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="2a639-116">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="2a639-117">Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="2a639-117">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="2a639-118">Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.</span><span class="sxs-lookup"><span data-stu-id="2a639-118">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="2a639-119">Dostosuj ilość w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="2a639-119">Adjust the load line quantity.</span></span>
- <span data-ttu-id="2a639-120">Cofnąć wszystkie rejestracje kompletacji i powtórzyć kompletację.</span><span class="sxs-lookup"><span data-stu-id="2a639-120">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="2a639-121">Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają</span><span class="sxs-lookup"><span data-stu-id="2a639-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="2a639-122">Poniższa procedura służy do przeglądu linii ładunkowych i upewnienia się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.</span><span class="sxs-lookup"><span data-stu-id="2a639-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="2a639-123">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="2a639-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="2a639-124">Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="2a639-124">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="2a639-125">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.</span><span class="sxs-lookup"><span data-stu-id="2a639-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="2a639-126">Zanotuj wartość pola **Ilość stworzonych prac**.</span><span class="sxs-lookup"><span data-stu-id="2a639-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="2a639-127">W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.</span><span class="sxs-lookup"><span data-stu-id="2a639-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="2a639-128">Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="2a639-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="2a639-129">Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.</span><span class="sxs-lookup"><span data-stu-id="2a639-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="2a639-130">Dostosuj ilość w wierszu ładunku</span><span class="sxs-lookup"><span data-stu-id="2a639-130">Adjust the load line quantity</span></span>

<span data-ttu-id="2a639-131">Do regulacji ilości przewodu ładunkowego należy użyć następującej procedury.</span><span class="sxs-lookup"><span data-stu-id="2a639-131">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="2a639-132">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="2a639-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="2a639-133">Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="2a639-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="2a639-134">Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="2a639-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="2a639-135">Na karcie  **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która powoduje problem.</span><span class="sxs-lookup"><span data-stu-id="2a639-135">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="2a639-136">Wybierz pozycję **Zmniejsz pobraną ilość**, aby dostosować pobraną ilość.</span><span class="sxs-lookup"><span data-stu-id="2a639-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="2a639-137">Ustaw pole **Zmniejsz wiersz ładunku**, aby odzwierciedlić dopasowania w linii obciążenia.</span><span class="sxs-lookup"><span data-stu-id="2a639-137">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="2a639-138">Cofnąć wszystkie rejestracje kompletacji i powtórzyć kompletację</span><span class="sxs-lookup"><span data-stu-id="2a639-138">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="2a639-139">Problem może wystąpić, ponieważ ktoś użył rejestracji kompletacji do zamknięcia linii ładunkowej bez pracy.</span><span class="sxs-lookup"><span data-stu-id="2a639-139">The issue might occur because someone used pick registration to close a load line without work.</span></span> <span data-ttu-id="2a639-140">W takim przypadku ręczna rejestracja kompletacji musi zostać cofnięta, a kompletacja musi zostać zakończona za pomocą aplikacji mobilnej Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="2a639-140">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="2a639-141">Aby odwrócić rejestrację frezów, należy postępować w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="2a639-141">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="2a639-142">Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="2a639-142">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="2a639-143">Wybierz zlecenie sprzedaży, dla którego nie można wysłać dokumentu pakowania dla ładunku.</span><span class="sxs-lookup"><span data-stu-id="2a639-143">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="2a639-144">Na karcie  **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży, dla których została wykonana rejestracja pobrania.</span><span class="sxs-lookup"><span data-stu-id="2a639-144">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="2a639-145">Wybierz pozycję **Aktualizuj wiersz \> Pobierz**, aby odebrać elementy.</span><span class="sxs-lookup"><span data-stu-id="2a639-145">Select **Update line \> Pick** to unpick the items.</span></span>
