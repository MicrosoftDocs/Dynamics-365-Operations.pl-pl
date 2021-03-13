---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 3 — Projektowanie raportu)
description: W tym temacie opisano sposób konfigurowania modelu raportowania elektronicznego w celu używania wymiarów finansowych jako źródła danych dla raportów ER. (część 3)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0d6da96850e04d5e975b3febbfae2737c8a86af
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092307"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="ad98c-104">ER Używanie wymiarów finansowych jako źródła danych (Część 3 — Projektowanie raportu)</span><span class="sxs-lookup"><span data-stu-id="ad98c-104">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ad98c-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="ad98c-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="ad98c-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="ad98c-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="ad98c-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 2: Mapowanie modelu)”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="ad98c-108">Projektowania raportu w celu przedstawienia wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="ad98c-108">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="ad98c-109">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="ad98c-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="ad98c-110">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="ad98c-111">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ad98c-111">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="ad98c-112">W polu Nowy wpisz „Format oparty na modelu danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-112">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="ad98c-113">Użyj utworzonego wcześniej modelu jako źródła danych dla nowego raportu.</span><span class="sxs-lookup"><span data-stu-id="ad98c-113">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="ad98c-114">W polu Nazwa wpisz „Raport arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-114">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="ad98c-115">W polu Definicja modelu danych zaznacz wartość Wpis.</span><span class="sxs-lookup"><span data-stu-id="ad98c-115">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="ad98c-116">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="ad98c-116">Click Create configuration.</span></span>
8. <span data-ttu-id="ad98c-117">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ad98c-117">Click Designer.</span></span>
9. <span data-ttu-id="ad98c-118">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ad98c-118">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="ad98c-119">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-119">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="ad98c-120">W polu Nazwa wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-120">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="ad98c-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-121">Click OK.</span></span>
13. <span data-ttu-id="ad98c-122">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ad98c-122">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="ad98c-123">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-123">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="ad98c-124">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-124">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="ad98c-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-125">Click OK.</span></span>
17. <span data-ttu-id="ad98c-126">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ad98c-126">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="ad98c-127">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-127">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="ad98c-128">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-128">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="ad98c-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-129">Click OK.</span></span>
21. <span data-ttu-id="ad98c-130">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-130">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="ad98c-131">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ad98c-131">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="ad98c-132">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-132">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="ad98c-133">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-133">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="ad98c-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-134">Click OK.</span></span>
26. <span data-ttu-id="ad98c-135">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ad98c-135">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="ad98c-136">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-136">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="ad98c-137">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-137">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="ad98c-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-138">Click OK.</span></span>
30. <span data-ttu-id="ad98c-139">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-139">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="ad98c-140">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ad98c-140">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="ad98c-141">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-141">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="ad98c-142">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-142">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="ad98c-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-143">Click OK.</span></span>
35. <span data-ttu-id="ad98c-144">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="ad98c-144">Click Add Attribute.</span></span>
36. <span data-ttu-id="ad98c-145">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-145">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="ad98c-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-146">Click OK.</span></span>
38. <span data-ttu-id="ad98c-147">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="ad98c-147">Click Add Attribute.</span></span>
39. <span data-ttu-id="ad98c-148">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-148">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="ad98c-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-149">Click OK.</span></span>
41. <span data-ttu-id="ad98c-150">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="ad98c-150">Click Add Attribute.</span></span>
42. <span data-ttu-id="ad98c-151">W polu Nazwa wpisz „Dt”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-151">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="ad98c-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-152">Click OK.</span></span>
44. <span data-ttu-id="ad98c-153">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="ad98c-153">Click Add Attribute.</span></span>
45. <span data-ttu-id="ad98c-154">W polu Nazwa wpisz „Ct”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-154">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="ad98c-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-155">Click OK.</span></span>
47. <span data-ttu-id="ad98c-156">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ad98c-156">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="ad98c-157">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-157">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="ad98c-158">W polu Nazwa wpisz „Wymiary”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-158">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="ad98c-159">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-159">Click OK.</span></span>
51. <span data-ttu-id="ad98c-160">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-160">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="ad98c-161">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ad98c-161">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="ad98c-162">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-162">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="ad98c-163">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-163">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="ad98c-164">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-164">Click OK.</span></span>
56. <span data-ttu-id="ad98c-165">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="ad98c-165">Click Add Attribute.</span></span>
57. <span data-ttu-id="ad98c-166">W polu Nazwa wpisz „Wartość”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-166">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="ad98c-167">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-167">Click OK.</span></span>
59. <span data-ttu-id="ad98c-168">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="ad98c-168">Click Add Attribute.</span></span>
60. <span data-ttu-id="ad98c-169">W polu Nazwa wpisz „Op”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-169">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="ad98c-170">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ad98c-170">Click OK.</span></span>
<span data-ttu-id="ad98c-171">![Strona projektanta Operacji ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="ad98c-171">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="ad98c-172">Mapowanie elementów raportu na źródła danych</span><span class="sxs-lookup"><span data-stu-id="ad98c-172">Map report elements to data sources</span></span>
1. <span data-ttu-id="ad98c-173">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="ad98c-173">Click the Mapping tab.</span></span>
2. <span data-ttu-id="ad98c-174">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-174">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="ad98c-175">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="ad98c-176">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="ad98c-177">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-177">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="ad98c-178">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Op: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-178">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="ad98c-179">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Op: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-179">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="ad98c-180">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-180">Click Bind.</span></span>
9. <span data-ttu-id="ad98c-181">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Wartość: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-181">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="ad98c-182">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Kod: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-182">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="ad98c-183">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-183">Click Bind.</span></span>
12. <span data-ttu-id="ad98c-184">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Kod: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-184">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="ad98c-185">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Nazwa: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="ad98c-186">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-186">Click Bind.</span></span>
15. <span data-ttu-id="ad98c-187">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="ad98c-188">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="ad98c-189">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-189">Click Bind.</span></span>
18. <span data-ttu-id="ad98c-190">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Ct: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-190">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="ad98c-191">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Kredyt: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-191">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="ad98c-192">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-192">Click Bind.</span></span>
21. <span data-ttu-id="ad98c-193">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Dt: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-193">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="ad98c-194">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Debet: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-194">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="ad98c-195">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-195">Click Bind.</span></span>
24. <span data-ttu-id="ad98c-196">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Waluta: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-196">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="ad98c-197">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Waluta: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-197">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="ad98c-198">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-198">Click Bind.</span></span>
27. <span data-ttu-id="ad98c-199">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Data: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-199">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="ad98c-200">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Data: Data”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-200">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="ad98c-201">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-201">Click Bind.</span></span>
30. <span data-ttu-id="ad98c-202">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Załącznik: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-202">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="ad98c-203">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Załącznik: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-203">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="ad98c-204">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-204">Click Bind.</span></span>
33. <span data-ttu-id="ad98c-205">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-205">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="ad98c-206">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-206">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="ad98c-207">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-207">Click Bind.</span></span>
36. <span data-ttu-id="ad98c-208">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Partia: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-208">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="ad98c-209">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Partia: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-209">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="ad98c-210">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-210">Click Bind.</span></span>
39. <span data-ttu-id="ad98c-211">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-211">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="ad98c-212">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-212">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="ad98c-213">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-213">Click Bind.</span></span>
42. <span data-ttu-id="ad98c-214">W drzewie zaznacz element „Element główny: Element XML\Firma: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-214">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="ad98c-215">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Firma: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ad98c-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="ad98c-216">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="ad98c-216">Click Bind.</span></span>
45. <span data-ttu-id="ad98c-217">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ad98c-217">Click Save.</span></span>
46. <span data-ttu-id="ad98c-218">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ad98c-218">Close the page.</span></span>
<span data-ttu-id="ad98c-219">![Strona projektanta Operacji ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="ad98c-219">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

