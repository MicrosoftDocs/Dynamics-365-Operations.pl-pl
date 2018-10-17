--- 
title: Tworzenie marszrut (luty 2016)
description: "To zadanie koncentruje się na utworzeniu marszrut produkcji wyrobu gotowego i półproduktu."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, RouteInventProd, RouteGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 965826f5fddc2f53f33157434929eb265979376e
ms.openlocfilehash: a68b28c0e0ee14429a23d3241cabdae948d706d2
ms.contentlocale: pl-pl
ms.lasthandoff: 09/17/2018

---
# <a name="create-routes-february-2016"></a><span data-ttu-id="4ee77-103">Tworzenie marszrut (luty 2016)</span><span class="sxs-lookup"><span data-stu-id="4ee77-103">Create routes (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4ee77-104">To zadanie koncentruje się na utworzeniu marszrut produkcji wyrobu gotowego i półproduktu.</span><span class="sxs-lookup"><span data-stu-id="4ee77-104">This task focuses on creating the production routes for a finished product and a semi-finished product.</span></span> <span data-ttu-id="4ee77-105">Jest to piąte zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="4ee77-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="4ee77-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="4ee77-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="4ee77-107">Tworzenie marszruty dla półproduktu</span><span class="sxs-lookup"><span data-stu-id="4ee77-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="4ee77-108">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="4ee77-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="4ee77-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4ee77-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4ee77-110">Zaznacz towar o numerze BOM_2.</span><span class="sxs-lookup"><span data-stu-id="4ee77-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="4ee77-111">W okienku akcji kliknij pozycję Konstruuj.</span><span class="sxs-lookup"><span data-stu-id="4ee77-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="4ee77-112">Kliknij opcję Marszruta.</span><span class="sxs-lookup"><span data-stu-id="4ee77-112">Click Route.</span></span>
5. <span data-ttu-id="4ee77-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4ee77-113">Click New.</span></span>
6. <span data-ttu-id="4ee77-114">Kliknij opcję Marszruta i wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="4ee77-114">Click Route and route version.</span></span>
7. <span data-ttu-id="4ee77-115">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="4ee77-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="4ee77-116">Na przykład wpisz MARSZRUTA_2.</span><span class="sxs-lookup"><span data-stu-id="4ee77-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="4ee77-117">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ee77-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="4ee77-118">W tym przykładzie wprowadź lub wybierz oddział 1.</span><span class="sxs-lookup"><span data-stu-id="4ee77-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="4ee77-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4ee77-119">Click OK.</span></span>
10. <span data-ttu-id="4ee77-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4ee77-120">Click New.</span></span>
11. <span data-ttu-id="4ee77-121">W polu Operacja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ee77-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="4ee77-122">W tym przykładzie wybierz opcję Montaż.</span><span class="sxs-lookup"><span data-stu-id="4ee77-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="4ee77-123">W polu Czas procesu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="4ee77-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="4ee77-124">Na przykład wpisz 1.</span><span class="sxs-lookup"><span data-stu-id="4ee77-124">For example, type 1.</span></span> <span data-ttu-id="4ee77-125">Czasy procesów są często uwzględniane w cenach obliczanych dla towarów.</span><span class="sxs-lookup"><span data-stu-id="4ee77-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="4ee77-126">W polu Grupa marszruty wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="4ee77-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="4ee77-127">W tym przykładzie wybierz opcję Standardowy.</span><span class="sxs-lookup"><span data-stu-id="4ee77-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="4ee77-128">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="4ee77-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="4ee77-129">W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ee77-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="4ee77-130">W tym przykładzie wybierz opcję Montaż.</span><span class="sxs-lookup"><span data-stu-id="4ee77-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="4ee77-131">Kliknij kartę Czasy.</span><span class="sxs-lookup"><span data-stu-id="4ee77-131">Click the Times tab.</span></span>
17. <span data-ttu-id="4ee77-132">W polu Czas przezbrajania wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="4ee77-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="4ee77-133">W tym przykładzie wpisz wartość 1.</span><span class="sxs-lookup"><span data-stu-id="4ee77-133">For this example, type 1.</span></span> <span data-ttu-id="4ee77-134">Czasy przezbrajania są często uwzględniane w cenach obliczanych dla towarów.</span><span class="sxs-lookup"><span data-stu-id="4ee77-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="4ee77-135">W okienku akcji kliknij pozycję Wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="4ee77-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="4ee77-136">Kliknij przycisk Zatwierdź.</span><span class="sxs-lookup"><span data-stu-id="4ee77-136">Click Approve.</span></span>
20. <span data-ttu-id="4ee77-137">W polu Czy chcesz także zatwierdzić marszrutę? kliknij opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="4ee77-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="4ee77-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4ee77-138">Click OK.</span></span>
22. <span data-ttu-id="4ee77-139">W okienku akcji kliknij pozycję Wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="4ee77-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="4ee77-140">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="4ee77-140">Click Activate.</span></span>
24. <span data-ttu-id="4ee77-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4ee77-141">Close the page.</span></span>
25. <span data-ttu-id="4ee77-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4ee77-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="4ee77-143">Tworzenie marszruty dla wyrobu gotowego</span><span class="sxs-lookup"><span data-stu-id="4ee77-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="4ee77-144">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4ee77-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4ee77-145">Zaznacz towar o numerze BOM_1.</span><span class="sxs-lookup"><span data-stu-id="4ee77-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="4ee77-146">W okienku akcji kliknij pozycję Konstruuj.</span><span class="sxs-lookup"><span data-stu-id="4ee77-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="4ee77-147">Kliknij opcję Marszruta.</span><span class="sxs-lookup"><span data-stu-id="4ee77-147">Click Route.</span></span>
4. <span data-ttu-id="4ee77-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4ee77-148">Click New.</span></span>
5. <span data-ttu-id="4ee77-149">Kliknij opcję Marszruta i wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="4ee77-149">Click Route and route version.</span></span>
6. <span data-ttu-id="4ee77-150">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="4ee77-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="4ee77-151">W tym przykładzie wpisz MARSZRUTA_1.</span><span class="sxs-lookup"><span data-stu-id="4ee77-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="4ee77-152">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ee77-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="4ee77-153">W tym przykładzie wprowadź lub wybierz oddział 1.</span><span class="sxs-lookup"><span data-stu-id="4ee77-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="4ee77-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4ee77-154">Click OK.</span></span>
9. <span data-ttu-id="4ee77-155">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4ee77-155">Click New.</span></span>
10. <span data-ttu-id="4ee77-156">W polu Operacja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ee77-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="4ee77-157">W tym przykładzie wybierz opcję Pakowanie.</span><span class="sxs-lookup"><span data-stu-id="4ee77-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="4ee77-158">W polu Czas procesu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="4ee77-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="4ee77-159">W tym przykładzie wpisz wartość 1.</span><span class="sxs-lookup"><span data-stu-id="4ee77-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="4ee77-160">W polu Grupa marszruty wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="4ee77-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="4ee77-161">W tym przykładzie wybierz opcję Standardowy.</span><span class="sxs-lookup"><span data-stu-id="4ee77-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="4ee77-162">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="4ee77-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="4ee77-163">W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ee77-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="4ee77-164">W tym przykładzie wybierz opcję Pakowanie.</span><span class="sxs-lookup"><span data-stu-id="4ee77-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="4ee77-165">Kliknij kartę Czasy.</span><span class="sxs-lookup"><span data-stu-id="4ee77-165">Click the Times tab.</span></span>
16. <span data-ttu-id="4ee77-166">W polu Czas przezbrajania wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="4ee77-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="4ee77-167">W tym przykładzie wpisz wartość 1.</span><span class="sxs-lookup"><span data-stu-id="4ee77-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="4ee77-168">W okienku akcji kliknij pozycję Wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="4ee77-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="4ee77-169">Kliknij przycisk Zatwierdź.</span><span class="sxs-lookup"><span data-stu-id="4ee77-169">Click Approve.</span></span>
19. <span data-ttu-id="4ee77-170">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4ee77-170">Click OK.</span></span>
20. <span data-ttu-id="4ee77-171">W okienku akcji kliknij pozycję Wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="4ee77-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="4ee77-172">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="4ee77-172">Click Activate.</span></span>
22. <span data-ttu-id="4ee77-173">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4ee77-173">Close the page.</span></span>
23. <span data-ttu-id="4ee77-174">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4ee77-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="4ee77-175">Włączanie automatycznego zużywania czasu przezbrajania</span><span class="sxs-lookup"><span data-stu-id="4ee77-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="4ee77-176">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Marszruty > Grupy marszrut.</span><span class="sxs-lookup"><span data-stu-id="4ee77-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="4ee77-177">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4ee77-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4ee77-178">Na liście zaznacz pozycję Standardowy.</span><span class="sxs-lookup"><span data-stu-id="4ee77-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="4ee77-179">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="4ee77-179">Click Edit.</span></span>
4. <span data-ttu-id="4ee77-180">W polu Czas przezbrajania zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="4ee77-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="4ee77-181">Czasy przezbrajania są często uwzględniane w cenach obliczanych dla towarów.</span><span class="sxs-lookup"><span data-stu-id="4ee77-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="4ee77-182">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="4ee77-182">Click Save.</span></span>
6. <span data-ttu-id="4ee77-183">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4ee77-183">Close the page.</span></span>


