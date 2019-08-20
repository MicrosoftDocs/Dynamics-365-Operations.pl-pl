---
title: Tworzenie surowców (luty 2016)
description: To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e20abf8a1b211bff2bc73d1a36a1e5c917ffaab
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844592"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="ef08c-103">Tworzenie surowców (luty 2016)</span><span class="sxs-lookup"><span data-stu-id="ef08c-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ef08c-104">To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów.</span><span class="sxs-lookup"><span data-stu-id="ef08c-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="ef08c-105">Jest to trzecie zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="ef08c-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="ef08c-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ef08c-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="ef08c-107">Tworzenie pierwszego materiału</span><span class="sxs-lookup"><span data-stu-id="ef08c-107">Create the first material</span></span>
1. <span data-ttu-id="ef08c-108">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="ef08c-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="ef08c-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ef08c-109">Click New.</span></span>
3. <span data-ttu-id="ef08c-110">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ef08c-111">W tym przykładzie wpisz ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="ef08c-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="ef08c-112">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-113">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="ef08c-113">Select STD.</span></span> <span data-ttu-id="ef08c-114">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="ef08c-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="ef08c-115">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-116">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="ef08c-116">For example, select Audio.</span></span> <span data-ttu-id="ef08c-117">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="ef08c-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="ef08c-118">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-119">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ef08c-119">Select SiteWH.</span></span> <span data-ttu-id="ef08c-120">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="ef08c-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="ef08c-121">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-122">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ef08c-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ef08c-123">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="ef08c-123">Select None.</span></span>  
8. <span data-ttu-id="ef08c-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ef08c-124">Click OK.</span></span>
9. <span data-ttu-id="ef08c-125">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="ef08c-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="ef08c-126">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="ef08c-126">Click Default order settings.</span></span>
11. <span data-ttu-id="ef08c-127">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-128">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ef08c-129">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-130">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ef08c-131">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-132">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="ef08c-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-133">Close the page.</span></span>
15. <span data-ttu-id="ef08c-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-134">Close the page.</span></span>
16. <span data-ttu-id="ef08c-135">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ef08c-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ef08c-136">Kliknij pozycję ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="ef08c-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="ef08c-137">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ef08c-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="ef08c-138">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ef08c-139">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="ef08c-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="ef08c-140">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ef08c-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="ef08c-141">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="ef08c-141">Click Item price.</span></span>
21. <span data-ttu-id="ef08c-142">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ef08c-142">Click New.</span></span>
22. <span data-ttu-id="ef08c-143">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-144">W tym przykładzie wybierz wartość 10, która odpowiada typowi wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="ef08c-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="ef08c-145">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-146">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="ef08c-147">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ef08c-148">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="ef08c-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="ef08c-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ef08c-149">Click Save.</span></span>
26. <span data-ttu-id="ef08c-150">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="ef08c-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="ef08c-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-151">Close the page.</span></span>
28. <span data-ttu-id="ef08c-152">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="ef08c-153">Tworzenie drugiego materiału</span><span class="sxs-lookup"><span data-stu-id="ef08c-153">Create the second material</span></span>
1. <span data-ttu-id="ef08c-154">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ef08c-154">Click New.</span></span>
2. <span data-ttu-id="ef08c-155">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ef08c-156">W tym przykładzie wpisz ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="ef08c-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="ef08c-157">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-158">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="ef08c-158">Select STD.</span></span> <span data-ttu-id="ef08c-159">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="ef08c-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="ef08c-160">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-161">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="ef08c-161">For example, select Audio.</span></span> <span data-ttu-id="ef08c-162">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="ef08c-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="ef08c-163">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-164">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ef08c-164">Select SiteWH.</span></span> <span data-ttu-id="ef08c-165">W tym przykładzie będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="ef08c-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="ef08c-166">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-167">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ef08c-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ef08c-168">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="ef08c-168">Select None.</span></span>  
7. <span data-ttu-id="ef08c-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ef08c-169">Click OK.</span></span>
8. <span data-ttu-id="ef08c-170">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="ef08c-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="ef08c-171">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="ef08c-171">Click Default order settings.</span></span>
10. <span data-ttu-id="ef08c-172">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-173">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="ef08c-174">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-175">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ef08c-176">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-177">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ef08c-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-178">Close the page.</span></span>
14. <span data-ttu-id="ef08c-179">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-179">Close the page.</span></span>
15. <span data-ttu-id="ef08c-180">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ef08c-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ef08c-181">Kliknij pozycję ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="ef08c-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="ef08c-182">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ef08c-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="ef08c-183">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ef08c-184">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="ef08c-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="ef08c-185">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ef08c-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="ef08c-186">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="ef08c-186">Click Item price.</span></span>
20. <span data-ttu-id="ef08c-187">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ef08c-187">Click New.</span></span>
21. <span data-ttu-id="ef08c-188">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-189">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="ef08c-189">For this example, select 10.</span></span> <span data-ttu-id="ef08c-190">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="ef08c-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="ef08c-191">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-192">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="ef08c-193">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ef08c-194">Dla demonstracji wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="ef08c-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="ef08c-195">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ef08c-195">Click Save.</span></span>
25. <span data-ttu-id="ef08c-196">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="ef08c-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="ef08c-197">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-197">Close the page.</span></span>
27. <span data-ttu-id="ef08c-198">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="ef08c-199">Tworzenie trzeciego materiału</span><span class="sxs-lookup"><span data-stu-id="ef08c-199">Create the third material</span></span>
1. <span data-ttu-id="ef08c-200">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ef08c-200">Click New.</span></span>
2. <span data-ttu-id="ef08c-201">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ef08c-202">Dla demonstracji wpisz ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="ef08c-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="ef08c-203">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-204">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="ef08c-204">Select STD.</span></span> <span data-ttu-id="ef08c-205">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="ef08c-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="ef08c-206">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-207">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="ef08c-207">For example, select Audio.</span></span> <span data-ttu-id="ef08c-208">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="ef08c-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="ef08c-209">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-210">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ef08c-210">Select SiteWH.</span></span> <span data-ttu-id="ef08c-211">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="ef08c-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="ef08c-212">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-213">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ef08c-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ef08c-214">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="ef08c-214">Select None.</span></span>  
7. <span data-ttu-id="ef08c-215">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ef08c-215">Click OK.</span></span>
8. <span data-ttu-id="ef08c-216">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="ef08c-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="ef08c-217">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="ef08c-217">Click Default order settings.</span></span>
10. <span data-ttu-id="ef08c-218">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-219">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="ef08c-220">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-221">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ef08c-222">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-223">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ef08c-224">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-224">Close the page.</span></span>
14. <span data-ttu-id="ef08c-225">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-225">Close the page.</span></span>
15. <span data-ttu-id="ef08c-226">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ef08c-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ef08c-227">Kliknij pozycję ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="ef08c-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="ef08c-228">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ef08c-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="ef08c-229">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ef08c-230">W tym przykładzie wpisz M1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="ef08c-231">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ef08c-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="ef08c-232">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="ef08c-232">Click Item price.</span></span>
20. <span data-ttu-id="ef08c-233">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ef08c-233">Click New.</span></span>
21. <span data-ttu-id="ef08c-234">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-235">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="ef08c-235">For this example, select 10.</span></span> <span data-ttu-id="ef08c-236">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="ef08c-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="ef08c-237">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef08c-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ef08c-238">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="ef08c-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="ef08c-239">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ef08c-240">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="ef08c-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="ef08c-241">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ef08c-241">Click Save.</span></span>
25. <span data-ttu-id="ef08c-242">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="ef08c-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="ef08c-243">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-243">Close the page.</span></span>
27. <span data-ttu-id="ef08c-244">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ef08c-244">Close the page.</span></span>

