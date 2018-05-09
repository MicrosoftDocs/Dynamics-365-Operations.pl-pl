--- 
title: "Tworzenie surowców (tylko luty 2016)"
description: "To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3a33e3f7c2bdc54bab255960cebdeb3edec6d20d
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="ecc8d-103">Tworzenie surowców (tylko luty 2016)</span><span class="sxs-lookup"><span data-stu-id="ecc8d-103">Create raw materials (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ecc8d-104">To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="ecc8d-105">Jest to trzecie zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="ecc8d-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="ecc8d-107">Tworzenie pierwszego materiału</span><span class="sxs-lookup"><span data-stu-id="ecc8d-107">Create the first material</span></span>
1. <span data-ttu-id="ecc8d-108">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="ecc8d-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-109">Click New.</span></span>
3. <span data-ttu-id="ecc8d-110">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ecc8d-111">W tym przykładzie wpisz ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="ecc8d-112">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-113">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-113">Select STD.</span></span> <span data-ttu-id="ecc8d-114">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="ecc8d-115">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-116">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-116">For example, select Audio.</span></span> <span data-ttu-id="ecc8d-117">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="ecc8d-118">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-119">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-119">Select SiteWH.</span></span> <span data-ttu-id="ecc8d-120">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="ecc8d-121">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-122">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ecc8d-123">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-123">Select None.</span></span>  
8. <span data-ttu-id="ecc8d-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-124">Click OK.</span></span>
9. <span data-ttu-id="ecc8d-125">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="ecc8d-126">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-126">Click Default order settings.</span></span>
11. <span data-ttu-id="ecc8d-127">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-128">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ecc8d-129">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-130">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ecc8d-131">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-132">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="ecc8d-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-133">Close the page.</span></span>
15. <span data-ttu-id="ecc8d-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-134">Close the page.</span></span>
16. <span data-ttu-id="ecc8d-135">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ecc8d-136">Kliknij pozycję ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="ecc8d-137">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="ecc8d-138">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ecc8d-139">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="ecc8d-140">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="ecc8d-141">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-141">Click Item price.</span></span>
21. <span data-ttu-id="ecc8d-142">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-142">Click New.</span></span>
22. <span data-ttu-id="ecc8d-143">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-144">W tym przykładzie wybierz wartość 10, która odpowiada typowi wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="ecc8d-145">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-146">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="ecc8d-147">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ecc8d-148">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="ecc8d-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-149">Click Save.</span></span>
26. <span data-ttu-id="ecc8d-150">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="ecc8d-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-151">Close the page.</span></span>
28. <span data-ttu-id="ecc8d-152">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="ecc8d-153">Tworzenie drugiego materiału</span><span class="sxs-lookup"><span data-stu-id="ecc8d-153">Create the second material</span></span>
1. <span data-ttu-id="ecc8d-154">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-154">Click New.</span></span>
2. <span data-ttu-id="ecc8d-155">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ecc8d-156">W tym przykładzie wpisz ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="ecc8d-157">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-158">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-158">Select STD.</span></span> <span data-ttu-id="ecc8d-159">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="ecc8d-160">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-161">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-161">For example, select Audio.</span></span> <span data-ttu-id="ecc8d-162">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="ecc8d-163">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-164">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-164">Select SiteWH.</span></span> <span data-ttu-id="ecc8d-165">W tym przykładzie będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="ecc8d-166">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-167">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ecc8d-168">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-168">Select None.</span></span>  
7. <span data-ttu-id="ecc8d-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-169">Click OK.</span></span>
8. <span data-ttu-id="ecc8d-170">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="ecc8d-171">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-171">Click Default order settings.</span></span>
10. <span data-ttu-id="ecc8d-172">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-173">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="ecc8d-174">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-175">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ecc8d-176">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-177">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ecc8d-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-178">Close the page.</span></span>
14. <span data-ttu-id="ecc8d-179">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-179">Close the page.</span></span>
15. <span data-ttu-id="ecc8d-180">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ecc8d-181">Kliknij pozycję ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="ecc8d-182">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="ecc8d-183">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ecc8d-184">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="ecc8d-185">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="ecc8d-186">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-186">Click Item price.</span></span>
20. <span data-ttu-id="ecc8d-187">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-187">Click New.</span></span>
21. <span data-ttu-id="ecc8d-188">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-189">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-189">For this example, select 10.</span></span> <span data-ttu-id="ecc8d-190">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="ecc8d-191">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-192">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="ecc8d-193">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ecc8d-194">Dla demonstracji wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="ecc8d-195">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-195">Click Save.</span></span>
25. <span data-ttu-id="ecc8d-196">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="ecc8d-197">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-197">Close the page.</span></span>
27. <span data-ttu-id="ecc8d-198">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="ecc8d-199">Tworzenie trzeciego materiału</span><span class="sxs-lookup"><span data-stu-id="ecc8d-199">Create the third material</span></span>
1. <span data-ttu-id="ecc8d-200">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-200">Click New.</span></span>
2. <span data-ttu-id="ecc8d-201">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ecc8d-202">Dla demonstracji wpisz ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="ecc8d-203">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-204">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-204">Select STD.</span></span> <span data-ttu-id="ecc8d-205">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="ecc8d-206">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-207">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-207">For example, select Audio.</span></span> <span data-ttu-id="ecc8d-208">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="ecc8d-209">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-210">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-210">Select SiteWH.</span></span> <span data-ttu-id="ecc8d-211">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="ecc8d-212">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-213">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ecc8d-214">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-214">Select None.</span></span>  
7. <span data-ttu-id="ecc8d-215">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-215">Click OK.</span></span>
8. <span data-ttu-id="ecc8d-216">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="ecc8d-217">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-217">Click Default order settings.</span></span>
10. <span data-ttu-id="ecc8d-218">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-219">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="ecc8d-220">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-221">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ecc8d-222">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-223">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ecc8d-224">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-224">Close the page.</span></span>
14. <span data-ttu-id="ecc8d-225">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-225">Close the page.</span></span>
15. <span data-ttu-id="ecc8d-226">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ecc8d-227">Kliknij pozycję ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="ecc8d-228">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="ecc8d-229">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ecc8d-230">W tym przykładzie wpisz M1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="ecc8d-231">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="ecc8d-232">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-232">Click Item price.</span></span>
20. <span data-ttu-id="ecc8d-233">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-233">Click New.</span></span>
21. <span data-ttu-id="ecc8d-234">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-235">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-235">For this example, select 10.</span></span> <span data-ttu-id="ecc8d-236">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="ecc8d-237">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecc8d-238">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="ecc8d-239">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ecc8d-240">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="ecc8d-241">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-241">Click Save.</span></span>
25. <span data-ttu-id="ecc8d-242">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="ecc8d-243">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-243">Close the page.</span></span>
27. <span data-ttu-id="ecc8d-244">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ecc8d-244">Close the page.</span></span>


