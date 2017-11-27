--- 
title: Konfigurowanie konteneryzacji
description: "W tej procedurze opisano sposób zautomatyzowania konteneryzacji ładunków w module Zarządzanie magazynem."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: c5faf926071dec5d2ddc1c9e921a98ecd0754917
ms.contentlocale: pl-pl
ms.lasthandoff: 11/02/2017

---
# <a name="set-up-containerization"></a><span data-ttu-id="c6eb1-103">Konfigurowanie konteneryzacji</span><span class="sxs-lookup"><span data-stu-id="c6eb1-103">Set up containerization</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c6eb1-104">W tej procedurze opisano sposób zautomatyzowania konteneryzacji ładunków w module Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-104">This procedure describes how to automate the containerization of loads in Warehouse management.</span></span> <span data-ttu-id="c6eb1-105">Podczas przetwarzania grupy czynności funkcja automatycznej konteneryzacji tworzy kontenery i pracę pobrania dla wysyłek, a wiersze pracy można podzielić na ilości mieszczące się w kontenerach.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-105">Automated containerization creates containers and the picking work for shipments when a wave is processed and work lines can be split into quantities that fit the containers.</span></span> <span data-ttu-id="c6eb1-106">W ten sposób pracownicy magazynu mogą pobierać towary bezpośrednio do wybranego kontenera.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-106">This helps warehouse workers to pick the items directly into the chosen container.</span></span> <span data-ttu-id="c6eb1-107">W porównaniu do ręcznego procesu pakowania zadania takie jak tworzenie kontenerów, przypisywania towarów i zamykanie kontenerów są zautomatyzowane przez system.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-107">Compared to the manual packing process, tasks such as creating containers, assigning items, and closing containers are automated by the system.</span></span> <span data-ttu-id="c6eb1-108">Ta procedura używa firmy demonstracyjnej USMF i jest wykonywana przez kierownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-108">This procedure uses the USMF demo company and is performed by a Warehouse manager.</span></span>


## <a name="set-up-a-wave-template"></a><span data-ttu-id="c6eb1-109">Konfigurowanie szablonu grupy czynności</span><span class="sxs-lookup"><span data-stu-id="c6eb1-109">Set up a wave template</span></span>
1. <span data-ttu-id="c6eb1-110">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Grupy czynności > Szablony grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-110">Go to Warehouse management > Setup > Waves > Wave templates.</span></span>
2. <span data-ttu-id="c6eb1-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-111">Click New.</span></span>
3. <span data-ttu-id="c6eb1-112">W polu Nazwa szablonu grupy czynności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-112">In the Wave template name field, type a value.</span></span>
4. <span data-ttu-id="c6eb1-113">W polu Opis szablonu grupy czynności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-113">In the Wave template description field, type a value.</span></span>
5. <span data-ttu-id="c6eb1-114">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="c6eb1-115">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-115">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="c6eb1-116">Rozwiń sekcję Metody.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-116">Expand the Methods section.</span></span>
    * <span data-ttu-id="c6eb1-117">W okienku Wybrane metody są wyświetlane metody dla wybranego typu szablonu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-117">The Selected methods pane lists the methods for the selected wave template type.</span></span> <span data-ttu-id="c6eb1-118">Szablon grupy czynności musi zawierać metodę konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-118">The wave template must include the containerize method.</span></span>  
8. <span data-ttu-id="c6eb1-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="c6eb1-120">W polu Kod kroku grupy czynności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-120">In the Wave step code field, type a value.</span></span>
    * <span data-ttu-id="c6eb1-121">Wprowadź kod kroku grupy czynności dla dodanej metody. Może to być dowolny kod.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-121">Enter a Wave step code for the added method, which can be any code.</span></span> <span data-ttu-id="c6eb1-122">Istnieje możliwość dodania metody więcej niż jeden raz oraz przypisania różnych kodów kroków grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-122">It’s possible to add the method more than once and assign different wave step codes.</span></span> <span data-ttu-id="c6eb1-123">Aby to zrobić, zaznacz dla tej metody opcję Cykliczny na stronie Metody przetwarzania grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-123">To do this, select Repeatable for this method in the Wave process methods page.</span></span>  
10. <span data-ttu-id="c6eb1-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-124">Click Save.</span></span>
11. <span data-ttu-id="c6eb1-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-125">Close the page.</span></span>

## <a name="set-up-a-container-type"></a><span data-ttu-id="c6eb1-126">Konfigurowanie typu kontenera</span><span class="sxs-lookup"><span data-stu-id="c6eb1-126">Set up a container type</span></span>
1. <span data-ttu-id="c6eb1-127">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Typy kontenerów.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
    * <span data-ttu-id="c6eb1-128">Kontenery można zdefiniować na stronie Typy kontenerów.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-128">You can define your containers in the Container types page.</span></span> <span data-ttu-id="c6eb1-129">Można skonfigurować wymiary fizyczne kontenera, w tym tarę, maksymalną wagę, maksymalną objętość, długość, szerokość i wysokość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-129">You can configure the physical dimensions of containers including tare weight, maximum weight, maximum volume, length, width, and height.</span></span> <span data-ttu-id="c6eb1-130">W tym przykładzie mamy trzy różne rozmiary skrzynek.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-130">In this example, we have three different sizes of boxes.</span></span>  
2. <span data-ttu-id="c6eb1-131">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-131">Click New.</span></span>
3. <span data-ttu-id="c6eb1-132">W polu Kod typu kontenera wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="c6eb1-133">W polu Waga tara wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-133">In the Tare weight field, enter a number.</span></span>
5. <span data-ttu-id="c6eb1-134">W polu Maksymalna waga wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-134">In the Maximum weight field, enter a number.</span></span>
6. <span data-ttu-id="c6eb1-135">W polu Objętość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-135">In the Volume field, enter a number.</span></span>
7. <span data-ttu-id="c6eb1-136">W polu Długość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-136">In the Length field, enter a number.</span></span>
8. <span data-ttu-id="c6eb1-137">W polu Szerokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-137">In the Width field, enter a number.</span></span>
9. <span data-ttu-id="c6eb1-138">W polu Wysokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-138">In the Height field, enter a number.</span></span>
10. <span data-ttu-id="c6eb1-139">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-139">In the Description field, type a value.</span></span>
11. <span data-ttu-id="c6eb1-140">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-140">Click Save.</span></span>
12. <span data-ttu-id="c6eb1-141">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-141">Click New.</span></span>
13. <span data-ttu-id="c6eb1-142">W polu Kod typu kontenera wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-142">In the Container type code field, type a value.</span></span>
14. <span data-ttu-id="c6eb1-143">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-143">In the Description field, type a value.</span></span>
15. <span data-ttu-id="c6eb1-144">W polu Waga tara wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-144">In the Tare weight field, enter a number.</span></span>
16. <span data-ttu-id="c6eb1-145">W polu Maksymalna waga wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-145">In the Maximum weight field, enter a number.</span></span>
17. <span data-ttu-id="c6eb1-146">W polu Objętość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-146">In the Volume field, enter a number.</span></span>
18. <span data-ttu-id="c6eb1-147">W polu Długość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-147">In the Length field, enter a number.</span></span>
19. <span data-ttu-id="c6eb1-148">W polu Szerokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-148">In the Width field, enter a number.</span></span>
20. <span data-ttu-id="c6eb1-149">W polu Wysokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-149">In the Height field, enter a number.</span></span>
21. <span data-ttu-id="c6eb1-150">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-150">Click Save.</span></span>
22. <span data-ttu-id="c6eb1-151">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-151">Click New.</span></span>
23. <span data-ttu-id="c6eb1-152">W polu Kod typu kontenera wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-152">In the Container type code field, type a value.</span></span>
24. <span data-ttu-id="c6eb1-153">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-153">In the Description field, type a value.</span></span>
25. <span data-ttu-id="c6eb1-154">W polu Waga tara wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-154">In the Tare weight field, enter a number.</span></span>
26. <span data-ttu-id="c6eb1-155">W polu Maksymalna waga wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-155">In the Maximum weight field, enter a number.</span></span>
27. <span data-ttu-id="c6eb1-156">W polu Objętość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-156">In the Volume field, enter a number.</span></span>
28. <span data-ttu-id="c6eb1-157">W polu Długość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-157">In the Length field, enter a number.</span></span>
29. <span data-ttu-id="c6eb1-158">W polu Szerokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-158">In the Width field, enter a number.</span></span>
30. <span data-ttu-id="c6eb1-159">W polu Wysokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-159">In the Height field, enter a number.</span></span>
31. <span data-ttu-id="c6eb1-160">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-160">Click Save.</span></span>
32. <span data-ttu-id="c6eb1-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-161">Close the page.</span></span>

## <a name="set-up-a-container-group"></a><span data-ttu-id="c6eb1-162">Ustawianie grupy kontenera</span><span class="sxs-lookup"><span data-stu-id="c6eb1-162">Set up a container group</span></span>
1. <span data-ttu-id="c6eb1-163">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Grupy kontenerów.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-163">Go to Warehouse management > Setup > Containers > Container groups.</span></span>
2. <span data-ttu-id="c6eb1-164">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-164">Click New.</span></span>
    * <span data-ttu-id="c6eb1-165">Można skonfigurować logiczne grupy typów kontenerów.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-165">You can set up logical groups of container types.</span></span> <span data-ttu-id="c6eb1-166">Dla każdej grupy można określić kolejność pakowania kontenerów oraz procent wypełnienia każdego kontenera.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-166">For each group, you can specify the sequence in which to pack the containers and the percentage of the containers to fill.</span></span> <span data-ttu-id="c6eb1-167">Wymiary rozmiaru towaru są używane do określenia, czy zmieści się on w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-167">The size dimensions of the item is used to determine whether it will fit in a container.</span></span> <span data-ttu-id="c6eb1-168">Używany jest kontener, którym wymiarami jest najbardziej zbliżony do towaru.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-168">The container that is closest to the size dimensions of the item is used.</span></span> <span data-ttu-id="c6eb1-169">Jeśli masz wiele typów kontenerów w grupie, zaleca się rozmieszczenie kolejności według rozmiarów, tak, aby największy kontener był pierwszy, numer 1 w sekwencji, a najmniejszy kontener ostatni.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-169">If you have multiple container types in a group, we recommend that you arrange the sequence by size, so that the largest container is first, number 1 in the sequence, and the smallest container is last.</span></span>    
3. <span data-ttu-id="c6eb1-170">W polu Identyfikator grupy kontenerów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-170">In the Container group ID field, type a value.</span></span>
4. <span data-ttu-id="c6eb1-171">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-171">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c6eb1-172">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-172">Click New.</span></span>
6. <span data-ttu-id="c6eb1-173">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-173">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="c6eb1-174">W polu Typ kontenera wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-174">In the Container type field, enter or select a value.</span></span>
8. <span data-ttu-id="c6eb1-175">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-175">Click New.</span></span>
9. <span data-ttu-id="c6eb1-176">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-176">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="c6eb1-177">W polu Typ kontenera wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-177">In the Container type field, enter or select a value.</span></span>
11. <span data-ttu-id="c6eb1-178">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-178">Click New.</span></span>
12. <span data-ttu-id="c6eb1-179">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-179">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="c6eb1-180">W polu Typ kontenera wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-180">In the Container type field, enter or select a value.</span></span>
14. <span data-ttu-id="c6eb1-181">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-181">Click Save.</span></span>
15. <span data-ttu-id="c6eb1-182">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-182">Close the page.</span></span>

## <a name="set-up-a-container-build-template"></a><span data-ttu-id="c6eb1-183">Ustawianie szablonu kompilacji kontenera</span><span class="sxs-lookup"><span data-stu-id="c6eb1-183">Set up a container build template</span></span>
1. <span data-ttu-id="c6eb1-184">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Szablony kompilacji kontenerów.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-184">Go to Warehouse management > Setup > Containers > Container build templates.</span></span>
2. <span data-ttu-id="c6eb1-185">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-185">Click New.</span></span>
    * <span data-ttu-id="c6eb1-186">Szablon kompilacji kontenera bazuje na doborze wykonywanych procesów konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-186">The container build template is based on which of the containerization processes are performed.</span></span> <span data-ttu-id="c6eb1-187">Każdy szablon kompilacji kontenera definiuje jeden proces konteneryzacji, który będzie używany przez szablon grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-187">Each container build template defines one containerization process that will be used by a wave template.</span></span> <span data-ttu-id="c6eb1-188">Opcja Edytuj kwerendę umożliwia określenie warunków, w oparciu o które będzie przetwarzany wybrany szablon.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-188">The Edit query option allows you to define the conditions on which the selected template will be processed.</span></span> <span data-ttu-id="c6eb1-189">Na przykład można uruchomić konteneryzację tylko dla określonych odbiorców, produktów lub magazynów albo też dodać odpowiednie zakresy zapytań do szablonu.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-189">For example, you may want to only run containerization for specific customers, products, or warehouses or you can add the corresponding query ranges to the template.</span></span> <span data-ttu-id="c6eb1-190">Wartość w polu Kod kroku grupy czynności określa, jak szablon kompilacji kontenera jest powiązany z krokami w szablonie grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-190">The Wave step code field is how a container build template is linked to steps in a wave template.</span></span> <span data-ttu-id="c6eb1-191">Podczas wykonywania grupy czynności system ustala, które szablony kompilacji kontenera są używane do inicjowania konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-191">When a wave is executed, it determines which container build template(s) are used to initiate containerization.</span></span> <span data-ttu-id="c6eb1-192">Wartość w polu Rodzaje podstawowej kwerendy określa, co należy zapakować i na czym należy oprzeć filtr zapytania.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-192">The Base query type field determines what to pack and what to base the filter query on.</span></span>  
3. <span data-ttu-id="c6eb1-193">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-193">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c6eb1-194">W polu Identyfikator szablonu kontenera wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-194">In the Container template ID field, type a value.</span></span>
5. <span data-ttu-id="c6eb1-195">W polu Identyfikator grupy kontenerów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-195">In the Container group ID field, enter or select a value.</span></span>
6. <span data-ttu-id="c6eb1-196">W polu Kod kroku grupy czynności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-196">In the Wave step code field, type a value.</span></span>
7. <span data-ttu-id="c6eb1-197">Zaznacz pole wyboru Zezwalaj na dzielenie pobierania.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-197">Select the Allow split picks check box.</span></span>
8. <span data-ttu-id="c6eb1-198">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-198">Click Save.</span></span>
9. <span data-ttu-id="c6eb1-199">Kliknij opcję Ograniczenia mieszające kontenera.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-199">Click Container mixing constraints.</span></span>
    * <span data-ttu-id="c6eb1-200">Funkcja Przerwy logiki łączenia pozwala skonfigurować reguły dla wierszy alokacji pakowania w kontenerach.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-200">Mixing logic breaks allows you to set up rules for packing allocation lines in containers.</span></span> <span data-ttu-id="c6eb1-201">Na przykład jeśli dodasz pole Numer pozycji, podczas przypisywania towarów do kontenerów będą tworzone nowe kontenery dla nowych numerów towarów.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-201">For example, if you add the Item number field, when items are assigned to containers, a new container will be created when there is a new item number.</span></span> <span data-ttu-id="c6eb1-202">Uniemożliwi to pracownikom pakowanie wierszy alokacji dla dwóch różnych odbiorców w tym samym kontenerze.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-202">This is will prevent workers from packing allocations lines for two different customers in the same container.</span></span>  
10. <span data-ttu-id="c6eb1-203">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-203">Click New.</span></span>
11. <span data-ttu-id="c6eb1-204">W polu Tabela wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-204">In the Table field, select an option.</span></span>
12. <span data-ttu-id="c6eb1-205">W polu Wybór pola wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-205">In the Field Select field, enter or select a value.</span></span>
13. <span data-ttu-id="c6eb1-206">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c6eb1-206">Click OK.</span></span>


