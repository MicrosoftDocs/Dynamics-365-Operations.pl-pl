---
title: Tworzenie zwolnionego produktu dla jednej firmy
description: Ta procedura prowadzi przez proces tworzenia jednego zwolnionego produktu w ramach jednej jednostki prawnej.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dfe93a3084bb8c7f2b181b35d393b8afdabb9f4b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258834"
---
# <a name="create-a-released-product-for-a-single-company"></a><span data-ttu-id="a52d2-103">Tworzenie zwolnionego produktu dla jednej firmy</span><span class="sxs-lookup"><span data-stu-id="a52d2-103">Create a released product for a single company</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a52d2-104">Ta procedura prowadzi przez proces tworzenia jednego zwolnionego produktu w ramach jednej jednostki prawnej.</span><span class="sxs-lookup"><span data-stu-id="a52d2-104">This procedure walks through how to create a single released product in the context of a single legal unit.</span></span> <span data-ttu-id="a52d2-105">Po utworzeniu zwolnionego produktu jest on natychmiast dostępny tylko w tej jednostce.</span><span class="sxs-lookup"><span data-stu-id="a52d2-105">After the released product is created,  it's immediately available in this unit only.</span></span> <span data-ttu-id="a52d2-106">Instruktaż można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="a52d2-106">You can walk through this procedure in demo data company USMF.</span></span> <span data-ttu-id="a52d2-107">To zadanie jest zwykle wykonywane przez konstruktora produktów.</span><span class="sxs-lookup"><span data-stu-id="a52d2-107">This task is usually performed by a product designer.</span></span>


## <a name="create-a-released-product"></a><span data-ttu-id="a52d2-108">Tworzenie zwolnionego produktu</span><span class="sxs-lookup"><span data-stu-id="a52d2-108">Create a released product</span></span>
1. <span data-ttu-id="a52d2-109">Przejdź do okna Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="a52d2-109">Go to Released products.</span></span>
2. <span data-ttu-id="a52d2-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a52d2-110">Click New.</span></span>
3. <span data-ttu-id="a52d2-111">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a52d2-111">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="a52d2-112">Jeśli w polu Numer produktu nie jest on automatycznie wprowadzony, wpisz unikatowy numer produktu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-112">If a product number is not automatically entered in the Product number field, type a unique product number.</span></span> <span data-ttu-id="a52d2-113">Ten krok jest wymagany tylko wtedy, jeśli żadna sekwencja numerów nie została skonfigurowana dla numerów produktów.</span><span class="sxs-lookup"><span data-stu-id="a52d2-113">This step is only  required if no number sequence has been set up for product numbers.</span></span>  
4. <span data-ttu-id="a52d2-114">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a52d2-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="a52d2-115">Nazwa produktu jest ustawiona domyślnie jako alias.</span><span class="sxs-lookup"><span data-stu-id="a52d2-115">The Product name is defaulted to the search name.</span></span> <span data-ttu-id="a52d2-116">W razie potrzeby można zmienić alias.</span><span class="sxs-lookup"><span data-stu-id="a52d2-116">If needed, you can select to change the search name.</span></span>  
5. <span data-ttu-id="a52d2-117">W polu Grupa modeli towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-117">In the Item model group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-118">Grupy modeli produktu zawierają ustawienia określające sposób kontroli i obsługi towarów przy ich przyjmowaniu i wydawaniu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-118">The item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="a52d2-119">Ustawienia określają także sposób obliczania zużycia towarów.</span><span class="sxs-lookup"><span data-stu-id="a52d2-119">The settings also determine how the consumption of items are calculated.</span></span>  
6. <span data-ttu-id="a52d2-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="a52d2-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-121">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a52d2-122">W polu Grupa towarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-122">In the Item group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-123">Grupy produktów służą do zarządzania zapasami przez dzielenie towarów magazynowych na grupy na podstawie ich charakterystyk.</span><span class="sxs-lookup"><span data-stu-id="a52d2-123">Item groups are used to manage inventory by dividing inventory items into groups based on item characteristics.</span></span> <span data-ttu-id="a52d2-124">Na przykład, aby zarządzać sposobem księgowania informacji na kontach głównych, można utworzyć szereg różnych grup towarów skojarzonych z określonymi kontami głównymi.</span><span class="sxs-lookup"><span data-stu-id="a52d2-124">For example, to manage how information is posted to main accounts, you can create a series of different item groups that are associated with specific main accounts.</span></span> <span data-ttu-id="a52d2-125">Dzięki temu można śledzić zmienną fizyczną wartość zapasów dla towarów w różnych etapach.</span><span class="sxs-lookup"><span data-stu-id="a52d2-125">This lets you track the inventory value of items at different stages.</span></span>  
9. <span data-ttu-id="a52d2-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-126">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="a52d2-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-127">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="a52d2-128">W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-128">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-129">Wymiary magazynowania umożliwiają sterowanie sposobem przechowywania towarów w magazynie i sposobem ich pobierania.</span><span class="sxs-lookup"><span data-stu-id="a52d2-129">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="a52d2-130">Na przykład wymiar magazynowania może obejmować oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="a52d2-130">For example, a storage dimension can be Site and Warehouse.</span></span>  
12. <span data-ttu-id="a52d2-131">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-131">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="a52d2-132">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-132">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="a52d2-133">W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-133">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-134">Grupa wymiarów śledzenia określa wymiary śledzenia, które można dodawać do produktu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-134">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="a52d2-135">Na przykład numer partii i numer seryjny mogą służyć do śledzenia pozycji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="a52d2-135">For example, the batch number and serial number are used to track inventory items.</span></span>  
15. <span data-ttu-id="a52d2-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-136">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="a52d2-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-137">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="a52d2-138">W polu Jednostka magazynowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-138">In the Inventory unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-139">Jednostka magazynowa określa sposób, w jaki produkt jest określany ilościowo podczas przechowywania w magazynie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-139">The inventory unit determines how the product is quantified when it's stored in inventory.</span></span>  
18. <span data-ttu-id="a52d2-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-140">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="a52d2-141">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-141">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="a52d2-142">W polu Jednostka zakupu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-142">In the Purchase unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-143">Jednostka zakupu określa sposób, jaki produkt jest określany ilościowo podczas nabywana od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="a52d2-143">The purchase unit determines how the product is quantified when it's purchased from a vendor.</span></span>  
21. <span data-ttu-id="a52d2-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-144">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="a52d2-145">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-145">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="a52d2-146">W polu Jednostka sprzedaży kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-146">In the Sales unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-147">Jednostka sprzedaży określa sposób, w jaki produkt jest określany ilościowo podczas sprzedaży do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="a52d2-147">The sales unit determines how the product is quantified when it's sold to a customer.</span></span>  
24. <span data-ttu-id="a52d2-148">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-148">In the list, find and select the desired record.</span></span>
25. <span data-ttu-id="a52d2-149">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-149">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="a52d2-150">W polu Jednostka BOM kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-150">In the BOM unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-151">Jednostka listy składowej (BOM) określa sposób, w jaki produkt jest określany ilościowo podczas dołączania go do listy składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="a52d2-151">The BOM unit determines how the product is quantified when including it in a bill of materials (BOM).</span></span>  
27. <span data-ttu-id="a52d2-152">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-152">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="a52d2-153">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-153">In the list, click the link in the selected row.</span></span>
29. <span data-ttu-id="a52d2-154">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-154">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-155">Grupa podatków dla produktu w grupie opodatkowania sprzedaży określa sposób obliczania podatku dla każdego towaru.</span><span class="sxs-lookup"><span data-stu-id="a52d2-155">The item sales tax group in the Sales taxation group determines how sales tax is calculated for each item.</span></span>  
30. <span data-ttu-id="a52d2-156">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-156">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="a52d2-157">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-157">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="a52d2-158">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-158">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a52d2-159">Grupa podatków dla produktu w grupie opodatkowania zakupu określa sposób obliczania podatku dla każdego towaru.</span><span class="sxs-lookup"><span data-stu-id="a52d2-159">The item sales tax group in the Purchase taxation group determines how purchase tax is calculated for each item.</span></span>  
33. <span data-ttu-id="a52d2-160">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-160">In the list, find and select the desired record.</span></span>
34. <span data-ttu-id="a52d2-161">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-161">In the list, click the link in the selected row.</span></span>
35. <span data-ttu-id="a52d2-162">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a52d2-162">Click OK.</span></span>

## <a name="add-product-characteristics"></a><span data-ttu-id="a52d2-163">Dodawanie cech produktu</span><span class="sxs-lookup"><span data-stu-id="a52d2-163">Add product characteristics</span></span>
1. <span data-ttu-id="a52d2-164">Rozwiń lub zwiń sekcję Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="a52d2-164">Expand or collapse the Manage inventory section.</span></span>
2. <span data-ttu-id="a52d2-165">W polu Waga netto wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="a52d2-165">In the Net weight field, enter a number.</span></span>
3. <span data-ttu-id="a52d2-166">W polu Waga tara wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="a52d2-166">In the Tare weight field, enter a number.</span></span>
4. <span data-ttu-id="a52d2-167">W polu Długość brutto wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a52d2-167">In the Gross depth field, enter a number.</span></span>
5. <span data-ttu-id="a52d2-168">W polu Szerokość brutto wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a52d2-168">In the Gross width field, enter a number.</span></span>
6. <span data-ttu-id="a52d2-169">W polu Wysokość brutto wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a52d2-169">In the Gross height field, enter a number.</span></span>
7. <span data-ttu-id="a52d2-170">W polu Objętość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="a52d2-170">In the Volume field, enter a number.</span></span>

## <a name="add-financial-dimensions"></a><span data-ttu-id="a52d2-171">Dodawanie wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="a52d2-171">Add financial dimensions</span></span>
1. <span data-ttu-id="a52d2-172">Rozwiń lub zwiń sekcję Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="a52d2-172">Expand or collapse the Financial dimensions section.</span></span>
2. <span data-ttu-id="a52d2-173">W polu BusinessUnit kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-173">In the BusinessUnit field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="a52d2-174">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-174">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="a52d2-175">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-175">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a52d2-176">W polu CostCenter kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-176">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a52d2-177">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-177">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="a52d2-178">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-178">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a52d2-179">W polu Dział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-179">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="a52d2-180">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-180">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="a52d2-181">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-181">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="a52d2-182">W polu ItemGroup kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a52d2-182">In the ItemGroup field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="a52d2-183">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a52d2-183">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="a52d2-184">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a52d2-184">In the list, click the link in the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]