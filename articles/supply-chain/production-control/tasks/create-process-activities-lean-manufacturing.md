---
title: Tworzenie działań procesu produkcji lean manufacturing
description: Tworzenie działania procesu dla produkcji oszczędnej.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup, PlanActivityDetails, KanbanJobPickingListPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46d6b7696d606333a170eaa1c06b9e0503ae1e02
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829025"
---
# <a name="create-process-activities-for-lean-manufacturing"></a><span data-ttu-id="06fcc-103">Tworzenie działań procesu produkcji lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="06fcc-103">Create process activities for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="06fcc-104">Tworzenie działania procesu dla produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="06fcc-104">Create a process activity for lean manufacturing.</span></span> 

<span data-ttu-id="06fcc-105">Wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="06fcc-105">Prerequisites:</span></span> 

1. <span data-ttu-id="06fcc-106">Musi być utworzony przepływ produkcji i wersja, która nie jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="06fcc-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="06fcc-107">Musi być utworzona komórka robocza.</span><span class="sxs-lookup"><span data-stu-id="06fcc-107">A work cell must be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="06fcc-108">Znajdowanie wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="06fcc-108">Find the production flow version</span></span>
1. <span data-ttu-id="06fcc-109">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="06fcc-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="06fcc-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="06fcc-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="06fcc-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="06fcc-111">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="06fcc-112">Tworzenie nowego działania</span><span class="sxs-lookup"><span data-stu-id="06fcc-112">Create a new activity</span></span>
1. <span data-ttu-id="06fcc-113">Kliknij opcję Działania.</span><span class="sxs-lookup"><span data-stu-id="06fcc-113">Click Activities.</span></span>
    * <span data-ttu-id="06fcc-114">Upewnij się, że wybrany przepływ produkcji ma wersję roboczą, i zaznacz tę wersję.</span><span class="sxs-lookup"><span data-stu-id="06fcc-114">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="06fcc-115">Kliknij opcję Utwórz nowe działanie planu.</span><span class="sxs-lookup"><span data-stu-id="06fcc-115">Click Create new plan activity.</span></span>
3. <span data-ttu-id="06fcc-116">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="06fcc-116">Click Next.</span></span>
4. <span data-ttu-id="06fcc-117">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="06fcc-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="06fcc-118">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="06fcc-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="06fcc-119">Należy zauważyć, że wszystkie wersje przepływu produkcji muszą mieć unikatowe nazwy.</span><span class="sxs-lookup"><span data-stu-id="06fcc-119">Note that the name must be unique for a given production flow for all versions.</span></span>  
6. <span data-ttu-id="06fcc-120">W polu Ilość dla procesu wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="06fcc-120">In the Process quantity field, enter a number.</span></span>
    * <span data-ttu-id="06fcc-121">Należy zauważyć, że niezależnie od tego, jaka ilość zadania będzie przetwarzana, jest to minimalna ilość w zadaniu, dla jakiej będą obliczane koszty robocizny.</span><span class="sxs-lookup"><span data-stu-id="06fcc-121">Note that no matter what job quantity will be processed, this is the minimum quantity per job to calculate the labor cost.</span></span> <span data-ttu-id="06fcc-122">Jeśli ilości w zadaniu różnią się od tej ilości, zostanie utworzone odchylenie kosztów robocizny.</span><span class="sxs-lookup"><span data-stu-id="06fcc-122">If job quantities deviate from this quantity, labor cost variance will be created.</span></span>  
7. <span data-ttu-id="06fcc-123">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="06fcc-123">Click Next.</span></span>

## <a name="select-the-work-cell"></a><span data-ttu-id="06fcc-124">Wybór komórki roboczej</span><span class="sxs-lookup"><span data-stu-id="06fcc-124">Select the work cell</span></span>
1. <span data-ttu-id="06fcc-125">W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="06fcc-125">In the Work cell field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="06fcc-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="06fcc-126">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="06fcc-127">Definiowanie aktualizacji zapasów</span><span class="sxs-lookup"><span data-stu-id="06fcc-127">Define the inventory updates</span></span>
1. <span data-ttu-id="06fcc-128">Zaznacz lub wyczyść pole wyboru Aktualizuj przychód dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="06fcc-128">Select or clear the Update on hand receipt check box.</span></span>
    * <span data-ttu-id="06fcc-129">Jeśli opcja Aktualizuj dostępne zapasy ma wartość Nie, można określić działanie przyjęcia półproduktu (działania nie osiąga następnego poziomu BOM).</span><span class="sxs-lookup"><span data-stu-id="06fcc-129">If Update On hand = No, you can define the activity to receive a semi-finished product (the activity does not reach the next BOM level).</span></span>    <span data-ttu-id="06fcc-130">Można również wybrać opcję zużywania półproduktów.</span><span class="sxs-lookup"><span data-stu-id="06fcc-130">You can also select to consume semi-finished products.</span></span>  

## <a name="define-the-picking-activities"></a><span data-ttu-id="06fcc-131">Definiowanie działań pobrania</span><span class="sxs-lookup"><span data-stu-id="06fcc-131">Define the picking activities</span></span>
1. <span data-ttu-id="06fcc-132">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="06fcc-132">Click Next.</span></span>
2. <span data-ttu-id="06fcc-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="06fcc-133">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="06fcc-134">Dla lokalizacji wejściowej wybranej komórki roboczej jest tworzone domyślne działanie pobrania.</span><span class="sxs-lookup"><span data-stu-id="06fcc-134">A default picking activity is created for the input location of the selected work cell.</span></span>  
3. <span data-ttu-id="06fcc-135">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="06fcc-135">Click Add.</span></span>
    * <span data-ttu-id="06fcc-136">Można utworzyć dodatkowe działania pobrania dla określonych produktów, które nie są przygotowywane w działaniu wprowadzenia do komórki roboczej.</span><span class="sxs-lookup"><span data-stu-id="06fcc-136">You can create additional picking activities for specific products, that are not staged at the work cell input activity.</span></span>  
4. <span data-ttu-id="06fcc-137">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="06fcc-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="06fcc-138">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="06fcc-138">In the Item number field, type a value.</span></span>
6. <span data-ttu-id="06fcc-139">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="06fcc-139">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="06fcc-140">W przypadku tej definicji wszystkie materiały zużywane w działaniu są pobierane z domyślnego magazynu wejściowego i lokalizacji, z wyjątkiem towaru, który jest zdefiniowany w drugim działaniu pobrania.</span><span class="sxs-lookup"><span data-stu-id="06fcc-140">With this definition, all materials consumed in the activity are picked from the default input warehouse and location except the item that is defined in the second picking activity.</span></span> <span data-ttu-id="06fcc-141">Ten towar będzie pobierany z innego magazynu i lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="06fcc-141">This item will be picked from a different warehouse and location.</span></span>  
7. <span data-ttu-id="06fcc-142">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="06fcc-142">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="06fcc-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="06fcc-143">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="06fcc-144">Zaznacz lub wyczyść pole wyboru Zarejestruj braki.</span><span class="sxs-lookup"><span data-stu-id="06fcc-144">Select or clear the Register scrap check box.</span></span>
10. <span data-ttu-id="06fcc-145">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="06fcc-145">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="06fcc-146">Definiowanie czasów działań</span><span class="sxs-lookup"><span data-stu-id="06fcc-146">Define the activity times</span></span>
1. <span data-ttu-id="06fcc-147">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="06fcc-147">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="06fcc-148">Zdefiniowanie czasu wykonywania jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="06fcc-148">The definition of a Runtime is required.</span></span> <span data-ttu-id="06fcc-149">Czas wykonywania jest używany do obliczania kosztów i czasów produktywności w zadaniach w systemie Kanban.</span><span class="sxs-lookup"><span data-stu-id="06fcc-149">The Runtime is used to calculate costs and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="06fcc-150">Czasy wykonywania nie są używane do obliczania obciążenia zdolności produkcyjnych i zużycia. Do obliczania tych parametrów służy czas cyklu pochodzący z zadania w wersji przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="06fcc-150">Runtimes are not used to calculate capacity load and consumption, this is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="06fcc-151">W polu Czas wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="06fcc-151">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="06fcc-152">W polu Jednostka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="06fcc-152">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="06fcc-153">Wybierz jednostkę czasu.</span><span class="sxs-lookup"><span data-stu-id="06fcc-153">Select the Time unit.</span></span>
5. <span data-ttu-id="06fcc-154">W polu Na ilość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="06fcc-154">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="06fcc-155">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="06fcc-155">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="06fcc-156">Czasy oczekiwania są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="06fcc-156">Queue times are optional.</span></span>  
7. <span data-ttu-id="06fcc-157">W polu Czas wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="06fcc-157">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="06fcc-158">W polu Jednostka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="06fcc-158">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="06fcc-159">Wybierz jednostkę czasu.</span><span class="sxs-lookup"><span data-stu-id="06fcc-159">Select the Time unit.</span></span>
10. <span data-ttu-id="06fcc-160">W polu Na ilość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="06fcc-160">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="06fcc-161">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="06fcc-161">Click Next.</span></span>
12. <span data-ttu-id="06fcc-162">Kliknij przycisk Zakończ.</span><span class="sxs-lookup"><span data-stu-id="06fcc-162">Click Finish.</span></span>
13. <span data-ttu-id="06fcc-163">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="06fcc-163">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]