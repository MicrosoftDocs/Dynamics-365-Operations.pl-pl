---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 3 — Projektowanie raportu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45096a728ad6f9e331b53b4e12ca0ff9317a3939
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "363000"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3-design-the-report"></a><span data-ttu-id="636a6-103">ER Używanie wymiarów finansowych jako źródła danych (Część 3: Projektowanie raportu)</span><span class="sxs-lookup"><span data-stu-id="636a6-103">ER Use financial dimensions as a data source (Part 3: Design the report)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="636a6-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="636a6-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="636a6-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="636a6-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="636a6-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 2: Mapowanie modelu)”.</span><span class="sxs-lookup"><span data-stu-id="636a6-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="636a6-107">Projektowania raportu w celu przedstawienia wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="636a6-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="636a6-108">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="636a6-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="636a6-109">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="636a6-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="636a6-110">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="636a6-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="636a6-111">W polu Nowy wpisz „Format oparty na modelu danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="636a6-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="636a6-112">Użyj utworzonego wcześniej modelu jako źródła danych dla nowego raportu.</span><span class="sxs-lookup"><span data-stu-id="636a6-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="636a6-113">W polu Nazwa wpisz „Raport arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="636a6-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="636a6-114">W polu Definicja modelu danych zaznacz wartość Wpis.</span><span class="sxs-lookup"><span data-stu-id="636a6-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="636a6-115">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="636a6-115">Click Create configuration.</span></span>
8. <span data-ttu-id="636a6-116">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="636a6-116">Click Designer.</span></span>
9. <span data-ttu-id="636a6-117">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="636a6-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="636a6-118">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="636a6-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="636a6-119">W polu Nazwa wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="636a6-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="636a6-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-120">Click OK.</span></span>
13. <span data-ttu-id="636a6-121">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="636a6-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="636a6-122">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="636a6-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="636a6-123">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="636a6-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="636a6-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-124">Click OK.</span></span>
17. <span data-ttu-id="636a6-125">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="636a6-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="636a6-126">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="636a6-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="636a6-127">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="636a6-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="636a6-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-128">Click OK.</span></span>
21. <span data-ttu-id="636a6-129">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="636a6-130">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="636a6-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="636a6-131">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="636a6-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="636a6-132">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="636a6-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="636a6-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-133">Click OK.</span></span>
26. <span data-ttu-id="636a6-134">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="636a6-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="636a6-135">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="636a6-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="636a6-136">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="636a6-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="636a6-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-137">Click OK.</span></span>
30. <span data-ttu-id="636a6-138">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="636a6-139">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="636a6-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="636a6-140">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="636a6-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="636a6-141">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="636a6-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="636a6-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-142">Click OK.</span></span>
35. <span data-ttu-id="636a6-143">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="636a6-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="636a6-144">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="636a6-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="636a6-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-145">Click OK.</span></span>
38. <span data-ttu-id="636a6-146">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="636a6-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="636a6-147">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="636a6-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="636a6-148">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-148">Click OK.</span></span>
41. <span data-ttu-id="636a6-149">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="636a6-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="636a6-150">W polu Nazwa wpisz „Dt”.</span><span class="sxs-lookup"><span data-stu-id="636a6-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="636a6-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-151">Click OK.</span></span>
44. <span data-ttu-id="636a6-152">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="636a6-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="636a6-153">W polu Nazwa wpisz „Ct”.</span><span class="sxs-lookup"><span data-stu-id="636a6-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="636a6-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-154">Click OK.</span></span>
47. <span data-ttu-id="636a6-155">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="636a6-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="636a6-156">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="636a6-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="636a6-157">W polu Nazwa wpisz „Wymiary”.</span><span class="sxs-lookup"><span data-stu-id="636a6-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="636a6-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-158">Click OK.</span></span>
51. <span data-ttu-id="636a6-159">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="636a6-160">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="636a6-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="636a6-161">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="636a6-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="636a6-162">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="636a6-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="636a6-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-163">Click OK.</span></span>
56. <span data-ttu-id="636a6-164">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="636a6-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="636a6-165">W polu Nazwa wpisz „Wartość”.</span><span class="sxs-lookup"><span data-stu-id="636a6-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="636a6-166">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-166">Click OK.</span></span>
59. <span data-ttu-id="636a6-167">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="636a6-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="636a6-168">W polu Nazwa wpisz „Op”.</span><span class="sxs-lookup"><span data-stu-id="636a6-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="636a6-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="636a6-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="636a6-170">Mapowanie elementów raportu na źródła danych</span><span class="sxs-lookup"><span data-stu-id="636a6-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="636a6-171">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="636a6-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="636a6-172">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="636a6-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="636a6-173">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="636a6-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="636a6-174">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="636a6-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="636a6-175">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="636a6-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="636a6-176">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Op: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="636a6-177">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Op: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="636a6-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="636a6-178">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-178">Click Bind.</span></span>
9. <span data-ttu-id="636a6-179">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Wartość: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="636a6-180">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Kod: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="636a6-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="636a6-181">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-181">Click Bind.</span></span>
12. <span data-ttu-id="636a6-182">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Kod: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="636a6-183">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Nazwa: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="636a6-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="636a6-184">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-184">Click Bind.</span></span>
15. <span data-ttu-id="636a6-185">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="636a6-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="636a6-186">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="636a6-187">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-187">Click Bind.</span></span>
18. <span data-ttu-id="636a6-188">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Ct: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="636a6-189">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Kredyt: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="636a6-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="636a6-190">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-190">Click Bind.</span></span>
21. <span data-ttu-id="636a6-191">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Dt: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="636a6-192">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Debet: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="636a6-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="636a6-193">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-193">Click Bind.</span></span>
24. <span data-ttu-id="636a6-194">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Waluta: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="636a6-195">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Waluta: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="636a6-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="636a6-196">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-196">Click Bind.</span></span>
27. <span data-ttu-id="636a6-197">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Data: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="636a6-198">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Data: Data”.</span><span class="sxs-lookup"><span data-stu-id="636a6-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="636a6-199">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-199">Click Bind.</span></span>
30. <span data-ttu-id="636a6-200">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Załącznik: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="636a6-201">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Załącznik: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="636a6-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="636a6-202">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-202">Click Bind.</span></span>
33. <span data-ttu-id="636a6-203">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="636a6-204">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="636a6-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="636a6-205">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-205">Click Bind.</span></span>
36. <span data-ttu-id="636a6-206">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Partia: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="636a6-207">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Partia: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="636a6-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="636a6-208">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-208">Click Bind.</span></span>
39. <span data-ttu-id="636a6-209">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="636a6-210">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="636a6-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="636a6-211">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-211">Click Bind.</span></span>
42. <span data-ttu-id="636a6-212">W drzewie zaznacz element „Element główny: Element XML\Firma: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="636a6-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="636a6-213">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Firma: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="636a6-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="636a6-214">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="636a6-214">Click Bind.</span></span>
45. <span data-ttu-id="636a6-215">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="636a6-215">Click Save.</span></span>
46. <span data-ttu-id="636a6-216">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="636a6-216">Close the page.</span></span>

