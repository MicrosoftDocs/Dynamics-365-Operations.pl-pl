---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 1 — Projektowanie modelu danych)
description: W tym temacie opisano sposób konfigurowania modelu raportowania elektronicznego w celu używania wymiarów finansowych jako źródła danych dla raportów ER. (część 1)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5ecae444d80698c03ac050b49894daa1b090f74
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570199"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="ac29e-104">ER Używanie wymiarów finansowych jako źródła danych (Część 1 — Projektowanie modelu danych)</span><span class="sxs-lookup"><span data-stu-id="ac29e-104">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ac29e-105">W poniższych krokach wyjaśniono, jak administrator systemu lub deweloper raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.</span><span class="sxs-lookup"><span data-stu-id="ac29e-105">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="ac29e-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="ac29e-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="ac29e-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-107">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="ac29e-108">Tworzenie nowego modelu danych</span><span class="sxs-lookup"><span data-stu-id="ac29e-108">Create a new data model</span></span>
1. <span data-ttu-id="ac29e-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="ac29e-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="ac29e-110">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="ac29e-110">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="ac29e-111">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="ac29e-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="ac29e-112">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="ac29e-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="ac29e-113">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-113">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="ac29e-114">W polu Nazwa wpisz „Wymiany finansowe przykładowego modelu”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-114">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="ac29e-115">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="ac29e-115">Click Create configuration.</span></span>
6. <span data-ttu-id="ac29e-116">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ac29e-116">Click Designer.</span></span>
7. <span data-ttu-id="ac29e-117">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="ac29e-118">W polu Nazwa wpisz „Wpis”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-118">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="ac29e-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-119">Click Add.</span></span>
10. <span data-ttu-id="ac29e-120">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-120">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="ac29e-121">W polu Nazwa wpisz „Firma”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-121">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="ac29e-122">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-122">Click Add.</span></span>
    * <span data-ttu-id="ac29e-123">Do naszego modelu dodamy nową listę rekordów.</span><span class="sxs-lookup"><span data-stu-id="ac29e-123">We will add to our model a new record list.</span></span> <span data-ttu-id="ac29e-124">Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) ustawienia wybranych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="ac29e-124">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="ac29e-125">Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi ustawienie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="ac29e-125">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="ac29e-126">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="ac29e-127">W polu Nazwa wpisz „Ustawienie wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-127">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="ac29e-128">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-128">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="ac29e-129">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-129">Click Add.</span></span>
17. <span data-ttu-id="ac29e-130">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-130">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="ac29e-131">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-131">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="ac29e-132">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-132">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="ac29e-133">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-133">Click Add.</span></span>
21. <span data-ttu-id="ac29e-134">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-134">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="ac29e-135">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-135">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="ac29e-136">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-136">Click Add.</span></span>
24. <span data-ttu-id="ac29e-137">W drzewie wybierz pozycję „Wpis”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-137">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="ac29e-138">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-138">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="ac29e-139">W polu Nazwa wpisz „Arkusz”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-139">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="ac29e-140">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-140">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="ac29e-141">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-141">Click Add.</span></span>
29. <span data-ttu-id="ac29e-142">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-142">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="ac29e-143">W polu Nazwa wpisz „Partia”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-143">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="ac29e-144">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-144">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="ac29e-145">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-145">Click Add.</span></span>
33. <span data-ttu-id="ac29e-146">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-146">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="ac29e-147">W polu Nazwa wpisz „Transakcja”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-147">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="ac29e-148">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-148">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="ac29e-149">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-149">Click Add.</span></span>
37. <span data-ttu-id="ac29e-150">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-150">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="ac29e-151">W polu Nazwa wpisz „Data”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-151">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="ac29e-152">W polu Typ elementu wybierz opcję „Data”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-152">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="ac29e-153">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-153">Click Add.</span></span>
41. <span data-ttu-id="ac29e-154">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-154">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="ac29e-155">W polu Nazwa wpisz „Debet”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-155">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="ac29e-156">W polu Typ elementu wybierz opcję „Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-156">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="ac29e-157">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-157">Click Add.</span></span>
45. <span data-ttu-id="ac29e-158">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-158">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="ac29e-159">W polu Nazwa wpisz „Kredyt”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-159">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="ac29e-160">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-160">Click Add.</span></span>
48. <span data-ttu-id="ac29e-161">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-161">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="ac29e-162">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-162">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="ac29e-163">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-163">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="ac29e-164">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-164">Click Add.</span></span>
52. <span data-ttu-id="ac29e-165">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-165">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="ac29e-166">W polu Nazwa wpisz „Załącznik”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-166">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="ac29e-167">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-167">Click Add.</span></span>
55. <span data-ttu-id="ac29e-168">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-168">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="ac29e-169">W polu Nazwa wpisz „Dane wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-169">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="ac29e-170">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-170">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="ac29e-171">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-171">Click Add.</span></span>
    * <span data-ttu-id="ac29e-172">Do naszego modelu dodaliśmy nową listę rekordów.</span><span class="sxs-lookup"><span data-stu-id="ac29e-172">We added to our model a new record list.</span></span> <span data-ttu-id="ac29e-173">Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) wartości wybranych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="ac29e-173">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="ac29e-174">Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi wartości wymiaru.</span><span class="sxs-lookup"><span data-stu-id="ac29e-174">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="ac29e-175">Nazwa wymiaru będzie również przedstawiana w tym rekordzie jako pole, które w razie potrzeby ma być używane na potrzeby wybierania.</span><span class="sxs-lookup"><span data-stu-id="ac29e-175">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="ac29e-176">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-176">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="ac29e-177">W polu Nazwa wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-177">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="ac29e-178">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-178">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="ac29e-179">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-179">Click Add.</span></span>
63. <span data-ttu-id="ac29e-180">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-180">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="ac29e-181">W polu Nazwa wpisz „Opis”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-181">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="ac29e-182">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-182">Click Add.</span></span>
66. <span data-ttu-id="ac29e-183">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ac29e-183">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="ac29e-184">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="ac29e-184">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="ac29e-185">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ac29e-185">Click Add.</span></span>
69. <span data-ttu-id="ac29e-186">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ac29e-186">Click Save.</span></span>
70. <span data-ttu-id="ac29e-187">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ac29e-187">Close the page.</span></span>

![Strona projektanta mapowania modelu danych ER](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]