---
title: Definiowanie inwentaryzacji ciągłej
description: Inwentaryzacja cykliczna jest procesem magazynowym, który służy do inspekcji pozycji magazynowych.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8b7f39fc9a91d9fe219445e409d000266e24775
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435582"
---
# <a name="define-cycle-counting"></a><span data-ttu-id="ca6cb-103">Definiowanie inwentaryzacji ciągłej</span><span class="sxs-lookup"><span data-stu-id="ca6cb-103">Define cycle counting</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca6cb-104">Inwentaryzacja cykliczna jest procesem magazynowym, który służy do inspekcji pozycji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="ca6cb-105">To nagranie zadania pokazuje, jak ustawić domyślny priorytet pracy inwentaryzacji, włączyć element menu urządzenia przenośnego do przetwarzania operacji zarówno pobrania, jak i inwentaryzacji, włączyć wyzwalacz progowy inwentaryzacji, gdy lokalizacja się opróżni, oraz włączyć plan inwentaryzacji ciągłej dla określonego towaru w określonym magazynie.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="ca6cb-106">Zazwyczaj te zadania wykonuje kierownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="ca6cb-107">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="ca6cb-108">Ustawianie priorytetu pracy inwentaryzacji</span><span class="sxs-lookup"><span data-stu-id="ca6cb-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="ca6cb-109">Otwórz **Okienko nawigacji**, **Moduły > Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-109">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="ca6cb-110">Kliknij kartę **Inwentaryzacja ciągła**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-110">Click the **Cycle counting** tab.</span></span>
3. <span data-ttu-id="ca6cb-111">W polu **Domyślny priorytet pracy inwentaryzacji ciągłej** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-111">In the **Default cycle count work priority** field, enter a number.</span></span> <span data-ttu-id="ca6cb-112">Ten krok spowoduje zmianę priorytetu pracy inwentaryzacji ciągłej względem innych typów pracy w magazynie.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="ca6cb-113">Wpisując liczbę niższą niż dla innych typów prac, podwyższasz priorytet pracy inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="ca6cb-114">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-114">Click **Save**.</span></span>
5. <span data-ttu-id="ca6cb-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="ca6cb-116">Włączanie obsługi urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="ca6cb-116">Enable the mobile device</span></span>
1. <span data-ttu-id="ca6cb-117">W **okienku nawigacji** wybierz kolejno opcje **Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-117">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="ca6cb-118">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-118">Click **New**.</span></span>
3. <span data-ttu-id="ca6cb-119">W polu **Nazwa elementu menu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-119">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="ca6cb-120">W polu **Tytuł** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-120">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="ca6cb-121">W polu **Tryb** wybierz opcję „Praca”.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-121">In the **Mode** field, select 'Work'.</span></span>
6. <span data-ttu-id="ca6cb-122">W opcji **Użyj istniejącej pracy** zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-122">Set the **Use existing work** option to Yes.</span></span> <span data-ttu-id="ca6cb-123">Gdy w tej opcji ustawisz wartość Tak, system będzie szukał istniejącej pracy w przypadku użycia elementu menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="ca6cb-124">W polu **Sterowane przez** wybierz opcję „Sterowane przez system”.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-124">In the **Directed by** field, select 'System directed'.</span></span> <span data-ttu-id="ca6cb-125">Jeżeli zaznaczysz opcję „Sterowane przez system”, pracownik magazynu zostanie skierowany do otwartej pracy należącej do zdefiniowanych klas pracy.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="ca6cb-126">(Te klasy pracy zostaną utworzone w następnym kroku).</span><span class="sxs-lookup"><span data-stu-id="ca6cb-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="ca6cb-127">Rozwiń skróconą kartę **Klasy robocze**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-127">Expand the **Work classes** fastTab.</span></span> <span data-ttu-id="ca6cb-128">Następnie utworzymy dwie klasy pracy, które będą używane z tym elementem menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="ca6cb-129">Użycie elementu menu spowoduje wykonanie zapytania o te klasy pracy i wyświetlenie użytkownikowi pracy o najwyższym priorytecie.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="ca6cb-130">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-130">Click **New**.</span></span>
10. <span data-ttu-id="ca6cb-131">W polu **Identyfikator klasy roboczej** wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-131">In the **Work class ID** field, select a value.</span></span>
11. <span data-ttu-id="ca6cb-132">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-132">Click **New**.</span></span>
12. <span data-ttu-id="ca6cb-133">W polu **Identyfikator klasy roboczej** wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-133">In the **Work class ID** field, select a value.</span></span>
13. <span data-ttu-id="ca6cb-134">W **okienku akcji** kliknij pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-134">In the **Action Pane**, click **Save**.</span></span>
14. <span data-ttu-id="ca6cb-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-135">Close the page.</span></span>
15. <span data-ttu-id="ca6cb-136">W **okienku nawigacji** wybierz kolejno **Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Menu urządzeń przenośnych**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-136">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
16. <span data-ttu-id="ca6cb-137">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="ca6cb-138">W drzewie wybierz element menu, który został właśnie utworzony.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="ca6cb-139">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-139">Click **Edit**.</span></span>
19. <span data-ttu-id="ca6cb-140">Kliknij strzałkę, aby dodać element menu do menu.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="ca6cb-141">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-141">Click **Save**.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="ca6cb-142">Tworzenie progu inwentaryzacji</span><span class="sxs-lookup"><span data-stu-id="ca6cb-142">Create a counting threshold</span></span>
1. <span data-ttu-id="ca6cb-143">W **okienku nawigacji** przejdź do **Moduły > Zarządzenie magazynem > Ustawienia > Inwentaryzacja ciągła > Progi inwentaryzacji ciągłej**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-143">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count thresholds**.</span></span>
2. <span data-ttu-id="ca6cb-144">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-144">Click **New**.</span></span>
3. <span data-ttu-id="ca6cb-145">W polu **Identyfikator progu inwentaryzacji ciągłej** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-145">In the **Cycle counting threshold ID** field, type a value.</span></span>
4. <span data-ttu-id="ca6cb-146">Ustaw opcję **Przetwarzaj natychmiast inwentaryzację ciągłą** na Tak.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-146">Set the **Process cycle counting immediately** option to Yes.</span></span>
5. <span data-ttu-id="ca6cb-147">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-147">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="ca6cb-148">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-148">Click **Save**.</span></span>
7. <span data-ttu-id="ca6cb-149">Kliknij opcję **Wybierz lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-149">Click **Select locations**.</span></span>
8. <span data-ttu-id="ca6cb-150">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="ca6cb-151">W polu **Kryteria** wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-151">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="ca6cb-152">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-152">Click **OK**.</span></span>
11. <span data-ttu-id="ca6cb-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="ca6cb-154">Tworzenie planu inwentaryzacji ciągłej</span><span class="sxs-lookup"><span data-stu-id="ca6cb-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="ca6cb-155">W **okienku nawigacji** przejdź do **Moduły > Zarządzenie magazynem > Ustawienia > Inwentaryzacja ciągła > Plany inwentaryzacji ciągłej**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-155">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count plans**.</span></span>
2. <span data-ttu-id="ca6cb-156">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-156">Click **New**.</span></span>
3. <span data-ttu-id="ca6cb-157">W polu **Identyfikator planu inwentaryzacji ciągłej** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-157">In the **Cycle counting plan ID** field, type a value.</span></span>
4. <span data-ttu-id="ca6cb-158">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-158">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="ca6cb-159">W polu **Maksymalna liczba inwentaryzacji ciągłych** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-159">In the **Maximum number of cycle counts** field, enter a number.</span></span>
6. <span data-ttu-id="ca6cb-160">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-160">Click **Save**.</span></span>
7. <span data-ttu-id="ca6cb-161">Kliknij opcję **Wybierz lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-161">Click **Select locations**.</span></span>
8. <span data-ttu-id="ca6cb-162">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="ca6cb-163">W polu **Kryteria** wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-163">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="ca6cb-164">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-164">Click **OK**.</span></span>
11. <span data-ttu-id="ca6cb-165">W polu **Dni między inwentaryzacją ciągłą** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-165">In the **Days between cycle counting** field, enter a number.</span></span> <span data-ttu-id="ca6cb-166">Na przykład jeśli wartość ustawiona w polu **Dni między inwentaryzacją ciągłą** to 5, praca inwentaryzacji ciągłej będzie tworzona co pięć dni.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-166">For example, if the **Days between cycle counting** field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="ca6cb-167">Jednak jeśli praca inwentaryzacji ciągłej jest przetwarzania w trzecim dniu, następna praca inwentaryzacji ciągłej zostanie utworzona 5 dni po przetworzeniu ostatniej inwentaryzacji ciągłej, czyli w dniu ósmym.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="ca6cb-168">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-168">Click **Save**.</span></span>
13. <span data-ttu-id="ca6cb-169">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-169">Click **New**.</span></span>
14. <span data-ttu-id="ca6cb-170">W polu **Numer sekwencyjny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-170">In the **Sequence number** field, enter a number.</span></span> <span data-ttu-id="ca6cb-171">Sortowanie odbywa się w porządku od najmniejszej liczby do największej liczby.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="ca6cb-172">Wartość musi być większa od 0 (zera).</span><span class="sxs-lookup"><span data-stu-id="ca6cb-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="ca6cb-173">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="ca6cb-174">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-174">In the **Description** field, type a value.</span></span>
17. <span data-ttu-id="ca6cb-175">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-175">Click **Save**.</span></span>
18. <span data-ttu-id="ca6cb-176">Kliknij opcję **Definiuj zapytanie produktu**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-176">Click **Define product** query.</span></span>
19. <span data-ttu-id="ca6cb-177">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="ca6cb-178">W polu **Kryteria** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-178">In the **Criteria** field, enter or select a value.</span></span>
21. <span data-ttu-id="ca6cb-179">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-179">Click **OK**.</span></span>
22. <span data-ttu-id="ca6cb-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ca6cb-180">Close the page.</span></span>

