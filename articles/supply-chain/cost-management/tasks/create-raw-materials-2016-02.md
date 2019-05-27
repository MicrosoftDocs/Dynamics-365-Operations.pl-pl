---
title: Tworzenie surowców (tylko luty 2016)
description: To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 869acddf6f7e9754bb4952176ded4b22c74eaffd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563303"
---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="e8155-103">Tworzenie surowców (tylko luty 2016)</span><span class="sxs-lookup"><span data-stu-id="e8155-103">Create raw materials (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e8155-104">To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów.</span><span class="sxs-lookup"><span data-stu-id="e8155-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="e8155-105">Jest to trzecie zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="e8155-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="e8155-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e8155-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="e8155-107">Tworzenie pierwszego materiału</span><span class="sxs-lookup"><span data-stu-id="e8155-107">Create the first material</span></span>
1. <span data-ttu-id="e8155-108">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="e8155-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="e8155-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e8155-109">Click New.</span></span>
3. <span data-ttu-id="e8155-110">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="e8155-111">W tym przykładzie wpisz ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="e8155-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="e8155-112">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-113">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="e8155-113">Select STD.</span></span> <span data-ttu-id="e8155-114">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="e8155-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="e8155-115">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-116">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="e8155-116">For example, select Audio.</span></span> <span data-ttu-id="e8155-117">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="e8155-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="e8155-118">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-119">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="e8155-119">Select SiteWH.</span></span> <span data-ttu-id="e8155-120">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="e8155-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="e8155-121">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-122">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e8155-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="e8155-123">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="e8155-123">Select None.</span></span>  
8. <span data-ttu-id="e8155-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e8155-124">Click OK.</span></span>
9. <span data-ttu-id="e8155-125">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="e8155-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="e8155-126">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="e8155-126">Click Default order settings.</span></span>
11. <span data-ttu-id="e8155-127">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-128">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="e8155-129">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-130">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="e8155-131">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-132">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="e8155-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-133">Close the page.</span></span>
15. <span data-ttu-id="e8155-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-134">Close the page.</span></span>
16. <span data-ttu-id="e8155-135">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e8155-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e8155-136">Kliknij pozycję ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="e8155-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="e8155-137">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e8155-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="e8155-138">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="e8155-139">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="e8155-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="e8155-140">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e8155-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="e8155-141">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="e8155-141">Click Item price.</span></span>
21. <span data-ttu-id="e8155-142">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e8155-142">Click New.</span></span>
22. <span data-ttu-id="e8155-143">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-144">W tym przykładzie wybierz wartość 10, która odpowiada typowi wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="e8155-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="e8155-145">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-146">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="e8155-147">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e8155-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="e8155-148">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="e8155-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="e8155-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e8155-149">Click Save.</span></span>
26. <span data-ttu-id="e8155-150">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="e8155-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="e8155-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-151">Close the page.</span></span>
28. <span data-ttu-id="e8155-152">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="e8155-153">Tworzenie drugiego materiału</span><span class="sxs-lookup"><span data-stu-id="e8155-153">Create the second material</span></span>
1. <span data-ttu-id="e8155-154">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e8155-154">Click New.</span></span>
2. <span data-ttu-id="e8155-155">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="e8155-156">W tym przykładzie wpisz ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="e8155-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="e8155-157">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-158">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="e8155-158">Select STD.</span></span> <span data-ttu-id="e8155-159">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="e8155-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="e8155-160">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-161">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="e8155-161">For example, select Audio.</span></span> <span data-ttu-id="e8155-162">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="e8155-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="e8155-163">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-164">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="e8155-164">Select SiteWH.</span></span> <span data-ttu-id="e8155-165">W tym przykładzie będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="e8155-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="e8155-166">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-167">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e8155-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="e8155-168">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="e8155-168">Select None.</span></span>  
7. <span data-ttu-id="e8155-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e8155-169">Click OK.</span></span>
8. <span data-ttu-id="e8155-170">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="e8155-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="e8155-171">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="e8155-171">Click Default order settings.</span></span>
10. <span data-ttu-id="e8155-172">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-173">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="e8155-174">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-175">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="e8155-176">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-177">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="e8155-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-178">Close the page.</span></span>
14. <span data-ttu-id="e8155-179">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-179">Close the page.</span></span>
15. <span data-ttu-id="e8155-180">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e8155-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e8155-181">Kliknij pozycję ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="e8155-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="e8155-182">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e8155-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="e8155-183">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="e8155-184">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="e8155-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="e8155-185">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e8155-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="e8155-186">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="e8155-186">Click Item price.</span></span>
20. <span data-ttu-id="e8155-187">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e8155-187">Click New.</span></span>
21. <span data-ttu-id="e8155-188">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-189">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="e8155-189">For this example, select 10.</span></span> <span data-ttu-id="e8155-190">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="e8155-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="e8155-191">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-192">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="e8155-193">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e8155-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="e8155-194">Dla demonstracji wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="e8155-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="e8155-195">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e8155-195">Click Save.</span></span>
25. <span data-ttu-id="e8155-196">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="e8155-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="e8155-197">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-197">Close the page.</span></span>
27. <span data-ttu-id="e8155-198">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="e8155-199">Tworzenie trzeciego materiału</span><span class="sxs-lookup"><span data-stu-id="e8155-199">Create the third material</span></span>
1. <span data-ttu-id="e8155-200">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e8155-200">Click New.</span></span>
2. <span data-ttu-id="e8155-201">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="e8155-202">Dla demonstracji wpisz ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="e8155-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="e8155-203">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-204">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="e8155-204">Select STD.</span></span> <span data-ttu-id="e8155-205">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="e8155-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="e8155-206">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-207">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="e8155-207">For example, select Audio.</span></span> <span data-ttu-id="e8155-208">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="e8155-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="e8155-209">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-210">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="e8155-210">Select SiteWH.</span></span> <span data-ttu-id="e8155-211">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="e8155-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="e8155-212">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-213">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e8155-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="e8155-214">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="e8155-214">Select None.</span></span>  
7. <span data-ttu-id="e8155-215">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e8155-215">Click OK.</span></span>
8. <span data-ttu-id="e8155-216">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="e8155-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="e8155-217">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="e8155-217">Click Default order settings.</span></span>
10. <span data-ttu-id="e8155-218">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-219">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="e8155-220">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-221">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="e8155-222">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-223">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="e8155-224">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-224">Close the page.</span></span>
14. <span data-ttu-id="e8155-225">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-225">Close the page.</span></span>
15. <span data-ttu-id="e8155-226">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e8155-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e8155-227">Kliknij pozycję ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="e8155-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="e8155-228">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e8155-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="e8155-229">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="e8155-230">W tym przykładzie wpisz M1.</span><span class="sxs-lookup"><span data-stu-id="e8155-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="e8155-231">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e8155-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="e8155-232">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="e8155-232">Click Item price.</span></span>
20. <span data-ttu-id="e8155-233">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e8155-233">Click New.</span></span>
21. <span data-ttu-id="e8155-234">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-235">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="e8155-235">For this example, select 10.</span></span> <span data-ttu-id="e8155-236">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="e8155-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="e8155-237">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e8155-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="e8155-238">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e8155-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="e8155-239">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e8155-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="e8155-240">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="e8155-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="e8155-241">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e8155-241">Click Save.</span></span>
25. <span data-ttu-id="e8155-242">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="e8155-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="e8155-243">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-243">Close the page.</span></span>
27. <span data-ttu-id="e8155-244">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e8155-244">Close the page.</span></span>

