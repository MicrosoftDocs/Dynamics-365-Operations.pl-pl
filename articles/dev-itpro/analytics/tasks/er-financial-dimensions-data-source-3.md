--- 
title: "Projektowanie raportu w celu używania wymiarów finansowych jako źródła danych na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 178deb75bec9ee7c9c355b06850f7f771bac8704
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="design-a-report-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="02d48-103">Projektowanie raportu w celu używania wymiarów finansowych jako źródła danych na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="02d48-103">Design a report to use financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="02d48-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="02d48-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="02d48-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="02d48-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="02d48-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 2: Mapowanie modelu)”.</span><span class="sxs-lookup"><span data-stu-id="02d48-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="02d48-107">Projektowania raportu w celu przedstawienia wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="02d48-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="02d48-108">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="02d48-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="02d48-109">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="02d48-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="02d48-110">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02d48-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="02d48-111">W polu Nowy wpisz „Format oparty na modelu danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="02d48-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="02d48-112">Użyj utworzonego wcześniej modelu jako źródła danych dla nowego raportu.</span><span class="sxs-lookup"><span data-stu-id="02d48-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="02d48-113">W polu Nazwa wpisz „Raport arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="02d48-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="02d48-114">W polu Definicja modelu danych zaznacz wartość Wpis.</span><span class="sxs-lookup"><span data-stu-id="02d48-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="02d48-115">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="02d48-115">Click Create configuration.</span></span>
8. <span data-ttu-id="02d48-116">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="02d48-116">Click Designer.</span></span>
9. <span data-ttu-id="02d48-117">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02d48-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="02d48-118">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="02d48-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="02d48-119">W polu Nazwa wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="02d48-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="02d48-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-120">Click OK.</span></span>
13. <span data-ttu-id="02d48-121">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02d48-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="02d48-122">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="02d48-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="02d48-123">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="02d48-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="02d48-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-124">Click OK.</span></span>
17. <span data-ttu-id="02d48-125">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02d48-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="02d48-126">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="02d48-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="02d48-127">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="02d48-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="02d48-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-128">Click OK.</span></span>
21. <span data-ttu-id="02d48-129">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="02d48-130">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02d48-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="02d48-131">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="02d48-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="02d48-132">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="02d48-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="02d48-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-133">Click OK.</span></span>
26. <span data-ttu-id="02d48-134">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02d48-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="02d48-135">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="02d48-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="02d48-136">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="02d48-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="02d48-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-137">Click OK.</span></span>
30. <span data-ttu-id="02d48-138">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="02d48-139">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02d48-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="02d48-140">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="02d48-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="02d48-141">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="02d48-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="02d48-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-142">Click OK.</span></span>
35. <span data-ttu-id="02d48-143">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="02d48-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="02d48-144">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="02d48-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="02d48-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-145">Click OK.</span></span>
38. <span data-ttu-id="02d48-146">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="02d48-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="02d48-147">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="02d48-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="02d48-148">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-148">Click OK.</span></span>
41. <span data-ttu-id="02d48-149">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="02d48-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="02d48-150">W polu Nazwa wpisz „Dt”.</span><span class="sxs-lookup"><span data-stu-id="02d48-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="02d48-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-151">Click OK.</span></span>
44. <span data-ttu-id="02d48-152">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="02d48-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="02d48-153">W polu Nazwa wpisz „Ct”.</span><span class="sxs-lookup"><span data-stu-id="02d48-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="02d48-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-154">Click OK.</span></span>
47. <span data-ttu-id="02d48-155">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02d48-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="02d48-156">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="02d48-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="02d48-157">W polu Nazwa wpisz „Wymiary”.</span><span class="sxs-lookup"><span data-stu-id="02d48-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="02d48-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-158">Click OK.</span></span>
51. <span data-ttu-id="02d48-159">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="02d48-160">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02d48-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="02d48-161">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="02d48-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="02d48-162">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="02d48-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="02d48-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-163">Click OK.</span></span>
56. <span data-ttu-id="02d48-164">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="02d48-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="02d48-165">W polu Nazwa wpisz „Wartość”.</span><span class="sxs-lookup"><span data-stu-id="02d48-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="02d48-166">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-166">Click OK.</span></span>
59. <span data-ttu-id="02d48-167">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="02d48-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="02d48-168">W polu Nazwa wpisz „Op”.</span><span class="sxs-lookup"><span data-stu-id="02d48-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="02d48-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="02d48-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="02d48-170">Mapowanie elementów raportu na źródła danych</span><span class="sxs-lookup"><span data-stu-id="02d48-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="02d48-171">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="02d48-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="02d48-172">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="02d48-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="02d48-173">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="02d48-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="02d48-174">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="02d48-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="02d48-175">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="02d48-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="02d48-176">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Op: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="02d48-177">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Op: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="02d48-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="02d48-178">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-178">Click Bind.</span></span>
9. <span data-ttu-id="02d48-179">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Wartość: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="02d48-180">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Kod: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="02d48-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="02d48-181">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-181">Click Bind.</span></span>
12. <span data-ttu-id="02d48-182">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Kod: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="02d48-183">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Nazwa: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="02d48-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="02d48-184">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-184">Click Bind.</span></span>
15. <span data-ttu-id="02d48-185">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="02d48-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="02d48-186">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="02d48-187">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-187">Click Bind.</span></span>
18. <span data-ttu-id="02d48-188">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Ct: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="02d48-189">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Kredyt: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="02d48-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="02d48-190">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-190">Click Bind.</span></span>
21. <span data-ttu-id="02d48-191">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Dt: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="02d48-192">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Debet: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="02d48-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="02d48-193">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-193">Click Bind.</span></span>
24. <span data-ttu-id="02d48-194">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Waluta: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="02d48-195">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Waluta: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="02d48-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="02d48-196">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-196">Click Bind.</span></span>
27. <span data-ttu-id="02d48-197">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Data: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="02d48-198">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Data: Data”.</span><span class="sxs-lookup"><span data-stu-id="02d48-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="02d48-199">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-199">Click Bind.</span></span>
30. <span data-ttu-id="02d48-200">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Załącznik: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="02d48-201">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Załącznik: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="02d48-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="02d48-202">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-202">Click Bind.</span></span>
33. <span data-ttu-id="02d48-203">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="02d48-204">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="02d48-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="02d48-205">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-205">Click Bind.</span></span>
36. <span data-ttu-id="02d48-206">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Partia: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="02d48-207">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Partia: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="02d48-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="02d48-208">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-208">Click Bind.</span></span>
39. <span data-ttu-id="02d48-209">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="02d48-210">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="02d48-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="02d48-211">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-211">Click Bind.</span></span>
42. <span data-ttu-id="02d48-212">W drzewie zaznacz element „Element główny: Element XML\Firma: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="02d48-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="02d48-213">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Firma: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="02d48-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="02d48-214">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="02d48-214">Click Bind.</span></span>
45. <span data-ttu-id="02d48-215">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="02d48-215">Click Save.</span></span>
46. <span data-ttu-id="02d48-216">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="02d48-216">Close the page.</span></span>


