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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552677"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="e89c4-103">Tworzenie surowców (luty 2016)</span><span class="sxs-lookup"><span data-stu-id="e89c4-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e89c4-104">To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów.</span><span class="sxs-lookup"><span data-stu-id="e89c4-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="e89c4-105">Jest to trzecie zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="e89c4-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="e89c4-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e89c4-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="e89c4-107">Tworzenie pierwszego materiału</span><span class="sxs-lookup"><span data-stu-id="e89c4-107">Create the first material</span></span>
1. <span data-ttu-id="e89c4-108">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="e89c4-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="e89c4-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e89c4-109">Click New.</span></span>
3. <span data-ttu-id="e89c4-110">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="e89c4-111">W tym przykładzie wpisz ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="e89c4-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="e89c4-112">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-113">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="e89c4-113">Select STD.</span></span> <span data-ttu-id="e89c4-114">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="e89c4-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="e89c4-115">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-116">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="e89c4-116">For example, select Audio.</span></span> <span data-ttu-id="e89c4-117">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="e89c4-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="e89c4-118">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-119">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="e89c4-119">Select SiteWH.</span></span> <span data-ttu-id="e89c4-120">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="e89c4-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="e89c4-121">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-122">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e89c4-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="e89c4-123">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="e89c4-123">Select None.</span></span>  
8. <span data-ttu-id="e89c4-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e89c4-124">Click OK.</span></span>
9. <span data-ttu-id="e89c4-125">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="e89c4-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="e89c4-126">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="e89c4-126">Click Default order settings.</span></span>
11. <span data-ttu-id="e89c4-127">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-128">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="e89c4-129">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-130">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="e89c4-131">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-132">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="e89c4-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-133">Close the page.</span></span>
15. <span data-ttu-id="e89c4-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-134">Close the page.</span></span>
16. <span data-ttu-id="e89c4-135">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e89c4-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e89c4-136">Kliknij pozycję ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="e89c4-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="e89c4-137">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e89c4-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="e89c4-138">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="e89c4-139">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="e89c4-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="e89c4-140">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e89c4-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="e89c4-141">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="e89c4-141">Click Item price.</span></span>
21. <span data-ttu-id="e89c4-142">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e89c4-142">Click New.</span></span>
22. <span data-ttu-id="e89c4-143">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-144">W tym przykładzie wybierz wartość 10, która odpowiada typowi wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="e89c4-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="e89c4-145">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-146">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="e89c4-147">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="e89c4-148">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="e89c4-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="e89c4-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e89c4-149">Click Save.</span></span>
26. <span data-ttu-id="e89c4-150">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="e89c4-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="e89c4-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-151">Close the page.</span></span>
28. <span data-ttu-id="e89c4-152">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="e89c4-153">Tworzenie drugiego materiału</span><span class="sxs-lookup"><span data-stu-id="e89c4-153">Create the second material</span></span>
1. <span data-ttu-id="e89c4-154">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e89c4-154">Click New.</span></span>
2. <span data-ttu-id="e89c4-155">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="e89c4-156">W tym przykładzie wpisz ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="e89c4-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="e89c4-157">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-158">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="e89c4-158">Select STD.</span></span> <span data-ttu-id="e89c4-159">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="e89c4-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="e89c4-160">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-161">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="e89c4-161">For example, select Audio.</span></span> <span data-ttu-id="e89c4-162">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="e89c4-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="e89c4-163">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-164">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="e89c4-164">Select SiteWH.</span></span> <span data-ttu-id="e89c4-165">W tym przykładzie będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="e89c4-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="e89c4-166">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-167">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e89c4-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="e89c4-168">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="e89c4-168">Select None.</span></span>  
7. <span data-ttu-id="e89c4-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e89c4-169">Click OK.</span></span>
8. <span data-ttu-id="e89c4-170">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="e89c4-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="e89c4-171">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="e89c4-171">Click Default order settings.</span></span>
10. <span data-ttu-id="e89c4-172">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-173">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="e89c4-174">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-175">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="e89c4-176">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-177">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="e89c4-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-178">Close the page.</span></span>
14. <span data-ttu-id="e89c4-179">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-179">Close the page.</span></span>
15. <span data-ttu-id="e89c4-180">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e89c4-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e89c4-181">Kliknij pozycję ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="e89c4-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="e89c4-182">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e89c4-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="e89c4-183">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="e89c4-184">W tym przykładzie wpisz M2.</span><span class="sxs-lookup"><span data-stu-id="e89c4-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="e89c4-185">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e89c4-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="e89c4-186">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="e89c4-186">Click Item price.</span></span>
20. <span data-ttu-id="e89c4-187">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e89c4-187">Click New.</span></span>
21. <span data-ttu-id="e89c4-188">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-189">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="e89c4-189">For this example, select 10.</span></span> <span data-ttu-id="e89c4-190">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="e89c4-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="e89c4-191">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-192">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="e89c4-193">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="e89c4-194">Dla demonstracji wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="e89c4-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="e89c4-195">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e89c4-195">Click Save.</span></span>
25. <span data-ttu-id="e89c4-196">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="e89c4-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="e89c4-197">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-197">Close the page.</span></span>
27. <span data-ttu-id="e89c4-198">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="e89c4-199">Tworzenie trzeciego materiału</span><span class="sxs-lookup"><span data-stu-id="e89c4-199">Create the third material</span></span>
1. <span data-ttu-id="e89c4-200">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e89c4-200">Click New.</span></span>
2. <span data-ttu-id="e89c4-201">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="e89c4-202">Dla demonstracji wpisz ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="e89c4-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="e89c4-203">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-204">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="e89c4-204">Select STD.</span></span> <span data-ttu-id="e89c4-205">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="e89c4-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="e89c4-206">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-207">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="e89c4-207">For example, select Audio.</span></span> <span data-ttu-id="e89c4-208">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="e89c4-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="e89c4-209">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-210">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="e89c4-210">Select SiteWH.</span></span> <span data-ttu-id="e89c4-211">W demonstracji będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="e89c4-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="e89c4-212">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-213">Wymiary śledzenia nie będą używane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e89c4-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="e89c4-214">Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="e89c4-214">Select None.</span></span>  
7. <span data-ttu-id="e89c4-215">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e89c4-215">Click OK.</span></span>
8. <span data-ttu-id="e89c4-216">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="e89c4-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="e89c4-217">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="e89c4-217">Click Default order settings.</span></span>
10. <span data-ttu-id="e89c4-218">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-219">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="e89c4-220">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-221">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="e89c4-222">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-223">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="e89c4-224">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-224">Close the page.</span></span>
14. <span data-ttu-id="e89c4-225">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-225">Close the page.</span></span>
15. <span data-ttu-id="e89c4-226">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e89c4-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e89c4-227">Kliknij pozycję ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="e89c4-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="e89c4-228">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e89c4-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="e89c4-229">W polu Grupa kosztów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="e89c4-230">W tym przykładzie wpisz M1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="e89c4-231">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="e89c4-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="e89c4-232">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="e89c4-232">Click Item price.</span></span>
20. <span data-ttu-id="e89c4-233">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e89c4-233">Click New.</span></span>
21. <span data-ttu-id="e89c4-234">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-235">W tym przykładzie wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="e89c4-235">For this example, select 10.</span></span> <span data-ttu-id="e89c4-236">Jest to typ wyceny Koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="e89c4-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="e89c4-237">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e89c4-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="e89c4-238">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="e89c4-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="e89c4-239">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="e89c4-240">W tym przykładzie wpisz wartość 10.</span><span class="sxs-lookup"><span data-stu-id="e89c4-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="e89c4-241">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e89c4-241">Click Save.</span></span>
25. <span data-ttu-id="e89c4-242">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="e89c4-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="e89c4-243">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-243">Close the page.</span></span>
27. <span data-ttu-id="e89c4-244">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e89c4-244">Close the page.</span></span>

