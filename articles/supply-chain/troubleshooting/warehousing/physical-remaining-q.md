---
title: Pozostała ilość w jednostkach musi być różna od zera
description: Podczas generowania dowodu pakowania dane, które są do niego dostarczane, mają niezerową ilość zapasów, ale zerową ilość sprzedaży.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248798"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a><span data-ttu-id="44542-103">Pozostała ilość w jednostkach musi być różna od zera</span><span class="sxs-lookup"><span data-stu-id="44542-103">Physical remaining quantity in the unit must not be zero</span></span>

<span data-ttu-id="44542-104">Kod błędu: SYS19591</span><span class="sxs-lookup"><span data-stu-id="44542-104">Error code: SYS19591</span></span>

## <a name="symptoms"></a><span data-ttu-id="44542-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="44542-105">Symptoms</span></span>

<span data-ttu-id="44542-106">Podczas generowania dowodu pakowania dane, które są do niego dostarczane, mają niezerową ilość zapasów, ale zerową ilość sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="44542-106">When you generate a packing slip, the data that is supplied to it has a non-zero inventory quantity but a zero sales quantity.</span></span>

<span data-ttu-id="44542-107">Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="44542-107">When you try to generate the packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="44542-108">Pozostała ilość w jednostkach %1 musi być różna od zera.</span><span class="sxs-lookup"><span data-stu-id="44542-108">Physical remaining quantity in the unit %1 must be other than zero.</span></span>

<span data-ttu-id="44542-109">Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="44542-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="44542-110">Powód</span><span class="sxs-lookup"><span data-stu-id="44542-110">Cause</span></span>

<span data-ttu-id="44542-111">System ocenia fizyczną ilość pozostałą w jednostce magazynowej i fizyczną ilość pozostałą w jednostce wysyłkowej.</span><span class="sxs-lookup"><span data-stu-id="44542-111">The system evaluates the physical remaining quantity in the inventory unit and the physical remaining quantity in the shipping unit.</span></span> <span data-ttu-id="44542-112">Jeśli system stwierdzi, że fizyczna ilość pozostała w jednostce wysyłkowej wynosi 0 (zero), ale fizyczna ilość pozostała w jednostce inwentarzowej nie wynosi 0, nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="44542-112">If the system finds that the physical remaining quantity in the shipping unit is 0 (zero), but the physical remaining quantity in the inventory unit isn't 0, you can't generate the packing slip.</span></span> <span data-ttu-id="44542-113">Na przykład, ten problem może wystąpić, jeśli jednostka sprzedaży i jednostka magazynowa dla pozycji są różne, a konwersja między jednostkami nie jest dokładna.</span><span class="sxs-lookup"><span data-stu-id="44542-113">For example, this issue might occur if the sales unit and inventory unit for the item differ, and the conversion between units isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="44542-114">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="44542-114">Resolution</span></span>

<span data-ttu-id="44542-115">Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="44542-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="44542-116">Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="44542-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="44542-117">Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.</span><span class="sxs-lookup"><span data-stu-id="44542-117">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="44542-118">Przejrzyj swoje linie ładunkowe i wprowadź poprawki, aby upewnić się, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem.</span><span class="sxs-lookup"><span data-stu-id="44542-118">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>
- <span data-ttu-id="44542-119">Przejrzyj linie ładunkowe i dokonaj korekty, aby upewnić się, że jednostka i ilość są wyrównane z precyzją dziesiętną jednostki.</span><span class="sxs-lookup"><span data-stu-id="44542-119">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>
- <span data-ttu-id="44542-120">Upewnij się, że jednostka miary zapasów jest mniejsza niż jednostka miary sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="44542-120">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="44542-121">Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają</span><span class="sxs-lookup"><span data-stu-id="44542-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="44542-122">Poniższa procedura służy do przeglądu linii ładunkowych i upewnienia się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.</span><span class="sxs-lookup"><span data-stu-id="44542-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="44542-123">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="44542-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="44542-124">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="44542-124">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="44542-125">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.</span><span class="sxs-lookup"><span data-stu-id="44542-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="44542-126">Zanotuj wartość pola **Ilość stworzonych prac**.</span><span class="sxs-lookup"><span data-stu-id="44542-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="44542-127">W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.</span><span class="sxs-lookup"><span data-stu-id="44542-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="44542-128">Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="44542-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="44542-129">Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.</span><span class="sxs-lookup"><span data-stu-id="44542-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a><span data-ttu-id="44542-130">Przejrzyj swoje linie ładunkowe i wprowadź poprawki, aby upewnić się, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem</span><span class="sxs-lookup"><span data-stu-id="44542-130">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues</span></span>

<span data-ttu-id="44542-131">Skorzystaj z poniższej procedury, aby przejrzeć linie ładunkowe i wprowadzić poprawki w celu zapewnienia, że ilość może być czysto przeliczona bez problemów związanych z zaokrąglaniem.</span><span class="sxs-lookup"><span data-stu-id="44542-131">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>

1. <span data-ttu-id="44542-132">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="44542-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="44542-133">Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="44542-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="44542-134">Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="44542-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="44542-135">Na karcie  **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent nadwyżki w dostawie.</span><span class="sxs-lookup"><span data-stu-id="44542-135">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery.</span></span>
1. <span data-ttu-id="44542-136">Wybierz pozycję **Zmniejsz pobraną ilość**, aby dostosować pobraną ilość.</span><span class="sxs-lookup"><span data-stu-id="44542-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="44542-137">Na karcie  **Szczegóły wiersza** wybierz **Zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="44542-137">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="44542-138">Ustaw pole **Ilość** na ilość pobraną (czyli wartość pola **Ilość utworzona**), aby można było rozpocząć generowanie kartonu.</span><span class="sxs-lookup"><span data-stu-id="44542-138">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="44542-139">Przejrzyj linie ładunkowe i dokonaj korekty, aby upewnić się, że jednostka i ilość są wyrównane z precyzją dziesiętną jednostki</span><span class="sxs-lookup"><span data-stu-id="44542-139">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="44542-140">Korzystając z poniższej procedury, należy przejrzeć linie ładunkowe i dokonać korekty, aby upewnić się, że jednostka i ilość są wyrównane z dokładnością dziesiętną jednostki.</span><span class="sxs-lookup"><span data-stu-id="44542-140">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="44542-141">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="44542-141">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="44542-142">Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="44542-142">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="44542-143">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która powoduje problem.</span><span class="sxs-lookup"><span data-stu-id="44542-143">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="44542-144">Zanotuj wartość pola **Ilość** i **Jednostka**.</span><span class="sxs-lookup"><span data-stu-id="44542-144">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="44542-145">Wybierz kolejno opcje **Administrowanie organizacją \> Jednostki \> Jednostki**.</span><span class="sxs-lookup"><span data-stu-id="44542-145">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="44542-146">Wybierz jednostkę, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="44542-146">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="44542-147">W razie potrzeby dostosuj wartość pola **Dokładność dziesiętna**.</span><span class="sxs-lookup"><span data-stu-id="44542-147">Adjust the value of the **Decimal precision** field as required.</span></span>

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a><span data-ttu-id="44542-148">Upewnij się, że jednostka miary zapasów jest mniejsza niż jednostka miary sprzedaży</span><span class="sxs-lookup"><span data-stu-id="44542-148">Make sure that the inventory unit of measure is smaller than the sales unit of measure</span></span>

<span data-ttu-id="44542-149">Upewnij się, że jednostka miary zapasów jest mniejsza niż jednostka miary sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="44542-149">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span> <span data-ttu-id="44542-150">Rozważ ponowne skonfigurowanie jednostka miary pozycji w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="44542-150">Consider reconfiguring the unit of measure for the item as required.</span></span>
