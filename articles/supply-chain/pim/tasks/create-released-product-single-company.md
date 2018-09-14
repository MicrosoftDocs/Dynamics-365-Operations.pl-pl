--- 
title: Tworzenie zwolnionego produktu dla jednej firmy
description: Ta procedura prowadzi przez proces tworzenia jednego zwolnionego produktu w ramach jednej jednostki prawnej.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 9265ee4311ac89ae88ff7dd089519251828b1e3c
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-released-product-for-a-single-company"></a><span data-ttu-id="d8498-103">Tworzenie zwolnionego produktu dla jednej firmy</span><span class="sxs-lookup"><span data-stu-id="d8498-103">Create a released product for a single company</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d8498-104">Ta procedura prowadzi przez proces tworzenia jednego zwolnionego produktu w ramach jednej jednostki prawnej.</span><span class="sxs-lookup"><span data-stu-id="d8498-104">This procedure walks through how to create a single released product in the context of a single legal unit.</span></span> <span data-ttu-id="d8498-105">Po utworzeniu zwolnionego produktu jest on natychmiast dostępny tylko w tej jednostce.</span><span class="sxs-lookup"><span data-stu-id="d8498-105">After the released product is created,  it's immediately available in this unit only.</span></span> <span data-ttu-id="d8498-106">Instruktaż można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d8498-106">You can walk through this procedure in demo data company USMF.</span></span> <span data-ttu-id="d8498-107">To zadanie jest zwykle wykonywane przez konstruktora produktów.</span><span class="sxs-lookup"><span data-stu-id="d8498-107">This task is usually performed by a product designer.</span></span>


## <a name="create-a-released-product"></a><span data-ttu-id="d8498-108">Tworzenie zwolnionego produktu</span><span class="sxs-lookup"><span data-stu-id="d8498-108">Create a released product</span></span>
1. <span data-ttu-id="d8498-109">Przejdź do okna Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="d8498-109">Go to Released products.</span></span>
2. <span data-ttu-id="d8498-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d8498-110">Click New.</span></span>
3. <span data-ttu-id="d8498-111">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d8498-111">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="d8498-112">Jeśli w polu Numer produktu nie jest on automatycznie wprowadzony, wpisz unikatowy numer produktu.</span><span class="sxs-lookup"><span data-stu-id="d8498-112">If a product number is not automatically entered in the Product number field, type a unique product number.</span></span> <span data-ttu-id="d8498-113">Ten krok jest wymagany tylko wtedy, jeśli żadna sekwencja numerów nie została skonfigurowana dla numerów produktów.</span><span class="sxs-lookup"><span data-stu-id="d8498-113">This step is only  required if no number sequence has been set up for product numbers.</span></span>  
4. <span data-ttu-id="d8498-114">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d8498-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="d8498-115">Nazwa produktu jest ustawiona domyślnie jako alias.</span><span class="sxs-lookup"><span data-stu-id="d8498-115">The Product name is defaulted to the search name.</span></span> <span data-ttu-id="d8498-116">W razie potrzeby można zmienić alias.</span><span class="sxs-lookup"><span data-stu-id="d8498-116">If needed, you can select to change the search name.</span></span>  
5. <span data-ttu-id="d8498-117">W polu Grupa modeli towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-117">In the Item model group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-118">Grupy modeli produktu zawierają ustawienia określające sposób kontroli i obsługi towarów przy ich przyjmowaniu i wydawaniu.</span><span class="sxs-lookup"><span data-stu-id="d8498-118">The item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="d8498-119">Ustawienia określają także sposób obliczania zużycia towarów.</span><span class="sxs-lookup"><span data-stu-id="d8498-119">The settings also determine how the consumption of items are calculated.</span></span>  
6. <span data-ttu-id="d8498-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d8498-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-121">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d8498-122">W polu Grupa towarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-122">In the Item group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-123">Grupy produktów służą do zarządzania zapasami przez dzielenie towarów magazynowych na grupy na podstawie ich charakterystyk.</span><span class="sxs-lookup"><span data-stu-id="d8498-123">Item groups are used to manage inventory by dividing inventory items into groups based on item characteristics.</span></span> <span data-ttu-id="d8498-124">Na przykład, aby zarządzać sposobem księgowania informacji na kontach głównych, można utworzyć szereg różnych grup towarów skojarzonych z określonymi kontami głównymi.</span><span class="sxs-lookup"><span data-stu-id="d8498-124">For example, to manage how information is posted to main accounts, you can create a series of different item groups that are associated with specific main accounts.</span></span> <span data-ttu-id="d8498-125">Dzięki temu można śledzić zmienną fizyczną wartość zapasów dla towarów w różnych etapach.</span><span class="sxs-lookup"><span data-stu-id="d8498-125">This lets you track the inventory value of items at different stages.</span></span>  
9. <span data-ttu-id="d8498-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-126">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="d8498-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-127">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="d8498-128">W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-128">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-129">Wymiary magazynowania umożliwiają sterowanie sposobem przechowywania towarów w magazynie i sposobem ich pobierania.</span><span class="sxs-lookup"><span data-stu-id="d8498-129">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="d8498-130">Na przykład wymiar magazynowania może obejmować oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="d8498-130">For example, a storage dimension can be Site and Warehouse.</span></span>  
12. <span data-ttu-id="d8498-131">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-131">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="d8498-132">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-132">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="d8498-133">W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-133">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-134">Grupa wymiarów śledzenia określa wymiary śledzenia, które można dodawać do produktu.</span><span class="sxs-lookup"><span data-stu-id="d8498-134">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="d8498-135">Na przykład numer partii i numer seryjny mogą służyć do śledzenia pozycji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="d8498-135">For example, the batch number and serial number are used to track inventory items.</span></span>  
15. <span data-ttu-id="d8498-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-136">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="d8498-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-137">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="d8498-138">W polu Jednostka magazynowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-138">In the Inventory unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-139">Jednostka magazynowa określa sposób, w jaki produkt jest określany ilościowo podczas przechowywania w magazynie.</span><span class="sxs-lookup"><span data-stu-id="d8498-139">The inventory unit determines how the product is quantified when it's stored in inventory.</span></span>  
18. <span data-ttu-id="d8498-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-140">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="d8498-141">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-141">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="d8498-142">W polu Jednostka zakupu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-142">In the Purchase unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-143">Jednostka zakupu określa sposób, jaki produkt jest określany ilościowo podczas nabywana od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="d8498-143">The purchase unit determines how the product is quantified when it’s purchased from a vendor.</span></span>  
21. <span data-ttu-id="d8498-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-144">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="d8498-145">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-145">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="d8498-146">W polu Jednostka sprzedaży kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-146">In the Sales unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-147">Jednostka sprzedaży określa sposób, w jaki produkt jest określany ilościowo podczas sprzedaży do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d8498-147">The sales unit determines how the product is quantified when it’s sold to a customer.</span></span>  
24. <span data-ttu-id="d8498-148">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-148">In the list, find and select the desired record.</span></span>
25. <span data-ttu-id="d8498-149">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-149">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="d8498-150">W polu Jednostka BOM kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-150">In the BOM unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-151">Jednostka listy składowej (BOM) określa sposób, w jaki produkt jest określany ilościowo podczas dołączania go do listy składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="d8498-151">The BOM unit determines how the product is quantified when including it in a bill of materials (BOM).</span></span>  
27. <span data-ttu-id="d8498-152">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-152">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="d8498-153">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-153">In the list, click the link in the selected row.</span></span>
29. <span data-ttu-id="d8498-154">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-154">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-155">Grupa podatków dla produktu w grupie opodatkowania sprzedaży określa sposób obliczania podatku dla każdego towaru.</span><span class="sxs-lookup"><span data-stu-id="d8498-155">The item sales tax group in the Sales taxation group determines how sales tax is calculated for each item.</span></span>  
30. <span data-ttu-id="d8498-156">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-156">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="d8498-157">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-157">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="d8498-158">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-158">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d8498-159">Grupa podatków dla produktu w grupie opodatkowania zakupu określa sposób obliczania podatku dla każdego towaru.</span><span class="sxs-lookup"><span data-stu-id="d8498-159">The item sales tax group in the Purchase taxation group determines how purchase tax is calculated for each item.</span></span>  
33. <span data-ttu-id="d8498-160">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-160">In the list, find and select the desired record.</span></span>
34. <span data-ttu-id="d8498-161">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-161">In the list, click the link in the selected row.</span></span>
35. <span data-ttu-id="d8498-162">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d8498-162">Click OK.</span></span>

## <a name="add-product-characteristics"></a><span data-ttu-id="d8498-163">Dodawanie cech produktu</span><span class="sxs-lookup"><span data-stu-id="d8498-163">Add product characteristics</span></span>
1. <span data-ttu-id="d8498-164">Rozwiń lub zwiń sekcję Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="d8498-164">Expand or collapse the Manage inventory section.</span></span>
2. <span data-ttu-id="d8498-165">W polu Waga netto wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="d8498-165">In the Net weight field, enter a number.</span></span>
3. <span data-ttu-id="d8498-166">W polu Waga tara wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="d8498-166">In the Tare weight field, enter a number.</span></span>
4. <span data-ttu-id="d8498-167">W polu Długość brutto wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="d8498-167">In the Gross depth field, enter a number.</span></span>
5. <span data-ttu-id="d8498-168">W polu Szerokość brutto wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="d8498-168">In the Gross width field, enter a number.</span></span>
6. <span data-ttu-id="d8498-169">W polu Wysokość brutto wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="d8498-169">In the Gross height field, enter a number.</span></span>
7. <span data-ttu-id="d8498-170">W polu Objętość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="d8498-170">In the Volume field, enter a number.</span></span>

## <a name="add-financial-dimensions"></a><span data-ttu-id="d8498-171">Dodawanie wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="d8498-171">Add financial dimensions</span></span>
1. <span data-ttu-id="d8498-172">Rozwiń lub zwiń sekcję Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="d8498-172">Expand or collapse the Financial dimensions section.</span></span>
2. <span data-ttu-id="d8498-173">W polu BusinessUnit kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-173">In the BusinessUnit field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d8498-174">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-174">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="d8498-175">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-175">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d8498-176">W polu CostCenter kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-176">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="d8498-177">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-177">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d8498-178">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-178">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d8498-179">W polu Dział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-179">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="d8498-180">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-180">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="d8498-181">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-181">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="d8498-182">W polu ItemGroup kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8498-182">In the ItemGroup field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="d8498-183">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d8498-183">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="d8498-184">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8498-184">In the list, click the link in the selected row.</span></span>


