---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 3 — Projektowanie raportu)
description: W tym temacie opisano sposób konfigurowania modelu raportowania elektronicznego w celu używania wymiarów finansowych jako źródła danych dla raportów ER. (część 3)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a3b9a8b5775d2001f3384480e2f9593f2dfa8b1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752419"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="b7e3a-104">ER Używanie wymiarów finansowych jako źródła danych (Część 3 — Projektowanie raportu)</span><span class="sxs-lookup"><span data-stu-id="b7e3a-104">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b7e3a-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="b7e3a-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="b7e3a-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 2: Mapowanie modelu)”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="b7e3a-108">Projektowania raportu w celu przedstawienia wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="b7e3a-108">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="b7e3a-109">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="b7e3a-110">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="b7e3a-111">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-111">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="b7e3a-112">W polu Nowy wpisz „Format oparty na modelu danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-112">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="b7e3a-113">Użyj utworzonego wcześniej modelu jako źródła danych dla nowego raportu.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-113">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="b7e3a-114">W polu Nazwa wpisz „Raport arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-114">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="b7e3a-115">W polu Definicja modelu danych zaznacz wartość Wpis.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-115">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="b7e3a-116">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-116">Click Create configuration.</span></span>
8. <span data-ttu-id="b7e3a-117">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-117">Click Designer.</span></span>
9. <span data-ttu-id="b7e3a-118">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-118">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="b7e3a-119">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-119">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="b7e3a-120">W polu Nazwa wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-120">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="b7e3a-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-121">Click OK.</span></span>
13. <span data-ttu-id="b7e3a-122">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-122">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="b7e3a-123">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-123">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="b7e3a-124">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-124">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="b7e3a-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-125">Click OK.</span></span>
17. <span data-ttu-id="b7e3a-126">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-126">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="b7e3a-127">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-127">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="b7e3a-128">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-128">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="b7e3a-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-129">Click OK.</span></span>
21. <span data-ttu-id="b7e3a-130">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-130">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="b7e3a-131">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-131">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="b7e3a-132">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-132">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="b7e3a-133">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-133">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="b7e3a-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-134">Click OK.</span></span>
26. <span data-ttu-id="b7e3a-135">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-135">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="b7e3a-136">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-136">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="b7e3a-137">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-137">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="b7e3a-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-138">Click OK.</span></span>
30. <span data-ttu-id="b7e3a-139">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-139">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="b7e3a-140">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-140">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="b7e3a-141">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-141">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="b7e3a-142">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-142">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="b7e3a-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-143">Click OK.</span></span>
35. <span data-ttu-id="b7e3a-144">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-144">Click Add Attribute.</span></span>
36. <span data-ttu-id="b7e3a-145">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-145">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="b7e3a-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-146">Click OK.</span></span>
38. <span data-ttu-id="b7e3a-147">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-147">Click Add Attribute.</span></span>
39. <span data-ttu-id="b7e3a-148">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-148">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="b7e3a-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-149">Click OK.</span></span>
41. <span data-ttu-id="b7e3a-150">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-150">Click Add Attribute.</span></span>
42. <span data-ttu-id="b7e3a-151">W polu Nazwa wpisz „Dt”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-151">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="b7e3a-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-152">Click OK.</span></span>
44. <span data-ttu-id="b7e3a-153">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-153">Click Add Attribute.</span></span>
45. <span data-ttu-id="b7e3a-154">W polu Nazwa wpisz „Ct”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-154">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="b7e3a-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-155">Click OK.</span></span>
47. <span data-ttu-id="b7e3a-156">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-156">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="b7e3a-157">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-157">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="b7e3a-158">W polu Nazwa wpisz „Wymiary”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-158">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="b7e3a-159">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-159">Click OK.</span></span>
51. <span data-ttu-id="b7e3a-160">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-160">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="b7e3a-161">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-161">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="b7e3a-162">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-162">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="b7e3a-163">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-163">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="b7e3a-164">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-164">Click OK.</span></span>
56. <span data-ttu-id="b7e3a-165">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-165">Click Add Attribute.</span></span>
57. <span data-ttu-id="b7e3a-166">W polu Nazwa wpisz „Wartość”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-166">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="b7e3a-167">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-167">Click OK.</span></span>
59. <span data-ttu-id="b7e3a-168">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-168">Click Add Attribute.</span></span>
60. <span data-ttu-id="b7e3a-169">W polu Nazwa wpisz „Op”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-169">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="b7e3a-170">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-170">Click OK.</span></span>
<span data-ttu-id="b7e3a-171">![Strona projektanta Operacji ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="b7e3a-171">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="b7e3a-172">Mapowanie elementów raportu na źródła danych</span><span class="sxs-lookup"><span data-stu-id="b7e3a-172">Map report elements to data sources</span></span>
1. <span data-ttu-id="b7e3a-173">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-173">Click the Mapping tab.</span></span>
2. <span data-ttu-id="b7e3a-174">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-174">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="b7e3a-175">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="b7e3a-176">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="b7e3a-177">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-177">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="b7e3a-178">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Op: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-178">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="b7e3a-179">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Op: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-179">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="b7e3a-180">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-180">Click Bind.</span></span>
9. <span data-ttu-id="b7e3a-181">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Wartość: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-181">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="b7e3a-182">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Kod: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-182">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="b7e3a-183">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-183">Click Bind.</span></span>
12. <span data-ttu-id="b7e3a-184">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Kod: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-184">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="b7e3a-185">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Nazwa: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="b7e3a-186">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-186">Click Bind.</span></span>
15. <span data-ttu-id="b7e3a-187">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="b7e3a-188">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="b7e3a-189">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-189">Click Bind.</span></span>
18. <span data-ttu-id="b7e3a-190">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Ct: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-190">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="b7e3a-191">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Kredyt: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-191">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="b7e3a-192">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-192">Click Bind.</span></span>
21. <span data-ttu-id="b7e3a-193">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Dt: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-193">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="b7e3a-194">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Debet: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-194">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="b7e3a-195">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-195">Click Bind.</span></span>
24. <span data-ttu-id="b7e3a-196">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Waluta: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-196">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="b7e3a-197">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Waluta: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-197">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="b7e3a-198">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-198">Click Bind.</span></span>
27. <span data-ttu-id="b7e3a-199">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Data: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-199">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="b7e3a-200">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Data: Data”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-200">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="b7e3a-201">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-201">Click Bind.</span></span>
30. <span data-ttu-id="b7e3a-202">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Załącznik: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-202">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="b7e3a-203">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Załącznik: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-203">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="b7e3a-204">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-204">Click Bind.</span></span>
33. <span data-ttu-id="b7e3a-205">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-205">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="b7e3a-206">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-206">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="b7e3a-207">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-207">Click Bind.</span></span>
36. <span data-ttu-id="b7e3a-208">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Partia: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-208">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="b7e3a-209">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Partia: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-209">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="b7e3a-210">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-210">Click Bind.</span></span>
39. <span data-ttu-id="b7e3a-211">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-211">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="b7e3a-212">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-212">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="b7e3a-213">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-213">Click Bind.</span></span>
42. <span data-ttu-id="b7e3a-214">W drzewie zaznacz element „Element główny: Element XML\Firma: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-214">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="b7e3a-215">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Firma: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="b7e3a-216">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-216">Click Bind.</span></span>
45. <span data-ttu-id="b7e3a-217">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-217">Click Save.</span></span>
46. <span data-ttu-id="b7e3a-218">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b7e3a-218">Close the page.</span></span>
<span data-ttu-id="b7e3a-219">![Strona projektanta Operacji ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="b7e3a-219">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]