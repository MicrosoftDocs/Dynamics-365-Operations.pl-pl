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
ms.openlocfilehash: 77f1f2d6390a1d99b22d6eab9f0cae30f9760cc8
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550586"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="eaaac-103">ER Używanie wymiarów finansowych jako źródła danych (Część 3 — Projektowanie raportu)</span><span class="sxs-lookup"><span data-stu-id="eaaac-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eaaac-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="eaaac-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="eaaac-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="eaaac-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="eaaac-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 2: Mapowanie modelu)”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="eaaac-107">Projektowania raportu w celu przedstawienia wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="eaaac-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="eaaac-108">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="eaaac-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="eaaac-109">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="eaaac-110">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="eaaac-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="eaaac-111">W polu Nowy wpisz „Format oparty na modelu danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="eaaac-112">Użyj utworzonego wcześniej modelu jako źródła danych dla nowego raportu.</span><span class="sxs-lookup"><span data-stu-id="eaaac-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="eaaac-113">W polu Nazwa wpisz „Raport arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="eaaac-114">W polu Definicja modelu danych zaznacz wartość Wpis.</span><span class="sxs-lookup"><span data-stu-id="eaaac-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="eaaac-115">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="eaaac-115">Click Create configuration.</span></span>
8. <span data-ttu-id="eaaac-116">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="eaaac-116">Click Designer.</span></span>
9. <span data-ttu-id="eaaac-117">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="eaaac-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="eaaac-118">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="eaaac-119">W polu Nazwa wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="eaaac-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-120">Click OK.</span></span>
13. <span data-ttu-id="eaaac-121">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="eaaac-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="eaaac-122">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="eaaac-123">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="eaaac-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-124">Click OK.</span></span>
17. <span data-ttu-id="eaaac-125">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="eaaac-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="eaaac-126">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="eaaac-127">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="eaaac-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-128">Click OK.</span></span>
21. <span data-ttu-id="eaaac-129">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="eaaac-130">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="eaaac-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="eaaac-131">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="eaaac-132">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="eaaac-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-133">Click OK.</span></span>
26. <span data-ttu-id="eaaac-134">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="eaaac-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="eaaac-135">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="eaaac-136">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="eaaac-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-137">Click OK.</span></span>
30. <span data-ttu-id="eaaac-138">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="eaaac-139">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="eaaac-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="eaaac-140">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="eaaac-141">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="eaaac-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-142">Click OK.</span></span>
35. <span data-ttu-id="eaaac-143">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="eaaac-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="eaaac-144">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="eaaac-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-145">Click OK.</span></span>
38. <span data-ttu-id="eaaac-146">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="eaaac-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="eaaac-147">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="eaaac-148">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-148">Click OK.</span></span>
41. <span data-ttu-id="eaaac-149">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="eaaac-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="eaaac-150">W polu Nazwa wpisz „Dt”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="eaaac-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-151">Click OK.</span></span>
44. <span data-ttu-id="eaaac-152">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="eaaac-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="eaaac-153">W polu Nazwa wpisz „Ct”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="eaaac-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-154">Click OK.</span></span>
47. <span data-ttu-id="eaaac-155">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="eaaac-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="eaaac-156">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="eaaac-157">W polu Nazwa wpisz „Wymiary”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="eaaac-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-158">Click OK.</span></span>
51. <span data-ttu-id="eaaac-159">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="eaaac-160">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="eaaac-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="eaaac-161">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="eaaac-162">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="eaaac-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-163">Click OK.</span></span>
56. <span data-ttu-id="eaaac-164">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="eaaac-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="eaaac-165">W polu Nazwa wpisz „Wartość”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="eaaac-166">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-166">Click OK.</span></span>
59. <span data-ttu-id="eaaac-167">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="eaaac-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="eaaac-168">W polu Nazwa wpisz „Op”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="eaaac-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="eaaac-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="eaaac-170">Mapowanie elementów raportu na źródła danych</span><span class="sxs-lookup"><span data-stu-id="eaaac-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="eaaac-171">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="eaaac-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="eaaac-172">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="eaaac-173">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="eaaac-174">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="eaaac-175">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="eaaac-176">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Op: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="eaaac-177">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Op: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="eaaac-178">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-178">Click Bind.</span></span>
9. <span data-ttu-id="eaaac-179">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Wartość: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="eaaac-180">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Kod: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="eaaac-181">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-181">Click Bind.</span></span>
12. <span data-ttu-id="eaaac-182">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Kod: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="eaaac-183">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Nazwa: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="eaaac-184">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-184">Click Bind.</span></span>
15. <span data-ttu-id="eaaac-185">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="eaaac-186">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="eaaac-187">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-187">Click Bind.</span></span>
18. <span data-ttu-id="eaaac-188">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Ct: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="eaaac-189">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Kredyt: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="eaaac-190">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-190">Click Bind.</span></span>
21. <span data-ttu-id="eaaac-191">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Dt: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="eaaac-192">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Debet: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="eaaac-193">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-193">Click Bind.</span></span>
24. <span data-ttu-id="eaaac-194">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Waluta: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="eaaac-195">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Waluta: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="eaaac-196">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-196">Click Bind.</span></span>
27. <span data-ttu-id="eaaac-197">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Data: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="eaaac-198">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Data: Data”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="eaaac-199">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-199">Click Bind.</span></span>
30. <span data-ttu-id="eaaac-200">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Załącznik: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="eaaac-201">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Załącznik: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="eaaac-202">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-202">Click Bind.</span></span>
33. <span data-ttu-id="eaaac-203">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="eaaac-204">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="eaaac-205">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-205">Click Bind.</span></span>
36. <span data-ttu-id="eaaac-206">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Partia: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="eaaac-207">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Partia: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="eaaac-208">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-208">Click Bind.</span></span>
39. <span data-ttu-id="eaaac-209">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="eaaac-210">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="eaaac-211">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-211">Click Bind.</span></span>
42. <span data-ttu-id="eaaac-212">W drzewie zaznacz element „Element główny: Element XML\Firma: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="eaaac-213">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Firma: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="eaaac-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="eaaac-214">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="eaaac-214">Click Bind.</span></span>
45. <span data-ttu-id="eaaac-215">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="eaaac-215">Click Save.</span></span>
46. <span data-ttu-id="eaaac-216">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="eaaac-216">Close the page.</span></span>

