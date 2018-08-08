--- 
title: Obliczanie sugestii liczby kart Kanban
description: "Ta procedura skupia się na optymalizowaniu wielkości i liczby kart Kanban dla określonej reguły Kanban poprzez obliczenie liczby kart Kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 540dd32c5da5859ef5e69f55d6806eada90bc840
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="calculate-kanban-quantity-suggestions"></a><span data-ttu-id="2c4cc-103">Obliczanie sugestii liczby kart Kanban</span><span class="sxs-lookup"><span data-stu-id="2c4cc-103">Calculate kanban quantity suggestions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2c4cc-104">Ta procedura skupia się na optymalizowaniu wielkości i liczby kart Kanban dla określonej reguły Kanban poprzez obliczenie liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-104">This procedure focuses on optimizing the kanban size and quantities for a specific kanban rule by using the kanban quantity calculation.</span></span> <span data-ttu-id="2c4cc-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2c4cc-106">Procedura jest przeznaczona dla menedżera strumienia wartości.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="2c4cc-107">Wcześniej należy wykonać procedurę Dodawanie nowej zasady obliczania liczby kart Kanban do reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-107">It is a prerequisite that you have completed the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span>


## <a name="create-a-kanban-quantity-calculation"></a><span data-ttu-id="2c4cc-108">Tworzenie obliczenia liczby kart Kanban</span><span class="sxs-lookup"><span data-stu-id="2c4cc-108">Create a kanban quantity calculation</span></span>
1. <span data-ttu-id="2c4cc-109">Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Obliczanie ilości na karcie Kanban > Oblicz liczbę kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Calculate kanban quantity.</span></span>
2. <span data-ttu-id="2c4cc-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-110">Click New.</span></span>
3. <span data-ttu-id="2c4cc-111">W polu Nazwa wpisz „Speaker2016”.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-111">In the Name field, type 'Speaker2016'.</span></span>
4. <span data-ttu-id="2c4cc-112">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-112">In the Name field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2c4cc-113">Wybierz zasadę utworzoną w procedurze Dodawanie nowej zasady obliczania liczby kart Kanban do reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-113">Select the policy that you have created in the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span> <span data-ttu-id="2c4cc-114">Na przykład Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-114">For example, Speaker2016.</span></span>  
5. <span data-ttu-id="2c4cc-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2c4cc-116">W polu Reguła aktywna w dniu ustaw datę i godzinę „2012-12-17T08:00:00”.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-116">In the Rule active as of date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="2c4cc-117">Ta data stanowi podstawę do określenia, które reguły stałych Kanban są brane pod uwagę w obliczaniu liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-117">This date serves as the basis for determining which fixed kanban rules are included in the kanban quantity calculation.</span></span>  
7. <span data-ttu-id="2c4cc-118">W polu Data początkowa okresu zaspokojenia popytu ustaw datę i godzinę „2012-11-17T09:00:00”.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-118">In the Fulfilled demand period start date field, set the date and time to '2012-11-17T09:00:00'.</span></span>
    * <span data-ttu-id="2c4cc-119">Data, od kiedy transakcje popytu w przeszłości są brane pod uwagę w obliczaniu liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-119">The date from when past demand transactions are included to calculate the kanban quantity.</span></span>  
8. <span data-ttu-id="2c4cc-120">W polu Data końcowa okresu zaspokojenia popytu ustaw datę i godzinę „2012-12-17T07:59:59”.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-120">In the Fulfilled demand period end date field, set the date and time to '2012-12-17T07:59:59'.</span></span>
    * <span data-ttu-id="2c4cc-121">Data, do kiedy transakcje popytu w przeszłości są brane pod uwagę w obliczaniu liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-121">The date until when past demand transactions are included to calculate the kanban quantity.</span></span>  
9. <span data-ttu-id="2c4cc-122">W polu Data początkowa okresu popytu ustaw datę i godzinę „2012-12-17T08:00:00”.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-122">In the Demand period start date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="2c4cc-123">Data, od kiedy transakcje bieżącego popytu są brane pod uwagę w obliczaniu liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-123">The date from when current demand transactions are included to calculate the kanban quantity.</span></span>  
10. <span data-ttu-id="2c4cc-124">W polu Data końcowa okresu popytu ustaw datę i godzinę „2013-01-16T07:59:59”.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-124">In the Demand period end date field, set the date and time to '2013-01-16T07:59:59'.</span></span>
    * <span data-ttu-id="2c4cc-125">Data, do kiedy transakcje bieżącego popytu są brane pod uwagę w obliczaniu liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-125">The date until when current demand transactions are included to calculate the kanban quantity.</span></span>  

## <a name="generate-kanban-quantity-proposal"></a><span data-ttu-id="2c4cc-126">Generowanie propozycji liczby kart Kanban</span><span class="sxs-lookup"><span data-stu-id="2c4cc-126">Generate kanban quantity proposal</span></span>
1. <span data-ttu-id="2c4cc-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-127">Click Save.</span></span>
2. <span data-ttu-id="2c4cc-128">Kliknij przycisk Generuj.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-128">Click Generate.</span></span>
    * <span data-ttu-id="2c4cc-129">Spowoduje to wygenerowanie wiersza propozycji liczby kart Kanban dla reguły Kanban 000020.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-129">This generates a kanban quantity proposal line for the kanban rule 000020.</span></span>  

## <a name="run-kanban-quantity-calculation"></a><span data-ttu-id="2c4cc-130">Obliczanie liczby kart Kanban</span><span class="sxs-lookup"><span data-stu-id="2c4cc-130">Run kanban quantity calculation</span></span>
1. <span data-ttu-id="2c4cc-131">Kliknij przycisk Oblicz.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-131">Click Calculate.</span></span>
    * <span data-ttu-id="2c4cc-132">Spowoduje to obliczenie propozycji liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-132">This calculates the kanban quantity proposal.</span></span>  
2. <span data-ttu-id="2c4cc-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-133">Click OK.</span></span>
3. <span data-ttu-id="2c4cc-134">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-134">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2c4cc-135">Należy zauważyć, że sugerowana liczba kart Kanban wynosi 2.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-135">Notice the suggested kanban quantity is 2.</span></span>  

## <a name="change-product-quantity-and-calculate-again"></a><span data-ttu-id="2c4cc-136">Zmiana ilości produktu i ponowne obliczanie</span><span class="sxs-lookup"><span data-stu-id="2c4cc-136">Change product quantity and calculate again</span></span>
1. <span data-ttu-id="2c4cc-137">W polu Ilość produktu ustaw wartość „5”.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-137">Set Product quantity to '5'.</span></span>
2. <span data-ttu-id="2c4cc-138">Kliknij przycisk Oblicz.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-138">Click Calculate.</span></span>
3. <span data-ttu-id="2c4cc-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-139">Click OK.</span></span>
    * <span data-ttu-id="2c4cc-140">Zwróć uwagę, że przy liczbie kart Kanban 5 sugestia zmienia się na liczbę kart Kanban 4.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-140">Notice that with a kanban quantity of 5, the suggestion is changed to a kanban quantity of 4.</span></span>  
    * <span data-ttu-id="2c4cc-141">Jest to spowodowane przez fakt, że przy mniejszej ilości produktu potrzeba więcej kart Kanban do zaspokojenia popytu.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-141">This is caused by the fact that with a lower product quantity, we need more kanbans to fulfill the demand.</span></span>  

## <a name="update-kanban-rule"></a><span data-ttu-id="2c4cc-142">Aktualizacja reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="2c4cc-142">Update kanban rule</span></span>
1. <span data-ttu-id="2c4cc-143">W polu Data aktywacji reguły wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-143">In the Rule effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="2c4cc-144">W polu „Reguła aktywna w dniu” ustaw datę w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-144">Set the 'Rule active as of date' to a date in the future.</span></span> <span data-ttu-id="2c4cc-145">Na przykład dzień dzisiejszy + jeden rok.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-145">For example, today + one year.</span></span>  
2. <span data-ttu-id="2c4cc-146">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-146">Click Update.</span></span>
3. <span data-ttu-id="2c4cc-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-147">Click OK.</span></span>
4. <span data-ttu-id="2c4cc-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-148">Close the page.</span></span>

## <a name="validate-change-on-kanban-rule"></a><span data-ttu-id="2c4cc-149">Sprawdzanie poprawności zmiany w regule Kanban</span><span class="sxs-lookup"><span data-stu-id="2c4cc-149">Validate change on kanban rule</span></span>
1. <span data-ttu-id="2c4cc-150">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-150">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="2c4cc-151">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2c4cc-152">Wybierz regułę Kanban, która została utworzona w poprzednim podzadaniu.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-152">Select the kanban rule that was created in the previous sub-task.</span></span> <span data-ttu-id="2c4cc-153">Powinna to być pierwsza reguła Kanban na liście posortowanej według numerów.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-153">This should be the first kanban rule in the list sorted by number.</span></span>  
3. <span data-ttu-id="2c4cc-154">Przełącz rozwinięcie sekcji Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-154">Toggle the expansion of the Details section.</span></span>
    * <span data-ttu-id="2c4cc-155">Zwróć uwagę na data obowiązywania, co oznacza, że ta reguła nie jest aktywowana przed tą datą.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-155">Notice the effective date, which means that this rule is not activated until this date.</span></span>  
4. <span data-ttu-id="2c4cc-156">Przełącz rozwinięcie sekcji Ilości.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-156">Toggle the expansion of the Quantities section.</span></span>
    * <span data-ttu-id="2c4cc-157">Należy zauważyć, że jest to domyślna ilość wprowadzona w obliczaniu liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-157">Notice this is the default quantity that you entered on the kanban quantity calculation.</span></span>  
    * <span data-ttu-id="2c4cc-158">Należy zauważyć, że jest to stała liczba kart Kanban 4 z obliczenia liczby kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-158">Notice this is the fixed kanban quantity of 4 from the kanban quantity calculation.</span></span>  
5. <span data-ttu-id="2c4cc-159">Kliknij kartę ListPanel.</span><span class="sxs-lookup"><span data-stu-id="2c4cc-159">Click the ListPanel tab.</span></span>


