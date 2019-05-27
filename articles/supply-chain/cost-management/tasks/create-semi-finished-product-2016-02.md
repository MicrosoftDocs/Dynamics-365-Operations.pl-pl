---
title: Tworzenie półproduktu (tylko luty 2016)
description: To zadanie koncentruje się na tworzeniu półproduktu.
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
ms.openlocfilehash: 76fcba3732879f85c9bf0faa6d2481b9c5313a17
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563188"
---
# <a name="create-a-semi-finished-product-february-2016-only"></a><span data-ttu-id="48a2a-103">Tworzenie półproduktu (tylko luty 2016)</span><span class="sxs-lookup"><span data-stu-id="48a2a-103">Create a semi-finished product (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="48a2a-104">To zadanie koncentruje się na tworzeniu półproduktu.</span><span class="sxs-lookup"><span data-stu-id="48a2a-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="48a2a-105">Jest to drugie zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="48a2a-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="48a2a-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="48a2a-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="48a2a-107">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="48a2a-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="48a2a-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="48a2a-108">Click New.</span></span>
3. <span data-ttu-id="48a2a-109">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="48a2a-110">W tym przykładzie wpisz BOM_2.</span><span class="sxs-lookup"><span data-stu-id="48a2a-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="48a2a-111">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-112">Wybierz opcję STD.</span><span class="sxs-lookup"><span data-stu-id="48a2a-112">Select STD.</span></span> <span data-ttu-id="48a2a-113">STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.</span><span class="sxs-lookup"><span data-stu-id="48a2a-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="48a2a-114">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-115">Na przykład zaznacz pozycję Dźwięk.</span><span class="sxs-lookup"><span data-stu-id="48a2a-115">For example, select Audio.</span></span> <span data-ttu-id="48a2a-116">To nie ma wpływu na obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="48a2a-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="48a2a-117">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-118">Zaznacz pozycję SiteWH.</span><span class="sxs-lookup"><span data-stu-id="48a2a-118">Select SiteWH.</span></span> <span data-ttu-id="48a2a-119">W tym przykładzie będą wykorzystywane tylko oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="48a2a-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="48a2a-120">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-121">Wymiary śledzenia nie będą używane w tym przykładzie. Wybierz opcję Brak.</span><span class="sxs-lookup"><span data-stu-id="48a2a-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="48a2a-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="48a2a-122">Click OK.</span></span>
9. <span data-ttu-id="48a2a-123">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="48a2a-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="48a2a-124">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="48a2a-124">Click Default order settings.</span></span>
11. <span data-ttu-id="48a2a-125">W polu Domyślny typ zamówienia wybierz opcję „Produkcja”.</span><span class="sxs-lookup"><span data-stu-id="48a2a-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="48a2a-126">Ponieważ jest to półprodukt, który zostanie wytworzony, wybierz opcję Produkcja.</span><span class="sxs-lookup"><span data-stu-id="48a2a-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="48a2a-127">W polu Oddział zakupu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-128">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="48a2a-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="48a2a-129">W polu Oddział zapasów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-130">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="48a2a-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="48a2a-131">W polu Oddział sprzedaży wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-132">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="48a2a-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="48a2a-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="48a2a-133">Close the page.</span></span>
16. <span data-ttu-id="48a2a-134">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="48a2a-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="48a2a-135">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="48a2a-135">Click Item price.</span></span>
18. <span data-ttu-id="48a2a-136">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="48a2a-136">Click New.</span></span>
19. <span data-ttu-id="48a2a-137">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="48a2a-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="48a2a-138">W polu Wersja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-139">W tym przykładzie wybierz opcję Wersja 10.</span><span class="sxs-lookup"><span data-stu-id="48a2a-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="48a2a-140">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-141">W tym przykładzie wybierz opcję Oddział 1.</span><span class="sxs-lookup"><span data-stu-id="48a2a-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="48a2a-142">W polu cena ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="48a2a-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="48a2a-143">W tym przykładzie wpisz koszt własny 10.</span><span class="sxs-lookup"><span data-stu-id="48a2a-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="48a2a-144">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="48a2a-144">Click Save.</span></span>
24. <span data-ttu-id="48a2a-145">Kliknij opcję Aktywuj oczekujące ceny.</span><span class="sxs-lookup"><span data-stu-id="48a2a-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="48a2a-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="48a2a-146">Close the page.</span></span>
26. <span data-ttu-id="48a2a-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="48a2a-147">Close the page.</span></span>
27. <span data-ttu-id="48a2a-148">Kliknij pozycję BOM_2, aby otworzyć tę listę składową.</span><span class="sxs-lookup"><span data-stu-id="48a2a-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="48a2a-149">Rozwiń sekcję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="48a2a-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="48a2a-150">W polu Grupa kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="48a2a-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="48a2a-151">W tym przykładzie wybierz opcję Grupa kosztów M1.</span><span class="sxs-lookup"><span data-stu-id="48a2a-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="48a2a-152">Użyj skrótu do zapisywania rekordu.</span><span class="sxs-lookup"><span data-stu-id="48a2a-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="48a2a-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="48a2a-153">Close the page.</span></span>

