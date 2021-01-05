---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 3 — Projektowanie raportu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.
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
ms.openlocfilehash: a12f88f1e8b5e451bc8a5c5486d820da61bf3ad0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684794"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="3e12e-103">ER Używanie wymiarów finansowych jako źródła danych (Część 3 — Projektowanie raportu)</span><span class="sxs-lookup"><span data-stu-id="3e12e-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3e12e-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="3e12e-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="3e12e-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="3e12e-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="3e12e-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 2: Mapowanie modelu)”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="3e12e-107">Projektowania raportu w celu przedstawienia wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="3e12e-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="3e12e-108">Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="3e12e-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="3e12e-109">W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="3e12e-110">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3e12e-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="3e12e-111">W polu Nowy wpisz „Format oparty na modelu danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="3e12e-112">Użyj utworzonego wcześniej modelu jako źródła danych dla nowego raportu.</span><span class="sxs-lookup"><span data-stu-id="3e12e-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="3e12e-113">W polu Nazwa wpisz „Raport arkusza księgi”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="3e12e-114">W polu Definicja modelu danych zaznacz wartość Wpis.</span><span class="sxs-lookup"><span data-stu-id="3e12e-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="3e12e-115">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="3e12e-115">Click Create configuration.</span></span>
8. <span data-ttu-id="3e12e-116">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="3e12e-116">Click Designer.</span></span>
9. <span data-ttu-id="3e12e-117">Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3e12e-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="3e12e-118">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="3e12e-119">W polu Nazwa wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="3e12e-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-120">Click OK.</span></span>
13. <span data-ttu-id="3e12e-121">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3e12e-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="3e12e-122">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="3e12e-123">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="3e12e-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-124">Click OK.</span></span>
17. <span data-ttu-id="3e12e-125">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3e12e-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="3e12e-126">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="3e12e-127">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="3e12e-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-128">Click OK.</span></span>
21. <span data-ttu-id="3e12e-129">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="3e12e-130">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3e12e-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="3e12e-131">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="3e12e-132">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="3e12e-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-133">Click OK.</span></span>
26. <span data-ttu-id="3e12e-134">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3e12e-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="3e12e-135">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="3e12e-136">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="3e12e-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-137">Click OK.</span></span>
30. <span data-ttu-id="3e12e-138">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="3e12e-139">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3e12e-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="3e12e-140">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="3e12e-141">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="3e12e-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-142">Click OK.</span></span>
35. <span data-ttu-id="3e12e-143">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="3e12e-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="3e12e-144">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="3e12e-145">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-145">Click OK.</span></span>
38. <span data-ttu-id="3e12e-146">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="3e12e-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="3e12e-147">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="3e12e-148">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-148">Click OK.</span></span>
41. <span data-ttu-id="3e12e-149">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="3e12e-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="3e12e-150">W polu Nazwa wpisz „Dt”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="3e12e-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-151">Click OK.</span></span>
44. <span data-ttu-id="3e12e-152">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="3e12e-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="3e12e-153">W polu Nazwa wpisz „Ct”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="3e12e-154">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-154">Click OK.</span></span>
47. <span data-ttu-id="3e12e-155">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3e12e-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="3e12e-156">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="3e12e-157">W polu Nazwa wpisz „Wymiary”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="3e12e-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-158">Click OK.</span></span>
51. <span data-ttu-id="3e12e-159">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="3e12e-160">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3e12e-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="3e12e-161">W drzewie zaznacz element „XML\Atrybut”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="3e12e-162">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="3e12e-163">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-163">Click OK.</span></span>
56. <span data-ttu-id="3e12e-164">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="3e12e-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="3e12e-165">W polu Nazwa wpisz „Wartość”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="3e12e-166">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-166">Click OK.</span></span>
59. <span data-ttu-id="3e12e-167">Kliknij opcję Dodaj atrybut.</span><span class="sxs-lookup"><span data-stu-id="3e12e-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="3e12e-168">W polu Nazwa wpisz „Op”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="3e12e-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3e12e-169">Click OK.</span></span>
<span data-ttu-id="3e12e-170">![Strona projektanta Operacji ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="3e12e-170">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="3e12e-171">Mapowanie elementów raportu na źródła danych</span><span class="sxs-lookup"><span data-stu-id="3e12e-171">Map report elements to data sources</span></span>
1. <span data-ttu-id="3e12e-172">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="3e12e-172">Click the Mapping tab.</span></span>
2. <span data-ttu-id="3e12e-173">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-173">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="3e12e-174">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="3e12e-175">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="3e12e-176">W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="3e12e-177">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Op: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-177">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="3e12e-178">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Op: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="3e12e-179">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-179">Click Bind.</span></span>
9. <span data-ttu-id="3e12e-180">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Wartość: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-180">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="3e12e-181">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Kod: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="3e12e-182">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-182">Click Bind.</span></span>
12. <span data-ttu-id="3e12e-183">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Kod: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-183">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="3e12e-184">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Nazwa: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="3e12e-185">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-185">Click Bind.</span></span>
15. <span data-ttu-id="3e12e-186">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-186">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="3e12e-187">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-187">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="3e12e-188">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-188">Click Bind.</span></span>
18. <span data-ttu-id="3e12e-189">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Ct: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-189">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="3e12e-190">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Kredyt: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="3e12e-191">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-191">Click Bind.</span></span>
21. <span data-ttu-id="3e12e-192">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Dt: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-192">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="3e12e-193">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Debet: Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="3e12e-194">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-194">Click Bind.</span></span>
24. <span data-ttu-id="3e12e-195">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Waluta: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-195">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="3e12e-196">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Waluta: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="3e12e-197">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-197">Click Bind.</span></span>
27. <span data-ttu-id="3e12e-198">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Data: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-198">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="3e12e-199">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Data: Data”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="3e12e-200">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-200">Click Bind.</span></span>
30. <span data-ttu-id="3e12e-201">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Załącznik: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-201">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="3e12e-202">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Załącznik: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="3e12e-203">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-203">Click Bind.</span></span>
33. <span data-ttu-id="3e12e-204">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-204">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="3e12e-205">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="3e12e-206">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-206">Click Bind.</span></span>
36. <span data-ttu-id="3e12e-207">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Partia: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-207">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="3e12e-208">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Partia: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-208">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="3e12e-209">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-209">Click Bind.</span></span>
39. <span data-ttu-id="3e12e-210">W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-210">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="3e12e-211">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-211">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="3e12e-212">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-212">Click Bind.</span></span>
42. <span data-ttu-id="3e12e-213">W drzewie zaznacz element „Element główny: Element XML\Firma: Atrybut XML”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-213">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="3e12e-214">W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Firma: Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="3e12e-214">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="3e12e-215">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="3e12e-215">Click Bind.</span></span>
45. <span data-ttu-id="3e12e-216">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3e12e-216">Click Save.</span></span>
46. <span data-ttu-id="3e12e-217">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3e12e-217">Close the page.</span></span>
<span data-ttu-id="3e12e-218">![Strona projektanta Operacji ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="3e12e-218">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

