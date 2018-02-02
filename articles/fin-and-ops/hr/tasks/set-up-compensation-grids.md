--- 
title: "Konfigurowanie siatek wynagrodzeń"
description: "Siatki wynagrodzeń są używane do definiowania i obsługi struktur płacy dla planów stałych wynagrodzeń."
author: kherr75
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a9d0d9a3f278a09e89311ee75b6f95fb4f3b04cb
ms.openlocfilehash: 39655850c1d54c56737881363bf5f805079fac89
ms.contentlocale: pl-pl
ms.lasthandoff: 02/02/2018

---
# <a name="set-up-compensation-grids"></a><span data-ttu-id="78b65-103">Konfigurowanie siatek wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="78b65-103">Set up compensation grids</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="78b65-104">Siatki wynagrodzeń są używane do definiowania i obsługi struktur płacy dla planów stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="78b65-104">Compensation grids are used to define and maintain the pay structures for fixed compensation plans.</span></span> <span data-ttu-id="78b65-105">Siatki wynagrodzeń mogą być współużytkowane przez wiele planów lub kopiowane podczas tworzenia nowego planu wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="78b65-105">Compensation grids can be shared between multiple plans or copied when creating a new compensation plan.</span></span>  <span data-ttu-id="78b65-106">Przed utworzeniem siatki wynagrodzeń należy skonfigurować poziomy i punkty odniesienia.</span><span class="sxs-lookup"><span data-stu-id="78b65-106">Before creating a compensation grid, Levels and Reference points must be set up.</span></span> <span data-ttu-id="78b65-107">W tym przykładzie zostanie utworzony nowy typ kategorii w siatce wynagrodzeń przy użyciu danych demonstracyjnych dla poziomów i punktów odniesienia.</span><span class="sxs-lookup"><span data-stu-id="78b65-107">This example will create a new Grade type of compensation grid using demo data for the Levels and Reference points.</span></span> <span data-ttu-id="78b65-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="78b65-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-information-about-the-compensation-grid"></a><span data-ttu-id="78b65-109">Konfigurowanie informacji o siatce wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="78b65-109">Set up information about the compensation grid</span></span>
1. <span data-ttu-id="78b65-110">Wybierz kolejno opcje Zasoby ludzkie > Wynagrodzenia > Stałe wynagrodzenie > Siatki wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="78b65-110">Go to Human resources > Compensation > Fixed compensation > Compensation grids.</span></span>
2. <span data-ttu-id="78b65-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="78b65-111">Click New.</span></span>
3. <span data-ttu-id="78b65-112">W polu Siatka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-112">In the Grid field, type a value.</span></span>
4. <span data-ttu-id="78b65-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="78b65-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="78b65-114">W polu Typ wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="78b65-114">In the Type field, select an option.</span></span>
6. <span data-ttu-id="78b65-115">W polu Konfiguracja odniesienia wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-115">In the Reference setup field, enter or select a value.</span></span>
7. <span data-ttu-id="78b65-116">W polu Waluta wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-116">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="78b65-117">W polu Waluta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-117">In the Currency field, type a value.</span></span>
9. <span data-ttu-id="78b65-118">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="78b65-118">In the Effective date field, enter a date.</span></span>

## <a name="add-levels-to-the-compensation-structure"></a><span data-ttu-id="78b65-119">Dodawanie poziomów do struktury wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="78b65-119">Add levels to the compensation structure</span></span>
1. <span data-ttu-id="78b65-120">Kliknij opcję Struktura wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="78b65-120">Click Compensation structure.</span></span>
2. <span data-ttu-id="78b65-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="78b65-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="78b65-122">W polu Poziom wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-122">In the Level field, enter or select a value.</span></span>
4. <span data-ttu-id="78b65-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="78b65-123">Click New.</span></span>
5. <span data-ttu-id="78b65-124">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="78b65-124">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="78b65-125">W polu Poziom wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-125">In the Level field, enter or select a value.</span></span>
7. <span data-ttu-id="78b65-126">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="78b65-126">Click New.</span></span>
8. <span data-ttu-id="78b65-127">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="78b65-127">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="78b65-128">W polu Poziom wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-128">In the Level field, enter or select a value.</span></span>
10. <span data-ttu-id="78b65-129">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="78b65-129">Click New.</span></span>
11. <span data-ttu-id="78b65-130">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="78b65-130">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="78b65-131">W polu Poziom wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-131">In the Level field, enter or select a value.</span></span>
13. <span data-ttu-id="78b65-132">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="78b65-132">Click New.</span></span>
14. <span data-ttu-id="78b65-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="78b65-133">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="78b65-134">W polu Poziom wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-134">In the Level field, enter or select a value.</span></span>

## <a name="fill-in-the-compensation-structure-with-values"></a><span data-ttu-id="78b65-135">Wypełnianie struktury wynagrodzeń wartościami</span><span class="sxs-lookup"><span data-stu-id="78b65-135">Fill in the compensation structure with values</span></span>
1. <span data-ttu-id="78b65-136">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="78b65-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="78b65-137">W tym momencie wartości wynagrodzeń można ręcznie wprowadzić do każdego pola w tabeli lub użyć funkcji zmiany masowej i w jednym kroku łatwo wypełnić wiele pól oraz wykonać podstawowe obliczenia.</span><span class="sxs-lookup"><span data-stu-id="78b65-137">At this point, compensation values can manually be entered into each field in the table, or the Mass change functionality can be used to easily fill in multiple fields and perform basic calculations.</span></span>  
2. <span data-ttu-id="78b65-138">Kliknij opcję Zmiana masowa.</span><span class="sxs-lookup"><span data-stu-id="78b65-138">Click Mass change.</span></span>
    * <span data-ttu-id="78b65-139">W tej siatce najpierw zastosujemy wartość punktu środkowego pierwszego poziomu do wszystkich pól w tabeli.</span><span class="sxs-lookup"><span data-stu-id="78b65-139">For this grid, we'll first apply the value for the midpoint of the first level's to all the fields in the table.</span></span> <span data-ttu-id="78b65-140">Będzie to podstawa macierzy wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="78b65-140">This will be the basis for the compensation matrix.</span></span>  
3. <span data-ttu-id="78b65-141">W polu Typ korekty wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="78b65-141">In the Adjustment type field, select an option.</span></span>
4. <span data-ttu-id="78b65-142">W polu Kwota korekty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="78b65-142">In the Adjustment amount field, enter a number.</span></span>
5. <span data-ttu-id="78b65-143">Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.</span><span class="sxs-lookup"><span data-stu-id="78b65-143">In the list, mark or unmark all rows.</span></span>
6. <span data-ttu-id="78b65-144">Kliknij przycisk Zastosuj do siatki.</span><span class="sxs-lookup"><span data-stu-id="78b65-144">Click Apply to grid.</span></span>
    * <span data-ttu-id="78b65-145">Teraz użyjemy funkcji zmiany masowej, aby zwiększyć kwoty na każdym kolejnym poziomie o określony procent lub kwotę.</span><span class="sxs-lookup"><span data-stu-id="78b65-145">Now we'll use the mass change function to increment the amounts in each subsequent level by a certain percentage or amount.</span></span> <span data-ttu-id="78b65-146">W tym przykładzie rozpiętość między punktami środkowymi kategorii będzie wynosiła 12,5%.</span><span class="sxs-lookup"><span data-stu-id="78b65-146">In this example, each grade will have a 12.5% spread between their midpoints.</span></span>  
7. <span data-ttu-id="78b65-147">W polu Typ korekty wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="78b65-147">In the Adjustment type field, select an option.</span></span>
8. <span data-ttu-id="78b65-148">W polu Kwota korekty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="78b65-148">In the Adjustment amount field, enter a number.</span></span>
9. <span data-ttu-id="78b65-149">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-149">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="78b65-150">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-150">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="78b65-151">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-151">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="78b65-152">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-152">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="78b65-153">Kliknij przycisk Zastosuj do siatki.</span><span class="sxs-lookup"><span data-stu-id="78b65-153">Click Apply to grid.</span></span>
14. <span data-ttu-id="78b65-154">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-154">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="78b65-155">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-155">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="78b65-156">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-156">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="78b65-157">Kliknij przycisk Zastosuj do siatki.</span><span class="sxs-lookup"><span data-stu-id="78b65-157">Click Apply to grid.</span></span>
18. <span data-ttu-id="78b65-158">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-158">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="78b65-159">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-159">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="78b65-160">Kliknij przycisk Zastosuj do siatki.</span><span class="sxs-lookup"><span data-stu-id="78b65-160">Click Apply to grid.</span></span>
21. <span data-ttu-id="78b65-161">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78b65-161">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="78b65-162">Kliknij przycisk Zastosuj do siatki.</span><span class="sxs-lookup"><span data-stu-id="78b65-162">Click Apply to grid.</span></span>
    * <span data-ttu-id="78b65-163">Teraz użyjemy funkcji zmiany masowej, aby skorygować punkty odniesienia minimalny i maksymalny na każdym poziomie.</span><span class="sxs-lookup"><span data-stu-id="78b65-163">Now we'll use the mass change function to adjust the Minimum and Maximum reference points for each level.</span></span> <span data-ttu-id="78b65-164">W tym przykładzie zostanie użyta rozpiętość 50%, tak że minimalny punkt odniesienia zostanie skorygowany o -20%, a punkt maksymalny o +20%.</span><span class="sxs-lookup"><span data-stu-id="78b65-164">This example will use a 50% spread so the Minimum reference point will be adjusted -20% and the Maximum will be adjusted +20%.</span></span>  
23. <span data-ttu-id="78b65-165">W polu Kwota korekty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="78b65-165">In the Adjustment amount field, enter a number.</span></span>
24. <span data-ttu-id="78b65-166">W polu Punkt odniesienia wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-166">In the Reference point field, enter or select a value.</span></span>
25. <span data-ttu-id="78b65-167">Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.</span><span class="sxs-lookup"><span data-stu-id="78b65-167">In the list, mark or unmark all rows.</span></span>
26. <span data-ttu-id="78b65-168">Kliknij przycisk Zastosuj do siatki.</span><span class="sxs-lookup"><span data-stu-id="78b65-168">Click Apply to grid.</span></span>
27. <span data-ttu-id="78b65-169">W polu Kwota korekty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="78b65-169">In the Adjustment amount field, enter a number.</span></span>
28. <span data-ttu-id="78b65-170">W polu Punkt odniesienia wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78b65-170">In the Reference point field, enter or select a value.</span></span>
29. <span data-ttu-id="78b65-171">Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.</span><span class="sxs-lookup"><span data-stu-id="78b65-171">In the list, mark or unmark all rows.</span></span>
30. <span data-ttu-id="78b65-172">Kliknij przycisk Zastosuj do siatki.</span><span class="sxs-lookup"><span data-stu-id="78b65-172">Click Apply to grid.</span></span>


