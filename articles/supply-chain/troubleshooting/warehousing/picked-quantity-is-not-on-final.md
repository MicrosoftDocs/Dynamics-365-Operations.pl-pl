---
title: Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary
description: Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f3ebd47ffc85d4ca257b404579d60d679f7929b6
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301312"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="04e3e-103">Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary</span><span class="sxs-lookup"><span data-stu-id="04e3e-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="04e3e-104">Kod błędu: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="04e3e-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="04e3e-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="04e3e-105">Symptoms</span></span>

<span data-ttu-id="04e3e-106">Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="04e3e-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="04e3e-107">Niektóre towary wymagane w ładunku %1 nie zostały jeszcze pobrane i przeniesione do końcowej lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="04e3e-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="04e3e-108">W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="04e3e-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="04e3e-109">Powód</span><span class="sxs-lookup"><span data-stu-id="04e3e-109">Cause</span></span>

<span data-ttu-id="04e3e-110">Nie można potwierdzić ładunku lub wysyłki w jego bieżącym stanie, ponieważ może istnieć jeden z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="04e3e-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="04e3e-111">Powiązana praca nie została jeszcze pobrana i przeniesiona do końcowej lokalizacji wysyłki.</span><span class="sxs-lookup"><span data-stu-id="04e3e-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="04e3e-112">Ilość pobrania pracy nie odpowiada utworzonej ilości pracy w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="04e3e-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="04e3e-113">Dyrektywa lokalizacji została skonfigurowana z lokalizacją pakowania jako ostateczną lokalizacją wysyłki podczas korzystania z konteneryzacji szablonu grup czynności.</span><span class="sxs-lookup"><span data-stu-id="04e3e-113">The location directive has been configured with packing location as the final shipping location while using Wave template containerization.</span></span>

## <a name="resolution"></a><span data-ttu-id="04e3e-114">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="04e3e-114">Resolution</span></span>

<span data-ttu-id="04e3e-115">Ładunek lub wysyłka jest obecnie w stanie, w którym potwierdzenie wysyłki nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="04e3e-115">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="04e3e-116">Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="04e3e-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="04e3e-117">Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.</span><span class="sxs-lookup"><span data-stu-id="04e3e-117">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="04e3e-118">Anuluj identyfikatory robocze, które zostały utworzone z lokalizacją pakowania jako ostateczną lokalizacją wysyłki, skonfiguruj ponownie dyrektywę lokalizacyjną i ponownie zwolnij ładunek.</span><span class="sxs-lookup"><span data-stu-id="04e3e-118">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="04e3e-119">Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają</span><span class="sxs-lookup"><span data-stu-id="04e3e-119">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="04e3e-120">Poniższa procedura służy do przeglądu linii ładunkowych i upewnienia się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.</span><span class="sxs-lookup"><span data-stu-id="04e3e-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="04e3e-121">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="04e3e-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="04e3e-122">Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.</span><span class="sxs-lookup"><span data-stu-id="04e3e-122">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="04e3e-123">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.</span><span class="sxs-lookup"><span data-stu-id="04e3e-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="04e3e-124">Zanotuj wartość pola **Ilość stworzonych prac**.</span><span class="sxs-lookup"><span data-stu-id="04e3e-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="04e3e-125">W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.</span><span class="sxs-lookup"><span data-stu-id="04e3e-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="04e3e-126">Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.</span><span class="sxs-lookup"><span data-stu-id="04e3e-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="04e3e-127">Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.</span><span class="sxs-lookup"><span data-stu-id="04e3e-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a><span data-ttu-id="04e3e-128">Anuluj identyfikatory robocze, które zostały utworzone z lokalizacją pakowania jako ostateczną lokalizacją wysyłki, skonfiguruj ponownie dyrektywę lokalizacyjną i ponownie zwolnij ładunek</span><span class="sxs-lookup"><span data-stu-id="04e3e-128">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load</span></span>

<span data-ttu-id="04e3e-129">Użyj poniższej procedury, aby anulować identyfikatory pracy, które mają lokalizację pakowania jako ostateczną lokalizację odkładania z uruchomioną automatyczną konteneryzacją.</span><span class="sxs-lookup"><span data-stu-id="04e3e-129">Use the following procedure to cancel the work IDs that have the packing location as the final put location with automated containerization in place.</span></span>

1. <span data-ttu-id="04e3e-130">Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.</span><span class="sxs-lookup"><span data-stu-id="04e3e-130">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="04e3e-131">Zostanie otwarte okno dialogowe **Anuluj pracę**.</span><span class="sxs-lookup"><span data-stu-id="04e3e-131">The **Cancel work** dialog opens.</span></span> <span data-ttu-id="04e3e-132">W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować.</span><span class="sxs-lookup"><span data-stu-id="04e3e-132">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span> <span data-ttu-id="04e3e-133">Wybrany identyfikator pracy musi mieć **Status pracy** o wartości *Otwarta*, *W toku*, *Kanałowa*, *Połączona* lub *Zamknięta*.</span><span class="sxs-lookup"><span data-stu-id="04e3e-133">The selected work ID must have a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="04e3e-134">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="04e3e-134">Select **OK**.</span></span>
1. <span data-ttu-id="04e3e-135">Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.</span><span class="sxs-lookup"><span data-stu-id="04e3e-135">Select **Yes** to confirm that you want to cancel the work.</span></span>
1. <span data-ttu-id="04e3e-136">W razie potrzeby powtórz tę procedurę dla innych identyfikatorów roboczych.</span><span class="sxs-lookup"><span data-stu-id="04e3e-136">Repeat this procedure for the other work IDs as needed.</span></span>

<span data-ttu-id="04e3e-137">Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="04e3e-137">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>

<span data-ttu-id="04e3e-138">Korzystając z poniższej procedury, należy ponownie skonfigurować dyrektywę lokalizacji, tak aby nie używała lokalizacji pakowania jako ostatecznej lokalizacji wysyłki, gdy dla szablonu grup czynności zostanie ustawiona automatyczna konteneryzacja.</span><span class="sxs-lookup"><span data-stu-id="04e3e-138">Use the following procedure to reconfigure the location directive so it won't use the packing location as the final shipping location when automated containerization is set up for the wave template.</span></span>

1. <span data-ttu-id="04e3e-139">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="04e3e-139">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="04e3e-140">W polu **Typ zlecenia pracy** wybierz opcję *Zamówienia sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="04e3e-140">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="04e3e-141">Wybierz dyrektywę lokalizacji, której używasz do automatycznej konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="04e3e-141">Select the location directive you are using for automated containerization.</span></span>
1. <span data-ttu-id="04e3e-142">Na skróconej karcie **Działania w ramach dyrektywy lokalizacyjnej** wybierz pozycję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="04e3e-142">On the **Location Directive Actions** FastTab toolbar, select **Edit query**.</span></span>
1. <span data-ttu-id="04e3e-143">W oknie dialogowym edytora zapytań, na zakładce **Zakres** znajdź wiersz, w którym **Pole** jest ustawione na *Profil lokalizacji* i sprawdź, czy pole **Kryteria** dla tego wiersza nie jest ustawione na profil lokalizacji, który ma **Typ lokalizacji** o wartości *Pakowanie*.</span><span class="sxs-lookup"><span data-stu-id="04e3e-143">In the query editor dialog, on the **Range** tab, find the row where **Field** is set to *Location profile*, and verify that the **Criteria** field for that row is not set to a location profile that has a **Location type** of *Packing*.</span></span> <span data-ttu-id="04e3e-144">Dostosuj pole **Kryteria**, aby skorygować końcową lokalizację odłożeń.</span><span class="sxs-lookup"><span data-stu-id="04e3e-144">Adjust the **Criteria** field to correct the final put location.</span></span>

<span data-ttu-id="04e3e-145">Użyj poniższej procedury, aby ponownie zwolnić ładunek i utworzyć identyfikatory robocze z prawidłową ostateczną lokalizacją wysyłki.</span><span class="sxs-lookup"><span data-stu-id="04e3e-145">Use the following procedure to rerelease the load and create work IDs with the correct final shipping location.</span></span>

1. <span data-ttu-id="04e3e-146">Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.</span><span class="sxs-lookup"><span data-stu-id="04e3e-146">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="04e3e-147">W sekcji **Ładunki** znajdź ładunek, który musi zostać zwolniony.</span><span class="sxs-lookup"><span data-stu-id="04e3e-147">In the **Loads** section, find the load that needs to be released.</span></span>
1. <span data-ttu-id="04e3e-148">Na pasku narzędzi sekcji **Ładunki** wybierz opcję **Zwolnij \> Zwolnij do magazynu**, aby zwolnić wybrany ładunek do magazynu.</span><span class="sxs-lookup"><span data-stu-id="04e3e-148">On the **Loads** section toolbar, select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="04e3e-149">W razie potrzeby powtórz tę procedurę dla innych ładunków.</span><span class="sxs-lookup"><span data-stu-id="04e3e-149">Repeat this procedure for the other loads as needed.</span></span>
