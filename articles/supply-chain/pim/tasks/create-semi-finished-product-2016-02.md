---
title: Tworzenie półproduktu (luty 2016)
description: To zadanie koncentruje się na tworzeniu półproduktu.
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
ms.openlocfilehash: 9caeae552471eed1cb1d8630f387ca31107fcece
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "362862"
---
# <a name="create-a-semi-finished-product-february-2016"></a><span data-ttu-id="38808-103">Tworzenie półproduktu (luty 2016)</span><span class="sxs-lookup"><span data-stu-id="38808-103">Create a semi-finished product (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38808-104">To zadanie koncentruje się na tworzeniu półproduktu.</span><span class="sxs-lookup"><span data-stu-id="38808-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="38808-105">Jest to drugie zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="38808-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="38808-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="38808-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="38808-107">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="38808-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="38808-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="38808-108">Click New.</span></span>
3. <span data-ttu-id="38808-109">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="38808-110">W tym przykładzie wpisz BOM_2.</span><span class="sxs-lookup"><span data-stu-id="38808-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="38808-111">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-112">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="38808-112">Select STD.</span></span> <span data-ttu-id="38808-113">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="38808-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="38808-114">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-115">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="38808-115">For example, select Audio.</span></span> <span data-ttu-id="38808-116">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="38808-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="38808-117">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-118">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="38808-118">Select SiteWH.</span></span> <span data-ttu-id="38808-119">W tym przykładzie będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="38808-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="38808-120">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-121">Wymiary śledzenia nie będą używane w tym przykładzie. Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="38808-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="38808-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="38808-122">Click OK.</span></span>
9. <span data-ttu-id="38808-123">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="38808-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="38808-124">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="38808-124">Click Default order settings.</span></span>
11. <span data-ttu-id="38808-125">W polu Domyślny typ zamówienia wybierz opcję „Produkcja”.</span><span class="sxs-lookup"><span data-stu-id="38808-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="38808-126">Ponieważ jest to półprodukt, który zostanie wytworzony, wybierz opcję Produkcja.</span><span class="sxs-lookup"><span data-stu-id="38808-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="38808-127">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-128">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="38808-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="38808-129">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-130">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="38808-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="38808-131">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-132">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="38808-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="38808-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38808-133">Close the page.</span></span>
16. <span data-ttu-id="38808-134">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="38808-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="38808-135">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="38808-135">Click Item price.</span></span>
18. <span data-ttu-id="38808-136">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="38808-136">Click New.</span></span>
19. <span data-ttu-id="38808-137">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="38808-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="38808-138">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-139">W tym przykładzie wybierz opcję Wersja 10.</span><span class="sxs-lookup"><span data-stu-id="38808-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="38808-140">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-141">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="38808-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="38808-142">W polu cena ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="38808-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="38808-143">W tym przykładzie wpisz koszt własny 10.</span><span class="sxs-lookup"><span data-stu-id="38808-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="38808-144">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="38808-144">Click Save.</span></span>
24. <span data-ttu-id="38808-145">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="38808-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="38808-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38808-146">Close the page.</span></span>
26. <span data-ttu-id="38808-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38808-147">Close the page.</span></span>
27. <span data-ttu-id="38808-148">Kliknij pozycję BOM_2, aby otworzyć tę listę składową.</span><span class="sxs-lookup"><span data-stu-id="38808-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="38808-149">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="38808-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="38808-150">W polu Grupa kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="38808-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="38808-151">W tym przykładzie wybierz opcję Grupa kosztów M1.</span><span class="sxs-lookup"><span data-stu-id="38808-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="38808-152">Użyj skrótu do zapisywania rekordu.</span><span class="sxs-lookup"><span data-stu-id="38808-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="38808-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38808-153">Close the page.</span></span>

