---
title: Tworzenie marszrut (tylko luty 2016)
description: To zadanie koncentruje się na utworzeniu marszrut produkcji wyrobu gotowego i półproduktu.
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
ms.openlocfilehash: 63ad2cc0c41a5931750dffbfc64bc7ce965a1da4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "316471"
---
# <a name="create-routes-february-2016-only"></a><span data-ttu-id="8ec38-103">Tworzenie marszrut (tylko luty 2016)</span><span class="sxs-lookup"><span data-stu-id="8ec38-103">Create routes (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8ec38-104">To zadanie koncentruje się na utworzeniu marszrut produkcji wyrobu gotowego i półproduktu.</span><span class="sxs-lookup"><span data-stu-id="8ec38-104">This task focuses on creating the production routes for a finished product and a semi-finished product.</span></span> <span data-ttu-id="8ec38-105">Jest to piąte zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="8ec38-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="8ec38-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="8ec38-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="8ec38-107">Tworzenie marszruty dla półproduktu</span><span class="sxs-lookup"><span data-stu-id="8ec38-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="8ec38-108">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="8ec38-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="8ec38-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8ec38-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8ec38-110">Zaznacz towar o numerze BOM_2.</span><span class="sxs-lookup"><span data-stu-id="8ec38-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="8ec38-111">W okienku akcji kliknij pozycję Konstruuj.</span><span class="sxs-lookup"><span data-stu-id="8ec38-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="8ec38-112">Kliknij opcję Marszruta.</span><span class="sxs-lookup"><span data-stu-id="8ec38-112">Click Route.</span></span>
5. <span data-ttu-id="8ec38-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8ec38-113">Click New.</span></span>
6. <span data-ttu-id="8ec38-114">Kliknij opcję Marszruta i wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="8ec38-114">Click Route and route version.</span></span>
7. <span data-ttu-id="8ec38-115">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="8ec38-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="8ec38-116">Na przykład wpisz MARSZRUTA_2.</span><span class="sxs-lookup"><span data-stu-id="8ec38-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="8ec38-117">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8ec38-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="8ec38-118">W tym przykładzie wprowadź lub wybierz oddział 1.</span><span class="sxs-lookup"><span data-stu-id="8ec38-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="8ec38-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8ec38-119">Click OK.</span></span>
10. <span data-ttu-id="8ec38-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8ec38-120">Click New.</span></span>
11. <span data-ttu-id="8ec38-121">W polu Operacja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8ec38-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="8ec38-122">W tym przykładzie wybierz opcję Montaż.</span><span class="sxs-lookup"><span data-stu-id="8ec38-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="8ec38-123">W polu Czas procesu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="8ec38-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="8ec38-124">Na przykład wpisz 1.</span><span class="sxs-lookup"><span data-stu-id="8ec38-124">For example, type 1.</span></span> <span data-ttu-id="8ec38-125">Czasy procesów są często uwzględniane w cenach obliczanych dla towarów.</span><span class="sxs-lookup"><span data-stu-id="8ec38-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="8ec38-126">W polu Grupa marszruty wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="8ec38-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="8ec38-127">W tym przykładzie wybierz opcję Standardowy.</span><span class="sxs-lookup"><span data-stu-id="8ec38-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="8ec38-128">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="8ec38-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="8ec38-129">W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8ec38-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="8ec38-130">W tym przykładzie wybierz opcję Montaż.</span><span class="sxs-lookup"><span data-stu-id="8ec38-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="8ec38-131">Kliknij kartę Czasy.</span><span class="sxs-lookup"><span data-stu-id="8ec38-131">Click the Times tab.</span></span>
17. <span data-ttu-id="8ec38-132">W polu Czas przezbrajania wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="8ec38-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="8ec38-133">W tym przykładzie wpisz wartość 1.</span><span class="sxs-lookup"><span data-stu-id="8ec38-133">For this example, type 1.</span></span> <span data-ttu-id="8ec38-134">Czasy przezbrajania są często uwzględniane w cenach obliczanych dla towarów.</span><span class="sxs-lookup"><span data-stu-id="8ec38-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="8ec38-135">W okienku akcji kliknij pozycję Wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="8ec38-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="8ec38-136">Kliknij przycisk Zatwierdź.</span><span class="sxs-lookup"><span data-stu-id="8ec38-136">Click Approve.</span></span>
20. <span data-ttu-id="8ec38-137">W polu Czy chcesz także zatwierdzić marszrutę? kliknij opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="8ec38-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="8ec38-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8ec38-138">Click OK.</span></span>
22. <span data-ttu-id="8ec38-139">W okienku akcji kliknij pozycję Wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="8ec38-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="8ec38-140">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="8ec38-140">Click Activate.</span></span>
24. <span data-ttu-id="8ec38-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8ec38-141">Close the page.</span></span>
25. <span data-ttu-id="8ec38-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8ec38-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="8ec38-143">Tworzenie marszruty dla wyrobu gotowego</span><span class="sxs-lookup"><span data-stu-id="8ec38-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="8ec38-144">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8ec38-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8ec38-145">Zaznacz towar o numerze BOM_1.</span><span class="sxs-lookup"><span data-stu-id="8ec38-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="8ec38-146">W okienku akcji kliknij pozycję Konstruuj.</span><span class="sxs-lookup"><span data-stu-id="8ec38-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="8ec38-147">Kliknij opcję Marszruta.</span><span class="sxs-lookup"><span data-stu-id="8ec38-147">Click Route.</span></span>
4. <span data-ttu-id="8ec38-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8ec38-148">Click New.</span></span>
5. <span data-ttu-id="8ec38-149">Kliknij opcję Marszruta i wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="8ec38-149">Click Route and route version.</span></span>
6. <span data-ttu-id="8ec38-150">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="8ec38-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="8ec38-151">W tym przykładzie wpisz MARSZRUTA_1.</span><span class="sxs-lookup"><span data-stu-id="8ec38-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="8ec38-152">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8ec38-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="8ec38-153">W tym przykładzie wprowadź lub wybierz oddział 1.</span><span class="sxs-lookup"><span data-stu-id="8ec38-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="8ec38-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8ec38-154">Click OK.</span></span>
9. <span data-ttu-id="8ec38-155">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8ec38-155">Click New.</span></span>
10. <span data-ttu-id="8ec38-156">W polu Operacja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8ec38-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="8ec38-157">W tym przykładzie wybierz opcję Pakowanie.</span><span class="sxs-lookup"><span data-stu-id="8ec38-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="8ec38-158">W polu Czas procesu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="8ec38-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="8ec38-159">W tym przykładzie wpisz wartość 1.</span><span class="sxs-lookup"><span data-stu-id="8ec38-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="8ec38-160">W polu Grupa marszruty wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="8ec38-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="8ec38-161">W tym przykładzie wybierz opcję Standardowy.</span><span class="sxs-lookup"><span data-stu-id="8ec38-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="8ec38-162">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="8ec38-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="8ec38-163">W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8ec38-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="8ec38-164">W tym przykładzie wybierz opcję Pakowanie.</span><span class="sxs-lookup"><span data-stu-id="8ec38-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="8ec38-165">Kliknij kartę Czasy.</span><span class="sxs-lookup"><span data-stu-id="8ec38-165">Click the Times tab.</span></span>
16. <span data-ttu-id="8ec38-166">W polu Czas przezbrajania wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="8ec38-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="8ec38-167">W tym przykładzie wpisz wartość 1.</span><span class="sxs-lookup"><span data-stu-id="8ec38-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="8ec38-168">W okienku akcji kliknij pozycję Wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="8ec38-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="8ec38-169">Kliknij przycisk Zatwierdź.</span><span class="sxs-lookup"><span data-stu-id="8ec38-169">Click Approve.</span></span>
19. <span data-ttu-id="8ec38-170">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8ec38-170">Click OK.</span></span>
20. <span data-ttu-id="8ec38-171">W okienku akcji kliknij pozycję Wersja marszruty.</span><span class="sxs-lookup"><span data-stu-id="8ec38-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="8ec38-172">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="8ec38-172">Click Activate.</span></span>
22. <span data-ttu-id="8ec38-173">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8ec38-173">Close the page.</span></span>
23. <span data-ttu-id="8ec38-174">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8ec38-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="8ec38-175">Włączanie automatycznego zużywania czasu przezbrajania</span><span class="sxs-lookup"><span data-stu-id="8ec38-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="8ec38-176">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Marszruty > Grupy marszrut.</span><span class="sxs-lookup"><span data-stu-id="8ec38-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="8ec38-177">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="8ec38-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8ec38-178">Na liście zaznacz pozycję Standardowy.</span><span class="sxs-lookup"><span data-stu-id="8ec38-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="8ec38-179">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="8ec38-179">Click Edit.</span></span>
4. <span data-ttu-id="8ec38-180">W polu Czas przezbrajania zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="8ec38-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="8ec38-181">Czasy przezbrajania są często uwzględniane w cenach obliczanych dla towarów.</span><span class="sxs-lookup"><span data-stu-id="8ec38-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="8ec38-182">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8ec38-182">Click Save.</span></span>
6. <span data-ttu-id="8ec38-183">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8ec38-183">Close the page.</span></span>

