---
title: Tworzenie działań przeniesienia produkcji lean manufacturing
description: Tworzenie działania przeniesienia dla produkcji oszczędnej.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2411dc51dc1b85499edb30d9a580f396277a5bd9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828881"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a><span data-ttu-id="a931c-103">Tworzenie działań przeniesienia produkcji lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="a931c-103">Create transfer activities for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a931c-104">Tworzenie działania przeniesienia dla produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="a931c-104">Create a transfer activity for lean manufacturing.</span></span> 

<span data-ttu-id="a931c-105">Wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="a931c-105">Prerequisites:</span></span> 

1. <span data-ttu-id="a931c-106">Musi być utworzony przepływ produkcji i wersja, która nie jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="a931c-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="a931c-107">Muszą być utworzone magazyny i lokalizacje źródłowe oraz docelowe.</span><span class="sxs-lookup"><span data-stu-id="a931c-107">The from and to warehouse and locations must be created.</span></span> <span data-ttu-id="a931c-108">Opcjonalnie można utworzyć uzupełnienie lub komórkę roboczą uzupełnienia.</span><span class="sxs-lookup"><span data-stu-id="a931c-108">Optionally, the replenishing or the replenished work cell should be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="a931c-109">Znajdowanie wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="a931c-109">Find the production flow version</span></span>
1. <span data-ttu-id="a931c-110">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="a931c-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="a931c-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a931c-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a931c-112">Należy zauważyć, że przepływ produkcji musi mieć wersję roboczą.</span><span class="sxs-lookup"><span data-stu-id="a931c-112">Note that the production flow must have a version in draft status.</span></span>  
3. <span data-ttu-id="a931c-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a931c-113">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="a931c-114">Tworzenie nowego działania</span><span class="sxs-lookup"><span data-stu-id="a931c-114">Create a new activity</span></span>
1. <span data-ttu-id="a931c-115">Kliknij opcję Działania.</span><span class="sxs-lookup"><span data-stu-id="a931c-115">Click Activities.</span></span>
    * <span data-ttu-id="a931c-116">Upewnij się, że wybrany przepływ produkcji ma wersję roboczą, i zaznacz tę wersję.</span><span class="sxs-lookup"><span data-stu-id="a931c-116">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="a931c-117">Kliknij opcję Utwórz nowe działanie planu.</span><span class="sxs-lookup"><span data-stu-id="a931c-117">Click Create new plan activity.</span></span>
3. <span data-ttu-id="a931c-118">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a931c-118">Click Next.</span></span>
4. <span data-ttu-id="a931c-119">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a931c-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="a931c-120">W polu Typ działania wybierz opcję „Przeniesienie”.</span><span class="sxs-lookup"><span data-stu-id="a931c-120">In the Activity type field, select 'Transfer'.</span></span>
6. <span data-ttu-id="a931c-121">W polu Ilość dla procesu wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a931c-121">In the Process quantity field, enter a number.</span></span>
7. <span data-ttu-id="a931c-122">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a931c-122">Click Next.</span></span>

## <a name="select-the-work-cells"></a><span data-ttu-id="a931c-123">Wybór komórek roboczych</span><span class="sxs-lookup"><span data-stu-id="a931c-123">Select the Work cells</span></span>
1. <span data-ttu-id="a931c-124">W polu Uzupełnienie kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a931c-124">In the Replenishing field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a931c-125">Aby użyć lokalizacji wyjściowej komórki roboczej jako lokalizacji źródłowej w działaniu przeniesienia, zaznacz komórkę roboczą.</span><span class="sxs-lookup"><span data-stu-id="a931c-125">To use the work cell output location as the from location in the transfer activity, select a work cell.</span></span> <span data-ttu-id="a931c-126">To samo można zrobić z uzupełnioną komórką roboczą, co ustawi lokalizację docelową działania przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="a931c-126">The same can be done with the replenished work cell, which sets the target location of the transfer activity.</span></span>  
2. <span data-ttu-id="a931c-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a931c-127">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="a931c-128">Definiowanie aktualizacji zapasów</span><span class="sxs-lookup"><span data-stu-id="a931c-128">Define the inventory updates</span></span>
1. <span data-ttu-id="a931c-129">W polu Typ produktu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="a931c-129">In the Product type field, select an option.</span></span>
    * <span data-ttu-id="a931c-130">Należy zwrócić uwagę, że przeniesienie nie zmienia typu produktu.</span><span class="sxs-lookup"><span data-stu-id="a931c-130">Note that a transfer does not change the type of product.</span></span> <span data-ttu-id="a931c-131">Można przenosić wyroby gotowe lub półprodukty (przenoszenie między dwoma działaniami w przepływie produkcji i ewentualnie w przepływie Kanban).</span><span class="sxs-lookup"><span data-stu-id="a931c-131">You can transfer finished products or semi-finished products (transfer between two activities of a production flow and possibly a kanban flow).</span></span>     <span data-ttu-id="a931c-132">Podczas przenoszenia wyrobów gotowych można określić, czy transakcja magazynowa będzie efektem pobrania czy przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="a931c-132">When transferring finished products, you can select if picking or receiving results in an inventory transaction.</span></span>  

## <a name="define-the-transfer-locations"></a><span data-ttu-id="a931c-133">Definiowanie lokalizacji przeniesienia</span><span class="sxs-lookup"><span data-stu-id="a931c-133">Define the transfer locations</span></span>
1. <span data-ttu-id="a931c-134">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a931c-134">Click Next.</span></span>
2. <span data-ttu-id="a931c-135">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a931c-135">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="a931c-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a931c-136">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="a931c-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a931c-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a931c-138">W polu Lokalizacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a931c-138">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a931c-139">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a931c-139">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="a931c-140">W polu Transportowane przez wybierz opcję „Spedytor”.</span><span class="sxs-lookup"><span data-stu-id="a931c-140">In the Freighted by field, select 'Shipper'.</span></span>
    * <span data-ttu-id="a931c-141">Dostępne są następujące opcje: Spedytor — organizacja prowadząca magazyn wysyłki, Adresat — organizacja prowadząca magazyn przyjęcia, Przewoźnik — zewnętrzny dostawca.</span><span class="sxs-lookup"><span data-stu-id="a931c-141">Options include: Shipper - the organization operating the shipping warehouse, Recipient -  the organization operating the receiving warehouse, Carrier - a third party vendor.</span></span> <span data-ttu-id="a931c-142">Jeśli organizacją realizującą jest dostawcą, działanie przeniesienia wymaga umowy podwykonawstwa.</span><span class="sxs-lookup"><span data-stu-id="a931c-142">If the operating organization is a vendor, the transfer activity requires a subcontracting agreement.</span></span>  
8. <span data-ttu-id="a931c-143">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a931c-143">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="a931c-144">Definiowanie czasów działań</span><span class="sxs-lookup"><span data-stu-id="a931c-144">Define the activity times</span></span>
1. <span data-ttu-id="a931c-145">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a931c-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a931c-146">Zdefiniowanie czasu wykonywania jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="a931c-146">The definition of a Runtime is required.</span></span> <span data-ttu-id="a931c-147">Czas wykonywania jest używany do obliczania kosztów i czasów produktywności w zadaniach w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="a931c-147">The Runtime is used to calculate cost and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="a931c-148">Czasy wykonywania nie są używane do obliczania obciążenia zdolności produkcyjnych i zużycia. Do obliczania tych parametrów służy czas cyklu pochodzący z zadania w wersji przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="a931c-148">Runtimes are not used to calculate capacity load and consumption, which is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="a931c-149">W polu Czas wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="a931c-149">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="a931c-150">W polu Jednostka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a931c-150">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="a931c-151">Wybierz jednostkę czasu.</span><span class="sxs-lookup"><span data-stu-id="a931c-151">Select the Time unit.</span></span>
5. <span data-ttu-id="a931c-152">W polu Na ilość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a931c-152">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="a931c-153">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a931c-153">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a931c-154">Czasy oczekiwania są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="a931c-154">Queue times are optional.</span></span>  
7. <span data-ttu-id="a931c-155">W polu Czas wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="a931c-155">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="a931c-156">W polu Jednostka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a931c-156">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="a931c-157">Wybierz jednostkę czasu.</span><span class="sxs-lookup"><span data-stu-id="a931c-157">Select the Time unit.</span></span>
10. <span data-ttu-id="a931c-158">W polu Na ilość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a931c-158">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="a931c-159">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="a931c-159">Click Next.</span></span>
12. <span data-ttu-id="a931c-160">Kliknij przycisk Zakończ.</span><span class="sxs-lookup"><span data-stu-id="a931c-160">Click Finish.</span></span>
13. <span data-ttu-id="a931c-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a931c-161">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]