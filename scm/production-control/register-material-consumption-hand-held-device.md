---
title: "Rejestracja na urządzeniu przenośnym zużycia materiałów"
description: "W tym temacie opisano przepływ pracy umożliwiający rejestrowanie zużycia surowców w produkcji przy użyciu urządzenia przenośnego (podręcznego)."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 97d374230cc6e833b9f585de000e1252f2a78b9d
ms.openlocfilehash: 83703d962d6099ba8ac107548a569c8d1f34882f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/30/2017

---

# <a name="register-material-consumption-using-a-mobile-device"></a><span data-ttu-id="b7a98-103">Rejestracja na urządzeniu przenośnym zużycia materiałów</span><span class="sxs-lookup"><span data-stu-id="b7a98-103">Register material consumption using a mobile device</span></span>
<span data-ttu-id="b7a98-104">W tym temacie opisano przepływ pracy umożliwiający rejestrowanie zużycia surowców w produkcji przy użyciu urządzenia przenośnego (podręcznego).</span><span class="sxs-lookup"><span data-stu-id="b7a98-104">This topic describes a workflow that enables registration of raw material consumption in production by using a handheld device.</span></span>

<a name="introduction"></a><span data-ttu-id="b7a98-105">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="b7a98-105">Introduction</span></span>
------------

<span data-ttu-id="b7a98-106">Ten przepływ pracy ma zastosowanie, jeśli istnieje ścisły wymóg identyfikowalności materiałów.</span><span class="sxs-lookup"><span data-stu-id="b7a98-106">This workflow is relevant if there is a strict requirement for material traceability.</span></span> <span data-ttu-id="b7a98-107">W tych przypadkach w celu utrzymania identyfikowalności materiałów należy raportować dokładny czas i ilość zużycia.</span><span class="sxs-lookup"><span data-stu-id="b7a98-107">In those cases, to maintain traceability of the materials, the exact time and quantity must be reported for the consumption.</span></span> <span data-ttu-id="b7a98-108">Ten proces może być traktowany jako przeciwieństwo operacji rozliczania wstępnego i wstecznego, gdzie występuje przesunięcie między czasem rejestracji a momentem, gdy dochodzi do faktycznego zużycia.</span><span class="sxs-lookup"><span data-stu-id="b7a98-108">This process can be seen as opposed to pre- or back-flushing operations, where there is an offset between the time of registration and the time when the actual consumption takes place.</span></span> <span data-ttu-id="b7a98-109">To wyjaśnia, dlaczego strategii automatycznego zużycia nie można używać do niektórych materiałów z wymogiem identyfikowalności.</span><span class="sxs-lookup"><span data-stu-id="b7a98-109">This explains why a strategy of automatic consumption cannot be used for some materials with traceability requirements.</span></span> <span data-ttu-id="b7a98-110">Spójrzmy na prosty scenariusz, który wyjaśnia, jak skonfigurować przepływ pracy, aby włączyć rejestrowanie zużycia surowców w produkcji za pomocą urządzenia podręcznego.</span><span class="sxs-lookup"><span data-stu-id="b7a98-110">Let’s look at a simple scenario that explains how to set up a workflow to enable registration of raw material consumption in production by using a handheld device.</span></span> [![](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a><span data-ttu-id="b7a98-111">Szczegóły scenariusza</span><span class="sxs-lookup"><span data-stu-id="b7a98-111">Scenario details</span></span>

<span data-ttu-id="b7a98-112">W procesie produkcji ciągłej (5) jest zużywany surowiec RM-100 wchodzący w skład partii.</span><span class="sxs-lookup"><span data-stu-id="b7a98-112">A continuous production process (5) consumes the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="b7a98-113">Materiał jest dostępny w lokalizacji Bulk-001 (1) pod numerem identyfikacyjnym PL-1 w dwóch partiach B1 i B2, obu z ilością 100 kg.</span><span class="sxs-lookup"><span data-stu-id="b7a98-113">The material is on-hand on location Bulk-001 (1) on license plate PL-1 with two batches, B1 and B2, both with a quantity of 100 lbs.</span></span> <span data-ttu-id="b7a98-114">Dla surowca RM-100 jest zwalniana i przetwarzana praca magazynowa (2), a materiał zostaje pobrany z lokalizacji Bulk-001 do lokalizacji wejściowej produkcji PIL-01 (3), która jest zdefiniowana jako niekontrolowana przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="b7a98-114">Warehouse work (2) is released and processed for RM-100, and the material is picked from Bulk-001 to the production input location PIL-01 (3), which is defined as non-license plate controlled.</span></span> <span data-ttu-id="b7a98-115">Operator maszyny waży materiał z lokalizacji wejściowej produkcji (3) i rejestruje masę oraz numer partii jako zużyte (4).</span><span class="sxs-lookup"><span data-stu-id="b7a98-115">The machine operator weighs out material from the production input location (3) and registers the weight and batch number as consumed (4).</span></span> <span data-ttu-id="b7a98-116">Z lokalizacji wejściowej produkcji część materiału jest ręcznie dodawana do procesu produkcji w zdefiniowanych odstępach czasu.</span><span class="sxs-lookup"><span data-stu-id="b7a98-116">From the production input location, a portion of the material is manually added to the production process in defined time intervals.</span></span> <span data-ttu-id="b7a98-117">Gdy operator maszyny dodaje materiał, waży go na wadze i rejestruje numer partii.</span><span class="sxs-lookup"><span data-stu-id="b7a98-117">When the machine operator adds material, it is weighed on a scale and the batch number is registered.</span></span>

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a><span data-ttu-id="b7a98-118">Konfigurowanie przepływu pracy rejestrowania zużycia przy użyciu urządzenia podręcznego</span><span class="sxs-lookup"><span data-stu-id="b7a98-118">Set up the workflow to register consumption using a handheld device</span></span>
<span data-ttu-id="b7a98-119">Utwórz wyrób gotowy FG-100 z listą składową zawierającą surowiec RM-100 wchodzący w skład partii.</span><span class="sxs-lookup"><span data-stu-id="b7a98-119">Create a finished-good product, FG-100, with a bill of material that has the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="b7a98-120">Doda dwie partie B1 i B2 surowca RM-100 w ilości 100 do lokalizacji Bulk-001 pod numerem identyfikacyjnym PL-1.</span><span class="sxs-lookup"><span data-stu-id="b7a98-120">Add two batches, B1 and B2, of RM-100 in a quantity of 100 to location: Bulk-001 on license plate: PL-1.</span></span> <span data-ttu-id="b7a98-121">Reguła rozliczania w wierszu listy składowej dla surowca RM-100 ma wartość **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="b7a98-121">The flushing principle on the bill of material line for RM-100 is set to **Manual**.</span></span> <span data-ttu-id="b7a98-122">Jako lokalizację wejściową produkcji ustaw PIL-01.</span><span class="sxs-lookup"><span data-stu-id="b7a98-122">Set  the production input location to PIL-01.</span></span> <span data-ttu-id="b7a98-123">Można to zrobić przez zaznaczenie tej lokalizacji jako domyślnej lokalizacji wejściowej produkcji w magazynie 51.</span><span class="sxs-lookup"><span data-stu-id="b7a98-123">You can do that by selecting this location as the default production input location on warehouse 51.</span></span>

1.  <span data-ttu-id="b7a98-124">Utwórz nowy element menu w urządzeniu komórkowym:</span><span class="sxs-lookup"><span data-stu-id="b7a98-124">Create a new mobile device menu item:</span></span> 

-    <span data-ttu-id="b7a98-125">**Nazwa elementu menu** — Zarejestruj zużycie materiałów.</span><span class="sxs-lookup"><span data-stu-id="b7a98-125">**Menu item name** - Register material consumption.</span></span> 
-    <span data-ttu-id="b7a98-126">**Tytuł** — Zarejestruj zużycie materiałów.</span><span class="sxs-lookup"><span data-stu-id="b7a98-126">**Title** - Register material consumption.</span></span> 
-    <span data-ttu-id="b7a98-127">**Tryb** — Pośrednie.</span><span class="sxs-lookup"><span data-stu-id="b7a98-127">**Mode** - Indirect.</span></span> 
-    <span data-ttu-id="b7a98-128">**Kod działania** — Zarejestruj zużycie materiałów.</span><span class="sxs-lookup"><span data-stu-id="b7a98-128">**Activity code** - Register material consumption.</span></span>

2.  <span data-ttu-id="b7a98-129">Dodaj element menu do menu urządzenia komórkowego **Produkcja**.</span><span class="sxs-lookup"><span data-stu-id="b7a98-129">Add the menu item to the **Production Mobile** device menu.</span></span>
3.  <span data-ttu-id="b7a98-130">Utwórz zlecenie produkcyjne na wyrób gotowy:</span><span class="sxs-lookup"><span data-stu-id="b7a98-130">Create a production order for the finished product:</span></span> 

-    <span data-ttu-id="b7a98-131">**Numer towaru** — FG-100</span><span class="sxs-lookup"><span data-stu-id="b7a98-131">**Item number** - FG-100</span></span> 
-    <span data-ttu-id="b7a98-132">**Oddział** — 5</span><span class="sxs-lookup"><span data-stu-id="b7a98-132">**Site** - 5</span></span> 
-    <span data-ttu-id="b7a98-133">**Magazyn** — 51</span><span class="sxs-lookup"><span data-stu-id="b7a98-133">**Warehouse** - 51</span></span> 
-    <span data-ttu-id="b7a98-134">**Ilość** — 150</span><span class="sxs-lookup"><span data-stu-id="b7a98-134">**Quantity** - 150</span></span>

<span data-ttu-id="b7a98-135">Zlecenie produkcyjne otrzymuje wartości atrybutów **Oszacowane** i **Zwolnione** oraz jest tworzona praca magazynu.</span><span class="sxs-lookup"><span data-stu-id="b7a98-135">The production order is **Estimated** and **Released** and warehouse work is created.</span></span>

4.  <span data-ttu-id="b7a98-136">Dokończ pracę przy użyciu przepływu pracy pobrania surowca na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="b7a98-136">Complete the work using the workflow for raw material picking for the handheld device.</span></span>

<span data-ttu-id="b7a98-137">To spowoduje przeniesienie materiału z lokalizacji zbiorczej do lokalizacji wejściowej produkcji PIL-01.</span><span class="sxs-lookup"><span data-stu-id="b7a98-137">This will bring the material from the bulk location to the production input location PIL-01.</span></span> <span data-ttu-id="b7a98-138">Po zakończeniu pracy materiał otrzymuje stan **Pobrane w lokalizacji wejściowej produkcji**.</span><span class="sxs-lookup"><span data-stu-id="b7a98-138">After the work is completed, the material has the status **Picked on the production input location**.</span></span> <span data-ttu-id="b7a98-139">Stan po przetworzeniu pracy może mieć wartość **Pobrane** lub **Fizycznie zarezerwowane**.</span><span class="sxs-lookup"><span data-stu-id="b7a98-139">The status after work has been processed can be either **Picked** or **Reserved physical**.</span></span> <span data-ttu-id="b7a98-140">To się konfiguruje przy użyciu parametru **Stan wydania po zapisaniu w formularzu magazynu**.</span><span class="sxs-lookup"><span data-stu-id="b7a98-140">This is configured with the parameter **Issue status after put on the warehouse form**.</span></span>

5.  <span data-ttu-id="b7a98-141">Rozpocznij zlecenie produkcyjne z klienta lub z urządzenia przenośnego przy użyciu elementu menu **Rozpoczęcia produkcji**.</span><span class="sxs-lookup"><span data-stu-id="b7a98-141">Start the production order either from the client or from the handheld device by using the **Production start** menu item.</span></span>

<span data-ttu-id="b7a98-142">Po uruchomieniu zlecenia produkcyjnego można rejestrować zużycie materiału za pomocą przepływu pracy na urządzeniu podręcznym.</span><span class="sxs-lookup"><span data-stu-id="b7a98-142">After the production order has been started, you can register material consumption with the workflow for the handheld device.</span></span> <span data-ttu-id="b7a98-143">Zacznijmy od zarejestrowania zużycia 25 kg z partii B1.</span><span class="sxs-lookup"><span data-stu-id="b7a98-143">Let's start by registering consumption of 25 lbs of batch B1.</span></span>

6.  <span data-ttu-id="b7a98-144">Wybierz element menu **Zarejestruj zużycie** **materiałów** w menu na urządzeniu przenośnym i wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="b7a98-144">Select the **Register material** **consumption** menu item in the menu for the hand held device, enter the following details:</span></span> 

-    <span data-ttu-id="b7a98-145">Numer zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="b7a98-145">The production order number.</span></span> 
-    <span data-ttu-id="b7a98-146">Lokalizacja, w której materiał będzie zużywany, w tym przypadku PIL-01.</span><span class="sxs-lookup"><span data-stu-id="b7a98-146">The location on which the material is going to be consumed, in this case PIL-01.</span></span> 
-    <span data-ttu-id="b7a98-147">Numer towaru RM-100.</span><span class="sxs-lookup"><span data-stu-id="b7a98-147">Item number RM-100.</span></span> 
-    <span data-ttu-id="b7a98-148">Numer partii B1.</span><span class="sxs-lookup"><span data-stu-id="b7a98-148">Batch number B1.</span></span> 
-    <span data-ttu-id="b7a98-149">Ilość 25.</span><span class="sxs-lookup"><span data-stu-id="b7a98-149">A quantity of 25.</span></span>

7.  <span data-ttu-id="b7a98-150">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7a98-150">Select **OK**.</span></span>

<span data-ttu-id="b7a98-151">Zwróć uwagę, że na ekranie pojawił się komunikat „Wiersz arkusza został utworzony”.</span><span class="sxs-lookup"><span data-stu-id="b7a98-151">Note that the message "Journal line is created" appears on the display.</span></span> <span data-ttu-id="b7a98-152">W zleceniu produkcyjnym istnieje otwarty arkusz typu **Lista pobrania produkcji** dla towaru o numerze RM-100 i partii o numerze B1.</span><span class="sxs-lookup"><span data-stu-id="b7a98-152">On the production order there is an open journal of the type **Production picking list** for item number RM-100 and batch number B1.</span></span> 

<span data-ttu-id="b7a98-153">Teraz możesz wybrać opcję kontynuowania rejestracji, na przykład partii o numerze B2. Po każdym kliknięciu przycisku **OK** zostanie dodany nowy wiersz arkusza do otwartego arkusza.</span><span class="sxs-lookup"><span data-stu-id="b7a98-153">You can now choose to continue your registration, for example on batch number B2, and each time you select **OK,** a new journal line is added to the open journal.</span></span> 

<span data-ttu-id="b7a98-154">Po zakończeniu rejestrowania kliknij przycisk **Gotowe**, aby zaksięgować arkusz i zakończyć przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="b7a98-154">After you have finished your registration, select **Done** to post the journal and end the workflow.</span></span>

### <a name="additional-comments"></a><span data-ttu-id="b7a98-155">Dodatkowe uwagi</span><span class="sxs-lookup"><span data-stu-id="b7a98-155">Additional comments</span></span> 

-   <span data-ttu-id="b7a98-156">Jeśli użytkownik anuluje przepływ pracy po utworzeniu wiersza arkusza, arkusz jest w stanie niezaksięgowania, ale jeśli użytkownik później użyje przepływu pracy do tego samego zlecenia produkcyjnego, wiersze zostaną dodane do otwartego arkusza, a nie do nowego arkusza.</span><span class="sxs-lookup"><span data-stu-id="b7a98-156">If a user cancels the workflow after a journal line is created, the journal is in an unposted state but if the user at a later point uses the workflow for the same production order, then the lines will be added to the open journal rather than to a new journal.</span></span>
-   <span data-ttu-id="b7a98-157">Nowy przepływ pracy umożliwia również rejestrowanie numerów seryjnych.</span><span class="sxs-lookup"><span data-stu-id="b7a98-157">The new workflow also supports the registration of serial numbers.</span></span>
-   <span data-ttu-id="b7a98-158">Można zarejestrować tylko kod towaru zdefiniowany na liście składowej lub w formule dla wybranego zlecenia produkcyjnego lub szarży produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="b7a98-158">It is only possible to register an item number that is defined in the bill of material or in the formula for the selected production order or batch order.</span></span>
-   <span data-ttu-id="b7a98-159">Materiał może być zużywany ponad miarę.</span><span class="sxs-lookup"><span data-stu-id="b7a98-159">Material can be overconsumed.</span></span> <span data-ttu-id="b7a98-160">Na przykład jeśli szacuje się, że materiał zostanie zużyty w ilości 100 kg, można go zużyć ponad miarę, na przykład w ilości 105 kg.</span><span class="sxs-lookup"><span data-stu-id="b7a98-160">For example, if the material is estimated to be consumed with the quantity of 100 lbs, then it can be overconsumed with a quantity of, for example, 105 lbs.</span></span>



