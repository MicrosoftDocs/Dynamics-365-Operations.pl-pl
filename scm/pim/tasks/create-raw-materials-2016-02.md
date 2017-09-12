--- 
title: "Tworzenie surowców (tylko luty 2016)"
description: "To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów."
author: BibiSp
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f1c10e0f8275d928c1455cd99105aece8780e7f0
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="c824b-103">Tworzenie surowców (tylko luty 2016)</span><span class="sxs-lookup"><span data-stu-id="c824b-103">Create raw materials (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c824b-104">To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów.</span><span class="sxs-lookup"><span data-stu-id="c824b-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="c824b-105">Jest to trzecie zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="c824b-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="c824b-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c824b-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="c824b-107">Tworzenie pierwszego materiału</span><span class="sxs-lookup"><span data-stu-id="c824b-107">Create the first material</span></span>
1. <span data-ttu-id="c824b-108">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="c824b-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="c824b-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c824b-109">Click New.</span></span>
3. <span data-ttu-id="c824b-110">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c824b-111">W tym przykładzie wpisz ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="c824b-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="c824b-112">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-113">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="c824b-113">Select STD.</span></span> <span data-ttu-id="c824b-114">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="c824b-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="c824b-115">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-116">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="c824b-116">For example, select Audio.</span></span> <span data-ttu-id="c824b-117">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="c824b-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="c824b-118">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-119">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="c824b-119">Select SiteWH.</span></span> <span data-ttu-id="c824b-120">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="c824b-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="c824b-121">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-122">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c824b-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c824b-123">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="c824b-123">Select None.</span></span>  
8. <span data-ttu-id="c824b-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c824b-124">Click OK.</span></span>
9. <span data-ttu-id="c824b-125">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="c824b-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="c824b-126">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="c824b-126">Click Default order settings.</span></span>
11. <span data-ttu-id="c824b-127">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-128">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c824b-129">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-130">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c824b-131">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-132">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="c824b-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-133">Close the page.</span></span>
15. <span data-ttu-id="c824b-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-134">Close the page.</span></span>
16. <span data-ttu-id="c824b-135">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c824b-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c824b-136">Kliknij pozycję ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="c824b-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="c824b-137">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="c824b-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="c824b-138">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c824b-139">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="c824b-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="c824b-140">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="c824b-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="c824b-141">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="c824b-141">Click Item price.</span></span>
21. <span data-ttu-id="c824b-142">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c824b-142">Click New.</span></span>
22. <span data-ttu-id="c824b-143">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-144">W tym przykładzie wybierz wartość 10, która odpowiada typowi wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="c824b-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="c824b-145">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-146">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="c824b-147">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c824b-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c824b-148">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="c824b-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="c824b-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c824b-149">Click Save.</span></span>
26. <span data-ttu-id="c824b-150">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="c824b-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="c824b-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-151">Close the page.</span></span>
28. <span data-ttu-id="c824b-152">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="c824b-153">Tworzenie drugiego materiału</span><span class="sxs-lookup"><span data-stu-id="c824b-153">Create the second material</span></span>
1. <span data-ttu-id="c824b-154">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c824b-154">Click New.</span></span>
2. <span data-ttu-id="c824b-155">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c824b-156">W tym przykładzie wpisz ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="c824b-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="c824b-157">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-158">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="c824b-158">Select STD.</span></span> <span data-ttu-id="c824b-159">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="c824b-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="c824b-160">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-161">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="c824b-161">For example, select Audio.</span></span> <span data-ttu-id="c824b-162">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="c824b-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="c824b-163">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-164">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="c824b-164">Select SiteWH.</span></span> <span data-ttu-id="c824b-165">W tym przykładzie będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="c824b-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="c824b-166">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-167">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c824b-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c824b-168">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="c824b-168">Select None.</span></span>  
7. <span data-ttu-id="c824b-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c824b-169">Click OK.</span></span>
8. <span data-ttu-id="c824b-170">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="c824b-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="c824b-171">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="c824b-171">Click Default order settings.</span></span>
10. <span data-ttu-id="c824b-172">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-173">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="c824b-174">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-175">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c824b-176">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-177">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c824b-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-178">Close the page.</span></span>
14. <span data-ttu-id="c824b-179">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-179">Close the page.</span></span>
15. <span data-ttu-id="c824b-180">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c824b-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c824b-181">Kliknij pozycję ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="c824b-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="c824b-182">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="c824b-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="c824b-183">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c824b-184">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="c824b-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="c824b-185">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="c824b-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="c824b-186">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="c824b-186">Click Item price.</span></span>
20. <span data-ttu-id="c824b-187">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c824b-187">Click New.</span></span>
21. <span data-ttu-id="c824b-188">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-189">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="c824b-189">For this example, select 10.</span></span> <span data-ttu-id="c824b-190">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="c824b-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="c824b-191">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-192">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="c824b-193">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c824b-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c824b-194">Dla demonstracji wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="c824b-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="c824b-195">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c824b-195">Click Save.</span></span>
25. <span data-ttu-id="c824b-196">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="c824b-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="c824b-197">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-197">Close the page.</span></span>
27. <span data-ttu-id="c824b-198">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="c824b-199">Tworzenie trzeciego materiału</span><span class="sxs-lookup"><span data-stu-id="c824b-199">Create the third material</span></span>
1. <span data-ttu-id="c824b-200">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c824b-200">Click New.</span></span>
2. <span data-ttu-id="c824b-201">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c824b-202">Dla demonstracji wpisz ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="c824b-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="c824b-203">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-204">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="c824b-204">Select STD.</span></span> <span data-ttu-id="c824b-205">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="c824b-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="c824b-206">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-207">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="c824b-207">For example, select Audio.</span></span> <span data-ttu-id="c824b-208">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="c824b-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="c824b-209">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-210">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="c824b-210">Select SiteWH.</span></span> <span data-ttu-id="c824b-211">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="c824b-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="c824b-212">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-213">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c824b-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c824b-214">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="c824b-214">Select None.</span></span>  
7. <span data-ttu-id="c824b-215">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c824b-215">Click OK.</span></span>
8. <span data-ttu-id="c824b-216">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="c824b-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="c824b-217">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="c824b-217">Click Default order settings.</span></span>
10. <span data-ttu-id="c824b-218">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-219">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="c824b-220">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-221">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c824b-222">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-223">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c824b-224">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-224">Close the page.</span></span>
14. <span data-ttu-id="c824b-225">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-225">Close the page.</span></span>
15. <span data-ttu-id="c824b-226">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c824b-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c824b-227">Kliknij pozycję ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="c824b-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="c824b-228">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="c824b-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="c824b-229">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c824b-230">W tym przykładzie wpisz M1.</span><span class="sxs-lookup"><span data-stu-id="c824b-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="c824b-231">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="c824b-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="c824b-232">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="c824b-232">Click Item price.</span></span>
20. <span data-ttu-id="c824b-233">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c824b-233">Click New.</span></span>
21. <span data-ttu-id="c824b-234">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-235">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="c824b-235">For this example, select 10.</span></span> <span data-ttu-id="c824b-236">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="c824b-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="c824b-237">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c824b-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c824b-238">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="c824b-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="c824b-239">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c824b-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c824b-240">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="c824b-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="c824b-241">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c824b-241">Click Save.</span></span>
25. <span data-ttu-id="c824b-242">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="c824b-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="c824b-243">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-243">Close the page.</span></span>
27. <span data-ttu-id="c824b-244">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c824b-244">Close the page.</span></span>


