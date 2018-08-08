--- 
title: "Definiowanie inwentaryzacji ciągłej"
description: "Inwentaryzacja cykliczna jest procesem magazynowym, który służy do inspekcji pozycji magazynowych."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2832547f81b0153d42ac4664184f18bd66f1acdd
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="define-cycle-counting"></a><span data-ttu-id="cbdd4-103">Definiowanie inwentaryzacji ciągłej</span><span class="sxs-lookup"><span data-stu-id="cbdd4-103">Define cycle counting</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cbdd4-104">Inwentaryzacja cykliczna jest procesem magazynowym, który służy do inspekcji pozycji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="cbdd4-105">To nagranie zadania pokazuje, jak ustawić domyślny priorytet pracy inwentaryzacji, włączyć element menu urządzenia przenośnego do przetwarzania operacji zarówno pobrania, jak i inwentaryzacji, włączyć wyzwalacz progowy inwentaryzacji, gdy lokalizacja się opróżni, oraz włączyć plan inwentaryzacji ciągłej dla określonego towaru w określonym magazynie.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="cbdd4-106">Zazwyczaj te zadania wykonuje kierownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="cbdd4-107">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="cbdd4-108">Ustawianie priorytetu pracy inwentaryzacji</span><span class="sxs-lookup"><span data-stu-id="cbdd4-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="cbdd4-109">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-109">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="cbdd4-110">Kliknij kartę Inwentaryzacja ciągła.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-110">Click the Cycle counting tab.</span></span>
3. <span data-ttu-id="cbdd4-111">W polu Domyślny priorytet pracy inwentaryzacji ciągłej wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-111">In the Default cycle count work priority field, enter a number.</span></span>
    * <span data-ttu-id="cbdd4-112">Ten krok spowoduje zmianę priorytetu pracy inwentaryzacji ciągłej względem innych typów pracy w magazynie.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="cbdd4-113">Wpisując liczbę niższą niż dla innych typów prac, podwyższasz priorytet pracy inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="cbdd4-114">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-114">Click Save.</span></span>
5. <span data-ttu-id="cbdd4-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="cbdd4-116">Włączanie obsługi urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="cbdd4-116">Enable the mobile device</span></span>
1. <span data-ttu-id="cbdd4-117">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-117">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="cbdd4-118">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-118">Click New.</span></span>
3. <span data-ttu-id="cbdd4-119">W polu Nazwa elementu menu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-119">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="cbdd4-120">W polu Tytuł wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-120">In the Title field, type a value.</span></span>
5. <span data-ttu-id="cbdd4-121">W polu Tryb wybierz opcję „Praca”.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-121">In the Mode field, select 'Work'.</span></span>
6. <span data-ttu-id="cbdd4-122">W opcji Użyj istniejącej pracy zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-122">Set the Use existing work option to Yes.</span></span>
    * <span data-ttu-id="cbdd4-123">Gdy w tej opcji ustawisz wartość Tak, system będzie szukał istniejącej pracy w przypadku użycia elementu menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="cbdd4-124">W polu Sterowane przez wybierz opcję „Sterowane przez system”.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-124">In the Directed by field, select 'System directed'.</span></span>
    * <span data-ttu-id="cbdd4-125">Jeżeli zaznaczysz opcję „Sterowane przez system”, pracownik magazynu zostanie skierowany do otwartej pracy należącej do zdefiniowanych klas pracy.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="cbdd4-126">(Te klasy pracy zostaną utworzone w następnym kroku).</span><span class="sxs-lookup"><span data-stu-id="cbdd4-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="cbdd4-127">Rozwiń lub zwiń sekcję Klasy robocze.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-127">Expand or collapse the Work classes section.</span></span>
    * <span data-ttu-id="cbdd4-128">Następnie utworzymy dwie klasy pracy, które będą używane z tym elementem menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="cbdd4-129">Użycie elementu menu spowoduje wykonanie zapytania o te klasy pracy i wyświetlenie użytkownikowi pracy o najwyższym priorytecie.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="cbdd4-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-130">Click New.</span></span>
10. <span data-ttu-id="cbdd4-131">W polu Identyfikator klasy roboczej wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-131">In the Work class ID field, select a value.</span></span>
11. <span data-ttu-id="cbdd4-132">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-132">Click New.</span></span>
12. <span data-ttu-id="cbdd4-133">W polu Identyfikator klasy roboczej wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-133">In the Work class ID field, select a value.</span></span>
13. <span data-ttu-id="cbdd4-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-134">Click Save.</span></span>
14. <span data-ttu-id="cbdd4-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-135">Close the page.</span></span>
15. <span data-ttu-id="cbdd4-136">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Menu urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-136">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
16. <span data-ttu-id="cbdd4-137">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="cbdd4-138">W drzewie wybierz element menu, który został właśnie utworzony.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="cbdd4-139">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-139">Click Edit.</span></span>
19. <span data-ttu-id="cbdd4-140">Kliknij strzałkę, aby dodać element menu do menu.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="cbdd4-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-141">Click Save.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="cbdd4-142">Tworzenie progu inwentaryzacji</span><span class="sxs-lookup"><span data-stu-id="cbdd4-142">Create a counting threshold</span></span>
1. <span data-ttu-id="cbdd4-143">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Inwentaryzacja ciągła > Progi inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-143">Go to Warehouse management > Setup > Cycle counting > Cycle count thresholds.</span></span>
2. <span data-ttu-id="cbdd4-144">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-144">Click New.</span></span>
3. <span data-ttu-id="cbdd4-145">W polu Identyfikator progu inwentaryzacji ciągłej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-145">In the Cycle counting threshold ID field, type a value.</span></span>
4. <span data-ttu-id="cbdd4-146">Ustaw opcję Przetwarzaj natychmiast inwentaryzację ciągłą na Tak.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-146">Set the Process cycle counting immediately option to Yes.</span></span>
5. <span data-ttu-id="cbdd4-147">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-147">In the Description field, type a value.</span></span>
6. <span data-ttu-id="cbdd4-148">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-148">Click Save.</span></span>
7. <span data-ttu-id="cbdd4-149">Kliknij opcję Wybierz lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-149">Click Select locations.</span></span>
8. <span data-ttu-id="cbdd4-150">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="cbdd4-151">W polu Kryteria wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-151">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="cbdd4-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-152">Click OK.</span></span>
11. <span data-ttu-id="cbdd4-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="cbdd4-154">Tworzenie planu inwentaryzacji ciągłej</span><span class="sxs-lookup"><span data-stu-id="cbdd4-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="cbdd4-155">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Inwentaryzacja ciągła > Plany inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-155">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="cbdd4-156">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-156">Click New.</span></span>
3. <span data-ttu-id="cbdd4-157">W polu Identyfikator planu inwentaryzacji ciągłej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-157">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="cbdd4-158">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-158">In the Description field, type a value.</span></span>
5. <span data-ttu-id="cbdd4-159">W polu Maksymalna liczba inwentaryzacji ciągłych wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-159">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="cbdd4-160">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-160">Click Save.</span></span>
7. <span data-ttu-id="cbdd4-161">Kliknij opcję Wybierz lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-161">Click Select locations.</span></span>
8. <span data-ttu-id="cbdd4-162">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="cbdd4-163">W polu Kryteria wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-163">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="cbdd4-164">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-164">Click OK.</span></span>
11. <span data-ttu-id="cbdd4-165">W polu Dni między inwentaryzacją ciągłą wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-165">In the Days between cycle counting field, enter a number.</span></span>
    * <span data-ttu-id="cbdd4-166">Na przykład jeśli wartość ustawiona w polu Dni między inwentaryzacją ciągłą to 5, praca inwentaryzacji ciągłej będzie tworzona co pięć dni.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-166">For example, if the Days between cycle counting field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="cbdd4-167">Jednak jeśli praca inwentaryzacji ciągłej jest przetwarzania w trzecim dniu, następna praca inwentaryzacji ciągłej zostanie utworzona 5 dni po przetworzeniu ostatniej inwentaryzacji ciągłej, czyli w dniu ósmym.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="cbdd4-168">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-168">Click Save.</span></span>
13. <span data-ttu-id="cbdd4-169">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-169">Click New.</span></span>
14. <span data-ttu-id="cbdd4-170">W polu Numer sekwencyjny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-170">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="cbdd4-171">Sortowanie odbywa się w porządku od najmniejszej liczby do największej liczby.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="cbdd4-172">Wartość musi być większa od 0 (zera).</span><span class="sxs-lookup"><span data-stu-id="cbdd4-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="cbdd4-173">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="cbdd4-174">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-174">In the Description field, type a value.</span></span>
17. <span data-ttu-id="cbdd4-175">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-175">Click Save.</span></span>
18. <span data-ttu-id="cbdd4-176">Kliknij opcję Definiuj zapytanie produktu.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-176">Click Define product query.</span></span>
19. <span data-ttu-id="cbdd4-177">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="cbdd4-178">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-178">In the Criteria field, enter or select a value.</span></span>
21. <span data-ttu-id="cbdd4-179">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-179">Click OK.</span></span>
22. <span data-ttu-id="cbdd4-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cbdd4-180">Close the page.</span></span>


