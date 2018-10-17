--- 
title: Tworzenie list BOM (luty 2016)
description: "To zadanie koncentruje się na utworzeniu struktury list składowych wyrobu gotowego i półproduktu."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 6c5cfb8aae1a61d14f7a7969f688cb282530840d
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="create-boms-february-2016"></a><span data-ttu-id="3c331-103">Tworzenie list BOM (luty 2016)</span><span class="sxs-lookup"><span data-stu-id="3c331-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3c331-104">To zadanie koncentruje się na utworzeniu struktury list składowych wyrobu gotowego i półproduktu.</span><span class="sxs-lookup"><span data-stu-id="3c331-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="3c331-105">Jest to czwarte zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="3c331-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="3c331-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3c331-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="3c331-107">Tworzenie BOM dla półproduktu</span><span class="sxs-lookup"><span data-stu-id="3c331-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="3c331-108">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="3c331-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="3c331-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3c331-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3c331-110">Zaznacz towar o numerze BOM_2.</span><span class="sxs-lookup"><span data-stu-id="3c331-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="3c331-111">W okienku akcji kliknij pozycję Konstruuj.</span><span class="sxs-lookup"><span data-stu-id="3c331-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="3c331-112">Kliknij opcję Wersje BOM.</span><span class="sxs-lookup"><span data-stu-id="3c331-112">Click BOM versions.</span></span>
5. <span data-ttu-id="3c331-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3c331-113">Click New.</span></span>
6. <span data-ttu-id="3c331-114">Kliknij opcję BOM i wersja BOM.</span><span class="sxs-lookup"><span data-stu-id="3c331-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="3c331-115">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="3c331-116">Na przykład wpisz BOM_2.</span><span class="sxs-lookup"><span data-stu-id="3c331-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="3c331-117">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="3c331-118">W tym przykładzie wprowadź lub wybierz oddział 1.</span><span class="sxs-lookup"><span data-stu-id="3c331-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="3c331-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c331-119">Click OK.</span></span>
10. <span data-ttu-id="3c331-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3c331-120">Click New.</span></span>
11. <span data-ttu-id="3c331-121">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="3c331-122">W tym przykładzie wpisz ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="3c331-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="3c331-123">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="3c331-124">W tym przykładzie wprowadź lub wybierz wartość 11.</span><span class="sxs-lookup"><span data-stu-id="3c331-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="3c331-125">Kliknij nagłówek.</span><span class="sxs-lookup"><span data-stu-id="3c331-125">Click Header.</span></span>
14. <span data-ttu-id="3c331-126">Kliknij przycisk Zatwierdź, aby zatwierdzić listy składowe (BOM).</span><span class="sxs-lookup"><span data-stu-id="3c331-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="3c331-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c331-127">Click OK.</span></span>
16. <span data-ttu-id="3c331-128">Kliknij przycisk Zatwierdź.</span><span class="sxs-lookup"><span data-stu-id="3c331-128">Click Approve.</span></span>
    * <span data-ttu-id="3c331-129">Przycisk Zatwierdź znajduje się na pasku narzędzi w sekcji Wersje BOM.</span><span class="sxs-lookup"><span data-stu-id="3c331-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="3c331-130">Jeśli go nie widać, kliknij opcję Nagłówek w prawym górnym rogu strony Listy składowe (BOM), a przycisk powinien się pojawić.</span><span class="sxs-lookup"><span data-stu-id="3c331-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="3c331-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c331-131">Click OK.</span></span>
18. <span data-ttu-id="3c331-132">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="3c331-132">Click Activate.</span></span>
19. <span data-ttu-id="3c331-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3c331-133">Close the page.</span></span>
20. <span data-ttu-id="3c331-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3c331-134">Close the page.</span></span>
21. <span data-ttu-id="3c331-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3c331-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="3c331-136">Tworzenie BOM dla wyrobu gotowego</span><span class="sxs-lookup"><span data-stu-id="3c331-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="3c331-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3c331-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3c331-138">Zaznacz towar o numerze BOM_1.</span><span class="sxs-lookup"><span data-stu-id="3c331-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="3c331-139">W okienku akcji kliknij pozycję Konstruuj.</span><span class="sxs-lookup"><span data-stu-id="3c331-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="3c331-140">Kliknij opcję Wersje BOM.</span><span class="sxs-lookup"><span data-stu-id="3c331-140">Click BOM versions.</span></span>
4. <span data-ttu-id="3c331-141">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3c331-141">Click New.</span></span>
5. <span data-ttu-id="3c331-142">Kliknij opcję BOM i wersja BOM.</span><span class="sxs-lookup"><span data-stu-id="3c331-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="3c331-143">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="3c331-144">Na przykład wpisz BOM_1.</span><span class="sxs-lookup"><span data-stu-id="3c331-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="3c331-145">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="3c331-146">W tym przykładzie wprowadź lub wybierz oddział 1.</span><span class="sxs-lookup"><span data-stu-id="3c331-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="3c331-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c331-147">Click OK.</span></span>
9. <span data-ttu-id="3c331-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3c331-148">Click New.</span></span>
10. <span data-ttu-id="3c331-149">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="3c331-150">W tym przykładzie wpisz ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="3c331-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="3c331-151">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="3c331-152">W tym przykładzie wybierz opcję 11.</span><span class="sxs-lookup"><span data-stu-id="3c331-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="3c331-153">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3c331-153">Click New.</span></span>
13. <span data-ttu-id="3c331-154">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="3c331-155">W tym przykładzie wpisz ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="3c331-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="3c331-156">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="3c331-157">W tym przykładzie wprowadź lub wybierz wartość 11.</span><span class="sxs-lookup"><span data-stu-id="3c331-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="3c331-158">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3c331-158">Click New.</span></span>
16. <span data-ttu-id="3c331-159">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="3c331-160">W tym przykładzie wpisz BOM_2.</span><span class="sxs-lookup"><span data-stu-id="3c331-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="3c331-161">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3c331-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="3c331-162">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c331-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="3c331-163">W tym przykładzie wprowadź lub wybierz magazyn 11.</span><span class="sxs-lookup"><span data-stu-id="3c331-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="3c331-164">Kliknij nagłówek.</span><span class="sxs-lookup"><span data-stu-id="3c331-164">Click Header.</span></span>
20. <span data-ttu-id="3c331-165">Kliknij przycisk Zatwierdź, aby zatwierdzić listy składowe (BOM).</span><span class="sxs-lookup"><span data-stu-id="3c331-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="3c331-166">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c331-166">Click OK.</span></span>
22. <span data-ttu-id="3c331-167">Kliknij przycisk Zatwierdź.</span><span class="sxs-lookup"><span data-stu-id="3c331-167">Click Approve.</span></span>
    * <span data-ttu-id="3c331-168">Przycisk Zatwierdź znajduje się na pasku narzędzi w sekcji Wersje BOM.</span><span class="sxs-lookup"><span data-stu-id="3c331-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="3c331-169">Jeśli go nie widać, kliknij opcję Nagłówek w prawym górnym rogu strony Listy składowe (BOM), a przycisk powinien się pojawić.</span><span class="sxs-lookup"><span data-stu-id="3c331-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="3c331-170">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c331-170">Click OK.</span></span>
24. <span data-ttu-id="3c331-171">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="3c331-171">Click Activate.</span></span>
25. <span data-ttu-id="3c331-172">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3c331-172">Close the page.</span></span>
26. <span data-ttu-id="3c331-173">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3c331-173">Close the page.</span></span>
27. <span data-ttu-id="3c331-174">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3c331-174">Close the page.</span></span>


